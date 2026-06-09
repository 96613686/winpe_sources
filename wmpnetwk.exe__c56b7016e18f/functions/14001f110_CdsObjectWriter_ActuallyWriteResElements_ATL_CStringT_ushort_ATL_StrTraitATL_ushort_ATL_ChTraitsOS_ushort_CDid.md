# CdsObjectWriter::ActuallyWriteResElements(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,CDidlLiteObjectWriter::CdsElement *)

- ea: `0x14001f110`
- end: `0x14001fadb`
- name: `?ActuallyWriteResElements@CdsObjectWriter@@MEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAVCdsElement@CDidlLiteObjectWriter@@@Z`
- size: `2507`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x140002ab4`
- `0x140003690`
- `0x1400065e0`
- `0x140018144`
- `0x14001e3ec`
- `0x14001f110`
- `0x14001fae4`
- `0x14001fe78`
- `0x1400207a0`
- `0x140024688`
- `0x140030724`
- `0x1400390a8`
- `0x1400396dc`
- `0x14003b2b8`
- `0x14003e4e0`
- `0x14003f17c`
- `0x140045f20`
- `0x140046020`
- `0x140046358`
- `0x140046d00`
- `0x140054490`
- `0x1400547b0`
- `0x140063b9c`
- `0x14009a224`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x14001f7a7`
- `KERNEL32!CompareStringOrdinal` at `0x14001f7a7`
- `KERNEL32!CompareStringW` at `0x14001f460`
- `KERNEL32!CompareStringW` at `0x14001f460`
- `OLEAUT32!__imp_VariantClear` at `0x14001f332`
- `OLEAUT32!__imp_VariantClear` at `0x14001f332`

## pseudocode

```c
__int64 __fastcall CdsObjectWriter::ActuallyWriteResElements(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // r12
  unsigned int *v6; // rsi
  __int64 v7; // rdx
  unsigned int v8; // ecx
  unsigned int v9; // r8d
  int v10; // r14d
  int v11; // r13d
  int WMCResElementData; // ebx
  const void ***v13; // rcx
  const void **v14; // r15
  const WCHAR *v15; // rdi
  PVOID *v16; // r10
  _QWORD *v17; // r14
  __int64 v19; // rsi
  __int64 v20; // rdx
  __int64 v21; // r8
  _QWORD *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rsi
  unsigned int v25; // r15d
  __int64 v26; // rdx
  __int64 *i; // rsi
  __int64 v28; // r15
  const WCHAR *v29; // r8
  unsigned __int64 v30; // rax
  __int64 v31; // rax
  PVOID v32; // rcx
  int v33; // edi
  __int64 v34; // r8
  _QWORD *v35; // rbx
  _QWORD *v36; // r14
  unsigned int v37; // eax
  int v38; // esi
  _QWORD *v39; // r15
  __int64 v40; // rbx
  _QWORD *v41; // r15
  _QWORD *v42; // r8
  _QWORD *v43; // rsi
  int v44; // eax
  __int64 *v45; // rsi
  __int64 v46; // r9
  _QWORD *v47; // rsi
  __int64 v48; // rdi
  _QWORD *Next; // rax
  int v50; // eax
  unsigned int v51; // [rsp+40h] [rbp-C0h] BYREF
  int v52; // [rsp+44h] [rbp-BCh]
  _QWORD *v53; // [rsp+48h] [rbp-B8h]
  _QWORD *v54; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+70h] [rbp-90h]
  unsigned int *v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+80h] [rbp-80h]
  unsigned int v61; // [rsp+84h] [rbp-7Ch]
  __int64 v62; // [rsp+88h] [rbp-78h] BYREF
  __int128 v63; // [rsp+90h] [rbp-70h] BYREF
  __int64 v64; // [rsp+A0h] [rbp-60h]
  __int128 v65; // [rsp+A8h] [rbp-58h]
  int v66; // [rsp+B8h] [rbp-48h]
  __int64 v67; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v68; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v69; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v70; // [rsp+D8h] [rbp-28h]
  __int128 v71; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int128 v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+108h] [rbp+8h]
  __int64 v75; // [rsp+110h] [rbp+10h]
  const void **v76; // [rsp+118h] [rbp+18h]
  __int128 v77; // [rsp+120h] [rbp+20h] BYREF
  __int64 v78; // [rsp+130h] [rbp+30h]
  __int128 v79; // [rsp+138h] [rbp+38h]
  int v80; // [rsp+148h] [rbp+48h]
  VARIANTARG pvarg; // [rsp+150h] [rbp+50h] BYREF
  __int64 v82[16]; // [rsp+170h] [rbp+70h] BYREF
  int v83; // [rsp+1F0h] [rbp+F0h]
  int v84; // [rsp+1F4h] [rbp+F4h]

  v58 = a3;
  v53 = a2;
  v5 = a1;
  v75 = a1;
  v6 = (unsigned int *)(a1 + 40);
  v59 = (unsigned int *)(a1 + 40);
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0qq_EventWriteTransfer(a1, CDS_Objwriter_Act_Write_Res_Element_Start, *v6, 0);
  else
    v59 = (unsigned int *)(a1 + 40);
  v7 = *a2;
  v8 = *(_DWORD *)(*a2 - 16LL);
  v9 = v8 - 10;
  v10 = 0;
  if ( v8 <= 0xA )
    v9 = 0;
  v61 = v9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)&WPP_dbb15cfc8a373ec782525eb0398c9c07_Traceguids,
      v7 + 2 * v9,
      a3);
  }
  pvarg.vt = 19;
  pvarg.lVal = CdsValues::GetElementTypeForAtom(*(unsigned int *)(a3 + 8));
  memset_0(v82, 0, 0x90u);
  lpString1 = (LPCWCH)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v70 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v69 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v68 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v67 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v11 = 0;
  v52 = 0;
  WMCResElementData = CdsItemInfoBase::GetWMCResElementData(
                        *(CdsItemInfoBase **)(v5 + 8),
                        (__int64)&v69,
                        (__int64)&v68,
                        (__int64)&v67,
                        (__int64)v82);
  v60 = WMCResElementData;
  v83 = *v6;
  v13 = *(const void ****)(v5 + 32);
  v14 = *v13;
  v15 = lpString1;
  if ( WMCResElementData < 0 )
  {
LABEL_8:
    v16 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_9;
  }
  while ( v14 )
  {
    v51 = 0;
    v55 = 0;
    v76 = (const void **)*v14;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v62,
      v14 + 2);
    v34 = 0;
    v56 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v66 = 10;
    v77 = 0;
    v78 = 0;
    v79 = 0;
    v80 = 10;
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v74 = 10;
    LODWORD(v54) = 1;
    v82[2] = v62;
    v84 = *(_DWORD *)(v5 + 16);
    v35 = **(_QWORD ***)(v5 + 56);
    v33 = 1;
    while ( v35 )
    {
      v36 = (_QWORD *)v35[2];
      v35 = (_QWORD *)*v35;
      v54 = v36;
      if ( v36 )
        (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v36 + 8LL))(v36, v26, v34);
      if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
        McTemplateU0qq_EventWriteTransfer(v32, CDS_Objwriter_Get_Res_Elements_Start, 0, 0);
      v37 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, unsigned int *, __int64 *))(*v36 + 64LL))(
              v36,
              v82,
              &v51,
              &v55);
      v38 = v37;
      if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
        McTemplateU0qq_EventWriteTransfer(v32, CDS_Objwriter_Get_Res_Elements_Stop, v51, v37);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v32 = (PVOID)(((v38 >> 31) & 0xFFFFFFFD) + 5);
        if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)v32 )
          WPP_SF_ddq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            &WPP_dbb15cfc8a373ec782525eb0398c9c07_Traceguids,
            (unsigned int)v38,
            v51,
            v55);
      }
      if ( v38 >= 0 && v51 && v55 )
      {
        v39 = operator new(0x18u);
        *v39 = 0;
        if ( v36 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v36 + 8LL))(v36);
          if ( *v39 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 16LL))(*v39);
          *v39 = v36;
        }
        *((_DWORD *)v39 + 2) = v51;
        v39[2] = v55;
        v19 = *((_QWORD *)&v71 + 1);
        ATL::CAtlList<_WMCResElement const *,ATL::CElementTraits<_WMCResElement const *>>::GetFreeNode(&v71);
        v22 = (_QWORD *)*((_QWORD *)&v73 + 1);
        v23 = **((_QWORD **)&v73 + 1);
        *(_QWORD *)(*((_QWORD *)&v73 + 1) + 16LL) = v39;
        *((_QWORD *)&v73 + 1) = v23;
        v22[1] = v19;
        *v22 = 0;
        ++v72;
        if ( *((_QWORD *)&v71 + 1) )
          **((_QWORD **)&v71 + 1) = v22;
        else
          *(_QWORD *)&v71 = v22;
        *((_QWORD *)&v71 + 1) = v22;
        if ( v33 )
        {
          v24 = v55;
          v25 = v51;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_dqqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, v21, v51, v55, &v63, &v56);
          }
          v56 = 0;
          CDidlLiteObjectWriter::AddResElementsIfNotDuplicate(v25, v24, &v63);
          for ( i = (__int64 *)v63; ; i = (__int64 *)*i )
          {
            if ( !i )
              goto LABEL_37;
            v28 = i[2];
            if ( *(_DWORD *)(v28 + 88) )
            {
              v29 = *(const WCHAR **)(v28 + 40);
              v30 = -1;
              do
                ++v30;
              while ( v29[v30] );
              if ( v30 > 4 && CompareStringW(0x7Fu, 0, v29, 4, L"http", 4) == 2 )
                break;
            }
          }
          v56 = v28;
          if ( i == (__int64 *)v63 )
            *(_QWORD *)&v63 = *i;
          else
            *(_QWORD *)i[1] = *i;
          if ( i == *((__int64 **)&v63 + 1) )
            *((_QWORD *)&v63 + 1) = i[1];
          else
            *(_QWORD *)(*i + 8) = i[1];
          *i = *((_QWORD *)&v65 + 1);
          *((_QWORD *)&v65 + 1) = i;
          v31 = --v64;
          if ( !v64 )
          {
            ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(&v63);
LABEL_37:
            v31 = v64;
          }
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              79,
              &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
              v56,
              v31);
          }
        }
        else
        {
          CDidlLiteObjectWriter::AddResElementsIfNotDuplicate(v51, v55, &v77);
        }
      }
      v33 = 0;
      if ( v36 )
        (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
      v34 = v56;
    }
    v40 = v62;
    v15 = lpString1;
    v5 = v75;
    v41 = v53;
    if ( v34 )
    {
      v52 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64, __int64))(*(_QWORD *)v75 + 64LL))(v75, v53, v34, v58);
      if ( v52 >= 0 )
        ++v11;
    }
    v42 = (_QWORD *)v63;
    if ( (_QWORD)v63 )
    {
      do
      {
        if ( !v42 )
          ATL::AtlThrowImpl(-2147467259);
        v54 = (_QWORD *)*v42;
        v43 = v54;
        v52 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int64))(*(_QWORD *)v5 + 64LL))(
                v5,
                v41,
                v42[2],
                v58);
        v42 = v43;
        v44 = v11 + 1;
        v32 = 0;
        if ( v52 < 0 )
          v44 = v11;
        v11 = v44;
      }
      while ( v43 );
    }
    v14 = v76;
    v54 = (_QWORD *)v77;
    if ( (_QWORD)v77 )
    {
      v47 = v53;
      v48 = v58;
      do
      {
        Next = (_QWORD *)ATL::CAtlList<CDidlLiteObjectWriter::CdsAttribute *,ATL::CElementTraits<CDidlLiteObjectWriter::CdsAttribute *>>::GetNext(
                           v32,
                           &v54);
        v52 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int64))(*(_QWORD *)v5 + 64LL))(
                v5,
                v47,
                *Next,
                v48);
        v50 = v11 + 1;
        if ( v52 < 0 )
          v50 = v11;
        v11 = v50;
      }
      while ( v54 );
      v40 = v62;
      v15 = lpString1;
    }
    while ( v72 )
    {
      v45 = (__int64 *)ATL::CAtlList<ResElementStorage *,ATL::CElementTraits<ResElementStorage *>>::RemoveHead(&v71);
      v46 = (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*v45 + 80LL))(
              *v45,
              *((unsigned int *)v45 + 2),
              v45[2]);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)((((int)v46 >> 31) & 0xFFFFFFFD) + 5) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_dbb15cfc8a373ec782525eb0398c9c07_Traceguids, v46);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v45);
      operator delete(v45);
    }
    ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(&v71);
    ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(&v77);
    ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(&v63);
    ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
    v10 = v52;
  }
  if ( v11 )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    WMCResElementData = v60;
  }
  else
  {
    WMCResElementData = v10;
    if ( v10 >= 0 )
      WMCResElementData = -2147024664;
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_87;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v13 = (const void ***)(((v10 >> 31) & 0xFFFFFFFD) + 5);
      if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)v13 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_dbb15cfc8a373ec782525eb0398c9c07_Traceguids,
          (unsigned int)v10);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( WMCResElementData < 0 )
    {
LABEL_87:
      v6 = v59;
      goto LABEL_9;
    }
  }
  v6 = v59;
  if ( (*(_BYTE *)v59 & 8) == 0 )
  {
    if ( CompareStringOrdinal(v15, 6, L"video/", -1, 1) == 2 )
    {
      v17 = v53;
      CdsObjectWriter::ActuallyWriteAlbumArtURIsAsResElement(v5, v53, v58);
      v16 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_10;
    }
    goto LABEL_8;
  }
LABEL_9:
  v17 = v53;
LABEL_10:
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
  {
    v13 = (const void ***)(((WMCResElementData >> 31) & 0xFFFFFFFD) + 5);
    if ( *((unsigned __int8 *)v16 + 25) >= (int)v13 )
      WPP_SF_dS(
        (unsigned int)v16[2],
        22,
        (unsigned int)&WPP_dbb15cfc8a373ec782525eb0398c9c07_Traceguids,
        WMCResElementData,
        *v17 + 2LL * v61);
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0qq_EventWriteTransfer(
      v13,
      CDS_Objwriter_Act_Write_Res_Element_Stop,
      *v6,
      (unsigned int)WMCResElementData);
  ATL::CStringData::Release((ATL::CStringData *)(v67 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v68 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v69 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v70 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 12));
  VariantClear(&pvarg);
  return (unsigned int)WMCResElementData;
}

```

## disassembly

```asm
0x14001f110  mov     [rsp-8+arg_18], rbx
0x14001f115  push    rbp
0x14001f116  push    rsi
0x14001f117  push    rdi
0x14001f118  push    r12
0x14001f11a  push    r13
0x14001f11c  push    r14
0x14001f11e  push    r15
0x14001f120  lea     rbp, [rsp-110h]
0x14001f128  sub     rsp, 210h
0x14001f12f  mov     rax, cs:__security_cookie
0x14001f136  xor     rax, rsp
0x14001f139  mov     [rbp+140h+var_40], rax
0x14001f140  mov     rdi, r8
0x14001f143  mov     [rsp+240h+var_1D0], r8
0x14001f148  mov     rbx, rdx
0x14001f14b  mov     [rsp+240h+var_1F8], rdx
0x14001f150  mov     r12, rcx
0x14001f153  mov     [rbp+140h+var_130], rcx
0x14001f157  lea     rsi, [rcx+28h]
0x14001f15b  mov     [rsp+240h+var_1C8], rsi
0x14001f160  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14001f167  jnz     loc_14001F876
0x14001f16d  mov     [rsp+240h+var_1C8], rsi
0x14001f172  mov     rdx, [rbx]
0x14001f175  mov     ecx, [rdx-10h]
0x14001f178  lea     r8d, [rcx-0Ah]
0x14001f17c  xor     r14d, r14d
0x14001f17f  cmp     ecx, 0Ah
0x14001f182  cmovbe  r8d, r14d
0x14001f186  mov     [rbp+140h+var_1BC], r8d
0x14001f18a  lea     rax, WPP_GLOBAL_Control
0x14001f191  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f198  cmp     rcx, rax
0x14001f19b  jz      short loc_14001F1A7
0x14001f19d  test    byte ptr [rcx+1Ch], 1
0x14001f1a1  jnz     loc_14001F88D
0x14001f1a7  mov     eax, 13h
0x14001f1ac  mov     word ptr [rbp+140h+pvarg], ax
0x14001f1b0  mov     ecx, [rdi+8]
0x14001f1b3  call    ?GetElementTypeForAtom@CdsValues@@SA?AW4CDS_ELEMENT_VALUE@@W4Value@CdsValue@@@Z; CdsValues::GetElementTypeForAtom(CdsValue::Value)
0x14001f1b8  mov     dword ptr [rbp+140h+pvarg+8], eax
0x14001f1bb  xor     edx, edx; Val
0x14001f1bd  mov     r8d, 90h; Size
0x14001f1c3  lea     rcx, [rbp+140h+var_D0]; void *
0x14001f1c7  call    memset_0
0x14001f1cc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f1d3  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f1da  mov     rcx, rbx
0x14001f1dd  mov     rax, [rax+18h]
0x14001f1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f1e6  add     rax, 18h
0x14001f1ea  mov     [rsp+240h+lpString1], rax
0x14001f1ef  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f1f6  mov     rcx, rbx
0x14001f1f9  mov     rax, [rax+18h]
0x14001f1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f202  add     rax, 18h
0x14001f206  mov     [rbp+140h+var_168], rax
0x14001f20a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f211  mov     rcx, rbx
0x14001f214  mov     rax, [rax+18h]
0x14001f218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f21d  add     rax, 18h
0x14001f221  mov     [rbp+140h+var_170], rax
0x14001f225  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f22c  mov     rcx, rbx
0x14001f22f  mov     rax, [rax+18h]
0x14001f233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f238  add     rax, 18h
0x14001f23c  mov     [rbp+140h+var_178], rax
0x14001f240  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f247  mov     rcx, rbx
0x14001f24a  mov     rax, [rax+18h]
0x14001f24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f253  add     rax, 18h
0x14001f257  mov     [rbp+140h+var_180], rax
0x14001f25b  mov     r13d, r14d
0x14001f25e  mov     [rsp+240h+var_1FC], r14d
0x14001f263  lea     rax, [rbp+140h+var_D0]
0x14001f267  mov     [rsp+240h+var_208], rax; __int64
0x14001f26c  lea     rax, [rbp+140h+var_180]
0x14001f270  mov     [rsp+240h+var_210], rax; __int64
0x14001f275  lea     rax, [rbp+140h+var_178]
0x14001f279  mov     qword ptr [rsp+240h+cchCount2], rax; __int64
0x14001f27e  lea     rax, [rbp+140h+var_170]
0x14001f282  mov     [rsp+240h+lpString2], rax; __int64
0x14001f287  lea     r9, [rbp+140h+var_168]
0x14001f28b  lea     r8, [rsp+240h+lpString1]
0x14001f290  mov     rcx, [r12+8]; this
0x14001f295  call    ?GetWMCResElementData@CdsItemInfoBase@@QEAAJ_NAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@1111AEAU_WMCResElementParams@@@Z; CdsItemInfoBase::GetWMCResElementData(bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,_WMCResElementParams &)
0x14001f29a  mov     ebx, eax
0x14001f29c  mov     [rbp+140h+var_1C0], eax
0x14001f29f  mov     ecx, [rsi]
0x14001f2a1  mov     [rbp+140h+var_50], ecx
0x14001f2a7  mov     rcx, [r12+20h]
0x14001f2ac  mov     r15, [rcx]
0x14001f2af  mov     rdi, [rsp+240h+lpString1]
0x14001f2b4  test    eax, eax
0x14001f2b6  jns     loc_14001F8BA
0x14001f2bc  mov     r10, cs:WPP_GLOBAL_Control
0x14001f2c3  mov     r14, [rsp+240h+var_1F8]
0x14001f2c8  lea     rax, WPP_GLOBAL_Control
0x14001f2cf  cmp     r10, rax
0x14001f2d2  jz      short loc_14001F2DF
0x14001f2d4  test    byte ptr [r10+1Ch], 1
0x14001f2d9  jnz     loc_14001FA7F
0x14001f2df  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14001f2e6  jnz     loc_14001FAC3
0x14001f2ec  mov     rcx, [rbp+140h+var_180]
0x14001f2f0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f2f4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f2f9  nop
0x14001f2fa  mov     rcx, [rbp+140h+var_178]
0x14001f2fe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f302  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f307  nop
0x14001f308  mov     rcx, [rbp+140h+var_170]
0x14001f30c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f310  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f315  nop
0x14001f316  mov     rcx, [rbp+140h+var_168]
0x14001f31a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f31e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f323  nop
0x14001f324  lea     rcx, [rdi-18h]; this
0x14001f328  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f32d  nop
0x14001f32e  lea     rcx, [rbp+140h+pvarg]; pvarg
0x14001f332  call    cs:__imp_VariantClear
0x14001f338  mov     eax, ebx
0x14001f33a  mov     rcx, [rbp+140h+var_40]
0x14001f341  xor     rcx, rsp; StackCookie
0x14001f344  call    __security_check_cookie
0x14001f349  mov     rbx, [rsp+240h+arg_18]
0x14001f351  add     rsp, 210h
0x14001f358  pop     r15
0x14001f35a  pop     r14
0x14001f35c  pop     r13
0x14001f35e  pop     r12
0x14001f360  pop     rdi
0x14001f361  pop     rsi
0x14001f362  pop     rbp
0x14001f363  retn
0x14001f364  mov     rcx, [r14]
0x14001f367  mov     rax, [rcx+8]
0x14001f36b  mov     rcx, r14
0x14001f36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f373  mov     rcx, [r15]
0x14001f376  test    rcx, rcx
0x14001f379  jnz     loc_14001F943
0x14001f37f  mov     [r15], r14
0x14001f382  mov     eax, [rsp+240h+var_200]
0x14001f386  mov     [r15+8], eax
0x14001f38a  mov     rax, [rsp+240h+var_1E8]
0x14001f38f  mov     [r15+10h], rax
0x14001f393  mov     rsi, qword ptr [rbp+140h+var_160+8]
0x14001f397  lea     rcx, [rbp+140h+var_160]
0x14001f39b  call    ?GetFreeNode@?$CAtlList@PEBU_WMCResElement@@V?$CElementTraits@PEBU_WMCResElement@@@ATL@@@ATL@@AEAAXXZ; ATL::CAtlList<_WMCResElement const *,ATL::CElementTraits<_WMCResElement const *>>::GetFreeNode(void)
0x14001f3a0  mov     rcx, [rbp+140h+var_140]
0x14001f3a4  mov     rax, [rcx]
0x14001f3a7  mov     [rcx+10h], r15
0x14001f3ab  mov     [rbp+140h+var_140], rax
0x14001f3af  mov     [rcx+8], rsi
0x14001f3b3  xor     esi, esi
0x14001f3b5  mov     [rcx], rsi
0x14001f3b8  inc     [rbp+140h+var_150]
0x14001f3bc  mov     rax, qword ptr [rbp+140h+var_160+8]
0x14001f3c0  test    rax, rax
0x14001f3c3  jnz     loc_14001F954
0x14001f3c9  mov     qword ptr [rbp+140h+var_160], rcx
0x14001f3cd  mov     qword ptr [rbp+140h+var_160+8], rcx
0x14001f3d1  test    edi, edi
0x14001f3d3  jz      loc_14001F98F
0x14001f3d9  mov     rsi, [rsp+240h+var_1E8]
0x14001f3de  mov     r15d, [rsp+240h+var_200]
0x14001f3e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f3ea  cmp     rcx, r12
0x14001f3ed  jz      short loc_14001F3F9
0x14001f3ef  test    byte ptr [rcx+1Ch], 2
0x14001f3f3  jnz     loc_14001F95C
0x14001f3f9  xor     edi, edi
0x14001f3fb  mov     [rsp+240h+var_1E0], rdi
0x14001f400  lea     r8, [rbp+140h+var_1B0]
0x14001f404  mov     rdx, rsi
0x14001f407  mov     ecx, r15d
0x14001f40a  call    ?AddResElementsIfNotDuplicate@CDidlLiteObjectWriter@@KAXJPEBU_WMCResElement@@AEAV?$CAtlList@PEBU_WMCResElement@@V?$CElementTraits@PEBU_WMCResElement@@@ATL@@@ATL@@@Z; CDidlLiteObjectWriter::AddResElementsIfNotDuplicate(long,_WMCResElement const *,ATL::CAtlList<_WMCResElement const *,ATL::CElementTraits<_WMCResElement const *>> &)
0x14001f40f  mov     rsi, qword ptr [rbp+140h+var_1B0]
0x14001f413  test    rsi, rsi
0x14001f416  jz      loc_14001F4B5
0x14001f41c  mov     r15, [rsi+10h]
0x14001f420  cmp     [r15+58h], edi
0x14001f424  jz      short loc_14001F43E
0x14001f426  mov     r8, [r15+28h]; lpString1
0x14001f42a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001f42e  inc     rax
0x14001f431  cmp     [r8+rax*2], di
0x14001f436  jnz     short loc_14001F42E
0x14001f438  cmp     rax, 4
0x14001f43c  ja      short loc_14001F443
0x14001f43e  mov     rsi, [rsi]
0x14001f441  jmp     short loc_14001F413
0x14001f443  mov     [rsp+240h+cchCount2], 4; cchCount2
0x14001f44b  lea     rax, aHttp_2; "http"
0x14001f452  mov     [rsp+240h+lpString2], rax; lpString2
0x14001f457  xor     edx, edx; dwCmpFlags
0x14001f459  lea     ecx, [rdx+7Fh]; Locale
0x14001f45c  lea     r9d, [rdx+4]; cchCount1
0x14001f460  call    cs:__imp_CompareStringW
0x14001f466  cmp     eax, 2
0x14001f469  jnz     short loc_14001F43E
0x14001f46b  mov     [rsp+240h+var_1E0], r15
0x14001f470  mov     rcx, [rsi]
0x14001f473  cmp     rsi, qword ptr [rbp+140h+var_1B0]
0x14001f477  jnz     loc_14001F62F
0x14001f47d  mov     qword ptr [rbp+140h+var_1B0], rcx
0x14001f481  mov     rcx, [rsi+8]
0x14001f485  cmp     rsi, qword ptr [rbp+140h+var_1B0+8]
0x14001f489  jnz     loc_14001F63B
0x14001f48f  mov     qword ptr [rbp+140h+var_1B0+8], rcx
0x14001f493  mov     rax, [rbp+140h+var_190]
0x14001f497  mov     [rsi], rax
0x14001f49a  mov     [rbp+140h+var_190], rsi
0x14001f49e  mov     rax, [rbp+140h+var_1A0]
0x14001f4a2  sub     rax, 1
0x14001f4a6  mov     [rbp+140h+var_1A0], rax
0x14001f4aa  jnz     short loc_14001F4B9
0x14001f4ac  lea     rcx, [rbp+140h+var_1B0]
0x14001f4b0  call    ?RemoveAll@?$CAtlList@Usockaddr_storage@@V?$CElementTraits@Usockaddr_storage@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(void)
0x14001f4b5  mov     rax, [rbp+140h+var_1A0]
0x14001f4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f4c0  cmp     rcx, r12
0x14001f4c3  jnz     loc_14001F647
0x14001f4c9  xor     esi, esi
0x14001f4cb  mov     edi, esi
0x14001f4cd  test    r14, r14
0x14001f4d0  jz      short loc_14001F4E2
0x14001f4d2  mov     rax, [r14]
0x14001f4d5  mov     rcx, r14
0x14001f4d8  mov     rax, [rax+10h]
0x14001f4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f4e1  nop
0x14001f4e2  mov     r8, [rsp+240h+var_1E0]
0x14001f4e7  jmp     loc_14001F581
0x14001f4ec  mov     [rsp+240h+var_200], esi
0x14001f4f0  mov     [rsp+240h+var_1E8], rsi
0x14001f4f5  mov     rax, [r15]
0x14001f4f8  mov     [rbp+140h+var_128], rax
0x14001f4fc  lea     rdx, [r15+10h]
0x14001f500  lea     rcx, [rbp+140h+var_1B8]
0x14001f504  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14001f509  nop
0x14001f50a  mov     r8, rsi
0x14001f50d  mov     [rsp+240h+var_1E0], rsi
0x14001f512  xorps   xmm0, xmm0
0x14001f515  movdqu  [rbp+140h+var_1B0], xmm0
0x14001f51a  mov     [rbp+140h+var_1A0], rsi
0x14001f51e  xorps   xmm1, xmm1
0x14001f521  movdqu  xmmword ptr [rbp-58h], xmm1
0x14001f526  mov     eax, 0Ah
0x14001f52b  mov     [rbp+140h+var_188], eax
0x14001f52e  movdqu  [rbp+140h+var_120], xmm0
0x14001f533  mov     [rbp+140h+var_110], rsi
0x14001f537  movdqu  [rbp+140h+var_108], xmm1
0x14001f53c  mov     [rbp+140h+var_F8], eax
0x14001f53f  movdqu  [rbp+140h+var_160], xmm0
0x14001f544  mov     [rbp+140h+var_150], rsi
0x14001f548  movdqu  xmmword ptr [rbp-8], xmm1
0x14001f54d  mov     [rbp+140h+var_138], eax
0x14001f550  mov     dword ptr [rsp+240h+var_1F0], 1
0x14001f558  mov     rbx, [rbp+140h+var_1B8]
0x14001f55c  mov     [rbp+140h+var_C0], rbx
0x14001f563  mov     eax, [r12+10h]
0x14001f568  mov     [rbp+140h+var_4C], eax
0x14001f56e  mov     rax, [r12+38h]
0x14001f573  mov     rbx, [rax]
0x14001f576  mov     edi, dword ptr [rsp+240h+var_1F0]
0x14001f57a  lea     r12, WPP_GLOBAL_Control
0x14001f581  test    rbx, rbx
0x14001f584  jz      loc_14001F67F
0x14001f58a  mov     r14, [rbx+10h]
0x14001f58e  mov     rbx, [rbx]
0x14001f591  mov     [rsp+240h+var_1F0], r14
0x14001f596  test    r14, r14
0x14001f599  jz      short loc_14001F5AB
0x14001f59b  mov     rax, [r14]
0x14001f59e  mov     rcx, r14
0x14001f5a1  mov     rax, [rax+8]
0x14001f5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5aa  nop
0x14001f5ab  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14001f5b2  jnz     loc_14001F8C1
0x14001f5b8  mov     rax, [r14]
0x14001f5bb  lea     r9, [rsp+240h+var_1E8]
0x14001f5c0  lea     r8, [rsp+240h+var_200]
0x14001f5c5  lea     rdx, [rbp+140h+var_D0]
0x14001f5c9  mov     rcx, r14
0x14001f5cc  mov     rax, [rax+40h]
0x14001f5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5d5  mov     esi, eax
  ... truncated ...
```
