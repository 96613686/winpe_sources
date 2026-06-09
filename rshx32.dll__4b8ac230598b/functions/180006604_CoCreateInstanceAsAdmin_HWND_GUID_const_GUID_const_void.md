# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180006604`
- end: `0x1800066f3`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007670`

## callees

- `0x180005684`
- `0x180006604`
- `0x18001d370`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006660`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006660`
- `ole32!CoGetObject` at `0x1800066c9`
- `ole32!CoGetObject` at `0x1800066c9`

## pseudocode

```c
HRESULT __fastcall CoCreateInstanceAsAdmin(HWND a1, const struct _GUID *a2, const struct _GUID *a3, void **a4)
{
  HRESULT result; // eax
  BIND_OPTS pBindOptions[3]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR sz[56]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[304]; // [rsp+C0h] [rbp-40h] BYREF

  *a4 = 0;
  memset(pBindOptions, 0, sizeof(pBindOptions));
  if ( !StringFromGUID2(&CLSID_NTFSSecurityExt, sz, 50) )
    return -2147024882;
  result = StringCchPrintfW(
             pszName,
             0x12Cu,
             L"Elevation:Administrator!new:%s",
             sz,
             *(_QWORD *)&pBindOptions[0].cbStruct,
             *(_QWORD *)&pBindOptions[0].grfMode,
             *(_OWORD *)&pBindOptions[1],
             *(_OWORD *)&pBindOptions[2]);
  if ( result >= 0 )
  {
    pBindOptions[0].cbStruct = 48;
    *(_QWORD *)&pBindOptions[2].grfMode = a1;
    pBindOptions[1].grfFlags = 4;
    *(_OWORD *)&pBindOptions[0].grfFlags = 0;
    *(_OWORD *)&pBindOptions[1].grfMode = 0;
    return CoGetObject(pszName, pBindOptions, &IID_IElevatedNtfsSecurity, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180006604  mov     [rsp-8+arg_8], rbx
0x180006609  mov     [rsp-8+arg_10], rdi
0x18000660e  push    rbp
0x18000660f  lea     rbp, [rsp-230h]
0x180006617  sub     rsp, 330h
0x18000661e  mov     rax, cs:__security_cookie
0x180006625  xor     rax, rsp
0x180006628  mov     [rbp+230h+var_10], rax
0x18000662f  xorps   xmm0, xmm0
0x180006632  mov     qword ptr [r9], 0
0x180006639  mov     rdi, rcx
0x18000663c  lea     rdx, [rsp+330h+sz]; lpsz
0x180006641  lea     rcx, CLSID_NTFSSecurityExt; rguid
0x180006648  mov     r8d, 32h ; '2'; cchMax
0x18000664e  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x180006653  mov     rbx, r9
0x180006656  movups  [rsp+330h+var_300], xmm0
0x18000665b  movups  [rsp+330h+var_2F0], xmm0
0x180006660  call    cs:__imp_StringFromGUID2
0x180006666  test    eax, eax
0x180006668  jnz     short loc_180006671
0x18000666a  mov     eax, 8007000Eh
0x18000666f  jmp     short loc_1800066CF
0x180006671  lea     r9, [rsp+330h+sz]
0x180006676  mov     edx, 12Ch; unsigned __int64
0x18000667b  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x180006682  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x180006686  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000668b  test    eax, eax
0x18000668d  js      short loc_1800066CF
0x18000668f  xorps   xmm0, xmm0
0x180006692  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x18000669a  xorps   xmm1, xmm1
0x18000669d  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x1800066a2  mov     r9, rbx; ppv
0x1800066a5  mov     dword ptr [rsp+330h+var_300+4], 4
0x1800066ad  lea     r8, IID_IElevatedNtfsSecurity; riid
0x1800066b4  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x1800066b9  lea     rcx, [rbp+230h+pszName]; pszName
0x1800066bd  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x1800066c3  movdqu  [rsp+330h+var_300+8], xmm1
0x1800066c9  call    cs:__imp_CoGetObject
0x1800066cf  mov     rcx, [rbp+230h+var_10]
0x1800066d6  xor     rcx, rsp; StackCookie
0x1800066d9  call    __security_check_cookie
0x1800066de  lea     r11, [rsp+330h+var_s0]
0x1800066e6  mov     rbx, [r11+18h]
0x1800066ea  mov     rdi, [r11+20h]
0x1800066ee  mov     rsp, r11
0x1800066f1  pop     rbp
0x1800066f2  retn
```
