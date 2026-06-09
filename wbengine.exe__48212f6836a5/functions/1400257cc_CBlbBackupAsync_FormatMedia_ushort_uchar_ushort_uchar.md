# CBlbBackupAsync::FormatMedia(ushort *,uchar,ushort *,uchar *)

- ea: `0x1400257cc`
- end: `0x140025e5f`
- name: `?FormatMedia@CBlbBackupAsync@@AEAAJPEAGE0PEAE@Z`
- size: `1683`
- prototype: `int(CBlbBackupAsync *__hidden this, unsigned __int16 *, unsigned __int8, unsigned __int16 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, service_task`

## callers

- `0x140019fd0`
- `0x14002d79c`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x1400154f0`
- `0x1400257cc`
- `0x14008863c`
- `0x1400889f0`
- `0x140092184`
- `0x14009257c`
- `0x140093964`
- `0x14010158c`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400258af`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140025aea`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400258af`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140025aea`
- `KERNEL32!WaitForSingleObject` at `0x140025db8`
- `KERNEL32!WaitForSingleObject` at `0x140025db8`
- `KERNEL32!CreateEventW` at `0x140025a6a`
- `KERNEL32!CreateEventW` at `0x140025a6a`
- `KERNEL32!FreeLibrary` at `0x140025a0f`
- `KERNEL32!FreeLibrary` at `0x140025a3e`
- `KERNEL32!FreeLibrary` at `0x140025a0f`
- `KERNEL32!FreeLibrary` at `0x140025a3e`
- `KERNEL32!GetProcAddress` at `0x1400259f6`
- `KERNEL32!GetProcAddress` at `0x140025a25`
- `KERNEL32!GetProcAddress` at `0x1400259f6`
- `KERNEL32!GetProcAddress` at `0x140025a25`
- `KERNEL32!GetLastError` at `0x1400259ce`
- `KERNEL32!GetLastError` at `0x1400259ce`
- `ole32!CoTaskMemFree` at `0x140025b0d`
- `ole32!CoTaskMemFree` at `0x140025b1b`
- `ole32!CoTaskMemFree` at `0x140025b0d`
- `ole32!CoTaskMemFree` at `0x140025b1b`

## string_xrefs

- `0x14002589c`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400259a7`: `base\stor\blb\engine\service\backup.cpp`
- `0x140025d0f`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400259b6`: `fmifs.dll`
- `0x140025d3f`: `FORMAT_ON_WRITE_TYPE(eMediaType)`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::FormatMedia(
        CBlbBackupAsync *this,
        unsigned __int16 *a2,
        char a3,
        unsigned __int16 *a4,
        unsigned __int8 *a5)
{
  int v5; // r15d
  void *v6; // r14
  unsigned __int16 *v7; // r12
  const wchar_t *v11; // r9
  void *v12; // rdx
  int appended; // eax
  signed int VolumeMediaType; // ebx
  HMODULE System32Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  HMODULE v18; // rcx
  FARPROC v19; // rax
  HANDLE EventW; // rax
  PVOID *v22; // rcx
  __int64 v23; // rcx
  unsigned __int8 (__fastcall *v24)(__int64, __int128 *, __int64); // rax
  __int64 v25; // rdx
  void (__fastcall *v26)(unsigned __int16 *, __int64, const wchar_t *, __int128 *, void *); // rsi
  unsigned int v27; // ebx
  const wchar_t *v28; // r8
  unsigned int v29; // ebx
  __int64 v30; // rdx
  unsigned __int16 *v31; // r15
  int v32; // [rsp+30h] [rbp-71h] BYREF
  unsigned __int16 *v33; // [rsp+38h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-61h] BYREF
  __int128 v35; // [rsp+48h] [rbp-59h] BYREF
  __int128 v36; // [rsp+58h] [rbp-49h]
  __int128 v37; // [rsp+68h] [rbp-39h]
  __int64 v38; // [rsp+78h] [rbp-29h]
  unsigned __int16 *v39; // [rsp+80h] [rbp-21h]
  unsigned __int8 *v40; // [rsp+88h] [rbp-19h]
  __int128 v41; // [rsp+90h] [rbp-11h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+A0h] [rbp-1h] BYREF

  v39 = a2;
  v5 = 0;
  v40 = a5;
  v6 = 0;
  v38 = 0;
  v7 = 0;
  v32 = 0;
  v33 = 0;
  pv = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v41 = 0;
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v11 = L"YES";
    if ( !a3 )
      v11 = L"NO";
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      215,
      (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
      (_DWORD)v11,
      (__int64)a2);
  }
  if ( !a5 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x146Au, "pbMediaFailure");
  *a5 = 0;
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  if ( !a3 )
  {
    appended = BlbutilAppendString(a2, L"\\", (unsigned __int16 **)&pv);
    v6 = pv;
    VolumeMediaType = appended;
    if ( appended < 0 )
      goto LABEL_40;
    VolumeMediaType = BlbQueryVolumeMediaType((unsigned __int16 *)pv, (enum _BLB_MEDIA_TYPE *)&v32);
    if ( VolumeMediaType < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          216,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (_DWORD)v6,
          VolumeMediaType);
      }
      goto LABEL_40;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = v32;
    }
    else
    {
      v5 = v32;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        217,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (_DWORD)v6,
        v32);
    }
  }
  if ( !*((_QWORD *)this + 68) )
  {
    if ( *((_QWORD *)this + 67) )
      BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x148Du, "!m_hFmifs");
    System32Library = BlbLoadSystem32LibraryEx(L"fmifs.dll", v12, 0);
    *((_QWORD *)this + 67) = System32Library;
    if ( !System32Library )
      goto LABEL_25;
    ProcAddress = GetProcAddress(System32Library, "FormatEx2");
    v18 = (HMODULE)*((_QWORD *)this + 67);
    *((_QWORD *)this + 68) = ProcAddress;
    if ( !ProcAddress )
    {
      FreeLibrary(v18);
      *((_QWORD *)this + 67) = 0;
      goto LABEL_25;
    }
    v19 = GetProcAddress(v18, "QueryDeviceInformation");
    *((_QWORD *)this + 69) = v19;
    if ( !v19 )
    {
      FreeLibrary(*((HMODULE *)this + 67));
      *((_QWORD *)this + 67) = 0;
      *((_QWORD *)this + 68) = 0;
      goto LABEL_25;
    }
  }
  if ( !*((_QWORD *)this + 70) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 70) = EventW;
    if ( !EventW )
    {
LABEL_25:
      LastError = GetLastError();
      VolumeMediaType = LastError;
      if ( LastError > 0 )
        VolumeMediaType = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_40;
    }
  }
  if ( a3 )
  {
    VolumeMediaType = BlbutilPrepareLabelForTargetMediaFormatting(
                        *(struct _FILETIME *)((char *)this + 392),
                        *((_DWORD *)this + 56) + 1,
                        &v33);
    if ( VolumeMediaType < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      goto LABEL_39;
    }
  }
  else
  {
    VolumeMediaType = BlbutilDuplicateString(&String1, &v33, 0);
    if ( VolumeMediaType < 0 )
    {
LABEL_39:
      v7 = v33;
      goto LABEL_40;
    }
  }
  v7 = v33;
  v38 = 0;
  LODWORD(v35) = 2;
  v36 = 0;
  LODWORD(v36) = 0;
  WORD2(v36) = 0;
  *((_QWORD *)&v35 + 1) = v33;
  DWORD1(v35) = a3 != 0 ? 4 : 37;
  v37 = 0;
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v33);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( *((_DWORD *)this + 84) != 1 )
    {
      if ( v22 == &WPP_GLOBAL_Control || (*((_BYTE *)v22 + 28) & 1) == 0 || *((_BYTE *)v22 + 25) < 4u )
        goto LABEL_74;
      v25 = 223;
      goto LABEL_73;
    }
    v23 = *((_QWORD *)this + 44);
    v24 = (unsigned __int8 (__fastcall *)(__int64, __int128 *, __int64))*((_QWORD *)this + 69);
    v41 = 0;
    if ( !v24(v23, &v41, 16) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          220,
          &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          *((_QWORD *)this + 44));
      }
      VolumeMediaType = -2139619258;
      *a5 = 1;
      goto LABEL_40;
    }
    if ( (v41 & 0x80u) != 0LL )
    {
      v22 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_74;
      }
      v25 = 221;
LABEL_73:
      WPP_SF_(v22[2], v25, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_74:
      DWORD1(v35) |= 1u;
      goto LABEL_75;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
  }
LABEL_75:
  if ( CBlbBackupAsync::s_pFormatBackupContext )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x14F8u, "!s_pFormatBackupContext");
  v26 = (void (__fastcall *)(unsigned __int16 *, __int64, const wchar_t *, __int128 *, void *))*((_QWORD *)this + 68);
  CBlbBackupAsync::s_pFormatBackupContext = this;
  if ( a3 )
  {
    v27 = *((_DWORD *)this + 84);
    if ( (BlbutilGetBackupFeatures(v27) & 0x20) == 0 )
      BlbAssert("base\\stor\\blb\\util\\blbutility.cpp", 0x188u, "FORMAT_ON_WRITE_TYPE(eMediaType)");
    v28 = 0;
    v29 = v27 - 1;
    if ( v29 )
    {
      if ( v29 == 4 )
        v28 = L"NTFS";
    }
    else
    {
      v28 = L"UDF";
    }
  }
  else
  {
    v28 = L"NTFS";
    v30 = 12;
    if ( v5 != 5 )
      goto LABEL_86;
  }
  v30 = 11;
LABEL_86:
  v31 = v39;
  v26(v39, v30, v28, &v35, &BlbFormatCallback);
  if ( WaitForSingleObject(*((HANDLE *)this + 70), 0xFFFFFFFF) == -1 )
    goto LABEL_25;
  VolumeMediaType = *((_DWORD *)this + 8);
  if ( VolumeMediaType == -2139619258 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v31);
    }
    *v40 = 1;
  }
  CBlbBackupAsync::s_pFormatBackupContext = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
LABEL_40:
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
  if ( a3 )
    ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add((char *)this + 648, SystemTimeAsFileTime);
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v6 )
    CoTaskMemFree(v6);
  return (unsigned int)VolumeMediaType;
}

```

## disassembly

```asm
0x1400257cc  mov     [rsp-8+arg_10], rbx
0x1400257d1  push    rbp
0x1400257d2  push    rsi
0x1400257d3  push    rdi
0x1400257d4  push    r12
0x1400257d6  push    r13
0x1400257d8  push    r14
0x1400257da  push    r15
0x1400257dc  lea     rbp, [rsp-1Fh]
0x1400257e1  sub     rsp, 0C0h
0x1400257e8  mov     rax, cs:__security_cookie
0x1400257ef  xor     rax, rsp
0x1400257f2  mov     [rbp+4Fh+var_40], rax
0x1400257f6  mov     rsi, [rbp+4Fh+arg_20]
0x1400257fa  xorps   xmm0, xmm0
0x1400257fd  xor     eax, eax
0x1400257ff  mov     [rbp+4Fh+var_70], rdx
0x140025803  xor     r15d, r15d
0x140025806  mov     [rbp+4Fh+var_68], rsi
0x14002580a  xor     r14d, r14d
0x14002580d  mov     [rbp+4Fh+var_78], rax
0x140025811  xor     r12d, r12d
0x140025814  mov     [rbp+4Fh+var_C0], r15d
0x140025818  mov     [rbp+4Fh+var_B8], r12
0x14002581c  mov     r13b, r8b
0x14002581f  mov     rbx, rdx
0x140025822  mov     [rbp+4Fh+pv], r14
0x140025826  mov     rdi, rcx
0x140025829  movups  [rbp+4Fh+var_A8], xmm0
0x14002582d  movups  [rbp+4Fh+var_98], xmm0
0x140025831  movups  [rbp+4Fh+var_88], xmm0
0x140025835  movups  [rbp+4Fh+var_60], xmm0
0x140025839  movups  xmmword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x14002583d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025844  lea     rax, WPP_GLOBAL_Control
0x14002584b  cmp     rcx, rax
0x14002584e  jz      short loc_14002588B
0x140025850  test    byte ptr [rcx+1Ch], 1
0x140025854  jz      short loc_14002588B
0x140025856  cmp     byte ptr [rcx+19h], 5
0x14002585a  jb      short loc_14002588B
0x14002585c  mov     rcx, [rcx+10h]
0x140025860  lea     rax, aNo_0; "NO"
0x140025867  test    r8b, r8b
0x14002586a  mov     [rsp+0F0h+var_D0], rbx
0x14002586f  lea     r9, aYes; "YES"
0x140025876  mov     edx, 0D7h
0x14002587b  cmovz   r9, rax
0x14002587f  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140025886  call    WPP_SF_SS
0x14002588b  test    rsi, rsi
0x14002588e  jnz     short loc_1400258A8
0x140025890  lea     r8, aPbmediafailure; "pbMediaFailure"
0x140025897  mov     edx, 146Ah; unsigned int
0x14002589c  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400258a3  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400258a8  lea     rcx, [rbp+4Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400258ac  mov     [rsi], r12b
0x1400258af  call    cs:__imp_GetSystemTimeAsFileTime
0x1400258b5  test    r13b, r13b
0x1400258b8  jnz     loc_140025983
0x1400258be  lea     r8, [rbp+4Fh+pv]; unsigned __int16 **
0x1400258c2  mov     rcx, rbx; unsigned __int16 *
0x1400258c5  lea     rdx, asc_14013C090; "\\"
0x1400258cc  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400258d1  mov     r14, [rbp+4Fh+pv]
0x1400258d5  mov     ebx, eax
0x1400258d7  test    eax, eax
0x1400258d9  js      loc_140025AE6
0x1400258df  lea     rdx, [rbp+4Fh+var_C0]; enum _BLB_MEDIA_TYPE *
0x1400258e3  mov     rcx, r14; unsigned __int16 *
0x1400258e6  call    ?BlbQueryVolumeMediaType@@YAJPEAGPEAW4_BLB_MEDIA_TYPE@@@Z; BlbQueryVolumeMediaType(ushort *,_BLB_MEDIA_TYPE *)
0x1400258eb  mov     ebx, eax
0x1400258ed  test    eax, eax
0x1400258ef  jns     short loc_14002593D
0x1400258f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400258f8  lea     rax, WPP_GLOBAL_Control
0x1400258ff  cmp     rcx, rax
0x140025902  jz      loc_140025AE6
0x140025908  test    byte ptr [rcx+1Ch], 1
0x14002590c  jz      loc_140025AE6
0x140025912  cmp     byte ptr [rcx+19h], 2
0x140025916  jb      loc_140025AE6
0x14002591c  mov     rcx, [rcx+10h]
0x140025920  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140025927  mov     edx, 0D8h
0x14002592c  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x140025930  mov     r9, r14
0x140025933  call    WPP_SF_Sd
0x140025938  jmp     loc_140025AE6
0x14002593d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025944  lea     rax, WPP_GLOBAL_Control
0x14002594b  cmp     rcx, rax
0x14002594e  jz      short loc_14002597F
0x140025950  test    byte ptr [rcx+1Ch], 1
0x140025954  jz      short loc_14002597F
0x140025956  cmp     byte ptr [rcx+19h], 4
0x14002595a  jb      short loc_14002597F
0x14002595c  mov     r15d, [rbp+4Fh+var_C0]
0x140025960  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140025967  mov     rcx, [rcx+10h]
0x14002596b  mov     edx, 0D9h
0x140025970  mov     r9, r14
0x140025973  mov     dword ptr [rsp+0F0h+var_D0], r15d
0x140025978  call    WPP_SF_Sd
0x14002597d  jmp     short loc_140025983
0x14002597f  mov     r15d, [rbp+4Fh+var_C0]
0x140025983  xor     ebx, ebx
0x140025985  cmp     [rdi+220h], rbx
0x14002598c  jnz     loc_140025A57
0x140025992  cmp     [rdi+218h], rbx
0x140025999  jz      short loc_1400259B3
0x14002599b  lea     r8, aMHfmifs; "!m_hFmifs"
0x1400259a2  mov     edx, 148Dh; unsigned int
0x1400259a7  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400259ae  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400259b3  xor     r8d, r8d; unsigned int
0x1400259b6  lea     rcx, aFmifsDll; "fmifs.dll"
0x1400259bd  call    ?BlbLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; BlbLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x1400259c2  mov     [rdi+218h], rax
0x1400259c9  test    rax, rax
0x1400259cc  jnz     short loc_1400259EC
0x1400259ce  call    cs:__imp_GetLastError
0x1400259d4  mov     ebx, eax
0x1400259d6  test    eax, eax
0x1400259d8  jle     loc_140025AE6
0x1400259de  movzx   ebx, ax
0x1400259e1  or      ebx, 80070000h
0x1400259e7  jmp     loc_140025AE6
0x1400259ec  lea     rdx, aFormatex2; "FormatEx2"
0x1400259f3  mov     rcx, rax; hModule
0x1400259f6  call    cs:__imp_GetProcAddress
0x1400259fc  mov     rcx, [rdi+218h]; hModule
0x140025a03  mov     [rdi+220h], rax
0x140025a0a  test    rax, rax
0x140025a0d  jnz     short loc_140025A1E
0x140025a0f  call    cs:__imp_FreeLibrary
0x140025a15  mov     [rdi+218h], rbx
0x140025a1c  jmp     short loc_1400259CE
0x140025a1e  lea     rdx, aQuerydeviceinf; "QueryDeviceInformation"
0x140025a25  call    cs:__imp_GetProcAddress
0x140025a2b  mov     [rdi+228h], rax
0x140025a32  test    rax, rax
0x140025a35  jnz     short loc_140025A57
0x140025a37  mov     rcx, [rdi+218h]; hLibModule
0x140025a3e  call    cs:__imp_FreeLibrary
0x140025a44  mov     [rdi+218h], rbx
0x140025a4b  mov     [rdi+220h], rbx
0x140025a52  jmp     loc_1400259CE
0x140025a57  cmp     [rdi+230h], rbx
0x140025a5e  jnz     short loc_140025A80
0x140025a60  xor     r9d, r9d; lpName
0x140025a63  xor     r8d, r8d; bInitialState
0x140025a66  xor     edx, edx; bManualReset
0x140025a68  xor     ecx, ecx; lpEventAttributes
0x140025a6a  call    cs:__imp_CreateEventW
0x140025a70  mov     [rdi+230h], rax
0x140025a77  test    rax, rax
0x140025a7a  jz      loc_1400259CE
0x140025a80  test    r13b, r13b
0x140025a83  jz      loc_140025B4A
0x140025a89  mov     edx, [rdi+0E0h]
0x140025a8f  lea     r8, [rbp+4Fh+var_B8]; unsigned __int16 **
0x140025a93  mov     rcx, [rdi+188h]; struct _FILETIME
0x140025a9a  inc     edx; unsigned int
0x140025a9c  call    ?BlbutilPrepareLabelForTargetMediaFormatting@@YAJU_FILETIME@@KAEAPEAG@Z; BlbutilPrepareLabelForTargetMediaFormatting(_FILETIME,ulong,ushort * &)
0x140025aa1  mov     ebx, eax
0x140025aa3  test    eax, eax
0x140025aa5  jns     loc_140025B67
0x140025aab  mov     rcx, cs:WPP_GLOBAL_Control
0x140025ab2  lea     rax, WPP_GLOBAL_Control
0x140025ab9  cmp     rcx, rax
0x140025abc  jz      short loc_140025AE2
0x140025abe  test    byte ptr [rcx+1Ch], 1
0x140025ac2  jz      short loc_140025AE2
0x140025ac4  cmp     byte ptr [rcx+19h], 2
0x140025ac8  jb      short loc_140025AE2
0x140025aca  mov     rcx, [rcx+10h]
0x140025ace  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140025ad5  mov     edx, 0DAh
0x140025ada  mov     r9d, ebx
0x140025add  call    WPP_SF_d
0x140025ae2  mov     r12, [rbp+4Fh+var_B8]
0x140025ae6  lea     rcx, [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x140025aea  call    cs:__imp_GetSystemTimeAsFileTime
0x140025af0  test    r13b, r13b
0x140025af3  jz      short loc_140025B05
0x140025af5  lea     rcx, [rdi+288h]
0x140025afc  lea     rdx, [rbp+4Fh+SystemTimeAsFileTime]
0x140025b00  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x140025b05  test    r12, r12
0x140025b08  jz      short loc_140025B13
0x140025b0a  mov     rcx, r12; pv
0x140025b0d  call    cs:__imp_CoTaskMemFree
0x140025b13  test    r14, r14
0x140025b16  jz      short loc_140025B21
0x140025b18  mov     rcx, r14; pv
0x140025b1b  call    cs:__imp_CoTaskMemFree
0x140025b21  mov     eax, ebx
0x140025b23  mov     rcx, [rbp+4Fh+var_40]
0x140025b27  xor     rcx, rsp; StackCookie
0x140025b2a  call    __security_check_cookie
0x140025b2f  mov     rbx, [rsp+0F0h+arg_10]
0x140025b37  add     rsp, 0C0h
0x140025b3e  pop     r15
0x140025b40  pop     r14
0x140025b42  pop     r13
0x140025b44  pop     r12
0x140025b46  pop     rdi
0x140025b47  pop     rsi
0x140025b48  pop     rbp
0x140025b49  retn
0x140025b4a  xor     r8d, r8d; unsigned __int64
0x140025b4d  lea     rdx, [rbp+4Fh+var_B8]; unsigned __int16 **
0x140025b51  lea     rcx, String1; unsigned __int16 *
0x140025b58  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140025b5d  mov     ebx, eax
0x140025b5f  test    eax, eax
0x140025b61  js      loc_140025AE2
0x140025b67  mov     r12, [rbp+4Fh+var_B8]
0x140025b6b  xor     eax, eax
0x140025b6d  xor     ebx, ebx
0x140025b6f  mov     [rbp+4Fh+var_78], rax
0x140025b73  xorps   xmm0, xmm0
0x140025b76  mov     al, r13b
0x140025b79  movups  [rbp+4Fh+var_A8], xmm0
0x140025b7d  neg     al
0x140025b7f  mov     word ptr [rbp+4Fh+var_A8], 2
0x140025b85  movups  [rbp+4Fh+var_98], xmm0
0x140025b89  sbb     ecx, ecx
0x140025b8b  mov     dword ptr [rbp+4Fh+var_98], ebx
0x140025b8e  and     ecx, 0FFFFFFDFh
0x140025b91  mov     word ptr [rbp+4Fh+var_98+4], bx
0x140025b95  add     ecx, 25h ; '%'
0x140025b98  mov     qword ptr [rbp+4Fh+var_A8+8], r12
0x140025b9c  mov     dword ptr [rbp+4Fh+var_A8+4], ecx
0x140025b9f  movups  [rbp+4Fh+var_88], xmm0
0x140025ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x140025baa  lea     rax, WPP_GLOBAL_Control
0x140025bb1  cmp     rcx, rax
0x140025bb4  jz      short loc_140025BE8
0x140025bb6  test    byte ptr [rcx+1Ch], 1
0x140025bba  jz      short loc_140025BE8
0x140025bbc  cmp     byte ptr [rcx+19h], 4
0x140025bc0  jb      short loc_140025BE8
0x140025bc2  mov     rcx, [rcx+10h]
0x140025bc6  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140025bcd  mov     edx, 0DBh
0x140025bd2  mov     r9, r12
0x140025bd5  call    WPP_SF_S
0x140025bda  mov     rcx, cs:WPP_GLOBAL_Control
0x140025be1  lea     rax, WPP_GLOBAL_Control
0x140025be8  test    r13b, r13b
0x140025beb  jz      loc_140025CFA
0x140025bf1  cmp     dword ptr [rdi+150h], 1
0x140025bf8  jnz     loc_140025CD0
0x140025bfe  mov     rcx, [rdi+160h]
0x140025c05  lea     rdx, [rbp+4Fh+var_60]
0x140025c09  mov     rax, [rdi+228h]
0x140025c10  xorps   xmm0, xmm0
0x140025c13  mov     r8d, 10h
0x140025c19  movups  [rbp+4Fh+var_60], xmm0
0x140025c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025c22  test    al, al
0x140025c24  jnz     short loc_140025C6E
0x140025c26  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c2d  lea     rax, WPP_GLOBAL_Control
0x140025c34  cmp     rcx, rax
0x140025c37  jz      short loc_140025C61
0x140025c39  test    byte ptr [rcx+1Ch], 1
0x140025c3d  jz      short loc_140025C61
0x140025c3f  cmp     byte ptr [rcx+19h], 2
0x140025c43  jb      short loc_140025C61
0x140025c45  mov     r9, [rdi+160h]
0x140025c4c  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140025c53  mov     rcx, [rcx+10h]
0x140025c57  mov     edx, 0DCh
0x140025c5c  call    WPP_SF_S
0x140025c61  mov     ebx, 80780046h
0x140025c66  mov     byte ptr [rsi], 1
0x140025c69  jmp     loc_140025AE6
0x140025c6e  test    byte ptr [rbp+4Fh+var_60], 80h
0x140025c72  jz      short loc_140025C9A
0x140025c74  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c7b  lea     rax, WPP_GLOBAL_Control
0x140025c82  cmp     rcx, rax
0x140025c85  jz      short loc_140025CF6
0x140025c87  test    byte ptr [rcx+1Ch], 1
0x140025c8b  jz      short loc_140025CF6
0x140025c8d  cmp     byte ptr [rcx+19h], 4
0x140025c91  jb      short loc_140025CF6
0x140025c93  mov     edx, 0DDh
0x140025c98  jmp     short loc_140025CE6
0x140025c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025ca1  lea     rax, WPP_GLOBAL_Control
0x140025ca8  cmp     rcx, rax
0x140025cab  jz      short loc_140025CFA
0x140025cad  test    byte ptr [rcx+1Ch], 1
0x140025cb1  jz      short loc_140025CFA
0x140025cb3  cmp     byte ptr [rcx+19h], 4
  ... truncated ...
```
