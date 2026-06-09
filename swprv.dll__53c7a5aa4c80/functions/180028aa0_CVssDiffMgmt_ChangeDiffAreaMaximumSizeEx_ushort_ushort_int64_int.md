# CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx(ushort *,ushort *,__int64,int)

- ea: `0x180028aa0`
- end: `0x1800294ce`
- name: `?ChangeDiffAreaMaximumSizeEx@CVssDiffMgmt@@UEAAJPEAG0_JH@Z`
- size: `2606`
- prototype: `__int64 __fastcall(CVssDiffMgmt *this, unsigned __int16 *, unsigned __int16 *, __int64, int)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800034cc`
- `0x180003888`
- `0x18000a6c4`
- `0x18001d7f0`
- `0x18001d8dc`
- `0x18001dc3c`
- `0x18001dd84`
- `0x18001e6f8`
- `0x18001e90c`
- `0x18001ea00`
- `0x180028aa0`
- `0x18002a280`
- `0x18002a4f8`
- `0x18002a774`
- `0x18002e79c`
- `0x180033a8c`
- `0x180033c78`
- `0x180034278`
- `0x180034324`
- `0x180034a4c`
- `0x18003649c`
- `0x1800367b8`
- `0x180039394`
- `0x18003d78c`
- `0x18003df28`
- `0x18003f1f4`
- `0x18003ff6c`
- `0x18004b010`

## string_xrefs

- `0x180028ae1`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028b85`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028c31`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028ca9`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028d27`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028da4`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028e32`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028ece`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028f35`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028fb1`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180029016`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x18002907e`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x1800292d4`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180029385`: `CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx`
- `0x180028dec`: `cannot remove a diff area with the volatile flag set`

## pseudocode

```c
__int64 __fastcall CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx(
        CVssDiffMgmt *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  bool v9; // dl
  unsigned int v10; // ecx
  const wchar_t *v11; // rax
  int AssociationFlags; // edi
  CVssDiffMgmt *v13; // rcx
  unsigned int SectorSizeForVolume; // esi
  CVssDiffMgmt *v15; // rcx
  bool v16; // dl
  bool IsExplicit; // si
  const unsigned __int16 *v18; // rdx
  unsigned int v19; // ebx
  __int64 v21; // [rsp+28h] [rbp-3B0h]
  const unsigned __int16 *v22; // [rsp+48h] [rbp-390h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-388h]
  const unsigned __int16 *v24; // [rsp+58h] [rbp-380h]
  int v25; // [rsp+60h] [rbp-378h]
  int v26; // [rsp+64h] [rbp-374h]
  int v27; // [rsp+68h] [rbp-370h]
  _BYTE v28[120]; // [rsp+70h] [rbp-368h] BYREF
  int v29; // [rsp+E8h] [rbp-2F0h]
  LPVOID v30; // [rsp+F0h] [rbp-2E8h] BYREF
  unsigned int v31; // [rsp+F8h] [rbp-2E0h]
  unsigned int v32; // [rsp+114h] [rbp-2C4h]
  int v33; // [rsp+160h] [rbp-278h] BYREF
  _com_error *v34; // [rsp+168h] [rbp-270h] BYREF
  const std::exception *v35; // [rsp+170h] [rbp-268h] BYREF
  LPCRITICAL_SECTION v36[3]; // [rsp+178h] [rbp-260h] BYREF
  struct _RTL_CRITICAL_SECTION v37[4]; // [rsp+190h] [rbp-248h] BYREF
  _BYTE v38[16]; // [rsp+240h] [rbp-198h] BYREF
  _QWORD v39[4]; // [rsp+250h] [rbp-188h] BYREF
  _QWORD v40[3]; // [rsp+270h] [rbp-168h] BYREF
  int v41; // [rsp+288h] [rbp-150h]
  int v42; // [rsp+28Ch] [rbp-14Ch]
  int v43; // [rsp+290h] [rbp-148h]
  _DWORD v44[34]; // [rsp+298h] [rbp-140h] BYREF
  unsigned __int16 v45[56]; // [rsp+320h] [rbp-B8h] BYREF

  v40[0] = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
  v40[1] = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
  v40[2] = L"SPRDIFMC";
  v41 = 464;
  v42 = 2;
  v43 = 255;
  v44[30] = 0x1000000;
  memset_0(v44, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v30, (__int64)v40, 0);
  try
  {
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
    v24 = L"SPRDIFMC";
    if ( !IsInGroup(v10, v9) )
    {
      v25 = 470;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(
        &v30,
        &v22,
        2147942405LL,
        L"The client process is not running under an administrator account");
    }
    v25 = 473;
    memset_0(v28, 0, sizeof(v28));
    v11 = L"TRUE";
    if ( !a5 )
      v11 = L"FALSE";
    CVssFunctionTracer::Trace(
      &v30,
      &v22,
      L"Parameters: pwszVolumeName = %s  pwszDiffAreaVolumeName = %s  llMaximumDiffSpace = %I64d  bVolatile = %s",
      a2,
      a3,
      a4,
      v11);
    if ( !a2 )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
      v24 = L"SPRDIFMC";
      v25 = 481;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v30, &v22, 2147942487LL, L"NULL pwszVolumeName");
    }
    if ( !a3 )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
      v24 = L"SPRDIFMC";
      v25 = 483;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v30, &v22, 2147942487LL, L"NULL pwszDiffAreaVolumeName");
    }
    if ( a4 < -1 )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
      v24 = L"SPRDIFMC";
      v25 = 485;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v30, &v22, 2147942487LL, L"Invalid llMaximumDiffSpace");
    }
    if ( a5 && !a4 )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
      v24 = L"SPRDIFMC";
      v25 = 487;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v30, &v22, 2147942487LL, L"cannot remove a diff area with the volatile flag set");
    }
    if ( (unsigned __int64)(a4 + 1) > 1 && a4 < CVssMachineInformation::GetMinDiffAreaOnVolume(a3) )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
      v24 = L"SPRDIFMC";
      v25 = 492;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v30, &v22, 2147754783LL, L"Not enough storage for the initial diff area allocation");
    }
    if ( (unsigned int)CVssSKU::IsClient() && a4 )
      (*(void (__fastcall **)(CVssDiffMgmt *, unsigned __int16 *, unsigned __int16 *, __int64))(*(_QWORD *)this + 144LL))(
        this,
        a2,
        a2,
        a4);
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
    v24 = L"SPRDIFMC";
    v25 = 502;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    GetVolumeNameWithCheck(&v22, 2147942487LL, a2, v45);
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
    v24 = L"SPRDIFMC";
    v25 = 507;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    GetVolumeNameWithCheck(&v22, 2147942487LL, a3, v40);
    CVssAutomaticLock2::CVssAutomaticLock2(
      (CVssAutomaticLock2 *)v36,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
    v24 = L"SPRDIFMC";
    v25 = 513;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v30, (const struct CVssDebugInfo *)&v22, 426);
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
    v24 = L"SPRDIFMC";
    v25 = 514;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    CVssFunctionTracer::AddContext((__int64)&v30, (const struct CVssDebugInfo *)&v22);
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
    v24 = L"SPRDIFMC";
    v25 = 515;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    CVssFunctionTracer::AddContext((__int64)&v30, (const struct CVssDebugInfo *)&v22);
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
    v24 = L"SPRDIFMC";
    v25 = 516;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    CVssFunctionTracer::AddContextEx(&v30, &v22, 5019, L"%I64u", a4);
    AssociationFlags = CVssDiffMgmt::GetAssociationFlags(v45, (unsigned __int16 *)v40);
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
    v24 = L"SPRDIFMC";
    v25 = 520;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    LODWORD(v21) = AssociationFlags;
    CVssFunctionTracer::Trace(&v30, &v22, L"An association is changing: %s - %s with flags 0x%08lx", v45, v40, v21);
    if ( (AssociationFlags & 4) != 0 )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
      v24 = L"SPRDIFMC";
      v25 = 523;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v30, &v22, 2147754760LL, L"Unsupported volume(s)");
    }
    if ( (AssociationFlags & 2) == 0 )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
      v24 = L"SPRDIFMC";
      v25 = 525;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v30, &v22, 2147754760LL, L"Unsupported volume(s)");
    }
    SectorSizeForVolume = CVssDiffMgmt::GetSectorSizeForVolume(v13, (unsigned __int16 *)v40);
    if ( SectorSizeForVolume > CVssDiffMgmt::GetSectorSizeForVolume(v15, v45) )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
      v24 = L"SPRDIFMC";
      v25 = 529;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(
        &v30,
        &v22,
        2147754764LL,
        L"Sector size of diff area volume must be <= sector size of original.");
    }
    CVssDiffArea::CVssDiffArea((CVssDiffArea *)v37, v16);
    CVssDiffArea::InitializeForVolume((CVssDiffArea *)v37, v45, 0);
    IsExplicit = CVssDiffArea::IsExplicit((CVssDiffArea *)v37);
    if ( a4 )
    {
      CVssDiffArea::ChangeDiffAreaMaximumSize((CVssDiffArea *)v37, a4, a5 != 0);
      if ( !IsExplicit )
        CVssDiffArea::SetExplicit((CVssDiffArea *)v37, 1);
    }
    else
    {
      if ( (AssociationFlags & 1) != 0 )
      {
        v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v23 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx";
        v24 = L"SPRDIFMC";
        v25 = 540;
        v26 = 2;
        v27 = 255;
        v29 = 0x1000000;
        memset_0(v28, 0, sizeof(v28));
        CVssFunctionTracer::Throw(&v30, &v22, 2147754781LL, L"The association is in use");
      }
      CVssDiffArea::Clear((CVssDiffArea *)v37);
      CVssClusterAPI::CVssClusterAPI((CVssClusterAPI *)v38);
      if ( CVssClusterAPI::Initialize((CVssClusterAPI *)v38, v18) )
        CVssClusterAPI::RemoveDependency((CVssClusterAPI *)v38, v45, (const unsigned __int16 *)v40);
      std::wstring::_Tidy_deallocate(v39);
    }
    CVssDiffArea::~CVssDiffArea(v37);
    CVssAutomaticLock2::~CVssAutomaticLock2(v36);
  }
  catch ( long v33 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v30,
      v33,
      L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
      L"SPRDIFMC",
      L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx",
      0x22Du,
      v32);
  }
  catch ( _com_error *v34 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v30,
      v34,
      L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
      L"SPRDIFMC",
      L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx",
      0x22Du,
      v32);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v30,
      L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
      L"SPRDIFMC",
      L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx",
      0x22Du,
      v32);
  }
  catch ( const std::exception *v35 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v30,
      v35,
      L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
      L"SPRDIFMC",
      L"CVssDiffMgmt::ChangeDiffAreaMaximumSizeEx",
      0x22Du,
      v32);
  }
  v22 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
  v26 = 2;
  v27 = 255;
}

```

## disassembly

```asm
0x180028aa0  mov     r11, rsp
0x180028aa3  push    rbx
0x180028aa4  push    rsi
0x180028aa5  push    rdi
0x180028aa6  push    r12
0x180028aa8  push    r13
0x180028aaa  push    r14
0x180028aac  push    r15
0x180028aae  sub     rsp, 3A0h
0x180028ab5  mov     rax, cs:__security_cookie
0x180028abc  xor     rax, rsp
0x180028abf  mov     [rsp+3D8h+var_48], rax
0x180028ac7  mov     rbx, r9
0x180028aca  mov     rdi, r8
0x180028acd  mov     rsi, rdx
0x180028ad0  mov     r14, rcx
0x180028ad3  lea     r15, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x180028ada  mov     [r11-168h], r15
0x180028ae1  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028ae8  mov     [r11-160h], rax
0x180028aef  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028af6  mov     [r11-158h], rax
0x180028afd  mov     [rsp+3D8h+var_150], 1D0h
0x180028b08  mov     r13d, 2
0x180028b0e  mov     [r11-14Ch], r13d
0x180028b15  mov     [rsp+3D8h+var_148], 0FFh
0x180028b20  mov     [rsp+3D8h+var_C8], 1000000h
0x180028b2b  xor     edx, edx; Val
0x180028b2d  lea     r8d, [r13+76h]; Size
0x180028b31  lea     rcx, [r11-140h]; void *
0x180028b38  call    memset_0
0x180028b3d  xor     r8d, r8d
0x180028b40  lea     rdx, [rsp+3D8h+var_168]
0x180028b48  lea     rcx, [rsp+3D8h+var_2E8]
0x180028b50  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180028b55  nop
0x180028b56  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x180028b5b  mov     [rsp+3D8h+var_390], r15
0x180028b60  mov     [rsp+3D8h+var_374], r13d
0x180028b65  mov     [rsp+3D8h+var_370], 0FFh
0x180028b6d  mov     [rsp+3D8h+var_2F0], 1000000h
0x180028b78  xor     edx, edx; Val
0x180028b7a  lea     r8d, [r13+76h]; Size
0x180028b7e  lea     rcx, [rsp+3D8h+var_368]; void *
0x180028b83  test    al, al
0x180028b85  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028b8c  mov     [rsp+3D8h+var_388], rax
0x180028b91  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028b98  mov     [rsp+3D8h+var_380], rax
0x180028b9d  jnz     short loc_180028BCB
0x180028b9f  mov     [rsp+3D8h+var_378], 1D6h
0x180028ba7  call    memset_0
0x180028bac  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x180028bb3  mov     r8d, 80070005h
0x180028bb9  lea     rdx, [rsp+3D8h+var_390]
0x180028bbe  lea     rcx, [rsp+3D8h+var_2E8]
0x180028bc6  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180028bcb  mov     [rsp+3D8h+var_378], 1D9h
0x180028bd3  call    memset_0
0x180028bd8  mov     r15d, [rsp+3D8h+arg_20]
0x180028be0  lea     rcx, aFalse; "FALSE"
0x180028be7  lea     rax, aTrue; "TRUE"
0x180028bee  test    r15d, r15d
0x180028bf1  cmovz   rax, rcx
0x180028bf5  mov     [rsp+3D8h+var_3A8], rax
0x180028bfa  mov     [rsp+3D8h+var_3B0], rbx
0x180028bff  mov     [rsp+3D8h+var_3B8], rdi
0x180028c04  mov     r9, rsi
0x180028c07  lea     r8, aParametersPwsz_4; "Parameters: pwszVolumeName = %s  pwszDi"...
0x180028c0e  lea     rdx, [rsp+3D8h+var_390]
0x180028c13  lea     rcx, [rsp+3D8h+var_2E8]
0x180028c1b  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180028c20  test    rsi, rsi
0x180028c23  jnz     short loc_180028C98
0x180028c25  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x180028c2c  mov     [rsp+3D8h+var_390], rax
0x180028c31  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028c38  mov     [rsp+3D8h+var_388], rax
0x180028c3d  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028c44  mov     [rsp+3D8h+var_380], rax
0x180028c49  mov     [rsp+3D8h+var_378], 1E1h
0x180028c51  mov     [rsp+3D8h+var_374], r13d
0x180028c56  mov     [rsp+3D8h+var_370], 0FFh
0x180028c5e  mov     [rsp+3D8h+var_2F0], 1000000h
0x180028c69  xor     edx, edx; Val
0x180028c6b  lea     r8d, [rsi+78h]; Size
0x180028c6f  lea     rcx, [rsp+3D8h+var_368]; void *
0x180028c74  call    memset_0
0x180028c79  lea     r9, aNullPwszvolume; "NULL pwszVolumeName"
0x180028c80  mov     r8d, 80070057h
0x180028c86  lea     rdx, [rsp+3D8h+var_390]
0x180028c8b  lea     rcx, [rsp+3D8h+var_2E8]
0x180028c93  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180028c98  test    rdi, rdi
0x180028c9b  jnz     short loc_180028D10
0x180028c9d  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x180028ca4  mov     [rsp+3D8h+var_390], rax
0x180028ca9  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028cb0  mov     [rsp+3D8h+var_388], rax
0x180028cb5  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028cbc  mov     [rsp+3D8h+var_380], rax
0x180028cc1  mov     [rsp+3D8h+var_378], 1E3h
0x180028cc9  mov     [rsp+3D8h+var_374], r13d
0x180028cce  mov     [rsp+3D8h+var_370], 0FFh
0x180028cd6  mov     [rsp+3D8h+var_2F0], 1000000h
0x180028ce1  xor     edx, edx; Val
0x180028ce3  lea     r8d, [rdi+78h]; Size
0x180028ce7  lea     rcx, [rsp+3D8h+var_368]; void *
0x180028cec  call    memset_0
0x180028cf1  lea     r9, aNullPwszdiffar; "NULL pwszDiffAreaVolumeName"
0x180028cf8  mov     r8d, 80070057h
0x180028cfe  lea     rdx, [rsp+3D8h+var_390]
0x180028d03  lea     rcx, [rsp+3D8h+var_2E8]
0x180028d0b  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180028d10  test    rbx, rbx
0x180028d13  jns     short loc_180028D8E
0x180028d15  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180028d19  jz      short loc_180028D8E
0x180028d1b  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x180028d22  mov     [rsp+3D8h+var_390], rax
0x180028d27  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028d2e  mov     [rsp+3D8h+var_388], rax
0x180028d33  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028d3a  mov     [rsp+3D8h+var_380], rax
0x180028d3f  mov     [rsp+3D8h+var_378], 1E5h
0x180028d47  mov     [rsp+3D8h+var_374], r13d
0x180028d4c  mov     [rsp+3D8h+var_370], 0FFh
0x180028d54  mov     [rsp+3D8h+var_2F0], 1000000h
0x180028d5f  xor     edx, edx; Val
0x180028d61  lea     r8d, [rdx+78h]; Size
0x180028d65  lea     rcx, [rsp+3D8h+var_368]; void *
0x180028d6a  call    memset_0
0x180028d6f  lea     r9, aInvalidLlmaxim; "Invalid llMaximumDiffSpace"
0x180028d76  mov     r8d, 80070057h
0x180028d7c  lea     rdx, [rsp+3D8h+var_390]
0x180028d81  lea     rcx, [rsp+3D8h+var_2E8]
0x180028d89  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180028d8e  test    r15d, r15d
0x180028d91  jz      short loc_180028E0B
0x180028d93  test    rbx, rbx
0x180028d96  jnz     short loc_180028E0B
0x180028d98  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x180028d9f  mov     [rsp+3D8h+var_390], rax
0x180028da4  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028dab  mov     [rsp+3D8h+var_388], rax
0x180028db0  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028db7  mov     [rsp+3D8h+var_380], rax
0x180028dbc  mov     [rsp+3D8h+var_378], 1E7h
0x180028dc4  mov     [rsp+3D8h+var_374], r13d
0x180028dc9  mov     [rsp+3D8h+var_370], 0FFh
0x180028dd1  mov     [rsp+3D8h+var_2F0], 1000000h
0x180028ddc  xor     edx, edx; Val
0x180028dde  lea     r8d, [rbx+78h]; Size
0x180028de2  lea     rcx, [rsp+3D8h+var_368]; void *
0x180028de7  call    memset_0
0x180028dec  lea     r9, aCannotRemoveAD; "cannot remove a diff area with the vola"...
0x180028df3  mov     r8d, 80070057h
0x180028df9  lea     rdx, [rsp+3D8h+var_390]
0x180028dfe  lea     rcx, [rsp+3D8h+var_2E8]
0x180028e06  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180028e0b  lea     rax, [rbx+1]
0x180028e0f  cmp     rax, 1
0x180028e13  jbe     loc_180028E99
0x180028e19  mov     rcx, rdi; unsigned __int16 *
0x180028e1c  call    ?GetMinDiffAreaOnVolume@CVssMachineInformation@@SA_JPEBG@Z; CVssMachineInformation::GetMinDiffAreaOnVolume(ushort const *)
0x180028e21  cmp     rbx, rax
0x180028e24  jge     short loc_180028E99
0x180028e26  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x180028e2d  mov     [rsp+3D8h+var_390], rax
0x180028e32  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028e39  mov     [rsp+3D8h+var_388], rax
0x180028e3e  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028e45  mov     [rsp+3D8h+var_380], rax
0x180028e4a  mov     [rsp+3D8h+var_378], 1ECh
0x180028e52  mov     [rsp+3D8h+var_374], r13d
0x180028e57  mov     [rsp+3D8h+var_370], 0FFh
0x180028e5f  mov     [rsp+3D8h+var_2F0], 1000000h
0x180028e6a  xor     edx, edx; Val
0x180028e6c  lea     r8d, [rdx+78h]; Size
0x180028e70  lea     rcx, [rsp+3D8h+var_368]; void *
0x180028e75  call    memset_0
0x180028e7a  lea     r9, aNotEnoughStora; "Not enough storage for the initial diff"...
0x180028e81  mov     r8d, 8004231Fh
0x180028e87  lea     rdx, [rsp+3D8h+var_390]
0x180028e8c  lea     rcx, [rsp+3D8h+var_2E8]
0x180028e94  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180028e99  call    ?IsClient@CVssSKU@@SAHXZ; CVssSKU::IsClient(void)
0x180028e9e  test    eax, eax
0x180028ea0  jz      short loc_180028EC2
0x180028ea2  test    rbx, rbx
0x180028ea5  jz      short loc_180028EC2
0x180028ea7  mov     rax, [r14]
0x180028eaa  mov     r9, rbx
0x180028ead  mov     r8, rsi
0x180028eb0  mov     rdx, rsi
0x180028eb3  mov     rcx, r14
0x180028eb6  mov     rax, [rax+90h]
0x180028ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ec2  lea     r14, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x180028ec9  mov     [rsp+3D8h+var_390], r14
0x180028ece  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028ed5  mov     [rsp+3D8h+var_388], rax
0x180028eda  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028ee1  mov     [rsp+3D8h+var_380], rax
0x180028ee6  mov     [rsp+3D8h+var_378], 1F6h
0x180028eee  mov     [rsp+3D8h+var_374], r13d
0x180028ef3  mov     [rsp+3D8h+var_370], 0FFh
0x180028efb  mov     [rsp+3D8h+var_2F0], 1000000h
0x180028f06  xor     edx, edx; Val
0x180028f08  lea     r8d, [rdx+78h]; Size
0x180028f0c  lea     rcx, [rsp+3D8h+var_368]; void *
0x180028f11  call    memset_0
0x180028f16  lea     r9, [rsp+3D8h+var_B8]
0x180028f1e  mov     r8, rsi
0x180028f21  mov     edx, 80070057h
0x180028f26  lea     rcx, [rsp+3D8h+var_390]
0x180028f2b  call    ?GetVolumeNameWithCheck@@YAXUCVssDebugInfo@@JPEBGPEAGK@Z; GetVolumeNameWithCheck(CVssDebugInfo,long,ushort const *,ushort *,ulong)
0x180028f30  mov     [rsp+3D8h+var_390], r14
0x180028f35  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028f3c  mov     [rsp+3D8h+var_388], rax
0x180028f41  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028f48  mov     [rsp+3D8h+var_380], rax
0x180028f4d  mov     [rsp+3D8h+var_378], 1FBh
0x180028f55  mov     [rsp+3D8h+var_374], r13d
0x180028f5a  mov     [rsp+3D8h+var_370], 0FFh
0x180028f62  mov     [rsp+3D8h+var_2F0], 1000000h
0x180028f6d  xor     edx, edx; Val
0x180028f6f  lea     r8d, [rdx+78h]; Size
0x180028f73  lea     rcx, [rsp+3D8h+var_368]; void *
0x180028f78  call    memset_0
0x180028f7d  lea     r9, [rsp+3D8h+var_168]
0x180028f85  mov     r8, rdi
0x180028f88  mov     edx, 80070057h
0x180028f8d  lea     rcx, [rsp+3D8h+var_390]
0x180028f92  call    ?GetVolumeNameWithCheck@@YAXUCVssDebugInfo@@JPEBGPEAGK@Z; GetVolumeNameWithCheck(CVssDebugInfo,long,ushort const *,ushort *,ulong)
0x180028f97  lea     rdx, ?m_cs@CVsSoftwareProvider@@0VCVssCriticalSection@@A; struct CVssCriticalSection *
0x180028f9e  lea     rcx, [rsp+3D8h+var_260]; this
0x180028fa6  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x180028fab  nop
0x180028fac  mov     [rsp+3D8h+var_390], r14
0x180028fb1  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180028fb8  mov     [rsp+3D8h+var_388], rax
0x180028fbd  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028fc4  mov     [rsp+3D8h+var_380], rax
0x180028fc9  mov     [rsp+3D8h+var_378], 201h
0x180028fd1  mov     [rsp+3D8h+var_374], r13d
0x180028fd6  mov     [rsp+3D8h+var_370], 0FFh
0x180028fde  mov     [rsp+3D8h+var_2F0], 1000000h
0x180028fe9  xor     edx, edx; Val
0x180028feb  lea     r8d, [rdx+78h]; Size
0x180028fef  lea     rcx, [rsp+3D8h+var_368]; void *
0x180028ff4  call    memset_0
0x180028ff9  mov     r8d, 1AAh
0x180028fff  lea     rdx, [rsp+3D8h+var_390]
0x180029004  lea     rcx, [rsp+3D8h+var_2E8]
0x18002900c  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x180029011  mov     [rsp+3D8h+var_390], r14
0x180029016  lea     rax, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x18002901d  mov     [rsp+3D8h+var_388], rax
0x180029022  lea     rax, aSprdifmc; "SPRDIFMC"
0x180029029  mov     [rsp+3D8h+var_380], rax
0x18002902e  mov     [rsp+3D8h+var_378], 202h
0x180029036  mov     [rsp+3D8h+var_374], r13d
0x18002903b  mov     [rsp+3D8h+var_370], 0FFh
0x180029043  mov     [rsp+3D8h+var_2F0], 1000000h
0x18002904e  xor     edx, edx; Val
0x180029050  lea     r8d, [rdx+78h]; Size
0x180029054  lea     rcx, [rsp+3D8h+var_368]; void *
0x180029059  call    memset_0
0x18002905e  mov     r9, rsi
0x180029061  mov     r8d, 1392h
0x180029067  lea     rdx, [rsp+3D8h+var_390]
0x18002906c  lea     rcx, [rsp+3D8h+var_2E8]
0x180029074  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x180029079  mov     [rsp+3D8h+var_390], r14
0x18002907e  lea     rsi, aCvssdiffmgmtCh_0; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"...
0x180029085  mov     [rsp+3D8h+var_388], rsi
0x18002908a  lea     rax, aSprdifmc; "SPRDIFMC"
0x180029091  mov     [rsp+3D8h+var_380], rax
0x180029096  mov     [rsp+3D8h+var_378], 203h
0x18002909e  mov     [rsp+3D8h+var_374], r13d
0x1800290a3  mov     [rsp+3D8h+var_370], 0FFh
0x1800290ab  mov     [rsp+3D8h+var_2F0], 1000000h
0x1800290b6  xor     edx, edx; Val
0x1800290b8  lea     r8d, [rdx+78h]; Size
0x1800290bc  lea     rcx, [rsp+3D8h+var_368]; void *
0x1800290c1  call    memset_0
0x1800290c6  mov     r9, rdi
0x1800290c9  mov     r8d, 139Ah
0x1800290cf  lea     rdx, [rsp+3D8h+var_390]
0x1800290d4  lea     rcx, [rsp+3D8h+var_2E8]
0x1800290dc  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x1800290e1  mov     [rsp+3D8h+var_390], r14
0x1800290e6  mov     [rsp+3D8h+var_388], rsi
0x1800290eb  lea     rax, aSprdifmc; "SPRDIFMC"
0x1800290f2  mov     [rsp+3D8h+var_380], rax
0x1800290f7  mov     [rsp+3D8h+var_378], 204h
0x1800290ff  mov     [rsp+3D8h+var_374], r13d
0x180029104  mov     [rsp+3D8h+var_370], 0FFh
0x18002910c  mov     [rsp+3D8h+var_2F0], 1000000h
  ... truncated ...
```
