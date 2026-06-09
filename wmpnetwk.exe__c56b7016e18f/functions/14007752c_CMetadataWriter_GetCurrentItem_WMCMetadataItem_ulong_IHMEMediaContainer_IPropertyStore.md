# CMetadataWriter::GetCurrentItem(_WMCMetadataItem *,ulong,IHMEMediaContainer * *,IPropertyStore * *)

- ea: `0x14007752c`
- end: `0x1400776fe`
- name: `?GetCurrentItem@CMetadataWriter@@IEAAJPEAU_WMCMetadataItem@@KPEAPEAUIHMEMediaContainer@@PEAPEAUIPropertyStore@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct _WMCMetadataItem *, unsigned int, struct IHMEMediaContainer **, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x14007df94`

## callees

- `0x1400028cc`
- `0x140006d70`
- `0x14000b3b0`
- `0x14000c920`
- `0x140024688`
- `0x1400246ac`
- `0x140025d90`
- `0x140029300`
- `0x14003d1a8`
- `0x14006ab20`
- `0x14006b1f0`
- `0x14006d124`
- `0x14007752c`
- `0x140081c6c`
- `0x14009e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400776dc`
- `ole32!CoTaskMemFree` at `0x1400776e6`
- `ole32!CoTaskMemFree` at `0x1400776dc`
- `ole32!CoTaskMemFree` at `0x1400776e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMetadataWriter::GetCurrentItem(
        const unsigned __int16 **this,
        struct _WMCMetadataItem *a2,
        unsigned int a3,
        struct IHMEMediaContainer **a4,
        struct IPropertyStore **a5)
{
  int ItemIDFromObjectID; // edi
  struct IHMEMediaContainer *v10; // rbx
  __int64 v11; // r9
  unsigned int v13; // [rsp+20h] [rbp-91h]
  __int64 v14; // [rsp+40h] [rbp-71h] BYREF
  CShellQueryResults *v15; // [rsp+48h] [rbp-69h] BYREF
  __int64 v16; // [rsp+50h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-59h] BYREF
  unsigned __int16 *v18; // [rsp+60h] [rbp-51h] BYREF
  _BYTE v19[48]; // [rsp+68h] [rbp-49h] BYREF
  _BYTE v20[104]; // [rsp+98h] [rbp-19h] BYREF
  struct IHMEMediaContainer *v21; // [rsp+110h] [rbp+5Fh] BYREF

  pv = 0;
  v18 = 0;
  ItemIDFromObjectID = CShellPropertyThunk::GetItemIDFromObjectID(this[1], (unsigned __int16 **)&pv, &v18);
  if ( ItemIDFromObjectID >= 0 )
  {
    v21 = 0;
    ItemIDFromObjectID = CHMEContainerManager::GetContainerForID(
                           (CHMEContainerManager *)*this,
                           (const unsigned __int16 *)pv,
                           &v21);
    if ( ItemIDFromObjectID >= 0 )
    {
      CdsBinaryOpQuery::CdsBinaryOpQuery((CdsBinaryOpQuery *)v19);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v14,
        this[1]);
      ItemIDFromObjectID = CdsBinaryOpQuery::Initialize(v19, 1, 1, &v14);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v14);
      if ( ItemIDFromObjectID >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v14);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v16);
        v10 = v21;
        CCDSToShellQueryTranslator::CCDSToShellQueryTranslator(
          (CCDSToShellQueryTranslator *)v20,
          v21,
          (const struct CdsQuery *)v19,
          a2,
          a3,
          0,
          0,
          0);
        ItemIDFromObjectID = CCDSToShellQueryTranslator::GenerateShellQuery((CCDSToShellQueryTranslator *)v20);
        if ( ItemIDFromObjectID >= 0 )
        {
          v15 = 0;
          LOBYTE(v13) = 0;
          LOBYTE(v11) = 1;
          ItemIDFromObjectID = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *, __int64, __int64, __int64, unsigned int, CShellQueryResults **))(*(_QWORD *)v10 + 128LL))(
                                 v10,
                                 v14,
                                 v16,
                                 v11,
                                 v13,
                                 &v15);
          if ( ItemIDFromObjectID >= 0 )
          {
            if ( *((_QWORD *)v15 + 9) )
            {
              CShellQueryResults::GetItem(v15, 0, a5);
              v21 = 0;
              *a4 = v10;
            }
            else
            {
              ItemIDFromObjectID = -2147023728;
            }
          }
          ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v15);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v20);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v16);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v14);
      }
      CdsBinaryOpQuery::~CdsBinaryOpQuery((CdsBinaryOpQuery *)v19);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v18);
  return (unsigned int)ItemIDFromObjectID;
}

```

## disassembly

```asm
0x14007752c  push    rbp
0x14007752e  push    rbx
0x14007752f  push    rsi
0x140077530  push    rdi
0x140077531  push    r14
0x140077533  push    r15
0x140077535  lea     rbp, [rsp-27h]
0x14007753a  sub     rsp, 0D8h
0x140077541  mov     rsi, r9
0x140077544  mov     r14d, r8d
0x140077547  mov     r15, rdx
0x14007754a  mov     rbx, rcx
0x14007754d  mov     [rbp+4Fh+pv], 0
0x140077555  mov     [rbp+4Fh+var_A0], 0
0x14007755d  lea     r8, [rbp+4Fh+var_A0]; unsigned __int16 **
0x140077561  lea     rdx, [rbp+4Fh+pv]; unsigned __int16 **
0x140077565  mov     rcx, [rcx+8]; unsigned __int16 *
0x140077569  call    ?GetItemIDFromObjectID@CShellPropertyThunk@@SAJPEBGPEAPEAG1@Z; CShellPropertyThunk::GetItemIDFromObjectID(ushort const *,ushort * *,ushort * *)
0x14007756e  mov     edi, eax
0x140077570  test    eax, eax
0x140077572  js      loc_1400776D8
0x140077578  mov     [rbp+4Fh+arg_0], 0
0x140077580  lea     r8, [rbp+4Fh+arg_0]; struct IHMEMediaContainer **
0x140077584  mov     rdx, [rbp+4Fh+pv]; unsigned __int16 *
0x140077588  mov     rcx, [rbx]; this
0x14007758b  call    ?GetContainerForID@CHMEContainerManager@@QEAAJPEBGPEAPEAUIHMEMediaContainer@@@Z; CHMEContainerManager::GetContainerForID(ushort const *,IHMEMediaContainer * *)
0x140077590  mov     edi, eax
0x140077592  test    eax, eax
0x140077594  js      loc_1400776CF
0x14007759a  lea     rcx, [rbp+4Fh+var_98]; this
0x14007759e  call    ??0CdsBinaryOpQuery@@QEAA@XZ; CdsBinaryOpQuery::CdsBinaryOpQuery(void)
0x1400775a3  nop
0x1400775a4  mov     rdx, [rbx+8]
0x1400775a8  lea     rcx, [rbp+4Fh+var_C0]
0x1400775ac  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400775b1  nop
0x1400775b2  lea     r9, [rbp+4Fh+var_C0]
0x1400775b6  mov     edx, 1
0x1400775bb  mov     r8d, edx
0x1400775be  lea     rcx, [rbp+4Fh+var_98]
0x1400775c2  call    ?Initialize@CdsBinaryOpQuery@@QEAAJW4Value@CdsValue@@W4Op@CdsBinaryOp@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CdsBinaryOpQuery::Initialize(CdsValue::Value,CdsBinaryOp::Op,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x1400775c7  mov     edi, eax
0x1400775c9  lea     rcx, [rbp+4Fh+var_C0]
0x1400775cd  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400775d2  test    edi, edi
0x1400775d4  js      loc_1400776C5
0x1400775da  lea     rcx, [rbp+4Fh+var_C0]
0x1400775de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x1400775e3  nop
0x1400775e4  lea     rcx, [rbp+4Fh+var_B0]
0x1400775e8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x1400775ed  nop
0x1400775ee  mov     [rsp+100h+var_C8], 0; struct __MIDL___MIDL_itf_playerps_0000_0005_0002 *
0x1400775f7  mov     [rsp+100h+var_D0], 0; unsigned int
0x1400775ff  mov     [rsp+100h+var_D8], 0; struct _WMCSortItem *
0x140077608  mov     [rsp+100h+var_E0], r14d; unsigned int
0x14007760d  mov     r9, r15; struct _WMCMetadataItem *
0x140077610  lea     r8, [rbp+4Fh+var_98]; struct CdsQuery *
0x140077614  mov     rbx, [rbp+4Fh+arg_0]
0x140077618  mov     rdx, rbx; struct IHMEMediaContainer *
0x14007761b  lea     rcx, [rbp+4Fh+var_68]; this
0x14007761f  call    ??0CCDSToShellQueryTranslator@@QEAA@PEAUIHMEMediaContainer@@PEBVCdsQuery@@PEBU_WMCMetadataItem@@KPEBU_WMCSortItem@@KPEBU__MIDL___MIDL_itf_playerps_0000_0005_0002@@@Z; CCDSToShellQueryTranslator::CCDSToShellQueryTranslator(IHMEMediaContainer *,CdsQuery const *,_WMCMetadataItem const *,ulong,_WMCSortItem const *,ulong,__MIDL___MIDL_itf_playerps_0000_0005_0002 const *)
0x140077624  nop
0x140077625  lea     r8, [rbp+4Fh+var_B0]
0x140077629  lea     rdx, [rbp+4Fh+var_C0]
0x14007762d  lea     rcx, [rbp+4Fh+var_68]; this
0x140077631  call    ?GenerateShellQuery@CCDSToShellQueryTranslator@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0@Z; CCDSToShellQueryTranslator::GenerateShellQuery(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140077636  mov     edi, eax
0x140077638  test    eax, eax
0x14007763a  js      short loc_1400776A7
0x14007763c  mov     [rbp+4Fh+var_B8], 0
0x140077644  mov     rax, [rbx]
0x140077647  lea     rcx, [rbp+4Fh+var_B8]
0x14007764b  mov     [rsp+100h+var_D8], rcx
0x140077650  mov     byte ptr [rsp+100h+var_E0], 0
0x140077655  mov     r9b, 1
0x140077658  mov     r8, [rbp+4Fh+var_B0]
0x14007765c  mov     rdx, [rbp+4Fh+var_C0]
0x140077660  mov     rcx, rbx
0x140077663  mov     rax, [rax+80h]
0x14007766a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007766f  mov     edi, eax
0x140077671  test    eax, eax
0x140077673  js      short loc_14007769D
0x140077675  mov     rcx, [rbp+4Fh+var_B8]; this
0x140077679  cmp     qword ptr [rcx+48h], 1
0x14007767e  jb      short loc_140077698
0x140077680  mov     r8, [rbp+4Fh+arg_20]; struct IPropertyStore **
0x140077684  xor     edx, edx; unsigned __int64
0x140077686  call    ?GetItem@CShellQueryResults@@QEBAX_KPEAPEAUIPropertyStore@@@Z; CShellQueryResults::GetItem(unsigned __int64,IPropertyStore * *)
0x14007768b  mov     [rbp+4Fh+arg_0], 0
0x140077693  mov     [rsi], rbx
0x140077696  jmp     short loc_14007769D
0x140077698  mov     edi, 80070490h
0x14007769d  lea     rcx, [rbp+4Fh+var_B8]; this
0x1400776a1  call    ??1ShellAggregateResultItem@@QEAA@XZ; ShellAggregateResultItem::~ShellAggregateResultItem(void)
0x1400776a6  nop
0x1400776a7  lea     rcx, [rbp+4Fh+var_68]
0x1400776ab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400776b0  nop
0x1400776b1  lea     rcx, [rbp+4Fh+var_B0]
0x1400776b5  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400776ba  nop
0x1400776bb  lea     rcx, [rbp+4Fh+var_C0]
0x1400776bf  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400776c4  nop
0x1400776c5  lea     rcx, [rbp+4Fh+var_98]; this
0x1400776c9  call    ??1CdsBinaryOpQuery@@UEAA@XZ; CdsBinaryOpQuery::~CdsBinaryOpQuery(void)
0x1400776ce  nop
0x1400776cf  lea     rcx, [rbp+4Fh+arg_0]
0x1400776d3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400776d8  mov     rcx, [rbp+4Fh+pv]; pv
0x1400776dc  call    cs:__imp_CoTaskMemFree
0x1400776e2  mov     rcx, [rbp+4Fh+var_A0]; pv
0x1400776e6  call    cs:__imp_CoTaskMemFree
0x1400776ec  mov     eax, edi
0x1400776ee  add     rsp, 0D8h
0x1400776f5  pop     r15
0x1400776f7  pop     r14
0x1400776f9  pop     rdi
0x1400776fa  pop     rsi
0x1400776fb  pop     rbx
0x1400776fc  pop     rbp
0x1400776fd  retn
```
