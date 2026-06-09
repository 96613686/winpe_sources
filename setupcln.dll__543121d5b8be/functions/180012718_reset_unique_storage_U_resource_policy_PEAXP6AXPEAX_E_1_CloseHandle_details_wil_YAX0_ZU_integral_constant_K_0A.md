# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180012718`
- end: `0x180012764`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000de78`
- `0x18000dfe0`
- `0x18000e31c`
- `0x180011f78`

## callees

- `0x18000d650`
- `0x18000dbd4`
- `0x18000e148`
- `0x180012718`

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
0x180012718  mov     [rsp+arg_8], rbx
0x18001271d  mov     [rsp+arg_10], rsi
0x180012722  push    rdi
0x180012723  sub     rsp, 20h
0x180012727  mov     rdi, [rcx]
0x18001272a  mov     rsi, rdx
0x18001272d  mov     rbx, rcx
0x180012730  test    rdi, rdi
0x180012733  jz      short loc_180012751
0x180012735  lea     rcx, [rsp+28h+arg_0]; this
0x18001273a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001273f  mov     rcx, rdi; this
0x180012742  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180012747  lea     rcx, [rsp+28h+arg_0]; this
0x18001274c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180012751  mov     [rbx], rsi
0x180012754  mov     rbx, [rsp+28h+arg_8]
0x180012759  mov     rsi, [rsp+28h+arg_10]
0x18001275e  add     rsp, 20h
0x180012762  pop     rdi
0x180012763  retn
```
