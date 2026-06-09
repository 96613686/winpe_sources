# WindowsFireall_EnableFileAndPrinterSharingV2

- ea: `0x1800411cc`
- end: `0x180041215`
- name: `WindowsFireall_EnableFileAndPrinterSharingV2`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b5d8`

## callees

- `0x1800119e0`
- `0x18001211c`
- `0x18004101c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180041207`
- `OLEAUT32!__imp_SysFreeString` at `0x180041207`

## string_xrefs

- `0x1800411da`: `@FirewallAPI.dll,-28672`

## pseudocode

```c
__int64 __fastcall WindowsFireall_EnableFileAndPrinterSharingV2(__int64 a1, _DWORD *a2)
{
  BSTR *v3; // rax
  int v4; // ecx
  BSTR bstrString; // [rsp+40h] [rbp+18h] BYREF
  char v7; // [rsp+48h] [rbp+20h] BYREF

  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"@FirewallAPI.dll,-28672");
  v3 = (BSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v7, (LPCSTR *)&bstrString);
  LODWORD(a2) = WindowsFireall_EnableFWGroup(v4, a2, v3);
  SysFreeString(bstrString);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x1800411cc  push    rbx
0x1800411ce  sub     rsp, 20h
0x1800411d2  mov     rbx, rdx
0x1800411d5  lea     rcx, [rsp+28h+bstrString]; this
0x1800411da  lea     rdx, aFirewallapiDll; "@FirewallAPI.dll,-28672"
0x1800411e1  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800411e6  lea     rdx, [rsp+28h+bstrString]; struct ATL::CComBSTR *
0x1800411eb  lea     rcx, [rsp+28h+arg_18]; this
0x1800411f0  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x1800411f5  mov     r8, rax
0x1800411f8  mov     rdx, rbx
0x1800411fb  call    WindowsFireall_EnableFWGroup
0x180041200  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180041205  mov     ebx, eax
0x180041207  call    cs:__imp_SysFreeString
0x18004120d  mov     eax, ebx
0x18004120f  add     rsp, 20h
0x180041213  pop     rbx
0x180041214  retn
```
