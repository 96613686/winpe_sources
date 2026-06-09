# CComUtils::CoCreateInSession(ulong,_GUID const &,ulong,_GUID const &,void * *)

- ea: `0x18009e80c`
- end: `0x18009ebf3`
- name: `?CoCreateInSession@CComUtils@@SAJKAEBU_GUID@@K0PEAPEAX@Z`
- size: `999`
- prototype: `static int(unsigned int, const struct _GUID *, unsigned int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005c478`
- `0x1800c3e0c`

## callees

- `0x1800052d0`
- `0x180005b78`
- `0x180015ab0`
- `0x1800321f0`
- `0x18009e80c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009e8e1`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009e8e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ebca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ebca`
- `ole32!MkParseDisplayName` at `0x18009ea5e`
- `ole32!MkParseDisplayName` at `0x18009ea5e`
- `ole32!CreateBindCtx` at `0x18009e876`
- `ole32!CreateBindCtx` at `0x18009e876`

## string_xrefs

- `0x18009e953`: `Session:%d!clsid:%s`
- `0x18009e8a4`: `CreateBindCtx`
- `0x18009e891`: `CoCreateInSession`
- `0x18009e8fc`: `CoCreateInSession`
- `0x18009e985`: `CoCreateInSession`
- `0x18009ea79`: `CoCreateInSession`
- `0x18009ead4`: `CoCreateInSession`
- `0x18009eb19`: `CoCreateInSession`
- `0x18009e90f`: `StringFromCLSID`
- `0x18009e9f2`: `Creating COM object in user session`
- `0x18009eb2c`: `pClassFactory->CreateInstance`

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
  const char **v11; // rax
  const char **v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  const char *v16; // rax
  const unsigned __int16 **v18; // [rsp+28h] [rbp-D8h]
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v22 = "CoCreateInSession";
    v10 = (char *)&dword_180113D9C;
    v23 = "CreateBindCtx";
    v21 = "Warning HResult failed";
    v19 = &v22;
    v11 = &v23;
    goto LABEL_22;
  }
  v9 = StringFromCLSID(a2, &lpsz);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v21 = "CoCreateInSession";
    v10 = byte_180113D51;
    v23 = "StringFromCLSID";
    v22 = "Warning HResult failed";
    v19 = &v21;
    v18 = (const unsigned __int16 **)&v23;
    v12 = &v22;
    goto LABEL_23;
  }
  v9 = StringCchPrintfW(szUserName, 0x100u, L"Session:%d!clsid:%s", (unsigned int)v6, lpsz);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v21 = "CoCreateInSession";
    v10 = (char *)&word_180113D06;
    v23 = "StringCchPrintf";
    v22 = "Warning HResult failed";
    v19 = &v21;
    v18 = (const unsigned __int16 **)&v23;
    v12 = &v22;
    goto LABEL_23;
  }
  if ( (unsigned int)dword_180128170 > 5 )
  {
    v21 = v7;
    v24 = szUserName;
    v23 = (const char *)a4;
    v25 = "Creating COM object in user session";
    v22 = (const char *)a2;
    v20 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
      v13,
      (__int64)word_180113E32,
      v14,
      v15,
      (const unsigned __int16 **)&v25,
      (const unsigned __int16 **)&v24,
      (__int64)&v20,
      (__int64 *)&v22,
      (__int64 *)&v23,
      (__int64)&v21);
  }
  v9 = MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v25 = "CoCreateInSession";
    v10 = byte_180113E9B;
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v25 = "CoCreateInSession";
    v10 = &byte_180113DE7;
    v16 = "pMoniker->BindToObject";
    goto LABEL_21;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v28 + 24LL))(
         v28,
         0,
         a4,
         a5);
  if ( v9 < 0 && (unsigned int)dword_180128170 > 3 )
  {
    v25 = "CoCreateInSession";
    v10 = (char *)&word_180113EE6;
    v16 = "pClassFactory->CreateInstance";
LABEL_21:
    v24 = (OLECHAR *)v16;
    v21 = "Warning HResult failed";
    v19 = &v25;
    v11 = (const char **)&v24;
LABEL_22:
    v18 = (const unsigned __int16 **)v11;
    v12 = &v21;
LABEL_23:
    LODWORD(v20) = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)&dword_180128170,
      (__int64)v10,
      0,
      0,
      (const unsigned __int16 **)v12,
      v18,
      (__int64)&v20,
      (const unsigned __int16 **)v19);
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
0x18009e80c  push    rbp
0x18009e80e  push    rbx
0x18009e80f  push    rsi
0x18009e810  push    rdi
0x18009e811  push    r12
0x18009e813  push    r14
0x18009e815  push    r15
0x18009e817  lea     rbp, [rsp-1C0h]
0x18009e81f  sub     rsp, 2C0h
0x18009e826  mov     rax, cs:__security_cookie
0x18009e82d  xor     rax, rsp
0x18009e830  mov     [rbp+1F0h+var_40], rax
0x18009e837  mov     r12, [rbp+1F0h+arg_20]
0x18009e83e  mov     rdi, rdx
0x18009e841  mov     esi, ecx
0x18009e843  lea     rdx, [rbp+1F0h+ppbc]; ppbc
0x18009e847  xor     ecx, ecx; reserved
0x18009e849  mov     r15d, r8d
0x18009e84c  mov     r14, r9
0x18009e84f  mov     [rbp+1F0h+ppbc], 0
0x18009e857  mov     [rbp+1F0h+ppmk], 0
0x18009e85f  mov     [rbp+1F0h+lpsz], 0
0x18009e867  mov     [rbp+1F0h+pchEaten], 0
0x18009e86e  mov     [rbp+1F0h+var_260], 0
0x18009e876  call    cs:__imp_CreateBindCtx
0x18009e87c  mov     ebx, eax
0x18009e87e  test    eax, eax
0x18009e880  jns     short loc_18009E8DA
0x18009e882  mov     ecx, cs:dword_180128170
0x18009e888  cmp     ecx, 3
0x18009e88b  jbe     loc_18009EB82
0x18009e891  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x18009e898  mov     [rsp+2F0h+var_290], rax
0x18009e89d  lea     rdx, dword_180113D9C
0x18009e8a4  lea     rax, aCreatebindctx_0; "CreateBindCtx"
0x18009e8ab  mov     [rsp+2F0h+var_288], rax
0x18009e8b0  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009e8b7  mov     [rsp+2F0h+var_298], rax
0x18009e8bc  lea     rax, [rsp+2F0h+var_290]
0x18009e8c1  mov     [rsp+2F0h+var_2B8], rax
0x18009e8c6  lea     rax, [rsp+2F0h+var_2A0]
0x18009e8cb  mov     [rsp+2F0h+var_2C0], rax
0x18009e8d0  lea     rax, [rsp+2F0h+var_288]
0x18009e8d5  jmp     loc_18009EB5D
0x18009e8da  lea     rdx, [rbp+1F0h+lpsz]; lplpsz
0x18009e8de  mov     rcx, rdi; rclsid
0x18009e8e1  call    cs:__imp_StringFromCLSID
0x18009e8e7  mov     ebx, eax
0x18009e8e9  test    eax, eax
0x18009e8eb  jns     short loc_18009E94F
0x18009e8ed  mov     eax, cs:dword_180128170
0x18009e8f3  cmp     eax, 3
0x18009e8f6  jbe     loc_18009EB82
0x18009e8fc  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x18009e903  mov     [rsp+2F0h+var_298], rax
0x18009e908  lea     rdx, byte_180113D51
0x18009e90f  lea     rax, aStringfromclsi_1; "StringFromCLSID"
0x18009e916  mov     [rsp+2F0h+var_288], rax
0x18009e91b  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009e922  mov     [rsp+2F0h+var_290], rax
0x18009e927  lea     rax, [rsp+2F0h+var_298]
0x18009e92c  mov     [rsp+2F0h+var_2B8], rax
0x18009e931  lea     rax, [rsp+2F0h+var_2A0]
0x18009e936  mov     [rsp+2F0h+var_2C0], rax
0x18009e93b  lea     rax, [rsp+2F0h+var_288]
0x18009e940  mov     [rsp+2F0h+var_2C8], rax
0x18009e945  lea     rax, [rsp+2F0h+var_290]
0x18009e94a  jmp     loc_18009EB67
0x18009e94f  mov     rax, [rbp+1F0h+lpsz]
0x18009e953  lea     r8, aSessionDClsidS; "Session:%d!clsid:%s"
0x18009e95a  mov     r9d, esi
0x18009e95d  mov     [rsp+2F0h+var_2D0], rax
0x18009e962  mov     edx, 100h; unsigned __int64
0x18009e967  lea     rcx, [rbp+1F0h+szUserName]; unsigned __int16 *
0x18009e96b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009e970  mov     ebx, eax
0x18009e972  test    eax, eax
0x18009e974  mov     eax, cs:dword_180128170
0x18009e97a  jns     short loc_18009E9D8
0x18009e97c  cmp     eax, 3
0x18009e97f  jbe     loc_18009EB82
0x18009e985  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x18009e98c  mov     [rsp+2F0h+var_298], rax
0x18009e991  lea     rdx, word_180113D06
0x18009e998  lea     rax, aStringcchprint_2; "StringCchPrintf"
0x18009e99f  mov     [rsp+2F0h+var_288], rax
0x18009e9a4  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009e9ab  mov     [rsp+2F0h+var_290], rax
0x18009e9b0  lea     rax, [rsp+2F0h+var_298]
0x18009e9b5  mov     [rsp+2F0h+var_2B8], rax
0x18009e9ba  lea     rax, [rsp+2F0h+var_2A0]
0x18009e9bf  mov     [rsp+2F0h+var_2C0], rax
0x18009e9c4  lea     rax, [rsp+2F0h+var_288]
0x18009e9c9  mov     [rsp+2F0h+var_2C8], rax
0x18009e9ce  lea     rax, [rsp+2F0h+var_290]
0x18009e9d3  jmp     loc_18009EB67
0x18009e9d8  cmp     eax, 5
0x18009e9db  jbe     short loc_18009EA4E
0x18009e9dd  lea     rax, [rbp+1F0h+szUserName]
0x18009e9e1  mov     [rsp+2F0h+var_298], r15
0x18009e9e6  mov     [rsp+2F0h+var_280], rax
0x18009e9eb  lea     rdx, word_180113E32
0x18009e9f2  lea     rax, aCreatingComObj; "Creating COM object in user session"
0x18009e9f9  mov     [rsp+2F0h+var_288], r14
0x18009e9fe  mov     [rsp+2F0h+var_278], rax
0x18009ea03  lea     rax, [rsp+2F0h+var_298]
0x18009ea08  mov     [rsp+2F0h+var_2A8], rax
0x18009ea0d  lea     rax, [rsp+2F0h+var_288]
0x18009ea12  mov     [rsp+2F0h+var_2B0], rax
0x18009ea17  lea     rax, [rsp+2F0h+var_290]
0x18009ea1c  mov     [rsp+2F0h+var_2B8], rax
0x18009ea21  lea     rax, [rsp+2F0h+var_2A0]
0x18009ea26  mov     [rsp+2F0h+var_2C0], rax
0x18009ea2b  lea     rax, [rsp+2F0h+var_280]
0x18009ea30  mov     [rsp+2F0h+var_2C8], rax
0x18009ea35  lea     rax, [rsp+2F0h+var_278]
0x18009ea3a  mov     [rsp+2F0h+var_2D0], rax
0x18009ea3f  mov     [rsp+2F0h+var_290], rdi
0x18009ea44  mov     [rsp+2F0h+var_2A0], rsi
0x18009ea49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@65@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x18009ea4e  mov     rcx, [rbp+1F0h+ppbc]; pbc
0x18009ea52  lea     r9, [rbp+1F0h+ppmk]; ppmk
0x18009ea56  lea     r8, [rbp+1F0h+pchEaten]; pchEaten
0x18009ea5a  lea     rdx, [rbp+1F0h+szUserName]; szUserName
0x18009ea5e  call    cs:__imp_MkParseDisplayName
0x18009ea64  mov     ebx, eax
0x18009ea66  test    eax, eax
0x18009ea68  jns     short loc_18009EA98
0x18009ea6a  mov     eax, cs:dword_180128170
0x18009ea70  cmp     eax, 3
0x18009ea73  jbe     loc_18009EB82
0x18009ea79  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x18009ea80  mov     [rsp+2F0h+var_278], rax
0x18009ea85  lea     rdx, byte_180113E9B
0x18009ea8c  lea     rax, aMkparsedisplay_0; "MkParseDisplayName"
0x18009ea93  jmp     loc_18009EB33
0x18009ea98  mov     rcx, [rbp+1F0h+ppmk]
0x18009ea9c  lea     rdx, [rbp+1F0h+var_260]
0x18009eaa0  mov     [rsp+2F0h+var_2D0], rdx
0x18009eaa5  lea     r9, IID_IClassFactory
0x18009eaac  mov     rdx, [rbp+1F0h+ppbc]
0x18009eab0  xor     r8d, r8d
0x18009eab3  mov     rax, [rcx]
0x18009eab6  mov     rax, [rax+40h]
0x18009eaba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eabf  mov     ebx, eax
0x18009eac1  test    eax, eax
0x18009eac3  jns     short loc_18009EAF0
0x18009eac5  mov     eax, cs:dword_180128170
0x18009eacb  cmp     eax, 3
0x18009eace  jbe     loc_18009EB82
0x18009ead4  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x18009eadb  mov     [rsp+2F0h+var_278], rax
0x18009eae0  lea     rdx, byte_180113DE7
0x18009eae7  lea     rax, aPmonikerBindto; "pMoniker->BindToObject"
0x18009eaee  jmp     short loc_18009EB33
0x18009eaf0  mov     rcx, [rbp+1F0h+var_260]
0x18009eaf4  mov     r9, r12
0x18009eaf7  mov     r8, r14
0x18009eafa  xor     edx, edx
0x18009eafc  mov     rax, [rcx]
0x18009eaff  mov     rax, [rax+18h]
0x18009eb03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb08  mov     ebx, eax
0x18009eb0a  test    eax, eax
0x18009eb0c  jns     short loc_18009EB82
0x18009eb0e  mov     eax, cs:dword_180128170
0x18009eb14  cmp     eax, 3
0x18009eb17  jbe     short loc_18009EB82
0x18009eb19  lea     rax, aCocreateinsess_0; "CoCreateInSession"
0x18009eb20  mov     [rsp+2F0h+var_278], rax
0x18009eb25  lea     rdx, word_180113EE6
0x18009eb2c  lea     rax, aPclassfactoryC; "pClassFactory->CreateInstance"
0x18009eb33  mov     [rsp+2F0h+var_280], rax
0x18009eb38  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009eb3f  mov     [rsp+2F0h+var_298], rax
0x18009eb44  lea     rax, [rsp+2F0h+var_278]
0x18009eb49  mov     [rsp+2F0h+var_2B8], rax
0x18009eb4e  lea     rax, [rsp+2F0h+var_2A0]
0x18009eb53  mov     [rsp+2F0h+var_2C0], rax
0x18009eb58  lea     rax, [rsp+2F0h+var_280]
0x18009eb5d  mov     [rsp+2F0h+var_2C8], rax
0x18009eb62  lea     rax, [rsp+2F0h+var_298]
0x18009eb67  xor     r9d, r9d
0x18009eb6a  mov     [rsp+2F0h+var_2D0], rax
0x18009eb6f  xor     r8d, r8d
0x18009eb72  mov     dword ptr [rsp+2F0h+var_2A0], ebx
0x18009eb76  lea     rcx, dword_180128170
0x18009eb7d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009eb82  mov     rcx, [rbp+1F0h+var_260]
0x18009eb86  test    rcx, rcx
0x18009eb89  jz      short loc_18009EB97
0x18009eb8b  mov     rax, [rcx]
0x18009eb8e  mov     rax, [rax+10h]
0x18009eb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb97  mov     rcx, [rbp+1F0h+ppmk]
0x18009eb9b  test    rcx, rcx
0x18009eb9e  jz      short loc_18009EBAC
0x18009eba0  mov     rax, [rcx]
0x18009eba3  mov     rax, [rax+10h]
0x18009eba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ebac  mov     rcx, [rbp+1F0h+ppbc]
0x18009ebb0  test    rcx, rcx
0x18009ebb3  jz      short loc_18009EBC1
0x18009ebb5  mov     rax, [rcx]
0x18009ebb8  mov     rax, [rax+10h]
0x18009ebbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ebc1  mov     rcx, [rbp+1F0h+lpsz]; pv
0x18009ebc5  test    rcx, rcx
0x18009ebc8  jz      short loc_18009EBD0
0x18009ebca  call    cs:__imp_CoTaskMemFree
0x18009ebd0  mov     eax, ebx
0x18009ebd2  mov     rcx, [rbp+1F0h+var_40]
0x18009ebd9  xor     rcx, rsp; StackCookie
0x18009ebdc  call    __security_check_cookie
0x18009ebe1  add     rsp, 2C0h
0x18009ebe8  pop     r15
0x18009ebea  pop     r14
0x18009ebec  pop     r12
0x18009ebee  pop     rdi
0x18009ebef  pop     rsi
0x18009ebf0  pop     rbx
0x18009ebf1  pop     rbp
0x18009ebf2  retn
```
