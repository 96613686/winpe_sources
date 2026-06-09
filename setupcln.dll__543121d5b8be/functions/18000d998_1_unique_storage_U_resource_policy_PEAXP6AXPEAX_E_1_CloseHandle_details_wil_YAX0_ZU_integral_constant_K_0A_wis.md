# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x18000d998`
- end: `0x18000d9ae`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d6e4`
- `0x18000d714`
- `0x18000d8a0`
- `0x18000db18`
- `0x18000de78`
- `0x18000dfe0`
- `0x1800117e0`

## callees

- `0x18000d998`
- `0x18000e148`

## pseudocode

```c
void __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rcx

  v2 = *a1;
  if ( v2 )
    wil::details::CloseHandle(v2, a2);
}

```

## disassembly

```asm
0x18000d998  sub     rsp, 28h
0x18000d99c  mov     rcx, [rcx]; this
0x18000d99f  test    rcx, rcx
0x18000d9a2  jz      short loc_18000D9A9
0x18000d9a4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000d9a9  add     rsp, 28h
0x18000d9ad  retn
```
