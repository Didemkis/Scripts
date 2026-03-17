A script that lists the available network connections.

```
#!/bin/bash

OUTPUT_FİLE =" /root/connection.txt"

if [-f "$OUTPUT_FİLE"]; then
    echo "The old file is being found and deleted."
    rm "$OUTPUT_FİLE"
fi

echo "Network Connections- $(date)" > $OUTPUT_FİLE
echo "------------------------------" >> $OUTPUT_FİLE

echo "Netstat Output:" >> $OUTPUT_FİLE
echo "----------------" >> $OUTPUT_FİLE
netstat -tulnp >> $OUTPUT_FİLE 2>&1
echo "" >> $OUTPUT_FİLE

echo "SS Output:" >> $OUTPUT_FİLE
echo "-----------" >> $OUTPUT_FİLE

```

CODE DESCRIPTION

#!/bin/bash: This specifies which shell to run the script with.

OUTPUT_FILE=‘/root/connections.txt’: Defines the path to the file to be created by the script.

if [ -f ‘$OUTPUT_FILE’ ]; then ... fi: If connections.txt already exists, the old file is deleted.

echo ‘Network Connections - $(date)’ > $OUTPUT_FILE: Adds date and time information at the beginning of the file.

The netstat -tulnp and ss -tulnp commands list the active connections using TCP/UDP protocols and the process information of these connections. The output is written to a file.

2>&1 is used to redirect standard error (stderr) to the same location as standard output (stdout). 





