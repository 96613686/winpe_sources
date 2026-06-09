# CPropertyBag::FreePropertyElement(_XWIZARD_PROPERTY_ELEMENT * *)

- ea: `0x18002a854`
- end: `0x18002a88a`
- name: `?FreePropertyElement@CPropertyBag@@AEAAXPEAPEAU_XWIZARD_PROPERTY_ELEMENT@@@Z`
- size: `54`
- prototype: `void __fastcall(CPropertyBag *__hidden this, struct _XWIZARD_PROPERTY_ELEMENT **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a774`
- `0x18002ad04`
- `0x18002ae80`

## callees

- `0x18002a854`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a86e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a86e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a877`

## pseudocode

```c
void __fastcall CPropertyBag::FreePropertyElement(CPropertyBag *this, LPVOID *a2)
{
  void *v3; // rcx

  if ( *a2 )
  {
    v3 = (void *)*((_QWORD *)*a2 + 2);
    if ( v3 )
      CoTaskMemFree(v3);
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x18002a854  push    rbx
0x18002a856  sub     rsp, 20h
0x18002a85a  mov     rcx, [rdx]
0x18002a85d  mov     rbx, rdx
0x18002a860  test    rcx, rcx
0x18002a863  jz      short loc_18002A884
0x18002a865  mov     rcx, [rcx+10h]; pv
0x18002a869  test    rcx, rcx
0x18002a86c  jz      short loc_18002A874
0x18002a86e  call    cs:__imp_CoTaskMemFree
0x18002a874  mov     rcx, [rbx]; pv
0x18002a877  call    cs:__imp_CoTaskMemFree
0x18002a87d  mov     qword ptr [rbx], 0
0x18002a884  add     rsp, 20h
0x18002a888  pop     rbx
0x18002a889  retn
```
