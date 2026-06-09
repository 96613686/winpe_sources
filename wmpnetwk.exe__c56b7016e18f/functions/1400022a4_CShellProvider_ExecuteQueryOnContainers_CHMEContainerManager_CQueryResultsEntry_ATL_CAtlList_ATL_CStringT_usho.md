# CShellProvider::ExecuteQueryOnContainers(CHMEContainerManager &,CQueryResultsEntry *,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> const &,CdsQuery const *,_WMCMetadataItem const *,ulong,_WMCSortItem *,ulong,ulong,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ulong *,IWMCContentCollection * *)

- ea: `0x1400022a4`
- end: `0x14000286a`
- name: `?ExecuteQueryOnContainers@CShellProvider@@CAJAEAVCHMEContainerManager@@PEAVCQueryResultsEntry@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEBVCdsQuery@@PEBU_WMCMetadataItem@@KPEAU_WMCSortItem@@KKKAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@5@6PEAKPEAPEAUIWMCContentCollection@@@Z`
- size: `1478`
- prototype: `__int64 __fastcall(int, int, int, int, struct _WMCMetadataItem *, unsigned int, struct _WMCSortItem *, unsigned int, int, int, __int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140076684`
- `0x140076a14`
- `0x140076cd0`
- `0x14007bec0`

## callees

- `0x140002194`
- `0x1400022a4`
- `0x140002870`
- `0x1400028cc`
- `0x1400028f0`
- `0x140003690`
- `0x1400065e0`
- `0x14000b3b0`
- `0x14000c920`
- `0x14001e4d4`
- `0x14001ea40`
- `0x140024688`
- `0x1400246ac`
- `0x140025d90`
- `0x14002d6e4`
- `0x14003a988`
- `0x14003d1a8`
- `0x14003dbfc`
- `0x14004a834`
- `0x1400547b0`
- `0x140075ee8`
- `0x14007d124`
- `0x14008027c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400022fe`
- `KERNEL32!GetTickCount` at `0x140002353`
- `KERNEL32!GetTickCount` at `0x14000277a`
- `KERNEL32!GetTickCount` at `0x1400022fe`
- `KERNEL32!GetTickCount` at `0x140002353`
- `KERNEL32!GetTickCount` at `0x14000277a`
- `ole32!CoTaskMemFree` at `0x1400026a0`
- `ole32!CoTaskMemFree` at `0x1400026d5`
- `ole32!CoTaskMemFree` at `0x1400026a0`
- `ole32!CoTaskMemFree` at `0x1400026d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CShellProvider::ExecuteQueryOnContainers(
        CHMEContainerManager *a1,
        CQueryResultsEntry *a2,
        __int64 a3,
        const struct CdsQuery *a4,
        struct _WMCMetadataItem *a5,
        unsigned int a6,
        struct _WMCSortItem *a7,
        unsigned int a8,
        int a9,
        unsigned int a10,
        char **a11,
        __int64 *a12,
        _DWORD *a13,
        _QWORD *a14)
{
  unsigned int v15; // r12d
  unsigned int v16; // r15d
  int ContainerForID; // esi
  int v18; // r13d
  const void **v19; // rax
  const unsigned __int16 **v20; // r14
  struct IHMEMediaContainer *v21; // rbx
  const void **v22; // rdx
  unsigned __int16 *v23; // rdi
  unsigned int v24; // r14d
  unsigned int v25; // eax
  PVOID *v26; // rcx
  int v28; // eax
  unsigned int i; // r15d
  int v30; // eax
  DWORD v31; // [rsp+20h] [rbp-E0h]
  struct CShellQueryResults *v32; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  struct IHMEMediaContainer *v36; // [rsp+70h] [rbp-90h] BYREF
  const void **v37; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v38; // [rsp+80h] [rbp-80h] BYREF
  __int128 v39; // [rsp+88h] [rbp-78h] BYREF
  __int128 v40; // [rsp+98h] [rbp-68h]
  LPVOID pv; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v43; // [rsp+B8h] [rbp-48h]
  __int64 v44; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v45; // [rsp+C8h] [rbp-38h]
  __int128 v46; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-20h]
  __int128 v48; // [rsp+E8h] [rbp-18h]
  int v49; // [rsp+F8h] [rbp-8h]
  __int64 v50[16]; // [rsp+100h] [rbp+0h] BYREF
  DWORD TickCount; // [rsp+1A0h] [rbp+A0h]

  v15 = a9;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v16 = a8;
  }
  else
  {
    v16 = a8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_dqDDDqS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        *(_DWORD *)(a3 + 16),
        (char)a4,
        a9,
        a10,
        a8,
        (char)a7,
        *a12);
  }
  ContainerForID = 0;
  v33 = 0;
  v18 = 0;
  TickCount = GetTickCount();
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 10;
  v19 = *(const void ***)a3;
  v37 = *(const void ***)a3;
  v20 = (const unsigned __int16 **)a12;
  while ( 1 )
  {
    if ( ContainerForID < 0 || !v19 )
    {
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( !v18 )
        goto LABEL_51;
      goto LABEL_27;
    }
    if ( GetTickCount() - TickCount > 0x3A98 )
      break;
    v21 = 0;
    v36 = 0;
    v22 = v37;
    v37 = (const void **)*v37;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v38,
      v22 + 2);
    v32 = 0;
    v23 = v38;
    if ( CQueryResultsEntry::GetContainerResults(a2, v38, &v32) )
      goto LABEL_8;
    ContainerForID = CHMEContainerManager::GetContainerForID(a1, v23, &v36);
    if ( ContainerForID >= 0 )
    {
      v39 = 0;
      v40 = 0;
      pv = 0;
      LODWORD(v39) = 1;
      ContainerForID = CDevicePolicy::LoadPolicy((CDevicePolicy *)&v39, *a11, *v20);
      v21 = v36;
      if ( ContainerForID >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v35);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v34);
        CCDSToShellQueryTranslator::CCDSToShellQueryTranslator(
          (CCDSToShellQueryTranslator *)v50,
          v21,
          a4,
          a5,
          a6,
          a7,
          v16,
          (const struct __MIDL___MIDL_itf_playerps_0000_0005_0002 *)&v39);
        if ( (int)CCDSToShellQueryTranslator::GenerateShellQuery((CCDSToShellQueryTranslator *)v50) < 0 )
          goto LABEL_40;
        LOBYTE(v31) = 1;
        v28 = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *, __int64, __int64, _QWORD, DWORD, struct CShellQueryResults **))(*(_QWORD *)v21 + 128LL))(
                v21,
                v35,
                v34,
                0,
                v31,
                &v32);
        if ( v28 < 0 )
        {
          v33 = v28;
LABEL_40:
          ContainerForID = 0;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v50);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v34);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v35);
          CoTaskMemFree(pv);
          ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v32);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v38);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
          goto LABEL_14;
        }
        ContainerForID = CQueryResultsEntry::StoreContainerResults(a2, v23, v32);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v50);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v34);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v35);
      }
      CoTaskMemFree(pv);
LABEL_8:
      if ( ContainerForID >= 0 )
      {
        *(_QWORD *)&v39 = &CContainerQueryEvaluator::`vftable';
        *((_QWORD *)&v39 + 1) = a4;
        LODWORD(v40) = 0;
        ContainerForID = CShellQueryResults::FilterContainers(v32, (struct IContainerSearchFilter *)&v39);
        if ( ContainerForID >= 0 )
        {
          v24 = *((_DWORD *)v32 + 10) + *((_DWORD *)v32 + 18);
          v18 += v24;
          if ( v16 )
          {
            for ( i = 0; i < v24; ++i )
            {
              v44 = 0;
              v45 = i;
              ATL::CComPtr<IWMCContentServer>::operator=(&v44, &v32);
              ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>>::AddTail(&v46, &v44);
              ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v44);
            }
          }
          else if ( v15 > v24 )
          {
            v15 -= v24;
          }
          else if ( v24 )
          {
            v25 = a10;
            do
            {
              if ( !v25 )
                break;
              if ( v15 )
              {
                --v15;
              }
              else
              {
                v42 = 0;
                v43 = v16;
                ATL::CComPtr<IWMCContentServer>::operator=(&v42, &v32);
                ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>>::AddTail(
                  &v46,
                  &v42);
                --a10;
                ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v42);
                v25 = a10;
              }
              ++v16;
            }
            while ( v16 < v24 );
          }
        }
      }
      goto LABEL_9;
    }
    v21 = v36;
LABEL_9:
    if ( v32 )
      (*(void (__fastcall **)(struct CShellQueryResults *))(*(_QWORD *)v32 + 16LL))(v32);
    ATL::CStringData::Release((ATL::CStringData *)(v23 - 12));
    if ( v21 )
      (*(void (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v21 + 16LL))(v21);
    v16 = a8;
    v20 = (const unsigned __int16 **)a12;
LABEL_14:
    v19 = v37;
  }
  v26 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v31 = GetTickCount();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids, TickCount);
    v26 = (PVOID *)WPP_GLOBAL_Control;
  }
  v18 = 0;
LABEL_51:
  v30 = v33;
  if ( v33 < 0 )
  {
LABEL_57:
    ContainerForID = v30;
    goto LABEL_28;
  }
LABEL_27:
  if ( ContainerForID < 0 )
    goto LABEL_28;
  if ( !v16 )
  {
LABEL_56:
    v30 = CShellProviderAggregateResults::CreateInstance(&v46, v20, a14);
    *a13 = v18;
    v26 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_57;
  }
  ContainerForID = CShellProvider::SortAggregateItemResultSet(v20, v16, a7, &v46, v31);
  if ( ContainerForID >= 0 )
  {
    CShellProvider::PruneAggregateItemResultSet(v15, a10, &v46);
    goto LABEL_56;
  }
  v26 = (PVOID *)WPP_GLOBAL_Control;
LABEL_28:
  if ( v26 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v26 + 28) & 1) != 0
    && *((unsigned __int8 *)v26 + 25) >= ((ContainerForID >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_ddq(v26[2], 199, &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids, (unsigned int)ContainerForID, *a13, *a14);
  }
  ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>>::RemoveAll(&v46);
  return (unsigned int)ContainerForID;
}

```

## disassembly

```asm
0x1400022a4  mov     [rsp-8+arg_18], r9
0x1400022a9  mov     [rsp-8+arg_8], rdx
0x1400022ae  mov     [rsp-8+arg_0], rcx
0x1400022b3  push    rbp
0x1400022b4  push    rbx
0x1400022b5  push    rsi
0x1400022b6  push    rdi
0x1400022b7  push    r12
0x1400022b9  push    r13
0x1400022bb  push    r14
0x1400022bd  push    r15
0x1400022bf  lea     rbp, [rsp-48h]
0x1400022c4  sub     rsp, 148h
0x1400022cb  mov     rbx, r8
0x1400022ce  lea     rax, WPP_GLOBAL_Control
0x1400022d5  mov     r12d, [rbp+80h+arg_40]
0x1400022dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022e3  cmp     rcx, rax
0x1400022e6  jnz     loc_14000250A
0x1400022ec  mov     r15d, [rbp+80h+arg_38]
0x1400022f3  xor     esi, esi
0x1400022f5  xor     eax, eax
0x1400022f7  mov     [rsp+180h+var_128], eax
0x1400022fb  xor     r13d, r13d
0x1400022fe  call    cs:__imp_GetTickCount
0x140002304  mov     [rbp+80h+arg_10], eax
0x14000230a  xorps   xmm0, xmm0
0x14000230d  movdqu  [rbp+80h+var_B0], xmm0
0x140002312  mov     [rbp+80h+var_A0], rsi
0x140002316  xorps   xmm1, xmm1
0x140002319  movdqu  [rbp+80h+var_98], xmm1
0x14000231e  mov     [rbp+80h+var_88], 0Ah
0x140002325  mov     rax, [rbx]
0x140002328  mov     [rsp+180h+var_108], rax
0x14000232d  mov     r14, [rbp+80h+arg_58]
0x140002334  mov     rbx, [rbp+80h+arg_68]
0x14000233b  mov     rdi, [rbp+80h+arg_60]
0x140002342  test    esi, esi
0x140002344  js      loc_1400024C3
0x14000234a  test    rax, rax
0x14000234d  jz      loc_1400024C3
0x140002353  call    cs:__imp_GetTickCount
0x140002359  sub     eax, [rbp+80h+arg_10]
0x14000235f  cmp     eax, 3A98h
0x140002364  ja      loc_14000275B
0x14000236a  xor     ebx, ebx
0x14000236c  mov     [rsp+180h+var_110], rbx
0x140002371  mov     rax, [rsp+180h+var_108]
0x140002376  mov     rdx, rax
0x140002379  mov     rax, [rax]
0x14000237c  mov     [rsp+180h+var_108], rax
0x140002381  add     rdx, 10h
0x140002385  lea     rcx, [rbp+80h+var_100]
0x140002389  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14000238e  nop
0x14000238f  mov     [rsp+180h+var_130], rbx
0x140002394  lea     r8, [rsp+180h+var_130]; struct CShellQueryResults **
0x140002399  mov     rdi, [rbp+80h+var_100]
0x14000239d  mov     rdx, rdi; unsigned __int16 *
0x1400023a0  mov     rcx, [rbp+80h+arg_8]; this
0x1400023a7  call    ?GetContainerResults@CQueryResultsEntry@@QEAA_NPEBGPEAPEAVCShellQueryResults@@@Z; CQueryResultsEntry::GetContainerResults(ushort const *,CShellQueryResults * *)
0x1400023ac  test    al, al
0x1400023ae  jz      loc_14000256D
0x1400023b4  test    esi, esi
0x1400023b6  jns     short loc_140002406
0x1400023b8  mov     rcx, [rsp+180h+var_130]
0x1400023bd  test    rcx, rcx
0x1400023c0  jz      short loc_1400023CF
0x1400023c2  mov     rax, [rcx]
0x1400023c5  mov     rax, [rax+10h]
0x1400023c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023ce  nop
0x1400023cf  lea     rcx, [rdi-18h]; this
0x1400023d3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400023d8  nop
0x1400023d9  test    rbx, rbx
0x1400023dc  jz      short loc_1400023EE
0x1400023de  mov     rax, [rbx]
0x1400023e1  mov     rcx, rbx
0x1400023e4  mov     rax, [rax+10h]
0x1400023e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023ed  nop
0x1400023ee  mov     r15d, [rbp+80h+arg_38]
0x1400023f5  mov     r14, [rbp+80h+arg_58]
0x1400023fc  mov     rax, [rsp+180h+var_108]
0x140002401  jmp     loc_140002334
0x140002406  lea     rax, ??_7CContainerQueryEvaluator@@6B@; const CContainerQueryEvaluator::`vftable'
0x14000240d  mov     qword ptr [rbp+80h+var_F8], rax
0x140002411  mov     rax, [rbp+80h+arg_18]
0x140002418  mov     qword ptr [rbp+80h+var_F8+8], rax
0x14000241c  mov     dword ptr [rbp+80h+var_E8], 0
0x140002423  lea     rdx, [rbp+80h+var_F8]; struct IContainerSearchFilter *
0x140002427  mov     rcx, [rsp+180h+var_130]; this
0x14000242c  call    ?FilterContainers@CShellQueryResults@@QEAAJPEAVIContainerSearchFilter@@@Z; CShellQueryResults::FilterContainers(IContainerSearchFilter *)
0x140002431  mov     esi, eax
0x140002433  test    eax, eax
0x140002435  js      short loc_1400023B8
0x140002437  mov     rcx, [rsp+180h+var_130]
0x14000243c  mov     r14d, [rcx+48h]
0x140002440  add     r14d, [rcx+28h]
0x140002444  add     r13d, r14d
0x140002447  test    r15d, r15d
0x14000244a  jnz     loc_140002712
0x140002450  cmp     r12d, r14d
0x140002453  ja      loc_14000270A
0x140002459  test    r14d, r14d
0x14000245c  jz      loc_1400023B8
0x140002462  mov     eax, [rbp+80h+arg_48]
0x140002468  test    eax, eax
0x14000246a  jz      loc_1400023B8
0x140002470  test    r12d, r12d
0x140002473  jnz     short loc_1400024BE
0x140002475  mov     [rbp+80h+var_D0], 0
0x14000247d  mov     [rbp+80h+var_C8], r15d
0x140002481  lea     rdx, [rsp+180h+var_130]
0x140002486  lea     rcx, [rbp+80h+var_D0]
0x14000248a  call    ??4?$CComPtr@UIWMCContentServer@@@ATL@@QEAAPEAUIWMCContentServer@@AEBV01@@Z; ATL::CComPtr<IWMCContentServer>::operator=(ATL::CComPtr<IWMCContentServer> const &)
0x14000248f  lea     rdx, [rbp+80h+var_D0]
0x140002493  lea     rcx, [rbp+80h+var_B0]
0x140002497  call    ?AddTail@?$CAtlList@UShellAggregateResultItem@@V?$CElementTraits@UShellAggregateResultItem@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBUShellAggregateResultItem@@@Z; ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>>::AddTail(ShellAggregateResultItem const &)
0x14000249c  dec     [rbp+80h+arg_48]
0x1400024a2  lea     rcx, [rbp+80h+var_D0]; this
0x1400024a6  call    ??1ShellAggregateResultItem@@QEAA@XZ; ShellAggregateResultItem::~ShellAggregateResultItem(void)
0x1400024ab  mov     eax, [rbp+80h+arg_48]
0x1400024b1  inc     r15d
0x1400024b4  cmp     r15d, r14d
0x1400024b7  jb      short loc_140002468
0x1400024b9  jmp     loc_1400023B8
0x1400024be  dec     r12d
0x1400024c1  jmp     short loc_1400024B1
0x1400024c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400024ca  test    r13d, r13d
0x1400024cd  jz      loc_1400027B1
0x1400024d3  test    esi, esi
0x1400024d5  jns     loc_1400027BE
0x1400024db  lea     rax, WPP_GLOBAL_Control
0x1400024e2  cmp     rcx, rax
0x1400024e5  jnz     loc_14000281D
0x1400024eb  lea     rcx, [rbp+80h+var_B0]
0x1400024ef  call    ?RemoveAll@?$CAtlList@UShellAggregateResultItem@@V?$CElementTraits@UShellAggregateResultItem@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>>::RemoveAll(void)
0x1400024f4  mov     eax, esi
0x1400024f6  add     rsp, 148h
0x1400024fd  pop     r15
0x1400024ff  pop     r14
0x140002501  pop     r13
0x140002503  pop     r12
0x140002505  pop     rdi
0x140002506  pop     rsi
0x140002507  pop     rbx
0x140002508  pop     rbp
0x140002509  retn
0x14000250a  test    byte ptr [rcx+1Ch], 1
0x14000250e  jz      loc_1400022EC
0x140002514  mov     r15d, [rbp+80h+arg_38]
0x14000251b  cmp     byte ptr [rcx+19h], 5
0x14000251f  jb      loc_1400022F3
0x140002525  mov     rax, [rbp+80h+arg_58]
0x14000252c  mov     rax, [rax]
0x14000252f  mov     [rsp+180h+var_138], rax
0x140002534  mov     rax, [rbp+80h+arg_30]
0x14000253b  mov     [rsp+180h+var_140], rax
0x140002540  mov     dword ptr [rsp+180h+var_148], r15d
0x140002545  mov     r14d, [rbp+80h+arg_48]
0x14000254c  mov     [rsp+180h+var_150], r14d
0x140002551  mov     dword ptr [rsp+180h+var_158], r12d
0x140002556  mov     qword ptr [rsp+180h+var_160], r9
0x14000255b  mov     r9d, [r8+10h]
0x14000255f  mov     rcx, [rcx+10h]
0x140002563  call    WPP_SF_dqDDDqS
0x140002568  jmp     loc_1400022F3
0x14000256d  lea     r8, [rsp+180h+var_110]; struct IHMEMediaContainer **
0x140002572  mov     rdx, rdi; unsigned __int16 *
0x140002575  mov     rcx, [rbp+80h+arg_0]; this
0x14000257c  call    ?GetContainerForID@CHMEContainerManager@@QEAAJPEBGPEAPEAUIHMEMediaContainer@@@Z; CHMEContainerManager::GetContainerForID(ushort const *,IHMEMediaContainer * *)
0x140002581  mov     esi, eax
0x140002583  test    eax, eax
0x140002585  js      loc_140002700
0x14000258b  xorps   xmm0, xmm0
0x14000258e  xor     eax, eax
0x140002590  movups  [rbp+80h+var_F8], xmm0
0x140002594  movups  [rbp+80h+var_E8], xmm0
0x140002598  mov     [rbp+80h+pv], rax
0x14000259c  mov     dword ptr [rbp+80h+var_F8], 1
0x1400025a3  mov     r8, [r14]; unsigned __int16 *
0x1400025a6  mov     rax, [rbp+80h+arg_50]
0x1400025ad  mov     rdx, [rax]; unsigned __int16 *
0x1400025b0  lea     rcx, [rbp+80h+var_F8]; this
0x1400025b4  call    ?LoadPolicy@CDevicePolicy@@QEAAJPEBG0@Z; CDevicePolicy::LoadPolicy(ushort const *,ushort const *)
0x1400025b9  mov     esi, eax
0x1400025bb  mov     rbx, [rsp+180h+var_110]
0x1400025c0  test    eax, eax
0x1400025c2  js      loc_14000269C
0x1400025c8  lea     rcx, [rsp+180h+var_118]
0x1400025cd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x1400025d2  nop
0x1400025d3  lea     rcx, [rsp+180h+var_120]
0x1400025d8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x1400025dd  nop
0x1400025de  lea     rax, [rbp+80h+var_F8]
0x1400025e2  mov     [rsp+180h+var_148], rax; struct __MIDL___MIDL_itf_playerps_0000_0005_0002 *
0x1400025e7  mov     [rsp+180h+var_150], r15d; unsigned int
0x1400025ec  mov     rax, [rbp+80h+arg_30]
0x1400025f3  mov     [rsp+180h+var_158], rax; struct _WMCSortItem *
0x1400025f8  mov     eax, [rbp+80h+arg_28]
0x1400025fe  mov     [rsp+180h+var_160], eax; unsigned int
0x140002602  mov     r9, [rbp+80h+arg_20]; struct _WMCMetadataItem *
0x140002609  mov     r8, [rbp+80h+arg_18]; struct CdsQuery *
0x140002610  mov     rdx, rbx; struct IHMEMediaContainer *
0x140002613  lea     rcx, [rbp+80h+var_80]; this
0x140002617  call    ??0CCDSToShellQueryTranslator@@QEAA@PEAUIHMEMediaContainer@@PEBVCdsQuery@@PEBU_WMCMetadataItem@@KPEBU_WMCSortItem@@KPEBU__MIDL___MIDL_itf_playerps_0000_0005_0002@@@Z; CCDSToShellQueryTranslator::CCDSToShellQueryTranslator(IHMEMediaContainer *,CdsQuery const *,_WMCMetadataItem const *,ulong,_WMCSortItem const *,ulong,__MIDL___MIDL_itf_playerps_0000_0005_0002 const *)
0x14000261c  nop
0x14000261d  lea     r8, [rsp+180h+var_120]
0x140002622  lea     rdx, [rsp+180h+var_118]
0x140002627  lea     rcx, [rbp+80h+var_80]; this
0x14000262b  call    ?GenerateShellQuery@CCDSToShellQueryTranslator@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0@Z; CCDSToShellQueryTranslator::GenerateShellQuery(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140002630  test    eax, eax
0x140002632  js      short loc_1400026AF
0x140002634  mov     rax, [rbx]
0x140002637  lea     rcx, [rsp+180h+var_130]
0x14000263c  mov     [rsp+180h+var_158], rcx
0x140002641  mov     byte ptr [rsp+180h+var_160], 1
0x140002646  xor     r9d, r9d
0x140002649  mov     r8, [rsp+180h+var_120]
0x14000264e  mov     rdx, [rsp+180h+var_118]
0x140002653  mov     rcx, rbx
0x140002656  mov     rax, [rax+80h]
0x14000265d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002662  test    eax, eax
0x140002664  js      short loc_1400026AB
0x140002666  mov     r8, [rsp+180h+var_130]; struct CShellQueryResults *
0x14000266b  mov     rdx, rdi; unsigned __int16 *
0x14000266e  mov     rcx, [rbp+80h+arg_8]; this
0x140002675  call    ?StoreContainerResults@CQueryResultsEntry@@QEAAJPEBGPEAVCShellQueryResults@@@Z; CQueryResultsEntry::StoreContainerResults(ushort const *,CShellQueryResults *)
0x14000267a  mov     esi, eax
0x14000267c  lea     rcx, [rbp+80h+var_80]
0x140002680  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140002685  nop
0x140002686  lea     rcx, [rsp+180h+var_120]
0x14000268b  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140002690  nop
0x140002691  lea     rcx, [rsp+180h+var_118]
0x140002696  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14000269b  nop
0x14000269c  mov     rcx, [rbp+80h+pv]; pv
0x1400026a0  call    cs:__imp_CoTaskMemFree
0x1400026a6  jmp     loc_1400023B4
0x1400026ab  mov     [rsp+180h+var_128], eax
0x1400026af  xor     esi, esi
0x1400026b1  lea     rcx, [rbp+80h+var_80]
0x1400026b5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400026ba  nop
0x1400026bb  lea     rcx, [rsp+180h+var_120]
0x1400026c0  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400026c5  nop
0x1400026c6  lea     rcx, [rsp+180h+var_118]
0x1400026cb  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400026d0  nop
0x1400026d1  mov     rcx, [rbp+80h+pv]; pv
0x1400026d5  call    cs:__imp_CoTaskMemFree
0x1400026db  nop
0x1400026dc  lea     rcx, [rsp+180h+var_130]; this
0x1400026e1  call    ??1ShellAggregateResultItem@@QEAA@XZ; ShellAggregateResultItem::~ShellAggregateResultItem(void)
0x1400026e6  nop
0x1400026e7  lea     rcx, [rbp+80h+var_100]
0x1400026eb  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400026f0  nop
0x1400026f1  lea     rcx, [rsp+180h+var_110]
0x1400026f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400026fb  jmp     loc_1400023FC
0x140002700  mov     rbx, [rsp+180h+var_110]
0x140002705  jmp     loc_1400023B8
0x14000270a  sub     r12d, r14d
0x14000270d  jmp     loc_1400023B8
0x140002712  xor     r15d, r15d
0x140002715  test    r14d, r14d
0x140002718  jz      loc_1400023B8
0x14000271e  mov     [rbp+80h+var_C0], 0
0x140002726  mov     [rbp+80h+var_B8], r15d
0x14000272a  lea     rdx, [rsp+180h+var_130]
0x14000272f  lea     rcx, [rbp+80h+var_C0]
0x140002733  call    ??4?$CComPtr@UIWMCContentServer@@@ATL@@QEAAPEAUIWMCContentServer@@AEBV01@@Z; ATL::CComPtr<IWMCContentServer>::operator=(ATL::CComPtr<IWMCContentServer> const &)
0x140002738  lea     rdx, [rbp+80h+var_C0]
0x14000273c  lea     rcx, [rbp+80h+var_B0]
0x140002740  call    ?AddTail@?$CAtlList@UShellAggregateResultItem@@V?$CElementTraits@UShellAggregateResultItem@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBUShellAggregateResultItem@@@Z; ATL::CAtlList<ShellAggregateResultItem,ATL::CElementTraits<ShellAggregateResultItem>>::AddTail(ShellAggregateResultItem const &)
0x140002745  lea     rcx, [rbp+80h+var_C0]; this
0x140002749  call    ??1ShellAggregateResultItem@@QEAA@XZ; ShellAggregateResultItem::~ShellAggregateResultItem(void)
0x14000274e  inc     r15d
0x140002751  cmp     r15d, r14d
0x140002754  jb      short loc_14000271E
0x140002756  jmp     loc_1400023B8
0x14000275b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002762  lea     rax, WPP_GLOBAL_Control
0x140002769  cmp     rcx, rax
0x14000276c  jz      short loc_1400027AE
0x14000276e  test    byte ptr [rcx+1Ch], 2
0x140002772  jz      short loc_1400027AE
0x140002774  cmp     byte ptr [rcx+19h], 5
0x140002778  jb      short loc_1400027AE
0x14000277a  call    cs:__imp_GetTickCount
0x140002780  mov     edx, 0C6h
  ... truncated ...
```
