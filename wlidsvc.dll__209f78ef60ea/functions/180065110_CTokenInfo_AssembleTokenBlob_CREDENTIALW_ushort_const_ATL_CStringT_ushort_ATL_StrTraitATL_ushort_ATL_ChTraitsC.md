# CTokenInfo::AssembleTokenBlob(_CREDENTIALW *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180065110`
- end: `0x180065583`
- name: `?AssembleTokenBlob@CTokenInfo@@SAJPEAU_CREDENTIALW@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1139`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039fdc`
- `0x180047008`
- `0x180065d40`

## callees

- `0x18000a354`
- `0x18000c050`
- `0x180013fb4`
- `0x180015860`
- `0x18001647c`
- `0x18001686c`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180029d54`
- `0x18002b370`
- `0x180037e48`
- `0x180064b90`
- `0x180065110`
- `0x180079554`
- `0x1800a3b60`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800652a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800652a7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180065430`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180065430`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006521d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006521d`

## string_xrefs

- `0x1800651ae`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180065338`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180065493`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800654cb`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180065504`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180065185`: `CTokenInfo::AssembleTokenBlob`
- `0x180065331`: `CTokenInfo::AssembleTokenBlob`
- `0x18006531c`: `hr = SafeCopyMemory(spCredentialAttributes + credentialAttributesSizeInBytes, credentialAttributesMaxSizeInBytes - credentialAttributesSizeInBytes, pAttri->Value, pAttri->ValueSize)`
- `0x1800654be`: `Token blob is empty.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTokenInfo::AssembleTokenBlob(__int64 a1, _WORD *a2, __int64 a3)
{
  __int64 v3; // rdi
  unsigned int v6; // r15d
  const char *v7; // rax
  int v8; // r9d
  unsigned int v9; // r8d
  HLOCAL v10; // rbx
  unsigned int v11; // r12d
  __int64 v12; // rdi
  int v13; // esi
  __int64 v14; // rbx
  int v15; // eax
  _QWORD *v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  _QWORD *v20; // rdx
  char *v22; // [rsp+20h] [rbp-E0h]
  char *v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v29[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v30[5]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v31[224]; // [rsp+A0h] [rbp-60h] BYREF
  void *Block; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v33[264]; // [rsp+188h] [rbp+88h] BYREF

  v3 = a3;
  v26[0] = a3;
  v6 = 0;
  v24 = 0;
  v25 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  memset(v29, 0, sizeof(v29));
  v30[0] = "CTokenInfo::AssembleTokenBlob";
  v30[1] = &v24;
  v30[2] = 0;
  v30[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    "CTokenInfo::AssembleTokenBlob",
    (const char *)0x10C6,
    0,
    (const unsigned __int16 *)v22);
  if ( !a1 )
  {
    v24 = -2147186544;
    v7 = "pCred != nullptr";
    v8 = -2147186544;
    v9 = 4297;
LABEL_37:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CTokenInfo::AssembleTokenBlob",
      v9,
      v8,
      v7);
    goto LABEL_38;
  }
  if ( !a2 || !*a2 )
  {
    v24 = -2147024809;
    v7 = "wszKeyword != nullptr && *wszKeyword != L'\\0'";
    v8 = -2147024809;
    v9 = 4299;
    goto LABEL_37;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(v3, &qword_18013DE20);
  v27 = *(_DWORD *)(a1 + 52) << 8;
  v10 = LocalAlloc(0x40u, v27);
  v29[0] = v10;
  if ( !v10 )
  {
    v24 = -2147024882;
    goto LABEL_38;
  }
  v11 = 0;
  if ( *(_DWORD *)(a1 + 52) )
  {
    while ( 1 )
    {
      v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v28,
        L"%s%-d",
        a2,
        v6);
      v12 = *(_QWORD *)(a1 + 56);
      if ( !v12 )
      {
        v16 = (_QWORD *)(v28 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v28 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
LABEL_23:
        v10 = (HLOCAL)v29[0];
        v3 = v26[0];
        break;
      }
      v13 = 0;
      v14 = v28;
      if ( *(_DWORD *)(a1 + 52) )
      {
        while ( (unsigned int)_o__wcsicmp(v14, *(_QWORD *)v12) )
        {
          v12 += 24;
          if ( (unsigned int)++v13 >= *(_DWORD *)(a1 + 52) )
            goto LABEL_15;
        }
        v15 = SafeCopyMemory(v29[0] + v11, v27 - v11, *(_QWORD *)(v12 + 16), *(unsigned int *)(v12 + 12));
        v24 = v15;
        if ( v15 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
            "CTokenInfo::AssembleTokenBlob",
            0x10E6u,
            v15,
            "hr = SafeCopyMemory(spCredentialAttributes + credentialAttributesSizeInBytes, credentialAttributesMaxSizeInB"
            "ytes - credentialAttributesSizeInBytes, pAttri->Value, pAttri->ValueSize)");
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 - 24 + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v14 - 24) + 8LL))(*(_QWORD *)(v14 - 24));
          goto LABEL_38;
        }
        v11 += *(_DWORD *)(v12 + 12);
      }
LABEL_15:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v14 - 24) + 8LL))(*(_QWORD *)(v14 - 24));
      if ( ++v6 >= *(_DWORD *)(a1 + 52) )
        goto LABEL_23;
    }
  }
  v17 = -1;
  while ( 1 )
  {
    if ( aMicrosoftWindo_1[v17 + 1] != a2[v17 + 1] )
    {
LABEL_28:
      ATL::CSimpleStringT<char,0>::SetString(&v25, v10, v11);
      goto LABEL_29;
    }
    v17 += 2;
    if ( v17 == 33 )
      break;
    if ( aMicrosoftWindo_1[v17] != a2[v17] )
      goto LABEL_28;
  }
  if ( v11 )
  {
    ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v31);
    v26[0] = v11;
    v26[1] = v10;
    v18 = CAuthInfo::DecryptSystemContextCredentials<CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,char>(
            (__int64)v31,
            (__int64)v26,
            (__int64)&v25);
    v24 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v23) = v18;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        0x10FBu,
        L"Failure - CAuthInfo::DecryptSystemContextCredentials, HRESULT: 0x%08X\n",
        v23);
      ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v31);
      goto LABEL_38;
    }
    ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v31);
  }
  else
  {
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x1100u,
      L"Token blob is empty.");
  }
LABEL_29:
  Block = v33;
  ATL::CA2WEX<128>::Init(&Block, v25, 65001);
  ATL::CSimpleStringT<unsigned short,0>::SetString(v3, Block);
  if ( Block != v33 )
    free(Block);
LABEL_38:
  v19 = v24;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v30);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v29);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(&v25);
  v20 = (_QWORD *)(v25 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v25 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
  return v19;
}

```

## disassembly

```asm
0x180065110  mov     [rsp-8+arg_18], rbx
0x180065115  push    rbp
0x180065116  push    rsi
0x180065117  push    rdi
0x180065118  push    r12
0x18006511a  push    r13
0x18006511c  push    r14
0x18006511e  push    r15
0x180065120  lea     rbp, [rsp-1A0h]
0x180065128  sub     rsp, 2A0h
0x18006512f  mov     rax, cs:__security_cookie
0x180065136  xor     rax, rsp
0x180065139  mov     [rbp+1D0h+var_40], rax
0x180065140  mov     rdi, r8
0x180065143  mov     qword ptr [rsp+2D0h+var_290], r8
0x180065148  mov     r13, rdx
0x18006514b  mov     r14, rcx
0x18006514e  xor     r15d, r15d
0x180065151  mov     [rsp+2D0h+var_2A0], r15d
0x180065156  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18006515d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180065164  mov     rax, [rax+18h]
0x180065168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006516d  add     rax, 18h
0x180065171  mov     [rsp+2D0h+var_298], rax
0x180065176  mov     [rsp+2D0h+var_270], r15
0x18006517b  mov     [rsp+2D0h+var_260], r15
0x180065180  mov     [rsp+2D0h+var_268], r15
0x180065185  lea     rbx, aCtokeninfoAsse; "CTokenInfo::AssembleTokenBlob"
0x18006518c  mov     [rsp+2D0h+var_258], rbx
0x180065191  lea     rax, [rsp+2D0h+var_2A0]
0x180065196  mov     [rbp+1D0h+var_250], rax
0x18006519a  mov     [rbp+1D0h+var_248], r15
0x18006519e  mov     [rbp+1D0h+var_240], r15
0x1800651a2  xor     r9d, r9d; unsigned int
0x1800651a5  mov     r8d, 10C6h; char *
0x1800651ab  mov     rdx, rbx; char *
0x1800651ae  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800651b5  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800651ba  nop
0x1800651bb  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800651c2  test    r14, r14
0x1800651c5  jnz     short loc_1800651E7
0x1800651c7  mov     [rsp+2D0h+var_2A0], 80048890h
0x1800651cf  lea     rax, aPcredNullptr; "pCred != nullptr"
0x1800651d6  mov     r9d, 80048890h
0x1800651dc  mov     r8d, 10C9h
0x1800651e2  jmp     loc_1800654FC
0x1800651e7  test    r13, r13
0x1800651ea  jz      loc_1800654E1
0x1800651f0  cmp     word ptr [r13+0], 0
0x1800651f6  jz      loc_1800654E1
0x1800651fc  lea     rdx, qword_18013DE20
0x180065203  mov     rcx, rdi
0x180065206  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18006520b  mov     eax, [r14+34h]
0x18006520f  shl     eax, 8
0x180065212  mov     [rsp+2D0h+var_280], eax
0x180065216  mov     edx, eax; uBytes
0x180065218  mov     ecx, 40h ; '@'; uFlags
0x18006521d  call    cs:__imp_LocalAlloc
0x180065223  mov     rbx, rax
0x180065226  mov     [rsp+2D0h+var_270], rax
0x18006522b  test    rax, rax
0x18006522e  jnz     short loc_18006523D
0x180065230  mov     [rsp+2D0h+var_2A0], 8007000Eh
0x180065238  jmp     loc_180065510
0x18006523d  mov     r12d, r15d
0x180065240  cmp     [r14+34h], r15d
0x180065244  jbe     loc_1800653A2
0x18006524a  nop     word ptr [rax+rax+00h]
0x180065250  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180065257  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18006525e  mov     rax, [rax+18h]
0x180065262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065267  add     rax, 18h
0x18006526b  mov     [rsp+2D0h+var_278], rax
0x180065270  mov     r9d, r15d
0x180065273  mov     r8, r13
0x180065276  lea     rdx, aSD_0; "%s%-d"
0x18006527d  lea     rcx, [rsp+2D0h+var_278]
0x180065282  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180065287  mov     rdi, [r14+38h]
0x18006528b  test    rdi, rdi
0x18006528e  jz      loc_180065374
0x180065294  xor     esi, esi
0x180065296  mov     rbx, [rsp+2D0h+var_278]
0x18006529b  cmp     [r14+34h], esi
0x18006529f  jbe     short loc_1800652E7
0x1800652a1  mov     rdx, [rdi]
0x1800652a4  mov     rcx, rbx
0x1800652a7  call    cs:__imp__o__wcsicmp
0x1800652ad  test    eax, eax
0x1800652af  jz      short loc_1800652BF
0x1800652b1  add     rdi, 18h
0x1800652b5  inc     esi
0x1800652b7  cmp     esi, [r14+34h]
0x1800652bb  jb      short loc_1800652A1
0x1800652bd  jmp     short loc_1800652E7
0x1800652bf  mov     r9d, [rdi+0Ch]
0x1800652c3  mov     edx, [rsp+2D0h+var_280]
0x1800652c7  sub     edx, r12d
0x1800652ca  mov     ecx, r12d
0x1800652cd  add     rcx, [rsp+2D0h+var_270]
0x1800652d2  mov     r8, [rdi+10h]
0x1800652d6  call    SafeCopyMemory
0x1800652db  mov     [rsp+2D0h+var_2A0], eax
0x1800652df  test    eax, eax
0x1800652e1  js      short loc_18006531C
0x1800652e3  add     r12d, [rdi+0Ch]
0x1800652e7  lea     rdx, [rbx-18h]
0x1800652eb  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800652f2  mov     eax, esi
0x1800652f4  lock xadd [rdx+10h], eax
0x1800652f9  sub     eax, 1
0x1800652fc  jg      short loc_18006530D
0x1800652fe  mov     rcx, [rdx]
0x180065301  mov     rax, [rcx]
0x180065304  mov     rax, [rax+8]
0x180065308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006530d  inc     r15d
0x180065310  cmp     r15d, [r14+34h]
0x180065314  jb      loc_180065250
0x18006531a  jmp     short loc_180065398
0x18006531c  lea     rcx, aHrSafecopymemo_7; "hr = SafeCopyMemory(spCredentialAttribu"...
0x180065323  mov     [rsp+2D0h+var_2B0], rcx; char *
0x180065328  mov     r9d, eax; int
0x18006532b  mov     r8d, 10E6h; unsigned int
0x180065331  lea     rdx, aCtokeninfoAsse; "CTokenInfo::AssembleTokenBlob"
0x180065338  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006533f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180065344  nop
0x180065345  lea     rdx, [rbx-18h]
0x180065349  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180065350  mov     eax, esi
0x180065352  lock xadd [rdx+10h], eax
0x180065357  sub     eax, 1
0x18006535a  jg      loc_180065510
0x180065360  mov     rcx, [rdx]
0x180065363  mov     rax, [rcx]
0x180065366  mov     rax, [rax+8]
0x18006536a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006536f  jmp     loc_180065510
0x180065374  mov     rdx, [rsp+2D0h+var_278]
0x180065379  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18006537d  mov     eax, esi
0x18006537f  lock xadd [rdx+10h], eax
0x180065384  sub     eax, 1
0x180065387  jg      short loc_180065398
0x180065389  mov     rcx, [rdx]
0x18006538c  mov     rax, [rcx]
0x18006538f  mov     rax, [rax+8]
0x180065393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065398  mov     rbx, [rsp+2D0h+var_270]
0x18006539d  mov     rdi, qword ptr [rsp+2D0h+var_290]
0x1800653a2  lea     rdx, aMicrosoftWindo_1; "Microsoft_WindowsLive:authstate:"
0x1800653a9  mov     rcx, rsi
0x1800653ac  nop     dword ptr [rax+00h]
0x1800653b0  movzx   eax, word ptr [rdx+rcx*2+2]
0x1800653b5  cmp     ax, [r13+rcx*2+2]
0x1800653bb  jnz     short loc_1800653D3
0x1800653bd  add     rcx, 2
0x1800653c1  cmp     rcx, 21h ; '!'
0x1800653c5  jz      short loc_18006543B
0x1800653c7  movzx   eax, word ptr [rdx+rcx*2]
0x1800653cb  cmp     ax, [r13+rcx*2+0]
0x1800653d1  jz      short loc_1800653B0
0x1800653d3  mov     r8d, r12d
0x1800653d6  mov     rdx, rbx
0x1800653d9  lea     rcx, [rsp+2D0h+var_298]
0x1800653de  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::SetString(char const *,int)
0x1800653e3  lea     rax, [rbp+1D0h+var_148]
0x1800653ea  mov     [rbp+1D0h+Block], rax
0x1800653f1  mov     r8d, 0FDE9h
0x1800653f7  mov     rdx, [rsp+2D0h+var_298]
0x1800653fc  lea     rcx, [rbp+1D0h+Block]
0x180065403  call    ?Init@?$CA2WEX@$0IA@@ATL@@AEAAXPEBDI@Z; ATL::CA2WEX<128>::Init(char const *,uint)
0x180065408  nop
0x180065409  mov     rdx, [rbp+1D0h+Block]
0x180065410  mov     rcx, rdi
0x180065413  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180065418  nop
0x180065419  mov     rcx, [rbp+1D0h+Block]; Block
0x180065420  lea     rax, [rbp+1D0h+var_148]
0x180065427  cmp     rcx, rax
0x18006542a  jz      loc_180065510
0x180065430  call    cs:__imp_free
0x180065436  jmp     loc_180065510
0x18006543b  test    r12d, r12d
0x18006543e  jz      short loc_1800654BE
0x180065440  lea     rcx, [rbp+1D0h+var_230]; this
0x180065444  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x180065449  nop
0x18006544a  mov     dword ptr [rsp+2D0h+var_290+4], 0
0x180065452  mov     dword ptr [rsp+2D0h+var_290], r12d
0x180065457  mov     qword ptr [rsp+2D0h+var_290+8], rbx
0x18006545c  movaps  xmm0, [rsp+2D0h+var_290]
0x180065461  movdqa  [rsp+2D0h+var_290], xmm0
0x180065467  lea     r8, [rsp+2D0h+var_298]
0x18006546c  lea     rdx, [rsp+2D0h+var_290]
0x180065471  lea     rcx, [rbp+1D0h+var_230]
0x180065475  call    ??$DecryptSystemContextCredentials@V?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@D@CAuthInfo@@SAJPEAVIServiceExecutionContext@@U_CRYPTOAPI_BLOB@@AEAV?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@@Z; CAuthInfo::DecryptSystemContextCredentials<CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,char>(IServiceExecutionContext *,_CRYPTOAPI_BLOB,CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18006547a  mov     [rsp+2D0h+var_2A0], eax
0x18006547e  test    eax, eax
0x180065480  jns     short loc_1800654B0
0x180065482  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x180065486  lea     r9, aFailureCauthin; "Failure - CAuthInfo::DecryptSystemConte"...
0x18006548d  mov     r8d, 10FBh; unsigned int
0x180065493  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006549a  mov     ecx, 2; unsigned __int8
0x18006549f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800654a4  nop
0x1800654a5  lea     rcx, [rbp+1D0h+var_230]; this
0x1800654a9  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x1800654ae  jmp     short loc_180065510
0x1800654b0  lea     rcx, [rbp+1D0h+var_230]; this
0x1800654b4  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x1800654b9  jmp     loc_1800653E3
0x1800654be  lea     r9, aTokenBlobIsEmp; "Token blob is empty."
0x1800654c5  mov     r8d, 1100h; unsigned int
0x1800654cb  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800654d2  mov     ecx, 5; unsigned __int8
0x1800654d7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800654dc  jmp     loc_1800653E3
0x1800654e1  mov     [rsp+2D0h+var_2A0], 80070057h
0x1800654e9  lea     rax, aWszkeywordNull; "wszKeyword != nullptr && *wszKeyword !="...
0x1800654f0  mov     r9d, 80070057h; int
0x1800654f6  mov     r8d, 10CBh; unsigned int
0x1800654fc  mov     [rsp+2D0h+var_2B0], rax; char *
0x180065501  mov     rdx, rbx; char *
0x180065504  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006550b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180065510  mov     ebx, [rsp+2D0h+var_2A0]
0x180065514  lea     rcx, [rsp+2D0h+var_258]
0x180065519  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18006551e  nop
0x18006551f  lea     rcx, [rsp+2D0h+var_270]
0x180065524  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180065529  nop
0x18006552a  lea     rcx, [rsp+2D0h+var_298]
0x18006552f  call    ?SetZeroMemory@?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAAXXZ; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(void)
0x180065534  mov     rdx, [rsp+2D0h+var_298]
0x180065539  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18006553d  lock xadd [rdx+10h], esi
0x180065542  sub     esi, 1
0x180065545  jg      short loc_180065557
0x180065547  mov     rcx, [rdx]
0x18006554a  mov     r8, [rcx]
0x18006554d  mov     rax, [r8+8]
0x180065551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065556  nop
0x180065557  mov     eax, ebx
0x180065559  mov     rcx, [rbp+1D0h+var_40]
0x180065560  xor     rcx, rsp; StackCookie
0x180065563  call    __security_check_cookie
0x180065568  mov     rbx, [rsp+2D0h+arg_18]
0x180065570  add     rsp, 2A0h
0x180065577  pop     r15
0x180065579  pop     r14
0x18006557b  pop     r13
0x18006557d  pop     r12
0x18006557f  pop     rdi
0x180065580  pop     rsi
0x180065581  pop     rbp
0x180065582  retn
```
