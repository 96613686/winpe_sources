# ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14003aa4c`
- end: `0x14003aadb`
- name: `?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `143`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400281f8`
- `0x140063c7c`
- `0x1400af510`
- `0x1400ef834`
- `0x1400f1f44`

## callees

- `0x14000ddac`
- `0x14000ea44`
- `0x14003aa4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14003aa68`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14003aa68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003aa9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003aa9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003aa76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003aa84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003aa76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003aa84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003aa8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003aa8f`

## string_xrefs

- `0x14003aab2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003aac9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        char a2)
{
  HANDLE Event; // rbp
  const char *v4; // r9
  void *v5; // rbx
  DWORD LastError; // esi
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v4);
  GetLastError();
  v5 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    SetLastError(LastError);
  }
  *a1 = Event;
}

```

## disassembly

```asm
0x14003aa4c  push    rbx
0x14003aa4e  push    rbp
0x14003aa4f  push    rsi
0x14003aa50  push    rdi
0x14003aa51  sub     rsp, 28h
0x14003aa55  and     edx, 3
0x14003aa58  mov     rdi, rcx
0x14003aa5b  mov     r8d, edx; dwFlags
0x14003aa5e  mov     r9d, 1F0003h; dwDesiredAccess
0x14003aa64  xor     edx, edx; lpName
0x14003aa66  xor     ecx, ecx; lpEventAttributes
0x14003aa68  call    cs:__imp_CreateEventExW
0x14003aa6e  mov     rbp, rax
0x14003aa71  test    rax, rax
0x14003aa74  jz      short loc_14003AAC4
0x14003aa76  call    cs:__imp_GetLastError
0x14003aa7c  mov     rbx, [rdi]
0x14003aa7f  test    rbx, rbx
0x14003aa82  jz      short loc_14003AAA1
0x14003aa84  call    cs:__imp_GetLastError
0x14003aa8a  mov     rcx, rbx; hObject
0x14003aa8d  mov     esi, eax
0x14003aa8f  call    cs:__imp_CloseHandle
0x14003aa95  test    eax, eax
0x14003aa97  jz      short loc_14003AAAD
0x14003aa99  mov     ecx, esi; dwErrCode
0x14003aa9b  call    cs:__imp_SetLastError
0x14003aaa1  mov     [rdi], rbp
0x14003aaa4  add     rsp, 28h
0x14003aaa8  pop     rdi
0x14003aaa9  pop     rsi
0x14003aaaa  pop     rbp
0x14003aaab  pop     rbx
0x14003aaac  retn
0x14003aaad  mov     rcx, [rsp+48h]; this
0x14003aab2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003aab9  mov     edx, 0A0Bh; void *
0x14003aabe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14003aac4  mov     rcx, [rsp+48h]; this
0x14003aac9  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003aad0  mov     edx, 1CC8h; void *
0x14003aad5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
