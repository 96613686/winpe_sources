# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180016ee8`
- end: `0x180016f3a`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014850`

## callees

- `0x1800120a4`
- `0x180016ee8`
- `0x180016f4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180016f07`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180016f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f15`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  wil::details *v5; // rcx
  HANDLE Semaphore; // rbx

  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v5);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x180016ee8  mov     [rsp+arg_0], rbx
0x180016eed  push    rdi
0x180016eee  sub     rsp, 30h
0x180016ef2  mov     rdi, rcx
0x180016ef5  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180016efd  xor     ecx, ecx; lpSemaphoreAttributes
0x180016eff  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180016f07  call    cs:__imp_CreateSemaphoreExW
0x180016f0d  mov     rbx, rax
0x180016f10  test    rax, rax
0x180016f13  jz      short loc_180016F2A
0x180016f15  call    cs:__imp_GetLastError
0x180016f1b  mov     rdx, rbx
0x180016f1e  mov     rcx, rdi
0x180016f21  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180016f26  xor     eax, eax
0x180016f28  jmp     short loc_180016F2F
0x180016f2a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180016f2f  mov     rbx, [rsp+38h+arg_0]
0x180016f34  add     rsp, 30h
0x180016f38  pop     rdi
0x180016f39  retn
```
