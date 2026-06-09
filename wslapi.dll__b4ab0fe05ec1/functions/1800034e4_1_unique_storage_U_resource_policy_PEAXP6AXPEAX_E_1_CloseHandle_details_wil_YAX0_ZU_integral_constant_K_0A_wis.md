# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x1800034e4`
- end: `0x1800034fa`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000337c`
- `0x18000355c`
- `0x180003638`
- `0x1800056a8`
- `0x180008594`
- `0x1800086b0`
- `0x18000c0bf`

## callees

- `0x1800034e4`
- `0x1800037f4`

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
0x1800034e4  sub     rsp, 28h
0x1800034e8  mov     rcx, [rcx]; this
0x1800034eb  test    rcx, rcx
0x1800034ee  jz      short loc_1800034F5
0x1800034f0  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800034f5  add     rsp, 28h
0x1800034f9  retn
```
