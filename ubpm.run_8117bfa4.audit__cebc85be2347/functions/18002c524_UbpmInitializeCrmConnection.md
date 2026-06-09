# UbpmInitializeCrmConnection

- ea: `0x18002c524`
- end: `0x18002c568`
- name: `UbpmInitializeCrmConnection`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x18002c420`

## callees

- `0x18002c524`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002c551`
- `ntdll!RtlNtStatusToDosError` at `0x18002c551`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x18002c53f`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x18002c53f`

## string_xrefs

- `0x18002c52a`: `UBPM / Task Scheduler`

## pseudocode

```c
__int64 UbpmInitializeCrmConnection()
{
  unsigned int v0; // ebx
  NTSTATUS v1; // eax

  v0 = 0;
  v1 = CrmRegister(&g_CrmRegistrationHandle, 302, L"UBPM / Task Scheduler");
  if ( v1 < 0 )
    return RtlNtStatusToDosError(v1);
  return v0;
}

```

## disassembly

```asm
0x18002c524  push    rbx
0x18002c526  sub     rsp, 20h
0x18002c52a  lea     r8, aUbpmTaskSchedu; "UBPM / Task Scheduler"
0x18002c531  mov     edx, 12Eh
0x18002c536  lea     rcx, g_CrmRegistrationHandle
0x18002c53d  xor     ebx, ebx
0x18002c53f  call    cs:__imp_CrmRegister
0x18002c546  nop     dword ptr [rax+rax+00h]
0x18002c54b  test    eax, eax
0x18002c54d  jns     short loc_18002C55F
0x18002c54f  mov     ecx, eax; Status
0x18002c551  call    cs:__imp_RtlNtStatusToDosError
0x18002c558  nop     dword ptr [rax+rax+00h]
0x18002c55d  mov     ebx, eax
0x18002c55f  mov     eax, ebx
0x18002c561  add     rsp, 20h
0x18002c565  pop     rbx
0x18002c566  retn
```
