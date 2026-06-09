# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x180011e44`
- end: `0x180011e91`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `77`
- prototype: `_QWORD *__fastcall(HANDLE *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000de78`
- `0x18000dfe0`
- `0x180010a84`
- `0x180010b04`

## callees

- `0x18000e48c`
- `0x180011e44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180011e5d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180011e5d`

## pseudocode

```c
_QWORD *__fastcall _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        HANDLE *a1,
        _QWORD *a2)
{
  HANDLE v2; // rbx
  DWORD v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a1;
  v4 = WaitForSingleObjectEx(*a1, 0xFFFFFFFF, 0);
  if ( v4 == 258 )
  {
    v2 = 0;
  }
  else if ( (v4 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(retaddr, v5, v6, v7);
  }
  *a2 = v2;
  return a2;
}

```

## disassembly

```asm
0x180011e44  mov     [rsp+arg_0], rbx
0x180011e49  push    rdi
0x180011e4a  sub     rsp, 20h
0x180011e4e  mov     rbx, [rcx]
0x180011e51  mov     rdi, rdx
0x180011e54  mov     rcx, rbx; hHandle
0x180011e57  xor     r8d, r8d; bAlertable
0x180011e5a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011e5d  call    cs:__imp_WaitForSingleObjectEx
0x180011e63  cmp     eax, 102h
0x180011e68  jz      short loc_180011E73
0x180011e6a  test    eax, 0FFFFFF7Fh
0x180011e6f  jnz     short loc_180011E86
0x180011e71  jmp     short loc_180011E75
0x180011e73  xor     ebx, ebx
0x180011e75  mov     [rdi], rbx
0x180011e78  mov     rax, rdi
0x180011e7b  mov     rbx, [rsp+28h+arg_0]
0x180011e80  add     rsp, 20h
0x180011e84  pop     rdi
0x180011e85  retn
0x180011e86  mov     rcx, [rsp+28h]; this
0x180011e8b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
