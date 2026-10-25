# Open-Source VLSI Tool Investigation — Week 03

## 1. Tool Selected

**Tool:** OpenROAD  
**Track:** Physical Design (PD)

**Official documentation:**  
https://openroad.readthedocs.io/en/latest/

**Official flow documentation:**  
https://openroad-flow-scripts.readthedocs.io/en/latest/user/UserGuide.html

**Official website:** https://openroad.org/

**GitHub repository:** https://github.com/The-OpenROAD-Project/OpenROAD

## 2. Purpose of the Tool

OpenROAD is an open-source tool used for digital chip physical-design implementation. It supports different stages of the physical-design process, including floorplanning, placement, Clock Tree Synthesis (CTS), routing, and design optimization.

It helps users explore and automate parts of the digital chip implementation workflow.

## 3. Main Inputs

Depending on the design stage and flow configuration, OpenROAD-related workflows may use the following inputs:

- RTL or a synthesized gate-level netlist
- Timing constraints in SDC format
- Standard-cell library data
- Technology and physical-library data
- Floorplan information and flow configuration files

These inputs provide the design information, timing requirements, and technology details needed by the implementation flow.

## 4. Main Outputs

Depending on the stage and flow configuration, outputs may include:

- Intermediate physical-design databases
- Placement results
- Clock Tree Synthesis results
- Routing results
- Timing and other design reports
- Layout data, including GDSII through the overall RTL-to-GDS flow

These outputs help engineers examine the physical implementation and evaluate whether the design meets its requirements.

## 5. Basic Workflow

A simplified RTL-to-GDS implementation workflow is:

1. **Synthesis:** Converts RTL into a gate-level netlist.
2. **Floorplanning:** Defines the chip area and initial arrangement of major design elements.
3. **Placement:** Determines the locations of standard cells.
4. **Clock Tree Synthesis (CTS):** Builds the clock distribution network.
5. **Timing Optimization:** Improves the design to help meet timing requirements.
6. **Routing:** Creates the interconnections between design elements.
7. **Chip Finishing and Verification:** Performs final implementation tasks and checks the resulting design.

The exact sequence and available steps can vary depending on the flow configuration.

## 6. What I Explored

I explored the official OpenROAD documentation and the OpenROAD Flow Scripts User Guide to understand the tool's purpose and its role in the Physical Design workflow.

I focused on the major implementation stages, including floorplanning, placement, Clock Tree Synthesis, timing optimization, and routing.

I also learned that the complete flow uses design inputs, technology information, and timing constraints to generate implementation results and reports.

This exploration helped me understand the basic workflow of an open-source physical-design tool.

## 7. Potential AI/ML Application

One potential application of machine learning in Physical Design is predicting timing risks or placement congestion using historical design-run data.

For example, an ML model could learn from previous design runs using features such as cell utilization, estimated wire length, congestion indicators, and timing information. It could then identify new designs or regions that may require further investigation.

However, the model's predictions must be compared with actual implementation results and timing reports. The accuracy of predictions depends on the quality and relevance of the training data.

Machine learning can support engineering decisions, but it cannot replace detailed timing analysis and engineering verification.

## 8. Learning Outcome

Through this investigation, I learned that OpenROAD supports important stages of digital chip physical-design implementation. I gained a basic understanding of how synthesis, floorplanning, placement, CTS, timing optimization, and routing fit into the overall workflow.

As a Physical Design learner, I can use this knowledge to understand implementation tools and their reports more effectively.

I also learned that AI and machine learning could potentially help identify timing risks and congestion problems, provided that their predictions are evaluated using actual design data.

## 9. Limitations and Considerations

### Limitations

- **Learning Curve:** Beginners may find it difficult to understand the commands, configuration files, and physical-design concepts.
- **Setup Requirements:** Running the complete flow may require installing dependencies and configuring technology files, libraries, and design inputs correctly.
- **Design Dependence:** Results depend on the input netlist, timing constraints, technology libraries, and flow configuration.
- **Computational Resources:** Large designs may require significant memory, processing power, and execution time.
- **Verification Requirements:** Generated placement, routing, and timing results must be checked carefully to determine whether design requirements are satisfied.
- **Open-Source Ecosystem:** The available features, integrations, documentation, and support may differ from those of commercial EDA tools.

### Considerations

- Use the official documentation to understand the correct commands and workflow.
- Start with a small example design before attempting a complex design.
- Ensure that the required technology files, libraries, and timing constraints are correct.
- Review timing, congestion, and other design reports after implementation.
- Do not assume that a successful tool run automatically means the design meets all requirements.
- Treat AI/ML predictions as guidance and verify them against actual design results.
- Check tool versions and flow configuration because they can affect results.

### Summary

OpenROAD provides an opportunity to learn and explore digital Physical Design using open-source tools. However, successful use requires correct setup, suitable design inputs, sufficient computing resources, and careful verification of the results.

## 10. Sources and Verification

### Sources

1. **OpenROAD Official Documentation**  
   https://openroad.readthedocs.io/en/latest/  
   **Purpose:** Used to understand the purpose and capabilities of OpenROAD.

2. **OpenROAD Flow Scripts User Guide**  
   https://openroad-flow-scripts.readthedocs.io/en/latest/user/UserGuide.html  
   **Purpose:** Used to understand how Yosys, OpenROAD, and KLayout work together in an RTL-to-GDS flow.

3. **OpenROAD Flow Scripts Documentation**  
   https://openroad-flow-scripts.readthedocs.io/en/latest/  
   **Purpose:** Used to review setup requirements, supported platforms, and the basic implementation flow.

### Verification
The official documentation supports the main claims about OpenROAD's purpose and its role in the RTL-to-GDS workflow.

This verification was based on documentation review. I did not run a complete OpenROAD design flow, so I have not claimed any experimental results or measured performance.

I learned that reliable technical information should be checked against official documentation, and actual tool results should be examined before drawing conclusions about a design.

