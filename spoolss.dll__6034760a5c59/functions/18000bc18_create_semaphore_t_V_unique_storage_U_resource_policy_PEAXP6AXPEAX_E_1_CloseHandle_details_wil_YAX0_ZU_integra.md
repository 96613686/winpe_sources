# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000bc18`
- end: `0x18000bc6a`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007898`

## callees

- `0x180004b7c`
- `0x18000bc18`
- `0x18000bdb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bc37`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bc37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc45`

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
0x18000bc18  mov     [rsp+arg_0], rbx
0x18000bc1d  push    rdi
0x18000bc1e  sub     rsp, 30h
0x18000bc22  mov     rdi, rcx
0x18000bc25  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000bc2d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000bc2f  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18000bc37  call    cs:__imp_CreateSemaphoreExW
0x18000bc3d  mov     rbx, rax
0x18000bc40  test    rax, rax
0x18000bc43  jz      short loc_18000BC5A
0x18000bc45  call    cs:__imp_GetLastError
0x18000bc4b  mov     rdx, rbx
0x18000bc4e  mov     rcx, rdi
0x18000bc51  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000bc56  xor     eax, eax
0x18000bc58  jmp     short loc_18000BC5F
0x18000bc5a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bc5f  mov     rbx, [rsp+38h+arg_0]
0x18000bc64  add     rsp, 30h
0x18000bc68  pop     rdi
0x18000bc69  retn
```
