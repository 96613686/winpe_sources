# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180024b58`
- end: `0x180024baa`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022614`

## callees

- `0x180022ce8`
- `0x180024b58`
- `0x180024bb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b85`
- `KERNEL32!CreateSemaphoreExW` at `0x180024b77`
- `KERNEL32!CreateSemaphoreExW` at `0x180024b77`

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
0x180024b58  mov     [rsp+arg_0], rbx
0x180024b5d  push    rdi
0x180024b5e  sub     rsp, 30h
0x180024b62  mov     rdi, rcx
0x180024b65  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180024b6d  xor     ecx, ecx; lpSemaphoreAttributes
0x180024b6f  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180024b77  call    cs:__imp_CreateSemaphoreExW
0x180024b7d  mov     rbx, rax
0x180024b80  test    rax, rax
0x180024b83  jz      short loc_180024B9A
0x180024b85  call    cs:__imp_GetLastError
0x180024b8b  mov     rdx, rbx
0x180024b8e  mov     rcx, rdi
0x180024b91  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180024b96  xor     eax, eax
0x180024b98  jmp     short loc_180024B9F
0x180024b9a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180024b9f  mov     rbx, [rsp+38h+arg_0]
0x180024ba4  add     rsp, 30h
0x180024ba8  pop     rdi
0x180024ba9  retn
```
