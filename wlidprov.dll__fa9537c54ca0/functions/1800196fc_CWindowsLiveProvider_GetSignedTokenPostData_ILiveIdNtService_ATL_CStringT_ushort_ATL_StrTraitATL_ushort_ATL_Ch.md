# CWindowsLiveProvider::GetSignedTokenPostData(ILiveIdNtService *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800196fc`
- end: `0x1800199dd`
- name: `?GetSignedTokenPostData@CWindowsLiveProvider@@AEAAJPEAVILiveIdNtService@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018d5c`

## callees

- `0x180004824`
- `0x180004910`
- `0x180004b44`
- `0x180006b50`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18000a4f0`
- `0x18000f100`
- `0x18000f138`
- `0x180010b80`
- `0x180013434`
- `0x1800196fc`
- `0x1800199e4`
- `0x180019b50`
- `0x180019b80`
- `0x180025a38`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800199c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800199c3`

## string_xrefs

- `0x180019951`: `Device token POST data: '%s'`
- `0x180019893`: `User token POST data: '%s'`
- `0x180019738`: `CWindowsLiveProvider::GetSignedTokenPostData`
- `0x1800197ed`: `WLIDCGetSignedTokens call failed. hr=0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CWindowsLiveProvider::GetSignedTokenPostData(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  char v7; // r14
  int v8; // esi
  __int64 v9; // rax
  unsigned __int8 v10; // dl
  PPTraceStatus *v11; // rcx
  char v12; // cl
  const unsigned __int16 *String; // rax
  unsigned __int8 v14; // dl
  PPTraceStatus *v15; // rcx
  const unsigned __int16 *v16; // rax
  unsigned int v17; // ebx
  int *v19; // [rsp+20h] [rbp-59h]
  int *v20; // [rsp+20h] [rbp-59h]
  __int64 v21; // [rsp+30h] [rbp-49h] BYREF
  __int64 v22; // [rsp+38h] [rbp-41h] BYREF
  void **v23; // [rsp+40h] [rbp-39h] BYREF
  __int64 v24; // [rsp+48h] [rbp-31h]
  __int64 v25; // [rsp+50h] [rbp-29h]
  char v26; // [rsp+58h] [rbp-21h]
  int *v27[4]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v28[10]; // [rsp+80h] [rbp+7h] BYREF
  int v29; // [rsp+E0h] [rbp+67h] BYREF
  int v30; // [rsp+E4h] [rbp+6Bh]
  __int64 v31; // [rsp+E8h] [rbp+6Fh] BYREF
  void *Block; // [rsp+F8h] [rbp+7Fh] BYREF

  v30 = HIDWORD(a1);
  v29 = 0;
  Block = 0;
  v5 = 0;
  v22 = 0;
  v6 = 0;
  v21 = 0;
  v28[0] = "CWindowsLiveProvider::GetSignedTokenPostData";
  v28[1] = &v29;
  v28[2] = 0;
  v28[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    "CWindowsLiveProvider::GetSignedTokenPostData",
    (const char *)0x7FE,
    0,
    (const unsigned __int16 *)v19);
  v7 = 1;
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v27,
    "CWindowsLiveProvider::GetSignedTokenPostData",
    &v29,
    1u,
    &qword_180069A70);
  ATL::CSimpleStringT<unsigned short,0>::Truncate(a3, 0);
  v8 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)a2 + 160LL))(a2, &Block);
  v9 = 0;
  if ( Block )
  {
    v5 = *(_QWORD *)Block;
    CMIDLPtr<unsigned short *>::Clear(&v22);
    v22 = v5;
    v6 = *((_QWORD *)Block + 1);
    CMIDLPtr<unsigned short *>::Clear(&v21);
    v21 = v6;
    v9 = v5;
  }
  if ( v8 >= 0 )
  {
    if ( v9 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v31,
        v5);
      UrlEscapeString(&v31);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a3,
        L"SUDA=%ls",
        v31);
      if ( !TraceSession::IsRedactionEnabled((TraceSession *)&TraceSession::_instance)
        || (LOBYTE(v11) = 1, !PPTraceStatus::TraceOnFlag(v11, v10)) )
      {
        v12 = 0;
      }
      v23 = &PPRedactedStringW::`vftable';
      v24 = v31;
      v25 = 0;
      v26 = v12;
      String = PPRedactedStringW::GetString((PPRedactedStringW *)&v23);
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
        0x81Eu,
        L"User token POST data: '%s'",
        String);
      PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v23);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
    }
    if ( v6 )
    {
      if ( *(_DWORD *)(*a3 - 16LL) )
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a3, 38);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v31,
        v6);
      UrlEscapeString(&v31);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a3,
        L"SDDA=%ls",
        v31);
      if ( !TraceSession::IsRedactionEnabled((TraceSession *)&TraceSession::_instance)
        || (LOBYTE(v15) = 1, !PPTraceStatus::TraceOnFlag(v15, v14)) )
      {
        v7 = 0;
      }
      v23 = &PPRedactedStringW::`vftable';
      v24 = v31;
      v25 = 0;
      v26 = v7;
      v16 = PPRedactedStringW::GetString((PPRedactedStringW *)&v23);
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
        0x82Bu,
        L"Device token POST data: '%s'",
        v16);
      PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v23);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
    }
  }
  else
  {
    LODWORD(v20) = v8;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
      0x813u,
      L"WLIDCGetSignedTokens call failed. hr=0x%x.",
      v20);
  }
  v17 = v29;
  ErrorVerifier::CheckAgainstList((const char *)v27[3], *v27[2], (unsigned __int64)v27[1], v27[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v28);
  CMIDLPtr<unsigned short *>::Clear(&v21);
  CMIDLPtr<unsigned short *>::Clear(&v22);
  if ( Block )
    free(Block);
  return v17;
}

```

## disassembly

```asm
0x1800196fc  mov     qword ptr [rsp-8+arg_0], rcx
0x180019701  push    rbp
0x180019702  push    rbx
0x180019703  push    rsi
0x180019704  push    rdi
0x180019705  push    r12
0x180019707  push    r14
0x180019709  push    r15
0x18001970b  lea     rbp, [rsp-27h]
0x180019710  sub     rsp, 0A0h
0x180019717  mov     r15, r8
0x18001971a  mov     rsi, rdx
0x18001971d  mov     [rbp+57h+arg_0], 0
0x180019724  mov     [rbp+57h+Block], 0
0x18001972c  xor     ebx, ebx
0x18001972e  mov     [rbp+57h+var_98], rbx
0x180019732  xor     edi, edi
0x180019734  mov     [rbp+57h+var_A0], rdi
0x180019738  lea     r12, aCwindowslivepr_8; "CWindowsLiveProvider::GetSignedTokenPos"...
0x18001973f  mov     [rbp+57h+var_50], r12
0x180019743  lea     rax, [rbp+57h+arg_0]
0x180019747  mov     [rbp+57h+var_48], rax
0x18001974b  mov     [rbp+57h+var_40], rdi
0x18001974f  mov     [rbp+57h+var_38], rdi
0x180019753  xor     r9d, r9d; unsigned int
0x180019756  mov     r8d, 7FEh; char *
0x18001975c  mov     rdx, r12; char *
0x18001975f  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180019766  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001976b  nop
0x18001976c  lea     rax, qword_180069A70
0x180019773  mov     [rsp+0D0h+var_B0], rax; int *
0x180019778  lea     r14d, [rbx+1]
0x18001977c  mov     r9d, r14d; unsigned __int64
0x18001977f  lea     r8, [rbp+57h+arg_0]; int *
0x180019783  mov     rdx, r12; char *
0x180019786  lea     rcx, [rbp+57h+var_70]; this
0x18001978a  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18001978f  nop
0x180019790  xor     edx, edx
0x180019792  mov     rcx, r15
0x180019795  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18001979a  mov     rax, [rsi]
0x18001979d  lea     rdx, [rbp+57h+Block]
0x1800197a1  mov     rcx, rsi
0x1800197a4  mov     rax, [rax+0A0h]
0x1800197ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197b0  mov     esi, eax
0x1800197b2  xor     eax, eax
0x1800197b4  mov     rcx, [rbp+57h+Block]
0x1800197b8  test    rcx, rcx
0x1800197bb  jz      short loc_1800197E5
0x1800197bd  mov     rbx, [rcx]
0x1800197c0  lea     rcx, [rbp+57h+var_98]
0x1800197c4  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800197c9  mov     [rbp+57h+var_98], rbx
0x1800197cd  mov     rdi, [rbp+57h+Block]
0x1800197d1  mov     rdi, [rdi+8]
0x1800197d5  lea     rcx, [rbp+57h+var_A0]
0x1800197d9  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800197de  mov     [rbp+57h+var_A0], rdi
0x1800197e2  mov     rax, rbx
0x1800197e5  test    esi, esi
0x1800197e7  jns     short loc_180019810
0x1800197e9  mov     dword ptr [rsp+0D0h+var_B0], esi
0x1800197ed  lea     r9, aWlidcgetsigned; "WLIDCGetSignedTokens call failed. hr=0x"...
0x1800197f4  mov     r8d, 813h; unsigned int
0x1800197fa  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180019801  mov     ecx, 2; unsigned __int8
0x180019806  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001980b  jmp     loc_180019981
0x180019810  lea     rsi, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180019817  mov     r12d, 5
0x18001981d  test    rax, rax
0x180019820  jz      loc_1800198C3
0x180019826  mov     rdx, rbx
0x180019829  lea     rcx, [rbp+57h+arg_8]
0x18001982d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180019832  nop
0x180019833  lea     rcx, [rbp+57h+arg_8]
0x180019837  call    ?UrlEscapeString@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; UrlEscapeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001983c  mov     r8, [rbp+57h+arg_8]
0x180019840  lea     rdx, aSudaLs; "SUDA=%ls"
0x180019847  mov     rcx, r15
0x18001984a  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001984f  lea     rcx, ?_instance@TraceSession@@0V1@A; this
0x180019856  call    ?IsRedactionEnabled@TraceSession@@QEAA_NXZ; TraceSession::IsRedactionEnabled(void)
0x18001985b  cmp     al, r14b
0x18001985e  jnz     short loc_18001986C
0x180019860  mov     cl, r14b; this
0x180019863  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180019868  test    al, al
0x18001986a  jnz     short loc_18001986E
0x18001986c  xor     cl, cl
0x18001986e  mov     [rbp+57h+var_90], rsi
0x180019872  mov     rax, [rbp+57h+arg_8]
0x180019876  mov     [rbp+57h+var_88], rax
0x18001987a  mov     [rbp+57h+var_80], 0
0x180019882  mov     [rbp+57h+var_78], cl
0x180019885  lea     rcx, [rbp+57h+var_90]; this
0x180019889  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x18001988e  mov     [rsp+0D0h+var_B0], rax
0x180019893  lea     r9, aUserTokenPostD; "User token POST data: '%s'"
0x18001989a  mov     r8d, 81Eh; unsigned int
0x1800198a0  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800198a7  mov     ecx, r12d; unsigned __int8
0x1800198aa  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800198af  nop
0x1800198b0  lea     rcx, [rbp+57h+var_90]; this
0x1800198b4  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x1800198b9  nop
0x1800198ba  lea     rcx, [rbp+57h+arg_8]; void *
0x1800198be  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800198c3  test    rdi, rdi
0x1800198c6  jz      loc_180019981
0x1800198cc  mov     rax, [r15]
0x1800198cf  cmp     dword ptr [rax-10h], 0
0x1800198d3  jz      short loc_1800198E2
0x1800198d5  mov     edx, 26h ; '&'
0x1800198da  mov     rcx, r15
0x1800198dd  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800198e2  mov     rdx, rdi
0x1800198e5  lea     rcx, [rbp+57h+arg_8]
0x1800198e9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800198ee  nop
0x1800198ef  lea     rcx, [rbp+57h+arg_8]
0x1800198f3  call    ?UrlEscapeString@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; UrlEscapeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800198f8  mov     r8, [rbp+57h+arg_8]
0x1800198fc  lea     rdx, aSddaLs; "SDDA=%ls"
0x180019903  mov     rcx, r15
0x180019906  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001990b  lea     rcx, ?_instance@TraceSession@@0V1@A; this
0x180019912  call    ?IsRedactionEnabled@TraceSession@@QEAA_NXZ; TraceSession::IsRedactionEnabled(void)
0x180019917  cmp     al, r14b
0x18001991a  jnz     short loc_180019928
0x18001991c  mov     cl, r14b; this
0x18001991f  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180019924  test    al, al
0x180019926  jnz     short loc_18001992B
0x180019928  xor     r14b, r14b
0x18001992b  mov     [rbp+57h+var_90], rsi
0x18001992f  mov     rax, [rbp+57h+arg_8]
0x180019933  mov     [rbp+57h+var_88], rax
0x180019937  mov     [rbp+57h+var_80], 0
0x18001993f  mov     [rbp+57h+var_78], r14b
0x180019943  lea     rcx, [rbp+57h+var_90]; this
0x180019947  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x18001994c  mov     [rsp+0D0h+var_B0], rax
0x180019951  lea     r9, aDeviceTokenPos; "Device token POST data: '%s'"
0x180019958  mov     r8d, 82Bh; unsigned int
0x18001995e  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180019965  mov     ecx, r12d; unsigned __int8
0x180019968  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001996d  nop
0x18001996e  lea     rcx, [rbp+57h+var_90]; this
0x180019972  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180019977  nop
0x180019978  lea     rcx, [rbp+57h+arg_8]; void *
0x18001997c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180019981  mov     ebx, [rbp+57h+arg_0]
0x180019984  mov     r9, [rbp+57h+var_70]; int *
0x180019988  mov     r8, [rbp+57h+var_68]; unsigned __int64
0x18001998c  mov     rdx, [rbp+57h+var_60]
0x180019990  mov     edx, [rdx]; int
0x180019992  mov     rcx, [rbp+57h+var_58]; char *
0x180019996  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18001999b  nop
0x18001999c  lea     rcx, [rbp+57h+var_50]
0x1800199a0  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800199a5  nop
0x1800199a6  lea     rcx, [rbp+57h+var_A0]
0x1800199aa  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800199af  nop
0x1800199b0  lea     rcx, [rbp+57h+var_98]
0x1800199b4  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800199b9  nop
0x1800199ba  mov     rcx, [rbp+57h+Block]; Block
0x1800199be  test    rcx, rcx
0x1800199c1  jz      short loc_1800199C9
0x1800199c3  call    cs:__imp_free
0x1800199c9  mov     eax, ebx
0x1800199cb  add     rsp, 0A0h
0x1800199d2  pop     r15
0x1800199d4  pop     r14
0x1800199d6  pop     r12
0x1800199d8  pop     rdi
0x1800199d9  pop     rsi
0x1800199da  pop     rbx
0x1800199db  pop     rbp
0x1800199dc  retn
```
