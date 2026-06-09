# DllRegisterServer

- ea: `0x180012790`
- end: `0x1800128a9`
- name: `DllRegisterServer`
- size: `281`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012790`

## import_xrefs

- `wbemcomn!RegisterDLL` at `0x1800127c9`
- `wbemcomn!RegisterDLL` at `0x1800127fb`
- `wbemcomn!RegisterDLL` at `0x180012837`
- `wbemcomn!RegisterDLL` at `0x180012869`
- `wbemcomn!RegisterDLL` at `0x18001289b`
- `wbemcomn!RegisterDLL` at `0x1800127c9`
- `wbemcomn!RegisterDLL` at `0x1800127fb`
- `wbemcomn!RegisterDLL` at `0x180012837`
- `wbemcomn!RegisterDLL` at `0x180012869`
- `wbemcomn!RegisterDLL` at `0x18001289b`
- `wbemcomn!IsNT` at `0x180012801`
- `wbemcomn!IsNT` at `0x180012801`

## string_xrefs

- `0x1800127b7`: `WBEM Registry Instance Provider`
- `0x1800127dd`: `WBEM Registry Property Provider`
- `0x18001287d`: `WBEM Registry Event Provider`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  GUID v1; // [rsp+30h] [rbp-18h] BYREF

  v1 = CLSID_RegProvider;
  RegisterDLL(ghModule, &v1, L"WBEM Registry Instance Provider", L"Both", 0);
  v1 = CLSID_RegPropProv;
  RegisterDLL(ghModule, &v1, L"WBEM Registry Property Provider", L"Both", 0);
  if ( IsNT() )
  {
    v1 = CLSID_PerfProvider;
    RegisterDLL(ghModule, &v1, L"WBEM PerfMon Instance Provider", L"Both", 0);
    v1 = CLSID_PerfPropProv;
    RegisterDLL(ghModule, &v1, L"WBEM PerfMon Property Provider", L"Both", 0);
  }
  v1 = CLSID_RegistryEventProvider;
  RegisterDLL(ghModule, &v1, L"WBEM Registry Event Provider", L"Both", 0);
  return 0;
}

```

## disassembly

```asm
0x180012790  push    rdi
0x180012792  sub     rsp, 40h
0x180012796  movups  xmm0, xmmword ptr cs:CLSID_RegProvider.Data1
0x18001279d  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghModule
0x1800127a4  lea     rdi, aBoth; "Both"
0x1800127ab  mov     r9, rdi
0x1800127ae  mov     [rsp+48h+var_28], 0
0x1800127b7  lea     r8, aWbemRegistryIn; "WBEM Registry Instance Provider"
0x1800127be  lea     rdx, [rsp+48h+var_18]
0x1800127c3  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x1800127c9  call    cs:__imp_?RegisterDLL@@YAXPEAUHINSTANCE__@@U_GUID@@PEAG22@Z; RegisterDLL(HINSTANCE__ *,_GUID,ushort *,ushort *,ushort *)
0x1800127cf  movups  xmm0, xmmword ptr cs:CLSID_RegPropProv.Data1
0x1800127d6  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghModule
0x1800127dd  lea     r8, aWbemRegistryPr; "WBEM Registry Property Provider"
0x1800127e4  mov     r9, rdi
0x1800127e7  mov     [rsp+48h+var_28], 0
0x1800127f0  lea     rdx, [rsp+48h+var_18]
0x1800127f5  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x1800127fb  call    cs:__imp_?RegisterDLL@@YAXPEAUHINSTANCE__@@U_GUID@@PEAG22@Z; RegisterDLL(HINSTANCE__ *,_GUID,ushort *,ushort *,ushort *)
0x180012801  call    cs:__imp_?IsNT@@YAHXZ; IsNT(void)
0x180012807  test    eax, eax
0x180012809  jz      short loc_18001286F
0x18001280b  movups  xmm0, xmmword ptr cs:CLSID_PerfProvider.Data1
0x180012812  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghModule
0x180012819  lea     r8, aWbemPerfmonIns; "WBEM PerfMon Instance Provider"
0x180012820  mov     r9, rdi
0x180012823  mov     [rsp+48h+var_28], 0
0x18001282c  lea     rdx, [rsp+48h+var_18]
0x180012831  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x180012837  call    cs:__imp_?RegisterDLL@@YAXPEAUHINSTANCE__@@U_GUID@@PEAG22@Z; RegisterDLL(HINSTANCE__ *,_GUID,ushort *,ushort *,ushort *)
0x18001283d  movups  xmm0, xmmword ptr cs:CLSID_PerfPropProv.Data1
0x180012844  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghModule
0x18001284b  lea     r8, aWbemPerfmonPro; "WBEM PerfMon Property Provider"
0x180012852  mov     r9, rdi
0x180012855  mov     [rsp+48h+var_28], 0
0x18001285e  lea     rdx, [rsp+48h+var_18]
0x180012863  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x180012869  call    cs:__imp_?RegisterDLL@@YAXPEAUHINSTANCE__@@U_GUID@@PEAG22@Z; RegisterDLL(HINSTANCE__ *,_GUID,ushort *,ushort *,ushort *)
0x18001286f  movups  xmm0, xmmword ptr cs:?CLSID_RegistryEventProvider@@3U_GUID@@B.Data1; _GUID const CLSID_RegistryEventProvider ...
0x180012876  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghModule
0x18001287d  lea     r8, aWbemRegistryEv; "WBEM Registry Event Provider"
0x180012884  mov     r9, rdi
0x180012887  mov     [rsp+48h+var_28], 0
0x180012890  lea     rdx, [rsp+48h+var_18]
0x180012895  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x18001289b  call    cs:__imp_?RegisterDLL@@YAXPEAUHINSTANCE__@@U_GUID@@PEAG22@Z; RegisterDLL(HINSTANCE__ *,_GUID,ushort *,ushort *,ushort *)
0x1800128a1  xor     eax, eax
0x1800128a3  add     rsp, 40h
0x1800128a7  pop     rdi
0x1800128a8  retn
```
