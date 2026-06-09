# CBlbApplicationBackupAsync::PerformVHDPruningForComponents(ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,_BLBCAT_BACKUP_SET_INFO *,ushort *,ulong,CBlbVolumeBackupContext *)

- ea: `0x1400115f0`
- end: `0x140011d9c`
- name: `?PerformVHDPruningForComponents@CBlbApplicationBackupAsync@@AEAAJAEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@0PEAU_BLBCAT_BACKUP_SET_INFO@@PEAGKPEAVCBlbVolumeBackupContext@@@Z`
- size: `1964`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, int, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002e92c`

## callees

- `0x140006a64`
- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000c574`
- `0x14000d5b8`
- `0x14000f8f4`
- `0x1400115f0`
- `0x140012e74`
- `0x140014200`
- `0x140014260`
- `0x1400869f0`
- `0x140086b88`
- `0x140088d0c`
- `0x14008e8e8`
- `0x1400f597c`
- `0x1400f7914`
- `0x1400ff774`
- `0x140108698`
- `0x1401087ac`
- `0x140109db8`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140011768`
- `ole32!CoTaskMemFree` at `0x14001183c`
- `ole32!CoTaskMemFree` at `0x140011a76`
- `ole32!CoTaskMemFree` at `0x140011a83`
- `ole32!CoTaskMemFree` at `0x140011be7`
- `ole32!CoTaskMemFree` at `0x140011c78`
- `ole32!CoTaskMemFree` at `0x140011c85`
- `ole32!CoTaskMemFree` at `0x140011768`
- `ole32!CoTaskMemFree` at `0x14001183c`
- `ole32!CoTaskMemFree` at `0x140011a76`
- `ole32!CoTaskMemFree` at `0x140011a83`
- `ole32!CoTaskMemFree` at `0x140011be7`
- `ole32!CoTaskMemFree` at `0x140011c78`
- `ole32!CoTaskMemFree` at `0x140011c85`

## string_xrefs

- `0x140011671`: `base\stor\blb\engine\service\appbackup.cpp`
- `0x140011c06`: `base\stor\blb\engine\service\appbackup.cpp`
- `0x140011c63`: `base\stor\blb\engine\service\appbackup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CBlbApplicationBackupAsync::PerformVHDPruningForComponents(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _BLBCAT_BACKUP_SET_INFO *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        __int64 a7)
{
  int VhdPath; // ebx
  WCHAR *v10; // r15
  char v11; // r14
  unsigned __int16 *v12; // rsi
  __int64 v13; // rdi
  __int64 i; // rax
  unsigned int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r14
  __int64 v20; // rcx
  PVOID v21; // rcx
  __int64 v22; // rcx
  CBlbPruningContext *v23; // r14
  struct _FILETIME v24; // r8
  int v25; // eax
  void *v26; // rcx
  int v27; // eax
  void *v28; // rcx
  char v30; // [rsp+30h] [rbp-D0h]
  int v31; // [rsp+34h] [rbp-CCh]
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  PCWSTR v33; // [rsp+40h] [rbp-C0h] BYREF
  void *v34[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v35; // [rsp+60h] [rbp-A0h]
  CBlbPruningContext *v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h]
  void *v38[3]; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+90h] [rbp-70h]
  __int64 v40[3]; // [rsp+98h] [rbp-68h] BYREF
  int v41; // [rsp+B0h] [rbp-50h]
  __int64 v42[3]; // [rsp+B8h] [rbp-48h] BYREF
  int v43; // [rsp+D0h] [rbp-30h]
  void *v44[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v45; // [rsp+F0h] [rbp-10h]
  struct _BLBCAT_BACKUP_SET_INFO *v46; // [rsp+F8h] [rbp-8h]
  struct _GUID Buf1; // [rsp+100h] [rbp+0h] BYREF
  void *v48[3]; // [rsp+110h] [rbp+10h] BYREF
  int v49; // [rsp+128h] [rbp+28h]
  void *v50[3]; // [rsp+130h] [rbp+30h] BYREF
  int v51; // [rsp+148h] [rbp+48h]
  void *v52[3]; // [rsp+150h] [rbp+50h] BYREF
  int v53; // [rsp+168h] [rbp+68h]

  v46 = a4;
  v37 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
  }
  if ( !a4 )
    BlbAssert("base\\stor\\blb\\engine\\service\\appbackup.cpp", 0xDACu, "pBsiCat");
  VhdPath = 0;
  v10 = 0;
  v33 = 0;
  v11 = 0;
  v30 = 0;
  v36 = 0;
  memset(v44, 0, sizeof(v44));
  v45 = 0;
  memset(v52, 0, sizeof(v52));
  v53 = 0;
  memset(v50, 0, sizeof(v50));
  v51 = 0;
  memset(v48, 0, sizeof(v48));
  v49 = 0;
  v12 = 0;
  pv = 0;
  memset(v38, 0, sizeof(v38));
  v39 = 0;
  memset(v42, 0, sizeof(v42));
  v43 = 0;
  memset(v40, 0, sizeof(v40));
  v41 = 0;
  v13 = 0;
  for ( i = 0; ; i = (unsigned int)(v31 + 1) )
  {
    v31 = i;
    if ( (unsigned int)i >= *(_DWORD *)(a1 + 220) )
      goto LABEL_70;
    memset(v34, 0, sizeof(v34));
    v35 = 0;
    v13 = *(_QWORD *)(a1 + 224) + 96 * i;
    if ( !*(_QWORD *)(v13 + 72) || !*(_QWORD *)(v13 + 88) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          133,
          WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids,
          *(_QWORD *)(v13 + 16));
      }
      goto LABEL_53;
    }
    if ( v10 )
    {
      CoTaskMemFree(v10);
      v33 = 0;
    }
    Buf1 = *(struct _GUID *)v13;
    VhdPath = BlbGetVhdPath(&Buf1, *(_DWORD *)(v13 + 40), a5, (unsigned __int16 **)&v33);
    if ( VhdPath < 0 )
      break;
    v10 = (WCHAR *)v33;
    if ( FileExists((unsigned __int16 *)v33) && (*(_BYTE *)(v13 + 40) & 8) == 0 )
    {
      v15 = 0;
      if ( !a6 )
        goto LABEL_23;
      while ( 1 )
      {
        v16 = 368LL * v15;
        v17 = *(_QWORD *)v13 - *(_QWORD *)(v16 + a7 + 68);
        if ( *(_QWORD *)v13 == *(_QWORD *)(v16 + a7 + 68) )
          v17 = *(_QWORD *)(v13 + 8) - *(_QWORD *)(v16 + a7 + 76);
        if ( !v17 )
          break;
        if ( ++v15 >= a6 )
          goto LABEL_23;
      }
      if ( !*(_QWORD *)(368LL * v15 + a7 + 224) )
      {
LABEL_23:
        VhdPath = CBlbVhdHelper::DeleteShadowsOnVhd(
                    v10,
                    (struct CBlbImpersonationHelper *)(*(_QWORD *)(a1 + 240) + 40LL));
        if ( VhdPath < 0 )
          goto LABEL_61;
        VhdPath = CBlbVhdHelper::MountVHD(
                    (struct CBlbImpersonationHelper *)(*(_QWORD *)(a1 + 240) + 40LL),
                    v10,
                    (unsigned __int16 **)&pv);
        if ( VhdPath < 0 )
        {
          ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v34);
          v12 = (unsigned __int16 *)pv;
          goto LABEL_70;
        }
        v12 = (unsigned __int16 *)pv;
        VhdPath = BlbutilSlashTerminatePath((unsigned __int16 *)pv, (LPVOID *)(v13 + 80));
        if ( VhdPath < 0 )
          goto LABEL_61;
        if ( v11 )
        {
          v19 = v37;
        }
        else
        {
          LOBYTE(v18) = 1;
          VhdPath = CBlbBackupItemsHelper::ConvertFileSpecs(a1 + 368, v18, v44);
          if ( VhdPath < 0 )
            goto LABEL_61;
          ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(v50, a1 + 400);
          ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(v50, v44);
          v19 = v37;
          ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(v48, v37);
          ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(v48, v44);
          v30 = 1;
        }
        ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(v38, 0);
        ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(v42, 0);
        ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(v40, 0);
        if ( (*(_BYTE *)(v13 + 40) & 0x40) != 0 || (*(_BYTE *)(v13 + 40) & 0x20) != 0 || (*(_BYTE *)(v13 + 40) & 8) != 0 )
        {
          VhdPath = CBlbApplicationBackupAsync::GetSpecsForVolume(v20, *(_QWORD *)(v13 + 16), v50, v38);
          if ( VhdPath < 0 )
            goto LABEL_61;
        }
        else
        {
          ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(v38, v34);
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
          }
        }
        VhdPath = CBlbApplicationBackupAsync::GetSpecsForVolume(v21, *(_QWORD *)(v13 + 16), v19, v42);
        if ( VhdPath < 0 )
          goto LABEL_61;
        VhdPath = CBlbApplicationBackupAsync::GetSpecsForVolume(v22, *(_QWORD *)(v13 + 16), v48, v40);
        if ( VhdPath < 0 )
          goto LABEL_61;
        VhdPath = ATL::CComObject<CBlbPruningContext>::CreateInstance(&v36);
        if ( VhdPath < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
          }
          goto LABEL_61;
        }
        v23 = v36;
        (*(void (__fastcall **)(CBlbPruningContext *))(*(_QWORD *)v36 + 8LL))(v36);
        VhdPath = CBlbPruningContext::Initialize(v23, *(struct CBlbBackupAsync **)(a1 + 240), v24, v46);
        if ( VhdPath < 0 )
          goto LABEL_61;
        Buf1 = *(struct _GUID *)v13;
        VhdPath = CBlbPruningContext::PerformPruning(v23, (__int64)v42, (__int64)v40);
        if ( VhdPath < 0 )
          goto LABEL_61;
        (*(void (__fastcall **)(CBlbPruningContext *))(*(_QWORD *)v23 + 16LL))(v23);
        v36 = 0;
        if ( v12 )
        {
          v25 = CBlbVhdHelper::Dismount(v12);
          VhdPath = v25;
          if ( v25 < 0 )
          {
            if ( *(int *)(a1 + 292) >= 0 )
              (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 64LL))(
                a1,
                2155348300LL,
                (unsigned int)v25);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                136,
                (unsigned int)WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids,
                (_DWORD)v12,
                VhdPath);
            }
LABEL_61:
            ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v34);
            goto LABEL_70;
          }
          v26 = *(void **)(v13 + 80);
          if ( v26 )
          {
            CoTaskMemFree(v26);
            *(_QWORD *)(v13 + 80) = 0;
          }
          CoTaskMemFree(v12);
          v12 = 0;
          pv = 0;
        }
        v11 = v30;
      }
    }
LABEL_53:
    ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v34);
  }
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v34);
  v10 = (WCHAR *)v33;
LABEL_70:
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v12 )
  {
    if ( VhdPath >= 0 )
      BlbAssert("base\\stor\\blb\\engine\\service\\appbackup.cpp", 0xE85u, "FAILED(hr)");
    v27 = CBlbVhdHelper::Dismount(v12);
    if ( v27 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        (unsigned int)WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids,
        (_DWORD)v12,
        v27);
    }
    if ( !v13 )
      BlbAssert("base\\stor\\blb\\engine\\service\\appbackup.cpp", 0xE8Fu, "pVolCtxt");
    v28 = *(void **)(v13 + 80);
    if ( v28 )
    {
      CoTaskMemFree(v28);
      *(_QWORD *)(v13 + 80) = 0;
    }
    CoTaskMemFree(v12);
  }
  if ( VhdPath < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
    }
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, 2155348301LL, (unsigned int)VhdPath);
  }
  BlbFreeFileSpecArr(v44);
  ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(v38, 0);
  ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(v42, 0);
  ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(v40, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
  }
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>((void **)v40);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>((void **)v42);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v38);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v48);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v50);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v52);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v44);
  return (unsigned int)VhdPath;
}

```

## disassembly

```asm
0x1400115f0  push    rbp
0x1400115f2  push    rbx
0x1400115f3  push    rsi
0x1400115f4  push    rdi
0x1400115f5  push    r12
0x1400115f7  push    r13
0x1400115f9  push    r14
0x1400115fb  push    r15
0x1400115fd  lea     rbp, [rsp-88h]
0x140011605  sub     rsp, 188h
0x14001160c  mov     rax, cs:__security_cookie
0x140011613  xor     rax, rsp
0x140011616  mov     [rbp+0C0h+var_50], rax
0x14001161a  mov     rbx, r9
0x14001161d  mov     [rbp+0C0h+var_C8], rbx
0x140011621  mov     [rsp+1C0h+var_150], rdx
0x140011626  mov     r12, rcx
0x140011629  lea     rax, WPP_GLOBAL_Control
0x140011630  mov     rcx, cs:WPP_GLOBAL_Control
0x140011637  cmp     rcx, rax
0x14001163a  jz      short loc_14001165D
0x14001163c  test    byte ptr [rcx+1Ch], 1
0x140011640  jz      short loc_14001165D
0x140011642  cmp     byte ptr [rcx+19h], 4
0x140011646  jb      short loc_14001165D
0x140011648  mov     edx, 84h
0x14001164d  lea     r8, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids
0x140011654  mov     rcx, [rcx+10h]
0x140011658  call    WPP_SF_
0x14001165d  xor     r13d, r13d
0x140011660  test    rbx, rbx
0x140011663  jnz     short loc_14001167D
0x140011665  lea     r8, aPbsicat_0; "pBsiCat"
0x14001166c  mov     edx, 0DACh; unsigned int
0x140011671  lea     rcx, aBaseStorBlbEng_47; "base\\stor\\blb\\engine\\service\\appba"...
0x140011678  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14001167d  mov     ebx, r13d
0x140011680  mov     r15, r13
0x140011683  mov     [rsp+1C0h+var_180], r13
0x140011688  mov     r14b, r13b
0x14001168b  mov     [rsp+1C0h+var_190], r13b
0x140011690  mov     [rsp+1C0h+var_158], r13
0x140011695  mov     [rbp+0C0h+var_E8], r13
0x140011699  mov     [rbp+0C0h+var_E0], r13
0x14001169d  mov     [rbp+0C0h+var_D8], r13
0x1400116a1  mov     [rbp+0C0h+var_D0], r13d
0x1400116a5  mov     [rbp+0C0h+var_70], r13
0x1400116a9  mov     [rbp+0C0h+var_68], r13
0x1400116ad  mov     [rbp+0C0h+var_60], r13
0x1400116b1  mov     [rbp+0C0h+var_58], r13d
0x1400116b5  mov     [rbp+0C0h+var_90], r13
0x1400116b9  mov     [rbp+0C0h+var_88], r13
0x1400116bd  mov     [rbp+0C0h+var_80], r13
0x1400116c1  mov     [rbp+0C0h+var_78], r13d
0x1400116c5  mov     [rbp+0C0h+var_B0], r13
0x1400116c9  mov     [rbp+0C0h+var_A8], r13
0x1400116cd  mov     [rbp+0C0h+var_A0], r13
0x1400116d1  mov     [rbp+0C0h+var_98], r13d
0x1400116d5  mov     rsi, r13
0x1400116d8  mov     [rsp+1C0h+pv], r13
0x1400116dd  mov     [rsp+1C0h+var_148], r13
0x1400116e2  mov     [rbp+0C0h+var_140], r13
0x1400116e6  mov     [rbp+0C0h+var_138], r13
0x1400116ea  mov     [rbp+0C0h+var_130], r13d
0x1400116ee  mov     [rbp+0C0h+var_108], r13
0x1400116f2  mov     [rbp+0C0h+var_100], r13
0x1400116f6  mov     [rbp+0C0h+var_F8], r13
0x1400116fa  mov     [rbp+0C0h+var_F0], r13d
0x1400116fe  mov     [rbp+0C0h+var_128], r13
0x140011702  mov     [rbp+0C0h+var_120], r13
0x140011706  mov     [rbp+0C0h+var_118], r13
0x14001170a  mov     [rbp+0C0h+var_110], r13d
0x14001170e  mov     rdi, r13
0x140011711  mov     eax, r13d
0x140011714  mov     [rsp+1C0h+var_18C], eax
0x140011718  cmp     eax, [r12+0DCh]
0x140011720  jnb     loc_140011BD8
0x140011726  mov     [rsp+1C0h+var_178], r13
0x14001172b  mov     [rsp+1C0h+var_170], r13
0x140011730  mov     [rsp+1C0h+var_168], r13
0x140011735  mov     [rsp+1C0h+var_160], r13d
0x14001173a  lea     rdi, [rax+rax*2]
0x14001173e  shl     rdi, 5
0x140011742  add     rdi, [r12+0E0h]
0x14001174a  cmp     qword ptr [rdi+48h], 0
0x14001174f  jz      loc_140011A98
0x140011755  cmp     qword ptr [rdi+58h], 0
0x14001175a  jz      loc_140011A98
0x140011760  test    r15, r15
0x140011763  jz      short loc_140011777
0x140011765  mov     rcx, r15; pv
0x140011768  call    cs:__imp_CoTaskMemFree
0x14001176e  mov     [rsp+1C0h+var_180], 0
0x140011777  movups  xmm0, xmmword ptr [rdi]
0x14001177a  movdqu  xmmword ptr [rbp+0C0h+Buf1.Data1], xmm0
0x14001177f  lea     r9, [rsp+1C0h+var_180]; unsigned __int16 **
0x140011784  mov     r8, [rbp+0C0h+arg_20]; unsigned __int16 *
0x14001178b  mov     edx, [rdi+28h]; unsigned int
0x14001178e  lea     rcx, [rbp+0C0h+Buf1]; Buf1
0x140011792  call    ?BlbGetVhdPath@@YAJU_GUID@@KPEAGPEAPEAG@Z; BlbGetVhdPath(_GUID,ulong,ushort *,ushort * *)
0x140011797  mov     ebx, eax
0x140011799  test    eax, eax
0x14001179b  js      loc_140011BC6
0x1400117a1  mov     r15, [rsp+1C0h+var_180]
0x1400117a6  mov     rcx, r15; unsigned __int16 *
0x1400117a9  call    ?FileExists@@YA_NPEAG@Z; FileExists(ushort *)
0x1400117ae  test    al, al
0x1400117b0  jz      loc_140011AD1
0x1400117b6  test    byte ptr [rdi+28h], 8
0x1400117ba  jnz     loc_140011AD1
0x1400117c0  xor     ecx, ecx
0x1400117c2  cmp     [rbp+0C0h+arg_28], ecx
0x1400117c8  jbe     short loc_140011816
0x1400117ca  mov     r9, [rbp+0C0h+arg_30]
0x1400117d1  mov     eax, ecx
0x1400117d3  imul    rdx, rax, 170h
0x1400117da  mov     rax, [rdi]
0x1400117dd  sub     rax, [rdx+r9+44h]
0x1400117e2  jnz     short loc_1400117ED
0x1400117e4  mov     rax, [rdi+8]
0x1400117e8  sub     rax, [rdx+r9+4Ch]
0x1400117ed  test    rax, rax
0x1400117f0  jz      short loc_1400117FE
0x1400117f2  inc     ecx
0x1400117f4  cmp     ecx, [rbp+0C0h+arg_28]
0x1400117fa  jb      short loc_1400117D1
0x1400117fc  jmp     short loc_140011816
0x1400117fe  mov     eax, ecx
0x140011800  imul    rcx, rax, 170h
0x140011807  cmp     qword ptr [rcx+r9+0E0h], 0
0x140011810  jnz     loc_140011AD1
0x140011816  mov     rdx, [r12+0F0h]
0x14001181e  add     rdx, 28h ; '('; this
0x140011822  mov     rcx, r15; PCWSTR
0x140011825  call    ?DeleteShadowsOnVhd@CBlbVhdHelper@@SAJPEBGPEAVCBlbImpersonationHelper@@@Z; CBlbVhdHelper::DeleteShadowsOnVhd(ushort const *,CBlbImpersonationHelper *)
0x14001182a  mov     ebx, eax
0x14001182c  test    eax, eax
0x14001182e  js      loc_140011AE9
0x140011834  test    rsi, rsi
0x140011837  jz      short loc_14001184B
0x140011839  mov     rcx, rsi; pv
0x14001183c  call    cs:__imp_CoTaskMemFree
0x140011842  mov     [rsp+1C0h+pv], 0
0x14001184b  mov     rcx, [r12+0F0h]
0x140011853  add     rcx, 28h ; '('; this
0x140011857  lea     r8, [rsp+1C0h+pv]; unsigned __int16 **
0x14001185c  mov     rdx, r15; PCWSTR
0x14001185f  call    ?MountVHD@CBlbVhdHelper@@SAJPEAVCBlbImpersonationHelper@@PEBGPEAPEAG@Z; CBlbVhdHelper::MountVHD(CBlbImpersonationHelper *,ushort const *,ushort * *)
0x140011864  mov     ebx, eax
0x140011866  test    eax, eax
0x140011868  js      loc_140011BB5
0x14001186e  lea     rdx, [rdi+50h]; unsigned __int16 **
0x140011872  mov     rsi, [rsp+1C0h+pv]
0x140011877  mov     rcx, rsi; unsigned __int16 *
0x14001187a  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14001187f  mov     ebx, eax
0x140011881  test    eax, eax
0x140011883  js      loc_140011AE9
0x140011889  test    r14b, r14b
0x14001188c  jnz     short loc_1400118EE
0x14001188e  lea     rcx, [r12+170h]
0x140011896  lea     r8, [rbp+0C0h+var_E8]
0x14001189a  mov     dl, 1
0x14001189c  call    ?ConvertFileSpecs@CBlbBackupItemsHelper@@SAJAEAV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@EAEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@3@@Z; CBlbBackupItemsHelper::ConvertFileSpecs(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> &,uchar,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &)
0x1400118a1  mov     ebx, eax
0x1400118a3  test    eax, eax
0x1400118a5  js      loc_140011AE9
0x1400118ab  lea     rdx, [r12+190h]
0x1400118b3  lea     rcx, [rbp+0C0h+var_90]
0x1400118b7  call    ?Append@?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@QEAA_KAEBV12@@Z; ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> const &)
0x1400118bc  lea     rdx, [rbp+0C0h+var_E8]
0x1400118c0  lea     rcx, [rbp+0C0h+var_90]
0x1400118c4  call    ?Append@?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@QEAA_KAEBV12@@Z; ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> const &)
0x1400118c9  mov     r14, [rsp+1C0h+var_150]
0x1400118ce  mov     rdx, r14
0x1400118d1  lea     rcx, [rbp+0C0h+var_B0]
0x1400118d5  call    ?Append@?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@QEAA_KAEBV12@@Z; ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> const &)
0x1400118da  lea     rdx, [rbp+0C0h+var_E8]
0x1400118de  lea     rcx, [rbp+0C0h+var_B0]
0x1400118e2  call    ?Append@?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@QEAA_KAEBV12@@Z; ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> const &)
0x1400118e7  mov     [rsp+1C0h+var_190], 1
0x1400118ec  jmp     short loc_1400118F3
0x1400118ee  mov     r14, [rsp+1C0h+var_150]
0x1400118f3  xor     edx, edx
0x1400118f5  lea     rcx, [rsp+1C0h+var_148]
0x1400118fa  call    ?SetCount@?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(unsigned __int64,int)
0x1400118ff  nop
0x140011900  xor     edx, edx
0x140011902  lea     rcx, [rbp+0C0h+var_108]
0x140011906  call    ?SetCount@?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(unsigned __int64,int)
0x14001190b  nop
0x14001190c  xor     edx, edx
0x14001190e  lea     rcx, [rbp+0C0h+var_128]
0x140011912  call    ?SetCount@?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(unsigned __int64,int)
0x140011917  nop
0x140011918  test    byte ptr [rdi+28h], 40h
0x14001191c  jnz     short loc_14001196F
0x14001191e  test    byte ptr [rdi+28h], 20h
0x140011922  jnz     short loc_14001196F
0x140011924  test    byte ptr [rdi+28h], 8
0x140011928  jnz     short loc_14001196F
0x14001192a  lea     rdx, [rsp+1C0h+var_178]
0x14001192f  lea     rcx, [rsp+1C0h+var_148]
0x140011934  call    ?Append@?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@QEAA_KAEBV12@@Z; ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>>::Append(ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> const &)
0x140011939  mov     rcx, cs:WPP_GLOBAL_Control
0x140011940  lea     rax, WPP_GLOBAL_Control
0x140011947  cmp     rcx, rax
0x14001194a  jz      short loc_14001198B
0x14001194c  test    byte ptr [rcx+1Ch], 1
0x140011950  jz      short loc_14001198B
0x140011952  cmp     byte ptr [rcx+19h], 4
0x140011956  jb      short loc_14001198B
0x140011958  mov     edx, 86h
0x14001195d  lea     r8, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids
0x140011964  mov     rcx, [rcx+10h]
0x140011968  call    WPP_SF_
0x14001196d  jmp     short loc_14001198B
0x14001196f  lea     r9, [rsp+1C0h+var_148]
0x140011974  lea     r8, [rbp+0C0h+var_90]
0x140011978  mov     rdx, [rdi+10h]
0x14001197c  call    ?GetSpecsForVolume@CBlbApplicationBackupAsync@@AEAAJPEBGAEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@1@Z; CBlbApplicationBackupAsync::GetSpecsForVolume(ushort const *,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &)
0x140011981  mov     ebx, eax
0x140011983  test    eax, eax
0x140011985  js      loc_140011AE9
0x14001198b  lea     r9, [rbp+0C0h+var_108]
0x14001198f  mov     r8, r14
0x140011992  mov     rdx, [rdi+10h]
0x140011996  call    ?GetSpecsForVolume@CBlbApplicationBackupAsync@@AEAAJPEBGAEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@1@Z; CBlbApplicationBackupAsync::GetSpecsForVolume(ushort const *,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &)
0x14001199b  mov     ebx, eax
0x14001199d  test    eax, eax
0x14001199f  js      loc_140011AE9
0x1400119a5  lea     r9, [rbp+0C0h+var_128]
0x1400119a9  lea     r8, [rbp+0C0h+var_B0]
0x1400119ad  mov     rdx, [rdi+10h]
0x1400119b1  call    ?GetSpecsForVolume@CBlbApplicationBackupAsync@@AEAAJPEBGAEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@1@Z; CBlbApplicationBackupAsync::GetSpecsForVolume(ushort const *,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &)
0x1400119b6  mov     ebx, eax
0x1400119b8  test    eax, eax
0x1400119ba  js      loc_140011AE9
0x1400119c0  lea     rcx, [rsp+1C0h+var_158]
0x1400119c5  call    ?CreateInstance@?$CComObject@VCBlbPruningContext@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CBlbPruningContext>::CreateInstance(ATL::CComObject<CBlbPruningContext> * *)
0x1400119ca  mov     ebx, eax
0x1400119cc  test    eax, eax
0x1400119ce  js      loc_140011B6E
0x1400119d4  mov     r14, [rsp+1C0h+var_158]
0x1400119d9  mov     rax, [r14]
0x1400119dc  mov     rcx, r14
0x1400119df  mov     rax, [rax+8]
0x1400119e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400119e8  mov     r9, [rbp+0C0h+var_C8]; struct _BLBCAT_BACKUP_SET_INFO *
0x1400119ec  mov     rdx, [r12+0F0h]; struct CBlbBackupAsync *
0x1400119f4  mov     rcx, r14; this
0x1400119f7  call    ?Initialize@CBlbPruningContext@@QEAAJPEAVCBlbBackupAsync@@U_FILETIME@@PEAU_BLBCAT_BACKUP_SET_INFO@@@Z; CBlbPruningContext::Initialize(CBlbBackupAsync *,_FILETIME,_BLBCAT_BACKUP_SET_INFO *)
0x1400119fc  mov     ebx, eax
0x1400119fe  test    eax, eax
0x140011a00  js      loc_140011AE9
0x140011a06  movups  xmm0, xmmword ptr [rdi]
0x140011a09  movdqu  xmmword ptr [rbp+0C0h+Buf1.Data1], xmm0
0x140011a0e  lea     rax, [rbp+0C0h+var_128]
0x140011a12  mov     [rsp+1C0h+var_198], rax; __int64
0x140011a17  lea     rax, [rbp+0C0h+var_108]
0x140011a1b  mov     [rsp+1C0h+var_1A0], rax; __int64
0x140011a20  lea     r9, [rsp+1C0h+var_148]
0x140011a25  lea     r8, [rdi+48h]
0x140011a29  lea     rdx, [rbp+0C0h+Buf1]
0x140011a2d  mov     rcx, r14; this
0x140011a30  call    ?PerformPruning@CBlbPruningContext@@QEAAJU_GUID@@PEAU_BLBSRV_VOLUME_MAP@@AEAV?$CAtlArray@U_BLB_FILESPEC_INFO@@V?$CElementTraits@U_BLB_FILESPEC_INFO@@@ATL@@@ATL@@22@Z; CBlbPruningContext::PerformPruning(_GUID,_BLBSRV_VOLUME_MAP *,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &,ATL::CAtlArray<_BLB_FILESPEC_INFO,ATL::CElementTraits<_BLB_FILESPEC_INFO>> &)
0x140011a35  mov     ebx, eax
0x140011a37  xor     r13d, r13d
0x140011a3a  test    eax, eax
0x140011a3c  js      loc_140011B62
0x140011a42  mov     rax, [r14]
0x140011a45  mov     rcx, r14
0x140011a48  mov     rax, [rax+10h]
0x140011a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a51  mov     [rsp+1C0h+var_158], r13
0x140011a56  test    rsi, rsi
0x140011a59  jz      short loc_140011A91
0x140011a5b  mov     rcx, rsi; unsigned __int16 *
0x140011a5e  call    ?Dismount@CBlbVhdHelper@@SAJPEBG@Z; CBlbVhdHelper::Dismount(ushort const *)
0x140011a63  mov     ebx, eax
0x140011a65  test    eax, eax
0x140011a67  js      loc_140011AF8
0x140011a6d  mov     rcx, [rdi+50h]; pv
0x140011a71  test    rcx, rcx
0x140011a74  jz      short loc_140011A80
0x140011a76  call    cs:__imp_CoTaskMemFree
0x140011a7c  mov     [rdi+50h], r13
0x140011a80  mov     rcx, rsi; pv
0x140011a83  call    cs:__imp_CoTaskMemFree
0x140011a89  mov     rsi, r13
0x140011a8c  mov     [rsp+1C0h+pv], r13
0x140011a91  mov     r14b, [rsp+1C0h+var_190]
0x140011a96  jmp     short loc_140011AD4
0x140011a98  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a9f  lea     rax, WPP_GLOBAL_Control
0x140011aa6  cmp     rcx, rax
0x140011aa9  jz      short loc_140011AD1
0x140011aab  test    byte ptr [rcx+1Ch], 1
0x140011aaf  jz      short loc_140011AD1
0x140011ab1  cmp     byte ptr [rcx+19h], 3
  ... truncated ...
```
