# CShellProvider::Search(ushort const *,ushort const *,_WMCMetadataItem *,ulong,_WMCSortItem *,ulong,ulong,ulong,ushort const *,ulong *,ulong *,IWMCContentCollection * *)

- ea: `0x14007bec0`
- end: `0x14007c93c`
- name: `?Search@CShellProvider@@UEAAJPEBG0PEAU_WMCMetadataItem@@KPEAU_WMCSortItem@@KKK0PEAK3PEAPEAUIWMCContentCollection@@@Z`
- size: `2684`
- prototype: `__int64 __usercall@<rax>(CShellProvider *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, struct _WMCMetadataItem *@<r9>, char, struct _WMCSortItem *, char, char, char, const unsigned __int16 *, unsigned int *, unsigned int *, struct IWMCContentCollection **)`
- caller_count: `0`
- callee_count: `32`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400022a4`
- `0x140006d70`
- `0x140007020`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c920`
- `0x140024688`
- `0x140027660`
- `0x14002eb14`
- `0x140039768`
- `0x14003e064`
- `0x140054490`
- `0x140057544`
- `0x14006baa4`
- `0x14006caf8`
- `0x14006cea0`
- `0x14006e01c`
- `0x140073204`
- `0x140074f10`
- `0x140074fcc`
- `0x140076684`
- `0x140076a14`
- `0x140076cd0`
- `0x140077050`
- `0x140078a48`
- `0x14007bec0`
- `0x14007d4ec`
- `0x14007f13c`
- `0x14007f9e0`
- `0x14008020c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14007c019`
- `KERNEL32!EnterCriticalSection` at `0x14007c019`
- `KERNEL32!LeaveCriticalSection` at `0x14007c831`
- `KERNEL32!LeaveCriticalSection` at `0x14007c831`
- `KERNEL32!CompareStringW` at `0x14007c1e1`
- `KERNEL32!CompareStringW` at `0x14007c432`
- `KERNEL32!CompareStringW` at `0x14007c1e1`
- `KERNEL32!CompareStringW` at `0x14007c432`

## pseudocode

```c
__int64 __fastcall CShellProvider::Search(
        CShellProvider *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _WMCMetadataItem *a4,
        unsigned int a5,
        struct _WMCSortItem *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        const unsigned __int16 *a10,
        struct CQueryResultsEntry *a11,
        unsigned int *a12,
        struct IWMCContentCollection **a13)
{
  char v13; // al
  unsigned int v15; // r13d
  unsigned int v16; // r12d
  char v17; // bl
  const unsigned __int16 *v18; // r14
  struct CQueryResultsEntry *v19; // rsi
  struct IWMCContentCollection **v20; // r15
  struct _WMCSortItem *v21; // r14
  char *v22; // rbx
  unsigned int v23; // ecx
  unsigned int *v24; // rax
  unsigned int v25; // eax
  __int64 (__fastcall *v26)(CShellProvider *, __int64, __int64); // rbx
  __int64 BufferSetLength; // rax
  int AllChildContainers; // ebx
  int v29; // r8d
  int v30; // r9d
  char v31; // r14
  int v32; // eax
  char v33; // dl
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  int v37; // r8d
  int v38; // r9d
  const struct CdsQuery *ChildQuery; // r14
  const struct CdsQuery *v40; // rax
  __int64 v41; // r8
  const struct CdsQuery *v42; // r15
  int v43; // r8d
  unsigned __int16 **v44; // rdx
  int v45; // ecx
  int v46; // r9d
  int v47; // eax
  bool v48; // zf
  int v49; // eax
  struct _WMCSortItem *v50; // r9
  __int64 v51; // r8
  int v52; // eax
  int v53; // r9d
  struct _WMCSortItem *v54; // r14
  int v55; // ebx
  __int64 v56; // r8
  int v57; // ecx
  unsigned int lpString2a; // [rsp+20h] [rbp-108h]
  struct _WMCSortItem *lpString2b; // [rsp+20h] [rbp-108h]
  struct _WMCSortItem *lpString2c; // [rsp+20h] [rbp-108h]
  struct _WMCSortItem *lpString2; // [rsp+20h] [rbp-108h]
  struct _WMCSortItem *cchCount2a; // [rsp+28h] [rbp-100h]
  char cchCount2; // [rsp+28h] [rbp-100h]
  char v65; // [rsp+30h] [rbp-F8h]
  char v66; // [rsp+30h] [rbp-F8h]
  struct _WMCSortItem *v67; // [rsp+30h] [rbp-F8h]
  struct _WMCSortItem *v68; // [rsp+30h] [rbp-F8h]
  char v69; // [rsp+38h] [rbp-F0h]
  char v70; // [rsp+38h] [rbp-F0h]
  char v71; // [rsp+38h] [rbp-F0h]
  char v72; // [rsp+40h] [rbp-E8h]
  char *v73; // [rsp+40h] [rbp-E8h]
  struct CQueryResultsEntry *v74; // [rsp+50h] [rbp-D8h]
  struct CQueryResultsEntry *v75; // [rsp+58h] [rbp-D0h]
  struct CQueryResultsEntry *v76; // [rsp+58h] [rbp-D0h]
  void *v77; // [rsp+80h] [rbp-A8h] BYREF
  unsigned __int16 *v78; // [rsp+88h] [rbp-A0h] BYREF
  CdsCompoundQuery *v79; // [rsp+90h] [rbp-98h] BYREF
  __int64 v80; // [rsp+98h] [rbp-90h] BYREF
  __int64 v81; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v82; // [rsp+A8h] [rbp-80h] BYREF
  __int64 v83; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v84[2]; // [rsp+B8h] [rbp-70h] BYREF
  __int64 v85; // [rsp+C8h] [rbp-60h]
  __int128 v86; // [rsp+D0h] [rbp-58h]
  int v87; // [rsp+E0h] [rbp-48h]
  __int64 v88; // [rsp+130h] [rbp+8h] BYREF
  const unsigned __int16 *v89; // [rsp+138h] [rbp+10h]
  unsigned __int16 *v90; // [rsp+140h] [rbp+18h]
  struct _WMCMetadataItem *v91; // [rsp+148h] [rbp+20h]

  v91 = a4;
  v90 = a3;
  v89 = a2;
  v13 = Microsoft_Windows_WMPNSS_ServiceEnableBits;
  v15 = a8;
  v16 = a7;
  v17 = a5;
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
  {
    McTemplateU0zzqqqqqq_EventWriteTransfer(
      (_DWORD)this,
      (unsigned int)WMP_Search_Start,
      (_DWORD)a2,
      (_DWORD)a3,
      a8,
      a9,
      a5,
      a7,
      0,
      0);
    v13 = Microsoft_Windows_WMPNSS_ServiceEnableBits;
  }
  v18 = a10;
  if ( (v13 & 0x20) != 0 )
    McTemplateU0z_EventWriteTransfer(this, WMP_Search_Remote_Address_Info, a10);
  v19 = a11;
  v20 = a13;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
  {
    v21 = a6;
    v22 = (char *)v89;
  }
  else
  {
    v75 = (struct CQueryResultsEntry *)v18;
    v21 = a6;
    v65 = v17;
    v22 = (char *)v89;
    WPP_SF_SSqDqDDDSqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)v90,
      (char)v91,
      v65,
      (char)a6,
      v16,
      v15,
      a9,
      (__int64)v75,
      (char)a11,
      (char)a12,
      (char)a13);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  v79 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &v77,
    v22);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v78);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v81);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v88);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v80);
  CShellProvider::TryEnsureLibraryMonitor(this);
  v23 = a9;
  v24 = a12;
  *(_DWORD *)v19 = 0;
  *v24 = 0;
  v25 = -1;
  *v20 = 0;
  if ( v23 )
    v25 = v23;
  a9 = v25;
  v26 = *(__int64 (__fastcall **)(CShellProvider *, __int64, __int64))(*(_QWORD *)this + 88LL);
  BufferSetLength = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(&v80, 64);
  AllChildContainers = v26(this, 63, BufferSetLength);
  LODWORD(a11) = AllChildContainers >> 31;
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v80, ((AllChildContainers >> 31) & 1u) - 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((unsigned int)a11 & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      214,
      (unsigned int)&WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
      AllChildContainers,
      v80);
  }
  if ( AllChildContainers < 0 )
    goto LABEL_65;
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v88, a10);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&a11,
    (char *)v90);
  AllChildContainers = CdsQueryParser::ParseQuery(&a11, &v79);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&a11);
  if ( AllChildContainers < 0 )
    goto LABEL_65;
  if ( (*((_BYTE *)v79 + 24) & 0x40) == 0 )
  {
    if ( (*((_BYTE *)v79 + 24) & 0x20) != 0 )
    {
      v33 = *((_BYTE *)v79 + 36);
      v34 = *((_DWORD *)v79 + 8);
      if ( v33 )
      {
        if ( v34 == 2 )
        {
          v35 = (int)v91;
          v69 = a9;
          lpString2b = v21;
          v31 = a5;
          v36 = a5;
          *(_DWORD *)v19 = 0;
          v32 = CShellProvider::ExecuteRefIDExistsTrueQuery(
                  (int)this,
                  (int)&v77,
                  v35,
                  v36,
                  lpString2b,
                  v16,
                  v15,
                  v69,
                  (__int64)this + 80,
                  (__int64)&v88,
                  v19,
                  (__int64)v20);
          goto LABEL_24;
        }
        if ( v33 == 1 && ((v34 - 1) & 0xFFFFFFED) == 0 && v34 != 3 )
        {
          v29 = 0;
          goto LABEL_23;
        }
      }
      else if ( v34 == 2 )
      {
        v37 = (int)v91;
        v70 = a9;
        lpString2c = v21;
        v31 = a5;
        v38 = a5;
        *(_DWORD *)v19 = 0;
        v32 = CShellProvider::ExecuteRefIDExistsFalseQuery(
                (int)this,
                (int)&v77,
                v37,
                v38,
                lpString2c,
                v16,
                v15,
                v70,
                (__int64)this + 80,
                (__int64)&v88,
                v19,
                (__int64)v20);
        goto LABEL_24;
      }
LABEL_65:
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v83);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v82);
      ATL::CSimpleStringT<unsigned short,0>::Empty(&v81);
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v78, &v77);
      if ( AllChildContainers < 0 )
      {
        v31 = a5;
      }
      else
      {
        v85 = 0;
        LOBYTE(v53) = 1;
        v87 = 10;
        *(_OWORD *)v84 = 0;
        v86 = 0;
        AllChildContainers = CShellProvider::GetAllChildContainers(
                               (int)this + 312,
                               (int)this + 600,
                               0,
                               v53,
                               v78,
                               v88,
                               (__int64)v84);
        if ( AllChildContainers < 0 )
        {
          v31 = a5;
        }
        else
        {
          v54 = a6;
          a11 = 0;
          AllChildContainers = CQueryResultsCache::GetQueryResults(
                                 (LPCRITICAL_SECTION)((char *)this + 712),
                                 v90,
                                 a6,
                                 v16,
                                 &a11);
          if ( AllChildContainers < 0 )
          {
            v31 = a5;
          }
          else
          {
            v68 = v54;
            v31 = a5;
            AllChildContainers = CShellProvider::ExecuteQueryOnContainers(
                                   (int)this + 312,
                                   (int)a11,
                                   (int)v84,
                                   (int)v79,
                                   v91,
                                   a5,
                                   v68,
                                   v16,
                                   v15,
                                   a9,
                                   (__int64)this + 80,
                                   (__int64)&v88,
                                   (__int64)v19,
                                   (__int64)v20);
          }
          Microsoft::WRL::ComPtr<CAdapterAddress>::InternalAddRef(&a11);
        }
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(v84);
      }
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v82);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v83);
      goto LABEL_75;
    }
    if ( (*((_BYTE *)v79 + 24) & 4) == 0 || CdsCompoundQuery::ChildQueryCount(v79) != 2 )
      goto LABEL_65;
    ChildQuery = CdsCompoundQuery::GetChildQuery(v79, 0);
    v40 = CdsCompoundQuery::GetChildQuery(v79, 1u);
    if ( (*((_BYTE *)ChildQuery + 24) & 0x20) != 0 && (*((_BYTE *)v40 + 24) & 0x40) != 0 )
    {
      v42 = v40;
    }
    else
    {
      if ( (*((_BYTE *)ChildQuery + 24) & 0x40) == 0 || (*((_BYTE *)v40 + 24) & 0x20) == 0 )
        goto LABEL_65;
      v42 = ChildQuery;
      ChildQuery = v40;
    }
    if ( !ChildQuery || !v42 )
      goto LABEL_64;
    if ( *((_DWORD *)v42 + 9) == 9 )
    {
      if ( *((_DWORD *)v42 + 8) == 17 && CompareStringW(0x7Fu, 1u, *((PCNZWCH *)v42 + 5), -1, L"object.item", -1) == 2 )
      {
        if ( *((_BYTE *)ChildQuery + 36) == 1 )
        {
          v20 = a13;
          if ( *((_DWORD *)ChildQuery + 8) != 2 )
            goto LABEL_65;
          v43 = (int)v91;
          v76 = (struct CQueryResultsEntry *)a13;
          v44 = (unsigned __int16 **)&v77;
          v74 = v19;
          v45 = (int)this;
          v73 = (char *)this + 80;
          v71 = a9;
          v66 = v15;
          cchCount2 = v16;
          lpString2 = a6;
          v31 = a5;
          v46 = a5;
          *(_DWORD *)v19 = 0;
          goto LABEL_51;
        }
        goto LABEL_64;
      }
      if ( *((_DWORD *)v42 + 9) == 9 && *((_DWORD *)v42 + 8) == 17 )
      {
        AllChildContainers = GetBetterContainerIDForSearchClass(&v77, (char *)v42 + 40, v41, &v78);
        if ( AllChildContainers >= 0 )
        {
          if ( !*((_DWORD *)v78 - 4) )
            ATL::CSimpleStringT<unsigned short,0>::operator=(&v78, &v77);
          v20 = a13;
          if ( *((_DWORD *)ChildQuery + 8) != 2 )
            goto LABEL_65;
          v43 = (int)v91;
          v76 = (struct CQueryResultsEntry *)a13;
          v74 = v19;
          v44 = &v78;
          v45 = (int)this;
          v73 = (char *)this + 80;
          v71 = a9;
          v66 = v15;
          *(_DWORD *)v19 = 0;
          v48 = *((_BYTE *)ChildQuery + 36) == 0;
          cchCount2 = v16;
          lpString2 = a6;
          v31 = a5;
          v46 = a5;
          if ( v48 )
          {
            v47 = CShellProvider::ExecuteRefIDExistsFalseQuery(
                    (int)this,
                    (int)&v78,
                    v43,
                    a5,
                    a6,
                    v16,
                    v15,
                    v71,
                    (__int64)v73,
                    (__int64)&v88,
                    v19,
                    (__int64)v76);
            goto LABEL_52;
          }
LABEL_51:
          v47 = CShellProvider::ExecuteRefIDExistsTrueQuery(
                  v45,
                  (int)v44,
                  v43,
                  v46,
                  lpString2,
                  cchCount2,
                  v66,
                  v71,
                  (__int64)v73,
                  (__int64)&v88,
                  v74,
                  (__int64)v76);
LABEL_52:
          AllChildContainers = v47;
          goto LABEL_76;
        }
LABEL_64:
        v20 = a13;
        goto LABEL_65;
      }
    }
    if ( !*((_BYTE *)ChildQuery + 36) )
    {
      v49 = *((_DWORD *)v42 + 8);
      v20 = a13;
      if ( *((_DWORD *)ChildQuery + 8) == v49 )
      {
        v50 = a6;
        v51 = a9;
        v67 = (struct _WMCSortItem *)a13;
        *(_DWORD *)v19 = 0;
        v52 = CShellProviderResults::CreateBrowseChildrenInstance(0, v15, v51, v50, v16, &v88, v67);
        v31 = a5;
        AllChildContainers = v52;
        goto LABEL_76;
      }
      goto LABEL_65;
    }
    goto LABEL_64;
  }
  if ( *((_DWORD *)v79 + 9) != 9
    || *((_DWORD *)v79 + 8) != 17
    || CompareStringW(0x7Fu, 1u, *((PCNZWCH *)v79 + 5), -1, L"object.item", -1) != 2 )
  {
    goto LABEL_65;
  }
  LOBYTE(v29) = 1;
LABEL_23:
  v30 = (int)v91;
  v72 = a9;
  cchCount2a = v21;
  v31 = a5;
  lpString2a = a5;
  *(_DWORD *)v19 = 0;
  v32 = CShellProvider::ExecuteReturnAllChildren(
          (int)this,
          (int)&v77,
          v29,
          v30,
          lpString2a,
          cchCount2a,
          v16,
          v15,
          v72,
          (__int64)this + 80,
          (__int64)&v88,
          v19,
          (__int64)v20);
LABEL_24:
  AllChildContainers = v32;
LABEL_75:
  v20 = a13;
LABEL_76:
  if ( AllChildContainers >= 0 )
    *a12 = *((_DWORD *)this + 211);
  v55 = CShellProvider::ConvertToCDError(AllChildContainers);
  if ( v55 == -2147220635 )
    v55 = -2147220626;
  CQueryResultsCache::CleanCache((LPCRITICAL_SECTION)((char *)this + 712));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  v57 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v55 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dDDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, v56, (unsigned int)v55, *(_DWORD *)v19, *a12, *v20);
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0zzqqqqqq_EventWriteTransfer(
      v57,
      (unsigned int)WMP_Search_Stop,
      (_DWORD)v89,
      (_DWORD)v90,
      v15,
      a9,
      v31,
      v16,
      *(_DWORD *)v19,
      v55);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v80);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v88);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v81);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v78);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v77);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v79);
  return (unsigned int)v55;
}

```

## disassembly

```asm
0x14007bec0  mov     [rsp+arg_18], r9
0x14007bec5  mov     [rsp+arg_10], r8
0x14007beca  mov     [rsp+arg_8], rdx
0x14007becf  push    rbx
0x14007bed0  push    rsi
0x14007bed1  push    rdi
0x14007bed2  push    r12
0x14007bed4  push    r13
0x14007bed6  push    r14
0x14007bed8  push    r15
0x14007beda  sub     rsp, 0F0h
0x14007bee1  mov     eax, cs:Microsoft_Windows_WMPNSS_ServiceEnableBits
0x14007bee7  mov     rdi, rcx
0x14007beea  mov     r13d, [rsp+128h+arg_38]
0x14007bef2  mov     r12d, [rsp+128h+arg_30]
0x14007befa  mov     ebx, [rsp+128h+arg_20]
0x14007bf01  test    al, 20h
0x14007bf03  jz      short loc_14007BF46
0x14007bf05  mov     eax, [rsp+128h+arg_40]
0x14007bf0c  mov     r9, r8
0x14007bf0f  mov     dword ptr [rsp+128h+var_E0], 0
0x14007bf17  mov     r8, rdx
0x14007bf1a  mov     dword ptr [rsp+128h+var_E8], 0
0x14007bf22  lea     rdx, WMP_Search_Start
0x14007bf29  mov     dword ptr [rsp+128h+var_F0], r12d
0x14007bf2e  mov     dword ptr [rsp+128h+var_F8], ebx
0x14007bf32  mov     [rsp+128h+cchCount2], eax
0x14007bf36  mov     dword ptr [rsp+128h+lpString2], r13d
0x14007bf3b  call    McTemplateU0zzqqqqqq_EventWriteTransfer
0x14007bf40  mov     eax, cs:Microsoft_Windows_WMPNSS_ServiceEnableBits
0x14007bf46  mov     r14, [rsp+128h+arg_48]
0x14007bf4e  test    al, 20h
0x14007bf50  jz      short loc_14007BF61
0x14007bf52  mov     r8, r14
0x14007bf55  lea     rdx, WMP_Search_Remote_Address_Info
0x14007bf5c  call    McTemplateU0z_EventWriteTransfer
0x14007bf61  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bf68  lea     rax, WPP_GLOBAL_Control
0x14007bf6f  mov     rsi, [rsp+128h+arg_50]
0x14007bf77  mov     r15, [rsp+128h+arg_60]
0x14007bf7f  cmp     rcx, rax
0x14007bf82  jz      short loc_14007C002
0x14007bf84  test    byte ptr [rcx+1Ch], 1
0x14007bf88  jz      short loc_14007C002
0x14007bf8a  cmp     byte ptr [rcx+19h], 5
0x14007bf8e  jb      short loc_14007C002
0x14007bf90  mov     rdx, [rsp+128h+arg_58]
0x14007bf98  mov     eax, [rsp+128h+arg_40]
0x14007bf9f  mov     rcx, [rcx+10h]; LoggerHandle
0x14007bfa3  mov     qword ptr [rsp+128h+var_B8], r15; char
0x14007bfa8  mov     qword ptr [rsp+128h+var_C0], rdx; char
0x14007bfad  mov     qword ptr [rsp+128h+var_C8], rsi; char
0x14007bfb2  mov     [rsp+128h+var_D0], r14; __int64
0x14007bfb7  mov     r14, [rsp+128h+arg_28]
0x14007bfbf  mov     dword ptr [rsp+128h+var_D8], eax; char
0x14007bfc3  mov     rax, [rsp+128h+arg_18]
0x14007bfcb  mov     dword ptr [rsp+128h+var_E0], r13d; char
0x14007bfd0  mov     dword ptr [rsp+128h+var_E8], r12d; char
0x14007bfd5  mov     qword ptr [rsp+128h+var_F0], r14; char
0x14007bfda  mov     dword ptr [rsp+128h+var_F8], ebx; char
0x14007bfde  mov     rbx, [rsp+128h+arg_8]
0x14007bfe6  mov     qword ptr [rsp+128h+cchCount2], rax; char
0x14007bfeb  mov     r9, rbx
0x14007bfee  mov     rax, [rsp+128h+arg_10]
0x14007bff6  mov     [rsp+128h+lpString2], rax; __int64
0x14007bffb  call    WPP_SF_SSqDqDDDSqqq
0x14007c000  jmp     short loc_14007C012
0x14007c002  mov     r14, [rsp+128h+arg_28]
0x14007c00a  mov     rbx, [rsp+128h+arg_8]
0x14007c012  lea     rcx, [rdi+100h]; lpCriticalSection
0x14007c019  call    cs:__imp_EnterCriticalSection
0x14007c01f  mov     rdx, rbx
0x14007c022  mov     [rsp+128h+var_98], 0
0x14007c02e  lea     rcx, [rsp+128h+var_A8]
0x14007c036  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14007c03b  lea     rcx, [rsp+128h+var_A0]
0x14007c043  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14007c048  lea     rcx, [rsp+128h+var_88]
0x14007c050  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14007c055  lea     rcx, [rsp+128h+arg_0]
0x14007c05d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14007c062  lea     rcx, [rsp+128h+var_90]
0x14007c06a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14007c06f  mov     rcx, rdi; this
0x14007c072  call    ?TryEnsureLibraryMonitor@CShellProvider@@QEAAXXZ; CShellProvider::TryEnsureLibraryMonitor(void)
0x14007c077  mov     ecx, [rsp+128h+arg_40]
0x14007c07e  xor     edx, edx
0x14007c080  mov     rax, [rsp+128h+arg_58]
0x14007c088  mov     [rsi], edx
0x14007c08a  mov     [rax], edx
0x14007c08c  or      eax, 0FFFFFFFFh
0x14007c08f  test    ecx, ecx
0x14007c091  mov     [r15], rdx
0x14007c094  mov     edx, 40h ; '@'
0x14007c099  cmovnz  eax, ecx
0x14007c09c  lea     rcx, [rsp+128h+var_90]
0x14007c0a4  mov     [rsp+128h+arg_40], eax
0x14007c0ab  mov     rax, [rdi]
0x14007c0ae  mov     rbx, [rax+58h]
0x14007c0b2  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x14007c0b7  mov     r8, rax
0x14007c0ba  mov     edx, 3Fh ; '?'
0x14007c0bf  mov     rax, rbx
0x14007c0c2  mov     rcx, rdi
0x14007c0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c0ca  mov     ebx, eax
0x14007c0cc  sar     eax, 1Fh
0x14007c0cf  lea     rcx, [rsp+128h+var_90]
0x14007c0d7  mov     edx, eax
0x14007c0d9  mov     dword ptr [rsp+128h+arg_50], eax
0x14007c0e0  and     edx, 1
0x14007c0e3  dec     edx
0x14007c0e5  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x14007c0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c0f1  lea     rax, WPP_GLOBAL_Control
0x14007c0f8  cmp     rcx, rax
0x14007c0fb  jz      short loc_14007C13D
0x14007c0fd  test    byte ptr [rcx+1Ch], 2
0x14007c101  jz      short loc_14007C13D
0x14007c103  mov     edx, dword ptr [rsp+128h+arg_50]
0x14007c10a  movzx   eax, byte ptr [rcx+19h]
0x14007c10e  and     edx, 0FFFFFFFDh
0x14007c111  add     edx, 5
0x14007c114  cmp     eax, edx
0x14007c116  jb      short loc_14007C13D
0x14007c118  mov     rax, [rsp+128h+var_90]
0x14007c120  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x14007c127  mov     rcx, [rcx+10h]
0x14007c12b  mov     edx, 0D6h
0x14007c130  mov     r9d, ebx
0x14007c133  mov     [rsp+128h+lpString2], rax
0x14007c138  call    WPP_SF_dS
0x14007c13d  test    ebx, ebx
0x14007c13f  js      loc_14007C621
0x14007c145  mov     rdx, [rsp+128h+arg_48]
0x14007c14d  lea     rcx, [rsp+128h+arg_0]
0x14007c155  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x14007c15a  mov     rdx, [rsp+128h+arg_10]
0x14007c162  lea     rcx, [rsp+128h+arg_50]
0x14007c16a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14007c16f  lea     rdx, [rsp+128h+var_98]
0x14007c177  lea     rcx, [rsp+128h+arg_50]
0x14007c17f  call    ?ParseQuery@CdsQueryParser@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAPEAVCdsQuery@@@Z; CdsQueryParser::ParseQuery(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,CdsQuery * *)
0x14007c184  lea     rcx, [rsp+128h+arg_50]
0x14007c18c  mov     ebx, eax
0x14007c18e  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007c193  test    ebx, ebx
0x14007c195  js      loc_14007C621
0x14007c19b  mov     rax, [rsp+128h+var_98]
0x14007c1a3  test    byte ptr [rax+18h], 40h
0x14007c1a7  jz      loc_14007C25F
0x14007c1ad  cmp     dword ptr [rax+24h], 9
0x14007c1b1  jnz     loc_14007C621
0x14007c1b7  cmp     dword ptr [rax+20h], 11h
0x14007c1bb  jnz     loc_14007C621
0x14007c1c1  mov     r8, [rax+28h]; lpString1
0x14007c1c5  lea     rcx, aObjectItem; "object.item"
0x14007c1cc  or      r9d, 0FFFFFFFFh; cchCount1
0x14007c1d0  mov     [rsp+128h+cchCount2], r9d; cchCount2
0x14007c1d5  mov     [rsp+128h+lpString2], rcx; lpString2
0x14007c1da  lea     edx, [r9+2]; dwCmpFlags
0x14007c1de  lea     ecx, [rdx+7Eh]; Locale
0x14007c1e1  call    cs:__imp_CompareStringW
0x14007c1e7  cmp     eax, 2
0x14007c1ea  jnz     loc_14007C621
0x14007c1f0  mov     r8b, 1; int
0x14007c1f3  mov     r9, [rsp+128h+arg_18]; int
0x14007c1fb  lea     rax, [rdi+50h]
0x14007c1ff  mov     qword ptr [rsp+128h+var_C8], r15; __int64
0x14007c204  lea     rcx, [rsp+128h+arg_0]
0x14007c20c  mov     [rsp+128h+var_D0], rsi; struct CQueryResultsEntry *
0x14007c211  lea     rdx, [rsp+128h+var_A8]; int
0x14007c219  mov     [rsp+128h+var_D8], rcx; __int64
0x14007c21e  mov     rcx, rdi; int
0x14007c221  mov     qword ptr [rsp+128h+var_E0], rax; __int64
0x14007c226  mov     eax, [rsp+128h+arg_40]
0x14007c22d  mov     dword ptr [rsp+128h+var_E8], eax; char
0x14007c231  mov     dword ptr [rsp+128h+var_F0], r13d; char
0x14007c236  mov     dword ptr [rsp+128h+var_F8], r12d; char
0x14007c23b  mov     qword ptr [rsp+128h+cchCount2], r14; struct _WMCSortItem *
0x14007c240  mov     r14d, [rsp+128h+arg_20]
0x14007c248  mov     dword ptr [rsp+128h+lpString2], r14d; unsigned int
0x14007c24d  mov     dword ptr [rsi], 0
0x14007c253  call    ?ExecuteReturnAllChildren@CShellProvider@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NPEBU_WMCMetadataItem@@KPEAU_WMCSortItem@@KKK00PEAKPEAPEAUIWMCContentCollection@@@Z; CShellProvider::ExecuteReturnAllChildren(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,bool,_WMCMetadataItem const *,ulong,_WMCSortItem *,ulong,ulong,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ulong *,IWMCContentCollection * *)
0x14007c258  mov     ebx, eax
0x14007c25a  jmp     loc_14007C7EB
0x14007c25f  test    byte ptr [rax+18h], 20h
0x14007c263  jz      loc_14007C37D
0x14007c269  mov     dl, [rax+24h]
0x14007c26c  mov     ecx, [rax+20h]
0x14007c26f  test    dl, dl
0x14007c271  jz      loc_14007C30C
0x14007c277  cmp     ecx, 2
0x14007c27a  jnz     short loc_14007C2E4
0x14007c27c  mov     r8, [rsp+128h+arg_18]; int
0x14007c284  lea     rax, [rdi+50h]
0x14007c288  mov     [rsp+128h+var_D0], r15; __int64
0x14007c28d  lea     rcx, [rsp+128h+arg_0]
0x14007c295  mov     [rsp+128h+var_D8], rsi; struct CQueryResultsEntry *
0x14007c29a  lea     rdx, [rsp+128h+var_A8]; int
0x14007c2a2  mov     qword ptr [rsp+128h+var_E0], rcx; __int64
0x14007c2a7  mov     rcx, rdi; int
0x14007c2aa  mov     qword ptr [rsp+128h+var_E8], rax; __int64
0x14007c2af  mov     eax, [rsp+128h+arg_40]
0x14007c2b6  mov     dword ptr [rsp+128h+var_F0], eax; char
0x14007c2ba  mov     dword ptr [rsp+128h+var_F8], r13d; char
0x14007c2bf  mov     [rsp+128h+cchCount2], r12d; char
0x14007c2c4  mov     [rsp+128h+lpString2], r14; struct _WMCSortItem *
0x14007c2c9  mov     r14d, [rsp+128h+arg_20]
0x14007c2d1  mov     r9d, r14d; int
0x14007c2d4  mov     dword ptr [rsi], 0
0x14007c2da  call    ?ExecuteRefIDExistsTrueQuery@CShellProvider@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBU_WMCMetadataItem@@KPEAU_WMCSortItem@@KKK00PEAKPEAPEAUIWMCContentCollection@@@Z; CShellProvider::ExecuteRefIDExistsTrueQuery(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,_WMCMetadataItem const *,ulong,_WMCSortItem *,ulong,ulong,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ulong *,IWMCContentCollection * *)
0x14007c2df  jmp     loc_14007C258
0x14007c2e4  cmp     dl, 1
0x14007c2e7  jnz     loc_14007C621
0x14007c2ed  lea     eax, [rcx-1]
0x14007c2f0  test    eax, 0FFFFFFEDh
0x14007c2f5  jnz     loc_14007C621
0x14007c2fb  cmp     ecx, 3
0x14007c2fe  jz      loc_14007C621
0x14007c304  xor     r8d, r8d
0x14007c307  jmp     loc_14007C1F3
0x14007c30c  cmp     ecx, 2
0x14007c30f  jnz     loc_14007C621
0x14007c315  mov     r8, [rsp+128h+arg_18]; int
0x14007c31d  lea     rax, [rdi+50h]
0x14007c321  mov     [rsp+128h+var_D0], r15; __int64
0x14007c326  lea     rcx, [rsp+128h+arg_0]
0x14007c32e  mov     [rsp+128h+var_D8], rsi; struct CQueryResultsEntry *
0x14007c333  lea     rdx, [rsp+128h+var_A8]; int
0x14007c33b  mov     qword ptr [rsp+128h+var_E0], rcx; __int64
0x14007c340  mov     rcx, rdi; int
0x14007c343  mov     qword ptr [rsp+128h+var_E8], rax; __int64
0x14007c348  mov     eax, [rsp+128h+arg_40]
0x14007c34f  mov     dword ptr [rsp+128h+var_F0], eax; char
0x14007c353  mov     dword ptr [rsp+128h+var_F8], r13d; char
0x14007c358  mov     [rsp+128h+cchCount2], r12d; char
0x14007c35d  mov     [rsp+128h+lpString2], r14; struct _WMCSortItem *
0x14007c362  mov     r14d, [rsp+128h+arg_20]
0x14007c36a  mov     r9d, r14d; int
0x14007c36d  mov     dword ptr [rsi], 0
0x14007c373  call    ?ExecuteRefIDExistsFalseQuery@CShellProvider@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBU_WMCMetadataItem@@KPEAU_WMCSortItem@@KKK00PEAKPEAPEAUIWMCContentCollection@@@Z; CShellProvider::ExecuteRefIDExistsFalseQuery(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,_WMCMetadataItem const *,ulong,_WMCSortItem *,ulong,ulong,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ulong *,IWMCContentCollection * *)
0x14007c378  jmp     loc_14007C258
0x14007c37d  test    byte ptr [rax+18h], 4
0x14007c381  jz      loc_14007C621
0x14007c387  mov     rcx, rax; this
0x14007c38a  call    ?ChildQueryCount@CdsCompoundQuery@@QEBA_KXZ; CdsCompoundQuery::ChildQueryCount(void)
0x14007c38f  cmp     rax, 2
0x14007c393  jnz     loc_14007C621
0x14007c399  mov     rcx, [rsp+128h+var_98]; this
0x14007c3a1  xor     edx, edx; unsigned __int64
0x14007c3a3  call    ?GetChildQuery@CdsCompoundQuery@@QEBAPEBVCdsQuery@@_K@Z; CdsCompoundQuery::GetChildQuery(unsigned __int64)
0x14007c3a8  mov     rcx, [rsp+128h+var_98]; this
0x14007c3b0  mov     edx, 1; unsigned __int64
0x14007c3b5  mov     r14, rax
0x14007c3b8  call    ?GetChildQuery@CdsCompoundQuery@@QEBAPEBVCdsQuery@@_K@Z; CdsCompoundQuery::GetChildQuery(unsigned __int64)
0x14007c3bd  test    byte ptr [r14+18h], 20h
0x14007c3c2  jz      short loc_14007C3CF
0x14007c3c4  test    byte ptr [rax+18h], 40h
0x14007c3c8  jz      short loc_14007C3CF
0x14007c3ca  mov     r15, rax
0x14007c3cd  jmp     short loc_14007C3EA
0x14007c3cf  test    byte ptr [r14+18h], 40h
0x14007c3d4  jz      loc_14007C621
0x14007c3da  test    byte ptr [rax+18h], 20h
0x14007c3de  jz      loc_14007C621
0x14007c3e4  mov     r15, r14
0x14007c3e7  mov     r14, rax
0x14007c3ea  test    r14, r14
0x14007c3ed  jz      loc_14007C619
0x14007c3f3  test    r15, r15
0x14007c3f6  jz      loc_14007C619
0x14007c3fc  cmp     dword ptr [r15+24h], 9
0x14007c401  jnz     loc_14007C5BA
0x14007c407  cmp     dword ptr [r15+20h], 11h
0x14007c40c  jnz     loc_14007C4D0
0x14007c412  mov     r8, [r15+28h]; lpString1
0x14007c416  lea     rcx, aObjectItem; "object.item"
0x14007c41d  or      r9d, 0FFFFFFFFh; cchCount1
0x14007c421  mov     [rsp+128h+cchCount2], r9d; cchCount2
0x14007c426  mov     [rsp+128h+lpString2], rcx; lpString2
0x14007c42b  lea     edx, [r9+2]; dwCmpFlags
0x14007c42f  lea     ecx, [rdx+7Eh]; Locale
0x14007c432  call    cs:__imp_CompareStringW
0x14007c438  cmp     eax, 2
0x14007c43b  jnz     loc_14007C4D0
0x14007c441  cmp     byte ptr [r14+24h], 1
0x14007c446  jnz     loc_14007C619
0x14007c44c  mov     r15, [rsp+128h+arg_60]
0x14007c454  cmp     [r14+20h], eax
0x14007c458  jnz     loc_14007C621
0x14007c45e  mov     r14, [rsp+128h+arg_28]
0x14007c466  lea     rcx, [rsp+128h+arg_0]
0x14007c46e  mov     r8, [rsp+128h+arg_18]; int
0x14007c476  lea     rax, [rdi+50h]
0x14007c47a  mov     [rsp+128h+var_D0], r15; __int64
0x14007c47f  lea     rdx, [rsp+128h+var_A8]; int
0x14007c487  mov     [rsp+128h+var_D8], rsi; struct CQueryResultsEntry *
0x14007c48c  mov     qword ptr [rsp+128h+var_E0], rcx; __int64
0x14007c491  mov     rcx, rdi; int
  ... truncated ...
```
