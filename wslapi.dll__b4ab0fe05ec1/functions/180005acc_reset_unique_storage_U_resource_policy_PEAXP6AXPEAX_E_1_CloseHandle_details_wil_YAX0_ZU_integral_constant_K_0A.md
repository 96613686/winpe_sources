# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180005acc`
- end: `0x180005b18`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003638`
- `0x180004cfc`
- `0x180005a74`
- `0x1800086b0`

## callees

- `0x180003338`
- `0x180003584`
- `0x1800037f4`
- `0x180005acc`

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
0x180005acc  mov     [rsp+arg_8], rbx
0x180005ad1  mov     [rsp+arg_10], rsi
0x180005ad6  push    rdi
0x180005ad7  sub     rsp, 20h
0x180005adb  mov     rdi, [rcx]
0x180005ade  mov     rsi, rdx
0x180005ae1  mov     rbx, rcx
0x180005ae4  test    rdi, rdi
0x180005ae7  jz      short loc_180005B05
0x180005ae9  lea     rcx, [rsp+28h+arg_0]; this
0x180005aee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180005af3  mov     rcx, rdi; this
0x180005af6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005afb  lea     rcx, [rsp+28h+arg_0]; this
0x180005b00  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180005b05  mov     [rbx], rsi
0x180005b08  mov     rbx, [rsp+28h+arg_8]
0x180005b0d  mov     rsi, [rsp+28h+arg_10]
0x180005b12  add     rsp, 20h
0x180005b16  pop     rdi
0x180005b17  retn
```
