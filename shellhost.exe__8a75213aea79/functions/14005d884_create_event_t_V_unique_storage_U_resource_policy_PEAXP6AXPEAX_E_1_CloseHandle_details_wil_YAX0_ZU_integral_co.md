# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14005d884`
- end: `0x14005d8d5`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140053d50`

## callees

- `0x14000c118`
- `0x14005b270`
- `0x14005d884`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14005d8a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14005d8a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d8af`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2)
{
  void *v3; // rdx
  HANDLE Event; // rbx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x14005d884  mov     [rsp+arg_0], rbx
0x14005d889  push    rdi
0x14005d88a  sub     rsp, 20h
0x14005d88e  and     edx, 3
0x14005d891  mov     rdi, rcx
0x14005d894  mov     r8d, edx; dwFlags
0x14005d897  mov     r9d, 1F0003h; dwDesiredAccess
0x14005d89d  xor     edx, edx; lpName
0x14005d89f  xor     ecx, ecx; lpEventAttributes
0x14005d8a1  call    cs:__imp_CreateEventExW
0x14005d8a7  mov     rbx, rax
0x14005d8aa  test    rax, rax
0x14005d8ad  jz      short loc_14005D8CA
0x14005d8af  call    cs:__imp_GetLastError
0x14005d8b5  mov     rdx, rbx
0x14005d8b8  mov     rcx, rdi
0x14005d8bb  mov     rbx, [rsp+28h+arg_0]
0x14005d8c0  add     rsp, 20h
0x14005d8c4  pop     rdi
0x14005d8c5  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14005d8ca  mov     rcx, [rsp+28h]; this
0x14005d8cf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
