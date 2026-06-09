# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180026898`
- end: `0x1800268ea`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025178`

## callees

- `0x180019b2c`
- `0x18001faa0`
- `0x180026898`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800268b7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800268b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268c5`

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
0x180026898  mov     [rsp+arg_0], rbx
0x18002689d  push    rdi
0x18002689e  sub     rsp, 30h
0x1800268a2  mov     rdi, rcx
0x1800268a5  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800268ad  xor     ecx, ecx; lpSemaphoreAttributes
0x1800268af  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800268b7  call    cs:__imp_CreateSemaphoreExW
0x1800268bd  mov     rbx, rax
0x1800268c0  test    rax, rax
0x1800268c3  jz      short loc_1800268DA
0x1800268c5  call    cs:__imp_GetLastError
0x1800268cb  mov     rdx, rbx
0x1800268ce  mov     rcx, rdi
0x1800268d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800268d6  xor     eax, eax
0x1800268d8  jmp     short loc_1800268DF
0x1800268da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800268df  mov     rbx, [rsp+38h+arg_0]
0x1800268e4  add     rsp, 30h
0x1800268e8  pop     rdi
0x1800268e9  retn
```
