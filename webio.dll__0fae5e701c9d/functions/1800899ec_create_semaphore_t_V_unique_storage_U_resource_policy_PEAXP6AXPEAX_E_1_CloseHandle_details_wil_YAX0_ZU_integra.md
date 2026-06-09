# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800899ec`
- end: `0x180089a4b`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180086798`

## callees

- `0x180071c14`
- `0x1800899ec`
- `0x180089a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089a1f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180089a0b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180089a0b`

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
0x1800899ec  mov     [rsp+arg_0], rbx
0x1800899f1  push    rdi
0x1800899f2  sub     rsp, 30h
0x1800899f6  mov     rdi, rcx
0x1800899f9  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180089a01  xor     ecx, ecx; lpSemaphoreAttributes
0x180089a03  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180089a0b  call    cs:__imp_CreateSemaphoreExW
0x180089a12  nop     dword ptr [rax+rax+00h]
0x180089a17  mov     rbx, rax
0x180089a1a  test    rax, rax
0x180089a1d  jz      short loc_180089A3A
0x180089a1f  call    cs:__imp_GetLastError
0x180089a26  nop     dword ptr [rax+rax+00h]
0x180089a2b  mov     rdx, rbx
0x180089a2e  mov     rcx, rdi
0x180089a31  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180089a36  xor     eax, eax
0x180089a38  jmp     short loc_180089A3F
0x180089a3a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180089a3f  mov     rbx, [rsp+38h+arg_0]
0x180089a44  add     rsp, 30h
0x180089a48  pop     rdi
0x180089a49  retn
```
