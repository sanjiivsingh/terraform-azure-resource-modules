# Architecture Decision Records (ADR)

## ADR-001: Independent Granular Child Modules vs. Monolithic Module

### Context
Infrastructure teams frequently build monolithic modules that provision networks, compute, storage, and security in a single tightly-coupled module, creating blast-radius risks.

### Decision
Implement **Atomic Single-Responsibility Child Modules**:
- 11 independent modules (`azurerm_resource_group`, `azurerm_virtual_network`, `azurerm_subnet`, `azurerm_nsg`, `azurerm_nsg_association`, `azurerm_public_ip`, `azurerm_network_interface`, `azurerm_linux_virtual_machine`, `azurerm_bastion_host`, `azurerm_application_gateway`, `azurerm_key_vault`).
- Decoupled contracts communicating via explicit typed inputs and standardized outputs.

