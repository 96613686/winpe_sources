# ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18002e0d0`
- end: `0x18002e162`
- name: `?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013d84`
- `0x180030c78`
- `0x180033d60`
- `0x1800349a8`
- `0x1800648fc`
- `0x180090af0`

## callees

- `0x180008ea8`
- `0x18002e0d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002e0ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002e0ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e10d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e11b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e10d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e11b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e132`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e126`

## pseudocode

```c
char __fastcall _try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        char a2,
        const WCHAR *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  HANDLE Event; // rax
  HANDLE v6; // rbp
  void *v7; // rbx
  DWORD LastError; // esi
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(a4, a3, a2 & 3, 0x1F0003u);
  v6 = Event;
  if ( Event )
  {
    GetLastError();
    v7 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v7) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v9, v10);
      SetLastError(LastError);
    }
    *a1 = v6;
    LOBYTE(Event) = 1;
  }
  return (char)Event;
}

```

## disassembly

```asm
0x18002e0d0  mov     [rsp+arg_0], rbx
0x18002e0d5  mov     [rsp+arg_8], rbp
0x18002e0da  mov     [rsp+arg_10], rsi
0x18002e0df  push    rdi
0x18002e0e0  sub     rsp, 20h
0x18002e0e4  and     edx, 3
0x18002e0e7  mov     r10, r9
0x18002e0ea  mov     rax, r8
0x18002e0ed  mov     rdi, rcx
0x18002e0f0  mov     r8d, edx; dwFlags
0x18002e0f3  mov     r9d, 1F0003h; dwDesiredAccess
0x18002e0f9  mov     rdx, rax; lpName
0x18002e0fc  mov     rcx, r10; lpEventAttributes
0x18002e0ff  call    cs:__imp_CreateEventExW
0x18002e105  mov     rbp, rax
0x18002e108  test    rax, rax
0x18002e10b  jz      short loc_18002E13D
0x18002e10d  call    cs:__imp_GetLastError
0x18002e113  mov     rbx, [rdi]
0x18002e116  test    rbx, rbx
0x18002e119  jz      short loc_18002E138
0x18002e11b  call    cs:__imp_GetLastError
0x18002e121  mov     rcx, rbx; hObject
0x18002e124  mov     esi, eax
0x18002e126  call    cs:__imp_CloseHandle
0x18002e12c  test    eax, eax
0x18002e12e  jz      short loc_18002E152
0x18002e130  mov     ecx, esi; dwErrCode
0x18002e132  call    cs:__imp_SetLastError
0x18002e138  mov     [rdi], rbp
0x18002e13b  mov     al, 1
0x18002e13d  mov     rbx, [rsp+28h+arg_0]
0x18002e142  mov     rbp, [rsp+28h+arg_8]
0x18002e147  mov     rsi, [rsp+28h+arg_10]
0x18002e14c  add     rsp, 20h
0x18002e150  pop     rdi
0x18002e151  retn
0x18002e152  mov     rcx, [rsp+28h]; this
0x18002e157  mov     edx, 9D1h; void *
0x18002e15c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
