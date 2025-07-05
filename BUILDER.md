# SHAFTT Builder Guide

## Overview

SHAFTT (Star Trek-inspired teleportation system) is a Minecraft mod that provides three distinct teleportation modules for server builds. Each module uses interactive acacia wall buttons and LCARS-style interfaces for project and location management.

## Core Modules

### Turbolift Module
Ship-based elevator system with deck organization.

**Blocks:** `turbolift_panel_tng`, `turbolift_panel_nem`, `turbolift_panel_tmp`, `turbolift_panel_nx`

**Workflow:**
1. **Create a Ship Project:**
   ```
   /turbolift create enterprise-d "USS Enterprise-D"
   ```

2. **Link Buttons to Decks:**
   ```
   /turbolift link enterprise-d 1 "Bridge"
   /turbolift link enterprise-d 2 "Engineering"
   /turbolift link enterprise-d 3 "Ten Forward"
   ```

**Creative Usage Examples:**
- **Dual Network System:** Create two separate turbolift networks on the same ship
  ```
  /turbolift create enterprise-main "Enterprise Main Lift"
  /turbolift create enterprise-emergency "Enterprise Emergency Lift"
  ```
  This mimics the Enterprise-D's battle bridge lift system

- **Deck-Based Organization:** Organize large ships by deck numbers
  ```
  /turbolift link defiant 1 "Bridge"
  /turbolift link defiant 2 "Engineering"
  /turbolift link defiant 3 "Crew Quarters"
  /turbolift link defiant 4 "Cargo Bay"
  ```

- **Multi-Ship Fleet:** Create separate projects for different ships
  ```
  /turbolift create voyager "USS Voyager"
  /turbolift create defiant "USS Defiant"
  /turbolift create ds9 "Deep Space Nine"
  ```

**Turbolift Commands:**

| Command | Description | Variables |
|---------|-------------|-----------|
| `/turbolift help [command]` | Show help or specific command help | `command` - Optional command name |
| `/turbolift create <id> <name>` | Create new ship project | `id` - Project ID (no spaces), `name` - Display name |
| `/turbolift link <project> <deck> [descriptor]` | Link button to deck | `project` - Project ID, `deck` - Deck number, `descriptor` - Optional description |
| `/turbolift list` | List all projects | None |
| `/turbolift info <project> [deck]` | Show project details | `project` - Project ID, `deck` - Optional deck filter |
| `/turbolift edit <deck> [descriptor]` | Edit button at current location | `deck` - Deck number, `descriptor` - Optional description |
| `/turbolift edit-build <project> <newName>` | Edit project display name | `project` - Project ID, `newName` - New display name |
| `/turbolift edit-button <project> <buttonId> <field> <value>` | Edit specific button | `project` - Project ID, `buttonId` - Button ID, `field` - Field name, `value` - New value |
| `/turbolift delete <project>` | Delete entire project | `project` - Project ID |
| `/turbolift unlink <project>` | Unlink button at current location | `project` - Project ID |
| `/turbolift unlink at <x> <y> <z>` | Unlink button at coordinates | `x,y,z` - Block coordinates |
| `/turbolift confirm` | Confirm pending action | None |

**Best Practices:**
- **Project IDs:** Use short, unique identifiers (e.g., "ENT_D", "VOY_V1", "DEFIANT")
- **Button Placement:** Place buttons near elevators and logical deck access points
- **Deck Organization:** Use consistent deck numbering across your ship
- **Maintenance:** Use `/turbolift list` to view current projects and `/turbolift info` for details

### Transporter Module
Teleportation system with project-based location management.

**Blocks:** `transporter_panel_tng`, `transporter_panel_nem`, `transporter_panel_tmp`

**Workflow:**
1. **Create a Project:**
   ```
   /transporter create voyager "USS Voyager"
   ```

2. **Add Teleportation Points:**
   ```
   /transporter add-location voyager "Bridge"
   /transporter add-location voyager "Engineering"
   /transporter add-location voyager "Cargo Bay"
   ```

**Creative Usage Examples:**
- **Multiple Transporter Rooms:** Create separate transporter systems for different areas
  ```
  /transporter create ds9-main "DS9 Main Transporter"
  /transporter create ds9-cargo "DS9 Cargo Transporter"
  ```

- **Emergency Transport System:** Set up backup transporter locations
  ```
  /transporter create enterprise-emergency "Enterprise Emergency Transport"
  /transporter add-location enterprise-emergency "Sickbay"
  /transporter add-location enterprise-emergency "Escape Pods"
  ```

- **Station-Ship Networks:** Connect space stations to ships
  ```
  /transporter create station-network "Station Network"
  /transporter add-location station-network "DS9 Ops"
  /transporter add-location station-network "Enterprise Bridge"
  /transporter add-location station-network "Voyager Bridge"
  ```

**Transporter Commands:**

| Command | Description | Variables |
|---------|-------------|-----------|
| `/transporter help [command]` | Show help or specific command help | `command` - Optional command name |
| `/transporter create <projectId> <name>` | Create new project | `projectId` - Project ID (no spaces), `name` - Display name |
| `/transporter add-location <projectId> <name>` | Add location to project | `projectId` - Project ID, `name` - Location name |
| `/transporter list [projectName]` | List projects or show details | `projectName` - Optional project name |
| `/transporter edit <projectId> project name <newName>` | Edit project display name | `projectId` - Project ID, `newName` - New display name |
| `/transporter edit <projectId> project location` | Edit project location | `projectId` - Project ID |
| `/transporter edit <projectId> location <locationId> name <newName>` | Edit location name | `projectId` - Project ID, `locationId` - Location ID, `newName` - New name |
| `/transporter edit <projectId> location <locationId> position` | Edit location position | `projectId` - Project ID, `locationId` - Location ID |
| `/transporter delete-location <projectId> <locationId>` | Delete location | `projectId` - Project ID, `locationId` - Location ID |
| `/transporter delete-project <projectId>` | Delete entire project | `projectId` - Project ID |

**Best Practices:**
- **Project IDs:** Use descriptive but unique identifiers (e.g., "DS9_MAIN", "ENT_EMERG", "VOY_V1")
- **Location Names:** Use clear, descriptive names that players will understand
- **Position Testing:** Test all teleportation points before finalizing builds
- **Organization:** Use `/transporter list` to manage your projects and locations

### Holodeck Module
Virtual reality simulation system with program management.

**Blocks:** `holodeck_panel_tng`, `holodeck_panel_nem`

**Workflow:**
1. **Create a Holodeck Project:**
   ```
   /holodeck create location enterprise-holodeck "Enterprise Holodeck"
   ```

2. **Create Programs:**
   ```
   /holodeck create program enterprise-holodeck "Sherlock Holmes"
   /holodeck create program enterprise-holodeck "Ancient Rome"
   /holodeck create program enterprise-holodeck "Beach Resort"
   ```

3. **Link Buttons to Programs:**
   ```
   /holodeck link enterprise-holodeck sherlock-holmes online
   /holodeck link enterprise-holodeck ancient-rome offline
   ```

**Creative Usage Examples:**
- **Multiple Holodeck Suites:** Create separate holodeck areas for different purposes
  ```
  /holodeck create location enterprise-recreation "Enterprise Recreation"
  /holodeck create location enterprise-training "Enterprise Training"
  ```

- **Emergency Programs:** Set up safety and emergency programs
  ```
  /holodeck create program enterprise-safety "Emergency Protocol Alpha"
  /holodeck create program enterprise-safety "Medical Training"
  ```

**Holodeck Commands:**

| Command | Description | Variables |
|---------|-------------|-----------|
| `/holodeck help [command]` | Show help or specific command help | `command` - Optional command name |
| `/holodeck create <type> <projectId> <name>` | Create project or program | `type` - "project", "online", or "offline", `projectId` - Project ID, `name` - Name |
| `/holodeck list [projectId]` | List projects or show details | `projectId` - Optional project ID |
| `/holodeck link <projectId> <locationId> <state>` | Link button to program | `projectId` - Project ID, `locationId` - Location ID, `state` - "online" or "offline" |
| `/holodeck unlink` | Unlink button at current location | None |
| `/holodeck info` | Show button information | None |
| `/holodeck edit project <projectId> <field> <value>` | Edit project | `projectId` - Project ID, `field` - "display_name" or "location", `value` - New value |
| `/holodeck edit panel <projectId> <panelId> location` | Edit panel location | `projectId` - Project ID, `panelId` - Panel ID |
| `/holodeck delete <type> <projectId> <name>` | Delete project or program | `type` - "project", "online", or "offline", `projectId` - Project ID, `name` - Name |
| `/holodeck confirm` | Confirm pending action | None |

**Best Practices:**
- **Project IDs:** Use unique identifiers with purpose (e.g., "ENT_REC", "VOY_TRAIN", "DEF_SAFETY")
- **Program Organization:** Group programs by purpose (recreation, training, safety)
- **Button Placement:** Place buttons in logical holodeck access areas
- **State Management:** Use online/offline states to control program availability

## Build Integration

### Block Placement
1. Place acacia wall buttons in your build
2. Use appropriate panel blocks for each module
3. Ensure buttons are accessible and visible

### Project Setup Examples

**Dual Turbolift Network Setup:**
```
/turbolift create ent-main "Enterprise Main Lift"
/turbolift create ent-emerg "Enterprise Emergency Lift"
/turbolift link ent-main 1 "Bridge"
/turbolift link ent-main 2 "Engineering"
/turbolift link ent-emerg 1 "Battle Bridge"
/turbolift link ent-emerg 2 "Emergency Engineering"
```

**Multi-Station Transporter Network:**
```
/transporter create ds9-main "DS9 Main Transporter"
/transporter create ds9-cargo "DS9 Cargo Transporter"
/transporter add-location ds9-main "Ops"
/transporter add-location ds9-main "Promenade"
/transporter add-location ds9-cargo "Cargo Bay 1"
/transporter add-location ds9-cargo "Cargo Bay 2"
```

**Recreation and Training Holodecks:**
```
/holodeck create location ent-rec "Enterprise Recreation"
/holodeck create location ent-train "Enterprise Training"
/holodeck create program ent-rec "Fair Haven"
/holodeck create program ent-rec "Sandrine's"
/holodeck create program ent-train "Bridge Simulator"
/holodeck create program ent-train "Engineering Simulator"
/holodeck link ent-rec fair-haven online
/holodeck link ent-train bridge-simulator online
```

### Project ID Guidelines

**Important:** Choose unique, short Project IDs to avoid conflicts and make management easier.

**Good Examples:**
- `ENT_D` - Enterprise-D
- `VOY_V1` - Voyager Variant 1
- `DEFIANT` - USS Defiant
- `DS9_MAIN` - DS9 Main Systems
- `MARTIN_VESTA` - Martin Vesta Class

**Avoid:**
- Generic names like `VOY` (multiple Voyagers)
- Very long names that are hard to type
- Names with spaces or special characters 