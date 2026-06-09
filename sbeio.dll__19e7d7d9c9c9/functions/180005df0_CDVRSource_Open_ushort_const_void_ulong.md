# CDVRSource::Open(ushort const *,void *,ulong)

- ea: `0x180005df0`
- end: `0x1800066d1`
- name: `?Open@CDVRSource@@UEAAJPEBGPEAXK@Z`
- size: `2273`
- prototype: `int(CDVRSource *__hidden this, const unsigned __int16 *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x1800015f0`
- `0x180005060`
- `0x1800050cc`
- `0x180005df0`
- `0x180006f20`
- `0x180006fbc`
- `0x18000774c`
- `0x18002b010`

## import_xrefs

- `KERNEL32!OpenMutexW` at `0x1800062da`
- `KERNEL32!OpenMutexW` at `0x1800062da`
- `KERNEL32!Sleep` at `0x180006081`
- `KERNEL32!Sleep` at `0x1800060f1`
- `KERNEL32!Sleep` at `0x180006081`
- `KERNEL32!Sleep` at `0x1800060f1`
- `KERNEL32!CreateEventW` at `0x180005f58`
- `KERNEL32!CreateEventW` at `0x180005f58`
- `KERNEL32!OpenProcess` at `0x18000634b`
- `KERNEL32!OpenProcess` at `0x18000634b`
- `KERNEL32!OpenFileMappingW` at `0x180006179`
- `KERNEL32!OpenFileMappingW` at `0x180006179`
- `KERNEL32!MapViewOfFile` at `0x18000626a`
- `KERNEL32!MapViewOfFile` at `0x18000626a`
- `KERNEL32!CloseHandle` at `0x180006631`
- `KERNEL32!CloseHandle` at `0x180006676`
- `KERNEL32!CloseHandle` at `0x18002a53d`
- `KERNEL32!CloseHandle` at `0x18002a590`
- `KERNEL32!CloseHandle` at `0x180006631`
- `KERNEL32!CloseHandle` at `0x180006676`
- `KERNEL32!CloseHandle` at `0x18002a53d`
- `KERNEL32!CloseHandle` at `0x18002a590`
- `KERNEL32!GetLastError` at `0x180005f2e`
- `KERNEL32!GetLastError` at `0x180006044`
- `KERNEL32!GetLastError` at `0x180006183`
- `KERNEL32!GetLastError` at `0x1800062e9`
- `KERNEL32!GetLastError` at `0x18000635a`
- `KERNEL32!GetLastError` at `0x18000654f`
- `KERNEL32!GetLastError` at `0x180005f2e`
- `KERNEL32!GetLastError` at `0x180006044`
- `KERNEL32!GetLastError` at `0x180006183`
- `KERNEL32!GetLastError` at `0x1800062e9`
- `KERNEL32!GetLastError` at `0x18000635a`
- `KERNEL32!GetLastError` at `0x18000654f`
- `KERNEL32!GetFileInformationByHandle` at `0x18000609d`
- `KERNEL32!GetFileInformationByHandle` at `0x180006105`
- `KERNEL32!GetFileInformationByHandle` at `0x18000609d`
- `KERNEL32!GetFileInformationByHandle` at `0x180006105`
- `KERNEL32!DuplicateHandle` at `0x180005f21`
- `KERNEL32!DuplicateHandle` at `0x180005f21`
- `KERNEL32!UnmapViewOfFile` at `0x180006668`
- `KERNEL32!UnmapViewOfFile` at `0x18002a57e`
- `KERNEL32!UnmapViewOfFile` at `0x180006668`
- `KERNEL32!UnmapViewOfFile` at `0x18002a57e`
- `KERNEL32!ReleaseMutex` at `0x180006619`
- `KERNEL32!ReleaseMutex` at `0x18002a521`
- `KERNEL32!ReleaseMutex` at `0x180006619`
- `KERNEL32!ReleaseMutex` at `0x18002a521`
- `KERNEL32!CreateFileW` at `0x180006030`
- `KERNEL32!CreateFileW` at `0x18000653f`
- `KERNEL32!CreateFileW` at `0x180006030`
- `KERNEL32!CreateFileW` at `0x18000653f`
- `KERNEL32!LeaveCriticalSection` at `0x1800066bc`
- `KERNEL32!LeaveCriticalSection` at `0x1800066bc`
- `KERNEL32!LeaveCriticalSection` at `0x18002a5da`
- `KERNEL32!GetCurrentProcess` at `0x180005eed`
- `KERNEL32!GetCurrentProcess` at `0x180005ef6`
- `KERNEL32!GetCurrentProcess` at `0x180005eed`
- `KERNEL32!GetCurrentProcess` at `0x180005ef6`
- `KERNEL32!GetFullPathNameW` at `0x180005f77`
- `KERNEL32!GetFullPathNameW` at `0x180005fc7`
- `KERNEL32!GetFullPathNameW` at `0x180005f77`
- `KERNEL32!GetFullPathNameW` at `0x180005fc7`
- `KERNEL32!EnterCriticalSection` at `0x180005e6d`
- `KERNEL32!EnterCriticalSection` at `0x180005e6d`

## pseudocode

```c
__int64 __fastcall CDVRSource::Open(CDVRSource *this, const unsigned __int16 *a2, void *a3, unsigned int a4)
{
  unsigned __int16 *v9; // r15
  char *v10; // r13
  signed int v11; // ebx
  HANDLE CurrentProcess; // rbx
  HANDLE v13; // rax
  bool v14; // zf
  signed int LastError; // eax
  HANDLE EventW; // rax
  DWORD FullPathNameW; // eax
  unsigned __int64 v18; // rbx
  void *v19; // rax
  HANDLE FileW; // rax
  const unsigned __int16 *v21; // r8
  void *v22; // rcx
  __int64 v23; // rcx
  bool v24; // sf
  _DWORD *v25; // rax
  int v26; // r15d
  DWORD v27; // eax
  HANDLE v28; // rax
  signed int v29; // eax
  __int64 v30; // r8
  HANDLE v31; // rax
  int *v32; // r8
  signed int i; // ebx
  bool v34; // zf
  bool v35; // zf
  __int64 v36; // rcx
  int v37; // eax
  unsigned int Data1; // edx
  __int64 v39; // r12
  int v40; // r14d
  __int64 v41; // rax
  int v42; // eax
  unsigned __int64 v43; // rsi
  unsigned __int16 *v44; // r13
  HANDLE v45; // rax
  signed int v46; // eax
  __int64 v47; // rax
  __int64 v48; // rcx
  void *v49; // rcx
  unsigned __int64 v50; // rdx
  DWORD dwDesiredAccess[2]; // [rsp+58h] [rbp-3C8h]
  DWORD dwDesiredAccessa[2]; // [rsp+58h] [rbp-3C8h]
  DWORD dwDesiredAccessb[2]; // [rsp+58h] [rbp-3C8h]
  __int64 bInheritHandle; // [rsp+60h] [rbp-3C0h]
  __int64 bInheritHandlea; // [rsp+60h] [rbp-3C0h]
  unsigned __int16 *v56; // [rsp+80h] [rbp-3A0h]
  WCHAR Buffer[2]; // [rsp+90h] [rbp-390h] BYREF
  struct _GUID v58; // [rsp+94h] [rbp-38Ch] BYREF
  int v59; // [rsp+A4h] [rbp-37Ch]
  CDVRSource *v60; // [rsp+A8h] [rbp-378h]
  LPWSTR FilePart; // [rsp+B0h] [rbp-370h] BYREF
  unsigned __int64 v62; // [rsp+B8h] [rbp-368h] BYREF
  unsigned __int64 v63[2]; // [rsp+C0h] [rbp-360h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+D0h] [rbp-350h] BYREF
  WCHAR Name[56]; // [rsp+108h] [rbp-318h] BYREF
  WCHAR v66[40]; // [rsp+178h] [rbp-2A8h] BYREF
  WCHAR v67[264]; // [rsp+1C8h] [rbp-258h] BYREF

  v60 = this;
  if ( !a2 )
    return 2147942487LL;
  v9 = 0;
  v56 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  memset(&FileInformation, 0, sizeof(FileInformation));
  FilePart = 0;
  Buffer[0] = 0;
  v10 = (char *)this - 8;
  if ( *((_DWORD *)this + 44) != 1
    || (v11 = (*(__int64 (__fastcall **)(CDVRSource *))(*(_QWORD *)this + 32LL))(this), v11 >= 0) )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 120LL))((char *)this - 8);
    if ( a3 )
    {
      CurrentProcess = GetCurrentProcess();
      v13 = GetCurrentProcess();
      v14 = !DuplicateHandle(v13, a3, CurrentProcess, (LPHANDLE)this + 14, 0, 0, 2u);
    }
    else
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 14) = EventW;
      v14 = EventW == 0;
    }
    if ( v14 )
      goto LABEL_8;
    FullPathNameW = GetFullPathNameW(a2, 0, Buffer, 0);
    if ( !FullPathNameW )
      goto LABEL_8;
    v18 = FullPathNameW + 1;
    v19 = operator new[](saturated_mul(v18, 2u));
    *((_QWORD *)this + 6) = v19;
    if ( !v19 )
    {
      v11 = -2147024882;
LABEL_113:
      v9 = v56;
      goto LABEL_114;
    }
    if ( GetFullPathNameW(a2, 0x104u, v67, &FilePart) )
    {
      v11 = StringCchCopyW(*((unsigned __int16 **)this + 6), v18, v67);
      if ( v11 < 0 )
        goto LABEL_113;
      *FilePart = 0;
      do
      {
        FileW = CreateFileW(*((LPCWSTR *)this + 6), 0x80000000, 7u, 0, 3u, 0x8000000u, 0);
        *((_QWORD *)this + 9) = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          *((_QWORD *)this + 9) = 0;
          LastError = GetLastError();
          v11 = LastError;
          if ( !a4 || LastError != 2 )
            goto LABEL_9;
          if ( a4 >= 0x64 )
          {
            if ( a4 != -1 )
              a4 -= 100;
          }
          else
          {
            a4 = 0;
          }
          Sleep(0x64u);
        }
      }
      while ( !*((_QWORD *)this + 9) );
      while ( 1 )
      {
        if ( !GetFileInformationByHandle(*((HANDLE *)this + 9), &FileInformation) )
          goto LABEL_8;
        if ( FileInformation.nFileSizeHigh || FileInformation.nFileSizeLow )
          break;
        if ( !a4 )
        {
          v11 = -1072889809;
          goto LABEL_113;
        }
        if ( a4 >= 0x64 )
        {
          if ( a4 != -1 )
            a4 -= 100;
        }
        else
        {
          a4 = 0;
        }
        Sleep(0x64u);
      }
      if ( !GetFileInformationByHandle(*((HANDLE *)this + 9), &FileInformation) )
        goto LABEL_8;
      v21 = L"Global\\MSDVRMM_%u_%u_%u";
      if ( !*((_DWORD *)this + 43) )
        v21 = L"MSDVRMM_%u_%u_%u";
      LODWORD(bInheritHandle) = FileInformation.nFileIndexLow;
      dwDesiredAccess[0] = FileInformation.nFileIndexHigh;
      v11 = StringCchPrintfW(
              Name,
              0x32u,
              v21,
              FileInformation.dwVolumeSerialNumber,
              *(_QWORD *)dwDesiredAccess,
              bInheritHandle);
      if ( v11 < 0 )
        goto LABEL_113;
      *((_QWORD *)this + 10) = OpenFileMappingW(6u, 0, Name);
      LastError = GetLastError();
      v11 = LastError;
      if ( *((_QWORD *)this + 10) || LastError == 2 )
      {
        LODWORD(bInheritHandlea) = FileInformation.nFileIndexLow;
        dwDesiredAccessa[0] = FileInformation.nFileIndexHigh;
        v11 = StringCchPrintfW(
                Name,
                0x32u,
                L"MSDVRMM_%u_%u_%u",
                FileInformation.dwVolumeSerialNumber,
                *(_QWORD *)dwDesiredAccessa,
                bInheritHandlea);
        if ( v11 < 0 )
          goto LABEL_113;
        v22 = (void *)*((_QWORD *)this + 10);
        if ( !v22 )
        {
          *((_DWORD *)this + 42) = 0;
          *((_QWORD *)this + 3) = 0;
          *((_QWORD *)this + 4) = FileInformation.nFileSizeLow + ((unsigned __int64)FileInformation.nFileSizeHigh << 32);
          v23 = *((_QWORD *)this + 17);
          if ( !v23 )
          {
LABEL_112:
            *((_QWORD *)this + 2) = 0;
            *((_DWORD *)this + 44) = 1;
            v11 = 0;
            goto LABEL_113;
          }
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, int))(*(_QWORD *)v23 + 24LL))(
                  v23,
                  0,
                  *((unsigned int *)this + 43),
                  *((_QWORD *)this + 6),
                  5,
                  3);
          v24 = v11 < 0;
LABEL_111:
          if ( v24 )
            goto LABEL_113;
          goto LABEL_112;
        }
        *((_DWORD *)this + 42) = 1;
        *((_QWORD *)this + 4) = -1;
        v25 = MapViewOfFile(v22, 6u, 0, 0, 0);
        *((_QWORD *)this + 7) = v25;
        if ( !v25 )
          goto LABEL_8;
        v26 = 0;
        *(_DWORD *)&v58.Data4[4] = 0;
        *(_DWORD *)v58.Data4 = 0;
        v27 = v25[96];
        if ( !v27 )
          goto LABEL_50;
        dwDesiredAccessb[0] = v27;
        StringCchPrintfW(v66, 0x28u, L"%s%u", L"Global\\_MS_TSDVRASF_MUTEX_", *(_QWORD *)dwDesiredAccessb);
        v28 = OpenMutexW(0x100000u, 0, v66);
        *((_QWORD *)this + 12) = v28;
        if ( !v28 )
        {
          v29 = GetLastError();
          v11 = v29;
          if ( v29 > 0 )
            v11 = (unsigned __int16)v29 | 0x80070000;
          goto LABEL_76;
        }
        v11 = (*(__int64 (__fastcall **)(char *, unsigned __int8 *))(*(_QWORD *)v10 + 128LL))(
                (char *)this - 8,
                v58.Data4);
        if ( v11 >= 0 )
        {
          v30 = *((_QWORD *)this + 7);
          if ( !*(_DWORD *)(v30 + 384) )
          {
LABEL_50:
            v11 = 0;
            goto LABEL_76;
          }
          v26 = 1;
          *(_DWORD *)&v58.Data4[4] = 1;
          v31 = OpenProcess(0x100000u, 0, *(_DWORD *)(v30 + 404));
          *((_QWORD *)this + 15) = v31;
          if ( !v31 )
            GetLastError();
          for ( i = 0; ; ++i )
          {
            *(_DWORD *)&v58.Data2 = i;
            v34 = i == 8;
            if ( i >= 8 )
              break;
            if ( !*(_DWORD *)(*((_QWORD *)this + 7) + 40LL * i + 72) )
            {
              v34 = i == 8;
              break;
            }
          }
          if ( !v34 )
            goto LABEL_74;
          for ( i = 0; ; ++i )
          {
            *(_DWORD *)&v58.Data2 = i;
            v35 = i == 8;
            if ( i >= 8 )
              break;
            v36 = *((_QWORD *)this + 7);
            v58.Data1 = 0;
            v37 = DVRSourceSink::ReaderEventExists((DVRSourceSink *)(v36 + 80 + 40LL * i), &v58, v32);
            Data1 = v58.Data1;
            if ( v37 < 0 )
              Data1 = 0;
            v58.Data1 = Data1;
            if ( !Data1 )
            {
              *(_DWORD *)(*((_QWORD *)this + 7) + 40LL * i + 76) = 1;
              *(_DWORD *)(*((_QWORD *)this + 7) + 40LL * i + 72) = 0;
              v35 = i == 8;
              break;
            }
          }
          if ( v35 )
          {
            v11 = -2147023446;
          }
          else
          {
LABEL_74:
            v11 = CDVRSource::RegisterReader((CDVRSource *)((char *)this - 8), i);
            if ( v11 >= 0 )
            {
              v39 = *((_QWORD *)this + 7);
              v11 = 0;
LABEL_77:
              v40 = 0;
              v59 = 0;
              if ( v11 < 0 )
                goto LABEL_99;
              v41 = *((_QWORD *)this + 7);
              if ( *(_DWORD *)(v41 + 412) || !*(_DWORD *)(v41 + 388) )
                goto LABEL_97;
              v62 = 0;
              v63[0] = 0;
              v42 = StringCchLengthW(v67, 0x104u, &v62);
              if ( v42 < 0 || (v42 = StringCchLengthW(Name, 0x32u, v63), v42 < 0) )
              {
                v11 = v42;
                goto LABEL_99;
              }
              v43 = (unsigned int)(v62 + 5 + LODWORD(v63[0]));
              v44 = (unsigned __int16 *)operator new[](saturated_mul(v43, 2u));
              v56 = v44;
              v63[1] = (unsigned __int64)v44;
              if ( !v44 )
              {
                v11 = -2147024882;
                goto LABEL_99;
              }
              StringCchPrintfW(v44, v43, L"%ls%ls.tmp", v67, Name);
              v45 = CreateFileW(v44, 0x80010000, 7u, 0, 3u, 0x10000000u, 0);
              *((_QWORD *)this + 11) = v45;
              if ( v45 != (HANDLE)-1LL )
              {
LABEL_97:
                v47 = *((_QWORD *)this + 7);
                if ( *(_DWORD *)(v47 + 388) )
                  *((_QWORD *)this + 3) = *(_QWORD *)(v47 + 32);
                goto LABEL_99;
              }
              v46 = GetLastError();
              v11 = v46;
              if ( v46 != 2 && v46 != 303 )
              {
                if ( v46 != 5 )
                {
LABEL_89:
                  if ( v46 > 0 )
                    v11 = (unsigned __int16)v46 | 0x80070000;
                  goto LABEL_91;
                }
                if ( *(_DWORD *)(*((_QWORD *)this + 7) + 408LL) )
                {
                  v11 = -2147024891;
LABEL_91:
                  *((_QWORD *)this + 11) = 0;
                  goto LABEL_99;
                }
              }
              if ( !v26 )
              {
                v40 = 1;
                v59 = 1;
                v11 = 0;
                *((_QWORD *)this + 11) = 0;
LABEL_99:
                if ( v11 >= 0 )
                {
                  v48 = *((_QWORD *)this + 17);
                  if ( v48 )
                    v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, int))(*(_QWORD *)v48 + 24LL))(
                            v48,
                            v39,
                            *((unsigned int *)this + 43),
                            *((_QWORD *)this + 6),
                            7,
                            3);
                }
                if ( *(_DWORD *)v58.Data4 )
                  ReleaseMutex(*((HANDLE *)this + 12));
                if ( v11 >= 0 )
                {
                  if ( !v26 )
                  {
                    v49 = (void *)*((_QWORD *)this + 12);
                    if ( v49 )
                    {
                      CloseHandle(v49);
                      *((_QWORD *)this + 12) = 0;
                    }
                  }
                  if ( v40 )
                  {
                    *((_DWORD *)this + 42) = 0;
                    *((_QWORD *)this + 3) = 0;
                    *((_QWORD *)this + 4) = FileInformation.nFileSizeLow
                                          + ((unsigned __int64)FileInformation.nFileSizeHigh << 32);
                    UnmapViewOfFile(*((LPCVOID *)this + 7));
                    *((_QWORD *)this + 7) = 0;
                    CloseHandle(*((HANDLE *)this + 10));
                    *((_QWORD *)this + 10) = 0;
                  }
                }
                v24 = v11 < 0;
                goto LABEL_111;
              }
              goto LABEL_89;
            }
          }
        }
LABEL_76:
        v39 = 0;
        goto LABEL_77;
      }
    }
    else
    {
LABEL_8:
      LastError = GetLastError();
      v11 = LastError;
    }
LABEL_9:
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_113;
  }
LABEL_114:
  if ( v11 < 0 )
    (*(void (__fastcall **)(CDVRSource *))(*(_QWORD *)this + 32LL))(this);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  operator delete(v9, v50);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005df0  push    rbx
0x180005df2  push    rsi
0x180005df3  push    rdi
0x180005df4  push    r12
0x180005df6  push    r13
0x180005df8  push    r14
0x180005dfa  push    r15
0x180005dfc  sub     rsp, 3B0h
0x180005e03  mov     rax, cs:__security_cookie
0x180005e0a  xor     rax, rsp
0x180005e0d  mov     [rsp+3E8h+var_48], rax
0x180005e15  mov     esi, r9d
0x180005e18  mov     r12, r8
0x180005e1b  mov     r14, rdx
0x180005e1e  mov     rdi, rcx
0x180005e21  mov     [rsp+3E8h+var_378], rcx
0x180005e26  test    rdx, rdx
0x180005e29  jnz     short loc_180005E53
0x180005e2b  mov     eax, 80070057h
0x180005e30  mov     rcx, [rsp+3E8h+var_48]
0x180005e38  xor     rcx, rsp; StackCookie
0x180005e3b  call    __security_check_cookie
0x180005e40  add     rsp, 3B0h
0x180005e47  pop     r15
0x180005e49  pop     r14
0x180005e4b  pop     r13
0x180005e4d  pop     r12
0x180005e4f  pop     rdi
0x180005e50  pop     rsi
0x180005e51  pop     rbx
0x180005e52  retn
0x180005e53  mov     [rsp+3E8h+var_3A8], 80004005h
0x180005e5b  xor     r15d, r15d
0x180005e5e  mov     [rsp+3E8h+var_3A0], r15
0x180005e63  lea     rax, [rcx+0B8h]
0x180005e6a  mov     rcx, rax; lpCriticalSection
0x180005e6d  call    cs:__imp_EnterCriticalSection
0x180005e73  nop
0x180005e74  xorps   xmm0, xmm0
0x180005e77  xor     eax, eax
0x180005e79  movups  xmmword ptr [rsp+3E8h+FileInformation.dwFileAttributes], xmm0
0x180005e81  movups  xmmword ptr [rsp+3E8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180005e89  movups  xmmword ptr [rsp+3E8h+FileInformation.nFileSizeHigh], xmm0
0x180005e91  mov     [rsp+3E8h+FileInformation.nFileIndexLow], eax
0x180005e98  mov     [rsp+3E8h+FilePart], rax
0x180005e9d  mov     [rsp+3E8h+Buffer], ax
0x180005ea2  mov     [rsp+3E8h+var_398], rax
0x180005ea7  mov     [rsp+3E8h+var_398], rax
0x180005eac  lea     r13, [rdi-8]
0x180005eb0  cmp     dword ptr [r13+0B8h], 1
0x180005eb8  jnz     short loc_180005ED8
0x180005eba  mov     rax, [rdi]
0x180005ebd  mov     rcx, rdi
0x180005ec0  mov     rax, [rax+20h]
0x180005ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec9  mov     ebx, eax
0x180005ecb  test    eax, eax
0x180005ecd  jns     short loc_180005ED8
0x180005ecf  mov     [rsp+3E8h+var_3A8], eax
0x180005ed3  jmp     loc_1800066A2
0x180005ed8  mov     rax, [r13+0]
0x180005edc  mov     rcx, r13
0x180005edf  mov     rax, [rax+78h]
0x180005ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee8  test    r12, r12
0x180005eeb  jz      short loc_180005F4C
0x180005eed  call    cs:__imp_GetCurrentProcess
0x180005ef3  mov     rbx, rax
0x180005ef6  call    cs:__imp_GetCurrentProcess
0x180005efc  mov     [rsp+3E8h+dwOptions], 2; dwOptions
0x180005f04  mov     dword ptr [rsp+3E8h+bInheritHandle], 0; bInheritHandle
0x180005f0c  mov     [rsp+3E8h+dwDesiredAccess], 0; dwDesiredAccess
0x180005f14  lea     r9, [rdi+70h]; lpTargetHandle
0x180005f18  mov     r8, rbx; hTargetProcessHandle
0x180005f1b  mov     rdx, r12; hSourceHandle
0x180005f1e  mov     rcx, rax; hSourceProcessHandle
0x180005f21  call    cs:__imp_DuplicateHandle
0x180005f27  xor     r12d, r12d
0x180005f2a  test    eax, eax
0x180005f2c  jnz     short loc_180005F6A
0x180005f2e  call    cs:__imp_GetLastError
0x180005f34  mov     ebx, eax
0x180005f36  test    eax, eax
0x180005f38  jle     loc_180006699
0x180005f3e  movzx   ebx, ax
0x180005f41  or      ebx, 80070000h
0x180005f47  jmp     loc_180006699
0x180005f4c  xor     r9d, r9d; lpName
0x180005f4f  xor     r8d, r8d; bInitialState
0x180005f52  lea     edx, [r9+1]; bManualReset
0x180005f56  xor     ecx, ecx; lpEventAttributes
0x180005f58  call    cs:__imp_CreateEventW
0x180005f5e  mov     [rdi+70h], rax
0x180005f62  xor     r12d, r12d
0x180005f65  test    rax, rax
0x180005f68  jmp     short loc_180005F2C
0x180005f6a  xor     r9d, r9d; lpFilePart
0x180005f6d  lea     r8, [rsp+3E8h+Buffer]; lpBuffer
0x180005f72  xor     edx, edx; nBufferLength
0x180005f74  mov     rcx, r14; lpFileName
0x180005f77  call    cs:__imp_GetFullPathNameW
0x180005f7d  test    eax, eax
0x180005f7f  jz      short loc_180005F2E
0x180005f81  lea     ebx, [rax+1]
0x180005f84  mov     eax, 2
0x180005f89  mul     rbx
0x180005f8c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005f93  cmovb   rax, rcx
0x180005f97  mov     rcx, rax; unsigned __int64
0x180005f9a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005f9f  mov     [rdi+30h], rax
0x180005fa3  test    rax, rax
0x180005fa6  jnz     short loc_180005FB2
0x180005fa8  mov     ebx, 8007000Eh
0x180005fad  jmp     loc_180006699
0x180005fb2  lea     r9, [rsp+3E8h+FilePart]; lpFilePart
0x180005fb7  lea     r8, [rsp+3E8h+var_258]; lpBuffer
0x180005fbf  mov     edx, 104h; nBufferLength
0x180005fc4  mov     rcx, r14; lpFileName
0x180005fc7  call    cs:__imp_GetFullPathNameW
0x180005fcd  test    eax, eax
0x180005fcf  jz      loc_180005F2E
0x180005fd5  lea     r8, [rsp+3E8h+var_258]; unsigned __int16 *
0x180005fdd  mov     rdx, rbx; unsigned __int64
0x180005fe0  mov     rcx, [rdi+30h]; unsigned __int16 *
0x180005fe4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005fe9  mov     ebx, eax
0x180005feb  test    eax, eax
0x180005fed  jns     short loc_180005FF8
0x180005fef  mov     [rsp+3E8h+var_3A8], eax
0x180005ff3  jmp     loc_18000669D
0x180005ff8  mov     rax, [rsp+3E8h+FilePart]
0x180005ffd  mov     [rax], r12w
0x180006001  mov     r14d, 64h ; 'd'
0x180006007  or      r15d, 0FFFFFFFFh
0x18000600b  mov     qword ptr [rsp+3E8h+dwOptions], r12; hTemplateFile
0x180006010  mov     dword ptr [rsp+3E8h+bInheritHandle], 8000000h; dwFlagsAndAttributes
0x180006018  mov     [rsp+3E8h+dwDesiredAccess], 3; dwCreationDisposition
0x180006020  xor     r9d, r9d; lpSecurityAttributes
0x180006023  mov     edx, 80000000h; dwDesiredAccess
0x180006028  lea     r8d, [r9+7]; dwShareMode
0x18000602c  mov     rcx, [rdi+30h]; lpFileName
0x180006030  call    cs:__imp_CreateFileW
0x180006036  mov     [rdi+48h], rax
0x18000603a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000603e  jnz     short loc_180006087
0x180006040  mov     [rdi+48h], r12
0x180006044  call    cs:__imp_GetLastError
0x18000604a  mov     ebx, eax
0x18000604c  test    esi, esi
0x18000604e  jz      loc_180005F36
0x180006054  cmp     eax, 2
0x180006057  jnz     loc_180005F36
0x18000605d  cmp     esi, r14d
0x180006060  jnb     short loc_18000606F
0x180006062  mov     esi, r12d
0x180006065  mov     [rsp+3E8h+arg_18], r12d
0x18000606d  jmp     short loc_18000607E
0x18000606f  cmp     esi, r15d
0x180006072  jz      short loc_18000607E
0x180006074  add     esi, 0FFFFFF9Ch
0x180006077  mov     [rsp+3E8h+arg_18], esi
0x18000607e  mov     ecx, r14d; dwMilliseconds
0x180006081  call    cs:__imp_Sleep
0x180006087  cmp     [rdi+48h], r12
0x18000608b  jz      loc_18000600B
0x180006091  lea     rdx, [rsp+3E8h+FileInformation]; lpFileInformation
0x180006099  mov     rcx, [rdi+48h]; hFile
0x18000609d  call    cs:__imp_GetFileInformationByHandle
0x1800060a3  test    eax, eax
0x1800060a5  jz      loc_180005F2E
0x1800060ab  cmp     [rsp+3E8h+FileInformation.nFileSizeHigh], r12d
0x1800060b3  ja      short loc_1800060F9
0x1800060b5  cmp     [rsp+3E8h+FileInformation.nFileSizeLow], r12d
0x1800060bd  ja      short loc_1800060F9
0x1800060bf  test    esi, esi
0x1800060c1  jnz     short loc_1800060CD
0x1800060c3  mov     ebx, 0C00D002Fh
0x1800060c8  jmp     loc_180006699
0x1800060cd  cmp     esi, r14d
0x1800060d0  jnb     short loc_1800060DF
0x1800060d2  mov     esi, r12d
0x1800060d5  mov     [rsp+3E8h+arg_18], r12d
0x1800060dd  jmp     short loc_1800060EE
0x1800060df  cmp     esi, r15d
0x1800060e2  jz      short loc_1800060EE
0x1800060e4  add     esi, 0FFFFFF9Ch
0x1800060e7  mov     [rsp+3E8h+arg_18], esi
0x1800060ee  mov     ecx, r14d; dwMilliseconds
0x1800060f1  call    cs:__imp_Sleep
0x1800060f7  jmp     short loc_180006091
0x1800060f9  lea     rdx, [rsp+3E8h+FileInformation]; lpFileInformation
0x180006101  mov     rcx, [rdi+48h]; hFile
0x180006105  call    cs:__imp_GetFileInformationByHandle
0x18000610b  test    eax, eax
0x18000610d  jz      loc_180005F2E
0x180006113  lea     r14, aMsdvrmmUUU; "MSDVRMM_%u_%u_%u"
0x18000611a  lea     r8, aGlobalMsdvrmmU; "Global\\MSDVRMM_%u_%u_%u"
0x180006121  cmp     [rdi+0ACh], r12d
0x180006128  cmovz   r8, r14; unsigned __int16 *
0x18000612c  mov     eax, [rsp+3E8h+FileInformation.nFileIndexLow]
0x180006133  mov     dword ptr [rsp+3E8h+bInheritHandle], eax
0x180006137  mov     eax, [rsp+3E8h+FileInformation.nFileIndexHigh]
0x18000613e  mov     [rsp+3E8h+dwDesiredAccess], eax
0x180006142  mov     r9d, [rsp+3E8h+FileInformation.dwVolumeSerialNumber]
0x18000614a  mov     r15d, 32h ; '2'
0x180006150  mov     edx, r15d; unsigned __int64
0x180006153  lea     rcx, [rsp+3E8h+Name]; unsigned __int16 *
0x18000615b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006160  mov     ebx, eax
0x180006162  test    eax, eax
0x180006164  js      loc_180005FEF
0x18000616a  lea     r8, [rsp+3E8h+Name]; lpName
0x180006172  xor     edx, edx; bInheritHandle
0x180006174  lea     esi, [rdx+6]
0x180006177  mov     ecx, esi; dwDesiredAccess
0x180006179  call    cs:__imp_OpenFileMappingW
0x18000617f  mov     [rdi+50h], rax
0x180006183  call    cs:__imp_GetLastError
0x180006189  mov     ebx, eax
0x18000618b  cmp     [rdi+50h], r12
0x18000618f  jnz     short loc_18000619A
0x180006191  cmp     eax, 2
0x180006194  jnz     loc_180005F36
0x18000619a  mov     eax, [rsp+3E8h+FileInformation.nFileIndexLow]
0x1800061a1  mov     dword ptr [rsp+3E8h+bInheritHandle], eax
0x1800061a5  mov     eax, [rsp+3E8h+FileInformation.nFileIndexHigh]
0x1800061ac  mov     [rsp+3E8h+dwDesiredAccess], eax
0x1800061b0  mov     r9d, [rsp+3E8h+FileInformation.dwVolumeSerialNumber]
0x1800061b8  mov     r8, r14; unsigned __int16 *
0x1800061bb  mov     rdx, r15; unsigned __int64
0x1800061be  lea     rcx, [rsp+3E8h+Name]; unsigned __int16 *
0x1800061c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800061cb  mov     ebx, eax
0x1800061cd  test    eax, eax
0x1800061cf  js      loc_180005FEF
0x1800061d5  mov     rcx, [rdi+50h]; hFileMappingObject
0x1800061d9  test    rcx, rcx
0x1800061dc  jnz     short loc_180006248
0x1800061de  mov     [rdi+0A8h], r12d
0x1800061e5  mov     [rdi+18h], r12
0x1800061e9  mov     ecx, [rsp+3E8h+FileInformation.nFileSizeHigh]
0x1800061f0  shl     rcx, 20h
0x1800061f4  mov     eax, [rsp+3E8h+FileInformation.nFileSizeLow]
0x1800061fb  add     rcx, rax
0x1800061fe  mov     [rdi+20h], rcx
0x180006202  mov     rcx, [rdi+88h]
0x180006209  test    rcx, rcx
0x18000620c  jz      loc_180006688
0x180006212  mov     rax, [rcx]
0x180006215  mov     dword ptr [rsp+3E8h+bInheritHandle], 3
0x18000621d  mov     [rsp+3E8h+dwDesiredAccess], 5
0x180006225  mov     r9, [rdi+30h]
0x180006229  mov     r8d, [rdi+0ACh]
0x180006230  xor     edx, edx
0x180006232  mov     rax, [rax+18h]
0x180006236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000623b  mov     ebx, eax
0x18000623d  mov     [rsp+3E8h+var_3A8], eax
0x180006241  test    eax, eax
0x180006243  jmp     loc_180006686
0x180006248  mov     r14d, 1
0x18000624e  mov     [rdi+0A8h], r14d
0x180006255  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x18000625d  mov     qword ptr [rsp+3E8h+dwDesiredAccess], r12; dwNumberOfBytesToMap
0x180006262  xor     r9d, r9d; dwFileOffsetLow
0x180006265  xor     r8d, r8d; dwFileOffsetHigh
0x180006268  mov     edx, esi; dwDesiredAccess
0x18000626a  call    cs:__imp_MapViewOfFile
0x180006270  mov     [rdi+38h], rax
0x180006274  test    rax, rax
0x180006277  jz      loc_180005F2E
0x18000627d  mov     [rsp+3E8h+var_3A4], r12d
0x180006282  mov     r15d, r12d
0x180006285  mov     dword ptr [rsp+3E8h+var_38C.Data4+4], r12d
0x18000628a  mov     dword ptr [rsp+3E8h+var_38C.Data4], r12d
0x18000628f  mov     eax, [rax+180h]
0x180006295  test    eax, eax
0x180006297  jnz     short loc_1800062A5
0x180006299  mov     ebx, r12d
0x18000629c  mov     [rsp+3E8h+var_3A4], ebx
0x1800062a0  jmp     loc_180006413
0x1800062a5  mov     [rsp+3E8h+dwDesiredAccess], eax
0x1800062a9  lea     r9, aGlobalMsTsdvra; "Global\\_MS_TSDVRASF_MUTEX_"
0x1800062b0  lea     r8, aSU; "%s%u"
0x1800062b7  mov     edx, 28h ; '('; unsigned __int64
0x1800062bc  lea     rcx, [rsp+3E8h+var_2A8]; unsigned __int16 *
0x1800062c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800062c9  lea     r8, [rsp+3E8h+var_2A8]; lpName
0x1800062d1  xor     edx, edx; bInheritHandle
0x1800062d3  mov     esi, 100000h
0x1800062d8  mov     ecx, esi; dwDesiredAccess
0x1800062da  call    cs:__imp_OpenMutexW
0x1800062e0  mov     [rdi+60h], rax
0x1800062e4  test    rax, rax
0x1800062e7  jnz     short loc_180006300
0x1800062e9  call    cs:__imp_GetLastError
0x1800062ef  mov     ebx, eax
0x1800062f1  test    eax, eax
0x1800062f3  jle     short loc_18000629C
  ... truncated ...
```
