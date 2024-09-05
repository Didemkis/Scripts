A script that monitors available system resources.

```

#!/bin/bash
 
OUTPUT_FİLE="/root/system_usege.txt"

if [-f "$OUTPUT_FİLE"]; then
    echo "The old file is being searched and deleted."
    rm "$OUTPUT_FİLE"
fi

while true
do
    echo "System resources - $(date)" >> $OUTPUT_FİLE
    echo "-------------------------" >> $OUTPUT_FİLE

    top -b -n 1 >> $OUTPUT_FİLE
    echo "" >> $OUTPUT_FİLE
    echo "Updated. 10 counts are expected.."

    sleep 10 
done

```

The while true statement creates an infinite loop. The loop runs continuously until it is stopped.

top -b -n 1: This command outputs the current state of the system (CPU memory usage, etc.) in a text-based format (batch mode) at once (-n 1).
