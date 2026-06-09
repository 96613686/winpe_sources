# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180004994`
- end: `0x180004a30`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000521c`

## callees

- `0x1800027b0`
- `0x1800037a4`
- `0x180004994`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049be`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049e5`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  unsigned int v5; // ebx
  wil::details *v6; // rcx
  HANDLE Semaphore; // r14
  void *v8; // rdi
  DWORD LastError; // ebp
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = 0;
  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v8 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v10, v11);
      SetLastError(LastError);
    }
    *a1 = Semaphore;
  }
  else
  {
    return (unsigned int)wil::details::GetLastErrorFailHr(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x180004994  mov     rax, rsp
0x180004997  mov     [rax+8], rbx
0x18000499b  mov     [rax+10h], rbp
0x18000499f  mov     [rax+18h], rsi
0x1800049a3  mov     [rax+20h], rdi
0x1800049a7  push    r14
0x1800049a9  sub     rsp, 30h
0x1800049ad  mov     rsi, rcx
0x1800049b0  mov     dword ptr [rax-10h], 1F0003h
0x1800049b7  xor     ebx, ebx
0x1800049b9  xor     ecx, ecx; lpSemaphoreAttributes
0x1800049bb  mov     [rax-18h], ebx
0x1800049be  call    cs:__imp_CreateSemaphoreExW
0x1800049c4  mov     r14, rax
0x1800049c7  test    rax, rax
0x1800049ca  jz      short loc_1800049FC
0x1800049cc  call    cs:__imp_GetLastError
0x1800049d2  mov     rdi, [rsi]
0x1800049d5  test    rdi, rdi
0x1800049d8  jz      short loc_1800049F7
0x1800049da  call    cs:__imp_GetLastError
0x1800049e0  mov     rcx, rdi; hObject
0x1800049e3  mov     ebp, eax
0x1800049e5  call    cs:__imp_CloseHandle
0x1800049eb  test    eax, eax
0x1800049ed  jz      short loc_180004A20
0x1800049ef  mov     ecx, ebp; dwErrCode
0x1800049f1  call    cs:__imp_SetLastError
0x1800049f7  mov     [rsi], r14
0x1800049fa  jmp     short loc_180004A03
0x1800049fc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004a01  mov     ebx, eax
0x180004a03  mov     rbp, [rsp+38h+arg_8]
0x180004a08  mov     eax, ebx
0x180004a0a  mov     rbx, [rsp+38h+arg_0]
0x180004a0f  mov     rsi, [rsp+38h+arg_10]
0x180004a14  mov     rdi, [rsp+38h+arg_18]
0x180004a19  add     rsp, 30h
0x180004a1d  pop     r14
0x180004a1f  retn
0x180004a20  mov     rcx, [rsp+38h]; this
0x180004a25  mov     edx, 9D1h; void *
0x180004a2a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
