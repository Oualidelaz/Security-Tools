
# Macof Command Reference Table

## Basic Command Structure

```bash
macof [OPTIONS]
```

---

#### **Basic Options**

| Command        | Short Definition                                   |
| -------------- | -------------------------------------------------- |
| `-i interface` | Specify the network interface (e.g., eth0, en0)    |
| `-n count`     | Number of packets to generate (default: Unlimited) |
| `-s`           | Set Source IP/MAC                                  |
| `-d`           | Set Destination IP/MAC                             |
| `-x`           | Specify the source port                            |
| `-y`           | Specify the destination port                       |

---

## Common Usage Examples

| Command                        | Purpose                              |
| ------------------------------ | ------------------------------------ |
| `macof -i eth0`                | Flood the specified interface        |
| `macof -i eth0 -n 10000`       | Generate 10,000 flooding packets     |
| `macof -i eth0 -d 192.168.1.1` | Flood specific target destination IP |
| `macof -i eth0 -s 192.168.1.1` | Flood specific target source IP      |

---

⚠️ **Important Warning**:  
- Macof is a network stress testing tool.  
- It should only be used in authorized testing environments.  
- Use of this tool can cause network disruption.  
- Unauthorized use may be illegal.  
- **Use responsibly and with proper permission.**
