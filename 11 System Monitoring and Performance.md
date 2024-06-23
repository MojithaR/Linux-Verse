# System Monitoring and Performance 📊

## Monitoring System Resources 🖥️

| Tool      | Description                                           |
|-----------|-------------------------------------------------------|
| `vmstat`  | Reports information about processes, memory, and CPU.  |
| `iostat`  | Reports CPU utilization and I/O statistics.            |
| `free`    | Displays amount of free and used memory in the system. |

## Disk Usage 📁

| Command   | Description                                           |
|-----------|-------------------------------------------------------|
| `df`      | Displays disk space usage of file systems.             |
| `du`      | Estimates file space usage.                            |

## Performance Tuning Basics ⚙️

- **Performance Monitoring**: Use tools to identify bottlenecks and optimize system performance.
- **System Optimization**: Adjust settings for better resource utilization and responsiveness.

### Examples
```bash
# Display system resource usage with vmstat
vmstat 1

# Show CPU and I/O statistics with iostat
iostat -c

# View memory usage with free
free -h

# Check disk space usage with df
df -h

# Estimate file space usage with du
du -sh /path/to/directory
```

### Summary

System monitoring and performance in Linux involve using tools like `vmstat`, `iostat`, and `free` to track resource usage such as CPU, memory, and disk. Commands like `df` and `du` provide insights into disk space availability and usage. Performance tuning enhances system efficiency through monitoring and optimization techniques, ensuring smooth operation and responsiveness.
