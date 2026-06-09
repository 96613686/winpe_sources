# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18000bae8`
- end: `0x18000bb62`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003b34`
- `0x180003f2c`
- `0x180004e8c`
- `0x180009638`
- `0x1800097c8`

## callees

- `0x18000b828`
- `0x18000bae8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000bb2d`
- `KERNEL32!SetLastError` at `0x18000bb2d`
- `KERNEL32!GetLastError` at `0x18000bb0a`
- `KERNEL32!GetLastError` at `0x18000bb0a`
- `KERNEL32!CloseHandle` at `0x18000bb1b`
- `KERNEL32!CloseHandle` at `0x18000bb1b`

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
0x18000bae8  mov     [rsp+arg_0], rbx
0x18000baed  mov     [rsp+arg_8], rbp
0x18000baf2  mov     [rsp+arg_10], rsi
0x18000baf7  push    rdi
0x18000baf8  sub     rsp, 20h
0x18000bafc  mov     rdi, [rcx]
0x18000baff  mov     rsi, rdx
0x18000bb02  mov     rbx, rcx
0x18000bb05  test    rdi, rdi
0x18000bb08  jz      short loc_18000BB39
0x18000bb0a  call    cs:__imp_GetLastError
0x18000bb11  nop     dword ptr [rax+rax+00h]
0x18000bb16  mov     rcx, rdi; hObject
0x18000bb19  mov     ebp, eax
0x18000bb1b  call    cs:__imp_CloseHandle
0x18000bb22  nop     dword ptr [rax+rax+00h]
0x18000bb27  test    eax, eax
0x18000bb29  jz      short loc_18000BB52
0x18000bb2b  mov     ecx, ebp; dwErrCode
0x18000bb2d  call    cs:__imp_SetLastError
0x18000bb34  nop     dword ptr [rax+rax+00h]
0x18000bb39  mov     rbp, [rsp+28h+arg_8]
0x18000bb3e  mov     [rbx], rsi
0x18000bb41  mov     rbx, [rsp+28h+arg_0]
0x18000bb46  mov     rsi, [rsp+28h+arg_10]
0x18000bb4b  add     rsp, 20h
0x18000bb4f  pop     rdi
0x18000bb50  retn
0x18000bb52  mov     rcx, [rsp+28h]; this
0x18000bb57  mov     edx, 9CDh; void *
0x18000bb5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
