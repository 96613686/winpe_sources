# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180016498`
- end: `0x1800164e5`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800441b0`

## callees

- `0x180016498`
- `0x18002283c`
- `0x180022894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800164b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800164b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164c0`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return 0;
}

```

## disassembly

```asm
0x180016498  mov     [rsp+arg_0], rbx
0x18001649d  push    rdi
0x18001649e  sub     rsp, 20h
0x1800164a2  mov     rdi, rcx
0x1800164a5  mov     r9d, 1F0003h; dwDesiredAccess
0x1800164ab  xor     ecx, ecx; lpEventAttributes
0x1800164ad  xor     r8d, r8d; dwFlags
0x1800164b0  xor     edx, edx; lpName
0x1800164b2  call    cs:__imp_CreateEventExW
0x1800164b8  mov     rbx, rax
0x1800164bb  test    rax, rax
0x1800164be  jz      short loc_1800164D5
0x1800164c0  call    cs:__imp_GetLastError
0x1800164c6  mov     rdx, rbx
0x1800164c9  mov     rcx, rdi
0x1800164cc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800164d1  xor     eax, eax
0x1800164d3  jmp     short loc_1800164DA
0x1800164d5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800164da  mov     rbx, [rsp+28h+arg_0]
0x1800164df  add     rsp, 20h
0x1800164e3  pop     rdi
0x1800164e4  retn
```
