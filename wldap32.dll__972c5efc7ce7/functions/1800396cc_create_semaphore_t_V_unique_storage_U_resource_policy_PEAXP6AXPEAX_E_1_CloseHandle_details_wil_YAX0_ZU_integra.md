# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800396cc`
- end: `0x18003972b`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003651c`

## callees

- `0x1800339f8`
- `0x1800396cc`
- `0x1800397e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800396eb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800396eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396ff`

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
0x1800396cc  mov     [rsp+arg_0], rbx
0x1800396d1  push    rdi
0x1800396d2  sub     rsp, 30h
0x1800396d6  mov     rdi, rcx
0x1800396d9  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800396e1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800396e3  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800396eb  call    cs:__imp_CreateSemaphoreExW
0x1800396f2  nop     dword ptr [rax+rax+00h]
0x1800396f7  mov     rbx, rax
0x1800396fa  test    rax, rax
0x1800396fd  jz      short loc_18003971A
0x1800396ff  call    cs:__imp_GetLastError
0x180039706  nop     dword ptr [rax+rax+00h]
0x18003970b  mov     rdx, rbx
0x18003970e  mov     rcx, rdi
0x180039711  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180039716  xor     eax, eax
0x180039718  jmp     short loc_18003971F
0x18003971a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003971f  mov     rbx, [rsp+38h+arg_0]
0x180039724  add     rsp, 30h
0x180039728  pop     rdi
0x180039729  retn
```
