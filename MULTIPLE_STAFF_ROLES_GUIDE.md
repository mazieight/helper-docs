# Multiple Staff Roles Enhancement

## Overview
The `!setrolestaff` command has been enhanced to support multiple staff roles instead of just one. This allows greater flexibility in assigning verification permissions to different role types.

## What Changed

### Before
```
!setrolestaff @Moderator    # Only one role could be set
```

### After
```
!setrolestaff @Moderator                           # Still works (single role)
!setrolestaff @Moderator @Admin @Helper           # NEW: Multiple roles!
!setrolestaff @Staff @Support @Moderator @VIP     # As many as you want!
```

## New Commands

### `!setrolestaff <role1> [role2] [role3] ...`
- **Function**: Sets multiple staff roles for verification commands
- **Permission**: Bot owner only
- **Examples**:
  - `!setrolestaff @Moderator`
  - `!setrolestaff @Moderator @Admin @Helper`
  - `!setrolestaff @Staff @Support @VIP @Premium`

### `!showrolestaff`
- **Function**: Shows all currently configured staff roles
- **Permission**: Anyone can use
- **Example output**: 
  ```
  📋 Current Staff Roles
  • @Moderator
  • @Admin  
  • @Helper
  • @Support
  ```

## Technical Implementation

### New Config Fields
- Added `staff_role_ids` array to store multiple role IDs
- Kept `staff_role_id` for backward compatibility

### New Helper Functions
- `get_staff_role_ids(ctx)`: Returns list of all staff role IDs
- `is_staff_member(member, ctx)`: Checks if member has any staff role

### Updated Commands
All verification commands now support multiple staff roles:
- `!vb` (verify boy)
- `!vg` (verify girl) 
- `!resetverif` (reset verification)
- `!removeverifrole` (remove verification role)
- `!sus` (suspend user)
- `!removesus` (remove suspension)

## Backward Compatibility
- Existing configurations with single staff role continue to work
- Old `staff_role_id` field is still supported and used as fallback
- No breaking changes for existing servers

## Usage Scenarios

### Scenario 1: Multiple Moderator Types
```
!setrolestaff @Moderator @SeniorMod @TrialMod @Helper
```
Now all these roles can use verification commands.

### Scenario 2: Department-Based Roles
```
!setrolestaff @VerificationTeam @SupportStaff @Management
```
Different departments can all help with verification.

### Scenario 3: Hierarchical Permissions
```
!setrolestaff @Admin @Moderator @Helper @Trainee
```
Multiple levels of staff can assist with verification tasks.

## Configuration Example
```json
{
  "verification": {
    "staff_role_id": 123456789,           // First role (backward compatibility)
    "staff_role_ids": [                   // New multiple roles field
      123456789,
      987654321, 
      456789123,
      789123456
    ]
  }
}
```
