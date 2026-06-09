# VSS_OBJECT_PROP_Ptr::~VSS_OBJECT_PROP_Ptr(void)

- ea: `0x18000dd84`
- end: `0x18000dda9`
- name: `??1VSS_OBJECT_PROP_Ptr@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `8`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e900`
- `0x180014fa0`
- `0x1800186e0`
- `0x18001c5dc`
- `0x180043820`
- `0x180045c0f`
- `0x180045c25`
- `0x180046672`

## callees

- `0x18000dd84`
- `0x18003abc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall VSS_OBJECT_PROP_Ptr::~VSS_OBJECT_PROP_Ptr(LPVOID *this)
{
  struct _VSS_OBJECT_PROP *v2; // rcx

  v2 = (struct _VSS_OBJECT_PROP *)*this;
  if ( v2 )
  {
    VSS_OBJECT_PROP_Copy::destroy(v2);
    CoTaskMemFree(*this);
  }
}

```

## disassembly

```asm
0x18000dd84  push    rbx
0x18000dd86  sub     rsp, 20h
0x18000dd8a  mov     rbx, rcx
0x18000dd8d  mov     rcx, [rcx]; struct _VSS_OBJECT_PROP *
0x18000dd90  test    rcx, rcx
0x18000dd93  jz      short loc_18000DDA3
0x18000dd95  call    ?destroy@VSS_OBJECT_PROP_Copy@@SAXPEAU_VSS_OBJECT_PROP@@@Z; VSS_OBJECT_PROP_Copy::destroy(_VSS_OBJECT_PROP *)
0x18000dd9a  mov     rcx, [rbx]; pv
0x18000dd9d  call    cs:__imp_CoTaskMemFree
0x18000dda3  add     rsp, 20h
0x18000dda7  pop     rbx
0x18000dda8  retn
```
