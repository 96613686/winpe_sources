# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x18000d9b4`
- end: `0x18000d9ca`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d8ac`
- `0x18000de78`
- `0x18000dfe0`
- `0x180010a84`
- `0x180010b04`

## callees

- `0x18000d9b4`
- `0x180010bcc`

## pseudocode

```c
void __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rcx

  v2 = *a1;
  if ( v2 )
    wil::details::ReleaseMutex(v2, a2);
}

```

## disassembly

```asm
0x18000d9b4  sub     rsp, 28h
0x18000d9b8  mov     rcx, [rcx]; this
0x18000d9bb  test    rcx, rcx
0x18000d9be  jz      short loc_18000D9C5
0x18000d9c0  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000d9c5  add     rsp, 28h
0x18000d9c9  retn
```
