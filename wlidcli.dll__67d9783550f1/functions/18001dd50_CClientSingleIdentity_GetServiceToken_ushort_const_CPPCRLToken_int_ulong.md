# CClientSingleIdentity::GetServiceToken(ushort const *,CPPCRLToken &,int,ulong)

- ea: `0x18001dd50`
- end: `0x18001e1c5`
- name: `?GetServiceToken@CClientSingleIdentity@@QEAAJPEBGAEAVCPPCRLToken@@HK@Z`
- size: `1141`
- prototype: `__int64 __fastcall(CClientSingleIdentity *__hidden this, const unsigned __int16 *, struct CPPCRLToken *, int, unsigned int)`
- caller_count: `7`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ca08`
- `0x180023fe4`
- `0x180026474`
- `0x18002935c`
- `0x18002a420`
- `0x18002a7f0`
- `0x18002cf70`

## callees

- `0x180003298`
- `0x18000a870`
- `0x18000b0bc`
- `0x18000ba8c`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x1800104dc`
- `0x180010eec`
- `0x1800114b0`
- `0x180012998`
- `0x18001dd50`
- `0x18001e1f8`
- `0x18001e2f0`
- `0x180020704`
- `0x180020848`
- `0x18004990c`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e1a2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e1a2`

## string_xrefs

- `0x18001dd9f`: `ServiceURI='%s'`
- `0x18001ddab`: `CClientSingleIdentity::GetServiceToken`
- `0x18001e0c5`: `StoreToken failed (0x%x).`
- `0x18001e15a`: `Internal Error: GetTokenBag() returned NULL.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CClientSingleIdentity::GetServiceToken(
        CClientSingleIdentity *this,
        const unsigned __int16 *a2,
        struct CPPCRLToken *a3,
        int a4,
        unsigned int a5)
{
  int v9; // ebx
  unsigned int v10; // edx
  __int64 v11; // r12
  __int64 v12; // rax
  int Token; // eax
  _QWORD *v14; // rax
  bool v15; // r15
  void **v16; // rbx
  void *v17; // rdx
  int v18; // eax
  const unsigned __int16 *v19; // r9
  unsigned int v20; // r8d
  int v21; // r12d
  int v22; // r13d
  int v23; // r15d
  __int64 *v24; // rdx
  __int64 v25; // r14
  const WCHAR *v26; // rdx
  __int64 v27; // rsi
  int v28; // edi
  int v29; // ebx
  int v30; // eax
  __int64 v31; // rbx
  __int64 v32; // rax
  struct CPPCRLToken *v33; // rdi
  _QWORD *v34; // rax
  char v35; // cl
  char v36; // bl
  unsigned int v37; // ebx
  __int64 v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41; // [rsp+74h] [rbp-8Ch]
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  void **v43; // [rsp+80h] [rbp-80h] BYREF
  char v44[8]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  int v46; // [rsp+98h] [rbp-68h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-60h]
  int v48; // [rsp+A8h] [rbp-58h]
  char v49[8]; // [rsp+B0h] [rbp-50h] BYREF
  char v50[8]; // [rsp+B8h] [rbp-48h] BYREF
  char v51[8]; // [rsp+C0h] [rbp-40h] BYREF
  char v52[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v55; // [rsp+E0h] [rbp-20h] BYREF
  const unsigned __int16 *v56; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v57; // [rsp+F8h] [rbp-8h]
  __int128 v58; // [rsp+108h] [rbp+8h]
  __int64 *v59; // [rsp+118h] [rbp+18h]
  char *v60; // [rsp+120h] [rbp+20h]
  char *v61; // [rsp+128h] [rbp+28h]
  char *v62; // [rsp+130h] [rbp+30h]
  char *v63; // [rsp+138h] [rbp+38h]
  char *v64[10]; // [rsp+140h] [rbp+40h] BYREF
  const unsigned __int16 *v66; // [rsp+1A8h] [rbp+A8h] BYREF
  struct CPPCRLToken *v67; // [rsp+1B0h] [rbp+B0h]

  v67 = a3;
  v66 = a2;
  v9 = 0;
  v41 = 0;
  v40 = 0;
  Block = 0;
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v64,
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
    0x300u,
    (char *)&v40,
    "CClientSingleIdentity::GetServiceToken",
    L"ServiceURI='%s'",
    a2);
  if ( a2 && *a2 )
  {
    v11 = *((_QWORD *)this + 9);
    v15 = 1;
    if ( v11 )
    {
      v12 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
              v44,
              a2);
      Token = CClientIdentityTokenBag::RetrieveToken(v11, v12, a3);
      v11 = 0;
      if ( Token )
      {
        v14 = (_QWORD *)CPPCRLToken::GetToken(a3, &v45);
        v9 = 1;
        v41 = 1;
        if ( *(_DWORD *)(*v14 - 16LL) )
        {
          if ( !a4 )
            v15 = 0;
        }
      }
    }
    if ( (v9 & 1) != 0 )
    {
      v41 = v9 & 0xFFFFFFFE;
      ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
    }
    if ( v15 )
    {
      if ( *((_QWORD *)this + 9) != v11 )
      {
        v57 = 0;
        v47 = v11;
        v46 = v11;
        v48 = v11;
        v56 = a2;
        v58 = a5;
        v16 = (void **)*((_QWORD *)this + 8);
        if ( !v16 )
        {
          v16 = (void **)operator new(0x28u);
          v43 = v16;
          v16[1] = 0;
          *((_DWORD *)v16 + 6) = 1;
          *v16 = &SmartWLIDHandle::`vftable'{for `SmartObj<void *>'};
          v16[2] = &SmartWLIDHandle::`vftable'{for `CRefCounted'};
          v16[4] = 0;
          CAutoRefPtr<SmartWLIDHandle>::Deinit((char *)this + 64);
          *((_QWORD *)this + 8) = v16;
        }
        v40 = WLIDCGetCachedTokens(
                v16[1],
                v10,
                (struct _WLIDRequestParams *const)&v56,
                (struct _WLIDResponseParams **)&Block);
        if ( v40 < 0 )
          goto LABEL_16;
        v17 = Block;
        if ( *((_DWORD *)Block + 8) == 2 )
        {
          v18 = CClientCertManager::PutCertWithKey(
                  g_pPPCRL + 162,
                  this,
                  v56,
                  *((_QWORD *)Block + 5),
                  *((_QWORD *)Block + 13),
                  *((_QWORD *)Block + 11),
                  v58);
          v40 = v18;
          if ( v18 < 0 )
          {
            v19 = L"PutCertWithKey failed (0x%x).";
            v20 = 810;
LABEL_21:
            LODWORD(v39) = v18;
            TracePrintW(2u, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp", v20, v19, v39);
LABEL_16:
            v40 = -2147186590;
LABEL_17:
            CBytePtr::Empty((CBytePtr *)&v46);
            goto LABEL_38;
          }
          v17 = Block;
        }
        CBytePtr::Attach((CBytePtr *)&v46, *((unsigned __int8 **)v17 + 2), *((_DWORD *)v17 + 2), 0);
        v43 = (void **)*((_QWORD *)this + 9);
        v59 = &v45;
        v53 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)&v45,
                *((_QWORD *)Block + 7));
        v21 = *((_DWORD *)Block + 1);
        v22 = *(_DWORD *)Block;
        v23 = IDCRLTokenType(*((unsigned int *)Block + 8));
        v54 = v24[13];
        v55 = v24[12];
        v60 = v44;
        v25 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)v44,
                v24[10]);
        v61 = v49;
        v26 = &String;
        if ( *((_QWORD *)Block + 6) )
          v26 = (const WCHAR *)*((_QWORD *)Block + 6);
        v27 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)v49,
                (__int64)v26);
        v62 = v50;
        v28 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)v50,
                (__int64)&String);
        v63 = v51;
        v29 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)v51,
                *((_QWORD *)Block + 5));
        v30 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                v52,
                v56);
        v18 = CClientIdentityTokenBag::StoreToken(
                (_DWORD)v43,
                v30,
                v29,
                v28,
                v27,
                v25,
                (__int64)&v55,
                (__int64)&v54,
                (__int64)&v46,
                v23,
                v22,
                v21,
                v53);
        v40 = v18;
        if ( v18 < 0 )
        {
          v19 = L"StoreToken failed (0x%x).";
          v20 = 832;
          goto LABEL_21;
        }
        v31 = *((_QWORD *)this + 9);
        v32 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                &v43,
                v66);
        v33 = v67;
        if ( (unsigned int)CClientIdentityTokenBag::RetrieveToken(v31, v32, v67) )
        {
          v34 = (_QWORD *)CPPCRLToken::GetToken(v33, &v66);
          v35 = v41 | 2;
          if ( *(_DWORD *)(*v34 - 16LL) )
          {
            v36 = 0;
            goto LABEL_32;
          }
        }
        else
        {
          v35 = v41;
        }
        v36 = 1;
LABEL_32:
        if ( (v35 & 2) != 0 )
          ATL::CStringData::Release((ATL::CStringData *)(v66 - 12));
        if ( !v36 )
          goto LABEL_17;
        goto LABEL_16;
      }
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
        0x34Eu,
        L"Internal Error: GetTokenBag() returned NULL.");
      v40 = -2147186590;
    }
  }
  else
  {
    v40 = -2147024809;
  }
LABEL_38:
  v37 = v40;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
  if ( Block )
    free(Block);
  return v37;
}

```

## disassembly

```asm
0x18001dd50  mov     rax, rsp
0x18001dd53  mov     [rax+20h], rbx
0x18001dd57  mov     [rax+18h], r8
0x18001dd5b  mov     [rax+10h], rdx
0x18001dd5f  mov     [rax+8], rcx
0x18001dd63  push    rbp
0x18001dd64  push    rsi
0x18001dd65  push    rdi
0x18001dd66  push    r12
0x18001dd68  push    r13
0x18001dd6a  push    r14
0x18001dd6c  push    r15
0x18001dd6e  lea     rbp, [rsp-60h]
0x18001dd73  sub     rsp, 160h
0x18001dd7a  mov     r13d, r9d
0x18001dd7d  mov     r15, r8
0x18001dd80  mov     rsi, rdx
0x18001dd83  mov     r14, rcx
0x18001dd86  xor     r12d, r12d
0x18001dd89  mov     ebx, r12d
0x18001dd8c  mov     [rsp+190h+var_11C], ebx
0x18001dd90  mov     [rsp+190h+var_120], r12d
0x18001dd95  mov     [rsp+190h+Block], r12
0x18001dd9a  mov     [rsp+190h+var_160], rdx
0x18001dd9f  lea     rax, aServiceuriS; "ServiceURI='%s'"
0x18001dda6  mov     [rsp+190h+var_168], rax
0x18001ddab  lea     rax, aCclientsinglei_8; "CClientSingleIdentity::GetServiceToken"
0x18001ddb2  mov     [rsp+190h+var_170], rax
0x18001ddb7  lea     r9, [rsp+190h+var_120]
0x18001ddbc  mov     r8d, 300h
0x18001ddc2  lea     rdx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001ddc9  lea     rcx, [rbp+90h+var_50]
0x18001ddcd  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x18001ddd2  nop
0x18001ddd3  test    rsi, rsi
0x18001ddd6  jz      loc_18001E182
0x18001dddc  cmp     [rsi], r12w
0x18001dde0  jz      loc_18001E182
0x18001dde6  mov     r12, [r14+48h]
0x18001ddea  mov     edi, 1
0x18001ddef  test    r12, r12
0x18001ddf2  jz      short loc_18001DE3A
0x18001ddf4  mov     rdx, rsi
0x18001ddf7  lea     rcx, [rbp+90h+var_108]
0x18001ddfb  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x18001de00  mov     r8, r15
0x18001de03  mov     rdx, rax
0x18001de06  mov     rcx, r12
0x18001de09  call    ?RetrieveToken@CClientIdentityTokenBag@@QEAAHV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAVCPPCRLToken@@@Z; CClientIdentityTokenBag::RetrieveToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CPPCRLToken &)
0x18001de0e  xor     r12d, r12d
0x18001de11  test    eax, eax
0x18001de13  jz      short loc_18001DE3A
0x18001de15  lea     rdx, [rbp+90h+var_100]
0x18001de19  mov     rcx, r15
0x18001de1c  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x18001de21  mov     ebx, edi
0x18001de23  mov     [rsp+190h+var_11C], ebx
0x18001de27  mov     rax, [rax]
0x18001de2a  cmp     [rax-10h], r12d
0x18001de2e  jz      short loc_18001DE3A
0x18001de30  test    r13d, r13d
0x18001de33  jnz     short loc_18001DE3A
0x18001de35  mov     r15b, r12b
0x18001de38  jmp     short loc_18001DE3D
0x18001de3a  mov     r15b, dil
0x18001de3d  test    dil, bl
0x18001de40  jz      short loc_18001DE56
0x18001de42  and     ebx, 0FFFFFFFEh
0x18001de45  mov     [rsp+190h+var_11C], ebx
0x18001de49  mov     rcx, [rbp+90h+var_100]
0x18001de4d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001de51  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001de56  test    r15b, r15b
0x18001de59  jz      loc_18001E18A
0x18001de5f  cmp     [r14+48h], r12
0x18001de63  jz      loc_18001E15A
0x18001de69  xorps   xmm0, xmm0
0x18001de6c  movups  [rbp+90h+var_98], xmm0
0x18001de70  movups  [rbp+90h+var_88], xmm0
0x18001de74  mov     [rbp+90h+var_F0], r12
0x18001de78  mov     [rbp+90h+var_F8], r12d
0x18001de7c  mov     [rbp+90h+var_E8], r12d
0x18001de80  mov     [rbp+90h+var_A0], rsi
0x18001de84  mov     eax, [rbp+90h+arg_20]
0x18001de8a  mov     qword ptr [rbp+90h+var_88], rax
0x18001de8e  lea     rsi, [r14+40h]
0x18001de92  mov     rbx, [rsi]
0x18001de95  test    rbx, rbx
0x18001de98  jnz     short loc_18001DEDA
0x18001de9a  lea     ecx, [rbx+28h]; Size
0x18001de9d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dea2  mov     rbx, rax
0x18001dea5  mov     [rbp+90h+var_110], rax
0x18001dea9  xor     eax, eax
0x18001deab  mov     [rbx+8], rax
0x18001deaf  mov     [rbx+18h], edi
0x18001deb2  lea     rax, ??_7SmartWLIDHandle@@6B?$SmartObj@PEAX@@@; const SmartWLIDHandle::`vftable'{for `SmartObj<void *>'}
0x18001deb9  mov     [rbx], rax
0x18001debc  lea     rax, ??_7SmartWLIDHandle@@6BCRefCounted@@@; const SmartWLIDHandle::`vftable'{for `CRefCounted'}
0x18001dec3  mov     [rbx+10h], rax
0x18001dec7  mov     qword ptr [rbx+20h], 0
0x18001decf  mov     rcx, rsi
0x18001ded2  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x18001ded7  mov     [rsi], rbx
0x18001deda  lea     r9, [rsp+190h+Block]; struct _WLIDResponseParams **
0x18001dedf  lea     r8, [rbp+90h+var_A0]; struct _WLIDRequestParams *
0x18001dee3  mov     rcx, [rbx+8]; void *
0x18001dee7  call    ?WLIDCGetCachedTokens@@YAJQEAXKQEAU_WLIDRequestParams@@PEAPEAU_WLIDResponseParams@@@Z; WLIDCGetCachedTokens(void * const,ulong,_WLIDRequestParams * const,_WLIDResponseParams * *)
0x18001deec  mov     [rsp+190h+var_120], eax
0x18001def0  test    eax, eax
0x18001def2  jns     short loc_18001DF0A
0x18001def4  mov     [rsp+190h+var_120], 80048862h
0x18001defc  lea     rcx, [rbp+90h+var_F8]; this
0x18001df00  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18001df05  jmp     loc_18001E18A
0x18001df0a  mov     rdx, [rsp+190h+Block]
0x18001df0f  cmp     dword ptr [rdx+20h], 2
0x18001df13  jnz     short loc_18001DF82
0x18001df15  mov     r9d, dword ptr [rbp+90h+var_88]
0x18001df19  mov     rax, [rdx+68h]
0x18001df1d  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x18001df24  add     rcx, 288h
0x18001df2b  mov     dword ptr [rsp+190h+var_160], r9d
0x18001df30  mov     r9, [rdx+58h]
0x18001df34  mov     [rsp+190h+var_168], r9
0x18001df39  mov     [rsp+190h+var_170], rax
0x18001df3e  mov     r9, [rdx+28h]
0x18001df42  mov     r8, [rbp+90h+var_A0]
0x18001df46  mov     rdx, r14
0x18001df49  call    ?PutCertWithKey@CClientCertManager@@QEAAJPEAXPEBG1VCTime@ATL@@1K@Z; CClientCertManager::PutCertWithKey(void *,ushort const *,ushort const *,ATL::CTime,ushort const *,ulong)
0x18001df4e  mov     [rsp+190h+var_120], eax
0x18001df52  test    eax, eax
0x18001df54  jns     short loc_18001DF7D
0x18001df56  lea     r9, aPutcertwithkey; "PutCertWithKey failed (0x%x)."
0x18001df5d  mov     r8d, 32Ah; unsigned int
0x18001df63  mov     dword ptr [rsp+190h+var_170], eax
0x18001df67  lea     rdx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001df6e  mov     ecx, 2; unsigned __int8
0x18001df73  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001df78  jmp     loc_18001DEF4
0x18001df7d  mov     rdx, [rsp+190h+Block]
0x18001df82  xor     r9d, r9d; bool
0x18001df85  mov     r8d, [rdx+8]; unsigned int
0x18001df89  mov     rdx, [rdx+10h]; unsigned __int8 *
0x18001df8d  lea     rcx, [rbp+90h+var_F8]; this
0x18001df91  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x18001df96  mov     rax, [r14+48h]
0x18001df9a  mov     [rbp+90h+var_110], rax
0x18001df9e  lea     rcx, [rbp+90h+var_100]
0x18001dfa2  mov     [rbp+90h+var_78], rcx
0x18001dfa6  mov     rdx, [rsp+190h+Block]
0x18001dfab  mov     rdx, [rdx+38h]
0x18001dfaf  lea     rcx, [rbp+90h+var_100]
0x18001dfb3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001dfb8  mov     [rbp+90h+var_C0], rax
0x18001dfbc  mov     rdx, [rsp+190h+Block]
0x18001dfc1  mov     r12d, [rdx+4]
0x18001dfc5  mov     r13d, [rdx]
0x18001dfc8  mov     ecx, [rdx+20h]
0x18001dfcb  call    ?IDCRLTokenType@@YA?AW4TokenFormat@@K@Z; IDCRLTokenType(ulong)
0x18001dfd0  mov     r15d, eax
0x18001dfd3  mov     rcx, [rdx+68h]
0x18001dfd7  mov     [rbp+90h+var_B8], rcx
0x18001dfdb  mov     rcx, [rdx+60h]
0x18001dfdf  mov     [rbp+90h+var_B0], rcx
0x18001dfe3  lea     rax, [rbp+90h+var_108]
0x18001dfe7  mov     [rbp+90h+var_70], rax
0x18001dfeb  mov     rdx, [rdx+50h]
0x18001dfef  lea     rcx, [rbp+90h+var_108]
0x18001dff3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001dff8  mov     r14, rax
0x18001dffb  lea     rax, [rbp+90h+var_E0]
0x18001dfff  mov     [rbp+90h+var_68], rax
0x18001e003  mov     rcx, [rsp+190h+Block]
0x18001e008  lea     rdx, String
0x18001e00f  cmp     qword ptr [rcx+30h], 0
0x18001e014  cmovnz  rdx, [rcx+30h]
0x18001e019  lea     rcx, [rbp+90h+var_E0]
0x18001e01d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001e022  mov     rsi, rax
0x18001e025  lea     rax, [rbp+90h+var_D8]
0x18001e029  mov     [rbp+90h+var_60], rax
0x18001e02d  lea     rdx, String
0x18001e034  lea     rcx, [rbp+90h+var_D8]
0x18001e038  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001e03d  mov     rdi, rax
0x18001e040  lea     rax, [rbp+90h+var_D0]
0x18001e044  mov     [rbp+90h+var_58], rax
0x18001e048  mov     rdx, [rsp+190h+Block]
0x18001e04d  mov     rdx, [rdx+28h]
0x18001e051  lea     rcx, [rbp+90h+var_D0]
0x18001e055  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001e05a  mov     rbx, rax
0x18001e05d  mov     rdx, [rbp+90h+var_A0]
0x18001e061  lea     rcx, [rbp+90h+var_C8]
0x18001e065  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x18001e06a  nop
0x18001e06b  mov     rcx, [rbp+90h+var_C0]
0x18001e06f  mov     [rsp+190h+var_130], rcx
0x18001e074  mov     [rsp+190h+var_138], r12d
0x18001e079  mov     [rsp+190h+var_140], r13d
0x18001e07e  mov     [rsp+190h+var_148], r15d
0x18001e083  lea     rcx, [rbp+90h+var_F8]
0x18001e087  mov     [rsp+190h+var_150], rcx
0x18001e08c  lea     rcx, [rbp+90h+var_B8]
0x18001e090  mov     [rsp+190h+var_158], rcx
0x18001e095  lea     rcx, [rbp+90h+var_B0]
0x18001e099  mov     [rsp+190h+var_160], rcx
0x18001e09e  mov     [rsp+190h+var_168], r14
0x18001e0a3  mov     [rsp+190h+var_170], rsi
0x18001e0a8  mov     r9, rdi
0x18001e0ab  mov     r8, rbx
0x18001e0ae  mov     rdx, rax
0x18001e0b1  mov     rcx, [rbp+90h+var_110]
0x18001e0b5  call    ?StoreToken@CClientIdentityTokenBag@@QEAAJV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@111AEAVCTime@3@2AEBVCBytePtr@@KJJ1@Z; CClientIdentityTokenBag::StoreToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CTime &,ATL::CTime &,CBytePtr const &,ulong,long,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18001e0ba  mov     [rsp+190h+var_120], eax
0x18001e0be  xor     r12d, r12d
0x18001e0c1  test    eax, eax
0x18001e0c3  jns     short loc_18001E0D7
0x18001e0c5  lea     r9, aStoretokenFail; "StoreToken failed (0x%x)."
0x18001e0cc  mov     r8d, 340h
0x18001e0d2  jmp     loc_18001DF63
0x18001e0d7  mov     rbx, [rbp+90h+arg_0]
0x18001e0de  mov     rbx, [rbx+48h]
0x18001e0e2  mov     rdx, [rbp+90h+arg_8]
0x18001e0e9  lea     rcx, [rbp+90h+var_110]
0x18001e0ed  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x18001e0f2  mov     rdi, [rbp+90h+arg_10]
0x18001e0f9  mov     r8, rdi
0x18001e0fc  mov     rdx, rax
0x18001e0ff  mov     rcx, rbx
0x18001e102  call    ?RetrieveToken@CClientIdentityTokenBag@@QEAAHV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAVCPPCRLToken@@@Z; CClientIdentityTokenBag::RetrieveToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CPPCRLToken &)
0x18001e107  test    eax, eax
0x18001e109  jz      short loc_18001E12F
0x18001e10b  lea     rdx, [rbp+90h+arg_8]
0x18001e112  mov     rcx, rdi
0x18001e115  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x18001e11a  mov     ecx, [rsp+190h+var_11C]
0x18001e11e  or      ecx, 2
0x18001e121  mov     rax, [rax]
0x18001e124  cmp     [rax-10h], r12d
0x18001e128  jz      short loc_18001E133
0x18001e12a  mov     bl, r12b
0x18001e12d  jmp     short loc_18001E138
0x18001e12f  mov     ecx, [rsp+190h+var_11C]
0x18001e133  mov     ebx, 1
0x18001e138  test    cl, 2
0x18001e13b  jz      short loc_18001E14D
0x18001e13d  mov     rcx, [rbp+90h+arg_8]
0x18001e144  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001e148  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e14d  test    bl, bl
0x18001e14f  jz      loc_18001DEFC
0x18001e155  jmp     loc_18001DEF4
0x18001e15a  lea     r9, aInternalErrorG; "Internal Error: GetTokenBag() returned "...
0x18001e161  mov     r8d, 34Eh; unsigned int
0x18001e167  lea     rdx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001e16e  mov     ecx, 2; unsigned __int8
0x18001e173  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e178  mov     [rsp+190h+var_120], 80048862h
0x18001e180  jmp     short loc_18001E18A
0x18001e182  mov     [rsp+190h+var_120], 80070057h
0x18001e18a  mov     ebx, [rsp+190h+var_120]
0x18001e18e  lea     rcx, [rbp+90h+var_50]
0x18001e192  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001e197  nop
0x18001e198  mov     rcx, [rsp+190h+Block]; Block
0x18001e19d  test    rcx, rcx
0x18001e1a0  jz      short loc_18001E1A8
0x18001e1a2  call    cs:__imp_free
0x18001e1a8  mov     eax, ebx
0x18001e1aa  mov     rbx, [rsp+190h+arg_18]
0x18001e1b2  add     rsp, 160h
0x18001e1b9  pop     r15
0x18001e1bb  pop     r14
0x18001e1bd  pop     r13
0x18001e1bf  pop     r12
0x18001e1c1  pop     rdi
0x18001e1c2  pop     rsi
0x18001e1c3  pop     rbp
0x18001e1c4  retn
```
