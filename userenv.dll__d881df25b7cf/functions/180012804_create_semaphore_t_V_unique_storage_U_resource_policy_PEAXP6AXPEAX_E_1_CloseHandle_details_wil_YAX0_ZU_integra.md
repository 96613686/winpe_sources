# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180012804`
- end: `0x180012863`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011730`

## callees

- `0x18000d848`
- `0x180012804`
- `0x180012880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012823`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012837`

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
0x180012804  mov     [rsp+arg_0], rbx
0x180012809  push    rdi
0x18001280a  sub     rsp, 30h
0x18001280e  mov     rdi, rcx
0x180012811  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180012819  xor     ecx, ecx; lpSemaphoreAttributes
0x18001281b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180012823  call    cs:__imp_CreateSemaphoreExW
0x18001282a  nop     dword ptr [rax+rax+00h]
0x18001282f  mov     rbx, rax
0x180012832  test    rax, rax
0x180012835  jz      short loc_180012852
0x180012837  call    cs:__imp_GetLastError
0x18001283e  nop     dword ptr [rax+rax+00h]
0x180012843  mov     rdx, rbx
0x180012846  mov     rcx, rdi
0x180012849  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001284e  xor     eax, eax
0x180012850  jmp     short loc_180012857
0x180012852  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012857  mov     rbx, [rsp+38h+arg_0]
0x18001285c  add     rsp, 30h
0x180012860  pop     rdi
0x180012861  retn
```
