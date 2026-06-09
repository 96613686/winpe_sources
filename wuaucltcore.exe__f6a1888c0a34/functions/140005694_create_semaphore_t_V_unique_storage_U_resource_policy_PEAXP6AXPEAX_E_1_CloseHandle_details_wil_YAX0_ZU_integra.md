# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140005694`
- end: `0x140005730`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005b58`

## callees

- `0x140003288`
- `0x140003e94`
- `0x140005694`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400056be`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400056be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400056cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400056da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400056cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400056da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400056f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400056f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400056e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400056e5`

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
0x140005694  mov     rax, rsp
0x140005697  mov     [rax+8], rbx
0x14000569b  mov     [rax+10h], rbp
0x14000569f  mov     [rax+18h], rsi
0x1400056a3  mov     [rax+20h], rdi
0x1400056a7  push    r14
0x1400056a9  sub     rsp, 30h
0x1400056ad  mov     rsi, rcx
0x1400056b0  mov     dword ptr [rax-10h], 1F0003h
0x1400056b7  xor     ebx, ebx
0x1400056b9  xor     ecx, ecx; lpSemaphoreAttributes
0x1400056bb  mov     [rax-18h], ebx
0x1400056be  call    cs:__imp_CreateSemaphoreExW
0x1400056c4  mov     r14, rax
0x1400056c7  test    rax, rax
0x1400056ca  jz      short loc_1400056FC
0x1400056cc  call    cs:__imp_GetLastError
0x1400056d2  mov     rdi, [rsi]
0x1400056d5  test    rdi, rdi
0x1400056d8  jz      short loc_1400056F7
0x1400056da  call    cs:__imp_GetLastError
0x1400056e0  mov     rcx, rdi; hObject
0x1400056e3  mov     ebp, eax
0x1400056e5  call    cs:__imp_CloseHandle
0x1400056eb  test    eax, eax
0x1400056ed  jz      short loc_140005720
0x1400056ef  mov     ecx, ebp; dwErrCode
0x1400056f1  call    cs:__imp_SetLastError
0x1400056f7  mov     [rsi], r14
0x1400056fa  jmp     short loc_140005703
0x1400056fc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005701  mov     ebx, eax
0x140005703  mov     rbp, [rsp+38h+arg_8]
0x140005708  mov     eax, ebx
0x14000570a  mov     rbx, [rsp+38h+arg_0]
0x14000570f  mov     rsi, [rsp+38h+arg_10]
0x140005714  mov     rdi, [rsp+38h+arg_18]
0x140005719  add     rsp, 30h
0x14000571d  pop     r14
0x14000571f  retn
0x140005720  mov     rcx, [rsp+38h]; this
0x140005725  mov     edx, 9D1h; void *
0x14000572a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
