# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001f924`
- end: `0x18001f976`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e0e8`

## callees

- `0x180016cf4`
- `0x180016d28`
- `0x18001f924`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f951`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001f943`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001f943`

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
0x18001f924  mov     [rsp+arg_0], rbx
0x18001f929  push    rdi
0x18001f92a  sub     rsp, 30h
0x18001f92e  mov     rdi, rcx
0x18001f931  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001f939  xor     ecx, ecx; lpSemaphoreAttributes
0x18001f93b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18001f943  call    cs:__imp_CreateSemaphoreExW
0x18001f949  mov     rbx, rax
0x18001f94c  test    rax, rax
0x18001f94f  jz      short loc_18001F966
0x18001f951  call    cs:__imp_GetLastError
0x18001f957  mov     rdx, rbx
0x18001f95a  mov     rcx, rdi
0x18001f95d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001f962  xor     eax, eax
0x18001f964  jmp     short loc_18001F96B
0x18001f966  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001f96b  mov     rbx, [rsp+38h+arg_0]
0x18001f970  add     rsp, 30h
0x18001f974  pop     rdi
0x18001f975  retn
```
