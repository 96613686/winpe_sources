# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18001ca0c`
- end: `0x18001ca59`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018b04`
- `0x180018c78`
- `0x180019070`
- `0x18001c7f0`

## callees

- `0x180018570`
- `0x180018a00`
- `0x180018e88`
- `0x18001ca0c`

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
0x18001ca0c  mov     [rsp+arg_8], rbx
0x18001ca11  mov     [rsp+arg_10], rsi
0x18001ca16  push    rdi
0x18001ca17  sub     rsp, 20h
0x18001ca1b  mov     rdi, [rcx]
0x18001ca1e  mov     rsi, rdx
0x18001ca21  mov     rbx, rcx
0x18001ca24  test    rdi, rdi
0x18001ca27  jz      short loc_18001CA45
0x18001ca29  lea     rcx, [rsp+28h+arg_0]; this
0x18001ca2e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ca33  mov     rcx, rdi; this
0x18001ca36  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001ca3b  lea     rcx, [rsp+28h+arg_0]; this
0x18001ca40  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ca45  mov     [rbx], rsi
0x18001ca48  mov     rbx, [rsp+28h+arg_8]
0x18001ca4d  mov     rsi, [rsp+28h+arg_10]
0x18001ca52  add     rsp, 20h
0x18001ca56  pop     rdi
0x18001ca57  retn
```
