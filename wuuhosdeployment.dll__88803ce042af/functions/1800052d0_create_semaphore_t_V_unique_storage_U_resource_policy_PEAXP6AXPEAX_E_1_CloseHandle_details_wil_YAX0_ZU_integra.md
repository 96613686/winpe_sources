# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800052d0`
- end: `0x18000536c`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005b74`

## callees

- `0x1800029a0`
- `0x180003994`
- `0x1800052d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800052fa`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800052fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000532d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000532d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005316`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005321`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005321`

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
0x1800052d0  mov     rax, rsp
0x1800052d3  mov     [rax+8], rbx
0x1800052d7  mov     [rax+10h], rbp
0x1800052db  mov     [rax+18h], rsi
0x1800052df  mov     [rax+20h], rdi
0x1800052e3  push    r14
0x1800052e5  sub     rsp, 30h
0x1800052e9  mov     rsi, rcx
0x1800052ec  mov     dword ptr [rax-10h], 1F0003h
0x1800052f3  xor     ebx, ebx
0x1800052f5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800052f7  mov     [rax-18h], ebx
0x1800052fa  call    cs:__imp_CreateSemaphoreExW
0x180005300  mov     r14, rax
0x180005303  test    rax, rax
0x180005306  jz      short loc_180005338
0x180005308  call    cs:__imp_GetLastError
0x18000530e  mov     rdi, [rsi]
0x180005311  test    rdi, rdi
0x180005314  jz      short loc_180005333
0x180005316  call    cs:__imp_GetLastError
0x18000531c  mov     rcx, rdi; hObject
0x18000531f  mov     ebp, eax
0x180005321  call    cs:__imp_CloseHandle
0x180005327  test    eax, eax
0x180005329  jz      short loc_18000535C
0x18000532b  mov     ecx, ebp; dwErrCode
0x18000532d  call    cs:__imp_SetLastError
0x180005333  mov     [rsi], r14
0x180005336  jmp     short loc_18000533F
0x180005338  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000533d  mov     ebx, eax
0x18000533f  mov     rbp, [rsp+38h+arg_8]
0x180005344  mov     eax, ebx
0x180005346  mov     rbx, [rsp+38h+arg_0]
0x18000534b  mov     rsi, [rsp+38h+arg_10]
0x180005350  mov     rdi, [rsp+38h+arg_18]
0x180005355  add     rsp, 30h
0x180005359  pop     r14
0x18000535b  retn
0x18000535c  mov     rcx, [rsp+38h]; this
0x180005361  mov     edx, 9D1h; void *
0x180005366  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
