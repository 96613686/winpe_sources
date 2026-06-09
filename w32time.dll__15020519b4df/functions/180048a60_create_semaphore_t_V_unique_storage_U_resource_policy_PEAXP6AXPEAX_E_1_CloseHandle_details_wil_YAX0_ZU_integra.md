# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180048a60`
- end: `0x180048abf`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042284`

## callees

- `0x18003c39c`
- `0x180048a60`
- `0x180048cac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180048a7f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180048a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a93`

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
0x180048a60  mov     [rsp+arg_0], rbx
0x180048a65  push    rdi
0x180048a66  sub     rsp, 30h
0x180048a6a  mov     rdi, rcx
0x180048a6d  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180048a75  xor     ecx, ecx; lpSemaphoreAttributes
0x180048a77  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180048a7f  call    cs:__imp_CreateSemaphoreExW
0x180048a86  nop     dword ptr [rax+rax+00h]
0x180048a8b  mov     rbx, rax
0x180048a8e  test    rax, rax
0x180048a91  jz      short loc_180048AAE
0x180048a93  call    cs:__imp_GetLastError
0x180048a9a  nop     dword ptr [rax+rax+00h]
0x180048a9f  mov     rdx, rbx
0x180048aa2  mov     rcx, rdi
0x180048aa5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180048aaa  xor     eax, eax
0x180048aac  jmp     short loc_180048AB3
0x180048aae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180048ab3  mov     rbx, [rsp+38h+arg_0]
0x180048ab8  add     rsp, 30h
0x180048abc  pop     rdi
0x180048abd  retn
```
