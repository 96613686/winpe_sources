# WsSendWnfNotification

- ea: `0x180031f88`
- end: `0x180031fc1`
- name: `WsSendWnfNotification`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180001750`
- `0x18002bd5c`

## callees

- `0x1800081b0`

## import_xrefs

- `ntdll!ZwUpdateWnfStateData` at `0x180031faa`
- `ntdll!ZwUpdateWnfStateData` at `0x180031faa`

## pseudocode

```c
__int64 WsSendWnfNotification()
{
  NTSTATUS updated; // eax

  updated = ZwUpdateWnfStateData(&WNF_PNPA_VOLUMES_CHANGED, 0, 0, 0, 0, 0, 0);
  return NetpNtStatusToApiStatus(updated);
}

```

## disassembly

```asm
0x180031f88  sub     rsp, 48h
0x180031f8c  xor     eax, eax
0x180031f8e  lea     rcx, WNF_PNPA_VOLUMES_CHANGED
0x180031f95  mov     [rsp+48h+var_18], eax
0x180031f99  xor     r9d, r9d
0x180031f9c  mov     [rsp+48h+var_20], eax
0x180031fa0  xor     r8d, r8d
0x180031fa3  xor     edx, edx
0x180031fa5  mov     [rsp+48h+var_28], rax
0x180031faa  call    cs:__imp_ZwUpdateWnfStateData
0x180031fb1  nop     dword ptr [rax+rax+00h]
0x180031fb6  mov     ecx, eax; Status
0x180031fb8  add     rsp, 48h
0x180031fbc  jmp     NetpNtStatusToApiStatus
```
