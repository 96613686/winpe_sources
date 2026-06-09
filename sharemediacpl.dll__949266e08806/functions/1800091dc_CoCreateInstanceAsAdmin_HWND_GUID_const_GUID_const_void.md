# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800091dc`
- end: `0x1800092cb`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009ab4`
- `0x1800100ac`

## callees

- `0x180001d60`
- `0x180006ca8`
- `0x1800091dc`

## import_xrefs

- `ole32!CoGetObject` at `0x1800092a1`
- `ole32!CoGetObject` at `0x1800092a1`
- `ole32!StringFromGUID2` at `0x180009238`
- `ole32!StringFromGUID2` at `0x180009238`

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
  if ( !StringFromGUID2(&CLSID_ShareMediaSettingsWriter, sz, 50) )
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
    return CoGetObject(pszName, pBindOptions, &GUID_b977cb2d_ec6e_4a8f_bffe_d18682bb0d52, a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800091dc  mov     [rsp-8+arg_8], rbx
0x1800091e1  mov     [rsp-8+arg_10], rdi
0x1800091e6  push    rbp
0x1800091e7  lea     rbp, [rsp-230h]
0x1800091ef  sub     rsp, 330h
0x1800091f6  mov     rax, cs:__security_cookie
0x1800091fd  xor     rax, rsp
0x180009200  mov     [rbp+230h+var_10], rax
0x180009207  xorps   xmm0, xmm0
0x18000920a  mov     qword ptr [r9], 0
0x180009211  mov     rdi, rcx
0x180009214  lea     rdx, [rsp+330h+sz]; lpsz
0x180009219  lea     rcx, CLSID_ShareMediaSettingsWriter; rguid
0x180009220  mov     r8d, 32h ; '2'; cchMax
0x180009226  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x18000922b  mov     rbx, r9
0x18000922e  movups  [rsp+330h+var_300], xmm0
0x180009233  movups  [rsp+330h+var_2F0], xmm0
0x180009238  call    cs:__imp_StringFromGUID2
0x18000923e  test    eax, eax
0x180009240  jnz     short loc_180009249
0x180009242  mov     eax, 8007000Eh
0x180009247  jmp     short loc_1800092A7
0x180009249  lea     r9, [rsp+330h+sz]
0x18000924e  mov     edx, 12Ch; unsigned __int64
0x180009253  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x18000925a  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x18000925e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009263  test    eax, eax
0x180009265  js      short loc_1800092A7
0x180009267  xorps   xmm0, xmm0
0x18000926a  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x180009272  xorps   xmm1, xmm1
0x180009275  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x18000927a  mov     r9, rbx; ppv
0x18000927d  mov     dword ptr [rsp+330h+var_300+4], 4
0x180009285  lea     r8, _GUID_b977cb2d_ec6e_4a8f_bffe_d18682bb0d52; riid
0x18000928c  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x180009291  lea     rcx, [rbp+230h+pszName]; pszName
0x180009295  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x18000929b  movdqu  [rsp+330h+var_300+8], xmm1
0x1800092a1  call    cs:__imp_CoGetObject
0x1800092a7  mov     rcx, [rbp+230h+var_10]
0x1800092ae  xor     rcx, rsp; StackCookie
0x1800092b1  call    __security_check_cookie
0x1800092b6  lea     r11, [rsp+330h+var_s0]
0x1800092be  mov     rbx, [r11+18h]
0x1800092c2  mov     rdi, [r11+20h]
0x1800092c6  mov     rsp, r11
0x1800092c9  pop     rbp
0x1800092ca  retn
```
