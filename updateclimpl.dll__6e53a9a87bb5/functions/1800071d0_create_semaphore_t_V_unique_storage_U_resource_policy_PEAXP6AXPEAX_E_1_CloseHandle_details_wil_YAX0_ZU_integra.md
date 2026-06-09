# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800071d0`
- end: `0x18000726c`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: `__int64 __fastcall(void **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007a74`

## callees

- `0x180004f80`
- `0x180005ec4`
- `0x1800071d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000722d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000722d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007216`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800071fa`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800071fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007221`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007221`

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
  __int64 v10; // r8
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
0x1800071d0  mov     rax, rsp
0x1800071d3  mov     [rax+8], rbx
0x1800071d7  mov     [rax+10h], rbp
0x1800071db  mov     [rax+18h], rsi
0x1800071df  mov     [rax+20h], rdi
0x1800071e3  push    r14
0x1800071e5  sub     rsp, 30h
0x1800071e9  mov     rsi, rcx
0x1800071ec  mov     dword ptr [rax-10h], 1F0003h
0x1800071f3  xor     ebx, ebx
0x1800071f5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800071f7  mov     [rax-18h], ebx
0x1800071fa  call    cs:__imp_CreateSemaphoreExW
0x180007200  mov     r14, rax
0x180007203  test    rax, rax
0x180007206  jz      short loc_180007238
0x180007208  call    cs:__imp_GetLastError
0x18000720e  mov     rdi, [rsi]
0x180007211  test    rdi, rdi
0x180007214  jz      short loc_180007233
0x180007216  call    cs:__imp_GetLastError
0x18000721c  mov     rcx, rdi; hObject
0x18000721f  mov     ebp, eax
0x180007221  call    cs:__imp_CloseHandle
0x180007227  test    eax, eax
0x180007229  jz      short loc_18000725C
0x18000722b  mov     ecx, ebp; dwErrCode
0x18000722d  call    cs:__imp_SetLastError
0x180007233  mov     [rsi], r14
0x180007236  jmp     short loc_18000723F
0x180007238  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000723d  mov     ebx, eax
0x18000723f  mov     rbp, [rsp+38h+arg_8]
0x180007244  mov     eax, ebx
0x180007246  mov     rbx, [rsp+38h+arg_0]
0x18000724b  mov     rsi, [rsp+38h+arg_10]
0x180007250  mov     rdi, [rsp+38h+arg_18]
0x180007255  add     rsp, 30h
0x180007259  pop     r14
0x18000725b  retn
0x18000725c  mov     rcx, [rsp+38h]; this
0x180007261  mov     edx, 9D1h; void *
0x180007266  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
