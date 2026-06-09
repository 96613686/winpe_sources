# CComUtils::CoCreateInSession(ulong,_GUID const &,ulong,_GUID const &,void * *)

- ea: `0x1800a3c3c`
- end: `0x1800a403c`
- name: `?CoCreateInSession@CComUtils@@SAJKAEBU_GUID@@K0PEAPEAX@Z`
- size: `1024`
- prototype: `static int(unsigned int, const struct _GUID *, unsigned int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005f2a4`
- `0x1800c9e98`

## callees

- `0x180005314`
- `0x180005bd0`
- `0x180016558`
- `0x180033f60`
- `0x1800a3c3c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a3d17`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a3d17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a400c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a400c`
- `ole32!MkParseDisplayName` at `0x1800a3e9a`
- `ole32!MkParseDisplayName` at `0x1800a3e9a`
- `ole32!CreateBindCtx` at `0x1800a3ca6`
- `ole32!CreateBindCtx` at `0x1800a3ca6`

## string_xrefs

- `0x1800a3d8f`: `Session:%d!clsid:%s`
- `0x1800a3cc7`: `CoCreateInSession`
- `0x1800a3d38`: `CoCreateInSession`
- `0x1800a3dc1`: `CoCreateInSession`
- `0x1800a3ebb`: `CoCreateInSession`
- `0x1800a3f16`: `CoCreateInSession`
- `0x1800a3f5b`: `CoCreateInSession`
- `0x1800a3d4b`: `StringFromCLSID`
- `0x1800a3cda`: `CreateBindCtx`
- `0x1800a3e2e`: `Creating COM object in user session`
- `0x1800a3f6e`: `pClassFactory->CreateInstance`

## pseudocode

```c
__int64 __fastcall CComUtils::CoCreateInSession(
        unsigned int a1,
        const struct _GUID *a2,
        unsigned int a3,
        const struct _GUID *a4,
        void **a5)
{
  __int64 v6; // rsi
  const char *v7; // r15
  HRESULT v9; // ebx
  char *v10; // rdx
  OLECHAR **v11; // rax
  const char **v12; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const char *v16; // rax
  const char **v18; // [rsp+28h] [rbp-D8h]
  const char **v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  const char *v21; // [rsp+58h] [rbp-A8h] BYREF
  const char *v22; // [rsp+60h] [rbp-A0h] BYREF
  const char *v23; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR *v24; // [rsp+70h] [rbp-90h] BYREF
  const char *v25; // [rsp+78h] [rbp-88h] BYREF
  LPBC ppbc; // [rsp+80h] [rbp-80h] BYREF
  ULONG pchEaten; // [rsp+88h] [rbp-78h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h] BYREF
  LPMONIKER ppmk; // [rsp+98h] [rbp-68h] BYREF
  LPOLESTR lpsz; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR szUserName[256]; // [rsp+B0h] [rbp-50h] BYREF

  v6 = a1;
  v7 = (const char *)a3;
  ppbc = 0;
  ppmk = 0;
  lpsz = 0;
  pchEaten = 0;
  v28 = 0;
  v9 = CreateBindCtx(0, &ppbc);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v22 = "CoCreateInSession";
    v10 = (char *)&dword_180119E1C;
    v23 = "CreateBindCtx";
    v21 = "Warning HResult failed";
    v19 = &v22;
    v11 = (OLECHAR **)&v23;
    goto LABEL_22;
  }
  v9 = StringFromCLSID(a2, &lpsz);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v21 = "CoCreateInSession";
    v10 = byte_180119DD1;
    v23 = "StringFromCLSID";
    v22 = "Warning HResult failed";
    v19 = &v21;
    v18 = &v23;
    v12 = &v22;
    goto LABEL_23;
  }
  v9 = StringCchPrintfW(szUserName, 0x100u, L"Session:%d!clsid:%s", (unsigned int)v6, lpsz);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v21 = "CoCreateInSession";
    v10 = (char *)&word_180119D86;
    v23 = "StringCchPrintf";
    v22 = "Warning HResult failed";
    v19 = &v21;
    v18 = &v23;
    v12 = &v22;
    goto LABEL_23;
  }
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    v21 = v7;
    v24 = szUserName;
    v23 = (const char *)a4;
    v25 = "Creating COM object in user session";
    v22 = (const char *)a2;
    v20 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
      v13,
      (unsigned int)word_180119EB2,
      v14,
      v15,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v20,
      (__int64)&v22,
      (__int64)&v23,
      (__int64)&v21);
  }
  v9 = MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v25 = "CoCreateInSession";
    v10 = byte_180119F1B;
    v16 = "MkParseDisplayName";
    goto LABEL_21;
  }
  v9 = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, __int64 *))ppmk->lpVtbl->BindToObject)(
         ppmk,
         ppbc,
         0,
         &IID_IClassFactory,
         &v28);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v25 = "CoCreateInSession";
    v10 = &byte_180119E67;
    v16 = "pMoniker->BindToObject";
    goto LABEL_21;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v28 + 24LL))(
         v28,
         0,
         a4,
         a5);
  if ( v9 < 0 && (unsigned int)dword_18012E170 > 3 )
  {
    v25 = "CoCreateInSession";
    v10 = (char *)&word_180119F66;
    v16 = "pClassFactory->CreateInstance";
LABEL_21:
    v24 = (OLECHAR *)v16;
    v21 = "Warning HResult failed";
    v19 = &v25;
    v11 = &v24;
LABEL_22:
    v18 = (const char **)v11;
    v12 = &v21;
LABEL_23:
    LODWORD(v20) = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)&dword_18012E170,
      (_DWORD)v10,
      0,
      0,
      (__int64)v12,
      (__int64)v18,
      (__int64)&v20,
      (__int64)v19);
  }
LABEL_24:
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( ppmk )
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a3c3c  push    rbp
0x1800a3c3e  push    rbx
0x1800a3c3f  push    rsi
0x1800a3c40  push    rdi
0x1800a3c41  push    r12
0x1800a3c43  push    r14
0x1800a3c45  push    r15
0x1800a3c47  lea     rbp, [rsp-1C0h]
0x1800a3c4f  sub     rsp, 2C0h
0x1800a3c56  mov     rax, cs:__security_cookie
0x1800a3c5d  xor     rax, rsp
0x1800a3c60  mov     [rbp+1F0h+var_40], rax
0x1800a3c67  mov     r12, [rbp+1F0h+arg_20]
0x1800a3c6e  mov     rdi, rdx
0x1800a3c71  mov     esi, ecx
0x1800a3c73  lea     rdx, [rbp+1F0h+ppbc]; ppbc
0x1800a3c77  xor     ecx, ecx; reserved
0x1800a3c79  mov     r15d, r8d
0x1800a3c7c  mov     r14, r9
0x1800a3c7f  mov     [rbp+1F0h+ppbc], 0
0x1800a3c87  mov     [rbp+1F0h+ppmk], 0
0x1800a3c8f  mov     [rbp+1F0h+lpsz], 0
0x1800a3c97  mov     [rbp+1F0h+pchEaten], 0
0x1800a3c9e  mov     [rbp+1F0h+var_260], 0
0x1800a3ca6  call    cs:__imp_CreateBindCtx
0x1800a3cad  nop     dword ptr [rax+rax+00h]
0x1800a3cb2  mov     ebx, eax
0x1800a3cb4  test    eax, eax
0x1800a3cb6  jns     short loc_1800A3D10
0x1800a3cb8  mov     ecx, cs:dword_18012E170
0x1800a3cbe  cmp     ecx, 3
0x1800a3cc1  jbe     loc_1800A3FC4
0x1800a3cc7  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x1800a3cce  mov     [rsp+2F0h+var_290], rax
0x1800a3cd3  lea     rdx, dword_180119E1C
0x1800a3cda  lea     rax, aCreatebindctx_0; "CreateBindCtx"
0x1800a3ce1  mov     [rsp+2F0h+var_288], rax
0x1800a3ce6  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800a3ced  mov     [rsp+2F0h+var_298], rax
0x1800a3cf2  lea     rax, [rsp+2F0h+var_290]
0x1800a3cf7  mov     [rsp+2F0h+var_2B8], rax
0x1800a3cfc  lea     rax, [rsp+2F0h+var_2A0]
0x1800a3d01  mov     [rsp+2F0h+var_2C0], rax
0x1800a3d06  lea     rax, [rsp+2F0h+var_288]
0x1800a3d0b  jmp     loc_1800A3F9F
0x1800a3d10  lea     rdx, [rbp+1F0h+lpsz]; lplpsz
0x1800a3d14  mov     rcx, rdi; rclsid
0x1800a3d17  call    cs:__imp_StringFromCLSID
0x1800a3d1e  nop     dword ptr [rax+rax+00h]
0x1800a3d23  mov     ebx, eax
0x1800a3d25  test    eax, eax
0x1800a3d27  jns     short loc_1800A3D8B
0x1800a3d29  mov     eax, cs:dword_18012E170
0x1800a3d2f  cmp     eax, 3
0x1800a3d32  jbe     loc_1800A3FC4
0x1800a3d38  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x1800a3d3f  mov     [rsp+2F0h+var_298], rax
0x1800a3d44  lea     rdx, byte_180119DD1
0x1800a3d4b  lea     rax, aStringfromclsi_1; "StringFromCLSID"
0x1800a3d52  mov     [rsp+2F0h+var_288], rax
0x1800a3d57  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800a3d5e  mov     [rsp+2F0h+var_290], rax
0x1800a3d63  lea     rax, [rsp+2F0h+var_298]
0x1800a3d68  mov     [rsp+2F0h+var_2B8], rax
0x1800a3d6d  lea     rax, [rsp+2F0h+var_2A0]
0x1800a3d72  mov     [rsp+2F0h+var_2C0], rax
0x1800a3d77  lea     rax, [rsp+2F0h+var_288]
0x1800a3d7c  mov     [rsp+2F0h+var_2C8], rax
0x1800a3d81  lea     rax, [rsp+2F0h+var_290]
0x1800a3d86  jmp     loc_1800A3FA9
0x1800a3d8b  mov     rax, [rbp+1F0h+lpsz]
0x1800a3d8f  lea     r8, aSessionDClsidS; "Session:%d!clsid:%s"
0x1800a3d96  mov     r9d, esi
0x1800a3d99  mov     [rsp+2F0h+var_2D0], rax
0x1800a3d9e  mov     edx, 100h; unsigned __int64
0x1800a3da3  lea     rcx, [rbp+1F0h+szUserName]; unsigned __int16 *
0x1800a3da7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3dac  mov     ebx, eax
0x1800a3dae  test    eax, eax
0x1800a3db0  mov     eax, cs:dword_18012E170
0x1800a3db6  jns     short loc_1800A3E14
0x1800a3db8  cmp     eax, 3
0x1800a3dbb  jbe     loc_1800A3FC4
0x1800a3dc1  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x1800a3dc8  mov     [rsp+2F0h+var_298], rax
0x1800a3dcd  lea     rdx, word_180119D86
0x1800a3dd4  lea     rax, aStringcchprint_2; "StringCchPrintf"
0x1800a3ddb  mov     [rsp+2F0h+var_288], rax
0x1800a3de0  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800a3de7  mov     [rsp+2F0h+var_290], rax
0x1800a3dec  lea     rax, [rsp+2F0h+var_298]
0x1800a3df1  mov     [rsp+2F0h+var_2B8], rax
0x1800a3df6  lea     rax, [rsp+2F0h+var_2A0]
0x1800a3dfb  mov     [rsp+2F0h+var_2C0], rax
0x1800a3e00  lea     rax, [rsp+2F0h+var_288]
0x1800a3e05  mov     [rsp+2F0h+var_2C8], rax
0x1800a3e0a  lea     rax, [rsp+2F0h+var_290]
0x1800a3e0f  jmp     loc_1800A3FA9
0x1800a3e14  cmp     eax, 5
0x1800a3e17  jbe     short loc_1800A3E8A
0x1800a3e19  lea     rax, [rbp+1F0h+szUserName]
0x1800a3e1d  mov     [rsp+2F0h+var_298], r15
0x1800a3e22  mov     [rsp+2F0h+var_280], rax
0x1800a3e27  lea     rdx, word_180119EB2
0x1800a3e2e  lea     rax, aCreatingComObj; "Creating COM object in user session"
0x1800a3e35  mov     [rsp+2F0h+var_288], r14
0x1800a3e3a  mov     [rsp+2F0h+var_278], rax
0x1800a3e3f  lea     rax, [rsp+2F0h+var_298]
0x1800a3e44  mov     [rsp+2F0h+var_2A8], rax
0x1800a3e49  lea     rax, [rsp+2F0h+var_288]
0x1800a3e4e  mov     [rsp+2F0h+var_2B0], rax
0x1800a3e53  lea     rax, [rsp+2F0h+var_290]
0x1800a3e58  mov     [rsp+2F0h+var_2B8], rax
0x1800a3e5d  lea     rax, [rsp+2F0h+var_2A0]
0x1800a3e62  mov     [rsp+2F0h+var_2C0], rax
0x1800a3e67  lea     rax, [rsp+2F0h+var_280]
0x1800a3e6c  mov     [rsp+2F0h+var_2C8], rax
0x1800a3e71  lea     rax, [rsp+2F0h+var_278]
0x1800a3e76  mov     [rsp+2F0h+var_2D0], rax
0x1800a3e7b  mov     [rsp+2F0h+var_290], rdi
0x1800a3e80  mov     [rsp+2F0h+var_2A0], rsi
0x1800a3e85  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@65@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x1800a3e8a  mov     rcx, [rbp+1F0h+ppbc]; pbc
0x1800a3e8e  lea     r9, [rbp+1F0h+ppmk]; ppmk
0x1800a3e92  lea     r8, [rbp+1F0h+pchEaten]; pchEaten
0x1800a3e96  lea     rdx, [rbp+1F0h+szUserName]; szUserName
0x1800a3e9a  call    cs:__imp_MkParseDisplayName
0x1800a3ea1  nop     dword ptr [rax+rax+00h]
0x1800a3ea6  mov     ebx, eax
0x1800a3ea8  test    eax, eax
0x1800a3eaa  jns     short loc_1800A3EDA
0x1800a3eac  mov     eax, cs:dword_18012E170
0x1800a3eb2  cmp     eax, 3
0x1800a3eb5  jbe     loc_1800A3FC4
0x1800a3ebb  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x1800a3ec2  mov     [rsp+2F0h+var_278], rax
0x1800a3ec7  lea     rdx, byte_180119F1B
0x1800a3ece  lea     rax, aMkparsedisplay_0; "MkParseDisplayName"
0x1800a3ed5  jmp     loc_1800A3F75
0x1800a3eda  mov     rcx, [rbp+1F0h+ppmk]
0x1800a3ede  lea     rdx, [rbp+1F0h+var_260]
0x1800a3ee2  mov     [rsp+2F0h+var_2D0], rdx
0x1800a3ee7  lea     r9, IID_IClassFactory
0x1800a3eee  mov     rdx, [rbp+1F0h+ppbc]
0x1800a3ef2  xor     r8d, r8d
0x1800a3ef5  mov     rax, [rcx]
0x1800a3ef8  mov     rax, [rax+40h]
0x1800a3efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f01  mov     ebx, eax
0x1800a3f03  test    eax, eax
0x1800a3f05  jns     short loc_1800A3F32
0x1800a3f07  mov     eax, cs:dword_18012E170
0x1800a3f0d  cmp     eax, 3
0x1800a3f10  jbe     loc_1800A3FC4
0x1800a3f16  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x1800a3f1d  mov     [rsp+2F0h+var_278], rax
0x1800a3f22  lea     rdx, byte_180119E67
0x1800a3f29  lea     rax, aPmonikerBindto; "pMoniker->BindToObject"
0x1800a3f30  jmp     short loc_1800A3F75
0x1800a3f32  mov     rcx, [rbp+1F0h+var_260]
0x1800a3f36  mov     r9, r12
0x1800a3f39  mov     r8, r14
0x1800a3f3c  xor     edx, edx
0x1800a3f3e  mov     rax, [rcx]
0x1800a3f41  mov     rax, [rax+18h]
0x1800a3f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f4a  mov     ebx, eax
0x1800a3f4c  test    eax, eax
0x1800a3f4e  jns     short loc_1800A3FC4
0x1800a3f50  mov     eax, cs:dword_18012E170
0x1800a3f56  cmp     eax, 3
0x1800a3f59  jbe     short loc_1800A3FC4
0x1800a3f5b  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x1800a3f62  mov     [rsp+2F0h+var_278], rax
0x1800a3f67  lea     rdx, word_180119F66
0x1800a3f6e  lea     rax, aPclassfactoryC; "pClassFactory->CreateInstance"
0x1800a3f75  mov     [rsp+2F0h+var_280], rax
0x1800a3f7a  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800a3f81  mov     [rsp+2F0h+var_298], rax
0x1800a3f86  lea     rax, [rsp+2F0h+var_278]
0x1800a3f8b  mov     [rsp+2F0h+var_2B8], rax
0x1800a3f90  lea     rax, [rsp+2F0h+var_2A0]
0x1800a3f95  mov     [rsp+2F0h+var_2C0], rax
0x1800a3f9a  lea     rax, [rsp+2F0h+var_280]
0x1800a3f9f  mov     [rsp+2F0h+var_2C8], rax
0x1800a3fa4  lea     rax, [rsp+2F0h+var_298]
0x1800a3fa9  xor     r9d, r9d
0x1800a3fac  mov     [rsp+2F0h+var_2D0], rax
0x1800a3fb1  xor     r8d, r8d
0x1800a3fb4  mov     dword ptr [rsp+2F0h+var_2A0], ebx
0x1800a3fb8  lea     rcx, dword_18012E170
0x1800a3fbf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800a3fc4  mov     rcx, [rbp+1F0h+var_260]
0x1800a3fc8  test    rcx, rcx
0x1800a3fcb  jz      short loc_1800A3FD9
0x1800a3fcd  mov     rax, [rcx]
0x1800a3fd0  mov     rax, [rax+10h]
0x1800a3fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3fd9  mov     rcx, [rbp+1F0h+ppmk]
0x1800a3fdd  test    rcx, rcx
0x1800a3fe0  jz      short loc_1800A3FEE
0x1800a3fe2  mov     rax, [rcx]
0x1800a3fe5  mov     rax, [rax+10h]
0x1800a3fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3fee  mov     rcx, [rbp+1F0h+ppbc]
0x1800a3ff2  test    rcx, rcx
0x1800a3ff5  jz      short loc_1800A4003
0x1800a3ff7  mov     rax, [rcx]
0x1800a3ffa  mov     rax, [rax+10h]
0x1800a3ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4003  mov     rcx, [rbp+1F0h+lpsz]; pv
0x1800a4007  test    rcx, rcx
0x1800a400a  jz      short loc_1800A4018
0x1800a400c  call    cs:__imp_CoTaskMemFree
0x1800a4013  nop     dword ptr [rax+rax+00h]
0x1800a4018  mov     eax, ebx
0x1800a401a  mov     rcx, [rbp+1F0h+var_40]
0x1800a4021  xor     rcx, rsp; StackCookie
0x1800a4024  call    __security_check_cookie
0x1800a4029  add     rsp, 2C0h
0x1800a4030  pop     r15
0x1800a4032  pop     r14
0x1800a4034  pop     r12
0x1800a4036  pop     rdi
0x1800a4037  pop     rsi
0x1800a4038  pop     rbx
0x1800a4039  pop     rbp
0x1800a403a  retn
```
