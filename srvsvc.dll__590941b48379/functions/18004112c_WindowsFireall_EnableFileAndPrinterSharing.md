# WindowsFireall_EnableFileAndPrinterSharing

- ea: `0x18004112c`
- end: `0x180041175`
- name: `WindowsFireall_EnableFileAndPrinterSharing`
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

- `OLEAUT32!__imp_SysFreeString` at `0x180041167`
- `OLEAUT32!__imp_SysFreeString` at `0x180041167`

## string_xrefs

- `0x18004113a`: `@FirewallAPI.dll,-28502`

## pseudocode

```c
__int64 __fastcall WindowsFireall_EnableFileAndPrinterSharing(__int64 a1, _DWORD *a2)
{
  BSTR *v3; // rax
  int v4; // ecx
  BSTR bstrString; // [rsp+40h] [rbp+18h] BYREF
  char v7; // [rsp+48h] [rbp+20h] BYREF

  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"@FirewallAPI.dll,-28502");
  v3 = (BSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v7, (LPCSTR *)&bstrString);
  LODWORD(a2) = WindowsFireall_EnableFWGroup(v4, a2, v3);
  SysFreeString(bstrString);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x18004112c  push    rbx
0x18004112e  sub     rsp, 20h
0x180041132  mov     rbx, rdx
0x180041135  lea     rcx, [rsp+28h+bstrString]; this
0x18004113a  lea     rdx, psz; "@FirewallAPI.dll,-28502"
0x180041141  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180041146  lea     rdx, [rsp+28h+bstrString]; struct ATL::CComBSTR *
0x18004114b  lea     rcx, [rsp+28h+arg_18]; this
0x180041150  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x180041155  mov     r8, rax
0x180041158  mov     rdx, rbx
0x18004115b  call    WindowsFireall_EnableFWGroup
0x180041160  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180041165  mov     ebx, eax
0x180041167  call    cs:__imp_SysFreeString
0x18004116d  mov     eax, ebx
0x18004116f  add     rsp, 20h
0x180041173  pop     rbx
0x180041174  retn
```
