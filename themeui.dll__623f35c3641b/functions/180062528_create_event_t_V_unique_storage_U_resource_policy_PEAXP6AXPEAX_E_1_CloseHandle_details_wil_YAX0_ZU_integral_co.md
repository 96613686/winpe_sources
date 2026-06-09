# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180062528`
- end: `0x18006257d`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001de34`

## callees

- `0x18001fbd8`
- `0x18002f824`
- `0x180062528`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006254a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006254a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062558`

## string_xrefs

- `0x180062535`: `Global\ShellCreateObjectTaskReadyEvent`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, L"Global\\ShellCreateObjectTaskReadyEvent", 1u, 0x1F0003u);
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
0x180062528  mov     [rsp+arg_0], rbx
0x18006252d  push    rdi
0x18006252e  sub     rsp, 20h
0x180062532  mov     rdi, rcx
0x180062535  lea     rdx, Name; "Global\\ShellCreateObjectTaskReadyEvent"
0x18006253c  xor     ecx, ecx; lpEventAttributes
0x18006253e  mov     r9d, 1F0003h; dwDesiredAccess
0x180062544  mov     r8d, 1; dwFlags
0x18006254a  call    cs:__imp_CreateEventExW
0x180062550  mov     rbx, rax
0x180062553  test    rax, rax
0x180062556  jz      short loc_18006256D
0x180062558  call    cs:__imp_GetLastError
0x18006255e  mov     rdx, rbx
0x180062561  mov     rcx, rdi
0x180062564  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180062569  xor     eax, eax
0x18006256b  jmp     short loc_180062572
0x18006256d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180062572  mov     rbx, [rsp+28h+arg_0]
0x180062577  add     rsp, 20h
0x18006257b  pop     rdi
0x18006257c  retn
```
