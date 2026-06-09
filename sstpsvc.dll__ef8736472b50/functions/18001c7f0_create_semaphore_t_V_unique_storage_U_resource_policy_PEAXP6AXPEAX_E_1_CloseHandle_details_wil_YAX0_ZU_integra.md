# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001c7f0`
- end: `0x18001c84f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018eec`

## callees

- `0x180019950`
- `0x18001c7f0`
- `0x18001ca0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001c80f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001c80f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c823`

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
0x18001c7f0  mov     [rsp+arg_0], rbx
0x18001c7f5  push    rdi
0x18001c7f6  sub     rsp, 30h
0x18001c7fa  mov     rdi, rcx
0x18001c7fd  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001c805  xor     ecx, ecx; lpSemaphoreAttributes
0x18001c807  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18001c80f  call    cs:__imp_CreateSemaphoreExW
0x18001c816  nop     dword ptr [rax+rax+00h]
0x18001c81b  mov     rbx, rax
0x18001c81e  test    rax, rax
0x18001c821  jz      short loc_18001C83E
0x18001c823  call    cs:__imp_GetLastError
0x18001c82a  nop     dword ptr [rax+rax+00h]
0x18001c82f  mov     rdx, rbx
0x18001c832  mov     rcx, rdi
0x18001c835  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001c83a  xor     eax, eax
0x18001c83c  jmp     short loc_18001C843
0x18001c83e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c843  mov     rbx, [rsp+38h+arg_0]
0x18001c848  add     rsp, 30h
0x18001c84c  pop     rdi
0x18001c84d  retn
```
