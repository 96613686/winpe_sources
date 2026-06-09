# CBlbBackupAsync::CleanupPreviousBackups(void)

- ea: `0x14001eca4`
- end: `0x14001f47f`
- name: `?CleanupPreviousBackups@CBlbBackupAsync@@AEAAJXZ`
- size: `2011`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000e824`
- `0x140014200`
- `0x140014260`
- `0x14001eca4`
- `0x140038178`
- `0x1400889f0`
- `0x1400f2a28`
- `0x1400f2d74`
- `0x140102128`
- `0x140102560`
- `0x140134cc6`
- `0x140134d20`

## import_xrefs

- `KERNEL32!FindClose` at `0x14001f14d`
- `KERNEL32!FindClose` at `0x14001f415`
- `KERNEL32!FindClose` at `0x14001f14d`
- `KERNEL32!FindClose` at `0x14001f415`
- `KERNEL32!DeleteFileW` at `0x14001eeed`
- `KERNEL32!DeleteFileW` at `0x14001f049`
- `KERNEL32!DeleteFileW` at `0x14001f293`
- `KERNEL32!DeleteFileW` at `0x14001eeed`
- `KERNEL32!DeleteFileW` at `0x14001f049`
- `KERNEL32!DeleteFileW` at `0x14001f293`
- `KERNEL32!GetLastError` at `0x14001ef26`
- `KERNEL32!GetLastError` at `0x14001f082`
- `KERNEL32!GetLastError` at `0x14001f2cc`
- `KERNEL32!GetLastError` at `0x14001ef26`
- `KERNEL32!GetLastError` at `0x14001f082`
- `KERNEL32!GetLastError` at `0x14001f2cc`
- `msvcrt!_wcsnicmp` at `0x14001eea0`
- `msvcrt!_wcsnicmp` at `0x14001eea0`
- `ole32!CoTaskMemFree` at `0x14001ee5d`
- `ole32!CoTaskMemFree` at `0x14001f119`
- `ole32!CoTaskMemFree` at `0x14001f166`
- `ole32!CoTaskMemFree` at `0x14001f202`
- `ole32!CoTaskMemFree` at `0x14001f363`
- `ole32!CoTaskMemFree` at `0x14001f3d3`
- `ole32!CoTaskMemFree` at `0x14001f3e8`
- `ole32!CoTaskMemFree` at `0x14001f3fd`
- `ole32!CoTaskMemFree` at `0x14001f42a`
- `ole32!CoTaskMemFree` at `0x14001ee5d`
- `ole32!CoTaskMemFree` at `0x14001f119`
- `ole32!CoTaskMemFree` at `0x14001f166`
- `ole32!CoTaskMemFree` at `0x14001f202`
- `ole32!CoTaskMemFree` at `0x14001f363`
- `ole32!CoTaskMemFree` at `0x14001f3d3`
- `ole32!CoTaskMemFree` at `0x14001f3e8`
- `ole32!CoTaskMemFree` at `0x14001f3fd`
- `ole32!CoTaskMemFree` at `0x14001f42a`
- `RPCRT4!UuidFromStringW` at `0x14001ef8a`
- `RPCRT4!UuidFromStringW` at `0x14001f261`
- `RPCRT4!UuidFromStringW` at `0x14001ef8a`
- `RPCRT4!UuidFromStringW` at `0x14001f261`

## string_xrefs

- `0x14001efbc`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::CleanupPreviousBackups(CBlbBackupAsync *this)
{
  WCHAR *v1; // rdi
  wchar_t *v2; // rsi
  _QWORD *v3; // r12
  unsigned int v4; // r15d
  int appended; // ebx
  const unsigned __int16 *v7; // rcx
  unsigned __int16 *v8; // r14
  int FirstFile; // eax
  PVOID *v10; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  unsigned int v13; // edx
  unsigned __int64 v14; // rax
  unsigned int v15; // r9d
  unsigned int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  unsigned int i; // ecx
  __int64 v21; // rax
  char LastError; // al
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  int NextFile; // eax
  int v26; // edx
  int v27; // eax
  unsigned __int64 v28; // rax
  __int64 v29; // rax
  char v30; // al
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  LPCWSTR lpFileName; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-31h] BYREF
  HANDLE hFindFile; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v39; // [rsp+58h] [rbp-11h] BYREF
  UUID Uuid; // [rsp+60h] [rbp-9h] BYREF

  hFindFile = (HANDLE)-1LL;
  pv = 0;
  v1 = 0;
  lpFileName = 0;
  v2 = 0;
  String1 = 0;
  v3 = 0;
  *(_QWORD *)&Uuid.Data1 = 0;
  v4 = 0;
  v37 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 605, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  appended = BlbAppendBagFile(*((unsigned __int16 **)this + 59), 0, 0, L".vhdx", (unsigned __int16 **)&pv);
  if ( appended < 0 )
    goto LABEL_109;
  v7 = (const unsigned __int16 *)*((_QWORD *)this + 59);
  v39 = 0;
  appended = StringCchLengthW(v7, 0x7FFFFFFFu, &v39);
  if ( appended < 0 )
    goto LABEL_109;
  if ( *((_BYTE *)this + 391) )
  {
    if ( (int)CBlbApplicationBackupAsync::GetAppBackupVolumes(
                *((CBlbApplicationBackupAsync **)this + 104),
                &v37,
                (struct _GUID **)&Uuid) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 606, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    v4 = v37;
    v3 = *(_QWORD **)&Uuid.Data1;
  }
  v8 = (unsigned __int16 *)pv;
  FirstFile = BlbFindFirstFile((unsigned __int16 *)pv, (LPVOID *)&lpFileName, &hFindFile, 0);
  appended = FirstFile;
  if ( FirstFile < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        607,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (_DWORD)v8,
        FirstFile);
LABEL_19:
      v1 = (WCHAR *)lpFileName;
      goto LABEL_110;
    }
    goto LABEL_108;
  }
  while ( 1 )
  {
    v1 = (WCHAR *)lpFileName;
    if ( !lpFileName )
      break;
    if ( v2 )
    {
      CoTaskMemFree(v2);
      String1 = 0;
    }
    v11 = BlbutilDuplicateString(&v1[v39 + 1], &String1, 0);
    v2 = String1;
    appended = v11;
    if ( v11 < 0 )
      goto LABEL_110;
    if ( !_wcsnicmp(String1, L"Esp", 3u) )
    {
      v12 = *((_DWORD *)this + 92);
      v13 = 0;
      if ( v12 )
      {
        while ( (*(_BYTE *)(368LL * v13 + *((_QWORD *)this + 27) + 84) & 1) == 0 )
        {
          if ( ++v13 >= v12 )
            goto LABEL_28;
        }
      }
      else
      {
LABEL_28:
        if ( v13 == v12
          && !DeleteFileW(v1)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 608, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
      }
      goto LABEL_67;
    }
    v14 = -1;
    do
      ++v14;
    while ( v2[v14] );
    if ( v14 < 0x24 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_67;
      }
      v24 = 611;
      goto LABEL_66;
    }
    v2[36] = 0;
    Uuid = GUID_NULL;
    if ( !UuidFromStringW(v2, &Uuid) )
    {
      if ( !memcmp_0(&Uuid, &GUID_NULL, 0x10u) )
        BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x37E2u, "guidBagVolumeId != GUID_NULL");
      v15 = *((_DWORD *)this + 92);
      v16 = 0;
      if ( v15 )
      {
        v17 = *((_QWORD *)this + 27);
        do
        {
          v18 = 368LL * v16;
          v19 = *(_QWORD *)(v18 + v17 + 68) - *(_QWORD *)&Uuid.Data1;
          if ( !v19 )
            v19 = *(_QWORD *)(v18 + v17 + 76) - *(_QWORD *)Uuid.Data4;
          if ( !v19 )
            break;
          ++v16;
        }
        while ( v16 < v15 );
      }
      for ( i = 0; i < v4; ++i )
      {
        v21 = v3[2 * i] - *(_QWORD *)&Uuid.Data1;
        if ( !v21 )
          v21 = v3[2 * i + 1] - *(_QWORD *)Uuid.Data4;
        if ( !v21 )
          break;
      }
      if ( v16 == v15
        && i == v4
        && !DeleteFileW(v1)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          609,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (_DWORD)v1,
          LastError);
      }
      goto LABEL_67;
    }
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v24 = 610;
LABEL_66:
      WPP_SF_S(v23[2], v24, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v1);
    }
LABEL_67:
    CoTaskMemFree(v1);
    lpFileName = 0;
    appended = BlbFindNextFile(v8, hFindFile, (LPVOID *)&lpFileName, 0);
    if ( appended < 0 )
    {
      v1 = (WCHAR *)lpFileName;
      goto LABEL_110;
    }
  }
  FindClose(hFindFile);
  hFindFile = (HANDLE)-1LL;
  if ( v8 )
  {
    CoTaskMemFree(v8);
    pv = 0;
  }
  appended = BlbAppendWriterMetadataFile(*((unsigned __int16 **)this + 59), 0, 0, 0, (unsigned __int16 **)&pv);
  if ( appended < 0 )
  {
LABEL_109:
    v8 = (unsigned __int16 *)pv;
LABEL_110:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_111;
  }
  v8 = (unsigned __int16 *)pv;
  NextFile = BlbFindFirstFile((unsigned __int16 *)pv, (LPVOID *)&lpFileName, &hFindFile, 0);
  appended = NextFile;
  if ( NextFile >= 0 )
  {
    while ( 1 )
    {
      v1 = (WCHAR *)lpFileName;
      if ( !lpFileName )
        goto LABEL_110;
      if ( v2 )
      {
        CoTaskMemFree(v2);
        String1 = 0;
      }
      v27 = BlbutilDuplicateString(&v1[v39 + 1], &String1, 0);
      v2 = String1;
      appended = v27;
      if ( v27 < 0 )
        goto LABEL_110;
      v28 = -1;
      do
        ++v28;
      while ( String1[v28] );
      if ( v28 < 0x24 )
        break;
      String1[36] = 0;
      Uuid = GUID_NULL;
      if ( !UuidFromStringW(v2, &Uuid) )
      {
        v29 = *(_QWORD *)&Uuid.Data1 - *((_QWORD *)this + 37);
        if ( *(_QWORD *)&Uuid.Data1 == *((_QWORD *)this + 37) )
          v29 = *(_QWORD *)Uuid.Data4 - *((_QWORD *)this + 38);
        if ( v29
          && !DeleteFileW(v1)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v30 = GetLastError();
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            613,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (_DWORD)v1,
            v30);
        }
        goto LABEL_103;
      }
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v32 = 614;
LABEL_102:
        WPP_SF_S(v31[2], v32, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v1);
      }
LABEL_103:
      CoTaskMemFree(v1);
      lpFileName = 0;
      NextFile = BlbFindNextFile(v8, hFindFile, (LPVOID *)&lpFileName, 0);
      appended = NextFile;
      if ( NextFile < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = 616;
          goto LABEL_77;
        }
        goto LABEL_108;
      }
    }
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_103;
    }
    v32 = 615;
    goto LABEL_102;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v26 = 612;
LABEL_77:
    WPP_SF_Sd(
      (unsigned int)v10[2],
      v26,
      (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
      (_DWORD)v8,
      NextFile);
    goto LABEL_19;
  }
LABEL_108:
  v1 = (WCHAR *)lpFileName;
LABEL_111:
  if ( v8 )
  {
    CoTaskMemFree(v8);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 )
  {
    CoTaskMemFree(v1);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 )
  {
    CoTaskMemFree(v2);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hFindFile != (HANDLE)-1LL )
  {
    FindClose(hFindFile);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    CoTaskMemFree(v3);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_(v10[2], 617, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14001eca4  push    rbp
0x14001eca6  push    rbx
0x14001eca7  push    rsi
0x14001eca8  push    rdi
0x14001eca9  push    r12
0x14001ecab  push    r13
0x14001ecad  push    r14
0x14001ecaf  push    r15
0x14001ecb1  lea     rbp, [rsp-1Fh]
0x14001ecb6  sub     rsp, 88h
0x14001ecbd  mov     rax, cs:__security_cookie
0x14001ecc4  xor     rax, rsp
0x14001ecc7  mov     [rbp+57h+var_50], rax
0x14001eccb  xor     r14d, r14d
0x14001ecce  mov     [rbp+57h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x14001ecd6  mov     [rbp+57h+pv], r14
0x14001ecda  mov     edi, r14d
0x14001ecdd  mov     [rbp+57h+lpFileName], r14
0x14001ece1  mov     esi, r14d
0x14001ece4  mov     [rbp+57h+String1], r14
0x14001ece8  mov     r12d, r14d
0x14001eceb  mov     qword ptr [rbp+57h+Uuid.Data1], r14
0x14001ecef  mov     r15d, r14d
0x14001ecf2  mov     [rbp+57h+var_78], r14d
0x14001ecf6  mov     r13, rcx
0x14001ecf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ed00  lea     rax, WPP_GLOBAL_Control
0x14001ed07  cmp     rcx, rax
0x14001ed0a  jz      short loc_14001ED2D
0x14001ed0c  test    byte ptr [rcx+1Ch], 1
0x14001ed10  jz      short loc_14001ED2D
0x14001ed12  cmp     byte ptr [rcx+19h], 4
0x14001ed16  jb      short loc_14001ED2D
0x14001ed18  mov     rcx, [rcx+10h]
0x14001ed1c  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001ed23  mov     edx, 25Dh
0x14001ed28  call    WPP_SF_
0x14001ed2d  mov     rcx, [r13+1D8h]; unsigned __int16 *
0x14001ed34  lea     rax, [rbp+57h+pv]
0x14001ed38  lea     r9, aVhdx; ".vhdx"
0x14001ed3f  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x14001ed44  xor     r8d, r8d; unsigned int
0x14001ed47  xor     edx, edx; Uuid
0x14001ed49  call    ?BlbAppendBagFile@@YAJPEAGPEAU_GUID@@KPEBGPEAPEAG@Z; BlbAppendBagFile(ushort *,_GUID *,ulong,ushort const *,ushort * *)
0x14001ed4e  mov     ebx, eax
0x14001ed50  test    eax, eax
0x14001ed52  js      loc_14001F3B9
0x14001ed58  mov     rcx, [r13+1D8h]; unsigned __int16 *
0x14001ed5f  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x14001ed63  mov     edx, 7FFFFFFFh; unsigned __int64
0x14001ed68  mov     [rbp+57h+var_68], r14
0x14001ed6c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001ed71  mov     ebx, eax
0x14001ed73  test    eax, eax
0x14001ed75  js      loc_14001F3B9
0x14001ed7b  cmp     [r13+187h], r14b
0x14001ed82  jz      short loc_14001EDDB
0x14001ed84  mov     rcx, [r13+340h]; this
0x14001ed8b  lea     r8, [rbp+57h+Uuid]; struct _GUID **
0x14001ed8f  lea     rdx, [rbp+57h+var_78]; unsigned int *
0x14001ed93  call    ?GetAppBackupVolumes@CBlbApplicationBackupAsync@@QEAAJPEAKPEAPEAU_GUID@@@Z; CBlbApplicationBackupAsync::GetAppBackupVolumes(ulong *,_GUID * *)
0x14001ed98  test    eax, eax
0x14001ed9a  jns     short loc_14001EDD3
0x14001ed9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eda3  lea     rdx, WPP_GLOBAL_Control
0x14001edaa  cmp     rcx, rdx
0x14001edad  jz      short loc_14001EDD3
0x14001edaf  test    byte ptr [rcx+1Ch], 1
0x14001edb3  jz      short loc_14001EDD3
0x14001edb5  cmp     byte ptr [rcx+19h], 3
0x14001edb9  jb      short loc_14001EDD3
0x14001edbb  mov     rcx, [rcx+10h]
0x14001edbf  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001edc6  mov     edx, 25Eh
0x14001edcb  mov     r9d, eax
0x14001edce  call    WPP_SF_d
0x14001edd3  mov     r15d, [rbp+57h+var_78]
0x14001edd7  mov     r12, qword ptr [rbp+57h+Uuid.Data1]
0x14001eddb  mov     r14, [rbp+57h+pv]
0x14001eddf  lea     r8, [rbp+57h+hFindFile]; void **
0x14001ede3  mov     rcx, r14; unsigned __int16 *
0x14001ede6  lea     rdx, [rbp+57h+lpFileName]; unsigned __int16 **
0x14001edea  xor     r9d, r9d; struct _WIN32_FIND_DATAW **
0x14001eded  call    ?BlbFindFirstFile@@YAJPEAGPEAPEAGPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindFirstFile(ushort *,ushort * *,void * *,_WIN32_FIND_DATAW * *)
0x14001edf2  mov     ebx, eax
0x14001edf4  test    eax, eax
0x14001edf6  jns     short loc_14001EE48
0x14001edf8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001edff  lea     r13, WPP_GLOBAL_Control
0x14001ee06  cmp     rcx, r13
0x14001ee09  jz      loc_14001F3B3
0x14001ee0f  test    byte ptr [rcx+1Ch], 1
0x14001ee13  jz      loc_14001F3B3
0x14001ee19  cmp     byte ptr [rcx+19h], 2
0x14001ee1d  jb      loc_14001F3B3
0x14001ee23  mov     edx, 25Fh
0x14001ee28  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14001ee2c  mov     rcx, [rcx+10h]
0x14001ee30  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001ee37  mov     r9, r14
0x14001ee3a  call    WPP_SF_Sd
0x14001ee3f  mov     rdi, [rbp+57h+lpFileName]
0x14001ee43  jmp     loc_14001F3C4
0x14001ee48  mov     rdi, [rbp+57h+lpFileName]
0x14001ee4c  test    rdi, rdi
0x14001ee4f  jz      loc_14001F149
0x14001ee55  test    rsi, rsi
0x14001ee58  jz      short loc_14001EE6B
0x14001ee5a  mov     rcx, rsi; pv
0x14001ee5d  call    cs:__imp_CoTaskMemFree
0x14001ee63  mov     [rbp+57h+String1], 0
0x14001ee6b  mov     rax, [rbp+57h+var_68]
0x14001ee6f  lea     rdx, [rbp+57h+String1]; unsigned __int16 **
0x14001ee73  inc     rax
0x14001ee76  xor     r8d, r8d; unsigned __int64
0x14001ee79  lea     rcx, [rdi+rax*2]; unsigned __int16 *
0x14001ee7d  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14001ee82  mov     rsi, [rbp+57h+String1]
0x14001ee86  mov     ebx, eax
0x14001ee88  test    eax, eax
0x14001ee8a  js      loc_14001F3BD
0x14001ee90  mov     r8d, 3; MaxCount
0x14001ee96  lea     rdx, aEsp; "Esp"
0x14001ee9d  mov     rcx, rsi; String1
0x14001eea0  call    cs:__imp__wcsnicmp
0x14001eea6  xor     ebx, ebx
0x14001eea8  test    eax, eax
0x14001eeaa  jnz     loc_14001EF5C
0x14001eeb0  mov     r8d, [r13+170h]
0x14001eeb7  mov     edx, ebx
0x14001eeb9  test    r8d, r8d
0x14001eebc  jz      short loc_14001EEE1
0x14001eebe  mov     r9, [r13+0D8h]
0x14001eec5  mov     eax, edx
0x14001eec7  imul    rcx, rax, 170h
0x14001eece  test    byte ptr [rcx+r9+54h], 1
0x14001eed4  jnz     loc_14001F116
0x14001eeda  inc     edx
0x14001eedc  cmp     edx, r8d
0x14001eedf  jb      short loc_14001EEC5
0x14001eee1  cmp     edx, r8d
0x14001eee4  jnz     loc_14001F116
0x14001eeea  mov     rcx, rdi; lpFileName
0x14001eeed  call    cs:__imp_DeleteFileW
0x14001eef3  test    eax, eax
0x14001eef5  jnz     loc_14001F116
0x14001eefb  mov     rax, cs:WPP_GLOBAL_Control
0x14001ef02  lea     rcx, WPP_GLOBAL_Control
0x14001ef09  cmp     rax, rcx
0x14001ef0c  jz      loc_14001F116
0x14001ef12  test    byte ptr [rax+1Ch], 1
0x14001ef16  jz      loc_14001F116
0x14001ef1c  cmp     byte ptr [rax+19h], 2
0x14001ef20  jb      loc_14001F116
0x14001ef26  call    cs:__imp_GetLastError
0x14001ef2c  test    eax, eax
0x14001ef2e  jle     short loc_14001EF38
0x14001ef30  movzx   eax, ax
0x14001ef33  or      eax, 80070000h
0x14001ef38  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef3f  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001ef46  mov     edx, 260h
0x14001ef4b  mov     r9d, eax
0x14001ef4e  mov     rcx, [rcx+10h]
0x14001ef52  call    WPP_SF_d
0x14001ef57  jmp     loc_14001F116
0x14001ef5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ef60  inc     rax
0x14001ef63  cmp     [rsi+rax*2], bx
0x14001ef67  jnz     short loc_14001EF60
0x14001ef69  cmp     rax, 24h ; '$'
0x14001ef6d  jb      loc_14001F0DF
0x14001ef73  mov     [rsi+48h], bx
0x14001ef77  lea     rdx, [rbp+57h+Uuid]; Uuid
0x14001ef7b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14001ef82  mov     rcx, rsi; StringUuid
0x14001ef85  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x14001ef8a  call    cs:__imp_UuidFromStringW
0x14001ef90  test    eax, eax
0x14001ef92  jnz     loc_14001F0B9
0x14001ef98  lea     r8d, [rax+10h]; Size
0x14001ef9c  lea     rdx, GUID_NULL; Buf2
0x14001efa3  lea     rcx, [rbp+57h+Uuid]; Buf1
0x14001efa7  call    memcmp_0
0x14001efac  test    eax, eax
0x14001efae  jnz     short loc_14001EFC8
0x14001efb0  lea     r8, aGuidbagvolumei; "guidBagVolumeId != GUID_NULL"
0x14001efb7  mov     edx, 37E2h; unsigned int
0x14001efbc  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14001efc3  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14001efc8  mov     r9d, [r13+170h]
0x14001efcf  mov     r8d, ebx
0x14001efd2  test    r9d, r9d
0x14001efd5  jz      short loc_14001F009
0x14001efd7  mov     rdx, [r13+0D8h]
0x14001efde  mov     eax, r8d
0x14001efe1  imul    rcx, rax, 170h
0x14001efe8  mov     rax, [rcx+rdx+44h]
0x14001efed  sub     rax, qword ptr [rbp+57h+Uuid.Data1]
0x14001eff1  jnz     short loc_14001EFFC
0x14001eff3  mov     rax, [rcx+rdx+4Ch]
0x14001eff8  sub     rax, qword ptr [rbp+57h+Uuid.Data4]
0x14001effc  test    rax, rax
0x14001efff  jz      short loc_14001F009
0x14001f001  inc     r8d
0x14001f004  cmp     r8d, r9d
0x14001f007  jb      short loc_14001EFDE
0x14001f009  mov     ecx, ebx
0x14001f00b  test    r15d, r15d
0x14001f00e  jz      short loc_14001F034
0x14001f010  mov     edx, ecx
0x14001f012  add     rdx, rdx
0x14001f015  mov     rax, [r12+rdx*8]
0x14001f019  sub     rax, qword ptr [rbp+57h+Uuid.Data1]
0x14001f01d  jnz     short loc_14001F028
0x14001f01f  mov     rax, [r12+rdx*8+8]
0x14001f024  sub     rax, qword ptr [rbp+57h+Uuid.Data4]
0x14001f028  test    rax, rax
0x14001f02b  jz      short loc_14001F034
0x14001f02d  inc     ecx
0x14001f02f  cmp     ecx, r15d
0x14001f032  jb      short loc_14001F010
0x14001f034  cmp     r8d, r9d
0x14001f037  jnz     loc_14001F116
0x14001f03d  cmp     ecx, r15d
0x14001f040  jnz     loc_14001F116
0x14001f046  mov     rcx, rdi; lpFileName
0x14001f049  call    cs:__imp_DeleteFileW
0x14001f04f  test    eax, eax
0x14001f051  jnz     loc_14001F116
0x14001f057  mov     rax, cs:WPP_GLOBAL_Control
0x14001f05e  lea     rcx, WPP_GLOBAL_Control
0x14001f065  cmp     rax, rcx
0x14001f068  jz      loc_14001F116
0x14001f06e  test    byte ptr [rax+1Ch], 1
0x14001f072  jz      loc_14001F116
0x14001f078  cmp     byte ptr [rax+19h], 2
0x14001f07c  jb      loc_14001F116
0x14001f082  call    cs:__imp_GetLastError
0x14001f088  test    eax, eax
0x14001f08a  jle     short loc_14001F094
0x14001f08c  movzx   eax, ax
0x14001f08f  or      eax, 80070000h
0x14001f094  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f09b  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001f0a2  mov     edx, 261h
0x14001f0a7  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14001f0ab  mov     r9, rdi
0x14001f0ae  mov     rcx, [rcx+10h]
0x14001f0b2  call    WPP_SF_Sd
0x14001f0b7  jmp     short loc_14001F116
0x14001f0b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0c0  lea     rax, WPP_GLOBAL_Control
0x14001f0c7  cmp     rcx, rax
0x14001f0ca  jz      short loc_14001F116
0x14001f0cc  test    byte ptr [rcx+1Ch], 1
0x14001f0d0  jz      short loc_14001F116
0x14001f0d2  cmp     byte ptr [rcx+19h], 3
0x14001f0d6  jb      short loc_14001F116
0x14001f0d8  mov     edx, 262h
0x14001f0dd  jmp     short loc_14001F103
0x14001f0df  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0e6  lea     rax, WPP_GLOBAL_Control
0x14001f0ed  cmp     rcx, rax
0x14001f0f0  jz      short loc_14001F116
0x14001f0f2  test    byte ptr [rcx+1Ch], 1
0x14001f0f6  jz      short loc_14001F116
0x14001f0f8  cmp     byte ptr [rcx+19h], 3
0x14001f0fc  jb      short loc_14001F116
0x14001f0fe  mov     edx, 263h
0x14001f103  mov     rcx, [rcx+10h]
0x14001f107  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001f10e  mov     r9, rdi
0x14001f111  call    WPP_SF_S
0x14001f116  mov     rcx, rdi; pv
0x14001f119  call    cs:__imp_CoTaskMemFree
0x14001f11f  mov     rdx, [rbp+57h+hFindFile]; hFindFile
0x14001f123  lea     r8, [rbp+57h+lpFileName]; unsigned __int16 **
0x14001f127  xor     r9d, r9d; struct _WIN32_FIND_DATAW **
0x14001f12a  mov     [rbp+57h+lpFileName], rbx
0x14001f12e  mov     rcx, r14; unsigned __int16 *
0x14001f131  call    ?BlbFindNextFile@@YAJPEAGPEAXPEAPEAGPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindNextFile(ushort *,void *,ushort * *,_WIN32_FIND_DATAW * *)
0x14001f136  mov     ebx, eax
0x14001f138  test    eax, eax
0x14001f13a  jns     loc_14001EE48
0x14001f140  mov     rdi, [rbp+57h+lpFileName]
0x14001f144  jmp     loc_14001F3BD
0x14001f149  mov     rcx, [rbp+57h+hFindFile]; hFindFile
0x14001f14d  call    cs:__imp_FindClose
0x14001f153  xor     r15d, r15d
0x14001f156  mov     [rbp+57h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x14001f15e  test    r14, r14
0x14001f161  jz      short loc_14001F170
0x14001f163  mov     rcx, r14; pv
0x14001f166  call    cs:__imp_CoTaskMemFree
0x14001f16c  mov     [rbp+57h+pv], r15
0x14001f170  mov     rcx, [r13+1D8h]; unsigned __int16 *
0x14001f177  lea     rax, [rbp+57h+pv]
0x14001f17b  xor     r9d, r9d; unsigned __int8
0x14001f17e  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
  ... truncated ...
```
