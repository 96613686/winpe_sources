# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000986c`
- end: `0x1400098cb`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400051a4`

## callees

- `0x140005ca0`
- `0x14000986c`
- `0x140009cdc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000989f`
- `KERNEL32!GetLastError` at `0x14000989f`
- `KERNEL32!CreateSemaphoreExW` at `0x14000988b`
- `KERNEL32!CreateSemaphoreExW` at `0x14000988b`

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
0x14000986c  mov     [rsp+arg_0], rbx
0x140009871  push    rdi
0x140009872  sub     rsp, 30h
0x140009876  mov     rdi, rcx
0x140009879  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140009881  xor     ecx, ecx; lpSemaphoreAttributes
0x140009883  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000988b  call    cs:__imp_CreateSemaphoreExW
0x140009892  nop     dword ptr [rax+rax+00h]
0x140009897  mov     rbx, rax
0x14000989a  test    rax, rax
0x14000989d  jz      short loc_1400098BA
0x14000989f  call    cs:__imp_GetLastError
0x1400098a6  nop     dword ptr [rax+rax+00h]
0x1400098ab  mov     rdx, rbx
0x1400098ae  mov     rcx, rdi
0x1400098b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400098b6  xor     eax, eax
0x1400098b8  jmp     short loc_1400098BF
0x1400098ba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400098bf  mov     rbx, [rsp+38h+arg_0]
0x1400098c4  add     rsp, 30h
0x1400098c8  pop     rdi
0x1400098c9  retn
```
