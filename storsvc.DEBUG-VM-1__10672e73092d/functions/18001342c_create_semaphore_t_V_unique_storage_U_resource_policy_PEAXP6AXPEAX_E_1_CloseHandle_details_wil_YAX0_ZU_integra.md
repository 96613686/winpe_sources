# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001342c`
- end: `0x18001347e`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010f94`

## callees

- `0x180011688`
- `0x18001342c`
- `0x180013484`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001344b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001344b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013459`

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
0x18001342c  mov     [rsp+arg_0], rbx
0x180013431  push    rdi
0x180013432  sub     rsp, 30h
0x180013436  mov     rdi, rcx
0x180013439  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180013441  xor     ecx, ecx; lpSemaphoreAttributes
0x180013443  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18001344b  call    cs:__imp_CreateSemaphoreExW
0x180013451  mov     rbx, rax
0x180013454  test    rax, rax
0x180013457  jz      short loc_18001346E
0x180013459  call    cs:__imp_GetLastError
0x18001345f  mov     rdx, rbx
0x180013462  mov     rcx, rdi
0x180013465  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001346a  xor     eax, eax
0x18001346c  jmp     short loc_180013473
0x18001346e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180013473  mov     rbx, [rsp+38h+arg_0]
0x180013478  add     rsp, 30h
0x18001347c  pop     rdi
0x18001347d  retn
```
