# WsSendWnfNotification

- ea: `0x18002f320`
- end: `0x18002f353`
- name: `WsSendWnfNotification`
- size: `51`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180001710`
- `0x18002988c`

## callees

- `0x180007c80`

## import_xrefs

- `ntdll!ZwUpdateWnfStateData` at `0x18002f342`
- `ntdll!ZwUpdateWnfStateData` at `0x18002f342`

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
0x18002f320  sub     rsp, 48h
0x18002f324  xor     eax, eax
0x18002f326  lea     rcx, WNF_PNPA_VOLUMES_CHANGED
0x18002f32d  mov     [rsp+48h+var_18], eax
0x18002f331  xor     r9d, r9d
0x18002f334  mov     [rsp+48h+var_20], eax
0x18002f338  xor     r8d, r8d
0x18002f33b  xor     edx, edx
0x18002f33d  mov     [rsp+48h+var_28], rax
0x18002f342  call    cs:__imp_ZwUpdateWnfStateData
0x18002f348  mov     ecx, eax; Status
0x18002f34a  add     rsp, 48h
0x18002f34e  jmp     NetpNtStatusToApiStatus
```
