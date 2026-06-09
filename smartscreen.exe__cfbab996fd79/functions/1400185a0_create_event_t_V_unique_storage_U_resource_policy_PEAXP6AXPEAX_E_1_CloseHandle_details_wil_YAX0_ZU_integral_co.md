# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1400185a0`
- end: `0x1400185fa`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007138`

## callees

- `0x140002d34`
- `0x1400185a0`
- `0x140018600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1400185ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1400185ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400185ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400185ce`

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
0x1400185a0  mov     [rsp+arg_0], rbx
0x1400185a5  push    rdi
0x1400185a6  sub     rsp, 20h
0x1400185aa  mov     rdi, rcx
0x1400185ad  mov     r9d, 1F0003h; dwDesiredAccess
0x1400185b3  xor     ecx, ecx; lpEventAttributes
0x1400185b5  xor     r8d, r8d; dwFlags
0x1400185b8  xor     edx, edx; lpName
0x1400185ba  call    cs:__imp_CreateEventExW
0x1400185c1  nop     dword ptr [rax+rax+00h]
0x1400185c6  mov     rbx, rax
0x1400185c9  test    rax, rax
0x1400185cc  jz      short loc_1400185E9
0x1400185ce  call    cs:__imp_GetLastError
0x1400185d5  nop     dword ptr [rax+rax+00h]
0x1400185da  mov     rdx, rbx
0x1400185dd  mov     rcx, rdi
0x1400185e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400185e5  xor     eax, eax
0x1400185e7  jmp     short loc_1400185EE
0x1400185e9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400185ee  mov     rbx, [rsp+28h+arg_0]
0x1400185f3  add     rsp, 20h
0x1400185f7  pop     rdi
0x1400185f8  retn
```
