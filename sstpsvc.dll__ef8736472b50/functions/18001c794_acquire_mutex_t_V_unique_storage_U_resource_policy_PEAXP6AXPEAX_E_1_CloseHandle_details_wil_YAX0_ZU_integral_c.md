# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x18001c794`
- end: `0x18001c7e8`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `84`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018b04`
- `0x180018c78`
- `0x18001b64c`
- `0x18001b6d8`

## callees

- `0x1800191f0`
- `0x18001c794`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c7ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c7ad`

## pseudocode

```c
_QWORD *__fastcall _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        HANDLE *a1,
        _QWORD *a2)
{
  HANDLE v2; // rbx
  DWORD v4; // eax
  void *v5; // rdx
  __int64 v6; // r8
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
0x18001c794  mov     [rsp+arg_0], rbx
0x18001c799  push    rdi
0x18001c79a  sub     rsp, 20h
0x18001c79e  mov     rbx, [rcx]
0x18001c7a1  mov     rdi, rdx
0x18001c7a4  mov     rcx, rbx; hHandle
0x18001c7a7  xor     r8d, r8d; bAlertable
0x18001c7aa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c7ad  call    cs:__imp_WaitForSingleObjectEx
0x18001c7b4  nop     dword ptr [rax+rax+00h]
0x18001c7b9  cmp     eax, 102h
0x18001c7be  jz      short loc_18001C7C9
0x18001c7c0  test    eax, 0FFFFFF7Fh
0x18001c7c5  jnz     short loc_18001C7DD
0x18001c7c7  jmp     short loc_18001C7CB
0x18001c7c9  xor     ebx, ebx
0x18001c7cb  mov     [rdi], rbx
0x18001c7ce  mov     rax, rdi
0x18001c7d1  mov     rbx, [rsp+28h+arg_0]
0x18001c7d6  add     rsp, 20h
0x18001c7da  pop     rdi
0x18001c7db  retn
0x18001c7dd  mov     rcx, [rsp+28h]; this
0x18001c7e2  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
