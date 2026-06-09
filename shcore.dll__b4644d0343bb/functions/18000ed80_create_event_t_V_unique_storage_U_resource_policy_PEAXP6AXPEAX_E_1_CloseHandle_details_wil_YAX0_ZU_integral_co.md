# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000ed80`
- end: `0x18000ede7`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000debc`
- `0x18000e988`

## callees

- `0x18000ed80`
- `0x18000f784`
- `0x18005bb30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000ed9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000ed9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000edd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000edd8`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        wil::details **a1,
        char a2)
{
  wil::details *v3; // rcx
  wil::details *Event; // rbp
  wil::details *v5; // rdi
  DWORD LastError; // ebx
  void *v8; // rdx

  Event = (wil::details *)CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v3);
  GetLastError();
  v5 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    wil::details::CloseHandle(v5, v8);
    SetLastError(LastError);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x18000ed80  push    rbx
0x18000ed82  push    rbp
0x18000ed83  push    rsi
0x18000ed84  push    rdi
0x18000ed85  sub     rsp, 28h
0x18000ed89  and     edx, 3
0x18000ed8c  mov     rsi, rcx
0x18000ed8f  mov     r8d, edx; dwFlags
0x18000ed92  mov     r9d, 1F0003h; dwDesiredAccess
0x18000ed98  xor     edx, edx; lpName
0x18000ed9a  xor     ecx, ecx; lpEventAttributes
0x18000ed9c  call    cs:__imp_CreateEventExW
0x18000eda2  mov     rbp, rax
0x18000eda5  test    rax, rax
0x18000eda8  jz      short loc_18000EDE0
0x18000edaa  call    cs:__imp_GetLastError
0x18000edb0  mov     rdi, [rsi]
0x18000edb3  test    rdi, rdi
0x18000edb6  jnz     short loc_18000EDC6
0x18000edb8  mov     [rsi], rbp
0x18000edbb  xor     eax, eax
0x18000edbd  add     rsp, 28h
0x18000edc1  pop     rdi
0x18000edc2  pop     rsi
0x18000edc3  pop     rbp
0x18000edc4  pop     rbx
0x18000edc5  retn
0x18000edc6  call    cs:__imp_GetLastError
0x18000edcc  mov     rcx, rdi; this
0x18000edcf  mov     ebx, eax
0x18000edd1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000edd6  mov     ecx, ebx; dwErrCode
0x18000edd8  call    cs:__imp_SetLastError
0x18000edde  jmp     short loc_18000EDB8
0x18000ede0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ede5  jmp     short loc_18000EDBD
```
