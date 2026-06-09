# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180003540`
- end: `0x18000364a`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `266`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003e14`

## callees

- `0x180003520`
- `0x180003540`
- `0x180004288`
- `0x18000466c`
- `0x18003c560`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003592`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003592`
- `ole32!CoGetObject` at `0x180003605`
- `ole32!CoGetObject` at `0x180003605`

## pseudocode

```c
__int64 __fastcall CoCreateInstanceAsAdmin(HWND a1, const struct _GUID *a2, const struct _GUID *a3, void **a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rcx
  HRESULT Object; // eax
  BIND_OPTS pBindOptions[3]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR sz[56]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[304]; // [rsp+C0h] [rbp-40h] BYREF

  memset(pBindOptions, 0, sizeof(pBindOptions));
  if ( !StringFromGUID2(&CLSID_SPPLUAObject, sz, 50) )
  {
    v6 = -2147467259;
    v7 = 2147500037LL;
LABEL_6:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_7;
  }
  Object = StringCchPrintfW(
             pszName,
             0x12Cu,
             L"Elevation:Administrator!new:%s",
             sz,
             *(_QWORD *)&pBindOptions[0].cbStruct,
             *(_QWORD *)&pBindOptions[0].grfMode,
             *(_OWORD *)&pBindOptions[1],
             *(_OWORD *)&pBindOptions[2]);
  v6 = Object;
  if ( Object < 0
    || (pBindOptions[0].cbStruct = 48,
        *(_QWORD *)&pBindOptions[2].grfMode = a1,
        pBindOptions[1].grfFlags = 4,
        *(_OWORD *)&pBindOptions[0].grfFlags = 0,
        *(_OWORD *)&pBindOptions[1].grfMode = 0,
        Object = CoGetObject(pszName, pBindOptions, &IID_ISPPLUA, a4),
        v6 = Object,
        Object < 0) )
  {
    v7 = (unsigned int)Object;
    goto LABEL_6;
  }
LABEL_7:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  return v6;
}

```

## disassembly

```asm
0x180003540  mov     [rsp-8+arg_8], rbx
0x180003545  push    rbp
0x180003546  push    rsi
0x180003547  push    rdi
0x180003548  lea     rbp, [rsp-230h]
0x180003550  sub     rsp, 330h
0x180003557  mov     rax, cs:__security_cookie
0x18000355e  xor     rax, rsp
0x180003561  mov     [rbp+240h+var_20], rax
0x180003568  xorps   xmm0, xmm0
0x18000356b  lea     rdx, [rsp+340h+sz]; lpsz
0x180003570  mov     rdi, rcx
0x180003573  mov     r8d, 32h ; '2'; cchMax
0x180003579  lea     rcx, CLSID_SPPLUAObject; rguid
0x180003580  mov     rsi, r9
0x180003583  movups  xmmword ptr [rsp+340h+pBindOptions.cbStruct], xmm0
0x180003588  movups  [rsp+340h+var_310], xmm0
0x18000358d  movups  [rsp+340h+var_300], xmm0
0x180003592  call    cs:__imp_StringFromGUID2
0x180003599  nop     dword ptr [rax+rax+00h]
0x18000359e  test    eax, eax
0x1800035a0  jnz     short loc_1800035AB
0x1800035a2  mov     ebx, 80004005h
0x1800035a7  mov     ecx, ebx
0x1800035a9  jmp     short loc_180003619
0x1800035ab  lea     r9, [rsp+340h+sz]
0x1800035b0  mov     edx, 12Ch; unsigned __int64
0x1800035b5  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x1800035bc  lea     rcx, [rbp+240h+pszName]; unsigned __int16 *
0x1800035c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800035c5  mov     ebx, eax
0x1800035c7  test    eax, eax
0x1800035c9  js      short loc_180003617
0x1800035cb  xorps   xmm0, xmm0
0x1800035ce  mov     [rsp+340h+pBindOptions.cbStruct], 30h ; '0'
0x1800035d6  xorps   xmm1, xmm1
0x1800035d9  mov     qword ptr [rsp+340h+var_300+8], rdi
0x1800035de  mov     r9, rsi; ppv
0x1800035e1  mov     dword ptr [rsp+340h+var_310+4], 4
0x1800035e9  lea     r8, IID_ISPPLUA; riid
0x1800035f0  lea     rdx, [rsp+340h+pBindOptions]; pBindOptions
0x1800035f5  lea     rcx, [rbp+240h+pszName]; pszName
0x1800035f9  movdqu  xmmword ptr [rsp+340h+pBindOptions.grfFlags], xmm0
0x1800035ff  movdqu  [rsp+340h+var_310+8], xmm1
0x180003605  call    cs:__imp_CoGetObject
0x18000360c  nop     dword ptr [rax+rax+00h]
0x180003611  mov     ebx, eax
0x180003613  test    eax, eax
0x180003615  jns     short loc_18000361E
0x180003617  mov     ecx, eax
0x180003619  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000361e  mov     ecx, ebx
0x180003620  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003625  mov     eax, ebx
0x180003627  mov     rcx, [rbp+240h+var_20]
0x18000362e  xor     rcx, rsp; StackCookie
0x180003631  call    __security_check_cookie
0x180003636  mov     rbx, [rsp+340h+arg_8]
0x18000363e  add     rsp, 330h
0x180003645  pop     rdi
0x180003646  pop     rsi
0x180003647  pop     rbp
0x180003648  retn
```
