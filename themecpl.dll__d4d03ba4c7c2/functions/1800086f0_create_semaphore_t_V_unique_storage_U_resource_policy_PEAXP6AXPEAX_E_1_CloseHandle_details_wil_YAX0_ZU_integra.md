# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800086f0`
- end: `0x18000878b`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005eb8`

## callees

- `0x1800066b0`
- `0x1800086d4`
- `0x1800086f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000870e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000870e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008736`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008747`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008747`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  wil::details *v5; // rcx
  HANDLE Semaphore; // rbp
  void *v7; // rbx
  DWORD LastError; // esi
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v5);
  GetLastError();
  v7 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
    SetLastError(LastError);
  }
  *a1 = Semaphore;
  return 0;
}

```

## disassembly

```asm
0x1800086f0  push    rbx
0x1800086f2  push    rbp
0x1800086f3  push    rsi
0x1800086f4  push    rdi
0x1800086f5  sub     rsp, 38h
0x1800086f9  mov     rdi, rcx
0x1800086fc  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008704  xor     ecx, ecx; lpSemaphoreAttributes
0x180008706  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000870e  call    cs:__imp_CreateSemaphoreExW
0x180008715  nop     dword ptr [rax+rax+00h]
0x18000871a  mov     rbp, rax
0x18000871d  test    rax, rax
0x180008720  jz      short loc_18000876C
0x180008722  call    cs:__imp_GetLastError
0x180008729  nop     dword ptr [rax+rax+00h]
0x18000872e  mov     rbx, [rdi]
0x180008731  test    rbx, rbx
0x180008734  jz      short loc_180008765
0x180008736  call    cs:__imp_GetLastError
0x18000873d  nop     dword ptr [rax+rax+00h]
0x180008742  mov     rcx, rbx; hObject
0x180008745  mov     esi, eax
0x180008747  call    cs:__imp_CloseHandle
0x18000874e  nop     dword ptr [rax+rax+00h]
0x180008753  test    eax, eax
0x180008755  jz      short loc_18000877B
0x180008757  mov     ecx, esi; dwErrCode
0x180008759  call    cs:__imp_SetLastError
0x180008760  nop     dword ptr [rax+rax+00h]
0x180008765  mov     [rdi], rbp
0x180008768  xor     eax, eax
0x18000876a  jmp     short loc_180008771
0x18000876c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008771  add     rsp, 38h
0x180008775  pop     rdi
0x180008776  pop     rsi
0x180008777  pop     rbp
0x180008778  pop     rbx
0x180008779  retn
0x18000877b  mov     rcx, [rsp+58h]; this
0x180008780  mov     edx, 0A0Bh; void *
0x180008785  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
