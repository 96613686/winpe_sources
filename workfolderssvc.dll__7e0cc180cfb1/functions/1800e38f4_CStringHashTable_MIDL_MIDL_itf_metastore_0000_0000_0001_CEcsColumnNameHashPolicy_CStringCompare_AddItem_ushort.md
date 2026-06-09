# CStringHashTable<__MIDL___MIDL_itf_metastore_0000_0000_0001,CEcsColumnNameHashPolicy,CStringCompare>::AddItem(ushort const * const &,__MIDL___MIDL_itf_metastore_0000_0000_0001 const &)

- ea: `0x1800e38f4`
- end: `0x1800e395b`
- name: `?AddItem@?$CStringHashTable@W4__MIDL___MIDL_itf_metastore_0000_0000_0001@@VCEcsColumnNameHashPolicy@@VCStringCompare@@@@QEAAJAEBQEBGAEBW4__MIDL___MIDL_itf_metastore_0000_0000_0001@@@Z`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e5e60`
- `0x1800ec330`

## callees

- `0x1800e2870`
- `0x1800e38f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3943`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3943`
- `SHLWAPI!SHStrDupW` at `0x1800e391c`
- `SHLWAPI!SHStrDupW` at `0x1800e391c`

## pseudocode

```c
__int64 __fastcall CStringHashTable<enum __MIDL___MIDL_itf_metastore_0000_0000_0001,CEcsColumnNameHashPolicy,CStringCompare>::AddItem(
        __int64 a1,
        LPCWSTR *a2,
        __int64 a3)
{
  __int64 v5; // rdx
  HRESULT updated; // ebx
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  pv = 0;
  updated = SHStrDupW(*a2, (LPWSTR *)&pv);
  if ( updated >= 0 )
  {
    updated = CSimpleHashTable<unsigned short const *,enum __MIDL___MIDL_itf_metastore_0000_0000_0001,CEcsColumnNameHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                a1,
                v5,
                &pv,
                a3);
    if ( updated < 0 )
      CoTaskMemFree(pv);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800e38f4  mov     r11, rsp
0x1800e38f7  mov     [r11+8], rbx
0x1800e38fb  mov     [r11+10h], rsi
0x1800e38ff  push    rdi
0x1800e3900  sub     rsp, 30h
0x1800e3904  mov     rax, rdx
0x1800e3907  mov     qword ptr [r11+20h], 0
0x1800e390f  mov     rsi, rcx
0x1800e3912  lea     rdx, [r11+20h]; ppwsz
0x1800e3916  mov     rdi, r8
0x1800e3919  mov     rcx, [rax]; psz
0x1800e391c  call    cs:__imp_SHStrDupW
0x1800e3922  mov     ebx, eax
0x1800e3924  test    eax, eax
0x1800e3926  js      short loc_1800E3949
0x1800e3928  mov     r9, rdi
0x1800e392b  lea     r8, [rsp+38h+pv]
0x1800e3930  mov     rcx, rsi
0x1800e3933  call    ?_AddUpdateItem@?$CSimpleHashTable@PEBGW4__MIDL___MIDL_itf_metastore_0000_0000_0001@@VCEcsColumnNameHashPolicy@@VCStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBQEBGAEBW4__MIDL___MIDL_itf_metastore_0000_0000_0001@@PEAW42@@Z; CSimpleHashTable<ushort const *,__MIDL___MIDL_itf_metastore_0000_0000_0001,CEcsColumnNameHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,ushort const * const &,__MIDL___MIDL_itf_metastore_0000_0000_0001 const &,__MIDL___MIDL_itf_metastore_0000_0000_0001 *)
0x1800e3938  mov     ebx, eax
0x1800e393a  test    eax, eax
0x1800e393c  jns     short loc_1800E3949
0x1800e393e  mov     rcx, [rsp+38h+pv]; pv
0x1800e3943  call    cs:__imp_CoTaskMemFree
0x1800e3949  mov     rsi, [rsp+38h+arg_8]
0x1800e394e  mov     eax, ebx
0x1800e3950  mov     rbx, [rsp+38h+arg_0]
0x1800e3955  add     rsp, 30h
0x1800e3959  pop     rdi
0x1800e395a  retn
```
