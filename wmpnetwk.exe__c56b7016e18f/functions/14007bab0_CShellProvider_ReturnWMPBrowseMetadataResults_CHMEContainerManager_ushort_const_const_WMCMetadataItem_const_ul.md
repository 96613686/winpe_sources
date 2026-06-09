# CShellProvider::ReturnWMPBrowseMetadataResults(CHMEContainerManager &,ushort const * const,_WMCMetadataItem const *,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,IWMCContentCollection * *,ulong *)

- ea: `0x14007bab0`
- end: `0x14007beb4`
- name: `?ReturnWMPBrowseMetadataResults@CShellProvider@@AEAAJAEAVCHMEContainerManager@@QEBGPEBU_WMCMetadataItem@@KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAPEAUIWMCContentCollection@@PEAK@Z`
- size: `1028`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140024004`
- `0x1400740a0`

## callees

- `0x1400028cc`
- `0x140006d70`
- `0x14000b3b0`
- `0x14000c920`
- `0x140024688`
- `0x1400246ac`
- `0x140025d90`
- `0x140025f38`
- `0x14003a988`
- `0x14003d1a8`
- `0x14003dbfc`
- `0x14005480c`
- `0x140057660`
- `0x14006ab20`
- `0x14006b1f0`
- `0x14006d124`
- `0x140075178`
- `0x140079444`
- `0x14007bab0`
- `0x140081c6c`
- `0x14008720c`
- `0x14009e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14007be10`
- `ole32!CoTaskMemFree` at `0x14007be30`
- `ole32!CoTaskMemFree` at `0x14007be3b`
- `ole32!CoTaskMemFree` at `0x14007be10`
- `ole32!CoTaskMemFree` at `0x14007be30`
- `ole32!CoTaskMemFree` at `0x14007be3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 CShellProvider::ReturnWMPBrowseMetadataResults(
        __int64 a1,
        CHMEContainerManager *a2,
        unsigned __int16 *a3,
        struct _WMCMetadataItem *a4,
        unsigned int a5,
        __int64 *a6,
        _QWORD *a7,
        ...)
{
  _QWORD *v10; // r15
  const unsigned __int16 **v11; // rsi
  struct IHMEMediaContainer *v12; // r12
  int ItemIDFromObjectID; // edi
  struct IHMEMediaContainer *v14; // rbx
  unsigned __int16 *v15; // rax
  int v16; // r8d
  unsigned int v17; // eax
  struct IHMEMediaContainer *v18; // rbx
  __int64 v19; // r9
  unsigned __int16 *v20; // rax
  int v21; // edx
  unsigned int v22; // eax
  int v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  struct IHMEMediaContainer *v26; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v27; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h]
  _QWORD v31[2]; // [rsp+88h] [rbp-78h] BYREF
  int v32; // [rsp+98h] [rbp-68h]
  _BYTE v33[48]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v34[14]; // [rsp+D0h] [rbp-30h] BYREF
  struct IUnknown *v35; // [rsp+150h] [rbp+50h] BYREF
  struct _WMCMetadataItem *v36; // [rsp+168h] [rbp+68h]
  struct IHMEMediaContainer *v37; // [rsp+188h] [rbp+88h] BYREF
  va_list va; // [rsp+188h] [rbp+88h]
  va_list va1; // [rsp+190h] [rbp+90h] BYREF

  va_start(va1, a7);
  va_start(va, a7);
  v37 = va_arg(va1, struct IHMEMediaContainer *);
  v36 = a4;
  v10 = a7;
  v11 = (const unsigned __int16 **)a6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSq(*((_QWORD *)WPP_GLOBAL_Control + 2), *a6, (char)a7);
  }
  v12 = v37;
  *(_DWORD *)v37 = *(_DWORD *)(a1 + 844);
  v35 = 0;
  if ( (int)CHMEContainerManager::GetContainerIDResults(a2, a3, (struct CShellQueryResults **)&v35) < 0 )
  {
    v27 = 0;
    v28 = 0;
    ItemIDFromObjectID = CShellPropertyThunk::GetItemIDFromObjectID(a3, (LPVOID *)&v27, (LPVOID *)&v28);
    if ( ItemIDFromObjectID >= 0 )
    {
      v26 = 0;
      ItemIDFromObjectID = CHMEContainerManager::GetContainerForID(a2, v27, &v26);
      if ( ItemIDFromObjectID >= 0 )
      {
        CdsBinaryOpQuery::CdsBinaryOpQuery((CdsBinaryOpQuery *)v33);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
          (void **)va,
          (char *)a3);
        ItemIDFromObjectID = CdsBinaryOpQuery::Initialize(v33, 1, 1, (struct IHMEMediaContainer **)va);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((struct IHMEMediaContainer **)va);
        if ( ItemIDFromObjectID >= 0 )
        {
          memset(v29, 0, sizeof(v29));
          pv = 0;
          LODWORD(v29[0]) = 1;
          ItemIDFromObjectID = CDevicePolicy::LoadPolicy((CDevicePolicy *)v29, *(char **)(a1 + 80), *v11);
          if ( ItemIDFromObjectID >= 0 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v25);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>((struct IHMEMediaContainer **)va);
            v18 = v26;
            CCDSToShellQueryTranslator::CCDSToShellQueryTranslator(
              (CCDSToShellQueryTranslator *)v34,
              v26,
              (const struct CdsQuery *)v33,
              v36,
              a5,
              0,
              0,
              (const struct __MIDL___MIDL_itf_playerps_0000_0005_0002 *)v29);
            ItemIDFromObjectID = CCDSToShellQueryTranslator::GenerateShellQuery((CCDSToShellQueryTranslator *)v34);
            if ( ItemIDFromObjectID >= 0 )
            {
              LOBYTE(v24) = 1;
              LOBYTE(v19) = 1;
              ItemIDFromObjectID = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *, __int64, struct IHMEMediaContainer *, __int64, int, struct IUnknown **))(*(_QWORD *)v18 + 128LL))(
                                     v18,
                                     v25,
                                     v37,
                                     v19,
                                     v24,
                                     &v35);
              if ( ItemIDFromObjectID >= 0 )
              {
                v31[0] = &CContainerQueryEvaluator::`vftable';
                v31[1] = v33;
                v32 = 0;
                ItemIDFromObjectID = CShellQueryResults::FilterContainers(
                                       (CShellQueryResults *)v35,
                                       (struct IContainerSearchFilter *)v31);
                if ( ItemIDFromObjectID >= 0 )
                {
                  ItemIDFromObjectID = CShellProviderResults::CreateBrowseMetadataInstance(v35);
                  if ( ItemIDFromObjectID >= 0 )
                  {
                    v20 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v18 + 56LL))(v18);
                    v21 = *v20 - 48;
                    if ( *v20 == 48 )
                      v21 = v20[1];
                    if ( v21 )
                    {
                      v22 = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v18 + 80LL))(v18);
                      *(_DWORD *)v12 = CShellProvider::GetUpdateIDForSchema(a1, v22);
                    }
                  }
                }
              }
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v34);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((struct IHMEMediaContainer **)va);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v25);
          }
          CoTaskMemFree(pv);
        }
        CdsBinaryOpQuery::~CdsBinaryOpQuery((CdsBinaryOpQuery *)v33);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v26);
    }
    CoTaskMemFree(v27);
    CoTaskMemFree(v28);
  }
  else
  {
    ItemIDFromObjectID = CShellProviderResults::CreateBrowseMetadataInstance(v35);
    if ( ItemIDFromObjectID >= 0 && v35[5].lpVtbl == (struct IUnknownVtbl *)1 )
    {
      v37 = 0;
      CShellQueryResults::GetContainer((CShellQueryResults *)v35, 0, (struct IHMEMediaContainer **)va);
      v14 = v37;
      v15 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v37 + 56LL))(v37);
      v16 = *v15 - 48;
      if ( *v15 == 48 )
        v16 = v15[1];
      if ( v16 )
      {
        v17 = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v14 + 80LL))(v14);
        *(_DWORD *)v12 = CShellProvider::GetUpdateIDForSchema(a1, v17);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)va);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ItemIDFromObjectID >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      175,
      &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
      (unsigned int)ItemIDFromObjectID,
      *v10);
  }
  ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v35);
  return (unsigned int)ItemIDFromObjectID;
}

```

## disassembly

```asm
0x14007bab0  mov     [rsp-8+arg_8], rbx
0x14007bab5  mov     [rsp-8+arg_18], r9
0x14007baba  push    rbp
0x14007babb  push    rsi
0x14007babc  push    rdi
0x14007babd  push    r12
0x14007babf  push    r13
0x14007bac1  push    r14
0x14007bac3  push    r15
0x14007bac5  lea     rbp, [rsp-10h]
0x14007baca  sub     rsp, 110h
0x14007bad1  mov     rbx, r8
0x14007bad4  mov     r14, rdx
0x14007bad7  mov     r13, rcx
0x14007bada  lea     rax, WPP_GLOBAL_Control
0x14007bae1  mov     r15, [rbp+40h+arg_30]
0x14007bae8  mov     rsi, [rbp+40h+arg_28]
0x14007baec  mov     rcx, cs:WPP_GLOBAL_Control
0x14007baf3  cmp     rcx, rax
0x14007baf6  jz      short loc_14007BB29
0x14007baf8  test    byte ptr [rcx+1Ch], 1
0x14007bafc  jz      short loc_14007BB29
0x14007bafe  cmp     byte ptr [rcx+19h], 5
0x14007bb02  jb      short loc_14007BB29
0x14007bb04  mov     edx, 0AEh
0x14007bb09  mov     [rsp+140h+var_118], r15; char
0x14007bb0e  mov     rax, [rsi]
0x14007bb11  mov     qword ptr [rsp+140h+var_120], rax; __int64
0x14007bb16  mov     r9, rbx
0x14007bb19  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x14007bb20  mov     rcx, [rcx+10h]; LoggerHandle
0x14007bb24  call    WPP_SF_SSq
0x14007bb29  mov     eax, [r13+34Ch]
0x14007bb30  mov     r12, [rbp+40h+arg_38]
0x14007bb37  mov     [r12], eax
0x14007bb3b  xor     edi, edi
0x14007bb3d  mov     [rbp+40h+arg_0], rdi
0x14007bb41  lea     r8, [rbp+40h+arg_0]; struct CShellQueryResults **
0x14007bb45  mov     rdx, rbx; unsigned __int16 *
0x14007bb48  mov     rcx, r14; this
0x14007bb4b  call    ?GetContainerIDResults@CHMEContainerManager@@QEAAJPEBGPEAPEAVCShellQueryResults@@@Z; CHMEContainerManager::GetContainerIDResults(ushort const *,CShellQueryResults * *)
0x14007bb50  test    eax, eax
0x14007bb52  js      loc_14007BBF9
0x14007bb58  mov     r9, r15
0x14007bb5b  mov     r8, rsi
0x14007bb5e  mov     rcx, [rbp+40h+arg_0]; struct IUnknown *
0x14007bb62  call    ?CreateBrowseMetadataInstance@CShellProviderResults@@SAJPEAVCShellQueryResults@@KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAPEAUIWMCContentCollection@@@Z; CShellProviderResults::CreateBrowseMetadataInstance(CShellQueryResults *,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,IWMCContentCollection * *)
0x14007bb67  mov     edi, eax
0x14007bb69  test    eax, eax
0x14007bb6b  js      loc_14007BE41
0x14007bb71  mov     rcx, [rbp+40h+arg_0]; this
0x14007bb75  cmp     qword ptr [rcx+28h], 1
0x14007bb7a  jnz     loc_14007BE41
0x14007bb80  mov     [rbp+40h+arg_38], 0
0x14007bb8b  lea     r8, [rbp+40h+arg_38]; struct IHMEMediaContainer **
0x14007bb92  xor     edx, edx; unsigned __int64
0x14007bb94  call    ?GetContainer@CShellQueryResults@@QEBAX_KPEAPEAUIHMEMediaContainer@@@Z; CShellQueryResults::GetContainer(unsigned __int64,IHMEMediaContainer * *)
0x14007bb99  mov     rbx, [rbp+40h+arg_38]
0x14007bba0  mov     rax, [rbx]
0x14007bba3  mov     rcx, rbx
0x14007bba6  mov     rax, [rax+38h]
0x14007bbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bbaf  movzx   r8d, word ptr [rax]
0x14007bbb3  sub     r8d, 30h ; '0'
0x14007bbb7  jnz     short loc_14007BBC6
0x14007bbb9  movzx   r8d, word ptr [rax+2]
0x14007bbbe  xor     eax, eax
0x14007bbc0  movzx   edx, ax
0x14007bbc3  sub     r8d, edx
0x14007bbc6  test    r8d, r8d
0x14007bbc9  jz      short loc_14007BBE8
0x14007bbcb  mov     rax, [rbx]
0x14007bbce  mov     rcx, rbx
0x14007bbd1  mov     rax, [rax+50h]
0x14007bbd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bbda  mov     edx, eax
0x14007bbdc  mov     rcx, r13
0x14007bbdf  call    ?GetUpdateIDForSchema@CShellProvider@@AEAAKW4MediaCacheSchema@@@Z; CShellProvider::GetUpdateIDForSchema(MediaCacheSchema)
0x14007bbe4  mov     [r12], eax
0x14007bbe8  lea     rcx, [rbp+40h+arg_38]
0x14007bbef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007bbf4  jmp     loc_14007BE41
0x14007bbf9  mov     [rsp+140h+var_F0], rdi
0x14007bbfe  mov     [rsp+140h+var_E8], rdi
0x14007bc03  lea     r8, [rsp+140h+var_E8]; unsigned __int16 **
0x14007bc08  lea     rdx, [rsp+140h+var_F0]; unsigned __int16 **
0x14007bc0d  mov     rcx, rbx; unsigned __int16 *
0x14007bc10  call    ?GetItemIDFromObjectID@CShellPropertyThunk@@SAJPEBGPEAPEAG1@Z; CShellPropertyThunk::GetItemIDFromObjectID(ushort const *,ushort * *,ushort * *)
0x14007bc15  mov     edi, eax
0x14007bc17  test    eax, eax
0x14007bc19  js      loc_14007BE2B
0x14007bc1f  mov     [rsp+140h+var_F8], 0
0x14007bc28  lea     r8, [rsp+140h+var_F8]; struct IHMEMediaContainer **
0x14007bc2d  mov     rdx, [rsp+140h+var_F0]; unsigned __int16 *
0x14007bc32  mov     rcx, r14; this
0x14007bc35  call    ?GetContainerForID@CHMEContainerManager@@QEAAJPEBGPEAPEAUIHMEMediaContainer@@@Z; CHMEContainerManager::GetContainerForID(ushort const *,IHMEMediaContainer * *)
0x14007bc3a  mov     edi, eax
0x14007bc3c  xor     r14d, r14d
0x14007bc3f  test    eax, eax
0x14007bc41  js      loc_14007BE21
0x14007bc47  lea     rcx, [rbp+40h+var_A0]; this
0x14007bc4b  call    ??0CdsBinaryOpQuery@@QEAA@XZ; CdsBinaryOpQuery::CdsBinaryOpQuery(void)
0x14007bc50  nop
0x14007bc51  mov     rdx, rbx
0x14007bc54  lea     rcx, [rbp+40h+arg_38]
0x14007bc5b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14007bc60  nop
0x14007bc61  lea     r9, [rbp+40h+arg_38]
0x14007bc68  lea     edx, [r14+1]
0x14007bc6c  mov     r8d, edx
0x14007bc6f  lea     rcx, [rbp+40h+var_A0]
0x14007bc73  call    ?Initialize@CdsBinaryOpQuery@@QEAAJW4Value@CdsValue@@W4Op@CdsBinaryOp@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CdsBinaryOpQuery::Initialize(CdsValue::Value,CdsBinaryOp::Op,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14007bc78  mov     edi, eax
0x14007bc7a  lea     rcx, [rbp+40h+arg_38]
0x14007bc81  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007bc86  test    edi, edi
0x14007bc88  js      loc_14007BE17
0x14007bc8e  xorps   xmm0, xmm0
0x14007bc91  xor     eax, eax
0x14007bc93  movups  [rsp+140h+var_E0], xmm0
0x14007bc98  movups  [rsp+140h+var_D0], xmm0
0x14007bc9d  mov     [rbp+40h+pv], rax
0x14007bca1  mov     dword ptr [rsp+140h+var_E0], 1
0x14007bca9  mov     r8, [rsi]; unsigned __int16 *
0x14007bcac  mov     rdx, [r13+50h]; unsigned __int16 *
0x14007bcb0  lea     rcx, [rsp+140h+var_E0]; this
0x14007bcb5  call    ?LoadPolicy@CDevicePolicy@@QEAAJPEBG0@Z; CDevicePolicy::LoadPolicy(ushort const *,ushort const *)
0x14007bcba  mov     edi, eax
0x14007bcbc  test    eax, eax
0x14007bcbe  js      loc_14007BE0C
0x14007bcc4  lea     rcx, [rsp+140h+var_100]
0x14007bcc9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14007bcce  nop
0x14007bccf  lea     rcx, [rbp+40h+arg_38]
0x14007bcd6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14007bcdb  nop
0x14007bcdc  lea     rax, [rsp+140h+var_E0]
0x14007bce1  mov     [rsp+140h+var_108], rax; struct __MIDL___MIDL_itf_playerps_0000_0005_0002 *
0x14007bce6  mov     [rsp+140h+var_110], r14d; unsigned int
0x14007bceb  mov     [rsp+140h+var_118], r14; struct _WMCSortItem *
0x14007bcf0  mov     eax, [rbp+40h+arg_20]
0x14007bcf3  mov     [rsp+140h+var_120], eax; unsigned int
0x14007bcf7  mov     r9, [rbp+40h+arg_18]; struct _WMCMetadataItem *
0x14007bcfb  lea     r8, [rbp+40h+var_A0]; struct CdsQuery *
0x14007bcff  mov     rbx, [rsp+140h+var_F8]
0x14007bd04  mov     rdx, rbx; struct IHMEMediaContainer *
0x14007bd07  lea     rcx, [rbp+40h+var_70]; this
0x14007bd0b  call    ??0CCDSToShellQueryTranslator@@QEAA@PEAUIHMEMediaContainer@@PEBVCdsQuery@@PEBU_WMCMetadataItem@@KPEBU_WMCSortItem@@KPEBU__MIDL___MIDL_itf_playerps_0000_0005_0002@@@Z; CCDSToShellQueryTranslator::CCDSToShellQueryTranslator(IHMEMediaContainer *,CdsQuery const *,_WMCMetadataItem const *,ulong,_WMCSortItem const *,ulong,__MIDL___MIDL_itf_playerps_0000_0005_0002 const *)
0x14007bd10  nop
0x14007bd11  lea     r8, [rbp+40h+arg_38]
0x14007bd18  lea     rdx, [rsp+140h+var_100]
0x14007bd1d  lea     rcx, [rbp+40h+var_70]; this
0x14007bd21  call    ?GenerateShellQuery@CCDSToShellQueryTranslator@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0@Z; CCDSToShellQueryTranslator::GenerateShellQuery(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14007bd26  mov     edi, eax
0x14007bd28  test    eax, eax
0x14007bd2a  js      loc_14007BDEA
0x14007bd30  mov     rax, [rbx]
0x14007bd33  lea     rcx, [rbp+40h+arg_0]
0x14007bd37  mov     [rsp+140h+var_118], rcx
0x14007bd3c  mov     byte ptr [rsp+140h+var_120], 1
0x14007bd41  mov     r9b, 1
0x14007bd44  mov     r8, [rbp+40h+arg_38]
0x14007bd4b  mov     rdx, [rsp+140h+var_100]
0x14007bd50  mov     rcx, rbx
0x14007bd53  mov     rax, [rax+80h]
0x14007bd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bd5f  mov     edi, eax
0x14007bd61  test    eax, eax
0x14007bd63  js      loc_14007BDEA
0x14007bd69  lea     rax, ??_7CContainerQueryEvaluator@@6B@; const CContainerQueryEvaluator::`vftable'
0x14007bd70  mov     [rbp+40h+var_B8], rax
0x14007bd74  lea     rax, [rbp+40h+var_A0]
0x14007bd78  mov     [rbp+40h+var_B0], rax
0x14007bd7c  mov     [rbp+40h+var_A8], r14d
0x14007bd80  lea     rdx, [rbp+40h+var_B8]; struct IContainerSearchFilter *
0x14007bd84  mov     rcx, [rbp+40h+arg_0]; this
0x14007bd88  call    ?FilterContainers@CShellQueryResults@@QEAAJPEAVIContainerSearchFilter@@@Z; CShellQueryResults::FilterContainers(IContainerSearchFilter *)
0x14007bd8d  mov     edi, eax
0x14007bd8f  test    eax, eax
0x14007bd91  js      short loc_14007BDEA
0x14007bd93  mov     r9, r15
0x14007bd96  mov     r8, rsi
0x14007bd99  mov     rcx, [rbp+40h+arg_0]; struct IUnknown *
0x14007bd9d  call    ?CreateBrowseMetadataInstance@CShellProviderResults@@SAJPEAVCShellQueryResults@@KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAPEAUIWMCContentCollection@@@Z; CShellProviderResults::CreateBrowseMetadataInstance(CShellQueryResults *,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,IWMCContentCollection * *)
0x14007bda2  mov     edi, eax
0x14007bda4  test    eax, eax
0x14007bda6  js      short loc_14007BDEA
0x14007bda8  mov     rax, [rbx]
0x14007bdab  mov     rcx, rbx
0x14007bdae  mov     rax, [rax+38h]
0x14007bdb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bdb7  movzx   edx, word ptr [rax]
0x14007bdba  sub     edx, 30h ; '0'
0x14007bdbd  jnz     short loc_14007BDC9
0x14007bdbf  movzx   edx, word ptr [rax+2]
0x14007bdc3  movzx   ecx, r14w
0x14007bdc7  sub     edx, ecx
0x14007bdc9  test    edx, edx
0x14007bdcb  jz      short loc_14007BDEA
0x14007bdcd  mov     rax, [rbx]
0x14007bdd0  mov     rcx, rbx
0x14007bdd3  mov     rax, [rax+50h]
0x14007bdd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bddc  mov     edx, eax
0x14007bdde  mov     rcx, r13
0x14007bde1  call    ?GetUpdateIDForSchema@CShellProvider@@AEAAKW4MediaCacheSchema@@@Z; CShellProvider::GetUpdateIDForSchema(MediaCacheSchema)
0x14007bde6  mov     [r12], eax
0x14007bdea  lea     rcx, [rbp+40h+var_70]
0x14007bdee  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007bdf3  nop
0x14007bdf4  lea     rcx, [rbp+40h+arg_38]
0x14007bdfb  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007be00  nop
0x14007be01  lea     rcx, [rsp+140h+var_100]
0x14007be06  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007be0b  nop
0x14007be0c  mov     rcx, [rbp+40h+pv]; pv
0x14007be10  call    cs:__imp_CoTaskMemFree
0x14007be16  nop
0x14007be17  lea     rcx, [rbp+40h+var_A0]; this
0x14007be1b  call    ??1CdsBinaryOpQuery@@UEAA@XZ; CdsBinaryOpQuery::~CdsBinaryOpQuery(void)
0x14007be20  nop
0x14007be21  lea     rcx, [rsp+140h+var_F8]
0x14007be26  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007be2b  mov     rcx, [rsp+140h+var_F0]; pv
0x14007be30  call    cs:__imp_CoTaskMemFree
0x14007be36  mov     rcx, [rsp+140h+var_E8]; pv
0x14007be3b  call    cs:__imp_CoTaskMemFree
0x14007be41  mov     rcx, cs:WPP_GLOBAL_Control
0x14007be48  lea     rax, WPP_GLOBAL_Control
0x14007be4f  cmp     rcx, rax
0x14007be52  jz      short loc_14007BE8E
0x14007be54  test    byte ptr [rcx+1Ch], 1
0x14007be58  jz      short loc_14007BE8E
0x14007be5a  mov     edx, edi
0x14007be5c  sar     edx, 1Fh
0x14007be5f  and     edx, 0FFFFFFFDh
0x14007be62  add     edx, 5
0x14007be65  movzx   eax, byte ptr [rcx+19h]
0x14007be69  cmp     eax, edx
0x14007be6b  jb      short loc_14007BE8E
0x14007be6d  mov     edx, 0AFh
0x14007be72  mov     rax, [r15]
0x14007be75  mov     qword ptr [rsp+140h+var_120], rax
0x14007be7a  mov     r9d, edi
0x14007be7d  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x14007be84  mov     rcx, [rcx+10h]
0x14007be88  call    WPP_SF_dq
0x14007be8d  nop
0x14007be8e  lea     rcx, [rbp+40h+arg_0]; this
0x14007be92  call    ??1ShellAggregateResultItem@@QEAA@XZ; ShellAggregateResultItem::~ShellAggregateResultItem(void)
0x14007be97  mov     eax, edi
0x14007be99  mov     rbx, [rsp+140h+arg_8]
0x14007bea1  add     rsp, 110h
0x14007bea8  pop     r15
0x14007beaa  pop     r14
0x14007beac  pop     r13
0x14007beae  pop     r12
0x14007beb0  pop     rdi
0x14007beb1  pop     rsi
0x14007beb2  pop     rbp
0x14007beb3  retn
```
