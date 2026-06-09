# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000d818`
- end: `0x18000d8b3`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a5c0`

## callees

- `0x180005ad4`
- `0x18000d7c4`
- `0x18000d818`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d84a`
- `KERNEL32!GetLastError` at `0x18000d85e`
- `KERNEL32!GetLastError` at `0x18000d84a`
- `KERNEL32!GetLastError` at `0x18000d85e`
- `KERNEL32!SetLastError` at `0x18000d881`
- `KERNEL32!SetLastError` at `0x18000d881`
- `KERNEL32!CloseHandle` at `0x18000d86f`
- `KERNEL32!CloseHandle` at `0x18000d86f`
- `KERNEL32!CreateSemaphoreExW` at `0x18000d836`
- `KERNEL32!CreateSemaphoreExW` at `0x18000d836`

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
0x18000d818  push    rbx
0x18000d81a  push    rbp
0x18000d81b  push    rsi
0x18000d81c  push    rdi
0x18000d81d  sub     rsp, 38h
0x18000d821  mov     rdi, rcx
0x18000d824  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000d82c  xor     ecx, ecx; lpSemaphoreAttributes
0x18000d82e  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000d836  call    cs:__imp_CreateSemaphoreExW
0x18000d83d  nop     dword ptr [rax+rax+00h]
0x18000d842  mov     rbp, rax
0x18000d845  test    rax, rax
0x18000d848  jz      short loc_18000D894
0x18000d84a  call    cs:__imp_GetLastError
0x18000d851  nop     dword ptr [rax+rax+00h]
0x18000d856  mov     rbx, [rdi]
0x18000d859  test    rbx, rbx
0x18000d85c  jz      short loc_18000D88D
0x18000d85e  call    cs:__imp_GetLastError
0x18000d865  nop     dword ptr [rax+rax+00h]
0x18000d86a  mov     rcx, rbx; hObject
0x18000d86d  mov     esi, eax
0x18000d86f  call    cs:__imp_CloseHandle
0x18000d876  nop     dword ptr [rax+rax+00h]
0x18000d87b  test    eax, eax
0x18000d87d  jz      short loc_18000D8A3
0x18000d87f  mov     ecx, esi; dwErrCode
0x18000d881  call    cs:__imp_SetLastError
0x18000d888  nop     dword ptr [rax+rax+00h]
0x18000d88d  mov     [rdi], rbp
0x18000d890  xor     eax, eax
0x18000d892  jmp     short loc_18000D899
0x18000d894  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d899  add     rsp, 38h
0x18000d89d  pop     rdi
0x18000d89e  pop     rsi
0x18000d89f  pop     rbp
0x18000d8a0  pop     rbx
0x18000d8a1  retn
0x18000d8a3  mov     rcx, [rsp+58h]; this
0x18000d8a8  mov     edx, 0A0Bh; void *
0x18000d8ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
