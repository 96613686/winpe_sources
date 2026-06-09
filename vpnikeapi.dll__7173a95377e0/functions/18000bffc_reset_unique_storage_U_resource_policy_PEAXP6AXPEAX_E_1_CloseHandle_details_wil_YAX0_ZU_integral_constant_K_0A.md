# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18000bffc`
- end: `0x18000c048`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007f30`
- `0x180008098`
- `0x1800083cc`
- `0x18000be04`

## callees

- `0x1800078cc`
- `0x180007e30`
- `0x180008200`
- `0x18000bffc`

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
0x18000bffc  mov     [rsp+arg_8], rbx
0x18000c001  mov     [rsp+arg_10], rsi
0x18000c006  push    rdi
0x18000c007  sub     rsp, 20h
0x18000c00b  mov     rdi, [rcx]
0x18000c00e  mov     rsi, rdx
0x18000c011  mov     rbx, rcx
0x18000c014  test    rdi, rdi
0x18000c017  jz      short loc_18000C035
0x18000c019  lea     rcx, [rsp+28h+arg_0]; this
0x18000c01e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000c023  mov     rcx, rdi; this
0x18000c026  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000c02b  lea     rcx, [rsp+28h+arg_0]; this
0x18000c030  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000c035  mov     [rbx], rsi
0x18000c038  mov     rbx, [rsp+28h+arg_8]
0x18000c03d  mov     rsi, [rsp+28h+arg_10]
0x18000c042  add     rsp, 20h
0x18000c046  pop     rdi
0x18000c047  retn
```
