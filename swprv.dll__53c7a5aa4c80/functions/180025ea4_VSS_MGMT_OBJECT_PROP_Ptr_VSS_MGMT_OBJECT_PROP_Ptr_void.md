# VSS_MGMT_OBJECT_PROP_Ptr::~VSS_MGMT_OBJECT_PROP_Ptr(void)

- ea: `0x180025ea4`
- end: `0x180025ec9`
- name: `??1VSS_MGMT_OBJECT_PROP_Ptr@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026da0`
- `0x180027530`
- `0x18002b490`
- `0x18002c080`
- `0x18002c830`
- `0x18002d1f0`
- `0x180047319`
- `0x18004839f`
- `0x18004855e`
- `0x18004889a`

## callees

- `0x180025ea4`
- `0x18003aad8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ebd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ebd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall VSS_MGMT_OBJECT_PROP_Ptr::~VSS_MGMT_OBJECT_PROP_Ptr(LPVOID *this)
{
  struct _VSS_MGMT_OBJECT_PROP *v2; // rcx

  v2 = (struct _VSS_MGMT_OBJECT_PROP *)*this;
  if ( v2 )
  {
    VSS_MGMT_OBJECT_PROP_Copy::destroy(v2);
    CoTaskMemFree(*this);
  }
}

```

## disassembly

```asm
0x180025ea4  push    rbx
0x180025ea6  sub     rsp, 20h
0x180025eaa  mov     rbx, rcx
0x180025ead  mov     rcx, [rcx]; struct _VSS_MGMT_OBJECT_PROP *
0x180025eb0  test    rcx, rcx
0x180025eb3  jz      short loc_180025EC3
0x180025eb5  call    ?destroy@VSS_MGMT_OBJECT_PROP_Copy@@SAXPEAU_VSS_MGMT_OBJECT_PROP@@@Z; VSS_MGMT_OBJECT_PROP_Copy::destroy(_VSS_MGMT_OBJECT_PROP *)
0x180025eba  mov     rcx, [rbx]; pv
0x180025ebd  call    cs:__imp_CoTaskMemFree
0x180025ec3  add     rsp, 20h
0x180025ec7  pop     rbx
0x180025ec8  retn
```
