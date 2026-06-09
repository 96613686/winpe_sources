# CIniPropertyBag::~CIniPropertyBag(void)

- ea: `0x18002c4a8`
- end: `0x18002c51e`
- name: `??1CIniPropertyBag@@EEAA@XZ`
- size: `118`
- prototype: `void __fastcall(CIniPropertyBag *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c530`

## callees

- `0x18002c4a8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4d5`

## pseudocode

```c
void __fastcall CIniPropertyBag::~CIniPropertyBag(CIniPropertyBag *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CIniPropertyBag::`vftable'{for `IPropertyBag'};
  *((_QWORD *)this + 1) = &CRegPropertyBag::`vftable'{for `IPropertyBag2'};
  *((_QWORD *)this + 2) = &CBasePropertyBag::`vftable'{for `IDataProvider'};
  CoTaskMemFree(*((LPVOID *)this + 5));
  v2 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *(_QWORD *)this = &CBasePropertyBag::`vftable'{for `IPropertyBag'};
  *((_QWORD *)this + 1) = &CRegPropertyBag::`vftable'{for `IPropertyBag2'};
  *((_QWORD *)this + 2) = &CBasePropertyBag::`vftable'{for `IDataProvider'};
}

```

## disassembly

```asm
0x18002c4a8  push    rbx
0x18002c4aa  sub     rsp, 20h
0x18002c4ae  lea     rax, ??_7CIniPropertyBag@@6BIPropertyBag@@@; const CIniPropertyBag::`vftable'{for `IPropertyBag'}
0x18002c4b5  mov     rbx, rcx
0x18002c4b8  mov     [rcx], rax
0x18002c4bb  lea     rax, ??_7CRegPropertyBag@@6BIPropertyBag2@@@; const CRegPropertyBag::`vftable'{for `IPropertyBag2'}
0x18002c4c2  mov     [rcx+8], rax
0x18002c4c6  lea     rax, ??_7CBasePropertyBag@@6BIDataProvider@@@; const CBasePropertyBag::`vftable'{for `IDataProvider'}
0x18002c4cd  mov     [rcx+10h], rax
0x18002c4d1  mov     rcx, [rcx+28h]; pv
0x18002c4d5  call    cs:__imp_CoTaskMemFree
0x18002c4db  mov     rcx, [rbx+20h]
0x18002c4df  mov     qword ptr [rbx+20h], 0
0x18002c4e7  test    rcx, rcx
0x18002c4ea  jz      short loc_18002C4F8
0x18002c4ec  mov     rax, [rcx]
0x18002c4ef  mov     rax, [rax+10h]
0x18002c4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4f8  lea     rax, ??_7CBasePropertyBag@@6BIPropertyBag@@@; const CBasePropertyBag::`vftable'{for `IPropertyBag'}
0x18002c4ff  mov     [rbx], rax
0x18002c502  lea     rax, ??_7CRegPropertyBag@@6BIPropertyBag2@@@; const CRegPropertyBag::`vftable'{for `IPropertyBag2'}
0x18002c509  mov     [rbx+8], rax
0x18002c50d  lea     rax, ??_7CBasePropertyBag@@6BIDataProvider@@@; const CBasePropertyBag::`vftable'{for `IDataProvider'}
0x18002c514  mov     [rbx+10h], rax
0x18002c518  add     rsp, 20h
0x18002c51c  pop     rbx
0x18002c51d  retn
```
