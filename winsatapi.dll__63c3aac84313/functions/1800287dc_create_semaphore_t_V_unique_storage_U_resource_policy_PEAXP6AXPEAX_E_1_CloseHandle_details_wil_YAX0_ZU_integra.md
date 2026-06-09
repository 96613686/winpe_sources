# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800287dc`
- end: `0x18002882e`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023900`

## callees

- `0x180012394`
- `0x1800287dc`
- `0x180029af8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028809`
- `KERNEL32!CreateSemaphoreExW` at `0x1800287fb`
- `KERNEL32!CreateSemaphoreExW` at `0x1800287fb`

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
0x1800287dc  mov     [rsp+arg_0], rbx
0x1800287e1  push    rdi
0x1800287e2  sub     rsp, 30h
0x1800287e6  mov     rdi, rcx
0x1800287e9  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800287f1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800287f3  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800287fb  call    cs:__imp_CreateSemaphoreExW
0x180028801  mov     rbx, rax
0x180028804  test    rax, rax
0x180028807  jz      short loc_18002881E
0x180028809  call    cs:__imp_GetLastError
0x18002880f  mov     rdx, rbx
0x180028812  mov     rcx, rdi
0x180028815  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002881a  xor     eax, eax
0x18002881c  jmp     short loc_180028823
0x18002881e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180028823  mov     rbx, [rsp+38h+arg_0]
0x180028828  add     rsp, 30h
0x18002882c  pop     rdi
0x18002882d  retn
```
