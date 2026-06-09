# CMDEContentServer::GetResElements(_WMCResElementParams *,long *,_WMCResElement * *)

- ea: `0x14001c430`
- end: `0x14001d010`
- name: `?GetResElements@CMDEContentServer@@UEAAJPEAU_WMCResElementParams@@PEAJPEAPEAU_WMCResElement@@@Z`
- size: `3040`
- prototype: `__int64 __fastcall(CMDEContentServer *__hidden this, struct _WMCResElementParams *, int *, struct _WMCResElement **)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140005b38`
- `0x1400065e0`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c920`
- `0x14000c94c`
- `0x140014f90`
- `0x140015230`
- `0x14001a1c0`
- `0x14001b560`
- `0x14001bef0`
- `0x14001c430`
- `0x14001d020`
- `0x14001e384`
- `0x14001e3ec`
- `0x14001e46c`
- `0x1400396dc`
- `0x14003b2b8`
- `0x14003d3f8`
- `0x140045f20`
- `0x140046020`
- `0x14004639c`
- `0x140046c32`
- `0x1400547b0`
- `0x140057bc4`
- `0x140090d94`
- `0x14009ad1c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14001c491`
- `KERNEL32!EnterCriticalSection` at `0x14001c491`
- `KERNEL32!LeaveCriticalSection` at `0x14001c5b8`
- `KERNEL32!LeaveCriticalSection` at `0x14001c5b8`
- `KERNEL32!CompareStringW` at `0x14001cde1`
- `KERNEL32!CompareStringW` at `0x14001cde1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c646`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c9f4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001cb19`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c646`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c9f4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001cb19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d005`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d005`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c60c`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c616`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c620`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c62a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c60c`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c616`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c620`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c62a`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::GetResElements(
        CMDEContentServer *this,
        struct _WMCResElementParams *a2,
        int *a3,
        struct _WMCResElement **a4)
{
  struct _WMCResElement **v4; // rdi
  int *v5; // r13
  struct _WMCResElementParams *v6; // rbx
  CMDEContentServer *v7; // rsi
  PVOID *v8; // rax
  unsigned __int64 v9; // rcx
  unsigned int v10; // r15d
  int TranscodingResElements; // r14d
  MDEProfile *v12; // rax
  unsigned int v13; // edx
  BSTR *v15; // rbx
  CMDEContentServer *v16; // rdx
  volatile signed __int32 *v17; // rsi
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rbx
  unsigned int *v22; // r13
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 **v25; // rax
  __int64 *v26; // rdi
  __int64 *v27; // r15
  const struct MDEProfile *v28; // r12
  struct _WMCResElement *v29; // rsi
  int v30; // edi
  _QWORD *v31; // rcx
  __int64 v32; // rax
  _OWORD *v33; // rbx
  bool v34; // zf
  __int64 v35; // rax
  __int64 v36; // rcx
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int64 (__fastcall *v39)(void ***); // rax
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int64 v46; // r12
  __int64 v47; // rax
  char *v48; // rdx
  __int64 v49; // r8
  int v50; // ecx
  unsigned __int64 v51; // r13
  unsigned __int64 v52; // rsi
  int v53; // eax
  __int64 v54; // rcx
  int *v55; // rsi
  unsigned __int64 v56; // r13
  int v57; // eax
  unsigned __int64 v58; // rsi
  __int64 v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rsi
  _QWORD *v62; // rcx
  __int64 v63; // rax
  ATL::CStringData *v64; // rcx
  __int64 v65; // rbx
  _QWORD *v66; // rax
  __int64 v67; // rax
  __int128 *v68; // rax
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // r9
  __int64 v72; // r10
  __int64 v73; // r11
  __int128 v74; // xmm1
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int128 v79; // xmm0
  __int128 v80; // xmm1
  __int128 v81; // xmm0
  const WCHAR *v82; // rcx
  struct _WMCResElement *v83; // rcx
  int v84; // eax
  void *v85; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+68h] [rbp-98h] BYREF
  CMDEContentServer *v87; // [rsp+70h] [rbp-90h]
  struct _WMCResElementParams *v88; // [rsp+78h] [rbp-88h] BYREF
  __int64 v89; // [rsp+80h] [rbp-80h] BYREF
  int *v90; // [rsp+88h] [rbp-78h]
  struct _WMCResElement **v91; // [rsp+90h] [rbp-70h]
  const struct MDEProfile *v92; // [rsp+98h] [rbp-68h]
  __int128 v93; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v94; // [rsp+B0h] [rbp-50h]
  __int128 v95; // [rsp+B8h] [rbp-48h]
  int v96; // [rsp+C8h] [rbp-38h]
  ATL::CStringData *v97; // [rsp+D0h] [rbp-30h]
  char *v98; // [rsp+D8h] [rbp-28h]
  __int128 v99; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v100; // [rsp+F0h] [rbp-10h]
  __int128 v101; // [rsp+F8h] [rbp-8h]
  int v102; // [rsp+108h] [rbp+8h]
  _QWORD v103[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v104; // [rsp+120h] [rbp+20h]
  __int64 v105; // [rsp+130h] [rbp+30h]
  void *Block; // [rsp+138h] [rbp+38h]
  _OWORD v107[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v108; // [rsp+160h] [rbp+60h]
  __int128 v109; // [rsp+170h] [rbp+70h]
  __int128 v110; // [rsp+180h] [rbp+80h]
  __int128 v111; // [rsp+190h] [rbp+90h]
  __int128 v112; // [rsp+1A0h] [rbp+A0h]
  __int128 v113; // [rsp+1B0h] [rbp+B0h]
  __int128 v114; // [rsp+1C0h] [rbp+C0h]
  _OWORD v115[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v116; // [rsp+1F0h] [rbp+F0h]
  __int128 v117; // [rsp+200h] [rbp+100h]
  __int128 v118; // [rsp+210h] [rbp+110h]
  __int128 v119; // [rsp+220h] [rbp+120h]
  __int128 v120; // [rsp+230h] [rbp+130h]
  __int128 v121; // [rsp+240h] [rbp+140h]
  __int128 v122; // [rsp+250h] [rbp+150h]

  v91 = a4;
  v4 = a4;
  v90 = a3;
  v5 = a3;
  v88 = a2;
  v6 = a2;
  v87 = this;
  v7 = this;
  if ( this )
  {
    v98 = (char *)this + 8;
    if ( this != (CMDEContentServer *)-8LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
  else
  {
    v98 = 0;
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0qq_EventWriteTransfer(this, MDE_Generate_Res_Element_Start, 0, 0);
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    if ( v6 )
    {
      v69 = *((_QWORD *)v6 + 5);
      v70 = *((_QWORD *)v6 + 4);
      v71 = *((_QWORD *)v6 + 3);
      v72 = *((_QWORD *)v6 + 2);
      v73 = *(_QWORD *)v6;
    }
    else
    {
      v69 = 0;
      v70 = 0;
      v71 = 0;
      v72 = 0;
      v73 = 0;
    }
    WPP_SF_qSSSSSqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v73, v72, v71, v70, v69, (char)v5, (char)v4);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = 0;
  v94 = 0;
  v96 = 10;
  v10 = -1;
  v100 = 0;
  v102 = 10;
  v103[0] = 0;
  v103[1] = 0;
  v105 = 10;
  Block = 0;
  v93 = 0;
  v95 = 0;
  v99 = 0;
  v101 = 0;
  v104 = 0;
  if ( v6 && v5 && v4 )
  {
    *v5 = 0;
    *v4 = 0;
    if ( !*((_QWORD *)v7 + 15) )
    {
      TranscodingResElements = -2147467259;
      goto LABEL_9;
    }
    TranscodingResElements = CMDEContentServer::CustomizeMDEProfiles(v7, v6);
    if ( TranscodingResElements < 0 )
      goto LABEL_130;
    v28 = 0;
    v68 = (__int128 *)((char *)v7 + 152);
    v92 = 0;
    v97 = (CMDEContentServer *)((char *)v7 + 200);
    if ( v100 )
    {
      v97 = (ATL::CStringData *)v103;
      v68 = &v99;
    }
    v25 = *(__int64 ***)v68;
    if ( v25 )
    {
      while ( 1 )
      {
        if ( TranscodingResElements < 0 )
        {
          v5 = v90;
          goto LABEL_130;
        }
        v26 = v25[2];
        v27 = *v25;
        if ( *((_DWORD *)v26 + 19)
          || !(unsigned int)CMDEContentServer::CanUseMDEProfile(v7, v6, (const struct MDEProfile *)v25[2]) )
        {
          goto LABEL_48;
        }
        v37 = *((_OWORD *)v6 + 1);
        v107[0] = *(_OWORD *)v6;
        v38 = *((_OWORD *)v6 + 2);
        v39 = (__int64 (__fastcall *)(void ***))ATL::g_strmgr[3];
        v107[1] = v37;
        v40 = *((_OWORD *)v6 + 3);
        v108 = v38;
        v41 = *((_OWORD *)v6 + 4);
        v109 = v40;
        v42 = *((_OWORD *)v6 + 5);
        v110 = v41;
        v43 = *((_OWORD *)v6 + 6);
        v111 = v42;
        v44 = *((_OWORD *)v6 + 7);
        v112 = v43;
        v45 = *((_OWORD *)v6 + 8);
        v113 = v44;
        v114 = v45;
        v46 = v39(&ATL::g_strmgr) + 24;
        v89 = v46;
        v22 = (unsigned int *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        v85 = v22;
        v47 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
        v50 = *((_DWORD *)v26 + 14);
        v21 = v47 + 24;
        v86 = v47 + 24;
        if ( !v50 )
          break;
        if ( v50 != 1 )
          goto LABEL_32;
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v89, L"rtsp", 4);
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v85, L"rtsp-rtp-udp", 12);
        v60 = *((_QWORD *)v7 + 51);
        v61 = v21 - 24;
        v62 = (_QWORD *)(v60 - 24);
        if ( v60 - 24 != v21 - 24 )
        {
          if ( *(int *)(v61 + 16) < 0 || *v62 != *(_QWORD *)v61 )
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v86, v60, *(unsigned int *)(v60 - 16));
            v46 = v89;
LABEL_113:
            v21 = v86;
            goto LABEL_31;
          }
          v63 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v62);
          v64 = (ATL::CStringData *)(v21 - 24);
          v65 = v63;
          ATL::CStringData::Release(v64);
          v21 = v65 + 24;
        }
        v46 = v89;
LABEL_31:
        v22 = (unsigned int *)v85;
        v7 = v87;
LABEL_32:
        *(_QWORD *)&v108 = 0;
        v23 = *((_QWORD *)v88 + 4);
        if ( !v23 )
          goto LABEL_148;
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)(v23 + 2 * v24) );
        if ( !v24 )
        {
LABEL_148:
          if ( *((_DWORD *)v26 + 16) || *((_DWORD *)v26 + 15) )
            goto LABEL_37;
          goto LABEL_90;
        }
        if ( !*((_DWORD *)v26 + 16) )
        {
          if ( !*((_DWORD *)v26 + 15)
            && !*((_DWORD *)v26 + 5)
            && !*((_DWORD *)v26 + 14)
            && (CompareStringW(0x7Fu, 1u, (PCNZWCH)v26[4], -1, L"application/octet-stream", -1) == 2
             || !*(_DWORD *)(v26[4] - 16)) )
          {
            v92 = (const struct MDEProfile *)v26;
          }
          goto LABEL_37;
        }
        if ( (*((_BYTE *)v88 + 128) & 0x20) == 0 )
        {
          *(_QWORD *)&v108 = L"Microsoft WM DRM";
LABEL_90:
          v67 = *((_QWORD *)v7 + 52);
          if ( *((_DWORD *)v26 + 5) )
            TranscodingResElements = CMDEContentServer::GenerateTranscodingResElements(
                                       (__int64)v7,
                                       (__int64)v107,
                                       v97,
                                       v26,
                                       v46,
                                       v21,
                                       v67,
                                       (__int64)v22,
                                       (__int64)&v93);
          else
            TranscodingResElements = CMDEContentServer::GenerateNonTranscodingResElements(
                                       (const WCHAR *)&v93,
                                       (__int64)v107,
                                       (const struct MDEProfile *)v26,
                                       v46,
                                       v21,
                                       v67,
                                       (__int64)v22,
                                       0,
                                       (__int64)&v93);
        }
LABEL_37:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v21 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v21 - 24) + 8LL))(*(_QWORD *)(v21 - 24));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v46 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v46 - 24) + 8LL))(*(_QWORD *)(v46 - 24));
        v6 = v88;
LABEL_48:
        v25 = (__int64 **)v27;
        if ( !v27 )
        {
          v5 = v90;
          if ( TranscodingResElements >= 0 )
          {
            v28 = v92;
            v10 = -1;
            v4 = v91;
            goto LABEL_51;
          }
LABEL_130:
          v4 = v91;
          v10 = -1;
          goto LABEL_22;
        }
      }
      v51 = *(v22 - 4);
      v52 = (L"http-get" - (_BYTE *)v85) >> 1;
      v53 = *((_DWORD *)v85 - 3) - 8;
      v54 = v53 | (unsigned int)(1 - *((_DWORD *)v85 - 2));
      if ( (v53 | (1 - *((_DWORD *)v85 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v85, 8);
      if ( v52 <= v51 )
      {
        if ( v85 && (v48 = (char *)v85 + 2 * v52) != 0 )
        {
          memmove_0(v85, v48, 0x10u);
          v55 = (int *)v85;
        }
        else
        {
          *(_DWORD *)_o__errno(v54, v48, v49) = 22;
          invalid_parameter_noinfo();
          v55 = (int *)v85;
        }
      }
      else
      {
        v55 = (int *)v85;
        if ( v85 )
        {
          *(_OWORD *)v85 = *(_OWORD *)L"http-get";
        }
        else
        {
          *(_DWORD *)_o__errno(v54, v48, v49) = 22;
          invalid_parameter_noinfo();
        }
      }
      if ( *(v55 - 3) < 8 )
LABEL_123:
        ATL::AtlThrowImpl(-2147024809);
      *(v55 - 4) = 8;
      *((_WORD *)v55 + 8) = 0;
      v56 = *(unsigned int *)(v46 - 16);
      v57 = *(_DWORD *)(v46 - 12) - 4;
      v58 = ((__int64)L"http" - v46) >> 1;
      v59 = v57 | (unsigned int)(1 - *(_DWORD *)(v46 - 8));
      if ( (v57 | (1 - *(_DWORD *)(v46 - 8))) < 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v89, 4);
        v46 = v89;
      }
      if ( v58 <= v56 )
      {
        if ( v46 )
        {
          v66 = (_QWORD *)(v46 + 2 * v58);
          if ( v66 )
          {
            *(_QWORD *)v46 = *v66;
            goto LABEL_24;
          }
        }
      }
      else if ( v46 )
      {
        *(_QWORD *)v46 = *(_QWORD *)L"http";
        goto LABEL_24;
      }
      *(_DWORD *)_o__errno(v59, v48, v49) = 22;
      invalid_parameter_noinfo();
LABEL_24:
      if ( *(int *)(v46 - 12) < 4 )
        goto LABEL_123;
      v16 = v87;
      v17 = (volatile signed __int32 *)(v21 - 24);
      *(_DWORD *)(v46 - 16) = 4;
      *(_WORD *)(v46 + 8) = 0;
      v18 = *((_QWORD *)v16 + 50);
      v19 = (_QWORD *)(v18 - 24);
      if ( v18 - 24 == v21 - 24 )
        goto LABEL_31;
      if ( *((int *)v17 + 4) >= 0 && *v19 == *(_QWORD *)v17 )
      {
        v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v19);
        if ( _InterlockedExchangeAdd(v17 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v17 + 8LL))(*(_QWORD *)v17, v17);
        v21 = v20 + 24;
        goto LABEL_31;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v86, v18, *(unsigned int *)(v18 - 16));
      goto LABEL_113;
    }
LABEL_51:
    v9 = v94;
    if ( v94 )
    {
      if ( v94 > 0x7FFFFFFF )
      {
        TranscodingResElements = -2147024809;
        goto LABEL_9;
      }
    }
    else
    {
      if ( v28 )
      {
        v74 = *((_OWORD *)v6 + 1);
        v115[0] = *(_OWORD *)v6;
        v75 = *((_OWORD *)v6 + 2);
        v115[1] = v74;
        v76 = *((_OWORD *)v6 + 3);
        v116 = v75;
        v77 = *((_OWORD *)v6 + 4);
        v117 = v76;
        v78 = *((_OWORD *)v6 + 5);
        v118 = v77;
        v79 = *((_OWORD *)v6 + 6);
        v119 = v78;
        v80 = *((_OWORD *)v6 + 7);
        v120 = v79;
        v81 = *((_OWORD *)v6 + 8);
        v121 = v80;
        v122 = v81;
        *(_QWORD *)&v116 = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v86);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v88);
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v86, L"http");
        ATL::CSimpleStringT<unsigned short,0>::operator=(&v88, (_QWORD *)v7 + 50);
        TranscodingResElements = CMDEContentServer::GenerateNonTranscodingResElements(
                                   v82,
                                   (__int64)v115,
                                   v28,
                                   v86,
                                   (__int64)v88,
                                   *((_QWORD *)v7 + 52),
                                   (__int64)L"http-get",
                                   0,
                                   (__int64)&v93);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v88);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v86);
        if ( TranscodingResElements < 0 )
          goto LABEL_130;
        v9 = v94;
      }
      if ( !v9 )
      {
        TranscodingResElements = -2147024809;
        goto LABEL_9;
      }
    }
    v29 = (struct _WMCResElement *)operator new[](saturated_mul(v9, 0x60u));
    v30 = 0;
    while ( 1 )
    {
      v9 = v94;
      if ( !v94 )
        break;
      v31 = (_QWORD *)v93;
      if ( !(_QWORD)v93 )
        ATL::AtlThrowImpl(-2147467259);
      v32 = *(_QWORD *)v93;
      v33 = *(_OWORD **)(v93 + 16);
      *(_QWORD *)&v93 = v32;
      if ( v32 )
        *(_QWORD *)(v32 + 8) = 0;
      else
        v93 = 0u;
      *v31 = *((_QWORD *)&v95 + 1);
      v34 = v94-- == 1;
      *((_QWORD *)&v95 + 1) = v31;
      if ( v34 )
        ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(&v93);
      v35 = v30++;
      v36 = 96 * v35;
      *(_OWORD *)((char *)v29 + v36) = *v33;
      *(_OWORD *)((char *)v29 + v36 + 16) = v33[1];
      *(_OWORD *)((char *)v29 + v36 + 32) = v33[2];
      *(_OWORD *)((char *)v29 + v36 + 48) = v33[3];
      *(_OWORD *)((char *)v29 + v36 + 64) = v33[4];
      *(_OWORD *)((char *)v29 + v36 + 80) = v33[5];
      *(_QWORD *)v33 = 0;
      *((_QWORD *)v33 + 2) = 0;
      *((_QWORD *)v33 + 5) = 0;
      *((_QWORD *)v33 + 6) = 0;
      operator delete(v33);
    }
    *v5 = v30;
    v4 = v91;
    *v91 = v29;
  }
  else
  {
    TranscodingResElements = -2147024809;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_qqq(v8[2], 99, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, v6, v5, v4);
      goto LABEL_22;
    }
  }
LABEL_9:
  while ( v9 )
  {
    v15 = (BSTR *)ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>>::RemoveHead(&v93);
    SysFreeString(*v15);
    SysFreeString(v15[2]);
    SysFreeString(v15[5]);
    SysFreeString(v15[6]);
    operator delete(v15);
LABEL_22:
    v9 = v94;
  }
  while ( v100 )
  {
    v12 = (MDEProfile *)ATL::CAtlList<MDEProfile *,ATL::CElementTraits<MDEProfile *>>::RemoveHead(&v99);
    if ( v12 )
      MDEProfile::`scalar deleting destructor'(v12, v13);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = ((TranscodingResElements >> 31) & 0xFFFFFFFD) + 5;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)v9 )
    {
      if ( v4 )
        v83 = *v4;
      else
        v83 = 0;
      if ( v5 )
        v84 = *v5;
      else
        v84 = -1;
      WPP_SF_ddq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        100,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)TranscodingResElements,
        v84,
        v83);
    }
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
  {
    if ( v5 )
      v10 = *v5;
    McTemplateU0qq_EventWriteTransfer(v9, MDE_Generate_Res_Element_Stop, v10, (unsigned int)TranscodingResElements);
  }
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<MDEProfile const *>>::RemoveAll(v103);
  if ( Block )
    free(Block);
  ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(&v99);
  ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(&v93);
  if ( v98 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v98 + 8));
  return (unsigned int)TranscodingResElements;
}

```

## disassembly

```asm
0x14001c430  push    rbp
0x14001c432  push    rbx
0x14001c433  push    rsi
0x14001c434  push    rdi
0x14001c435  push    r13
0x14001c437  push    r15
0x14001c439  lea     rbp, [rsp-188h]
0x14001c441  sub     rsp, 288h
0x14001c448  mov     rax, cs:__security_cookie
0x14001c44f  xor     rax, rsp
0x14001c452  mov     [rbp+1B0h+var_50], rax
0x14001c459  mov     [rbp+1B0h+var_220], r9
0x14001c45d  mov     rdi, r9
0x14001c460  mov     [rbp+1B0h+var_228], r8
0x14001c464  mov     r13, r8
0x14001c467  mov     [rsp+2B0h+var_238], rdx
0x14001c46c  mov     rbx, rdx
0x14001c46f  mov     [rsp+2B0h+var_240], rcx
0x14001c474  mov     rsi, rcx
0x14001c477  test    rcx, rcx
0x14001c47a  jz      loc_14001C5F0
0x14001c480  lea     rax, [rcx+8]
0x14001c484  mov     [rbp+1B0h+var_1D8], rax
0x14001c488  test    rax, rax
0x14001c48b  jz      short loc_14001C497
0x14001c48d  lea     rcx, [rax+8]; lpCriticalSection
0x14001c491  call    cs:__imp_EnterCriticalSection
0x14001c497  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14001c49e  jnz     loc_14001CC8B
0x14001c4a4  mov     rax, cs:WPP_GLOBAL_Control
0x14001c4ab  lea     rdx, WPP_GLOBAL_Control
0x14001c4b2  cmp     rax, rdx
0x14001c4b5  jnz     loc_14001CCA2
0x14001c4bb  xor     ecx, ecx
0x14001c4bd  mov     [rsp+2B0h+var_30], r12
0x14001c4c5  mov     [rsp+2B0h+var_38], r14
0x14001c4cd  xorps   xmm0, xmm0
0x14001c4d0  mov     [rbp+1B0h+var_200], rcx
0x14001c4d4  xorps   xmm1, xmm1
0x14001c4d7  mov     [rbp+1B0h+var_1E8], 0Ah
0x14001c4de  mov     r15, 0FFFFFFFFFFFFFFFFh
0x14001c4e5  mov     [rbp+1B0h+var_1C0], rcx
0x14001c4e9  mov     [rbp+1B0h+var_1A8], 0Ah
0x14001c4f0  mov     [rbp+1B0h+var_1A0], rcx
0x14001c4f4  mov     [rbp+1B0h+var_198], rcx
0x14001c4f8  mov     [rbp+1B0h+var_180], 0Ah
0x14001c500  mov     [rbp+1B0h+Block], rcx
0x14001c504  movdqu  [rbp+1B0h+var_210], xmm0
0x14001c509  movdqu  [rbp+1B0h+var_1F8], xmm0
0x14001c50e  movdqu  [rbp+1B0h+var_1D0], xmm0
0x14001c513  movdqu  [rbp+1B0h+var_1B8], xmm1
0x14001c518  movdqu  [rbp+1B0h+var_190], xmm0
0x14001c51d  test    rbx, rbx
0x14001c520  jnz     loc_14001CD25
0x14001c526  mov     r14d, 80070057h
0x14001c52c  cmp     rax, rdx
0x14001c52f  jnz     loc_14001CF46
0x14001c535  test    rcx, rcx
0x14001c538  jnz     loc_14001C5FD
0x14001c53e  xchg    ax, ax
0x14001c540  cmp     [rbp+1B0h+var_1C0], 0
0x14001c545  jz      short loc_14001C55F
0x14001c547  lea     rcx, [rbp+1B0h+var_1D0]
0x14001c54b  call    ?RemoveHead@?$CAtlList@PEAUMDEProfile@@V?$CElementTraits@PEAUMDEProfile@@@ATL@@@ATL@@QEAAPEAUMDEProfile@@XZ; ATL::CAtlList<MDEProfile *,ATL::CElementTraits<MDEProfile *>>::RemoveHead(void)
0x14001c550  test    rax, rax
0x14001c553  jz      short loc_14001C540
0x14001c555  mov     rcx, rax; this
0x14001c558  call    ??_GMDEProfile@@QEAAPEAXI@Z; MDEProfile::`scalar deleting destructor'(uint)
0x14001c55d  jmp     short loc_14001C540
0x14001c55f  mov     r10, cs:WPP_GLOBAL_Control
0x14001c566  lea     rax, WPP_GLOBAL_Control
0x14001c56d  cmp     r10, rax
0x14001c570  jnz     loc_14001CF81
0x14001c576  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14001c57d  jnz     loc_14001CFE5
0x14001c583  lea     rcx, [rbp+1B0h+var_1A0]
0x14001c587  call    ?RemoveAll@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@QEAAXXZ; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>>::RemoveAll(void)
0x14001c58c  mov     rcx, [rbp+1B0h+Block]; Block
0x14001c590  test    rcx, rcx
0x14001c593  jnz     loc_14001D005
0x14001c599  lea     rcx, [rbp+1B0h+var_1D0]
0x14001c59d  call    ?RemoveAll@?$CAtlList@Usockaddr_storage@@V?$CElementTraits@Usockaddr_storage@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(void)
0x14001c5a2  lea     rcx, [rbp+1B0h+var_210]
0x14001c5a6  call    ?RemoveAll@?$CAtlList@Usockaddr_storage@@V?$CElementTraits@Usockaddr_storage@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(void)
0x14001c5ab  mov     rax, [rbp+1B0h+var_1D8]
0x14001c5af  test    rax, rax
0x14001c5b2  jz      short loc_14001C5BE
0x14001c5b4  lea     rcx, [rax+8]; lpCriticalSection
0x14001c5b8  call    cs:__imp_LeaveCriticalSection
0x14001c5be  mov     r12, [rsp+2B0h+var_30]
0x14001c5c6  mov     eax, r14d
0x14001c5c9  mov     r14, [rsp+2B0h+var_38]
0x14001c5d1  mov     rcx, [rbp+1B0h+var_50]
0x14001c5d8  xor     rcx, rsp; StackCookie
0x14001c5db  call    __security_check_cookie
0x14001c5e0  add     rsp, 288h
0x14001c5e7  pop     r15
0x14001c5e9  pop     r13
0x14001c5eb  pop     rdi
0x14001c5ec  pop     rsi
0x14001c5ed  pop     rbx
0x14001c5ee  pop     rbp
0x14001c5ef  retn
0x14001c5f0  mov     [rbp+1B0h+var_1D8], 0
0x14001c5f8  jmp     loc_14001C497
0x14001c5fd  lea     rcx, [rbp+1B0h+var_210]
0x14001c601  call    ?RemoveHead@?$CAtlList@PEAU_WMCResElement@@V?$CElementTraits@PEAU_WMCResElement@@@ATL@@@ATL@@QEAAPEAU_WMCResElement@@XZ; ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>>::RemoveHead(void)
0x14001c606  mov     rbx, rax
0x14001c609  mov     rcx, [rax]; bstrString
0x14001c60c  call    cs:__imp_SysFreeString
0x14001c612  mov     rcx, [rbx+10h]; bstrString
0x14001c616  call    cs:__imp_SysFreeString
0x14001c61c  mov     rcx, [rbx+28h]; bstrString
0x14001c620  call    cs:__imp_SysFreeString
0x14001c626  mov     rcx, [rbx+30h]; bstrString
0x14001c62a  call    cs:__imp_SysFreeString
0x14001c630  mov     edx, 60h ; '`'
0x14001c635  mov     rcx, rbx; Block
0x14001c638  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001c63d  mov     rcx, [rbp+1B0h+var_200]
0x14001c641  jmp     loc_14001C535
0x14001c646  call    cs:__imp__o__errno
0x14001c64c  mov     dword ptr [rax], 16h
0x14001c652  call    _invalid_parameter_noinfo
0x14001c657  cmp     dword ptr [r12-0Ch], 4
0x14001c65d  jl      loc_14001CDF9
0x14001c663  mov     rdx, [rsp+2B0h+var_240]
0x14001c668  lea     rsi, [rbx-18h]
0x14001c66c  xor     eax, eax
0x14001c66e  mov     dword ptr [r12-10h], 4
0x14001c677  mov     [r12+8], ax
0x14001c67d  mov     rdx, [rdx+190h]
0x14001c684  lea     rcx, [rdx-18h]
0x14001c688  cmp     rcx, rsi
0x14001c68b  jz      short loc_14001C6CF
0x14001c68d  cmp     [rsi+10h], eax
0x14001c690  jl      loc_14001CD5B
0x14001c696  mov     rax, [rsi]
0x14001c699  cmp     [rcx], rax
0x14001c69c  jnz     loc_14001CD5B
0x14001c6a2  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001c6a7  mov     rbx, rax
0x14001c6aa  mov     ecx, 0FFFFFFFFh
0x14001c6af  lock xadd [rsi+10h], ecx
0x14001c6b4  sub     ecx, 1
0x14001c6b7  jg      short loc_14001C6CB
0x14001c6b9  mov     rcx, [rsi]
0x14001c6bc  mov     rdx, [rcx]
0x14001c6bf  mov     rax, [rdx+8]
0x14001c6c3  mov     rdx, rsi
0x14001c6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c6cb  add     rbx, 18h
0x14001c6cf  mov     r13, [rsp+2B0h+var_250]
0x14001c6d4  mov     rsi, [rsp+2B0h+var_240]
0x14001c6d9  mov     rdx, [rsp+2B0h+var_238]
0x14001c6de  mov     qword ptr [rbp+1B0h+var_150], 0
0x14001c6e6  mov     rcx, [rdx+20h]
0x14001c6ea  test    rcx, rcx
0x14001c6ed  jz      short loc_14001C709
0x14001c6ef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14001c6f6  inc     rax
0x14001c6f9  cmp     word ptr [rcx+rax*2], 0
0x14001c6fe  jnz     short loc_14001C6F6
0x14001c700  test    rax, rax
0x14001c703  jnz     loc_14001CD73
0x14001c709  mov     eax, [rdi+40h]
0x14001c70c  test    eax, eax
0x14001c70e  jz      loc_14001CB87
0x14001c714  lea     rdx, [rbx-18h]
0x14001c718  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14001c71f  mov     eax, ebx
0x14001c721  lock xadd [rdx+10h], eax
0x14001c726  sub     eax, 1
0x14001c729  jg      short loc_14001C73A
0x14001c72b  mov     rcx, [rdx]
0x14001c72e  mov     rax, [rcx]
0x14001c731  mov     rax, [rax+8]
0x14001c735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c73a  lea     rdx, [r13-18h]
0x14001c73e  mov     eax, ebx
0x14001c740  lock xadd [rdx+10h], eax
0x14001c745  sub     eax, 1
0x14001c748  jg      short loc_14001C759
0x14001c74a  mov     rcx, [rdx]
0x14001c74d  mov     rax, [rcx]
0x14001c750  mov     rax, [rax+8]
0x14001c754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c759  lea     rdx, [r12-18h]
0x14001c75e  mov     eax, ebx
0x14001c760  lock xadd [rdx+10h], eax
0x14001c765  sub     eax, 1
0x14001c768  jg      short loc_14001C779
0x14001c76a  mov     rcx, [rdx]
0x14001c76d  mov     rax, [rcx]
0x14001c770  mov     rax, [rax+8]
0x14001c774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c779  mov     rbx, [rsp+2B0h+var_238]
0x14001c77e  jmp     short loc_14001C7BC
0x14001c780  mov     rax, [rax]
0x14001c783  test    rax, rax
0x14001c786  jz      short loc_14001C7E2
0x14001c788  nop     dword ptr [rax+rax+00000000h]
0x14001c790  test    r14d, r14d
0x14001c793  js      loc_14001CF32
0x14001c799  mov     rdi, [rax+10h]
0x14001c79d  mov     r15, [rax]
0x14001c7a0  cmp     dword ptr [rdi+4Ch], 0
0x14001c7a4  jnz     short loc_14001C7BC
0x14001c7a6  mov     r8, rdi; struct MDEProfile *
0x14001c7a9  mov     rdx, rbx; struct _WMCResElementParams *
0x14001c7ac  mov     rcx, rsi; this
0x14001c7af  call    ?CanUseMDEProfile@CMDEContentServer@@AEAAHPEBU_WMCResElementParams@@PEBUMDEProfile@@@Z; CMDEContentServer::CanUseMDEProfile(_WMCResElementParams const *,MDEProfile const *)
0x14001c7b4  test    eax, eax
0x14001c7b6  jnz     loc_14001C8E3
0x14001c7bc  mov     rax, r15
0x14001c7bf  mov     ecx, r14d
0x14001c7c2  test    r15, r15
0x14001c7c5  jnz     short loc_14001C790
0x14001c7c7  mov     r13, [rbp+1B0h+var_228]
0x14001c7cb  test    ecx, ecx
0x14001c7cd  js      loc_14001CF36
0x14001c7d3  mov     r12, [rbp+1B0h+var_218]
0x14001c7d7  mov     r15, 0FFFFFFFFFFFFFFFFh
0x14001c7de  mov     rdi, [rbp+1B0h+var_220]
0x14001c7e2  mov     rcx, [rbp+1B0h+var_200]
0x14001c7e6  test    rcx, rcx
0x14001c7e9  jz      loc_14001CE04
0x14001c7ef  cmp     rcx, 7FFFFFFFh
0x14001c7f6  ja      loc_14001CF1A
0x14001c7fc  mov     eax, 60h ; '`'
0x14001c801  mul     rcx
0x14001c804  cmovb   rax, r15
0x14001c808  mov     rcx, rax; unsigned __int64
0x14001c80b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001c810  mov     rsi, rax
0x14001c813  xor     edi, edi
0x14001c815  nop     word ptr [rax+rax+00000000h]
0x14001c820  mov     rcx, [rbp+1B0h+var_200]
0x14001c824  test    rcx, rcx
0x14001c827  jz      loc_14001CB77
0x14001c82d  mov     rcx, qword ptr [rbp+1B0h+var_210]
0x14001c831  test    rcx, rcx
0x14001c834  jz      loc_14001CAF5
0x14001c83a  mov     rax, [rcx]
0x14001c83d  mov     rbx, [rcx+10h]
0x14001c841  mov     qword ptr [rbp+1B0h+var_210], rax
0x14001c845  test    rax, rax
0x14001c848  jz      loc_14001CF25
0x14001c84e  mov     qword ptr [rax+8], 0
0x14001c856  mov     rax, qword ptr [rbp+1B0h+var_1F8+8]
0x14001c85a  mov     [rcx], rax
0x14001c85d  sub     [rbp+1B0h+var_200], 1
0x14001c862  mov     qword ptr [rbp+1B0h+var_1F8+8], rcx
0x14001c866  jnz     short loc_14001C871
0x14001c868  lea     rcx, [rbp+1B0h+var_210]
0x14001c86c  call    ?RemoveAll@?$CAtlList@Usockaddr_storage@@V?$CElementTraits@Usockaddr_storage@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(void)
0x14001c871  movups  xmm0, xmmword ptr [rbx]
0x14001c874  movsxd  rax, edi
0x14001c877  mov     edx, 60h ; '`'
0x14001c87c  inc     edi
0x14001c87e  lea     rcx, [rax+rax*2]
0x14001c882  shl     rcx, 5
0x14001c886  movups  xmmword ptr [rcx+rsi], xmm0
0x14001c88a  movups  xmm1, xmmword ptr [rbx+10h]
0x14001c88e  movups  xmmword ptr [rcx+rsi+10h], xmm1
0x14001c893  movups  xmm0, xmmword ptr [rbx+20h]
0x14001c897  movups  xmmword ptr [rcx+rsi+20h], xmm0
0x14001c89c  movups  xmm1, xmmword ptr [rbx+30h]
0x14001c8a0  movups  xmmword ptr [rcx+rsi+30h], xmm1
0x14001c8a5  movups  xmm0, xmmword ptr [rbx+40h]
0x14001c8a9  movups  xmmword ptr [rcx+rsi+40h], xmm0
0x14001c8ae  movups  xmm1, xmmword ptr [rbx+50h]
0x14001c8b2  movups  xmmword ptr [rcx+rsi+50h], xmm1
0x14001c8b7  mov     rcx, rbx; Block
0x14001c8ba  mov     qword ptr [rbx], 0
0x14001c8c1  mov     qword ptr [rbx+10h], 0
0x14001c8c9  mov     qword ptr [rbx+28h], 0
0x14001c8d1  mov     qword ptr [rbx+30h], 0
0x14001c8d9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001c8de  jmp     loc_14001C820
0x14001c8e3  movups  xmm0, xmmword ptr [rbx]
0x14001c8e6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001c8ed  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001c8f4  movups  xmm1, xmmword ptr [rbx+10h]
0x14001c8f8  movaps  [rbp+1B0h+var_170], xmm0
0x14001c8fc  movups  xmm0, xmmword ptr [rbx+20h]
0x14001c900  mov     rax, [rax+18h]
0x14001c904  movaps  [rbp+1B0h+var_160], xmm1
0x14001c908  movups  xmm1, xmmword ptr [rbx+30h]
0x14001c90c  movaps  [rbp+1B0h+var_150], xmm0
0x14001c910  movups  xmm0, xmmword ptr [rbx+40h]
0x14001c914  movaps  [rbp+1B0h+var_140], xmm1
0x14001c918  movups  xmm1, xmmword ptr [rbx+50h]
0x14001c91c  movaps  [rbp+1B0h+var_130], xmm0
0x14001c923  movups  xmm0, xmmword ptr [rbx+60h]
0x14001c927  movaps  [rbp+1B0h+var_120], xmm1
0x14001c92e  movups  xmm1, xmmword ptr [rbx+70h]
0x14001c932  movaps  [rbp+1B0h+var_110], xmm0
0x14001c939  movups  xmm0, xmmword ptr [rbx+80h]
0x14001c940  movaps  [rbp+1B0h+var_100], xmm1
  ... truncated ...
```
