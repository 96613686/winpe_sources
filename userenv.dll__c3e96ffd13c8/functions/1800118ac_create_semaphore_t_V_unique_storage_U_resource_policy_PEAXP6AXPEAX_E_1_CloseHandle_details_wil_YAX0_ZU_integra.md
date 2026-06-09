# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800118ac`
- end: `0x1800118fe`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010870`

## callees

- `0x18000cb08`
- `0x1800118ac`
- `0x180011918`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800118cb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800118cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118d9`

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
0x1800118ac  mov     [rsp+arg_0], rbx
0x1800118b1  push    rdi
0x1800118b2  sub     rsp, 30h
0x1800118b6  mov     rdi, rcx
0x1800118b9  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800118c1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800118c3  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800118cb  call    cs:__imp_CreateSemaphoreExW
0x1800118d1  mov     rbx, rax
0x1800118d4  test    rax, rax
0x1800118d7  jz      short loc_1800118EE
0x1800118d9  call    cs:__imp_GetLastError
0x1800118df  mov     rdx, rbx
0x1800118e2  mov     rcx, rdi
0x1800118e5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800118ea  xor     eax, eax
0x1800118ec  jmp     short loc_1800118F3
0x1800118ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800118f3  mov     rbx, [rsp+38h+arg_0]
0x1800118f8  add     rsp, 30h
0x1800118fc  pop     rdi
0x1800118fd  retn
```
