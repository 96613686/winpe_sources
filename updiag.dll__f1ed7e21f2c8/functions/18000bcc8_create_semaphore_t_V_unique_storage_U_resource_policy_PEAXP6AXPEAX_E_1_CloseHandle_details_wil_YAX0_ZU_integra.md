# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000bcc8`
- end: `0x18000bd64`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c18c`

## callees

- `0x18000a738`
- `0x18000ada0`
- `0x18000bcc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd0e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bcf2`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bcf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd19`

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
0x18000bcc8  mov     rax, rsp
0x18000bccb  mov     [rax+8], rbx
0x18000bccf  mov     [rax+10h], rbp
0x18000bcd3  mov     [rax+18h], rsi
0x18000bcd7  mov     [rax+20h], rdi
0x18000bcdb  push    r14
0x18000bcdd  sub     rsp, 30h
0x18000bce1  mov     rsi, rcx
0x18000bce4  mov     dword ptr [rax-10h], 1F0003h
0x18000bceb  xor     ebx, ebx
0x18000bced  xor     ecx, ecx; lpSemaphoreAttributes
0x18000bcef  mov     [rax-18h], ebx
0x18000bcf2  call    cs:__imp_CreateSemaphoreExW
0x18000bcf8  mov     r14, rax
0x18000bcfb  test    rax, rax
0x18000bcfe  jz      short loc_18000BD30
0x18000bd00  call    cs:__imp_GetLastError
0x18000bd06  mov     rdi, [rsi]
0x18000bd09  test    rdi, rdi
0x18000bd0c  jz      short loc_18000BD2B
0x18000bd0e  call    cs:__imp_GetLastError
0x18000bd14  mov     rcx, rdi; hObject
0x18000bd17  mov     ebp, eax
0x18000bd19  call    cs:__imp_CloseHandle
0x18000bd1f  test    eax, eax
0x18000bd21  jz      short loc_18000BD54
0x18000bd23  mov     ecx, ebp; dwErrCode
0x18000bd25  call    cs:__imp_SetLastError
0x18000bd2b  mov     [rsi], r14
0x18000bd2e  jmp     short loc_18000BD37
0x18000bd30  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bd35  mov     ebx, eax
0x18000bd37  mov     rbp, [rsp+38h+arg_8]
0x18000bd3c  mov     eax, ebx
0x18000bd3e  mov     rbx, [rsp+38h+arg_0]
0x18000bd43  mov     rsi, [rsp+38h+arg_10]
0x18000bd48  mov     rdi, [rsp+38h+arg_18]
0x18000bd4d  add     rsp, 30h
0x18000bd51  pop     r14
0x18000bd53  retn
0x18000bd54  mov     rcx, [rsp+38h]; this
0x18000bd59  mov     edx, 9D1h; void *
0x18000bd5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
