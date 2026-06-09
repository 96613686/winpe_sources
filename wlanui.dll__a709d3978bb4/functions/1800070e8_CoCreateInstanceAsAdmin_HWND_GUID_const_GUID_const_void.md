# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800070e8`
- end: `0x1800071cf`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `231`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d464`
- `0x18000f370`

## callees

- `0x1800070e8`
- `0x18000d670`
- `0x18001bf40`

## import_xrefs

- `ole32!CoGetObject` at `0x1800071a9`
- `ole32!CoGetObject` at `0x1800071a9`
- `ole32!StringFromGUID2` at `0x18000713c`
- `ole32!StringFromGUID2` at `0x18000713c`

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
  if ( !StringFromGUID2(&CLSID_CElevateWlanUi, sz, 50) )
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
    pBindOptions[1].grfFlags = 4;
    *(_OWORD *)&pBindOptions[0].grfFlags = 0;
    memset(&pBindOptions[1].grfMode, 0, 24);
    return CoGetObject(pszName, pBindOptions, &IID_IElevateWlanUi, a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800070e8  mov     [rsp-8+arg_0], rbx
0x1800070ed  push    rbp
0x1800070ee  lea     rbp, [rsp-230h]
0x1800070f6  sub     rsp, 330h
0x1800070fd  mov     rax, cs:__security_cookie
0x180007104  xor     rax, rsp
0x180007107  mov     [rbp+230h+var_10], rax
0x18000710e  xorps   xmm0, xmm0
0x180007111  mov     qword ptr [r9], 0
0x180007118  mov     r8d, 32h ; '2'; cchMax
0x18000711e  lea     rdx, [rsp+330h+sz]; lpsz
0x180007123  lea     rcx, CLSID_CElevateWlanUi; rguid
0x18000712a  mov     rbx, r9
0x18000712d  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x180007132  movups  [rsp+330h+var_300], xmm0
0x180007137  movups  [rsp+330h+var_2F0], xmm0
0x18000713c  call    cs:__imp_StringFromGUID2
0x180007142  test    eax, eax
0x180007144  jnz     short loc_18000714D
0x180007146  mov     eax, 8007000Eh
0x18000714b  jmp     short loc_1800071AF
0x18000714d  lea     r9, [rsp+330h+sz]
0x180007152  mov     edx, 12Ch; unsigned __int64
0x180007157  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x18000715e  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x180007162  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007167  test    eax, eax
0x180007169  js      short loc_1800071AF
0x18000716b  xorps   xmm0, xmm0
0x18000716e  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x180007176  xorps   xmm1, xmm1
0x180007179  mov     qword ptr [rsp+330h+var_2F0+8], 0
0x180007182  mov     r9, rbx; ppv
0x180007185  mov     dword ptr [rsp+330h+var_300+4], 4
0x18000718d  lea     r8, IID_IElevateWlanUi; riid
0x180007194  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x180007199  lea     rcx, [rbp+230h+pszName]; pszName
0x18000719d  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x1800071a3  movdqu  [rsp+330h+var_300+8], xmm1
0x1800071a9  call    cs:__imp_CoGetObject
0x1800071af  mov     rcx, [rbp+230h+var_10]
0x1800071b6  xor     rcx, rsp; StackCookie
0x1800071b9  call    __security_check_cookie
0x1800071be  mov     rbx, [rsp+330h+arg_0]
0x1800071c6  add     rsp, 330h
0x1800071cd  pop     rbp
0x1800071ce  retn
```
