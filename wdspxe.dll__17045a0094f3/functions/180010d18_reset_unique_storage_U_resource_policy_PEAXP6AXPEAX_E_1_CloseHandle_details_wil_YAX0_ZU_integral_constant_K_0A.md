# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180010d18`
- end: `0x180010d92`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a204`
- `0x18000a5fc`
- `0x18000aa10`
- `0x18000e64c`
- `0x18000e7dc`

## callees

- `0x180010a48`
- `0x180010d18`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180010d5d`
- `KERNEL32!SetLastError` at `0x180010d5d`
- `KERNEL32!GetLastError` at `0x180010d3a`
- `KERNEL32!GetLastError` at `0x180010d3a`
- `KERNEL32!CloseHandle` at `0x180010d4b`
- `KERNEL32!CloseHandle` at `0x180010d4b`

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
0x180010d18  mov     [rsp+arg_0], rbx
0x180010d1d  mov     [rsp+arg_8], rbp
0x180010d22  mov     [rsp+arg_10], rsi
0x180010d27  push    rdi
0x180010d28  sub     rsp, 20h
0x180010d2c  mov     rdi, [rcx]
0x180010d2f  mov     rsi, rdx
0x180010d32  mov     rbx, rcx
0x180010d35  test    rdi, rdi
0x180010d38  jz      short loc_180010D69
0x180010d3a  call    cs:__imp_GetLastError
0x180010d41  nop     dword ptr [rax+rax+00h]
0x180010d46  mov     rcx, rdi; hObject
0x180010d49  mov     ebp, eax
0x180010d4b  call    cs:__imp_CloseHandle
0x180010d52  nop     dword ptr [rax+rax+00h]
0x180010d57  test    eax, eax
0x180010d59  jz      short loc_180010D82
0x180010d5b  mov     ecx, ebp; dwErrCode
0x180010d5d  call    cs:__imp_SetLastError
0x180010d64  nop     dword ptr [rax+rax+00h]
0x180010d69  mov     rbp, [rsp+28h+arg_8]
0x180010d6e  mov     [rbx], rsi
0x180010d71  mov     rbx, [rsp+28h+arg_0]
0x180010d76  mov     rsi, [rsp+28h+arg_10]
0x180010d7b  add     rsp, 20h
0x180010d7f  pop     rdi
0x180010d80  retn
0x180010d82  mov     rcx, [rsp+28h]; this
0x180010d87  mov     edx, 9CDh; void *
0x180010d8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
