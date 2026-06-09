# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180009d24`
- end: `0x180009d83`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007aa8`

## callees

- `0x180008140`
- `0x180009d24`
- `0x180009d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009d43`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009d43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d57`

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
0x180009d24  mov     [rsp+arg_0], rbx
0x180009d29  push    rdi
0x180009d2a  sub     rsp, 30h
0x180009d2e  mov     rdi, rcx
0x180009d31  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009d39  xor     ecx, ecx; lpSemaphoreAttributes
0x180009d3b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180009d43  call    cs:__imp_CreateSemaphoreExW
0x180009d4a  nop     dword ptr [rax+rax+00h]
0x180009d4f  mov     rbx, rax
0x180009d52  test    rax, rax
0x180009d55  jz      short loc_180009D72
0x180009d57  call    cs:__imp_GetLastError
0x180009d5e  nop     dword ptr [rax+rax+00h]
0x180009d63  mov     rdx, rbx
0x180009d66  mov     rcx, rdi
0x180009d69  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009d6e  xor     eax, eax
0x180009d70  jmp     short loc_180009D77
0x180009d72  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009d77  mov     rbx, [rsp+38h+arg_0]
0x180009d7c  add     rsp, 30h
0x180009d80  pop     rdi
0x180009d81  retn
```
