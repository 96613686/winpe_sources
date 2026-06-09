# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18000c590`
- end: `0x18000c60a`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009600`
- `0x18000a904`
- `0x18000ae14`

## callees

- `0x18000c478`
- `0x18000c590`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000c5c3`
- `KERNEL32!CloseHandle` at `0x18000c5c3`
- `KERNEL32!GetLastError` at `0x18000c5b2`
- `KERNEL32!GetLastError` at `0x18000c5b2`
- `KERNEL32!SetLastError` at `0x18000c5da`
- `KERNEL32!SetLastError` at `0x18000c5da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        void **a1,
        void *a2)
{
  void *v4; // rdi
  DWORD LastError; // ebp
  __int64 v6; // r8
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v6, v7);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000c590  mov     [rsp+arg_0], rbx
0x18000c595  mov     [rsp+arg_8], rbp
0x18000c59a  mov     [rsp+arg_10], rsi
0x18000c59f  push    rdi
0x18000c5a0  sub     rsp, 20h
0x18000c5a4  mov     rsi, rdx
0x18000c5a7  mov     rbx, rcx
0x18000c5aa  mov     rdi, [rcx]
0x18000c5ad  test    rdi, rdi
0x18000c5b0  jz      short loc_18000C5E6
0x18000c5b2  call    cs:__imp_GetLastError
0x18000c5b9  nop     dword ptr [rax+rax+00h]
0x18000c5be  mov     ebp, eax
0x18000c5c0  mov     rcx, rdi; hObject
0x18000c5c3  call    cs:__imp_CloseHandle
0x18000c5ca  nop     dword ptr [rax+rax+00h]
0x18000c5cf  mov     rcx, [rsp+28h]; this
0x18000c5d4  test    eax, eax
0x18000c5d6  jz      short loc_18000C5FF
0x18000c5d8  mov     ecx, ebp; dwErrCode
0x18000c5da  call    cs:__imp_SetLastError
0x18000c5e1  nop     dword ptr [rax+rax+00h]
0x18000c5e6  mov     [rbx], rsi
0x18000c5e9  mov     rbx, [rsp+28h+arg_0]
0x18000c5ee  mov     rbp, [rsp+28h+arg_8]
0x18000c5f3  mov     rsi, [rsp+28h+arg_10]
0x18000c5f8  add     rsp, 20h
0x18000c5fc  pop     rdi
0x18000c5fd  retn
0x18000c5ff  mov     edx, 9DDh; void *
0x18000c604  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
