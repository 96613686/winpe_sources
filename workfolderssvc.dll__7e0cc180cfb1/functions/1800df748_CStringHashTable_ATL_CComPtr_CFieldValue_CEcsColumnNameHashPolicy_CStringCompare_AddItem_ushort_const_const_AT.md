# CStringHashTable<ATL::CComPtr<CFieldValue>,CEcsColumnNameHashPolicy,CStringCompare>::AddItem(ushort const * const &,ATL::CComPtr<CFieldValue> const &)

- ea: `0x1800df748`
- end: `0x1800df7af`
- name: `?AddItem@?$CStringHashTable@V?$CComPtr@VCFieldValue@@@ATL@@VCEcsColumnNameHashPolicy@@VCStringCompare@@@@QEAAJAEBQEBGAEBV?$CComPtr@VCFieldValue@@@ATL@@@Z`
- size: `103`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800df690`
- `0x1800e1e98`
- `0x1800ed734`
- `0x1800ef2e8`

## callees

- `0x1800df748`
- `0x1800e12d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df797`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df797`
- `SHLWAPI!SHStrDupW` at `0x1800df770`
- `SHLWAPI!SHStrDupW` at `0x1800df770`

## pseudocode

```c
__int64 __fastcall CStringHashTable<ATL::CComPtr<CFieldValue>,CEcsColumnNameHashPolicy,CStringCompare>::AddItem(
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
    updated = CSimpleHashTable<unsigned short const *,ATL::CComPtr<CFieldValue>,CEcsColumnNameHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
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
0x1800df748  mov     r11, rsp
0x1800df74b  mov     [r11+8], rbx
0x1800df74f  mov     [r11+10h], rsi
0x1800df753  push    rdi
0x1800df754  sub     rsp, 30h
0x1800df758  mov     rax, rdx
0x1800df75b  mov     qword ptr [r11+20h], 0
0x1800df763  mov     rsi, rcx
0x1800df766  lea     rdx, [r11+20h]; ppwsz
0x1800df76a  mov     rdi, r8
0x1800df76d  mov     rcx, [rax]; psz
0x1800df770  call    cs:__imp_SHStrDupW
0x1800df776  mov     ebx, eax
0x1800df778  test    eax, eax
0x1800df77a  js      short loc_1800DF79D
0x1800df77c  mov     r9, rdi
0x1800df77f  lea     r8, [rsp+38h+pv]
0x1800df784  mov     rcx, rsi
0x1800df787  call    ?_AddUpdateItem@?$CSimpleHashTable@PEBGV?$CComPtr@VCFieldValue@@@ATL@@VCEcsColumnNameHashPolicy@@VCStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBQEBGAEBV?$CComPtr@VCFieldValue@@@ATL@@PEAV23@@Z; CSimpleHashTable<ushort const *,ATL::CComPtr<CFieldValue>,CEcsColumnNameHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,ushort const * const &,ATL::CComPtr<CFieldValue> const &,ATL::CComPtr<CFieldValue> *)
0x1800df78c  mov     ebx, eax
0x1800df78e  test    eax, eax
0x1800df790  jns     short loc_1800DF79D
0x1800df792  mov     rcx, [rsp+38h+pv]; pv
0x1800df797  call    cs:__imp_CoTaskMemFree
0x1800df79d  mov     rsi, [rsp+38h+arg_8]
0x1800df7a2  mov     eax, ebx
0x1800df7a4  mov     rbx, [rsp+38h+arg_0]
0x1800df7a9  add     rsp, 30h
0x1800df7ad  pop     rdi
0x1800df7ae  retn
```
