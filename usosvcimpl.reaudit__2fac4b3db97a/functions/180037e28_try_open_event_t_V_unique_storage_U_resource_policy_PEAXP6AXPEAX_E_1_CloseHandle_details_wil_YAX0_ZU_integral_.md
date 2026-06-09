# ?try_open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEB_WK_N@Z

- ea: `0x180037e28`
- end: `0x180037ea6`
- name: `?try_open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEB_WK_N@Z`
- size: `126`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180031edc`
- `0x180033d60`
- `0x180064a3c`
- `0x180073800`

## callees

- `0x180008ea8`
- `0x180037e28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180037e49`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180037e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037e76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037e6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037e6a`

## pseudocode

```c
char __fastcall _try_open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NPEB_WK_N_Z(
        void **a1,
        const WCHAR *a2)
{
  HANDLE v3; // rax
  HANDLE v4; // rsi
  void *v5; // rbx
  DWORD LastError; // ebp
  unsigned int v7; // r8d
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = OpenEventW(0x100002u, 0, a2);
  v4 = v3;
  if ( v3 )
  {
    v5 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v7, v8);
      SetLastError(LastError);
    }
    *a1 = v4;
    LOBYTE(v3) = 1;
  }
  return (char)v3;
}

```

## disassembly

```asm
0x180037e28  mov     [rsp+arg_0], rbx
0x180037e2d  mov     [rsp+arg_8], rbp
0x180037e32  mov     [rsp+arg_10], rsi
0x180037e37  push    rdi
0x180037e38  sub     rsp, 20h
0x180037e3c  mov     rdi, rcx
0x180037e3f  mov     r8, rdx; lpName
0x180037e42  xor     edx, edx; bInheritHandle
0x180037e44  mov     ecx, 100002h; dwDesiredAccess
0x180037e49  call    cs:__imp_OpenEventW
0x180037e4f  mov     rsi, rax
0x180037e52  test    rax, rax
0x180037e55  jz      short loc_180037E81
0x180037e57  mov     rbx, [rdi]
0x180037e5a  test    rbx, rbx
0x180037e5d  jz      short loc_180037E7C
0x180037e5f  call    cs:__imp_GetLastError
0x180037e65  mov     rcx, rbx; hObject
0x180037e68  mov     ebp, eax
0x180037e6a  call    cs:__imp_CloseHandle
0x180037e70  test    eax, eax
0x180037e72  jz      short loc_180037E96
0x180037e74  mov     ecx, ebp; dwErrCode
0x180037e76  call    cs:__imp_SetLastError
0x180037e7c  mov     [rdi], rsi
0x180037e7f  mov     al, 1
0x180037e81  mov     rbx, [rsp+28h+arg_0]
0x180037e86  mov     rbp, [rsp+28h+arg_8]
0x180037e8b  mov     rsi, [rsp+28h+arg_10]
0x180037e90  add     rsp, 20h
0x180037e94  pop     rdi
0x180037e95  retn
0x180037e96  mov     rcx, [rsp+28h]; this
0x180037e9b  mov     edx, 9D1h; void *
0x180037ea0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
