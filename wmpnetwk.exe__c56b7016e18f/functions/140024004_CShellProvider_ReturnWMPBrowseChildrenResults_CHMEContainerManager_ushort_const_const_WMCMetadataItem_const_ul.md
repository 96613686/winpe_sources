# CShellProvider::ReturnWMPBrowseChildrenResults(CHMEContainerManager &,ushort const * const,_WMCMetadataItem const *,ulong,_WMCSortItem const *,ulong,ulong,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ulong *,IWMCContentCollection * *,ulong *)

- ea: `0x140024004`
- end: `0x14002467f`
- name: `?ReturnWMPBrowseChildrenResults@CShellProvider@@AEAAJAEAVCHMEContainerManager@@QEBGPEBU_WMCMetadataItem@@KPEBU_WMCSortItem@@KKKAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAKPEAPEAUIWMCContentCollection@@5@Z`
- size: `1659`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400740a0`

## callees

- `0x1400065e0`
- `0x140015100`
- `0x14001e4d4`
- `0x14001ea40`
- `0x140024004`
- `0x140024688`
- `0x140024770`
- `0x140025e00`
- `0x140025e58`
- `0x14002d6e4`
- `0x1400396dc`
- `0x140039e80`
- `0x14003a988`
- `0x14003ad78`
- `0x140054984`
- `0x140074fcc`
- `0x140075ee8`
- `0x140076358`
- `0x140079444`
- `0x14007bab0`
- `0x14007f4bc`
- `0x140086790`
- `0x140089fac`
- `0x14008a0bc`
- `0x14008a6b4`
- `0x14008a878`
- `0x14009e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14002438c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14002438c`
- `ole32!CoTaskMemFree` at `0x140024561`
- `ole32!CoTaskMemFree` at `0x140024561`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CShellProvider::ReturnWMPBrowseChildrenResults(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        struct _WMCMetadataItem *a4,
        unsigned int a5,
        struct _WMCSortItem *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        __int64 *a10,
        _DWORD *a11,
        _QWORD *a12,
        _DWORD *a13)
{
  const unsigned __int16 **v17; // r12
  __int64 v18; // rbx
  unsigned int ContainerIndexForObjectID; // eax
  int Container; // eax
  struct IHMEMediaContainer *v21; // r14
  int Policy; // edi
  struct _WMCSortItem *v23; // rsi
  const wchar_t *v24; // rdx
  __int64 v25; // rcx
  CShellProvider *v26; // rcx
  _DWORD *v27; // rax
  int v28; // ecx
  bool v29; // zf
  int v30; // r15d
  _DWORD *v31; // rsi
  _QWORD *i; // rdi
  __int64 v33; // rcx
  _QWORD *v34; // rax
  int v35; // edx
  _QWORD *v36; // rax
  __int64 v37; // r12
  unsigned __int16 *v38; // rax
  int v39; // edx
  unsigned int v40; // eax
  _QWORD *v41; // r13
  _DWORD *v42; // r8
  int v44; // [rsp+20h] [rbp-E0h]
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h]
  unsigned int v47; // [rsp+70h] [rbp-90h]
  struct IHMEMediaContainer *v48; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  __int128 v50; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+98h] [rbp-68h]
  __int128 v52; // [rsp+A0h] [rbp-60h]
  unsigned int v53; // [rsp+B0h] [rbp-50h]
  struct IHMEMediaContainer *v54; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE *v55; // [rsp+C0h] [rbp-40h]
  struct _WMCMetadataItem *v56; // [rsp+C8h] [rbp-38h]
  unsigned int v57; // [rsp+D0h] [rbp-30h]
  struct _WMCSortItem *v58; // [rsp+D8h] [rbp-28h]
  unsigned int v59; // [rsp+E0h] [rbp-20h]
  _OWORD *v60; // [rsp+E8h] [rbp-18h]
  __int64 v61; // [rsp+F0h] [rbp-10h]
  _OWORD v62[2]; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+118h] [rbp+18h]
  _BYTE v64[96]; // [rsp+120h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v17 = (const unsigned __int16 **)a10;
  }
  else
  {
    v17 = (const unsigned __int16 **)a10;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_SDqLLSqq(*((_QWORD *)WPP_GLOBAL_Control + 2), a7, (char)a6, a8, a9, *a10, (char)a11, (char)a12);
  }
  v48 = 0;
  v46 = 0;
  v45 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v49 = v18;
  *a13 = *(_DWORD *)(a1 + 844);
  ContainerIndexForObjectID = FindContainerIndexForObjectID(a3);
  if ( ContainerIndexForObjectID == -1
    || (Container = CHMEMediaContainerFactory::CreateContainer(
                      (const struct SHMEContainerDefinition *)&qword_1400BDF20[8
                                                                             * (unsigned __int64)ContainerIndexForObjectID],
                      (const struct CShellCommandFactory *)(a2 + 72),
                      (struct CGeneratedContainerFactory *)a2,
                      &v48),
        Container == -2147220635) )
  {
    Container = CGeneratedContainerFactory::FindContainer((CGeneratedContainerFactory *)a2, a3, &v48);
  }
  v21 = v48;
  if ( Container >= 0 )
  {
    memset(v62, 0, sizeof(v62));
    pv = 0;
    LODWORD(v62[0]) = 1;
    Policy = CDevicePolicy::LoadPolicy((CDevicePolicy *)v62, *(char **)(a1 + 80), *v17);
    if ( Policy < 0 )
    {
LABEL_59:
      CoTaskMemFree(pv);
      v41 = a12;
      goto LABEL_60;
    }
    CdsStarQuery::CdsStarQuery((CdsStarQuery *)v64);
    v54 = v21;
    if ( v21 )
      (*(void (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v21 + 8LL))(v21);
    v55 = v64;
    v56 = a4;
    v57 = a5;
    v23 = a6;
    v58 = a6;
    v59 = a7;
    v60 = v62;
    Policy = CCDSToShellQueryTranslator::_GenerateUnconditionalQuery((__int64)&v54, &v45);
    if ( Policy < 0 )
      goto LABEL_58;
    Policy = CCDSToShellQueryTranslator::_AddOrderByClause(&v54, &v49);
    if ( Policy >= 0 )
    {
      if ( *((_DWORD *)v55 + 6) == 1 )
      {
        if ( !CCDSToShellQueryTranslator::_HasDevicePolicyQuery((CCDSToShellQueryTranslator *)&v54) )
          goto LABEL_22;
        v24 = L" WHERE";
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::Append(&v45, L" WHERE");
        Policy = CCDSToShellQueryTranslator::_AddQueryCondition(&v54, v55, &v45);
        if ( Policy < 0 )
          goto LABEL_57;
        if ( !CCDSToShellQueryTranslator::_HasDevicePolicyQuery((CCDSToShellQueryTranslator *)&v54) )
          goto LABEL_22;
        v24 = L" AND";
      }
      ATL::CSimpleStringT<unsigned short,0>::Append(&v45, v24);
      Policy = CCDSToShellQueryTranslator::_GenerateQueryConditionForDevicePolicy(v25, v60, &v45);
      if ( Policy >= 0 )
      {
LABEL_22:
        LOBYTE(v44) = 1;
        v18 = v49;
        Policy = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *, __int64, __int64, _QWORD))(*(_QWORD *)v21
                                                                                                  + 128LL))(
                   v21,
                   v45,
                   v49,
                   0);
        if ( Policy >= 0 )
        {
          if ( a7 )
          {
            v27 = (_DWORD *)v46;
            if ( *(_QWORD *)(v46 + 40) )
            {
LABEL_27:
              v50 = 0;
              v51 = 0;
              v52 = 0;
              v53 = 10;
              v28 = v27[18];
              v29 = v27[10] + v28 == 0;
              v47 = v27[10] + v28;
              v30 = 0;
              if ( !v29 )
              {
                while ( 1 )
                {
                  v31 = 0;
                  if ( v27 )
                  {
                    v31 = v27;
                    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v27 + 8LL))(v27);
                  }
                  v61 = *((_QWORD *)&v50 + 1);
                  i = (_QWORD *)*((_QWORD *)&v52 + 1);
                  if ( !*((_QWORD *)&v52 + 1) )
                  {
                    v33 = v53;
                    if ( v53 )
                    {
                      if ( 0xFFFFFFFFFFFFFFFFuLL / v53 < 0x20 )
                        goto LABEL_46;
                      v33 = 32LL * v53;
                    }
                    v34 = malloc(v33 + 8);
                    if ( !v34 )
LABEL_46:
                      ATL::AtlThrowImpl(-2147024882);
                    *v34 = v52;
                    *(_QWORD *)&v52 = v34;
                    v35 = v53 - 1;
                    v36 = &v34[4 * v53 - 3];
                    for ( i = (_QWORD *)*((_QWORD *)&v52 + 1); v35 >= 0; --v35 )
                    {
                      *v36 = i;
                      i = v36;
                      *((_QWORD *)&v52 + 1) = v36;
                      v36 -= 4;
                    }
                  }
                  v37 = *i;
                  i[2] = v31;
                  if ( v31 )
                    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v31 + 8LL))(v31);
                  *((_DWORD *)i + 6) = v30;
                  *((_QWORD *)&v52 + 1) = v37;
                  i[1] = v61;
                  *i = 0;
                  ++v51;
                  if ( *((_QWORD *)&v50 + 1) )
                    **((_QWORD **)&v50 + 1) = i;
                  else
                    *(_QWORD *)&v50 = i;
                  *((_QWORD *)&v50 + 1) = i;
                  if ( v31 )
                    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v31 + 16LL))(v31);
                  if ( ++v30 >= v47 )
                    break;
                  v27 = (_DWORD *)v46;
                }
                v17 = (const unsigned __int16 **)a10;
                v23 = a6;
              }
              Policy = CShellProvider::SortAggregateItemResultSet(v17, a7, v23, &v50, v44);
              if ( Policy >= 0 )
              {
                CShellProvider::PruneAggregateItemResultSet(a8, a9, &v50);
                Policy = CShellProviderAggregateResults::CreateInstance(&v50, v17, a12);
              }
              ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>>::RemoveAll(&v50);
              goto LABEL_52;
            }
            if ( !CShellProvider::DoesSortContainDirectMapping(v26, a6, a7) )
            {
              v27 = (_DWORD *)v46;
              goto LABEL_27;
            }
          }
          Policy = CShellProviderResults::CreateBrowseChildrenInstance(v46, a8, a9, a6, a7, v17, a12);
LABEL_52:
          if ( Policy >= 0 )
          {
            *a11 = *(_DWORD *)(v46 + 40) + *(_DWORD *)(v46 + 72);
            v38 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v21 + 56LL))(v21);
            v39 = *v38 - 48;
            if ( *v38 == 48 )
              v39 = v38[1];
            if ( v39 )
            {
              v40 = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v21 + 80LL))(v21);
              *a13 = CShellProvider::GetUpdateIDForSchema(a1, v40);
            }
          }
        }
LABEL_58:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v54);
        CdsStarQuery::~CdsStarQuery((CdsStarQuery *)v64);
        goto LABEL_59;
      }
    }
LABEL_57:
    v18 = v49;
    goto LABEL_58;
  }
  v41 = a12;
  Policy = CShellProvider::ReturnWMPBrowseMetadataResults(
             a1,
             (CHMEContainerManager *)a2,
             a3,
             a4,
             a5,
             (__int64 *)v17,
             a12,
             a13);
  if ( Policy >= 0 )
  {
    v42 = a11;
    *a11 = 1;
    goto LABEL_61;
  }
LABEL_60:
  v42 = a11;
LABEL_61:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((Policy >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      177,
      &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
      (unsigned int)Policy,
      *v41,
      *v42);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v21 )
    (*(void (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)Policy;
}

```

## disassembly

```asm
0x140024004  mov     [rsp-8+arg_0], rcx
0x140024009  push    rbp
0x14002400a  push    rbx
0x14002400b  push    rsi
0x14002400c  push    rdi
0x14002400d  push    r12
0x14002400f  push    r13
0x140024011  push    r14
0x140024013  push    r15
0x140024015  lea     rbp, [rsp-48h]
0x14002401a  sub     rsp, 148h
0x140024021  mov     r15, r9
0x140024024  mov     rdi, r8
0x140024027  mov     rsi, rdx
0x14002402a  mov     r14, rcx
0x14002402d  lea     rax, WPP_GLOBAL_Control
0x140024034  mov     r13d, dword ptr [rbp+80h+arg_30]
0x14002403b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024042  cmp     rcx, rax
0x140024045  jz      short loc_1400240AE
0x140024047  test    byte ptr [rcx+1Ch], 1
0x14002404b  jz      short loc_1400240AE
0x14002404d  mov     r12, [rbp+80h+arg_48]
0x140024054  cmp     byte ptr [rcx+19h], 5
0x140024058  jb      short loc_1400240B5
0x14002405a  mov     rax, [rbp+80h+arg_58]
0x140024061  mov     qword ptr [rsp+180h+var_130], rax; char
0x140024066  mov     rax, [rbp+80h+arg_50]
0x14002406d  mov     qword ptr [rsp+180h+var_138], rax; char
0x140024072  mov     rax, [r12]
0x140024076  mov     [rsp+180h+var_140], rax; __int64
0x14002407b  mov     eax, dword ptr [rbp+80h+arg_40]
0x140024081  mov     dword ptr [rsp+180h+var_148], eax; char
0x140024085  mov     eax, dword ptr [rbp+80h+arg_38]
0x14002408b  mov     dword ptr [rsp+180h+var_150], eax; char
0x14002408f  mov     rax, [rbp+80h+arg_28]
0x140024096  mov     qword ptr [rsp+180h+var_158], rax; char
0x14002409b  mov     dword ptr [rsp+180h+var_160], r13d; char
0x1400240a0  mov     r9, r8
0x1400240a3  mov     rcx, [rcx+10h]; LoggerHandle
0x1400240a7  call    WPP_SF_SDqLLSqq
0x1400240ac  jmp     short loc_1400240B5
0x1400240ae  mov     r12, [rbp+80h+arg_48]
0x1400240b5  mov     [rsp+180h+var_108], 0
0x1400240be  mov     [rsp+180h+var_118], 0
0x1400240c7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400240ce  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400240d5  mov     rax, [rax+18h]
0x1400240d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400240de  add     rax, 18h
0x1400240e2  mov     [rsp+180h+var_120], rax
0x1400240e7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400240ee  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400240f5  mov     rax, [rax+18h]
0x1400240f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400240fe  lea     rbx, [rax+18h]
0x140024102  mov     [rbp+80h+var_100], rbx
0x140024106  mov     eax, [r14+34Ch]
0x14002410d  mov     rcx, [rbp+80h+arg_60]
0x140024114  mov     [rcx], eax
0x140024116  mov     rcx, rdi; unsigned __int16 *
0x140024119  call    ?FindContainerIndexForObjectID@@YAKPEBG@Z; FindContainerIndexForObjectID(ushort const *)
0x14002411e  cmp     eax, 0FFFFFFFFh
0x140024121  jz      short loc_14002414B
0x140024123  lea     rdx, [rsi+48h]; struct CShellCommandFactory *
0x140024127  mov     ecx, eax
0x140024129  shl     rcx, 6
0x14002412d  lea     rax, qword_1400BDF20
0x140024134  add     rcx, rax; struct SHMEContainerDefinition *
0x140024137  lea     r9, [rsp+180h+var_108]; struct IHMEMediaContainer **
0x14002413c  mov     r8, rsi; struct CGeneratedContainerFactory *
0x14002413f  call    ?CreateContainer@CHMEMediaContainerFactory@@SAJPEBUSHMEContainerDefinition@@PEBVCShellCommandFactory@@PEAVCGeneratedContainerFactory@@PEAPEAUIHMEMediaContainer@@@Z; CHMEMediaContainerFactory::CreateContainer(SHMEContainerDefinition const *,CShellCommandFactory const *,CGeneratedContainerFactory *,IHMEMediaContainer * *)
0x140024144  cmp     eax, 80040365h
0x140024149  jnz     short loc_14002415B
0x14002414b  lea     r8, [rsp+180h+var_108]; struct IHMEMediaContainer **
0x140024150  mov     rdx, rdi; unsigned __int16 *
0x140024153  mov     rcx, rsi; this
0x140024156  call    ?FindContainer@CGeneratedContainerFactory@@QEBAJPEBGPEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::FindContainer(ushort const *,IHMEMediaContainer * *)
0x14002415b  mov     r14, [rsp+180h+var_108]
0x140024160  test    eax, eax
0x140024162  js      loc_140024625
0x140024168  xorps   xmm0, xmm0
0x14002416b  xor     eax, eax
0x14002416d  movups  [rbp+80h+var_88], xmm0
0x140024171  movups  [rbp+80h+var_78], xmm0
0x140024175  mov     [rbp+80h+pv], rax
0x140024179  mov     dword ptr [rbp+80h+var_88], 1
0x140024180  mov     r8, [r12]; unsigned __int16 *
0x140024184  mov     rdx, [rbp+80h+arg_0]
0x14002418b  mov     rdx, [rdx+50h]; unsigned __int16 *
0x14002418f  lea     rcx, [rbp+80h+var_88]; this
0x140024193  call    ?LoadPolicy@CDevicePolicy@@QEAAJPEBG0@Z; CDevicePolicy::LoadPolicy(ushort const *,ushort const *)
0x140024198  mov     edi, eax
0x14002419a  test    eax, eax
0x14002419c  js      loc_14002455D
0x1400241a2  lea     rcx, [rbp+80h+var_60]; this
0x1400241a6  call    ??0CdsStarQuery@@QEAA@XZ; CdsStarQuery::CdsStarQuery(void)
0x1400241ab  nop
0x1400241ac  mov     [rbp+80h+var_C8], r14
0x1400241b0  test    r14, r14
0x1400241b3  jz      short loc_1400241C5
0x1400241b5  mov     rax, [r14]
0x1400241b8  mov     rcx, r14
0x1400241bb  mov     rax, [rax+8]
0x1400241bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400241c4  nop
0x1400241c5  lea     rax, [rbp+80h+var_60]
0x1400241c9  mov     [rbp+80h+var_C0], rax
0x1400241cd  mov     [rbp+80h+var_B8], r15
0x1400241d1  mov     eax, [rbp+80h+arg_20]
0x1400241d7  mov     [rbp+80h+var_B0], eax
0x1400241da  mov     rsi, [rbp+80h+arg_28]
0x1400241e1  mov     [rbp+80h+var_A8], rsi
0x1400241e5  mov     [rbp+80h+var_A0], r13d
0x1400241e9  lea     rax, [rbp+80h+var_88]
0x1400241ed  mov     [rbp+80h+var_98], rax
0x1400241f1  lea     rdx, [rsp+180h+var_120]
0x1400241f6  lea     rcx, [rbp+80h+var_C8]
0x1400241fa  call    ?_GenerateUnconditionalQuery@CCDSToShellQueryTranslator@@IEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CCDSToShellQueryTranslator::_GenerateUnconditionalQuery(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x1400241ff  mov     edi, eax
0x140024201  test    eax, eax
0x140024203  js      loc_140024549
0x140024209  lea     rdx, [rbp+80h+var_100]
0x14002420d  lea     rcx, [rbp+80h+var_C8]
0x140024211  call    ?_AddOrderByClause@CCDSToShellQueryTranslator@@IEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CCDSToShellQueryTranslator::_AddOrderByClause(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140024216  mov     edi, eax
0x140024218  test    eax, eax
0x14002421a  js      loc_140024545
0x140024220  mov     rax, [rbp+80h+var_C0]
0x140024224  cmp     dword ptr [rax+18h], 1
0x140024228  jz      short loc_14002426D
0x14002422a  lea     rdx, aWhere_1; " WHERE"
0x140024231  lea     rcx, [rsp+180h+var_120]
0x140024236  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14002423b  lea     r8, [rsp+180h+var_120]
0x140024240  mov     rdx, [rbp+80h+var_C0]
0x140024244  lea     rcx, [rbp+80h+var_C8]
0x140024248  call    ?_AddQueryCondition@CCDSToShellQueryTranslator@@IEAAJPEBVCdsQuery@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CCDSToShellQueryTranslator::_AddQueryCondition(CdsQuery const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14002424d  mov     edi, eax
0x14002424f  test    eax, eax
0x140024251  js      loc_140024545
0x140024257  lea     rcx, [rbp+80h+var_C8]; this
0x14002425b  call    ?_HasDevicePolicyQuery@CCDSToShellQueryTranslator@@IEAA_NXZ; CCDSToShellQueryTranslator::_HasDevicePolicyQuery(void)
0x140024260  test    al, al
0x140024262  jz      short loc_1400242A3
0x140024264  lea     rdx, aAnd_3; " AND"
0x14002426b  jmp     short loc_140024281
0x14002426d  lea     rcx, [rbp+80h+var_C8]; this
0x140024271  call    ?_HasDevicePolicyQuery@CCDSToShellQueryTranslator@@IEAA_NXZ; CCDSToShellQueryTranslator::_HasDevicePolicyQuery(void)
0x140024276  test    al, al
0x140024278  jz      short loc_1400242A3
0x14002427a  lea     rdx, aWhere_1; " WHERE"
0x140024281  lea     rcx, [rsp+180h+var_120]
0x140024286  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14002428b  lea     r8, [rsp+180h+var_120]
0x140024290  mov     rdx, [rbp+80h+var_98]
0x140024294  call    ?_GenerateQueryConditionForDevicePolicy@CCDSToShellQueryTranslator@@IEAAJPEBU__MIDL___MIDL_itf_playerps_0000_0005_0002@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CCDSToShellQueryTranslator::_GenerateQueryConditionForDevicePolicy(__MIDL___MIDL_itf_playerps_0000_0005_0002 const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140024299  mov     edi, eax
0x14002429b  test    eax, eax
0x14002429d  js      loc_140024545
0x1400242a3  mov     rax, [r14]
0x1400242a6  lea     rcx, [rsp+180h+var_118]
0x1400242ab  mov     qword ptr [rsp+180h+var_158], rcx
0x1400242b0  mov     [rsp+180h+var_160], 1
0x1400242b5  xor     r9d, r9d
0x1400242b8  mov     rbx, [rbp+80h+var_100]
0x1400242bc  mov     r8, rbx
0x1400242bf  mov     rdx, [rsp+180h+var_120]
0x1400242c4  mov     rcx, r14
0x1400242c7  mov     rax, [rax+80h]
0x1400242ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400242d3  mov     edi, eax
0x1400242d5  test    eax, eax
0x1400242d7  js      loc_140024549
0x1400242dd  test    r13d, r13d
0x1400242e0  jz      loc_1400244AD
0x1400242e6  mov     rax, [rsp+180h+var_118]
0x1400242eb  cmp     qword ptr [rax+28h], 0
0x1400242f0  jnz     short loc_14002430A
0x1400242f2  mov     r8d, r13d; unsigned int
0x1400242f5  mov     rdx, rsi; struct _WMCSortItem *
0x1400242f8  call    ?DoesSortContainDirectMapping@CShellProvider@@AEAA_NPEBU_WMCSortItem@@K@Z; CShellProvider::DoesSortContainDirectMapping(_WMCSortItem const *,ulong)
0x1400242fd  test    al, al
0x1400242ff  jnz     loc_1400244AD
0x140024305  mov     rax, [rsp+180h+var_118]
0x14002430a  xorps   xmm0, xmm0
0x14002430d  movdqu  [rbp+80h+var_F8], xmm0
0x140024312  mov     [rbp+80h+var_E8], 0
0x14002431a  xorps   xmm1, xmm1
0x14002431d  movdqu  [rbp+80h+var_E0], xmm1
0x140024322  mov     [rbp+80h+var_D0], 0Ah
0x140024329  mov     ecx, [rax+48h]
0x14002432c  add     ecx, [rax+28h]
0x14002432f  mov     [rsp+180h+var_110], ecx
0x140024333  mov     r15d, 0
0x140024339  jz      loc_140024460
0x14002433f  xor     esi, esi
0x140024341  test    rax, rax
0x140024344  jz      short loc_140024358
0x140024346  mov     rsi, rax
0x140024349  mov     rax, [rax]
0x14002434c  mov     rcx, rsi
0x14002434f  mov     rax, [rax+8]
0x140024353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024358  mov     rax, qword ptr [rbp+80h+var_F8+8]
0x14002435c  mov     [rbp+80h+var_90], rax
0x140024360  mov     rdi, qword ptr [rbp+80h+var_E0+8]
0x140024364  test    rdi, rdi
0x140024367  jnz     short loc_1400243D3
0x140024369  mov     ecx, [rbp+80h+var_D0]
0x14002436c  test    rcx, rcx
0x14002436f  jz      short loc_140024388
0x140024371  xor     edx, edx
0x140024373  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024377  div     rcx
0x14002437a  cmp     rax, 20h ; ' '
0x14002437e  jb      loc_140024447
0x140024384  shl     rcx, 5
0x140024388  add     rcx, 8; Size
0x14002438c  call    cs:__imp_malloc
0x140024392  test    rax, rax
0x140024395  jz      loc_140024447
0x14002439b  mov     rcx, qword ptr [rbp+80h+var_E0]
0x14002439f  mov     [rax], rcx
0x1400243a2  mov     qword ptr [rbp+80h+var_E0], rax
0x1400243a6  mov     edx, [rbp+80h+var_D0]
0x1400243a9  dec     edx
0x1400243ab  mov     ecx, edx
0x1400243ad  shl     rcx, 5
0x1400243b1  add     rcx, 8
0x1400243b5  add     rax, rcx
0x1400243b8  mov     rdi, qword ptr [rbp+80h+var_E0+8]
0x1400243bc  test    edx, edx
0x1400243be  js      short loc_1400243D3
0x1400243c0  mov     [rax], rdi
0x1400243c3  mov     rdi, rax
0x1400243c6  mov     qword ptr [rbp+80h+var_E0+8], rax
0x1400243ca  sub     rax, 20h ; ' '
0x1400243ce  sub     edx, 1
0x1400243d1  jns     short loc_1400243C0
0x1400243d3  mov     r12, [rdi]
0x1400243d6  mov     [rdi+10h], rsi
0x1400243da  test    rsi, rsi
0x1400243dd  jz      short loc_1400243EE
0x1400243df  mov     rax, [rsi]
0x1400243e2  mov     rcx, rsi
0x1400243e5  mov     rax, [rax+8]
0x1400243e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400243ee  mov     [rdi+18h], r15d
0x1400243f2  mov     qword ptr [rbp+80h+var_E0+8], r12
0x1400243f6  mov     rax, [rbp+80h+var_90]
0x1400243fa  mov     [rdi+8], rax
0x1400243fe  mov     qword ptr [rdi], 0
0x140024405  inc     [rbp+80h+var_E8]
0x140024409  mov     rax, qword ptr [rbp+80h+var_F8+8]
0x14002440d  test    rax, rax
0x140024410  jz      short loc_140024417
0x140024412  mov     [rax], rdi
0x140024415  jmp     short loc_14002441B
0x140024417  mov     qword ptr [rbp+80h+var_F8], rdi
0x14002441b  mov     qword ptr [rbp+80h+var_F8+8], rdi
0x14002441f  test    rsi, rsi
0x140024422  jz      short loc_140024433
0x140024424  mov     rax, [rsi]
0x140024427  mov     rcx, rsi
0x14002442a  mov     rax, [rax+10h]
0x14002442e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024433  inc     r15d
0x140024436  cmp     r15d, [rsp+180h+var_110]
0x14002443b  jnb     short loc_140024452
0x14002443d  mov     rax, [rsp+180h+var_118]
0x140024442  jmp     loc_14002433F
0x140024447  mov     ecx, 8007000Eh; int
0x14002444c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140024452  mov     r12, [rbp+80h+arg_48]
0x140024459  mov     rsi, [rbp+80h+arg_28]
0x140024460  lea     r9, [rbp+80h+var_F8]
0x140024464  mov     r8, rsi
0x140024467  mov     edx, r13d
0x14002446a  mov     rcx, r12
0x14002446d  call    ?SortAggregateItemResultSet@CShellProvider@@CAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@KPEBU_WMCSortItem@@AEAV?$CAtlList@UShellAggregateResultItem@@V?$CElementTraits@UShellAggregateResultItem@@@ATL@@@3@@Z; CShellProvider::SortAggregateItemResultSet(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ulong,_WMCSortItem const *,ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>> &)
0x140024472  mov     edi, eax
0x140024474  test    eax, eax
0x140024476  js      short loc_1400244A2
0x140024478  lea     r8, [rbp+80h+var_F8]
0x14002447c  mov     edx, dword ptr [rbp+80h+arg_40]
0x140024482  mov     ecx, dword ptr [rbp+80h+arg_38]
0x140024488  call    ?PruneAggregateItemResultSet@CShellProvider@@CAXKKAEAV?$CAtlList@UShellAggregateResultItem@@V?$CElementTraits@UShellAggregateResultItem@@@ATL@@@ATL@@@Z; CShellProvider::PruneAggregateItemResultSet(ulong,ulong,ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>> &)
0x14002448d  mov     r8, [rbp+80h+arg_58]
0x140024494  mov     rdx, r12
0x140024497  lea     rcx, [rbp+80h+var_F8]
0x14002449b  call    ?CreateInstance@CShellProviderAggregateResults@@SAJAEBV?$CAtlList@UShellAggregateResultItem@@V?$CElementTraits@UShellAggregateResultItem@@@ATL@@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@3@PEAPEAUIWMCContentCollection@@@Z; CShellProviderAggregateResults::CreateInstance(ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,IWMCContentCollection * *)
0x1400244a0  mov     edi, eax
0x1400244a2  lea     rcx, [rbp+80h+var_F8]
0x1400244a6  call    ?RemoveAll@?$CAtlList@UShellAggregateResultItem@@V?$CElementTraits@UShellAggregateResultItem@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>>::RemoveAll(void)
0x1400244ab  jmp     short loc_1400244DF
0x1400244ad  mov     rax, [rbp+80h+arg_58]
0x1400244b4  mov     qword ptr [rsp+180h+var_150], rax
0x1400244b9  mov     qword ptr [rsp+180h+var_158], r12
0x1400244be  mov     dword ptr [rsp+180h+var_160], r13d
  ... truncated ...
```
