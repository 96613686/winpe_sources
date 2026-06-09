# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18004d9ec`
- end: `0x18004da39`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004d038`
- `0x18004d168`

## callees

- `0x180015a04`
- `0x1800229b0`
- `0x18004d9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004da06`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004da06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004da14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004da14`

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
0x18004d9ec  mov     [rsp+arg_0], rbx
0x18004d9f1  push    rdi
0x18004d9f2  sub     rsp, 20h
0x18004d9f6  mov     rdi, rcx
0x18004d9f9  mov     r9d, 1F0003h; dwDesiredAccess
0x18004d9ff  xor     ecx, ecx; lpEventAttributes
0x18004da01  xor     r8d, r8d; dwFlags
0x18004da04  xor     edx, edx; lpName
0x18004da06  call    cs:__imp_CreateEventExW
0x18004da0c  mov     rbx, rax
0x18004da0f  test    rax, rax
0x18004da12  jz      short loc_18004DA29
0x18004da14  call    cs:__imp_GetLastError
0x18004da1a  mov     rdx, rbx
0x18004da1d  mov     rcx, rdi
0x18004da20  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004da25  xor     eax, eax
0x18004da27  jmp     short loc_18004DA2E
0x18004da29  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004da2e  mov     rbx, [rsp+28h+arg_0]
0x18004da33  add     rsp, 20h
0x18004da37  pop     rdi
0x18004da38  retn
```
