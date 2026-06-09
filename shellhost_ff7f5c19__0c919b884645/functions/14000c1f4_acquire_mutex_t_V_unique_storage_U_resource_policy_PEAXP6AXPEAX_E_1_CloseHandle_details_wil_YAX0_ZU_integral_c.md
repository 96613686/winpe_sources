# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x14000c1f4`
- end: `0x14000c24b`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `87`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000bd68`
- `0x14000bf18`
- `0x14004913c`
- `0x1400491bc`

## callees

- `0x14000c1f4`
- `0x140046a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000c20d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000c20d`

## string_xrefs

- `0x14000c226`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        HANDLE *a1,
        _QWORD *a2)
{
  HANDLE v2; // rbx
  DWORD v4; // eax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a1;
  v4 = WaitForSingleObjectEx(*a1, 0xFFFFFFFF, 0);
  if ( v4 == 258 )
  {
    v2 = 0;
  }
  else if ( (v4 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  }
  *a2 = v2;
  return a2;
}

```

## disassembly

```asm
0x14000c1f4  mov     [rsp+arg_0], rbx
0x14000c1f9  push    rdi
0x14000c1fa  sub     rsp, 20h
0x14000c1fe  mov     rbx, [rcx]
0x14000c201  mov     rdi, rdx
0x14000c204  mov     rcx, rbx; hHandle
0x14000c207  xor     r8d, r8d; bAlertable
0x14000c20a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000c20d  call    cs:__imp_WaitForSingleObjectEx
0x14000c213  cmp     eax, 102h
0x14000c218  jz      short loc_14000C238
0x14000c21a  test    eax, 0FFFFFF7Fh
0x14000c21f  jz      short loc_14000C23A
0x14000c221  mov     rcx, [rsp+28h]; this
0x14000c226  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000c22d  mov     edx, 0E01h; void *
0x14000c232  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000c238  xor     ebx, ebx
0x14000c23a  mov     [rdi], rbx
0x14000c23d  mov     rax, rdi
0x14000c240  mov     rbx, [rsp+28h+arg_0]
0x14000c245  add     rsp, 20h
0x14000c249  pop     rdi
0x14000c24a  retn
```
