# CBlbBackupAsync::PerformVHDPruning(_BLBCAT_BACKUP_SET_INFO *)

- ea: `0x14002e92c`
- end: `0x14002f0cc`
- name: `?PerformVHDPruning@CBlbBackupAsync@@AEAAJPEAU_BLBCAT_BACKUP_SET_INFO@@@Z`
- size: `1952`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this, struct _BLBCAT_BACKUP_SET_INFO *)`
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006a64`
- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000c030`
- `0x14000c574`
- `0x14000d5b8`
- `0x14000efd0`
- `0x1400115f0`
- `0x140012e74`
- `0x140013008`
- `0x14002667c`
- `0x140027d94`
- `0x14002c38c`
- `0x14002d6c4`
- `0x14002e92c`
- `0x14003c69c`
- `0x1400869f0`
- `0x140086b88`
- `0x140088d0c`
- `0x14009e734`
- `0x1400f7914`
- `0x1400fa48c`
- `0x1400fbb90`
- `0x1400ff774`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002eca3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002ecf0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002eca3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002ecf0`
- `ole32!CoTaskMemFree` at `0x14002eb13`
- `ole32!CoTaskMemFree` at `0x14002eea0`
- `ole32!CoTaskMemFree` at `0x14002eeee`
- `ole32!CoTaskMemFree` at `0x14002ef27`
- `ole32!CoTaskMemFree` at `0x14002ef89`
- `ole32!CoTaskMemFree` at `0x14002efc2`
- `ole32!CoTaskMemFree` at `0x14002eb13`
- `ole32!CoTaskMemFree` at `0x14002eea0`
- `ole32!CoTaskMemFree` at `0x14002eeee`
- `ole32!CoTaskMemFree` at `0x14002ef27`
- `ole32!CoTaskMemFree` at `0x14002ef89`
- `ole32!CoTaskMemFree` at `0x14002efc2`

## string_xrefs

- `0x14002e997`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002e9b8`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002ebe4`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002ee04`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002ed7b`: `base\stor\blb\engine\service\prune.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CBlbBackupAsync::PerformVHDPruning(CBlbBackupAsync *this, struct _BLBCAT_BACKUP_SET_INFO *a2)
{
  void *v4; // r14
  int ComponentsList; // ebx
  char v6; // r15
  unsigned int i; // r12d
  __int64 v8; // rsi
  __int64 v9; // r13
  __int64 v10; // r8
  __int64 v11; // rdx
  CBlbPruningContext *v12; // r15
  struct _FILETIME v13; // r8
  _QWORD *v14; // rsi
  unsigned int j; // r14d
  LPVOID *v16; // rax
  __int64 v17; // rax
  unsigned int k; // r14d
  LPVOID *v19; // rax
  __int64 v20; // rax
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  struct _BLBCAT_COMPONENT_INFO *v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+90h] [rbp-70h]
  CBlbPruningContext *v33; // [rsp+98h] [rbp-68h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36[3]; // [rsp+B0h] [rbp-50h] BYREF
  int v37; // [rsp+C8h] [rbp-38h]
  struct _GUID Buf1; // [rsp+D0h] [rbp-30h] BYREF
  void *v39[3]; // [rsp+E0h] [rbp-20h] BYREF
  int v40; // [rsp+F8h] [rbp-8h]
  void *v41[3]; // [rsp+100h] [rbp+0h] BYREF
  int v42; // [rsp+118h] [rbp+18h]
  void *v43[3]; // [rsp+120h] [rbp+20h] BYREF
  int v44; // [rsp+138h] [rbp+38h]
  unsigned __int8 v45; // [rsp+190h] [rbp+90h] BYREF
  struct _BLBCAT_BACKUP_SET_INFO *v46; // [rsp+198h] [rbp+98h]
  char v47; // [rsp+1A0h] [rbp+A0h]
  unsigned int v48; // [rsp+1A8h] [rbp+A8h] BYREF

  v46 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 843, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x4D40u, "pBsiCat");
  if ( (*((_BYTE *)this + 340) & 2) != 0 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x4D41u, "!CHUNKED(m_ulFeatures)");
  v4 = 0;
  pv = 0;
  v24 = 0;
  v48 = 0;
  v33 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  *(_QWORD *)v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset(v41, 0, sizeof(v41));
  v42 = 0;
  memset(v43, 0, sizeof(v43));
  v44 = 0;
  memset(v39, 0, sizeof(v39));
  v40 = 0;
  memset(v36, 0, sizeof(v36));
  v37 = 0;
  ComponentsList = CBlbBackupAsync::GetComponentsList(this, &v24, &v48);
  if ( ComponentsList >= 0 )
  {
    ComponentsList = CBlbBackupItemsHelper::GetSpecsInfo(*((unsigned __int16 **)this + 107));
    if ( ComponentsList >= 0 )
    {
      ComponentsList = CBlbBackupItemsHelper::GetWriterSpecs(
                         v48,
                         v24,
                         *((_QWORD *)this + 57),
                         (unsigned int)(*((_BYTE *)this + 390) != 0) + 2,
                         0,
                         v25);
      if ( ComponentsList >= 0 )
      {
        v6 = 0;
        v47 = 0;
        for ( i = 0; i < *((_DWORD *)this + 92); ++i )
        {
          v22 = 0;
          v45 = 0;
          v8 = *((_QWORD *)this + 27) + 368LL * i;
          if ( *(_DWORD *)(v8 + 20) != 12 )
          {
            if ( v4 )
            {
              CoTaskMemFree(v4);
              pv = 0;
            }
            Buf1 = *(struct _GUID *)(v8 + 68);
            ComponentsList = BlbGetVhdPath(
                               &Buf1,
                               *(_DWORD *)(v8 + 84),
                               *((unsigned __int16 **)this + 59),
                               (unsigned __int16 **)&pv);
            v4 = pv;
            if ( ComponentsList < 0 )
              goto LABEL_51;
            ComponentsList = CBlbVolumeBackupContext::IsPruningRequired(
                               (CBlbVolumeBackupContext *)v8,
                               (unsigned __int16 *)pv,
                               (CBlbBackupAsync *)((char *)this + 40),
                               *(_BYTE *)(v8 + 256),
                               &v45);
            if ( ComponentsList < 0 )
              goto LABEL_51;
            if ( v45 )
            {
              *(_BYTE *)(v8 + 345) = 1;
              ComponentsList = CBlbBackupAsync::MountAndDeleteShadowsOnVhd(
                                 this,
                                 (struct CBlbVolumeBackupContext *)v8,
                                 (PCWSTR)v4);
              if ( ComponentsList < 0 )
                goto LABEL_51;
              ComponentsList = CBlbBackupAsync::GetVolumeMapIndex(this, (struct CBlbVolumeBackupContext *)v8, &v22);
              if ( ComponentsList < 0 )
                goto LABEL_51;
              v9 = *((_QWORD *)this + 105) + 24LL * v22;
              if ( !v9 )
                BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x4DADu, "pVolumeMap");
              ComponentsList = BlbutilSlashTerminatePath(*(unsigned __int16 **)(v8 + 224), (LPVOID *)(v9 + 8));
              if ( ComponentsList < 0 )
                goto LABEL_51;
              if ( !v6 )
              {
                CBlbApplicationBackupAsync::GetFileSpecsForComponents(*((_QWORD *)this + 104), v39, v10);
                LOBYTE(v11) = 1;
                ComponentsList = CBlbBackupItemsHelper::ConvertFileSpecs(v39, v11, v41);
                if ( ComponentsList < 0 )
                  goto LABEL_51;
                ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(v36, v25);
                ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(v36, v41);
                v47 = 1;
              }
              ComponentsList = ATL::CComObject<CBlbPruningContext>::CreateInstance(&v33);
              if ( ComponentsList < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 844, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
                }
                goto LABEL_51;
              }
              v12 = v33;
              (*(void (__fastcall **)(CBlbPruningContext *))(*(_QWORD *)v33 + 8LL))(v33);
              ComponentsList = CBlbPruningContext::Initialize(v12, this, v13, v46);
              if ( ComponentsList < 0 )
                goto LABEL_51;
              GetSystemTimeAsFileTime((LPFILETIME)(v8 + 188));
              Buf1 = *(struct _GUID *)(v8 + 68);
              ComponentsList = CBlbPruningContext::PerformPruning(v12, (__int64)&v29, (__int64)v36);
              if ( ComponentsList < 0 )
                goto LABEL_51;
              GetSystemTimeAsFileTime((LPFILETIME)(v8 + 196));
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v35 = *(_QWORD *)(v8 + 188);
                v34 = *(_QWORD *)(v8 + 196);
                WPP_SF_q(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  845,
                  &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                  (v34 - v35) / 0x2710uLL);
              }
              v14 = (_QWORD *)(v8 + 352);
              if ( !v14 )
                BlbAssert("base\\stor\\blb\\engine\\service\\prune.cpp", 0x171u, "pcNumberOfFilesProcessed");
              *v14 = *((_QWORD *)v12 + 13);
              (*(void (__fastcall **)(CBlbPruningContext *))(*(_QWORD *)v12 + 16LL))(v12);
              v33 = 0;
              v6 = v47;
            }
          }
        }
        if ( !*((_QWORD *)this + 104) )
          BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x4DF6u, "m_pAppBackupContext != NULL");
        ComponentsList = CBlbApplicationBackupAsync::PerformVHDPruningForComponents(
                           *((_QWORD *)this + 104),
                           (__int64)&v29,
                           (__int64)v25,
                           v46,
                           *((unsigned __int16 **)this + 59),
                           *((_DWORD *)this + 92),
                           *((_QWORD *)this + 27));
        if ( ComponentsList < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 846, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
LABEL_51:
        if ( v4 )
          CoTaskMemFree(v4);
      }
    }
  }
  if ( v24 )
    FreeComponentInfo(v48, v24);
  for ( j = 0; j < v30; ++j )
  {
    if ( *(_QWORD *)ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](&v29, j) )
    {
      v16 = (LPVOID *)ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](&v29, j);
      CoTaskMemFree(*v16);
      *(_QWORD *)ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](&v29, j) = 0;
    }
    if ( *(_QWORD *)(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](&v29, j) + 8) )
    {
      v17 = ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](&v29, j);
      CoTaskMemFree(*(LPVOID *)(v17 + 8));
      *(_QWORD *)(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](&v29, j) + 8) = 0;
    }
  }
  ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(&v29, 0);
  for ( k = 0; k < v26; ++k )
  {
    if ( *(_QWORD *)ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](v25, k) )
    {
      v19 = (LPVOID *)ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](v25, k);
      CoTaskMemFree(*v19);
      *(_QWORD *)ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](v25, k) = 0;
    }
    if ( *(_QWORD *)(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](v25, k) + 8) )
    {
      v20 = ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](v25, k);
      CoTaskMemFree(*(LPVOID *)(v20 + 8));
      *(_QWORD *)(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::operator[](v25, k) + 8) = 0;
    }
  }
  ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(v25, 0);
  ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(v36, 0);
  if ( ComponentsList < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 847, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    CBlbAsync::SetResult((CBlbBackupAsync *)((char *)this + 24), -2139618995, ComponentsList, 0);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 848, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>((void **)v36);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v39);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v43);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v41);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>((void **)v25);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>((void **)&v29);
  return (unsigned int)ComponentsList;
}

```

## disassembly

```asm
0x14002e92c  mov     [rsp-8+arg_8], rdx
0x14002e931  push    rbp
0x14002e932  push    rbx
0x14002e933  push    rsi
0x14002e934  push    rdi
0x14002e935  push    r12
0x14002e937  push    r13
0x14002e939  push    r14
0x14002e93b  push    r15
0x14002e93d  lea     rbp, [rsp-48h]
0x14002e942  sub     rsp, 148h
0x14002e949  mov     rsi, rdx
0x14002e94c  mov     rdi, rcx
0x14002e94f  lea     r15, WPP_GLOBAL_Control
0x14002e956  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e95d  cmp     rcx, r15
0x14002e960  jz      short loc_14002E983
0x14002e962  test    byte ptr [rcx+1Ch], 1
0x14002e966  jz      short loc_14002E983
0x14002e968  cmp     byte ptr [rcx+19h], 4
0x14002e96c  jb      short loc_14002E983
0x14002e96e  mov     edx, 34Bh
0x14002e973  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002e97a  mov     rcx, [rcx+10h]
0x14002e97e  call    WPP_SF_
0x14002e983  xor     r13d, r13d
0x14002e986  test    rsi, rsi
0x14002e989  jnz     short loc_14002E9A3
0x14002e98b  lea     r8, aPbsicat_0; "pBsiCat"
0x14002e992  mov     edx, 4D40h; unsigned int
0x14002e997  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002e99e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002e9a3  test    byte ptr [rdi+154h], 2
0x14002e9aa  jz      short loc_14002E9C4
0x14002e9ac  lea     r8, aChunkedMUlfeat; "!CHUNKED(m_ulFeatures)"
0x14002e9b3  mov     edx, 4D41h; unsigned int
0x14002e9b8  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002e9bf  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002e9c4  mov     r14, r13
0x14002e9c7  mov     [rsp+180h+pv], r13
0x14002e9cc  mov     [rsp+180h+var_130], r13
0x14002e9d1  mov     [rbp+80h+arg_18], r13d
0x14002e9d8  mov     [rbp+80h+var_E8], r13
0x14002e9dc  mov     [rsp+180h+var_108], r13
0x14002e9e1  mov     [rbp+80h+var_100], r13
0x14002e9e5  mov     [rbp+80h+var_F8], r13
0x14002e9e9  mov     [rbp+80h+var_F0], r13d
0x14002e9ed  mov     qword ptr [rsp+180h+var_128], r13
0x14002e9f2  mov     [rsp+180h+var_120], r13
0x14002e9f7  mov     [rsp+180h+var_118], r13
0x14002e9fc  mov     [rsp+180h+var_110], r13d
0x14002ea01  mov     [rbp+80h+var_80], r13
0x14002ea05  mov     [rbp+80h+var_78], r13
0x14002ea09  mov     [rbp+80h+var_70], r13
0x14002ea0d  mov     [rbp+80h+var_68], r13d
0x14002ea11  mov     [rbp+80h+var_60], r13
0x14002ea15  mov     [rbp+80h+var_58], r13
0x14002ea19  mov     [rbp+80h+var_50], r13
0x14002ea1d  mov     [rbp+80h+var_48], r13d
0x14002ea21  mov     [rbp+80h+var_A0], r13
0x14002ea25  mov     [rbp+80h+var_98], r13
0x14002ea29  mov     [rbp+80h+var_90], r13
0x14002ea2d  mov     [rbp+80h+var_88], r13d
0x14002ea31  mov     [rbp+80h+var_D0], r13
0x14002ea35  mov     [rbp+80h+var_C8], r13
0x14002ea39  mov     [rbp+80h+var_C0], r13
0x14002ea3d  mov     [rbp+80h+var_B8], r13d
0x14002ea41  lea     r8, [rbp+80h+arg_18]; unsigned int *
0x14002ea48  lea     rdx, [rsp+180h+var_130]; struct _BLBCAT_COMPONENT_INFO **
0x14002ea4d  mov     rcx, rdi; this
0x14002ea50  call    ?GetComponentsList@CBlbBackupAsync@@AEAAJPEAPEAU_BLBCAT_COMPONENT_INFO@@PEAK@Z; CBlbBackupAsync::GetComponentsList(_BLBCAT_COMPONENT_INFO * *,ulong *)
0x14002ea55  mov     ebx, eax
0x14002ea57  test    eax, eax
0x14002ea59  js      loc_14002EEA6
0x14002ea5f  lea     r9, [rsp+180h+var_108]
0x14002ea64  lea     r8, [rbp+80h+arg_0]
0x14002ea6b  lea     rdx, [rbp+80h+arg_10]
0x14002ea72  mov     rcx, [rdi+358h]; unsigned __int16 *
0x14002ea79  call    ?GetSpecsInfo@CBlbBackupItemsHelper@@SAJPEAGPEAE1AEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@@Z; CBlbBackupItemsHelper::GetSpecsInfo(ushort *,uchar *,uchar *,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &)
0x14002ea7e  mov     ebx, eax
0x14002ea80  test    eax, eax
0x14002ea82  js      loc_14002EEA6
0x14002ea88  mov     al, [rdi+186h]
0x14002ea8e  neg     al
0x14002ea90  sbb     r9d, r9d
0x14002ea93  neg     r9d
0x14002ea96  add     r9d, 2
0x14002ea9a  lea     rax, [rsp+180h+var_128]
0x14002ea9f  mov     [rsp+180h+var_158], rax
0x14002eaa4  mov     byte ptr [rsp+180h+var_160], r13b
0x14002eaa9  mov     r8, [rdi+1C8h]
0x14002eab0  mov     rdx, [rsp+180h+var_130]
0x14002eab5  mov     ecx, [rbp+80h+arg_18]
0x14002eabb  call    ?GetWriterSpecs@CBlbBackupItemsHelper@@SAJKPEAU_BLBCAT_COMPONENT_INFO@@PEAU_SPP_METADATA_PROP@@W4SpecsType@1@EAEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@@Z; CBlbBackupItemsHelper::GetWriterSpecs(ulong,_BLBCAT_COMPONENT_INFO *,_SPP_METADATA_PROP *,CBlbBackupItemsHelper::SpecsType,uchar,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &)
0x14002eac0  mov     ebx, eax
0x14002eac2  test    eax, eax
0x14002eac4  js      loc_14002EEA6
0x14002eaca  mov     r15b, r13b
0x14002eacd  mov     [rbp+80h+arg_10], r13b
0x14002ead4  mov     r12d, r13d
0x14002ead7  cmp     r12d, [rdi+170h]
0x14002eade  jnb     loc_14002EDEF
0x14002eae4  mov     [rsp+180h+var_140], r13d
0x14002eae9  mov     [rbp+80h+arg_0], r13b
0x14002eaf0  mov     eax, r12d
0x14002eaf3  imul    rsi, rax, 170h
0x14002eafa  add     rsi, [rdi+0D8h]
0x14002eb01  cmp     dword ptr [rsi+14h], 0Ch
0x14002eb05  jz      loc_14002EDA8
0x14002eb0b  test    r14, r14
0x14002eb0e  jz      short loc_14002EB1E
0x14002eb10  mov     rcx, r14; pv
0x14002eb13  call    cs:__imp_CoTaskMemFree
0x14002eb19  mov     [rsp+180h+pv], r13
0x14002eb1e  movups  xmm0, xmmword ptr [rsi+44h]
0x14002eb22  movdqu  xmmword ptr [rbp+80h+Buf1.Data1], xmm0
0x14002eb27  lea     r9, [rsp+180h+pv]; unsigned __int16 **
0x14002eb2c  mov     r8, [rdi+1D8h]; unsigned __int16 *
0x14002eb33  mov     edx, [rsi+54h]; unsigned int
0x14002eb36  lea     rcx, [rbp+80h+Buf1]; Buf1
0x14002eb3a  call    ?BlbGetVhdPath@@YAJU_GUID@@KPEAGPEAPEAG@Z; BlbGetVhdPath(_GUID,ulong,ushort *,ushort * *)
0x14002eb3f  mov     ebx, eax
0x14002eb41  mov     r14, [rsp+180h+pv]
0x14002eb46  test    eax, eax
0x14002eb48  js      loc_14002EE91
0x14002eb4e  lea     r8, [rdi+28h]; struct CBlbImpersonationHelper *
0x14002eb52  lea     rax, [rbp+80h+arg_0]
0x14002eb59  mov     [rsp+180h+var_160], rax; unsigned __int8 *
0x14002eb5e  mov     r9b, [rsi+100h]; unsigned __int8
0x14002eb65  mov     rdx, r14; unsigned __int16 *
0x14002eb68  mov     rcx, rsi; this
0x14002eb6b  call    ?IsPruningRequired@CBlbVolumeBackupContext@@QEAAJPEAGPEAVCBlbImpersonationHelper@@EPEAE@Z; CBlbVolumeBackupContext::IsPruningRequired(ushort *,CBlbImpersonationHelper *,uchar,uchar *)
0x14002eb70  mov     ebx, eax
0x14002eb72  test    eax, eax
0x14002eb74  js      loc_14002EE91
0x14002eb7a  cmp     [rbp+80h+arg_0], r13b
0x14002eb81  jz      loc_14002EDA8
0x14002eb87  mov     byte ptr [rsi+159h], 1
0x14002eb8e  mov     r8, r14; PCWSTR
0x14002eb91  mov     rdx, rsi; struct CBlbVolumeBackupContext *
0x14002eb94  mov     rcx, rdi; this
0x14002eb97  call    ?MountAndDeleteShadowsOnVhd@CBlbBackupAsync@@AEAAJPEAVCBlbVolumeBackupContext@@PEBG@Z; CBlbBackupAsync::MountAndDeleteShadowsOnVhd(CBlbVolumeBackupContext *,ushort const *)
0x14002eb9c  mov     ebx, eax
0x14002eb9e  test    eax, eax
0x14002eba0  js      loc_14002EE91
0x14002eba6  lea     r8, [rsp+180h+var_140]; unsigned int *
0x14002ebab  mov     rdx, rsi; struct CBlbVolumeBackupContext *
0x14002ebae  mov     rcx, rdi; this
0x14002ebb1  call    ?GetVolumeMapIndex@CBlbBackupAsync@@AEAAJPEAVCBlbVolumeBackupContext@@PEAK@Z; CBlbBackupAsync::GetVolumeMapIndex(CBlbVolumeBackupContext *,ulong *)
0x14002ebb6  mov     ebx, eax
0x14002ebb8  test    eax, eax
0x14002ebba  js      loc_14002EE91
0x14002ebc0  mov     eax, [rsp+180h+var_140]
0x14002ebc4  lea     rcx, [rax+rax*2]
0x14002ebc8  mov     rax, [rdi+348h]
0x14002ebcf  lea     r13, [rax+rcx*8]
0x14002ebd3  test    r13, r13
0x14002ebd6  jnz     short loc_14002EBF0
0x14002ebd8  lea     r8, aPvolumemap; "pVolumeMap"
0x14002ebdf  mov     edx, 4DADh; unsigned int
0x14002ebe4  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002ebeb  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002ebf0  lea     rdx, [r13+8]; unsigned __int16 **
0x14002ebf4  mov     rcx, [rsi+0E0h]; unsigned __int16 *
0x14002ebfb  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14002ec00  mov     ebx, eax
0x14002ec02  test    eax, eax
0x14002ec04  js      loc_14002EE8E
0x14002ec0a  test    r15b, r15b
0x14002ec0d  jnz     short loc_14002EC5A
0x14002ec0f  lea     rdx, [rbp+80h+var_A0]
0x14002ec13  mov     rcx, [rdi+340h]
0x14002ec1a  call    ?GetFileSpecsForComponents@CBlbApplicationBackupAsync@@QEAAXAEAV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@@Z; CBlbApplicationBackupAsync::GetFileSpecsForComponents(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> &)
0x14002ec1f  lea     r8, [rbp+80h+var_80]
0x14002ec23  mov     dl, 1
0x14002ec25  lea     rcx, [rbp+80h+var_A0]
0x14002ec29  call    ?ConvertFileSpecs@CBlbBackupItemsHelper@@SAJAEAV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@EAEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@3@@Z; CBlbBackupItemsHelper::ConvertFileSpecs(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> &,uchar,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &)
0x14002ec2e  mov     ebx, eax
0x14002ec30  test    eax, eax
0x14002ec32  js      loc_14002EE8E
0x14002ec38  lea     rdx, [rsp+180h+var_128]
0x14002ec3d  lea     rcx, [rbp+80h+var_D0]
0x14002ec41  call    ?Append@?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@QEAA_KAEBV12@@Z; ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> const &)
0x14002ec46  lea     rdx, [rbp+80h+var_80]
0x14002ec4a  lea     rcx, [rbp+80h+var_D0]
0x14002ec4e  call    ?Append@?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@QEAA_KAEBV12@@Z; ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> const &)
0x14002ec53  mov     [rbp+80h+arg_10], 1
0x14002ec5a  lea     rcx, [rbp+80h+var_E8]
0x14002ec5e  call    ?CreateInstance@?$CComObject@VCBlbPruningContext@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CBlbPruningContext>::CreateInstance(ATL::CComObject<CBlbPruningContext> * *)
0x14002ec63  mov     ebx, eax
0x14002ec65  test    eax, eax
0x14002ec67  js      loc_14002EDB0
0x14002ec6d  mov     r15, [rbp+80h+var_E8]
0x14002ec71  mov     rax, [r15]
0x14002ec74  mov     rcx, r15
0x14002ec77  mov     rax, [rax+8]
0x14002ec7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ec80  mov     r9, [rbp+80h+arg_8]; struct _BLBCAT_BACKUP_SET_INFO *
0x14002ec87  mov     rdx, rdi; struct CBlbBackupAsync *
0x14002ec8a  mov     rcx, r15; this
0x14002ec8d  call    ?Initialize@CBlbPruningContext@@QEAAJPEAVCBlbBackupAsync@@U_FILETIME@@PEAU_BLBCAT_BACKUP_SET_INFO@@@Z; CBlbPruningContext::Initialize(CBlbBackupAsync *,_FILETIME,_BLBCAT_BACKUP_SET_INFO *)
0x14002ec92  mov     ebx, eax
0x14002ec94  test    eax, eax
0x14002ec96  js      loc_14002EE8E
0x14002ec9c  lea     rcx, [rsi+0BCh]; lpSystemTimeAsFileTime
0x14002eca3  call    cs:__imp_GetSystemTimeAsFileTime
0x14002eca9  movups  xmm0, xmmword ptr [rsi+44h]
0x14002ecad  movdqu  xmmword ptr [rbp+80h+Buf1.Data1], xmm0
0x14002ecb2  lea     rax, [rbp+80h+var_D0]
0x14002ecb6  mov     [rsp+180h+var_158], rax; __int64
0x14002ecbb  lea     rax, [rsp+180h+var_108]
0x14002ecc0  mov     [rsp+180h+var_160], rax; __int64
0x14002ecc5  lea     r9, [rbp+80h+var_60]
0x14002ecc9  mov     r8, r13
0x14002eccc  lea     rdx, [rbp+80h+Buf1]
0x14002ecd0  mov     rcx, r15; this
0x14002ecd3  call    ?PerformPruning@CBlbPruningContext@@QEAAJU_GUID@@PEAU_BLBSRV_VOLUME_MAP@@AEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@22@Z; CBlbPruningContext::PerformPruning(_GUID,_BLBSRV_VOLUME_MAP *,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &)
0x14002ecd8  mov     ebx, eax
0x14002ecda  xor     r13d, r13d
0x14002ecdd  test    eax, eax
0x14002ecdf  js      loc_14002EE91
0x14002ece5  lea     rbx, [rsi+0BCh]
0x14002ecec  lea     rcx, [rbx+8]; lpSystemTimeAsFileTime
0x14002ecf0  call    cs:__imp_GetSystemTimeAsFileTime
0x14002ecf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ecfd  lea     rax, WPP_GLOBAL_Control
0x14002ed04  cmp     rcx, rax
0x14002ed07  jz      short loc_14002ED66
0x14002ed09  test    byte ptr [rcx+1Ch], 1
0x14002ed0d  jz      short loc_14002ED66
0x14002ed0f  cmp     byte ptr [rcx+19h], 4
0x14002ed13  jb      short loc_14002ED66
0x14002ed15  mov     eax, [rbx]
0x14002ed17  mov     dword ptr [rbp+80h+var_D8], eax
0x14002ed1a  mov     eax, [rsi+0C0h]
0x14002ed20  mov     dword ptr [rbp+80h+var_D8+4], eax
0x14002ed23  mov     eax, [rsi+0C4h]
0x14002ed29  mov     dword ptr [rbp+80h+var_E0], eax
0x14002ed2c  mov     eax, [rsi+0C8h]
0x14002ed32  mov     dword ptr [rbp+80h+var_E0+4], eax
0x14002ed35  mov     rdx, [rbp+80h+var_E0]
0x14002ed39  sub     rdx, [rbp+80h+var_D8]
0x14002ed3d  mov     rax, 346DC5D63886594Bh
0x14002ed47  mul     rdx
0x14002ed4a  mov     r9, rdx
0x14002ed4d  shr     r9, 0Bh
0x14002ed51  mov     edx, 34Dh
0x14002ed56  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002ed5d  mov     rcx, [rcx+10h]
0x14002ed61  call    WPP_SF_q
0x14002ed66  add     rsi, 160h
0x14002ed6d  jnz     short loc_14002ED87
0x14002ed6f  lea     r8, aPcnumberoffile; "pcNumberOfFilesProcessed"
0x14002ed76  mov     edx, 171h; unsigned int
0x14002ed7b  lea     rcx, aBaseStorBlbEng_15; "base\\stor\\blb\\engine\\service\\prune"...
0x14002ed82  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002ed87  mov     rax, [r15+68h]
0x14002ed8b  mov     [rsi], rax
0x14002ed8e  mov     rax, [r15]
0x14002ed91  mov     rcx, r15
0x14002ed94  mov     rax, [rax+10h]
0x14002ed98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ed9d  mov     [rbp+80h+var_E8], r13
0x14002eda1  mov     r15b, [rbp+80h+arg_10]
0x14002eda8  inc     r12d
0x14002edab  jmp     loc_14002EAD7
0x14002edb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002edb7  lea     r15, WPP_GLOBAL_Control
0x14002edbe  cmp     rcx, r15
0x14002edc1  jz      short loc_14002EDE7
0x14002edc3  test    byte ptr [rcx+1Ch], 1
0x14002edc7  jz      short loc_14002EDE7
0x14002edc9  cmp     byte ptr [rcx+19h], 2
0x14002edcd  jb      short loc_14002EDE7
0x14002edcf  mov     edx, 34Ch
0x14002edd4  mov     r9d, eax
0x14002edd7  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002edde  mov     rcx, [rcx+10h]
0x14002ede2  call    WPP_SF_d
0x14002ede7  xor     r13d, r13d
0x14002edea  jmp     loc_14002EE98
0x14002edef  cmp     [rdi+340h], r13
0x14002edf6  jnz     short loc_14002EE10
0x14002edf8  lea     r8, aMPappbackupcon_0; "m_pAppBackupContext != NULL"
0x14002edff  mov     edx, 4DF6h; unsigned int
0x14002ee04  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002ee0b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002ee10  mov     rax, [rdi+0D8h]
0x14002ee17  mov     [rsp+180h+var_150], rax; __int64
0x14002ee1c  mov     eax, [rdi+170h]
0x14002ee22  mov     dword ptr [rsp+180h+var_158], eax; int
0x14002ee26  mov     rax, [rdi+1D8h]
0x14002ee2d  mov     [rsp+180h+var_160], rax; unsigned __int16 *
0x14002ee32  mov     r9, [rbp+80h+arg_8]; int
0x14002ee39  lea     r8, [rsp+180h+var_128]; int
0x14002ee3e  lea     rdx, [rsp+180h+var_108]; int
0x14002ee43  mov     rcx, [rdi+340h]; int
0x14002ee4a  call    ?PerformVHDPruningForComponents@CBlbApplicationBackupAsync@@AEAAJAEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@0PEAU_BLBCAT_BACKUP_SET_INFO@@PEAGKPEAVCBlbVolumeBackupContext@@@Z; CBlbApplicationBackupAsync::PerformVHDPruningForComponents(ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,_BLBCAT_BACKUP_SET_INFO *,ushort *,ulong,CBlbVolumeBackupContext *)
0x14002ee4f  mov     ebx, eax
0x14002ee51  test    eax, eax
  ... truncated ...
```
