# CBlbSystemStateRestoreAsync::MountVolumesInBackupSet(CBlbEngine *,ulong,ulong *,_BLBSRV_VOLUME_MAP * *,ushort * * *)

- ea: `0x140077044`
- end: `0x14007783b`
- name: `?MountVolumesInBackupSet@CBlbSystemStateRestoreAsync@@AEAAJPEAVCBlbEngine@@KPEAKPEAPEAU_BLBSRV_VOLUME_MAP@@PEAPEAPEAG@Z`
- size: `2039`
- prototype: `__int64 __usercall@<rax>(CBlbSystemStateRestoreAsync *__hidden this@<rcx>, struct CBlbEngine *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, struct _BLBSRV_VOLUME_MAP **, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x140075000`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000b25c`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x140014200`
- `0x140014260`
- `0x140026c8c`
- `0x140077044`
- `0x1400889f0`
- `0x140088d0c`
- `0x14008ba2c`
- `0x1400fdf2c`
- `0x14012e834`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14007727c`
- `ole32!CoTaskMemAlloc` at `0x1400772b5`
- `ole32!CoTaskMemAlloc` at `0x14007727c`
- `ole32!CoTaskMemAlloc` at `0x1400772b5`
- `ole32!CoTaskMemFree` at `0x14007734d`
- `ole32!CoTaskMemFree` at `0x14007762e`
- `ole32!CoTaskMemFree` at `0x140077647`
- `ole32!CoTaskMemFree` at `0x140077682`
- `ole32!CoTaskMemFree` at `0x140077724`
- `ole32!CoTaskMemFree` at `0x14007773b`
- `ole32!CoTaskMemFree` at `0x140077751`
- `ole32!CoTaskMemFree` at `0x140077773`
- `ole32!CoTaskMemFree` at `0x140077782`
- `ole32!CoTaskMemFree` at `0x140077790`
- `ole32!CoTaskMemFree` at `0x14007734d`
- `ole32!CoTaskMemFree` at `0x14007762e`
- `ole32!CoTaskMemFree` at `0x140077647`
- `ole32!CoTaskMemFree` at `0x140077682`
- `ole32!CoTaskMemFree` at `0x140077724`
- `ole32!CoTaskMemFree` at `0x14007773b`
- `ole32!CoTaskMemFree` at `0x140077751`
- `ole32!CoTaskMemFree` at `0x140077773`
- `ole32!CoTaskMemFree` at `0x140077782`
- `ole32!CoTaskMemFree` at `0x140077790`
- `OLEAUT32!__imp_SysFreeString` at `0x1400771e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400775d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400771e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400775d0`

## string_xrefs

- `0x140077119`: `base\stor\blb\engine\service\systemstaterestore.cpp`
- `0x140077138`: `base\stor\blb\engine\service\systemstaterestore.cpp`
- `0x140077224`: `base\stor\blb\engine\service\systemstaterestore.cpp`
- `0x14007780c`: `base\stor\blb\engine\service\systemstaterestore.cpp`

## pseudocode

```c
__int64 __fastcall CBlbSystemStateRestoreAsync::MountVolumesInBackupSet(
        unsigned __int16 **this,
        struct CBlbEngine *a2,
        __int64 a3,
        unsigned int *a4,
        struct _BLBSRV_VOLUME_MAP **a5,
        unsigned __int16 ***a6)
{
  unsigned __int16 *v6; // r14
  int v7; // r12d
  unsigned int v10; // r13d
  unsigned __int16 *v11; // rdx
  PVOID *v12; // r8
  unsigned int v13; // edi
  __int64 v14; // rdx
  ATL::CComBSTR *v15; // rax
  char *v16; // rsi
  unsigned __int16 **v17; // r15
  unsigned int v18; // edi
  unsigned __int16 **v19; // rax
  int v20; // eax
  unsigned int v21; // ecx
  unsigned __int16 *v22; // rdx
  struct _GUID *v23; // r13
  unsigned int Data1; // edx
  bool v25; // zf
  void *ImpersonationToken; // rax
  __int128 v27; // xmm1
  __int64 v28; // rcx
  __int64 v29; // rdx
  const unsigned __int16 *v30; // rcx
  int v31; // eax
  LPVOID *v32; // r13
  int v33; // eax
  ATL::CComBSTR *v34; // rax
  void *v35; // rcx
  unsigned int i; // r12d
  __int64 v37; // rbx
  unsigned int v38; // r12d
  struct CBlbEngine *v39; // rdi
  __int64 v40; // r15
  int v41; // eax
  __int64 v42; // rcx
  char v43; // r8
  int v44; // eax
  void *v45; // rcx
  void *v46; // rcx
  int VolumeName; // [rsp+70h] [rbp-90h]
  unsigned int v49; // [rsp+74h] [rbp-8Ch]
  int v50; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v51; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v52; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v53; // [rsp+8Ch] [rbp-74h] BYREF
  struct _GUID *v54; // [rsp+90h] [rbp-70h] BYREF
  int v55; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp-58h] BYREF
  struct CBlbEngine *v58; // [rsp+B0h] [rbp-50h]
  struct _BLB_VOLUME_INFO *v59; // [rsp+B8h] [rbp-48h] BYREF
  BSTR Catalog; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v61; // [rsp+C8h] [rbp-38h]
  struct _BLBSRV_VOLUME_MAP **v62; // [rsp+D0h] [rbp-30h]
  unsigned __int16 ***v63; // [rsp+D8h] [rbp-28h]
  struct _GUID v64; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v65; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v66[264]; // [rsp+100h] [rbp+0h] BYREF

  v6 = 0;
  v7 = 0;
  v62 = a5;
  v63 = a6;
  v55 = 0;
  v61 = a4;
  v58 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
  }
  v54 = 0;
  v53 = 1;
  pv = 0;
  v55 = 0;
  Catalog = (BSTR)CBlbAsync::GetCatalog((CBlbAsync *)this);
  v51 = 0;
  v10 = 0;
  v49 = 0;
  v59 = 0;
  v52 = 0;
  if ( !a5 )
    BlbAssert("base\\stor\\blb\\engine\\service\\systemstaterestore.cpp", 0x3D9u, "ppVolumeMap");
  if ( !a6 )
    BlbAssert("base\\stor\\blb\\engine\\service\\systemstaterestore.cpp", 0x3DAu, "ppwszVolumesInBackup");
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  v11 = this[71];
  if ( !*((_DWORD *)v11 + 16) )
    goto LABEL_23;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  v13 = 0;
  do
  {
    v14 = 120LL * v13 + *((_QWORD *)v11 + 9);
    if ( (*(_BYTE *)(v14 + 16) & 0x20) != 0 )
    {
      if ( *(_BYTE *)(v14 + 41) || *((_DWORD *)this + 117) == 4 )
      {
        ++v10;
      }
      else
      {
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 4u )
        {
          v15 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct _GUID *)v14);
          v7 |= 1u;
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids,
            *(_QWORD *)v15);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (v7 & 1) != 0 )
        {
          v7 &= ~1u;
          SysFreeString(bstrString);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
    v11 = this[71];
    ++v13;
  }
  while ( v13 < *((_DWORD *)v11 + 16) );
  v6 = v51;
  v49 = v10;
  if ( !v10 )
LABEL_23:
    BlbAssert("base\\stor\\blb\\engine\\service\\systemstaterestore.cpp", 0x3F6u, "cVolumeMap > 0");
  *((_DWORD *)this + 93) = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
  }
  v16 = (char *)CoTaskMemAlloc(24LL * v10);
  if ( !v16 )
  {
    v17 = 0;
LABEL_30:
    v18 = -2147024882;
    VolumeName = -2147024882;
    goto LABEL_67;
  }
  memset_0(v16, 0, 24LL * v10);
  v19 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v10);
  v17 = v19;
  if ( !v19 )
    goto LABEL_30;
  memset_0(v19, 0, 8LL * v10);
  VolumeName = (*(__int64 (__fastcall **)(struct CBlbEngine *, unsigned int *, struct _BLB_VOLUME_INFO **))(*(_QWORD *)v58 + 64LL))(
                 v58,
                 &v52,
                 &v59);
  v18 = VolumeName;
  if ( VolumeName >= 0 )
  {
    v20 = 0;
    v21 = 0;
    v50 = 0;
    while ( 1 )
    {
      v22 = this[71];
      LODWORD(bstrString) = v21;
      if ( v21 >= *((_DWORD *)v22 + 16) )
        break;
      v23 = (struct _GUID *)(*((_QWORD *)v22 + 9) + 120LL * v21);
      if ( (v23[1].Data1 & 0x20) != 0 && (v23[1].Data1 & 1) == 0 && (v23[2].Data4[1] || *((_DWORD *)this + 117) == 4) )
      {
        CoTaskMemFree(pv);
        Data1 = v23[1].Data1;
        pv = 0;
        VolumeName = BlbutilQueryVolumeName(v23, Data1, (unsigned __int16 **)&pv, 0);
        v18 = VolumeName;
        if ( VolumeName < 0 )
          goto LABEL_66;
        if ( v54 )
          FreeVolumes((struct _BLB_VOLUME_INFO **)&v54, &v53);
        v25 = *((_DWORD *)this + 117) == 4;
        v54 = 0;
        v53 = 1;
        if ( !v25 )
        {
          VolumeName = BlbFindLocalVolumeMatch(
                         v58,
                         0,
                         (struct _BLBCAT_VOLUME_INFO *)v23,
                         *((_DWORD *)this + 114) == 0,
                         v59,
                         v52,
                         (struct _BLB_VOLUME_INFO **)&v54);
          v18 = VolumeName;
          if ( VolumeName < 0 )
            goto LABEL_66;
        }
        v66[0] = 0;
        ImpersonationToken = CBlbImpersonationHelper::GetImpersonationToken((CBlbImpersonationHelper *)(this + 2));
        v27 = *((_OWORD *)this + 16);
        v28 = *(_QWORD *)v58;
        v64 = *v23;
        v65 = v27;
        VolumeName = (*(__int64 (__fastcall **)(struct CBlbEngine *, __int128 *, struct _GUID *, _QWORD, unsigned __int16 *, __int64, void *, int, BSTR, int *, unsigned __int16 *, _DWORD))(v28 + 344))(
                       v58,
                       &v65,
                       &v64,
                       0,
                       this[53],
                       v29,
                       ImpersonationToken,
                       260,
                       Catalog,
                       &v55,
                       v66,
                       v29);
        v18 = VolumeName;
        if ( VolumeName < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v34 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&Catalog, v23);
            LOBYTE(v7) = v7 | 2;
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              (unsigned int)WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids,
              *(_QWORD *)v34,
              VolumeName);
          }
          if ( (v7 & 2) != 0 )
            SysFreeString(Catalog);
          (*((void (__fastcall **)(char *, __int64, _QWORD))this[17] + 8))(
            (char *)this + 136,
            2155348228LL,
            (unsigned int)VolumeName);
LABEL_66:
          v10 = v49;
          goto LABEL_67;
        }
        v30 = *(const unsigned __int16 **)v23[1].Data4;
        if ( v30 )
          v31 = BlbutilDuplicateString(v30, &v51, 0);
        else
          v31 = BlbutilQueryVolumeName(v23, v23[1].Data1, &v51, 0);
        v6 = v51;
        v18 = v31;
        VolumeName = v31;
        if ( v31 < 0 )
          goto LABEL_66;
        v32 = (LPVOID *)&v16[24 * v50];
        VolumeName = BlbutilSlashTerminatePath(v51, v32);
        v18 = VolumeName;
        if ( VolumeName < 0 )
          goto LABEL_66;
        v33 = *((_DWORD *)this + 117) == 4
            ? BlbutilSlashTerminatePath(this[56], v32 + 1)
            : BlbutilQueryVolumeName(v54, *(_DWORD *)v54[5].Data4, (unsigned __int16 **)v32 + 1, 0);
        VolumeName = v33;
        v18 = v33;
        if ( v33 < 0 )
          goto LABEL_66;
        VolumeName = BlbutilSlashTerminatePath(v66, v32 + 2);
        v18 = VolumeName;
        if ( VolumeName < 0 )
          goto LABEL_66;
        VolumeName = BlbutilDuplicateString((const unsigned __int16 *)pv, &v17[v50], 0);
        v18 = VolumeName;
        if ( VolumeName < 0 )
          goto LABEL_66;
        v20 = ++v50;
      }
      else
      {
        v20 = v50;
      }
      v21 = (_DWORD)bstrString + 1;
    }
    v10 = v49;
    if ( v20 != v49 )
      BlbAssert("base\\stor\\blb\\engine\\service\\systemstaterestore.cpp", 0x49Bu, "iVolumeMap == cVolumeMap");
    *v61 = v49;
    *v62 = (struct _BLBSRV_VOLUME_MAP *)v16;
    v16 = 0;
    *v63 = v17;
    v17 = 0;
  }
LABEL_67:
  FreeVolumes(&v59, &v52);
  v35 = 0;
  if ( v54 )
  {
    FreeVolumes((struct _BLB_VOLUME_INFO **)&v54, &v53);
    v35 = 0;
  }
  if ( v17 )
  {
    for ( i = 0; i < v10; v17[v37] = 0 )
    {
      v37 = i;
      CoTaskMemFree(v17[i++]);
    }
    CoTaskMemFree(v17);
    v35 = 0;
  }
  if ( v16 )
  {
    v38 = 0;
    if ( v10 )
    {
      v39 = v58;
      v40 = 0;
      do
      {
        if ( *(void **)&v16[24 * v40 + 16] != v35 )
        {
          if ( v6 )
          {
            CoTaskMemFree(v6);
            v51 = 0;
          }
          v41 = BlbutilDuplicateString(*(const unsigned __int16 **)&v16[24 * v40 + 16], &v51, 0);
          v6 = v51;
          v42 = -1;
          v43 = v41;
          do
            ++v42;
          while ( v51[v42] );
          v51[v42 - 1] = 0;
          if ( v41 < 0
            || (v44 = (*(__int64 (__fastcall **)(struct CBlbEngine *, unsigned __int16 *, _QWORD))(*(_QWORD *)v39 + 360LL))(
                        v39,
                        v6,
                        (unsigned int)v41),
                v43 = v44,
                v44 < 0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                39,
                (unsigned int)WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids,
                (_DWORD)v6,
                v43);
            }
          }
        }
        v45 = *(void **)&v16[24 * v40 + 16];
        if ( v45 )
        {
          CoTaskMemFree(v45);
          *(_QWORD *)&v16[24 * v40 + 16] = 0;
        }
        v46 = *(void **)&v16[24 * v40 + 8];
        if ( v46 )
        {
          CoTaskMemFree(v46);
          *(_QWORD *)&v16[24 * v40 + 8] = 0;
        }
        v35 = *(void **)&v16[24 * v40];
        if ( v35 )
        {
          CoTaskMemFree(v35);
          v35 = 0;
          *(_QWORD *)&v16[24 * v40] = 0;
        }
        ++v38;
        ++v40;
      }
      while ( v38 < v10 );
      v18 = VolumeName;
    }
    CoTaskMemFree(v16);
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
  }
  return v18;
}

```

## disassembly

```asm
0x140077044  mov     [rsp-8+arg_10], rbx
0x140077049  push    rbp
0x14007704a  push    rsi
0x14007704b  push    rdi
0x14007704c  push    r12
0x14007704e  push    r13
0x140077050  push    r14
0x140077052  push    r15
0x140077054  lea     rbp, [rsp-220h]
0x14007705c  sub     rsp, 320h
0x140077063  mov     rax, cs:__security_cookie
0x14007706a  xor     rax, rsp
0x14007706d  mov     [rbp+250h+var_40], rax
0x140077074  mov     rsi, [rbp+250h+arg_20]
0x14007707b  xor     r14d, r14d
0x14007707e  mov     rdi, [rbp+250h+arg_28]
0x140077085  mov     r12d, r14d
0x140077088  mov     [rbp+250h+var_280], rsi
0x14007708c  mov     r15, r9
0x14007708f  mov     [rbp+250h+var_278], rdi
0x140077093  mov     rbx, rcx
0x140077096  mov     [rbp+250h+var_2B8], r14d
0x14007709a  mov     [rbp+250h+var_288], r9
0x14007709e  mov     [rbp+250h+var_2A0], rdx
0x1400770a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400770a9  lea     rax, WPP_GLOBAL_Control
0x1400770b0  cmp     rcx, rax
0x1400770b3  jz      short loc_1400770D5
0x1400770b5  test    byte ptr [rcx+1Ch], 1
0x1400770b9  jz      short loc_1400770D5
0x1400770bb  cmp     byte ptr [rcx+19h], 4
0x1400770bf  jb      short loc_1400770D5
0x1400770c1  mov     rcx, [rcx+10h]
0x1400770c5  lea     edx, [r14+23h]
0x1400770c9  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x1400770d0  call    WPP_SF_
0x1400770d5  mov     rcx, rbx; this
0x1400770d8  mov     [rbp+250h+var_2C0], r14
0x1400770dc  mov     [rbp+250h+var_2C4], 1
0x1400770e3  mov     [rbp+250h+pv], r14
0x1400770e7  mov     [rbp+250h+var_2B8], r14d
0x1400770eb  call    ?GetCatalog@CBlbAsync@@QEAAPEAUIBLBCatalogSystem@@XZ; CBlbAsync::GetCatalog(void)
0x1400770f0  mov     [rbp+250h+var_290], rax
0x1400770f4  xor     eax, eax
0x1400770f6  mov     [rbp+250h+var_2D0], rax
0x1400770fa  mov     r13d, eax
0x1400770fd  mov     [rsp+350h+var_2DC], eax
0x140077101  mov     [rbp+250h+var_298], rax
0x140077105  mov     [rbp+250h+var_2C8], eax
0x140077108  test    rsi, rsi
0x14007710b  jnz     short loc_140077127
0x14007710d  lea     r8, aPpvolumemap; "ppVolumeMap"
0x140077114  mov     edx, 3D9h; unsigned int
0x140077119  lea     rcx, aBaseStorBlbEng_41; "base\\stor\\blb\\engine\\service\\syste"...
0x140077120  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140077125  xor     eax, eax
0x140077127  test    rdi, rdi
0x14007712a  jnz     short loc_140077146
0x14007712c  lea     r8, aPpwszvolumesin; "ppwszVolumesInBackup"
0x140077133  mov     edx, 3DAh; unsigned int
0x140077138  lea     rcx, aBaseStorBlbEng_41; "base\\stor\\blb\\engine\\service\\syste"...
0x14007713f  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140077144  xor     eax, eax
0x140077146  mov     [r15], eax
0x140077149  mov     [rsi], rax
0x14007714c  mov     [rdi], rax
0x14007714f  mov     rdx, [rbx+238h]
0x140077156  cmp     [rdx+40h], eax
0x140077159  jbe     loc_140077218
0x14007715f  mov     r8, cs:WPP_GLOBAL_Control
0x140077166  mov     edi, r14d
0x140077169  mov     rdx, [rdx+48h]
0x14007716d  mov     eax, edi
0x14007716f  imul    rcx, rax, 78h ; 'x'
0x140077173  add     rdx, rcx; struct _GUID *
0x140077176  test    byte ptr [rdx+10h], 20h
0x14007717a  jz      short loc_1400771F8
0x14007717c  cmp     [rdx+29h], r14b
0x140077180  jnz     short loc_1400771F5
0x140077182  cmp     dword ptr [rbx+1D4h], 4
0x140077189  jz      short loc_1400771F5
0x14007718b  lea     rax, WPP_GLOBAL_Control
0x140077192  cmp     r8, rax
0x140077195  jz      short loc_1400771D8
0x140077197  test    byte ptr [r8+1Ch], 1
0x14007719c  jz      short loc_1400771D8
0x14007719e  cmp     byte ptr [r8+19h], 4
0x1400771a3  jb      short loc_1400771D8
0x1400771a5  lea     rcx, [rbp+250h+bstrString]; this
0x1400771a9  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x1400771ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400771b5  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x1400771bc  or      r12d, 1
0x1400771c0  mov     edx, 24h ; '$'
0x1400771c5  mov     r9, [rax]
0x1400771c8  mov     rcx, [rcx+10h]
0x1400771cc  call    WPP_SF_S
0x1400771d1  mov     r8, cs:WPP_GLOBAL_Control
0x1400771d8  test    r12b, 1
0x1400771dc  jz      short loc_1400771F8
0x1400771de  mov     rcx, [rbp+250h+bstrString]; bstrString
0x1400771e2  and     r12d, 0FFFFFFFEh
0x1400771e6  call    cs:__imp_SysFreeString
0x1400771ec  mov     r8, cs:WPP_GLOBAL_Control
0x1400771f3  jmp     short loc_1400771F8
0x1400771f5  inc     r13d
0x1400771f8  mov     rdx, [rbx+238h]
0x1400771ff  inc     edi
0x140077201  cmp     edi, [rdx+40h]
0x140077204  jb      loc_140077169
0x14007720a  mov     r14, [rbp+250h+var_2D0]
0x14007720e  mov     [rsp+350h+var_2DC], r13d
0x140077213  test    r13d, r13d
0x140077216  jnz     short loc_140077230
0x140077218  lea     r8, aCvolumemap0; "cVolumeMap > 0"
0x14007721f  mov     edx, 3F6h; unsigned int
0x140077224  lea     rcx, aBaseStorBlbEng_41; "base\\stor\\blb\\engine\\service\\syste"...
0x14007722b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140077230  mov     [rbx+174h], r13d
0x140077237  mov     rcx, cs:WPP_GLOBAL_Control
0x14007723e  lea     rax, WPP_GLOBAL_Control
0x140077245  cmp     rcx, rax
0x140077248  jz      short loc_14007726E
0x14007724a  test    byte ptr [rcx+1Ch], 1
0x14007724e  jz      short loc_14007726E
0x140077250  cmp     byte ptr [rcx+19h], 4
0x140077254  jb      short loc_14007726E
0x140077256  mov     rcx, [rcx+10h]
0x14007725a  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x140077261  mov     edx, 25h ; '%'
0x140077266  mov     r9d, r13d
0x140077269  call    WPP_SF_d
0x14007726e  mov     r15d, r13d
0x140077271  lea     rdi, [r15+r15*2]
0x140077275  shl     rdi, 3
0x140077279  mov     rcx, rdi; cb
0x14007727c  call    cs:__imp_CoTaskMemAlloc
0x140077282  mov     rsi, rax
0x140077285  xor     eax, eax
0x140077287  test    rsi, rsi
0x14007728a  jnz     short loc_14007729D
0x14007728c  mov     r15d, eax
0x14007728f  mov     edi, 8007000Eh
0x140077294  mov     [rsp+350h+var_2E0], edi
0x140077298  jmp     loc_1400775F6
0x14007729d  mov     r8, rdi; Size
0x1400772a0  xor     edx, edx; Val
0x1400772a2  mov     rcx, rsi; void *
0x1400772a5  call    memset_0
0x1400772aa  lea     rdi, ds:0[r15*8]
0x1400772b2  mov     rcx, rdi; cb
0x1400772b5  call    cs:__imp_CoTaskMemAlloc
0x1400772bb  mov     r15, rax
0x1400772be  test    rax, rax
0x1400772c1  jz      short loc_14007728F
0x1400772c3  mov     r8, rdi; Size
0x1400772c6  xor     edx, edx; Val
0x1400772c8  mov     rcx, rax; void *
0x1400772cb  call    memset_0
0x1400772d0  mov     rcx, [rbp+250h+var_2A0]
0x1400772d4  lea     r8, [rbp+250h+var_298]
0x1400772d8  lea     rdx, [rbp+250h+var_2C8]
0x1400772dc  mov     rax, [rcx]
0x1400772df  mov     rax, [rax+40h]
0x1400772e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400772e8  xor     r8d, r8d
0x1400772eb  mov     [rsp+350h+var_2E0], eax
0x1400772ef  mov     edi, eax
0x1400772f1  test    eax, eax
0x1400772f3  js      loc_1400775F6
0x1400772f9  mov     eax, r8d
0x1400772fc  mov     ecx, r8d
0x1400772ff  mov     [rsp+350h+var_2D8], eax
0x140077303  mov     rdx, [rbx+238h]
0x14007730a  mov     dword ptr [rbp+250h+bstrString], ecx
0x14007730d  cmp     ecx, [rdx+40h]
0x140077310  jnb     loc_1400777F6
0x140077316  mov     eax, ecx
0x140077318  imul    r13, rax, 78h ; 'x'
0x14007731c  add     r13, [rdx+48h]
0x140077320  test    byte ptr [r13+10h], 20h
0x140077325  jz      loc_140077566
0x14007732b  test    byte ptr [r13+10h], 1
0x140077330  jnz     loc_140077566
0x140077336  cmp     [r13+29h], r8b
0x14007733a  jnz     short loc_140077349
0x14007733c  cmp     dword ptr [rbx+1D4h], 4
0x140077343  jnz     loc_140077566
0x140077349  mov     rcx, [rbp+250h+pv]; pv
0x14007734d  call    cs:__imp_CoTaskMemFree
0x140077353  mov     edx, [r13+10h]; unsigned int
0x140077357  lea     r8, [rbp+250h+pv]; unsigned __int16 **
0x14007735b  xor     r9d, r9d; unsigned __int8
0x14007735e  mov     [rbp+250h+pv], 0
0x140077366  mov     rcx, r13; struct _GUID *
0x140077369  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x14007736e  xor     edx, edx
0x140077370  mov     [rsp+350h+var_2E0], eax
0x140077374  mov     edi, eax
0x140077376  test    eax, eax
0x140077378  js      loc_1400775F1
0x14007737e  cmp     [rbp+250h+var_2C0], rdx
0x140077382  jz      short loc_140077393
0x140077384  lea     rdx, [rbp+250h+var_2C4]; unsigned int *
0x140077388  lea     rcx, [rbp+250h+var_2C0]; struct _BLB_VOLUME_INFO **
0x14007738c  call    ?FreeVolumes@@YAXAEAPEAU_BLB_VOLUME_INFO@@AEAK@Z; FreeVolumes(_BLB_VOLUME_INFO * &,ulong &)
0x140077391  xor     edx, edx; struct _BLBCAT_BACKUP_SET_INFO *
0x140077393  cmp     dword ptr [rbx+1D4h], 4
0x14007739a  mov     [rbp+250h+var_2C0], rdx
0x14007739e  mov     [rbp+250h+var_2C4], 1
0x1400773a5  jz      short loc_1400773E9
0x1400773a7  mov     rcx, [rbp+250h+var_298]
0x1400773ab  lea     rax, [rbp+250h+var_2C0]
0x1400773af  cmp     [rbx+1C8h], edx
0x1400773b5  mov     r9d, edx
0x1400773b8  mov     [rsp+350h+var_320], rax; struct _BLB_VOLUME_INFO **
0x1400773bd  mov     r8, r13; struct _BLBCAT_VOLUME_INFO *
0x1400773c0  mov     eax, [rbp+250h+var_2C8]
0x1400773c3  setz    r9b; int
0x1400773c7  mov     [rsp+350h+var_328], eax; unsigned int
0x1400773cb  mov     [rsp+350h+var_330], rcx; struct _BLB_VOLUME_INFO *
0x1400773d0  mov     rcx, [rbp+250h+var_2A0]; struct CBlbEngine *
0x1400773d4  call    ?BlbFindLocalVolumeMatch@@YAJPEAVCBlbEngine@@AEAU_BLBCAT_BACKUP_SET_INFO@@PEAU_BLBCAT_VOLUME_INFO@@HPEAU_BLB_VOLUME_INFO@@KPEAPEAU4@@Z; BlbFindLocalVolumeMatch(CBlbEngine *,_BLBCAT_BACKUP_SET_INFO &,_BLBCAT_VOLUME_INFO *,int,_BLB_VOLUME_INFO *,ulong,_BLB_VOLUME_INFO * *)
0x1400773d9  xor     edx, edx
0x1400773db  mov     [rsp+350h+var_2E0], eax
0x1400773df  mov     edi, eax
0x1400773e1  test    eax, eax
0x1400773e3  js      loc_1400775F1
0x1400773e9  lea     rcx, [rbx+10h]; this
0x1400773ed  mov     [rbp+250h+var_250], dx
0x1400773f1  call    ?GetImpersonationToken@CBlbImpersonationHelper@@QEAAPEAXXZ; CBlbImpersonationHelper::GetImpersonationToken(void)
0x1400773f6  mov     r11, [rbp+250h+var_2A0]
0x1400773fa  lea     r8, [rbp+250h+var_270]
0x1400773fe  movups  xmm0, xmmword ptr [r13+0]
0x140077403  mov     [rsp+350h+var_2F8], edx
0x140077407  xor     r9d, r9d
0x14007740a  movups  xmm1, xmmword ptr [rbx+100h]
0x140077411  mov     rcx, [r11]
0x140077414  movdqu  [rbp+250h+var_270], xmm0
0x140077419  movdqu  [rbp+250h+var_260], xmm1
0x14007741e  mov     r10, [rcx+158h]
0x140077425  lea     rcx, [rbp+250h+var_250]
0x140077429  mov     [rsp+350h+var_300], rcx
0x14007742e  lea     rcx, [rbp+250h+var_2B8]
0x140077432  mov     [rsp+350h+var_308], rcx
0x140077437  mov     rcx, [rbp+250h+var_290]
0x14007743b  mov     [rsp+350h+var_310], rcx
0x140077440  mov     rcx, [rbx+1A8h]
0x140077447  mov     [rsp+350h+var_318], 104h
0x14007744f  mov     [rsp+350h+var_320], rax
0x140077454  mov     rax, r10
0x140077457  mov     qword ptr [rsp+350h+var_328], rdx
0x14007745c  lea     rdx, [rbp+250h+var_260]
0x140077460  mov     [rsp+350h+var_330], rcx
0x140077465  mov     rcx, r11
0x140077468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007746d  mov     [rsp+350h+var_2E0], eax
0x140077471  mov     edi, eax
0x140077473  test    eax, eax
0x140077475  js      loc_140077574
0x14007747b  mov     rcx, [r13+18h]; unsigned __int16 *
0x14007747f  test    rcx, rcx
0x140077482  jz      short loc_140077492
0x140077484  xor     r8d, r8d; unsigned __int64
0x140077487  lea     rdx, [rbp+250h+var_2D0]; unsigned __int16 **
0x14007748b  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140077490  jmp     short loc_1400774A5
0x140077492  mov     edx, [r13+10h]; unsigned int
0x140077496  lea     r8, [rbp+250h+var_2D0]; unsigned __int16 **
0x14007749a  xor     r9d, r9d; unsigned __int8
0x14007749d  mov     rcx, r13; struct _GUID *
0x1400774a0  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x1400774a5  mov     r14, [rbp+250h+var_2D0]
0x1400774a9  mov     edi, eax
0x1400774ab  mov     [rsp+350h+var_2E0], eax
0x1400774af  test    eax, eax
0x1400774b1  js      loc_1400775F1
0x1400774b7  mov     eax, [rsp+350h+var_2D8]
0x1400774bb  mov     rcx, r14; unsigned __int16 *
0x1400774be  lea     rax, [rax+rax*2]
0x1400774c2  lea     r13, [rsi+rax*8]
0x1400774c6  mov     rdx, r13; unsigned __int16 **
0x1400774c9  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x1400774ce  mov     [rsp+350h+var_2E0], eax
0x1400774d2  mov     edi, eax
0x1400774d4  test    eax, eax
0x1400774d6  js      loc_1400775F1
0x1400774dc  cmp     dword ptr [rbx+1D4h], 4
0x1400774e3  lea     rdx, [r13+8]; unsigned __int16 **
0x1400774e7  jz      short loc_140077500
0x1400774e9  mov     rax, [rbp+250h+var_2C0]
0x1400774ed  mov     r8, rdx; unsigned __int16 **
0x1400774f0  xor     r9d, r9d; unsigned __int8
0x1400774f3  mov     rcx, rax; struct _GUID *
0x1400774f6  mov     edx, [rax+58h]; unsigned int
0x1400774f9  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x1400774fe  jmp     short loc_14007750C
0x140077500  mov     rcx, [rbx+1C0h]; unsigned __int16 *
0x140077507  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14007750c  mov     [rsp+350h+var_2E0], eax
  ... truncated ...
```
