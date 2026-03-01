
# 🧠 DHCP Relay Design (VLAN 10-40)

To maintain the 'Zero Trust' model while centralizing resources, a DHCP Relay was required.

1. **The Problem:** DHCP Discovery is a Layer 2 broadcast. It cannot cross the boundaries of VLAN 10, 20, 30, or 40.
2. **The Solution:** The 'ip helper-address 10.0.50.10' command was applied to each SVI on the Core Switch.
3. **The Result:** The Core Switch intercepts the broadcast, converts it to a Unicast packet, and routes it specifically to the Server Farm in VLAN 50.
