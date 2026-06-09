# CComponentEntry::_GetComponentVolumesAndFiles(IVssWMComponent *,CVolumeEntryMap *,CFileDescriptorEntryArray *,CPathCache *)

- ea: `0x180023874`
- end: `0x180023fbe`
- name: `?_GetComponentVolumesAndFiles@CComponentEntry@@AEAAJPEAVIVssWMComponent@@PEAVCVolumeEntryMap@@PEAVCFileDescriptorEntryArray@@PEAVCPathCache@@@Z`
- size: `1866`
- prototype: `__int64 __fastcall(CComponentEntry *__hidden this, struct IVssWMComponent *, struct CVolumeEntryMap *, struct CFileDescriptorEntryArray *, struct CPathCache *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180023fc4`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x18000406c`
- `0x1800074e4`
- `0x180007a74`
- `0x18000c804`
- `0x18000dce0`
- `0x18000e104`
- `0x18000e308`
- `0x180020710`
- `0x180020af4`
- `0x180023360`
- `0x1800234d4`
- `0x180023874`
- `0x180024640`
- `0x1800268b4`
- `0x1800269ac`
- `0x18003532c`
- `0x180037010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180023f88`
- `OLEAUT32!__imp_SysFreeString` at `0x180023f88`

## string_xrefs

- `0x1800238d6`: `CComponentEntry::_GetComponentVolumesAndFiles`

## pseudocode

```c
__int64 __fastcall CComponentEntry::_GetComponentVolumesAndFiles(
        CComponentEntry *this,
        struct IVssWMComponent *a2,
        struct CVolumeEntryMap *a3,
        struct CFileDescriptorEntryArray *a4,
        struct CPathCache *a5)
{
  struct IVssWMComponent *v7; // r15
  struct CVolumeEntry *v8; // rbx
  CVolumeEntry *v9; // rsi
  const unsigned __int16 **v10; // rdi
  __int16 v11; // ax
  __int64 v12; // rax
  int v13; // eax
  bool v14; // sf
  unsigned int i; // r12d
  __int16 v16; // r15
  int v17; // eax
  __int16 v18; // ax
  int v19; // r15d
  int v20; // eax
  int v21; // eax
  __int16 v22; // ax
  unsigned int j; // r12d
  int v24; // eax
  int v25; // r15d
  int v26; // eax
  int v27; // eax
  unsigned int k; // r12d
  int v29; // eax
  int v30; // r15d
  int v31; // eax
  int v32; // eax
  unsigned int v33; // r14d
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned __int8 v37[8]; // [rsp+38h] [rbp-51h] BYREF
  struct CVolumeEntry *v38; // [rsp+40h] [rbp-49h] BYREF
  CVolumeEntry *v39; // [rsp+48h] [rbp-41h] BYREF
  struct CFileDescriptorEntry *v40; // [rsp+50h] [rbp-39h] BYREF
  int v41; // [rsp+58h] [rbp-31h] BYREF
  __int16 v42; // [rsp+5Ch] [rbp-2Dh]
  __int16 v43; // [rsp+5Eh] [rbp-2Bh]
  struct IVssWMFiledesc *v44; // [rsp+90h] [rbp+7h] BYREF
  _DWORD *v45; // [rsp+98h] [rbp+Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v41,
    "CComponentEntry::_GetComponentVolumesAndFiles",
    596,
    1);
  v45 = 0;
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v44);
  v7 = a2;
  v8 = 0;
  v9 = 0;
  v38 = 0;
  v10 = 0;
  v39 = 0;
  v40 = 0;
  v11 = 608;
  if ( !a2 || (v42 = 608, v11 = 609, !a3) )
  {
    v41 = -2147024809;
LABEL_6:
    v43 = v11;
    goto LABEL_90;
  }
  v42 = 609;
  v12 = *(_QWORD *)a2;
  v41 = 0;
  v41 = (*(__int64 (__fastcall **)(struct IVssWMComponent *, _DWORD **))(v12 + 24))(a2, &v45);
  v11 = 611;
  if ( v41 < 0 )
    goto LABEL_6;
  v42 = 611;
  v13 = CVolumeEntry::CreateInstance(&v38);
  v8 = v38;
  v14 = v13 < 0;
  v41 = v13;
  v11 = 614;
  if ( v14 )
    goto LABEL_6;
  v42 = 614;
  for ( i = 0; ; ++i )
  {
    v16 = 623;
    if ( i >= v45[13] )
      break;
    v37[0] = 0;
    ATL::CComPtrBase<IVssWMComponent>::Release(&v44);
    v41 = (*(__int64 (__fastcall **)(struct IVssWMComponent *, _QWORD, struct IVssWMFiledesc **))(*(_QWORD *)a2 + 40LL))(
            a2,
            i,
            &v44);
    if ( v41 < 0 )
    {
LABEL_36:
      v43 = v16;
      goto LABEL_89;
    }
    v42 = 623;
    if ( v10 )
    {
      v40 = 0;
      CFileDescriptorEntry::Release((CFileDescriptorEntry *)v10);
    }
    v17 = CFileDescriptorEntry::CreateInstance(&v40);
    v10 = (const unsigned __int16 **)v40;
    v14 = v17 < 0;
    v41 = v17;
    v18 = 626;
    if ( v14 )
    {
LABEL_31:
      v43 = v18;
      goto LABEL_89;
    }
    v42 = 626;
    v19 = CFileDescriptorEntry::_Initialize(v40, v44, a5, v37);
    if ( (unsigned int)(v19 + 2130706163) <= 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids,
          *((_QWORD *)this + 7),
          *((_QWORD *)this + 3));
      CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(a3);
      CSxRefArray<CFileDescriptorEntryArray,CFileDescriptorEntry>::DeleteAll(a4);
      v22 = 637;
      *((_DWORD *)this + 26) = 1;
      *((_DWORD *)this + 36) = v19;
      goto LABEL_88;
    }
    if ( v37[0] )
      *((_DWORD *)this + 29) = 1;
    if ( !v19 )
    {
      v41 = CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(a4, v10);
      v18 = 650;
      if ( v41 < 0 )
        goto LABEL_31;
      v42 = 650;
      v41 = CBsString::Set((struct CVolumeEntry *)((char *)v8 + 8), v10[5]);
      v18 = 653;
      if ( v41 < 0 )
        goto LABEL_31;
      v42 = 653;
      if ( v9 )
      {
        v39 = 0;
        CVolumeEntry::Release(v9);
      }
      v20 = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(a3, v8, &v39);
      v9 = v39;
      v14 = v20 < 0;
      v41 = v20;
      v18 = 656;
      if ( v14 )
        goto LABEL_31;
      v42 = 656;
      if ( v8 == v39 )
      {
        if ( v8 )
        {
          v38 = 0;
          CVolumeEntry::Release(v8);
        }
        v21 = CVolumeEntry::CreateInstance(&v38);
        v8 = v38;
        v14 = v21 < 0;
        v41 = v21;
        v18 = 664;
        if ( v14 )
          goto LABEL_31;
        v42 = 664;
      }
    }
  }
  for ( j = 0; ; ++j )
  {
    v16 = 675;
    if ( j >= v45[14] )
      break;
    v37[0] = 0;
    ATL::CComPtrBase<IVssWMComponent>::Release(&v44);
    v41 = (*(__int64 (__fastcall **)(struct IVssWMComponent *, _QWORD, struct IVssWMFiledesc **))(*(_QWORD *)a2 + 48LL))(
            a2,
            j,
            &v44);
    if ( v41 < 0 )
      goto LABEL_36;
    v42 = 675;
    if ( v10 )
    {
      v40 = 0;
      CFileDescriptorEntry::Release((CFileDescriptorEntry *)v10);
    }
    v24 = CFileDescriptorEntry::CreateInstance(&v40);
    v10 = (const unsigned __int16 **)v40;
    v14 = v24 < 0;
    v41 = v24;
    v18 = 678;
    if ( v14 )
      goto LABEL_31;
    v42 = 678;
    v25 = CFileDescriptorEntry::_Initialize(v40, v44, a5, v37);
    if ( (unsigned int)(v25 + 2130706163) <= 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids,
          *((_QWORD *)this + 7),
          *((_QWORD *)this + 3));
      CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(a3);
      CSxRefArray<CFileDescriptorEntryArray,CFileDescriptorEntry>::DeleteAll(a4);
      v22 = 690;
      *((_DWORD *)this + 26) = 1;
      *((_DWORD *)this + 36) = v25;
      goto LABEL_88;
    }
    if ( v37[0] )
      *((_DWORD *)this + 29) = 1;
    if ( !v25 )
    {
      v41 = CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(a4, v10);
      v18 = 703;
      if ( v41 < 0 )
        goto LABEL_31;
      v42 = 703;
      v41 = CBsString::Set((struct CVolumeEntry *)((char *)v8 + 8), v10[5]);
      v18 = 706;
      if ( v41 < 0 )
        goto LABEL_31;
      v42 = 706;
      if ( v9 )
      {
        v39 = 0;
        CVolumeEntry::Release(v9);
      }
      v26 = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(a3, v8, &v39);
      v9 = v39;
      v14 = v26 < 0;
      v41 = v26;
      v18 = 709;
      if ( v14 )
        goto LABEL_31;
      v42 = 709;
      if ( v8 == v39 )
      {
        if ( v8 )
        {
          v38 = 0;
          CVolumeEntry::Release(v8);
        }
        v27 = CVolumeEntry::CreateInstance(&v38);
        v8 = v38;
        v14 = v27 < 0;
        v41 = v27;
        v18 = 717;
        if ( v14 )
          goto LABEL_31;
        v42 = 717;
      }
    }
  }
  for ( k = 0; ; ++k )
  {
    v16 = 728;
    if ( k >= v45[15] )
    {
      v22 = 774;
      goto LABEL_88;
    }
    v37[0] = 0;
    ATL::CComPtrBase<IVssWMComponent>::Release(&v44);
    v41 = (*(__int64 (__fastcall **)(struct IVssWMComponent *, _QWORD, struct IVssWMFiledesc **))(*(_QWORD *)a2 + 56LL))(
            a2,
            k,
            &v44);
    if ( v41 < 0 )
      goto LABEL_36;
    v42 = 728;
    if ( v10 )
    {
      v40 = 0;
      CFileDescriptorEntry::Release((CFileDescriptorEntry *)v10);
    }
    v29 = CFileDescriptorEntry::CreateInstance(&v40);
    v10 = (const unsigned __int16 **)v40;
    v14 = v29 < 0;
    v41 = v29;
    v18 = 731;
    if ( v14 )
      goto LABEL_31;
    v42 = 731;
    v30 = CFileDescriptorEntry::_Initialize(v40, v44, a5, v37);
    if ( (unsigned int)(v30 + 2130706163) <= 1 )
      break;
    if ( v37[0] )
      *((_DWORD *)this + 29) = 1;
    if ( !v30 )
    {
      v41 = CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(a4, v10);
      v18 = 756;
      if ( v41 < 0 )
        goto LABEL_31;
      v42 = 756;
      v41 = CBsString::Set((struct CVolumeEntry *)((char *)v8 + 8), v10[5]);
      v18 = 759;
      if ( v41 < 0 )
        goto LABEL_31;
      v42 = 759;
      if ( v9 )
      {
        v39 = 0;
        CVolumeEntry::Release(v9);
      }
      v31 = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(a3, v8, &v39);
      v9 = v39;
      v14 = v31 < 0;
      v41 = v31;
      v18 = 762;
      if ( v14 )
        goto LABEL_31;
      v42 = 762;
      if ( v8 == v39 )
      {
        if ( v8 )
        {
          v38 = 0;
          CVolumeEntry::Release(v8);
        }
        v32 = CVolumeEntry::CreateInstance(&v38);
        v8 = v38;
        v14 = v32 < 0;
        v41 = v32;
        v18 = 770;
        if ( v14 )
          goto LABEL_31;
        v42 = 770;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)&WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids,
      *((_QWORD *)this + 7),
      *((_QWORD *)this + 3));
  CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(a3);
  CSxRefArray<CFileDescriptorEntryArray,CFileDescriptorEntry>::DeleteAll(a4);
  v22 = 743;
  *((_DWORD *)this + 26) = 1;
  *((_DWORD *)this + 36) = v30;
LABEL_88:
  v42 = v22;
  v41 = 0;
LABEL_89:
  v7 = a2;
LABEL_90:
  (*(void (__fastcall **)(struct IVssWMComponent *, _DWORD *))(*(_QWORD *)v7 + 32LL))(v7, v45);
  v33 = v41;
  if ( v10 )
    CFileDescriptorEntry::Release((CFileDescriptorEntry *)v10);
  if ( v9 )
    CVolumeEntry::Release(v9);
  if ( v8 )
    CVolumeEntry::Release(v8);
  SysFreeString(0);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v41, v34, v35);
  return v33;
}

```

## disassembly

```asm
0x180023874  mov     rax, rsp
0x180023877  mov     [rax+8], rbx
0x18002387b  mov     [rax+20h], r9
0x18002387f  mov     [rax+10h], rdx
0x180023883  push    rbp
0x180023884  push    rsi
0x180023885  push    rdi
0x180023886  push    r12
0x180023888  push    r13
0x18002388a  push    r14
0x18002388c  push    r15
0x18002388e  lea     rbp, [rax-57h]
0x180023892  sub     rsp, 0A0h
0x180023899  mov     r13, r8
0x18002389c  mov     r14, rcx
0x18002389f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238a6  lea     rax, WPP_GLOBAL_Control
0x1800238ad  cmp     rcx, rax
0x1800238b0  jz      short loc_1800238D0
0x1800238b2  test    dword ptr [rcx+1Ch], 20000000h
0x1800238b9  jz      short loc_1800238D0
0x1800238bb  mov     rcx, [rcx+10h]
0x1800238bf  lea     r8, WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids
0x1800238c6  mov     edx, 0Fh
0x1800238cb  call    WPP_SF_
0x1800238d0  mov     r9d, 1; unsigned __int16
0x1800238d6  lea     rdx, aCcomponententr_0; "CComponentEntry::_GetComponentVolumesAn"...
0x1800238dd  mov     r8d, 254h; unsigned __int16
0x1800238e3  lea     rcx, [rbp+4Fh+var_80]; this
0x1800238e7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800238ec  lea     rcx, [rbp+4Fh+var_48]
0x1800238f0  mov     [rbp+4Fh+var_40], 0
0x1800238f8  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800238fd  mov     r15, [rbp+4Fh+arg_8]
0x180023901  xor     ebx, ebx
0x180023903  xor     esi, esi
0x180023905  mov     [rbp+4Fh+var_98], rbx
0x180023909  xor     edi, edi
0x18002390b  mov     [rbp+4Fh+var_90], rsi
0x18002390f  mov     [rbp+4Fh+var_88], rdi
0x180023913  mov     eax, 260h
0x180023918  test    r15, r15
0x18002391b  jnz     short loc_18002392D
0x18002391d  mov     [rbp+4Fh+var_80], 80070057h
0x180023924  mov     [rbp+4Fh+var_7A], ax
0x180023928  jmp     loc_180023F48
0x18002392d  mov     [rbp+4Fh+var_7C], ax
0x180023931  mov     eax, 261h
0x180023936  test    r13, r13
0x180023939  jz      short loc_18002391D
0x18002393b  mov     [rbp+4Fh+var_7C], ax
0x18002393f  lea     rdx, [rbp+4Fh+var_40]
0x180023943  mov     rax, [r15]
0x180023946  mov     rcx, r15
0x180023949  mov     [rbp+4Fh+var_80], ebx
0x18002394c  mov     rax, [rax+18h]
0x180023950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023955  mov     [rbp+4Fh+var_80], eax
0x180023958  test    eax, eax
0x18002395a  mov     eax, 263h
0x18002395f  js      short loc_180023924
0x180023961  lea     rcx, [rbp+4Fh+var_98]; struct CVolumeEntry **
0x180023965  mov     [rbp+4Fh+var_7C], ax
0x180023969  call    ?CreateInstance@CVolumeEntry@@SAJPEAPEAV1@@Z; CVolumeEntry::CreateInstance(CVolumeEntry * *)
0x18002396e  mov     rbx, [rbp+4Fh+var_98]
0x180023972  test    eax, eax
0x180023974  mov     [rbp+4Fh+var_80], eax
0x180023977  mov     eax, 266h
0x18002397c  js      short loc_180023924
0x18002397e  mov     [rbp+4Fh+var_7C], ax
0x180023982  xor     r12d, r12d
0x180023985  mov     rax, [rbp+4Fh+var_40]
0x180023989  mov     r15d, 26Fh
0x18002398f  cmp     r12d, [rax+34h]
0x180023993  jnb     loc_180023B6F
0x180023999  lea     rcx, [rbp+4Fh+var_48]
0x18002399d  mov     [rbp+4Fh+var_A0], 0
0x1800239a1  call    ?Release@?$CComPtrBase@VIVssWMComponent@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVssWMComponent>::Release(void)
0x1800239a6  mov     rcx, [rbp+4Fh+arg_8]
0x1800239aa  lea     r8, [rbp+4Fh+var_48]
0x1800239ae  mov     edx, r12d
0x1800239b1  mov     rax, [rcx]
0x1800239b4  mov     rax, [rax+28h]
0x1800239b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239bd  mov     [rbp+4Fh+var_80], eax
0x1800239c0  test    eax, eax
0x1800239c2  js      loc_180023B65
0x1800239c8  mov     [rbp+4Fh+var_7C], r15w
0x1800239cd  test    rdi, rdi
0x1800239d0  jz      short loc_1800239E2
0x1800239d2  mov     rcx, rdi; this
0x1800239d5  mov     [rbp+4Fh+var_88], 0
0x1800239dd  call    ?Release@CFileDescriptorEntry@@QEAAKXZ; CFileDescriptorEntry::Release(void)
0x1800239e2  lea     rcx, [rbp+4Fh+var_88]; struct CFileDescriptorEntry **
0x1800239e6  call    ?CreateInstance@CFileDescriptorEntry@@SAJPEAPEAU1@@Z; CFileDescriptorEntry::CreateInstance(CFileDescriptorEntry * *)
0x1800239eb  mov     rdi, [rbp+4Fh+var_88]
0x1800239ef  test    eax, eax
0x1800239f1  mov     [rbp+4Fh+var_80], eax
0x1800239f4  mov     eax, 272h
0x1800239f9  js      loc_180023AF4
0x1800239ff  mov     r8, [rbp+4Fh+arg_20]; struct CPathCache *
0x180023a03  lea     r9, [rbp+4Fh+var_A0]; unsigned __int8 *
0x180023a07  mov     rdx, [rbp+4Fh+var_48]; struct IVssWMFiledesc *
0x180023a0b  mov     rcx, rdi; this
0x180023a0e  mov     [rbp+4Fh+var_7C], ax
0x180023a12  call    ?_Initialize@CFileDescriptorEntry@@QEAAJPEAVIVssWMFiledesc@@PEAVCPathCache@@PEAE@Z; CFileDescriptorEntry::_Initialize(IVssWMFiledesc *,CPathCache *,uchar *)
0x180023a17  mov     r15d, eax
0x180023a1a  lea     ecx, [rax+7EFFFEF3h]
0x180023a20  cmp     ecx, 1
0x180023a23  jbe     loc_180023AFD
0x180023a29  cmp     [rbp+4Fh+var_A0], 0
0x180023a2d  jz      short loc_180023A37
0x180023a2f  mov     dword ptr [r14+74h], 1
0x180023a37  test    r15d, r15d
0x180023a3a  jnz     loc_180023AEC
0x180023a40  mov     rcx, [rbp+4Fh+arg_18]
0x180023a44  mov     rdx, rdi
0x180023a47  call    ?Append@?$CSxRefArray@VCSxVolumeInfoArray@@VCSxVolumeInfo@@@@QEAAJPEAVCSxVolumeInfo@@@Z; CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(CSxVolumeInfo *)
0x180023a4c  mov     [rbp+4Fh+var_80], eax
0x180023a4f  test    eax, eax
0x180023a51  mov     eax, 28Ah
0x180023a56  js      loc_180023AF4
0x180023a5c  mov     [rbp+4Fh+var_7C], ax
0x180023a60  lea     rcx, [rbx+8]; this
0x180023a64  mov     rdx, [rdi+28h]; unsigned __int16 *
0x180023a68  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180023a6d  mov     [rbp+4Fh+var_80], eax
0x180023a70  test    eax, eax
0x180023a72  mov     eax, 28Dh
0x180023a77  js      short loc_180023AF4
0x180023a79  mov     [rbp+4Fh+var_7C], ax
0x180023a7d  test    rsi, rsi
0x180023a80  jz      short loc_180023A92
0x180023a82  mov     rcx, rsi; this
0x180023a85  mov     [rbp+4Fh+var_90], 0
0x180023a8d  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180023a92  lea     r8, [rbp+4Fh+var_90]
0x180023a96  mov     rdx, rbx
0x180023a99  mov     rcx, r13
0x180023a9c  call    ?Insert@?$CSxRefMap@VCVolumeOnDiskPropCacheMap@@VCVolumeOnDiskPropCacheEntry@@@@QEAAJPEAVCVolumeOnDiskPropCacheEntry@@PEAPEAV2@@Z; CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(CVolumeOnDiskPropCacheEntry *,CVolumeOnDiskPropCacheEntry * *)
0x180023aa1  mov     rsi, [rbp+4Fh+var_90]
0x180023aa5  test    eax, eax
0x180023aa7  mov     [rbp+4Fh+var_80], eax
0x180023aaa  mov     eax, 290h
0x180023aaf  js      short loc_180023AF4
0x180023ab1  mov     [rbp+4Fh+var_7C], ax
0x180023ab5  cmp     rbx, rsi
0x180023ab8  jnz     short loc_180023AEC
0x180023aba  test    rbx, rbx
0x180023abd  jz      short loc_180023ACF
0x180023abf  mov     rcx, rbx; this
0x180023ac2  mov     [rbp+4Fh+var_98], 0
0x180023aca  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180023acf  lea     rcx, [rbp+4Fh+var_98]; struct CVolumeEntry **
0x180023ad3  call    ?CreateInstance@CVolumeEntry@@SAJPEAPEAV1@@Z; CVolumeEntry::CreateInstance(CVolumeEntry * *)
0x180023ad8  mov     rbx, [rbp+4Fh+var_98]
0x180023adc  test    eax, eax
0x180023ade  mov     [rbp+4Fh+var_80], eax
0x180023ae1  mov     eax, 298h
0x180023ae6  js      short loc_180023AF4
0x180023ae8  mov     [rbp+4Fh+var_7C], ax
0x180023aec  inc     r12d
0x180023aef  jmp     loc_180023985
0x180023af4  mov     [rbp+4Fh+var_7A], ax
0x180023af8  jmp     loc_180023F44
0x180023afd  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b04  lea     rax, WPP_GLOBAL_Control
0x180023b0b  cmp     rcx, rax
0x180023b0e  jz      short loc_180023B3B
0x180023b10  test    dword ptr [rcx+1Ch], 8000000h
0x180023b17  jz      short loc_180023B3B
0x180023b19  mov     rax, [r14+18h]
0x180023b1d  lea     r8, WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids
0x180023b24  mov     r9, [r14+38h]
0x180023b28  mov     edx, 10h
0x180023b2d  mov     rcx, [rcx+10h]
0x180023b31  mov     [rsp+20h], rax
0x180023b36  call    WPP_SF_SS
0x180023b3b  mov     rcx, r13
0x180023b3e  call    ?DeleteAll@?$CSxRefMap@VCVolumeEntryMap@@VCVolumeEntry@@@@QEAAXXZ; CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(void)
0x180023b43  mov     rcx, [rbp+4Fh+arg_18]
0x180023b47  call    ?DeleteAll@?$CSxRefArray@VCFileDescriptorEntryArray@@UCFileDescriptorEntry@@@@QEAAXXZ; CSxRefArray<CFileDescriptorEntryArray,CFileDescriptorEntry>::DeleteAll(void)
0x180023b4c  mov     eax, 27Dh
0x180023b51  mov     dword ptr [r14+68h], 1
0x180023b59  mov     [r14+90h], r15d
0x180023b60  jmp     loc_180023F39
0x180023b65  mov     [rbp+4Fh+var_7A], r15w
0x180023b6a  jmp     loc_180023F44
0x180023b6f  xor     r12d, r12d
0x180023b72  mov     rax, [rbp+4Fh+var_40]
0x180023b76  mov     r15d, 2A3h
0x180023b7c  cmp     r12d, [rax+38h]
0x180023b80  jnb     loc_180023D51
0x180023b86  lea     rcx, [rbp+4Fh+var_48]
0x180023b8a  mov     [rbp+4Fh+var_A0], 0
0x180023b8e  call    ?Release@?$CComPtrBase@VIVssWMComponent@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVssWMComponent>::Release(void)
0x180023b93  mov     rcx, [rbp+4Fh+arg_8]
0x180023b97  lea     r8, [rbp+4Fh+var_48]
0x180023b9b  mov     edx, r12d
0x180023b9e  mov     rax, [rcx]
0x180023ba1  mov     rax, [rax+30h]
0x180023ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023baa  mov     [rbp+4Fh+var_80], eax
0x180023bad  test    eax, eax
0x180023baf  js      short loc_180023B65
0x180023bb1  mov     [rbp+4Fh+var_7C], r15w
0x180023bb6  test    rdi, rdi
0x180023bb9  jz      short loc_180023BCB
0x180023bbb  mov     rcx, rdi; this
0x180023bbe  mov     [rbp+4Fh+var_88], 0
0x180023bc6  call    ?Release@CFileDescriptorEntry@@QEAAKXZ; CFileDescriptorEntry::Release(void)
0x180023bcb  lea     rcx, [rbp+4Fh+var_88]; struct CFileDescriptorEntry **
0x180023bcf  call    ?CreateInstance@CFileDescriptorEntry@@SAJPEAPEAU1@@Z; CFileDescriptorEntry::CreateInstance(CFileDescriptorEntry * *)
0x180023bd4  mov     rdi, [rbp+4Fh+var_88]
0x180023bd8  test    eax, eax
0x180023bda  mov     [rbp+4Fh+var_80], eax
0x180023bdd  mov     eax, 2A6h
0x180023be2  js      loc_180023AF4
0x180023be8  mov     r8, [rbp+4Fh+arg_20]; struct CPathCache *
0x180023bec  lea     r9, [rbp+4Fh+var_A0]; unsigned __int8 *
0x180023bf0  mov     rdx, [rbp+4Fh+var_48]; struct IVssWMFiledesc *
0x180023bf4  mov     rcx, rdi; this
0x180023bf7  mov     [rbp+4Fh+var_7C], ax
0x180023bfb  call    ?_Initialize@CFileDescriptorEntry@@QEAAJPEAVIVssWMFiledesc@@PEAVCPathCache@@PEAE@Z; CFileDescriptorEntry::_Initialize(IVssWMFiledesc *,CPathCache *,uchar *)
0x180023c00  mov     r15d, eax
0x180023c03  lea     ecx, [rax+7EFFFEF3h]
0x180023c09  cmp     ecx, 1
0x180023c0c  jbe     loc_180023CE9
0x180023c12  cmp     [rbp+4Fh+var_A0], 0
0x180023c16  jz      short loc_180023C20
0x180023c18  mov     dword ptr [r14+74h], 1
0x180023c20  test    r15d, r15d
0x180023c23  jnz     loc_180023CE1
0x180023c29  mov     rcx, [rbp+4Fh+arg_18]
0x180023c2d  mov     rdx, rdi
0x180023c30  call    ?Append@?$CSxRefArray@VCSxVolumeInfoArray@@VCSxVolumeInfo@@@@QEAAJPEAVCSxVolumeInfo@@@Z; CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(CSxVolumeInfo *)
0x180023c35  mov     [rbp+4Fh+var_80], eax
0x180023c38  test    eax, eax
0x180023c3a  mov     eax, 2BFh
0x180023c3f  js      loc_180023AF4
0x180023c45  mov     [rbp+4Fh+var_7C], ax
0x180023c49  lea     rcx, [rbx+8]; this
0x180023c4d  mov     rdx, [rdi+28h]; unsigned __int16 *
0x180023c51  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180023c56  mov     [rbp+4Fh+var_80], eax
0x180023c59  test    eax, eax
0x180023c5b  mov     eax, 2C2h
0x180023c60  js      loc_180023AF4
0x180023c66  mov     [rbp+4Fh+var_7C], ax
0x180023c6a  test    rsi, rsi
0x180023c6d  jz      short loc_180023C7F
0x180023c6f  mov     rcx, rsi; this
0x180023c72  mov     [rbp+4Fh+var_90], 0
0x180023c7a  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180023c7f  lea     r8, [rbp+4Fh+var_90]
0x180023c83  mov     rdx, rbx
0x180023c86  mov     rcx, r13
0x180023c89  call    ?Insert@?$CSxRefMap@VCVolumeOnDiskPropCacheMap@@VCVolumeOnDiskPropCacheEntry@@@@QEAAJPEAVCVolumeOnDiskPropCacheEntry@@PEAPEAV2@@Z; CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(CVolumeOnDiskPropCacheEntry *,CVolumeOnDiskPropCacheEntry * *)
0x180023c8e  mov     rsi, [rbp+4Fh+var_90]
0x180023c92  test    eax, eax
0x180023c94  mov     [rbp+4Fh+var_80], eax
0x180023c97  mov     eax, 2C5h
0x180023c9c  js      loc_180023AF4
0x180023ca2  mov     [rbp+4Fh+var_7C], ax
0x180023ca6  cmp     rbx, rsi
0x180023ca9  jnz     short loc_180023CE1
0x180023cab  test    rbx, rbx
0x180023cae  jz      short loc_180023CC0
0x180023cb0  mov     rcx, rbx; this
0x180023cb3  mov     [rbp+4Fh+var_98], 0
0x180023cbb  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180023cc0  lea     rcx, [rbp+4Fh+var_98]; struct CVolumeEntry **
0x180023cc4  call    ?CreateInstance@CVolumeEntry@@SAJPEAPEAV1@@Z; CVolumeEntry::CreateInstance(CVolumeEntry * *)
0x180023cc9  mov     rbx, [rbp+4Fh+var_98]
0x180023ccd  test    eax, eax
0x180023ccf  mov     [rbp+4Fh+var_80], eax
0x180023cd2  mov     eax, 2CDh
0x180023cd7  js      loc_180023AF4
0x180023cdd  mov     [rbp+4Fh+var_7C], ax
0x180023ce1  inc     r12d
0x180023ce4  jmp     loc_180023B72
0x180023ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023cf0  lea     rax, WPP_GLOBAL_Control
0x180023cf7  cmp     rcx, rax
0x180023cfa  jz      short loc_180023D27
0x180023cfc  test    dword ptr [rcx+1Ch], 8000000h
0x180023d03  jz      short loc_180023D27
0x180023d05  mov     rax, [r14+18h]
0x180023d09  lea     r8, WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids
0x180023d10  mov     r9, [r14+38h]
0x180023d14  mov     edx, 11h
0x180023d19  mov     rcx, [rcx+10h]
0x180023d1d  mov     [rsp+20h], rax
0x180023d22  call    WPP_SF_SS
0x180023d27  mov     rcx, r13
0x180023d2a  call    ?DeleteAll@?$CSxRefMap@VCVolumeEntryMap@@VCVolumeEntry@@@@QEAAXXZ; CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(void)
0x180023d2f  mov     rcx, [rbp+4Fh+arg_18]
0x180023d33  call    ?DeleteAll@?$CSxRefArray@VCFileDescriptorEntryArray@@UCFileDescriptorEntry@@@@QEAAXXZ; CSxRefArray<CFileDescriptorEntryArray,CFileDescriptorEntry>::DeleteAll(void)
0x180023d38  mov     eax, 2B2h
0x180023d3d  mov     dword ptr [r14+68h], 1
  ... truncated ...
```
