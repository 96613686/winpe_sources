# CUwfManagement::CommitFile(ushort const *,ushort const *)

- ea: `0x180014d80`
- end: `0x18001519e`
- name: `?CommitFile@CUwfManagement@@QEAAJPEBG0@Z`
- size: `1054`
- prototype: `__int64 __fastcall(CUwfManagement *this, wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180017fa0`

## callees

- `0x1800054d0`
- `0x180008cf0`
- `0x18000b940`
- `0x180011e40`
- `0x180014d80`
- `0x180016468`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001512a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001512a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015148`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001506e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180015120`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001506e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180015120`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015013`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015013`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014e9d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014f66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014e9d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014f66`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180014e23`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180014e23`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x180014e3e`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x180014e3e`

## pseudocode

```c
__int64 __fastcall CUwfManagement::CommitFile(CUwfManagement *this, wchar_t *a2, wchar_t *a3)
{
  signed int IsFileExcluded; // ebx
  HKEY v7; // rcx
  LSTATUS v8; // eax
  int StaticVolumeConfiguration; // eax
  HKEY v10; // rcx
  LSTATUS v11; // eax
  bool v12; // dl
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rdx
  char *v18; // rax
  char *v19; // rcx
  signed int v20; // eax
  bool v22; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  struct CUwfStaticVolumeConfiguration *v27; // [rsp+58h] [rbp-A8h] BYREF
  __int128 OutBuffer; // [rsp+60h] [rbp-A0h] BYREF
  int InBuffer; // [rsp+70h] [rbp-90h] BYREF
  char v30; // [rsp+74h] [rbp-8Ch] BYREF
  WCHAR FileName[56]; // [rsp+880h] [rbp+780h] BYREF
  WCHAR pszPath[264]; // [rsp+8F0h] [rbp+7F0h] BYREF

  memset_0(FileName, 0, 0x64u);
  BytesReturned = 0;
  OutBuffer = 0;
  memset_0(&InBuffer, 0, 0x804u);
  v27 = 0;
  v22 = 0;
  IsFileExcluded = StringCchPrintfW(pszPath, 0x104u, L"%ws%ws", a2, a3);
  if ( IsFileExcluded < 0 )
    return (unsigned int)IsFileExcluded;
  if ( !PathFileExistsW(pszPath) )
    return (unsigned int)-2147024894;
  if ( PathIsDirectoryW(pszPath) || !CanFileBeCommitted(a2, a3) )
    return (unsigned int)-2147024809;
  v7 = (HKEY)*((_QWORD *)this + 17);
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  v8 = RegQueryValueExW(v7, L"UWFEnabled", 0, &Type, Data, &cbData);
  IsFileExcluded = v8;
  if ( !v8 )
  {
    if ( Type != 4 )
      return (unsigned int)-2147023267;
    if ( cbData != 4 )
      return (unsigned int)-2147024883;
LABEL_16:
    if ( !*(_DWORD *)Data )
      return 0;
    CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration((CUwfManagement *)((char *)this + 120));
    StaticVolumeConfiguration = CUwfStaticConfiguration::get_StaticVolumeConfiguration(
                                  (CUwfManagement *)((char *)this + 120),
                                  a2,
                                  &v27);
    IsFileExcluded = StaticVolumeConfiguration;
    if ( StaticVolumeConfiguration == -2147024894 )
      goto LABEL_19;
    if ( StaticVolumeConfiguration >= 0 )
    {
      Type = 0;
      *(_DWORD *)Data = 0;
      v10 = (HKEY)*((_QWORD *)v27 + 2);
      cbData = 4;
      v11 = RegQueryValueExW(v10, L"VolumeEnabled", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData);
      IsFileExcluded = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          IsFileExcluded = (unsigned __int16)v11 | 0x80070000;
        if ( IsFileExcluded < 0 )
          goto LABEL_49;
      }
      else
      {
        if ( *(_DWORD *)Data != 4 )
        {
          IsFileExcluded = -2147023267;
          goto LABEL_49;
        }
        if ( cbData != 4 )
        {
          IsFileExcluded = -2147024883;
          goto LABEL_49;
        }
      }
      if ( !Type )
      {
LABEL_19:
        IsFileExcluded = 0;
        goto LABEL_49;
      }
      IsFileExcluded = CUwfManagement::IsFileExcluded(this, v12, a2, 0, a3, &v22);
      if ( IsFileExcluded >= 0 )
      {
        if ( !v22 )
        {
          IsFileExcluded = StringCchPrintfW(FileName, 0x32u, L"\\\\?\\%s", a2);
          if ( IsFileExcluded >= 0 )
          {
            FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
            if ( FileW != (HANDLE)-1LL )
              goto LABEL_36;
            LastError = GetLastError();
            IsFileExcluded = LastError;
            if ( LastError > 0 )
              IsFileExcluded = (unsigned __int16)LastError | 0x80070000;
            if ( IsFileExcluded >= 0 )
            {
LABEL_36:
              if ( DeviceIoControl(FileW, 0x22496Cu, 0, 0, &OutBuffer, 0x10u, &BytesReturned, 0) )
                goto LABEL_37;
              v15 = GetLastError();
              IsFileExcluded = v15;
              if ( v15 > 0 )
                IsFileExcluded = (unsigned __int16)v15 | 0x80070000;
              if ( IsFileExcluded >= 0 )
              {
LABEL_37:
                v16 = 2147483646;
                InBuffer = DWORD1(OutBuffer);
                v17 = 1023;
                v18 = &v30;
                do
                {
                  if ( !v16 )
                    break;
                  if ( !*a3 )
                    break;
                  *(_WORD *)v18 = *a3++;
                  v18 += 2;
                  --v16;
                  --v17;
                }
                while ( v17 );
                v19 = v18 - 2;
                if ( v17 )
                  v19 = v18;
                *(_WORD *)v19 = 0;
                IsFileExcluded = v17 == 0 ? 0x8007007A : 0;
                if ( v17 )
                {
                  if ( !DeviceIoControl(FileW, 0x2289CCu, &InBuffer, 0x804u, 0, 0, &BytesReturned, 0) )
                  {
                    v20 = GetLastError();
                    IsFileExcluded = v20;
                    if ( v20 > 0 )
                      IsFileExcluded = (unsigned __int16)v20 | 0x80070000;
                  }
                }
              }
              if ( FileW != (HANDLE)-1LL )
                CloseHandle(FileW);
            }
          }
          goto LABEL_49;
        }
        goto LABEL_19;
      }
    }
LABEL_49:
    if ( this != (CUwfManagement *)-120LL )
      CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration((CUwfManagement *)((char *)this + 120));
    return (unsigned int)IsFileExcluded;
  }
  if ( v8 > 0 )
    IsFileExcluded = (unsigned __int16)v8 | 0x80070000;
  if ( IsFileExcluded >= 0 )
    goto LABEL_16;
  return (unsigned int)IsFileExcluded;
}

```

## disassembly

```asm
0x180014d80  push    rbp
0x180014d82  push    rbx
0x180014d83  push    rsi
0x180014d84  push    rdi
0x180014d85  push    r12
0x180014d87  push    r14
0x180014d89  push    r15
0x180014d8b  lea     rbp, [rsp-0A10h]
0x180014d93  sub     rsp, 0B10h
0x180014d9a  mov     rax, cs:__security_cookie
0x180014da1  xor     rax, rsp
0x180014da4  mov     [rbp+0A40h+var_40], rax
0x180014dab  mov     rdi, rdx
0x180014dae  mov     rsi, r8
0x180014db1  xor     edx, edx; Val
0x180014db3  mov     r15, rcx
0x180014db6  lea     rcx, [rbp+0A40h+FileName]; void *
0x180014dbd  lea     r8d, [rdx+64h]; Size
0x180014dc1  call    memset_0
0x180014dc6  xorps   xmm0, xmm0
0x180014dc9  lea     rcx, [rsp+0B40h+InBuffer]; void *
0x180014dce  xor     r12d, r12d
0x180014dd1  xor     edx, edx; Val
0x180014dd3  mov     r8d, 804h; Size
0x180014dd9  mov     [rsp+0B40h+BytesReturned], r12d
0x180014dde  movups  [rsp+0B40h+OutBuffer], xmm0
0x180014de3  call    memset_0
0x180014de8  mov     r9, rdi
0x180014deb  mov     [rsp+0B40h+var_AE8], r12
0x180014df0  lea     r8, aWsWs_0; "%ws%ws"
0x180014df7  mov     [rsp+0B40h+var_B00], r12b
0x180014dfc  mov     edx, 104h; unsigned __int64
0x180014e01  mov     [rsp+0B40h+lpData], rsi
0x180014e06  lea     rcx, [rbp+0A40h+pszPath]; unsigned __int16 *
0x180014e0d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014e12  mov     ebx, eax
0x180014e14  test    eax, eax
0x180014e16  js      loc_18001515B
0x180014e1c  lea     rcx, [rbp+0A40h+pszPath]; pszPath
0x180014e23  call    cs:__imp_PathFileExistsW
0x180014e29  test    eax, eax
0x180014e2b  jnz     short loc_180014E37
0x180014e2d  mov     ebx, 80070002h
0x180014e32  jmp     loc_18001515B
0x180014e37  lea     rcx, [rbp+0A40h+pszPath]; pszPath
0x180014e3e  call    cs:__imp_PathIsDirectoryW
0x180014e44  test    eax, eax
0x180014e46  jz      short loc_180014E52
0x180014e48  mov     ebx, 80070057h
0x180014e4d  jmp     loc_18001515B
0x180014e52  mov     rdx, rsi; wchar_t *
0x180014e55  mov     rcx, rdi; String1
0x180014e58  call    ?CanFileBeCommitted@@YA_NPEBG0@Z; CanFileBeCommitted(ushort const *,ushort const *)
0x180014e5d  test    al, al
0x180014e5f  jz      short loc_180014E48
0x180014e61  mov     rcx, [r15+88h]; hKey
0x180014e68  lea     rax, [rsp+0B40h+cbData]
0x180014e6d  mov     [rsp+0B40h+lpcbData], rax; lpcbData
0x180014e72  lea     r9, [rsp+0B40h+Type]; lpType
0x180014e77  lea     rax, [rsp+0B40h+Data]
0x180014e7c  mov     dword ptr [rsp+0B40h+Data], r12d
0x180014e81  xor     r8d, r8d; lpReserved
0x180014e84  mov     [rsp+0B40h+lpData], rax; lpData
0x180014e89  lea     rdx, aUwfenabled; "UWFEnabled"
0x180014e90  mov     [rsp+0B40h+Type], r12d
0x180014e95  mov     [rsp+0B40h+cbData], 4
0x180014e9d  call    cs:__imp_RegQueryValueExW
0x180014ea3  mov     ebx, eax
0x180014ea5  test    eax, eax
0x180014ea7  jz      short loc_180014EBD
0x180014ea9  jle     short loc_180014EB4
0x180014eab  movzx   ebx, ax
0x180014eae  or      ebx, 80070000h
0x180014eb4  test    ebx, ebx
0x180014eb6  jns     short loc_180014EDF
0x180014eb8  jmp     loc_18001515B
0x180014ebd  cmp     [rsp+0B40h+Type], 4
0x180014ec2  jz      short loc_180014ECE
0x180014ec4  mov     ebx, 8007065Dh
0x180014ec9  jmp     loc_18001515B
0x180014ece  cmp     [rsp+0B40h+cbData], 4
0x180014ed3  jz      short loc_180014EDF
0x180014ed5  mov     ebx, 8007000Dh
0x180014eda  jmp     loc_18001515B
0x180014edf  cmp     dword ptr [rsp+0B40h+Data], r12d
0x180014ee4  setnz   al
0x180014ee7  test    al, al
0x180014ee9  jnz     short loc_180014EF3
0x180014eeb  mov     ebx, r12d
0x180014eee  jmp     loc_18001515B
0x180014ef3  lea     r14, [r15+78h]
0x180014ef7  mov     rcx, r14; this
0x180014efa  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x180014eff  lea     r8, [rsp+0B40h+var_AE8]; struct CUwfStaticVolumeConfiguration **
0x180014f04  mov     rdx, rdi; unsigned __int16 *
0x180014f07  mov     rcx, r14; this
0x180014f0a  call    ?get_StaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAJPEBGPEAPEAVCUwfStaticVolumeConfiguration@@@Z; CUwfStaticConfiguration::get_StaticVolumeConfiguration(ushort const *,CUwfStaticVolumeConfiguration * *)
0x180014f0f  mov     ebx, eax
0x180014f11  cmp     eax, 80070002h
0x180014f16  jnz     short loc_180014F20
0x180014f18  mov     ebx, r12d
0x180014f1b  jmp     loc_18001514E
0x180014f20  test    eax, eax
0x180014f22  js      loc_18001514E
0x180014f28  mov     rcx, [rsp+0B40h+var_AE8]
0x180014f2d  lea     rax, [rsp+0B40h+cbData]
0x180014f32  mov     [rsp+0B40h+lpcbData], rax; lpcbData
0x180014f37  lea     r9, [rsp+0B40h+Data]; lpType
0x180014f3c  lea     rax, [rsp+0B40h+Type]
0x180014f41  mov     [rsp+0B40h+Type], r12d
0x180014f46  xor     r8d, r8d; lpReserved
0x180014f49  mov     dword ptr [rsp+0B40h+Data], r12d
0x180014f4e  mov     rcx, [rcx+10h]; hKey
0x180014f52  lea     rdx, ValueName; "VolumeEnabled"
0x180014f59  mov     [rsp+0B40h+cbData], 4
0x180014f61  mov     [rsp+0B40h+lpData], rax; lpData
0x180014f66  call    cs:__imp_RegQueryValueExW
0x180014f6c  mov     ebx, eax
0x180014f6e  test    eax, eax
0x180014f70  jz      loc_18001517E
0x180014f76  jle     short loc_180014F81
0x180014f78  movzx   ebx, ax
0x180014f7b  or      ebx, 80070000h
0x180014f81  test    ebx, ebx
0x180014f83  js      loc_18001514E
0x180014f89  cmp     [rsp+0B40h+Type], r12d
0x180014f8e  setnz   al
0x180014f91  test    al, al
0x180014f93  jz      short loc_180014F18
0x180014f95  lea     rax, [rsp+0B40h+var_B00]
0x180014f9a  xor     r9d, r9d; unsigned __int16 *
0x180014f9d  mov     [rsp+0B40h+lpcbData], rax; bool *
0x180014fa2  mov     r8, rdi; unsigned __int16 *
0x180014fa5  mov     rcx, r15; this
0x180014fa8  mov     [rsp+0B40h+lpData], rsi; unsigned __int16 *
0x180014fad  call    ?IsFileExcluded@CUwfManagement@@AEAAJ_NPEBG11PEA_N@Z; CUwfManagement::IsFileExcluded(bool,ushort const *,ushort const *,ushort const *,bool *)
0x180014fb2  mov     ebx, eax
0x180014fb4  test    eax, eax
0x180014fb6  js      loc_18001514E
0x180014fbc  cmp     [rsp+0B40h+var_B00], r12b
0x180014fc1  jnz     loc_180014F18
0x180014fc7  mov     r9, rdi
0x180014fca  lea     r8, aS; "\\\\?\\%s"
0x180014fd1  mov     edx, 32h ; '2'; unsigned __int64
0x180014fd6  lea     rcx, [rbp+0A40h+FileName]; unsigned __int16 *
0x180014fdd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014fe2  mov     ebx, eax
0x180014fe4  test    eax, eax
0x180014fe6  js      loc_18001514E
0x180014fec  mov     [rsp+0B40h+hTemplateFile], r12; hTemplateFile
0x180014ff1  lea     rcx, [rbp+0A40h+FileName]; lpFileName
0x180014ff8  mov     r8d, 3; dwShareMode
0x180014ffe  mov     dword ptr [rsp+0B40h+lpcbData], 80h; dwFlagsAndAttributes
0x180015006  xor     r9d, r9d; lpSecurityAttributes
0x180015009  mov     dword ptr [rsp+0B40h+lpData], r8d; dwCreationDisposition
0x18001500e  mov     edx, 0C0000000h; dwDesiredAccess
0x180015013  call    cs:__imp_CreateFileW
0x180015019  mov     rdi, rax
0x18001501c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015020  jnz     short loc_18001503F
0x180015022  call    cs:__imp_GetLastError
0x180015028  mov     ebx, eax
0x18001502a  test    eax, eax
0x18001502c  jle     short loc_180015037
0x18001502e  movzx   ebx, ax
0x180015031  or      ebx, 80070000h
0x180015037  test    ebx, ebx
0x180015039  js      loc_18001514E
0x18001503f  mov     [rsp+0B40h+lpOverlapped], r12; lpOverlapped
0x180015044  lea     rax, [rsp+0B40h+BytesReturned]
0x180015049  mov     [rsp+0B40h+hTemplateFile], rax; lpBytesReturned
0x18001504e  xor     r9d, r9d; nInBufferSize
0x180015051  lea     rax, [rsp+0B40h+OutBuffer]
0x180015056  mov     dword ptr [rsp+0B40h+lpcbData], 10h; nOutBufferSize
0x18001505e  xor     r8d, r8d; lpInBuffer
0x180015061  mov     [rsp+0B40h+lpData], rax; lpOutBuffer
0x180015066  mov     edx, 22496Ch; dwIoControlCode
0x18001506b  mov     rcx, rdi; hDevice
0x18001506e  call    cs:__imp_DeviceIoControl
0x180015074  test    eax, eax
0x180015076  jnz     short loc_180015095
0x180015078  call    cs:__imp_GetLastError
0x18001507e  mov     ebx, eax
0x180015080  test    eax, eax
0x180015082  jle     short loc_18001508D
0x180015084  movzx   ebx, ax
0x180015087  or      ebx, 80070000h
0x18001508d  test    ebx, ebx
0x18001508f  js      loc_18001513F
0x180015095  mov     eax, dword ptr [rsp+0B40h+OutBuffer+4]
0x180015099  mov     ecx, 7FFFFFFEh
0x18001509e  mov     [rsp+0B40h+InBuffer], eax
0x1800150a2  mov     edx, 3FFh
0x1800150a7  lea     rax, [rsp+0B40h+var_ACC]
0x1800150ac  test    rcx, rcx
0x1800150af  jz      short loc_1800150D0
0x1800150b1  movzx   r8d, word ptr [rsi]
0x1800150b5  test    r8w, r8w
0x1800150b9  jz      short loc_1800150D0
0x1800150bb  mov     [rax], r8w
0x1800150bf  add     rsi, 2
0x1800150c3  add     rax, 2
0x1800150c7  dec     rcx
0x1800150ca  sub     rdx, 1
0x1800150ce  jnz     short loc_1800150AC
0x1800150d0  test    rdx, rdx
0x1800150d3  lea     rcx, [rax-2]
0x1800150d7  cmovnz  rcx, rax
0x1800150db  mov     rax, rdx
0x1800150de  neg     rax
0x1800150e1  sbb     ebx, ebx
0x1800150e3  not     ebx
0x1800150e5  mov     [rcx], r12w
0x1800150e9  and     ebx, 8007007Ah
0x1800150ef  test    rdx, rdx
0x1800150f2  jz      short loc_18001513F
0x1800150f4  mov     [rsp+0B40h+lpOverlapped], r12; lpOverlapped
0x1800150f9  lea     rax, [rsp+0B40h+BytesReturned]
0x1800150fe  mov     [rsp+0B40h+hTemplateFile], rax; lpBytesReturned
0x180015103  lea     r8, [rsp+0B40h+InBuffer]; lpInBuffer
0x180015108  mov     dword ptr [rsp+0B40h+lpcbData], r12d; nOutBufferSize
0x18001510d  mov     r9d, 804h; nInBufferSize
0x180015113  mov     edx, 2289CCh; dwIoControlCode
0x180015118  mov     [rsp+0B40h+lpData], r12; lpOutBuffer
0x18001511d  mov     rcx, rdi; hDevice
0x180015120  call    cs:__imp_DeviceIoControl
0x180015126  test    eax, eax
0x180015128  jnz     short loc_18001513F
0x18001512a  call    cs:__imp_GetLastError
0x180015130  mov     ebx, eax
0x180015132  test    eax, eax
0x180015134  jle     short loc_18001513F
0x180015136  movzx   ebx, ax
0x180015139  or      ebx, 80070000h
0x18001513f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180015143  jz      short loc_18001514E
0x180015145  mov     rcx, rdi; hObject
0x180015148  call    cs:__imp_CloseHandle
0x18001514e  test    r14, r14
0x180015151  jz      short loc_18001515B
0x180015153  mov     rcx, r14; this
0x180015156  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18001515b  mov     eax, ebx
0x18001515d  mov     rcx, [rbp+0A40h+var_40]
0x180015164  xor     rcx, rsp; StackCookie
0x180015167  call    __security_check_cookie
0x18001516c  add     rsp, 0B10h
0x180015173  pop     r15
0x180015175  pop     r14
0x180015177  pop     r12
0x180015179  pop     rdi
0x18001517a  pop     rsi
0x18001517b  pop     rbx
0x18001517c  pop     rbp
0x18001517d  retn
0x18001517e  cmp     dword ptr [rsp+0B40h+Data], 4
0x180015183  jz      short loc_18001518C
0x180015185  mov     ebx, 8007065Dh
0x18001518a  jmp     short loc_18001514E
0x18001518c  cmp     [rsp+0B40h+cbData], 4
0x180015191  jz      loc_180014F89
0x180015197  mov     ebx, 8007000Dh
0x18001519c  jmp     short loc_18001514E
```
