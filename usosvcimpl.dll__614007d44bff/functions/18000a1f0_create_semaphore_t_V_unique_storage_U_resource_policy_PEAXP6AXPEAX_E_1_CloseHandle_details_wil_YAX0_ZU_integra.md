# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000a1f0`
- end: `0x18000a28c`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000acb8`

## callees

- `0x1800081c0`
- `0x180008ea8`
- `0x18000a1f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a21a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a236`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a24d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a24d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a241`

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
0x18000a1f0  mov     rax, rsp
0x18000a1f3  mov     [rax+8], rbx
0x18000a1f7  mov     [rax+10h], rbp
0x18000a1fb  mov     [rax+18h], rsi
0x18000a1ff  mov     [rax+20h], rdi
0x18000a203  push    r14
0x18000a205  sub     rsp, 30h
0x18000a209  mov     rsi, rcx
0x18000a20c  mov     dword ptr [rax-10h], 1F0003h
0x18000a213  xor     ebx, ebx
0x18000a215  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a217  mov     [rax-18h], ebx
0x18000a21a  call    cs:__imp_CreateSemaphoreExW
0x18000a220  mov     r14, rax
0x18000a223  test    rax, rax
0x18000a226  jz      short loc_18000A258
0x18000a228  call    cs:__imp_GetLastError
0x18000a22e  mov     rdi, [rsi]
0x18000a231  test    rdi, rdi
0x18000a234  jz      short loc_18000A253
0x18000a236  call    cs:__imp_GetLastError
0x18000a23c  mov     rcx, rdi; hObject
0x18000a23f  mov     ebp, eax
0x18000a241  call    cs:__imp_CloseHandle
0x18000a247  test    eax, eax
0x18000a249  jz      short loc_18000A27C
0x18000a24b  mov     ecx, ebp; dwErrCode
0x18000a24d  call    cs:__imp_SetLastError
0x18000a253  mov     [rsi], r14
0x18000a256  jmp     short loc_18000A25F
0x18000a258  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a25d  mov     ebx, eax
0x18000a25f  mov     rbp, [rsp+38h+arg_8]
0x18000a264  mov     eax, ebx
0x18000a266  mov     rbx, [rsp+38h+arg_0]
0x18000a26b  mov     rsi, [rsp+38h+arg_10]
0x18000a270  mov     rdi, [rsp+38h+arg_18]
0x18000a275  add     rsp, 30h
0x18000a279  pop     r14
0x18000a27b  retn
0x18000a27c  mov     rcx, [rsp+38h]; this
0x18000a281  mov     edx, 9D1h; void *
0x18000a286  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
