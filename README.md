HyperGate V 4.7

Proxmox Infrastructure Management & Inventory Extraction Tool:

🚀 The Mission

I am an Infrastructure guy driven by a single mission: To eliminate manual complexity through code.

In the modern data center, visibility and efficiency are non-negotiable. HyperGate is part of a larger vision to develop high-performance tools designed to solve the real-world bottlenecks encountered in daily operations.
My projects are built with a focus on speed, executive-level clarity, and seamless integration. I don’t just manage infrastructure; I build the software that makes infrastructure smarter.

🛡️ Security, Privacy & Antivirus

I built this tool to be transparent and secure. Here is the blunt truth:

Zero Data Sharing: HyperGate does NOT phone home. It does not send your cluster data, IPs, or credentials to any external server. Everything stays on your local machine.
Session-Based Auth: No credentials (usernames or passwords) are stored locally. Once you close the app, the session is gone.
Antivirus Flags: Because the tool extracts a required driver (opengl32.dll) and automatically restarts itself to initialize it, some aggressive Antivirus programs (CrowdStrike, SentinelOne) might flag it as "Self-Modifying."
   
The Fix: This is a false positive caused by the portability logic. If it gets blocked, simply whitelist the application folder.

4. Ghost Prevention: The tool creates a temporary .lock file to prevent "ghost" instances from running in the background.

🤝 The "Best Friend" Disclaimer

I’m giving you this tool like a true friend would—honestly and bluntly.
It’s Pro-Grade: It works on everything from Windows 10 to Windows Server 2022 because of the forced software rendering.
Be Patient: On the very first run, it will flash and close—don't panic. It's just setting up the environment. It will reopen itself in a second.
Don't Break It: Use the provided Excel template. If you mess up the column order, the engine will get confused. Stick to the plan.

☕ Why Support?

Your support fuels the research, lab environment, and development hours required to build and maintain this growing ecosystem of tools. Contributions go directly toward:

Innovation: Developing new modules for my infrastructure management suite.
Validation: Testing complex multi-vendor cluster scenarios in a dedicated lab.
Accessibility: Keeping my current and future tools accessible for the community.

If my work has saved you time or simplified your workflow, consider buying me a coffee to keep the innovation engine running.

📂 Configuration & Data Mapping

HyperGate is fueled by a local inventory file. To ensure your infrastructure tree builds correctly, you must follow the formatting standards.

Template: A sample file is provided in /documentation/Master_Inventory_Sample.xlsx.
The Rules: Read the /documentation/Excel_Formatting_Guide before filling out your data.

🔮 What’s Next?

This is just Phase 1. I am already working on the next evolution of the Proxmox ecosystem, including more advanced orchestration (migrations/actions) and deep observability layers.

Stay tuned. The infrastructure is getting smarter.

How to Run

Download HyperGate_V47.exe.

Place Master_Inventory.xlsx in the same folder.
Modify Master_Inventory.xlsx in the same folder, as per your Proxmox infrastructure.
Run HyperGate Tool.exe, agree to the terms, and enjoy !!

Developer: Inderjeet Singh
