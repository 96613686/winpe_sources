# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18000ee68`
- end: `0x18000eee2`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000794c`
- `0x180007d44`
- `0x180008288`
- `0x18000c490`
- `0x18000c620`

## callees

- `0x18000eac4`
- `0x18000ee68`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000eead`
- `KERNEL32!SetLastError` at `0x18000eead`
- `KERNEL32!GetLastError` at `0x18000ee8a`
- `KERNEL32!GetLastError` at `0x18000ee8a`
- `KERNEL32!CloseHandle` at `0x18000ee9b`
- `KERNEL32!CloseHandle` at `0x18000ee9b`

## pseudocode

```c
void __fastcall _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  DWORD LastError; // ebp
  __int64 v6; // r8
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v2) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v6, v7);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000ee68  mov     [rsp+arg_0], rbx
0x18000ee6d  mov     [rsp+arg_8], rbp
0x18000ee72  mov     [rsp+arg_10], rsi
0x18000ee77  push    rdi
0x18000ee78  sub     rsp, 20h
0x18000ee7c  mov     rdi, [rcx]
0x18000ee7f  mov     rsi, rdx
0x18000ee82  mov     rbx, rcx
0x18000ee85  test    rdi, rdi
0x18000ee88  jz      short loc_18000EEB9
0x18000ee8a  call    cs:__imp_GetLastError
0x18000ee91  nop     dword ptr [rax+rax+00h]
0x18000ee96  mov     rcx, rdi; hObject
0x18000ee99  mov     ebp, eax
0x18000ee9b  call    cs:__imp_CloseHandle
0x18000eea2  nop     dword ptr [rax+rax+00h]
0x18000eea7  test    eax, eax
0x18000eea9  jz      short loc_18000EED2
0x18000eeab  mov     ecx, ebp; dwErrCode
0x18000eead  call    cs:__imp_SetLastError
0x18000eeb4  nop     dword ptr [rax+rax+00h]
0x18000eeb9  mov     rbp, [rsp+28h+arg_8]
0x18000eebe  mov     [rbx], rsi
0x18000eec1  mov     rbx, [rsp+28h+arg_0]
0x18000eec6  mov     rsi, [rsp+28h+arg_10]
0x18000eecb  add     rsp, 20h
0x18000eecf  pop     rdi
0x18000eed0  retn
0x18000eed2  mov     rcx, [rsp+28h]; this
0x18000eed7  mov     edx, 9CDh; void *
0x18000eedc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
