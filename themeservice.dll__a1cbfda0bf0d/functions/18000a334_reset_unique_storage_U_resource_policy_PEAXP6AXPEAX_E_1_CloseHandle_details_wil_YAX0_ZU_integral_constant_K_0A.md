# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18000a334`
- end: `0x18000a380`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008790`
- `0x180008a50`
- `0x18000a2dc`
- `0x18000a99c`

## callees

- `0x180006fec`
- `0x180007070`
- `0x1800088f8`
- `0x18000a334`

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
0x18000a334  mov     [rsp+arg_8], rbx
0x18000a339  mov     [rsp+arg_10], rsi
0x18000a33e  push    rdi
0x18000a33f  sub     rsp, 20h
0x18000a343  mov     rdi, [rcx]
0x18000a346  mov     rsi, rdx
0x18000a349  mov     rbx, rcx
0x18000a34c  test    rdi, rdi
0x18000a34f  jz      short loc_18000A36D
0x18000a351  lea     rcx, [rsp+28h+arg_0]; this
0x18000a356  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a35b  mov     rcx, rdi; this
0x18000a35e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000a363  lea     rcx, [rsp+28h+arg_0]; this
0x18000a368  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a36d  mov     [rbx], rsi
0x18000a370  mov     rbx, [rsp+28h+arg_8]
0x18000a375  mov     rsi, [rsp+28h+arg_10]
0x18000a37a  add     rsp, 20h
0x18000a37e  pop     rdi
0x18000a37f  retn
```
