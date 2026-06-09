# CBlbEngine::QueryVolumes(ulong *,_BLB_VOLUME_INFO * *)

- ea: `0x14004f230`
- end: `0x14004fa9e`
- name: `?QueryVolumes@CBlbEngine@@UEAAJPEAKPEAPEAU_BLB_VOLUME_INFO@@@Z`
- size: `2158`
- prototype: `__int64 __fastcall(CBlbEngine *__hidden this, unsigned int *, struct _BLB_VOLUME_INFO **)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x140055310`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x140014200`
- `0x1400142d8`
- `0x14003c434`
- `0x14003c54c`
- `0x14003e280`
- `0x140045dec`
- `0x140048394`
- `0x14004f230`
- `0x1400507a4`
- `0x14008b940`
- `0x14008f9ec`
- `0x1400fdd50`
- `0x140121890`
- `0x14012d880`
- `0x14012e834`
- `0x140134cc6`
- `0x140134d20`

## import_xrefs

- `KERNEL32!FindVolumeClose` at `0x14004f4c6`
- `KERNEL32!FindVolumeClose` at `0x14004fa93`
- `KERNEL32!FindVolumeClose` at `0x14004f4c6`
- `KERNEL32!FindVolumeClose` at `0x14004fa93`
- `KERNEL32!FindNextVolumeW` at `0x14004f4a3`
- `KERNEL32!FindNextVolumeW` at `0x14004f92e`
- `KERNEL32!FindNextVolumeW` at `0x14004f4a3`
- `KERNEL32!FindNextVolumeW` at `0x14004f92e`
- `KERNEL32!FindFirstVolumeW` at `0x14004f439`
- `KERNEL32!FindFirstVolumeW` at `0x14004f612`
- `KERNEL32!FindFirstVolumeW` at `0x14004f439`
- `KERNEL32!FindFirstVolumeW` at `0x14004f612`
- `KERNEL32!GetLastError` at `0x14004f448`
- `KERNEL32!GetLastError` at `0x14004f4b2`
- `KERNEL32!GetLastError` at `0x14004f621`
- `KERNEL32!GetLastError` at `0x14004f957`
- `KERNEL32!GetLastError` at `0x14004f448`
- `KERNEL32!GetLastError` at `0x14004f4b2`
- `KERNEL32!GetLastError` at `0x14004f621`
- `KERNEL32!GetLastError` at `0x14004f957`
- `KERNEL32!EnterCriticalSection` at `0x14004f532`
- `KERNEL32!EnterCriticalSection` at `0x14004f532`
- `ole32!CoTaskMemAlloc` at `0x14004f4d6`
- `ole32!CoTaskMemAlloc` at `0x14004f4d6`
- `ole32!CoTaskMemFree` at `0x14004f31d`
- `ole32!CoTaskMemFree` at `0x14004f975`
- `ole32!CoTaskMemFree` at `0x14004f31d`
- `ole32!CoTaskMemFree` at `0x14004f975`
- `ole32!CoTaskMemRealloc` at `0x14004f830`
- `ole32!CoTaskMemRealloc` at `0x14004f830`
- `OLEAUT32!__imp_SysFreeString` at `0x14004f774`
- `OLEAUT32!__imp_SysFreeString` at `0x14004f795`
- `OLEAUT32!__imp_SysFreeString` at `0x14004f774`
- `OLEAUT32!__imp_SysFreeString` at `0x14004f795`

## string_xrefs

- `0x14004f51f`: `base\stor\blb\engine\service\engine.cpp`

## pseudocode

```c
__int64 __fastcall CBlbEngine::QueryVolumes(
        struct _BLB_VOLUME_INFO **this,
        unsigned int *a2,
        struct _BLB_VOLUME_INFO **a3)
{
  unsigned int v3; // r14d
  unsigned int v4; // r15d
  signed int IsInitialized; // edi
  void *v8; // r13
  PVOID *v9; // rcx
  HANDLE FirstVolumeW; // r12
  struct _BLB_VOLUME_INFO *v12; // rax
  struct _BLB_VOLUME_INFO *v13; // rsi
  char v14; // bl
  struct _BLB_VOLUME_INFO *v15; // rcx
  char v16; // bl
  __int64 v17; // rdx
  PVOID *v18; // rbx
  ATL::CComBSTR *v19; // rax
  __int64 v20; // rbx
  ATL::CComBSTR *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // ebx
  struct _BLB_VOLUME_INFO *v24; // rax
  struct _BLB_VOLUME_INFO *v25; // rbx
  const void *v26; // rdx
  signed int LastError; // ebx
  unsigned __int8 v28[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+34h] [rbp-CCh]
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v31; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v32; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v33; // [rsp+48h] [rbp-B8h] BYREF
  struct _BLB_VOLUME_INFO *v34; // [rsp+50h] [rbp-B0h] BYREF
  struct _BLB_VOLUME_INFO **v35; // [rsp+58h] [rbp-A8h]
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v37; // [rsp+68h] [rbp-98h]
  _QWORD v38[2]; // [rsp+70h] [rbp-90h] BYREF
  char v39; // [rsp+80h] [rbp-80h]
  struct _GUID Buf1; // [rsp+88h] [rbp-78h] BYREF
  WCHAR szVolumeName[264]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = 0;
  v35 = a3;
  v31 = 0;
  v4 = 0;
  v33 = 0;
  v34 = 0;
  v28[0] = 0;
  pv = 0;
  v32 = 0;
  v37 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    a3 = v35;
  }
  v39 = 0;
  v38[0] = &CBlbLock::`vftable';
  v38[1] = &g_csGlobal;
  if ( !a2 || (*a2 = 0, !a3) )
  {
    IsInitialized = -2147467261;
LABEL_7:
    v8 = pv;
    goto LABEL_8;
  }
  *a3 = 0;
  IsInitialized = CBlbEngine::IsInitialized((CBlbEngine *)this);
  if ( IsInitialized < 0 )
    goto LABEL_7;
  v29 = g_dwSystemVolumeFlags & 1;
  if ( (int)BlbutilGetSystemVolumeUniqueId((unsigned __int8 **)&pv, &v32) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  }
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    IsInitialized = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    if ( IsInitialized > 0 )
      IsInitialized = (unsigned __int16)IsInitialized | 0x80070000;
    goto LABEL_7;
  }
  do
    ++v4;
  while ( FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) );
  v33 = v4;
  IsInitialized = GetLastError();
  if ( IsInitialized != 18 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    if ( IsInitialized > 0 )
      IsInitialized = (unsigned __int16)IsInitialized | 0x80070000;
    v8 = pv;
    goto LABEL_135;
  }
  FindVolumeClose(FirstVolumeW);
  v12 = (struct _BLB_VOLUME_INFO *)CoTaskMemAlloc((unsigned __int64)v4 << 7);
  v34 = v12;
  v13 = v12;
  if ( !v12 )
  {
    IsInitialized = -2147024882;
    goto LABEL_7;
  }
  memset_0(v12, 0, (unsigned __int64)v4 << 7);
  v14 = v29;
  if ( (_BYTE)v29 )
  {
    if ( !v4 )
      BlbAssert("base\\stor\\blb\\engine\\service\\engine.cpp", 0x3B9u, "cVolume < cMaxVolume");
    EnterCriticalSection(&g_csGlobal);
    v15 = this[13];
    v39 = 1;
    if ( v15 )
    {
      IsInitialized = CopyVolumeInfo(v15, v13);
      if ( IsInitialized < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
        }
        goto LABEL_7;
      }
      v3 = 1;
      v16 = 1;
    }
    else
    {
      v16 = 0;
    }
    CBlbLock::ReleaseLock((CBlbLock *)v38);
    if ( !v16 )
    {
      if ( (int)CBlbEngine::FillVolumeInfo(0, 1u, v13) >= 0 )
      {
        ++v3;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      }
    }
    v14 = v29;
  }
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    IsInitialized = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    if ( IsInitialized > 0 )
      IsInitialized = (unsigned __int16)IsInitialized | 0x80070000;
    goto LABEL_7;
  }
  v8 = pv;
  while ( 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids, szVolumeName);
    }
    if ( !v14 )
      goto LABEL_88;
    Buf1 = 0;
    v17 = -1;
    do
      ++v17;
    while ( szVolumeName[v17] );
    IsInitialized = BlbutilQueryVolumeId(szVolumeName, v17, &Buf1);
    if ( IsInitialized < 0 )
      goto LABEL_74;
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v19 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, &g_guidSystemVolumeId);
      v31 |= 3u;
      v20 = *(_QWORD *)v19;
      v21 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&pv, &Buf1);
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
        *(_QWORD *)v21,
        v20);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    v22 = v31;
    if ( (v31 & 2) != 0 )
    {
      v31 &= ~2u;
      SysFreeString((BSTR)pv);
      v22 = v31;
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (v22 & 1) != 0 )
    {
      v31 = v22 & 0xFFFFFFFE;
      SysFreeString(bstrString);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !memcmp_0(&Buf1, &g_guidSystemVolumeId, 0x10u) )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 4u )
        WPP_SF_(v18[2], 66, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    else
    {
LABEL_88:
      IsInitialized = BlbIsVolumeFixed(szVolumeName, v28);
      if ( IsInitialized < 0 )
        goto LABEL_74;
      if ( v28[0] )
      {
        if ( v3 >= v4 )
        {
          v23 = v4 + 8;
          v24 = (struct _BLB_VOLUME_INFO *)CoTaskMemRealloc(v13, (unsigned __int64)(v4 + 8) << 7);
          v13 = v24;
          if ( !v24 )
          {
            IsInitialized = -2147024882;
            goto LABEL_135;
          }
          memset_0((char *)v24 + 128 * (unsigned __int64)v4, 0, 0x400u);
          v33 = v4 + 8;
          v4 += 8;
          v34 = v13;
          if ( v3 >= v23 )
          {
            IsInitialized = -2147418113;
            goto LABEL_135;
          }
        }
        v25 = (struct _BLB_VOLUME_INFO *)((char *)v13 + 128 * (unsigned __int64)v3);
        IsInitialized = CBlbEngine::FillVolumeInfo(szVolumeName, 0, v25);
        if ( IsInitialized < 0 )
        {
          if ( IsInitialized == -2147024882 )
            goto LABEL_135;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              67,
              (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
              IsInitialized,
              (__int64)szVolumeName);
          }
LABEL_74:
          IsInitialized = 0;
          goto LABEL_105;
        }
        if ( v8 )
        {
          v26 = (const void *)*((_QWORD *)v25 + 12);
          if ( v26 )
          {
            if ( v32 == *((_WORD *)v25 + 46) && !memcmp_0(v8, v26, v32) )
              *((_DWORD *)v25 + 22) |= 2u;
          }
        }
        ++v3;
      }
    }
LABEL_105:
    if ( !FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) )
      break;
    v14 = v29;
  }
  LastError = GetLastError();
  if ( LastError == 18 )
  {
    if ( v3 )
    {
      if ( v3 <= v4 )
        goto LABEL_119;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      }
      IsInitialized = -2147418113;
    }
    else
    {
      if ( v13 )
      {
        CoTaskMemFree(v13);
        v13 = 0;
        goto LABEL_120;
      }
LABEL_119:
      IsInitialized = BlbFillCriticalVolumesInfo<_BLB_VOLUME_INFO>(v13, v3);
      if ( IsInitialized >= 0 )
      {
LABEL_120:
        v34 = 0;
        *v37 = v3;
        *v35 = v13;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    if ( LastError > 0 )
      IsInitialized = (unsigned __int16)LastError | 0x80070000;
    else
      IsInitialized = LastError;
  }
LABEL_135:
  FindVolumeClose(FirstVolumeW);
LABEL_8:
  FreeVolumes(&v34, &v33);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( IsInitialized >= 0 )
  {
LABEL_15:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      goto LABEL_15;
    }
LABEL_16:
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x200) != 0 && *((_BYTE *)v9 + 25) >= 4u )
      WPP_SF_(v9[2], 71, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  }
  CBlbLock::~CBlbLock((CBlbLock *)v38);
  return (unsigned int)IsInitialized;
}

```

## disassembly

```asm
0x14004f230  mov     [rsp-8+arg_18], rbx
0x14004f235  push    rbp
0x14004f236  push    rsi
0x14004f237  push    rdi
0x14004f238  push    r12
0x14004f23a  push    r13
0x14004f23c  push    r14
0x14004f23e  push    r15
0x14004f240  lea     rbp, [rsp-1C0h]
0x14004f248  sub     rsp, 2C0h
0x14004f24f  mov     rax, cs:__security_cookie
0x14004f256  xor     rax, rsp
0x14004f259  mov     [rbp+1F0h+var_40], rax
0x14004f260  xor     r14d, r14d
0x14004f263  mov     [rsp+2F0h+var_298], r8
0x14004f268  mov     [rsp+2F0h+var_2B0], r14d
0x14004f26d  mov     r15d, r14d
0x14004f270  mov     [rsp+2F0h+var_2A8], r14d
0x14004f275  mov     rbx, rdx
0x14004f278  mov     [rsp+2F0h+var_2A0], r14
0x14004f27d  mov     r13, rcx
0x14004f280  mov     [rsp+2F0h+var_2C0], r14b
0x14004f285  mov     [rsp+2F0h+pv], r14
0x14004f28a  mov     [rsp+2F0h+var_2AC], r14w
0x14004f290  mov     [rsp+2F0h+var_288], rdx
0x14004f295  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f29c  lea     rsi, WPP_GLOBAL_Control
0x14004f2a3  cmp     rcx, rsi
0x14004f2a6  jz      short loc_14004F2D0
0x14004f2a8  test    dword ptr [rcx+1Ch], 200h
0x14004f2af  jz      short loc_14004F2D0
0x14004f2b1  cmp     byte ptr [rcx+19h], 4
0x14004f2b5  jb      short loc_14004F2D0
0x14004f2b7  mov     rcx, [rcx+10h]
0x14004f2bb  lea     edx, [r14+39h]
0x14004f2bf  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004f2c6  call    WPP_SF_
0x14004f2cb  mov     r8, [rsp+2F0h+var_298]
0x14004f2d0  mov     [rbp+1F0h+var_270], r14b
0x14004f2d4  lea     rax, ??_7CBlbLock@@6B@; const CBlbLock::`vftable'
0x14004f2db  mov     [rsp+2F0h+var_280], rax
0x14004f2e0  lea     rax, ?g_csGlobal@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csGlobal
0x14004f2e7  mov     [rsp+2F0h+var_278], rax
0x14004f2ec  test    rbx, rbx
0x14004f2ef  jnz     loc_14004F3BD
0x14004f2f5  mov     edi, 80004003h
0x14004f2fa  lea     rbx, WPP_GLOBAL_Control
0x14004f301  mov     r13, [rsp+2F0h+pv]
0x14004f306  lea     rdx, [rsp+2F0h+var_2A8]; unsigned int *
0x14004f30b  lea     rcx, [rsp+2F0h+var_2A0]; struct _BLB_VOLUME_INFO **
0x14004f310  call    ?FreeVolumes@@YAXAEAPEAU_BLB_VOLUME_INFO@@AEAK@Z; FreeVolumes(_BLB_VOLUME_INFO * &,ulong &)
0x14004f315  test    r13, r13
0x14004f318  jz      short loc_14004F323
0x14004f31a  mov     rcx, r13; pv
0x14004f31d  call    cs:__imp_CoTaskMemFree
0x14004f323  test    edi, edi
0x14004f325  jns     short loc_14004F357
0x14004f327  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f32e  cmp     rcx, rbx
0x14004f331  jz      short loc_14004F387
0x14004f333  test    byte ptr [rcx+1Ch], 1
0x14004f337  jz      short loc_14004F35E
0x14004f339  cmp     byte ptr [rcx+19h], 2
0x14004f33d  jb      short loc_14004F35E
0x14004f33f  mov     rcx, [rcx+10h]
0x14004f343  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004f34a  mov     edx, 46h ; 'F'
0x14004f34f  mov     r9d, edi
0x14004f352  call    WPP_SF_d
0x14004f357  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f35e  cmp     rcx, rbx
0x14004f361  jz      short loc_14004F387
0x14004f363  test    dword ptr [rcx+1Ch], 200h
0x14004f36a  jz      short loc_14004F387
0x14004f36c  cmp     byte ptr [rcx+19h], 4
0x14004f370  jb      short loc_14004F387
0x14004f372  mov     rcx, [rcx+10h]
0x14004f376  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004f37d  mov     edx, 47h ; 'G'
0x14004f382  call    WPP_SF_
0x14004f387  lea     rcx, [rsp+2F0h+var_280]; this
0x14004f38c  call    ??1CBlbLock@@UEAA@XZ; CBlbLock::~CBlbLock(void)
0x14004f391  mov     eax, edi
0x14004f393  mov     rcx, [rbp+1F0h+var_40]
0x14004f39a  xor     rcx, rsp; StackCookie
0x14004f39d  call    __security_check_cookie
0x14004f3a2  mov     rbx, [rsp+2F0h+arg_18]
0x14004f3aa  add     rsp, 2C0h
0x14004f3b1  pop     r15
0x14004f3b3  pop     r14
0x14004f3b5  pop     r13
0x14004f3b7  pop     r12
0x14004f3b9  pop     rdi
0x14004f3ba  pop     rsi
0x14004f3bb  pop     rbp
0x14004f3bc  retn
0x14004f3bd  mov     [rbx], r14d
0x14004f3c0  test    r8, r8
0x14004f3c3  jz      loc_14004F2F5
0x14004f3c9  mov     rcx, r13; this
0x14004f3cc  mov     [r8], r14
0x14004f3cf  call    ?IsInitialized@CBlbEngine@@QEAAJXZ; CBlbEngine::IsInitialized(void)
0x14004f3d4  mov     edi, eax
0x14004f3d6  test    eax, eax
0x14004f3d8  js      loc_14004F2FA
0x14004f3de  mov     eax, cs:?g_dwSystemVolumeFlags@@3KA; ulong g_dwSystemVolumeFlags
0x14004f3e4  lea     rdx, [rsp+2F0h+var_2AC]; unsigned __int16 *
0x14004f3e9  and     eax, 1
0x14004f3ec  lea     rcx, [rsp+2F0h+pv]; unsigned __int8 **
0x14004f3f1  mov     [rsp+2F0h+var_2BC], eax
0x14004f3f5  call    ?BlbutilGetSystemVolumeUniqueId@@YAJPEAPEAEAEAG@Z; BlbutilGetSystemVolumeUniqueId(uchar * *,ushort &)
0x14004f3fa  test    eax, eax
0x14004f3fc  jns     short loc_14004F42E
0x14004f3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f405  cmp     rcx, rsi
0x14004f408  jz      short loc_14004F42E
0x14004f40a  test    byte ptr [rcx+1Ch], 1
0x14004f40e  jz      short loc_14004F42E
0x14004f410  cmp     byte ptr [rcx+19h], 3
0x14004f414  jb      short loc_14004F42E
0x14004f416  mov     rcx, [rcx+10h]
0x14004f41a  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004f421  mov     edx, 3Ah ; ':'
0x14004f426  mov     r9d, eax
0x14004f429  call    WPP_SF_d
0x14004f42e  mov     ebx, 104h
0x14004f433  lea     rcx, [rbp+1F0h+szVolumeName]; lpszVolumeName
0x14004f437  mov     edx, ebx; cchBufferLength
0x14004f439  call    cs:__imp_FindFirstVolumeW
0x14004f43f  mov     r12, rax
0x14004f442  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004f446  jnz     short loc_14004F496
0x14004f448  call    cs:__imp_GetLastError
0x14004f44e  mov     edi, eax
0x14004f450  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f457  cmp     rcx, rsi
0x14004f45a  jz      short loc_14004F480
0x14004f45c  test    byte ptr [rcx+1Ch], 1
0x14004f460  jz      short loc_14004F480
0x14004f462  cmp     byte ptr [rcx+19h], 2
0x14004f466  jb      short loc_14004F480
0x14004f468  mov     rcx, [rcx+10h]
0x14004f46c  lea     edx, [r12+3Ch]
0x14004f471  mov     r9d, eax
0x14004f474  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004f47b  call    WPP_SF_d
0x14004f480  test    edi, edi
0x14004f482  jle     loc_14004F2FA
0x14004f488  movzx   edi, di
0x14004f48b  or      edi, 80070000h
0x14004f491  jmp     loc_14004F2FA
0x14004f496  mov     r8d, ebx; cchBufferLength
0x14004f499  lea     rdx, [rbp+1F0h+szVolumeName]; lpszVolumeName
0x14004f49d  mov     rcx, r12; hFindVolume
0x14004f4a0  inc     r15d
0x14004f4a3  call    cs:__imp_FindNextVolumeW
0x14004f4a9  test    eax, eax
0x14004f4ab  jnz     short loc_14004F496
0x14004f4ad  mov     [rsp+2F0h+var_2A8], r15d
0x14004f4b2  call    cs:__imp_GetLastError
0x14004f4b8  mov     edi, eax
0x14004f4ba  cmp     eax, 12h
0x14004f4bd  jnz     loc_14004FA47
0x14004f4c3  mov     rcx, r12; hFindVolume
0x14004f4c6  call    cs:__imp_FindVolumeClose
0x14004f4cc  mov     ebx, r15d
0x14004f4cf  shl     rbx, 7
0x14004f4d3  mov     rcx, rbx; cb
0x14004f4d6  call    cs:__imp_CoTaskMemAlloc
0x14004f4dc  mov     [rsp+2F0h+var_2A0], rax
0x14004f4e1  mov     rsi, rax
0x14004f4e4  test    rax, rax
0x14004f4e7  jnz     short loc_14004F4F3
0x14004f4e9  mov     edi, 8007000Eh
0x14004f4ee  jmp     loc_14004F2FA
0x14004f4f3  mov     r8, rbx; Size
0x14004f4f6  xor     edx, edx; Val
0x14004f4f8  mov     rcx, rsi; void *
0x14004f4fb  call    memset_0
0x14004f500  mov     ebx, [rsp+2F0h+var_2BC]
0x14004f504  xor     edi, edi
0x14004f506  test    bl, bl
0x14004f508  jz      loc_14004F609
0x14004f50e  test    r15d, r15d
0x14004f511  jnz     short loc_14004F52B
0x14004f513  lea     r8, aCvolumeCmaxvol; "cVolume < cMaxVolume"
0x14004f51a  mov     edx, 3B9h; unsigned int
0x14004f51f  lea     rcx, aBaseStorBlbEng_40; "base\\stor\\blb\\engine\\service\\engin"...
0x14004f526  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14004f52b  lea     rcx, ?g_csGlobal@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004f532  call    cs:__imp_EnterCriticalSection
0x14004f538  mov     rcx, [r13+68h]; struct _BLB_VOLUME_INFO *
0x14004f53c  mov     [rbp+1F0h+var_270], 1
0x14004f540  test    rcx, rcx
0x14004f543  jz      short loc_14004F5A8
0x14004f545  mov     rdx, rsi; struct _BLB_VOLUME_INFO *
0x14004f548  call    ?CopyVolumeInfo@@YAJAEAU_BLB_VOLUME_INFO@@0@Z; CopyVolumeInfo(_BLB_VOLUME_INFO &,_BLB_VOLUME_INFO &)
0x14004f54d  mov     edi, eax
0x14004f54f  test    eax, eax
0x14004f551  jns     short loc_14004F59B
0x14004f553  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f55a  lea     rbx, WPP_GLOBAL_Control
0x14004f561  cmp     rcx, rbx
0x14004f564  jz      loc_14004F301
0x14004f56a  test    byte ptr [rcx+1Ch], 1
0x14004f56e  jz      loc_14004F301
0x14004f574  cmp     byte ptr [rcx+19h], 2
0x14004f578  jb      loc_14004F301
0x14004f57e  mov     rcx, [rcx+10h]
0x14004f582  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004f589  mov     edx, 3Dh ; '='
0x14004f58e  mov     r9d, eax
0x14004f591  call    WPP_SF_d
0x14004f596  jmp     loc_14004F301
0x14004f59b  mov     r14d, 1
0x14004f5a1  xor     edi, edi
0x14004f5a3  mov     bl, r14b
0x14004f5a6  jmp     short loc_14004F5AB
0x14004f5a8  mov     bl, dil
0x14004f5ab  lea     rcx, [rsp+2F0h+var_280]; this
0x14004f5b0  call    ?ReleaseLock@CBlbLock@@QEAAXXZ; CBlbLock::ReleaseLock(void)
0x14004f5b5  test    bl, bl
0x14004f5b7  jnz     short loc_14004F605
0x14004f5b9  mov     r8, rsi; struct _BLB_VOLUME_INFO *
0x14004f5bc  mov     dl, 1; unsigned __int8
0x14004f5be  xor     ecx, ecx; unsigned __int16 *
0x14004f5c0  call    ?FillVolumeInfo@CBlbEngine@@CAJPEAGEPEAU_BLB_VOLUME_INFO@@@Z; CBlbEngine::FillVolumeInfo(ushort *,uchar,_BLB_VOLUME_INFO *)
0x14004f5c5  test    eax, eax
0x14004f5c7  jns     short loc_14004F602
0x14004f5c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f5d0  lea     rdx, WPP_GLOBAL_Control
0x14004f5d7  cmp     rcx, rdx
0x14004f5da  jz      short loc_14004F605
0x14004f5dc  test    byte ptr [rcx+1Ch], 1
0x14004f5e0  jz      short loc_14004F605
0x14004f5e2  cmp     byte ptr [rcx+19h], 3
0x14004f5e6  jb      short loc_14004F605
0x14004f5e8  mov     rcx, [rcx+10h]
0x14004f5ec  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004f5f3  mov     edx, 3Eh ; '>'
0x14004f5f8  mov     r9d, eax
0x14004f5fb  call    WPP_SF_d
0x14004f600  jmp     short loc_14004F605
0x14004f602  inc     r14d
0x14004f605  mov     ebx, [rsp+2F0h+var_2BC]
0x14004f609  mov     edx, 104h; cchBufferLength
0x14004f60e  lea     rcx, [rbp+1F0h+szVolumeName]; lpszVolumeName
0x14004f612  call    cs:__imp_FindFirstVolumeW
0x14004f618  mov     r12, rax
0x14004f61b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004f61f  jnz     short loc_14004F676
0x14004f621  call    cs:__imp_GetLastError
0x14004f627  mov     edi, eax
0x14004f629  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f630  lea     rbx, WPP_GLOBAL_Control
0x14004f637  cmp     rcx, rbx
0x14004f63a  jz      short loc_14004F660
0x14004f63c  test    byte ptr [rcx+1Ch], 1
0x14004f640  jz      short loc_14004F660
0x14004f642  cmp     byte ptr [rcx+19h], 2
0x14004f646  jb      short loc_14004F660
0x14004f648  mov     rcx, [rcx+10h]
0x14004f64c  lea     edx, [r12+40h]
0x14004f651  mov     r9d, eax
0x14004f654  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004f65b  call    WPP_SF_d
0x14004f660  test    edi, edi
0x14004f662  jle     loc_14004F301
0x14004f668  movzx   edi, di
0x14004f66b  or      edi, 80070000h
0x14004f671  jmp     loc_14004F301
0x14004f676  mov     r13, [rsp+2F0h+pv]
0x14004f67b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f682  lea     rax, WPP_GLOBAL_Control
0x14004f689  cmp     rcx, rax
0x14004f68c  jz      short loc_14004F6B3
0x14004f68e  test    byte ptr [rcx+1Ch], 1
0x14004f692  jz      short loc_14004F6B3
0x14004f694  cmp     byte ptr [rcx+19h], 4
0x14004f698  jb      short loc_14004F6B3
0x14004f69a  mov     rcx, [rcx+10h]
0x14004f69e  lea     r9, [rbp+1F0h+szVolumeName]
0x14004f6a2  mov     edx, 40h ; '@'
0x14004f6a7  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004f6ae  call    WPP_SF_S
0x14004f6b3  test    bl, bl
0x14004f6b5  jz      loc_14004F7FA
0x14004f6bb  xorps   xmm0, xmm0
0x14004f6be  lea     rax, [rbp+1F0h+szVolumeName]
0x14004f6c2  movups  xmmword ptr [rbp+1F0h+Buf1.Data1], xmm0
0x14004f6c6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14004f6ca  inc     rdx; unsigned int
0x14004f6cd  cmp     [rax+rdx*2], di
0x14004f6d1  jnz     short loc_14004F6CA
0x14004f6d3  lea     r8, [rbp+1F0h+Buf1]; struct _GUID *
0x14004f6d7  lea     rcx, [rbp+1F0h+szVolumeName]; unsigned __int16 *
0x14004f6db  call    ?BlbutilQueryVolumeId@@YAJPEAGKPEAU_GUID@@@Z; BlbutilQueryVolumeId(ushort *,ulong,_GUID *)
0x14004f6e0  mov     edi, eax
0x14004f6e2  xor     eax, eax
0x14004f6e4  test    edi, edi
  ... truncated ...
```
