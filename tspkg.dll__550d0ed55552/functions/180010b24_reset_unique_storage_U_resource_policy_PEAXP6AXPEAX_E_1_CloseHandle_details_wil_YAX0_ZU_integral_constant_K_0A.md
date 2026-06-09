# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180010b24`
- end: `0x180010b70`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d724`
- `0x18000d88c`
- `0x18000dbbc`
- `0x180010988`

## callees

- `0x18000d334`
- `0x18000d61c`
- `0x18000d9f4`
- `0x180010b24`

## pseudocode

```c
void __fastcall _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        wil::details **a1,
        wil::details *a2)
{
  wil::details *v2; // rdi
  void *v5; // rdx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v6);
    wil::details::CloseHandle(v2, v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v6);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180010b24  mov     [rsp+arg_8], rbx
0x180010b29  mov     [rsp+arg_10], rsi
0x180010b2e  push    rdi
0x180010b2f  sub     rsp, 20h
0x180010b33  mov     rdi, [rcx]
0x180010b36  mov     rsi, rdx
0x180010b39  mov     rbx, rcx
0x180010b3c  test    rdi, rdi
0x180010b3f  jz      short loc_180010B5D
0x180010b41  lea     rcx, [rsp+28h+arg_0]; this
0x180010b46  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180010b4b  mov     rcx, rdi; this
0x180010b4e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180010b53  lea     rcx, [rsp+28h+arg_0]; this
0x180010b58  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180010b5d  mov     [rbx], rsi
0x180010b60  mov     rbx, [rsp+28h+arg_8]
0x180010b65  mov     rsi, [rsp+28h+arg_10]
0x180010b6a  add     rsp, 20h
0x180010b6e  pop     rdi
0x180010b6f  retn
```
