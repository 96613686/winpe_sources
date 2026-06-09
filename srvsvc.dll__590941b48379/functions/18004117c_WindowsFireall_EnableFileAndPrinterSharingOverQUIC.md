# WindowsFireall_EnableFileAndPrinterSharingOverQUIC

- ea: `0x18004117c`
- end: `0x1800411c5`
- name: `WindowsFireall_EnableFileAndPrinterSharingOverQUIC`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031c8c`

## callees

- `0x1800119e0`
- `0x18001211c`
- `0x18004101c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800411b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800411b7`

## string_xrefs

- `0x18004118a`: `@FirewallAPI.dll,-28652`

## pseudocode

```c
__int64 __fastcall WindowsFireall_EnableFileAndPrinterSharingOverQUIC(__int64 a1, _DWORD *a2)
{
  BSTR *v3; // rax
  int v4; // ecx
  BSTR bstrString; // [rsp+40h] [rbp+18h] BYREF
  char v7; // [rsp+48h] [rbp+20h] BYREF

  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"@FirewallAPI.dll,-28652");
  v3 = (BSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v7, (LPCSTR *)&bstrString);
  LODWORD(a2) = WindowsFireall_EnableFWGroup(v4, a2, v3);
  SysFreeString(bstrString);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x18004117c  push    rbx
0x18004117e  sub     rsp, 20h
0x180041182  mov     rbx, rdx
0x180041185  lea     rcx, [rsp+28h+bstrString]; this
0x18004118a  lea     rdx, aFirewallapiDll_0; "@FirewallAPI.dll,-28652"
0x180041191  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180041196  lea     rdx, [rsp+28h+bstrString]; struct ATL::CComBSTR *
0x18004119b  lea     rcx, [rsp+28h+arg_18]; this
0x1800411a0  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x1800411a5  mov     r8, rax
0x1800411a8  mov     rdx, rbx
0x1800411ab  call    WindowsFireall_EnableFWGroup
0x1800411b0  mov     rcx, [rsp+28h+bstrString]; bstrString
0x1800411b5  mov     ebx, eax
0x1800411b7  call    cs:__imp_SysFreeString
0x1800411bd  mov     eax, ebx
0x1800411bf  add     rsp, 20h
0x1800411c3  pop     rbx
0x1800411c4  retn
```
