# CDmpClient::Init(int)

- ea: `0x100481be0`
- end: `0x100481f76`
- name: `?Init@CDmpClient@@UEAAJH@Z`
- size: `918`
- prototype: `__int64 __fastcall(CDmpClient *__hidden this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x100403b90`
- `0x100481230`
- `0x1004818c0`
- `0x100481a70`
- `0x100481be0`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x100481c3f`
- `KERNEL32!CreateMutexW` at `0x100481ca6`
- `KERNEL32!CreateMutexW` at `0x100481c3f`
- `KERNEL32!CreateMutexW` at `0x100481ca6`
- `KERNEL32!SetHandleInformation` at `0x100481c78`
- `KERNEL32!SetHandleInformation` at `0x100481cdf`
- `KERNEL32!SetHandleInformation` at `0x100481c78`
- `KERNEL32!SetHandleInformation` at `0x100481cdf`
- `KERNEL32!Sleep` at `0x100481f02`
- `KERNEL32!Sleep` at `0x100481f02`
- `KERNEL32!LoadLibraryExW` at `0x100481f1f`
- `KERNEL32!LoadLibraryExW` at `0x100481f1f`
- `KERNEL32!FreeLibrary` at `0x100481f51`
- `KERNEL32!FreeLibrary` at `0x100481f51`
- `KERNEL32!GetSystemInfo` at `0x100481f5c`
- `KERNEL32!GetSystemInfo` at `0x100481f5c`
- `KERNEL32!GetProcAddress` at `0x100481f32`
- `KERNEL32!GetProcAddress` at `0x100481f32`
- `KERNEL32!GetLastError` at `0x100481c4e`
- `KERNEL32!GetLastError` at `0x100481c82`
- `KERNEL32!GetLastError` at `0x100481cb5`
- `KERNEL32!GetLastError` at `0x100481ce9`
- `KERNEL32!GetLastError` at `0x100481c4e`
- `KERNEL32!GetLastError` at `0x100481c82`
- `KERNEL32!GetLastError` at `0x100481cb5`
- `KERNEL32!GetLastError` at `0x100481ce9`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100481e4e`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100481e4e`
- `ADVAPI32!RegOpenKeyExW` at `0x100481d4e`
- `ADVAPI32!RegOpenKeyExW` at `0x100481d4e`
- `ADVAPI32!RegCloseKey` at `0x100481e8a`
- `ADVAPI32!RegCloseKey` at `0x100481eaf`
- `ADVAPI32!RegCloseKey` at `0x100481e8a`
- `ADVAPI32!RegCloseKey` at `0x100481eaf`
- `ADVAPI32!RegQueryValueExW` at `0x100481dee`
- `ADVAPI32!RegQueryValueExW` at `0x100481dee`

## string_xrefs

- `0x100481f12`: `psapi.dll`

## pseudocode

```c
__int64 __fastcall CDmpClient::Init(CDmpClient *this, int a2)
{
  char *v3; // rsi
  signed int inited; // ebx
  HANDLE MutexW; // rax
  signed int LastError; // eax
  signed int v7; // eax
  HANDLE v8; // rax
  signed int v9; // eax
  signed int v10; // eax
  char *v11; // rsi
  _WORD *v12; // rcx
  __int64 v13; // rdx
  __int16 v14; // ax
  _WORD *v15; // rax
  LSTATUS v16; // eax
  unsigned __int64 v17; // rax
  struct __crt_locale_pointers *DefaultLocale; // rax
  HMODULE Library; // rbx
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-58h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+8h] BYREF
  DWORD Type; // [rsp+98h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+20h] BYREF

  if ( a2 )
    *((_DWORD *)this + 3848) = 1;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 2, 1, 0) )
  {
    v3 = (char *)this + 16;
    inited = DmpHeap::Init((CDmpClient *)((char *)this + 16));
    if ( inited < 0 )
      goto LABEL_50;
    *((_QWORD *)this + 42) = v3;
    MutexW = CreateMutexW(0, 0, 0);
    *((_QWORD *)this + 3) = MutexW;
    if ( !MutexW )
    {
      LastError = GetLastError();
      inited = LastError;
      if ( LastError > 0 )
        inited = (unsigned __int16)LastError | 0x80070000;
      if ( inited < 0 )
        goto LABEL_50;
    }
    _mm_lfence();
    if ( !SetHandleInformation(*((HANDLE *)this + 3), 2u, 2u) )
    {
      v7 = GetLastError();
      inited = v7;
      if ( v7 > 0 )
        inited = (unsigned __int16)v7 | 0x80070000;
      if ( inited < 0 )
        goto LABEL_50;
    }
    v8 = CreateMutexW(0, 0, 0);
    *((_QWORD *)this + 4) = v8;
    if ( !v8 )
    {
      v9 = GetLastError();
      inited = v9;
      if ( v9 > 0 )
        inited = (unsigned __int16)v9 | 0x80070000;
      if ( inited < 0 )
        goto LABEL_50;
    }
    _mm_lfence();
    if ( !SetHandleInformation(*((HANDLE *)this + 4), 2u, 2u) )
    {
      v10 = GetLastError();
      inited = v10;
      if ( v10 > 0 )
        inited = (unsigned __int16)v10 | 0x80070000;
      if ( inited < 0 )
        goto LABEL_50;
    }
    if ( *((_DWORD *)this + 3848) )
    {
      _mm_lfence();
      inited = CDmpClient::InitPaths(this, 0);
LABEL_50:
      *((_DWORD *)this + 3) = inited;
      _InterlockedCompareExchange((volatile signed __int32 *)this + 2, 2, 1);
      goto LABEL_53;
    }
    inited = 0;
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Microsoft SQL Server\\160", 0, 1u, &hKey) )
    {
      _mm_lfence();
      inited = CDmpClient::GetDefaultDir(this);
LABEL_48:
      if ( inited < 0 )
        memset_0((char *)this + 6160, 0, 0x410u);
      goto LABEL_50;
    }
    v11 = (char *)this + 6680;
    Type = 0;
    cbData = 520;
    v12 = (_WORD *)((char *)this + 6680);
    v13 = 260;
    do
    {
      if ( v13 == -2147483386 )
        break;
      v14 = *(_WORD *)((char *)v12 + (char *)&word_1004A26DC - ((char *)this + 6680));
      if ( !v14 )
        break;
      *v12++ = v14;
      --v13;
    }
    while ( v13 );
    v15 = v12 - 1;
    if ( v13 )
      v15 = v12;
    *v15 = 0;
    _mm_lfence();
    v16 = RegQueryValueExW(hKey, L"SharedCode", 0, &Type, (LPBYTE)this + 6680, &cbData);
    if ( v16 )
    {
      if ( v16 > 0 )
        inited = (unsigned __int16)v16 | 0x80070000;
      else
        inited = v16;
    }
    else if ( Type != 1 || (cbData & 1) != 0 || cbData < 2 )
    {
      inited = -2147024885;
    }
    else
    {
      v17 = (unsigned __int64)cbData >> 1;
      if ( *(_WORD *)&v11[2 * v17 - 2] )
      {
        if ( v17 < 0x104 )
        {
          *(_WORD *)&v11[2 * v17] = 0;
LABEL_43:
          _mm_lfence();
          DefaultLocale = GetDefaultLocale();
          inited = StringCchPrintf_lW(
                     (wchar_t *)this + 3080,
                     0x104u,
                     L"%ls\\%ls",
                     DefaultLocale,
                     (char *)this + 6680,
                     L"SQLDUMPER.EXE");
          RegCloseKey(hKey);
          goto LABEL_48;
        }
        inited = -2147024774;
      }
    }
    if ( inited < 0 )
    {
      if ( inited == -2147024894 )
      {
        _mm_lfence();
        inited = CDmpClient::GetDefaultDir(this);
      }
      RegCloseKey(hKey);
      goto LABEL_48;
    }
    goto LABEL_43;
  }
  while ( *((_DWORD *)this + 2) != 2 )
    Sleep(1u);
LABEL_53:
  Library = LoadLibraryExW(L"psapi.dll", 0, 0x800u);
  s_QueryWorkingSetExRoutine = (int (*)(void *, void *, unsigned int))GetProcAddress(Library, "QueryWorkingSetEx");
  if ( !s_QueryWorkingSetExRoutine && Library )
    FreeLibrary(Library);
  GetSystemInfo(&SystemInfo);
  s_dwPageSize = SystemInfo.dwPageSize;
  return *((unsigned int *)this + 3);
}

```

## disassembly

```asm
0x100481be0  push    rbx
0x100481be2  push    rdi
0x100481be3  sub     rsp, 78h
0x100481be7  mov     [rsp+88h+var_18], rbp
0x100481bec  mov     ebp, 1
0x100481bf1  mov     rdi, rcx
0x100481bf4  test    edx, edx
0x100481bf6  jz      short loc_100481BFE
0x100481bf8  mov     [rcx+3C20h], ebp
0x100481bfe  xor     eax, eax
0x100481c00  lock cmpxchg [rcx+8], ebp
0x100481c05  jnz     loc_100481EF3
0x100481c0b  mov     [rsp+88h+var_20], rsi
0x100481c10  lea     rsi, [rcx+10h]
0x100481c14  mov     rcx, rsi; this
0x100481c17  mov     [rsp+88h+var_28], r14
0x100481c1c  call    ?Init@DmpHeap@@QEAAJXZ; DmpHeap::Init(void)
0x100481c21  mov     ebx, eax
0x100481c23  mov     r14d, 2
0x100481c29  test    eax, eax
0x100481c2b  js      loc_100481EDC
0x100481c31  xor     r8d, r8d; lpName
0x100481c34  mov     [rdi+150h], rsi
0x100481c3b  xor     edx, edx; bInitialOwner
0x100481c3d  xor     ecx, ecx; lpMutexAttributes
0x100481c3f  call    cs:__imp_CreateMutexW
0x100481c45  mov     [rdi+18h], rax
0x100481c49  test    rax, rax
0x100481c4c  jnz     short loc_100481C6B
0x100481c4e  call    cs:__imp_GetLastError
0x100481c54  mov     ebx, eax
0x100481c56  test    eax, eax
0x100481c58  jle     short loc_100481C63
0x100481c5a  movzx   ebx, ax
0x100481c5d  or      ebx, 80070000h
0x100481c63  test    ebx, ebx
0x100481c65  js      loc_100481EDC
0x100481c6b  lfence
0x100481c6e  mov     rcx, [rdi+18h]; hObject
0x100481c72  mov     r8d, r14d; dwFlags
0x100481c75  mov     edx, r14d; dwMask
0x100481c78  call    cs:__imp_SetHandleInformation
0x100481c7e  test    eax, eax
0x100481c80  jnz     short loc_100481C9F
0x100481c82  call    cs:__imp_GetLastError
0x100481c88  mov     ebx, eax
0x100481c8a  test    eax, eax
0x100481c8c  jle     short loc_100481C97
0x100481c8e  movzx   ebx, ax
0x100481c91  or      ebx, 80070000h
0x100481c97  test    ebx, ebx
0x100481c99  js      loc_100481EDC
0x100481c9f  xor     r8d, r8d; lpName
0x100481ca2  xor     edx, edx; bInitialOwner
0x100481ca4  xor     ecx, ecx; lpMutexAttributes
0x100481ca6  call    cs:__imp_CreateMutexW
0x100481cac  mov     [rdi+20h], rax
0x100481cb0  test    rax, rax
0x100481cb3  jnz     short loc_100481CD2
0x100481cb5  call    cs:__imp_GetLastError
0x100481cbb  mov     ebx, eax
0x100481cbd  test    eax, eax
0x100481cbf  jle     short loc_100481CCA
0x100481cc1  movzx   ebx, ax
0x100481cc4  or      ebx, 80070000h
0x100481cca  test    ebx, ebx
0x100481ccc  js      loc_100481EDC
0x100481cd2  lfence
0x100481cd5  mov     rcx, [rdi+20h]; hObject
0x100481cd9  mov     r8d, r14d; dwFlags
0x100481cdc  mov     edx, r14d; dwMask
0x100481cdf  call    cs:__imp_SetHandleInformation
0x100481ce5  test    eax, eax
0x100481ce7  jnz     short loc_100481D06
0x100481ce9  call    cs:__imp_GetLastError
0x100481cef  mov     ebx, eax
0x100481cf1  test    eax, eax
0x100481cf3  jle     short loc_100481CFE
0x100481cf5  movzx   ebx, ax
0x100481cf8  or      ebx, 80070000h
0x100481cfe  test    ebx, ebx
0x100481d00  js      loc_100481EDC
0x100481d06  cmp     dword ptr [rdi+3C20h], 0
0x100481d0d  jz      short loc_100481D23
0x100481d0f  lfence
0x100481d12  xor     edx, edx; wchar_t *
0x100481d14  mov     rcx, rdi; this
0x100481d17  call    ?InitPaths@CDmpClient@@AEAAJPEB_W@Z; CDmpClient::InitPaths(wchar_t const *)
0x100481d1c  mov     ebx, eax
0x100481d1e  jmp     loc_100481EDC
0x100481d23  lea     rax, [rsp+88h+hKey]
0x100481d2b  xor     ebx, ebx
0x100481d2d  mov     r9d, ebp; samDesired
0x100481d30  mov     [rsp+88h+hKey], rbx
0x100481d38  xor     r8d, r8d; ulOptions
0x100481d3b  mov     [rsp+88h+phkResult], rax; phkResult
0x100481d40  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0x100481d47  mov     rcx, 0FFFFFFFF80000002h; hKey
0x100481d4e  call    cs:__imp_RegOpenKeyExW
0x100481d54  test    eax, eax
0x100481d56  jnz     loc_100481EB7
0x100481d5c  lea     rsi, [rdi+1A18h]
0x100481d63  mov     [rsp+88h+Type], ebx
0x100481d6a  lea     r8, word_1004A26DC
0x100481d71  mov     [rsp+88h+cbData], 208h
0x100481d7c  mov     rcx, rsi
0x100481d7f  sub     r8, rsi
0x100481d82  mov     edx, 104h
0x100481d87  nop     word ptr [rax+rax+00000000h]
0x100481d90  lea     rax, [rdx+7FFFFEFAh]
0x100481d97  test    rax, rax
0x100481d9a  jz      short loc_100481DB1
0x100481d9c  movzx   eax, word ptr [r8+rcx]
0x100481da1  test    ax, ax
0x100481da4  jz      short loc_100481DB1
0x100481da6  mov     [rcx], ax
0x100481da9  add     rcx, r14
0x100481dac  sub     rdx, rbp
0x100481daf  jnz     short loc_100481D90
0x100481db1  test    rdx, rdx
0x100481db4  lea     rax, [rcx-2]
0x100481db8  cmovnz  rax, rcx
0x100481dbc  mov     [rax], bx
0x100481dbf  lfence
0x100481dc2  mov     rcx, [rsp+88h+hKey]; hKey
0x100481dca  lea     rax, [rsp+88h+cbData]
0x100481dd2  mov     [rsp+88h+lpcbData], rax; lpcbData
0x100481dd7  lea     r9, [rsp+88h+Type]; lpType
0x100481ddf  xor     r8d, r8d; lpReserved
0x100481de2  mov     [rsp+88h+phkResult], rsi; lpData
0x100481de7  lea     rdx, ValueName; "SharedCode"
0x100481dee  call    cs:__imp_RegQueryValueExW
0x100481df4  test    eax, eax
0x100481df6  jnz     short loc_100481E38
0x100481df8  cmp     [rsp+88h+Type], ebp
0x100481dff  jnz     short loc_100481E31
0x100481e01  mov     eax, [rsp+88h+cbData]
0x100481e08  test    bpl, al
0x100481e0b  jnz     short loc_100481E31
0x100481e0d  cmp     eax, r14d
0x100481e10  jb      short loc_100481E31
0x100481e12  shr     rax, 1
0x100481e15  cmp     [rsi+rax*2-2], bx
0x100481e1a  jz      short loc_100481E47
0x100481e1c  cmp     rax, 104h
0x100481e22  jnb     short loc_100481E2A
0x100481e24  mov     [rsi+rax*2], bx
0x100481e28  jmp     short loc_100481E4B
0x100481e2a  mov     ebx, 8007007Ah
0x100481e2f  jmp     short loc_100481E47
0x100481e31  mov     ebx, 8007000Bh
0x100481e36  jmp     short loc_100481E47
0x100481e38  jg      short loc_100481E3E
0x100481e3a  mov     ebx, eax
0x100481e3c  jmp     short loc_100481E47
0x100481e3e  movzx   ebx, ax
0x100481e41  or      ebx, 80070000h
0x100481e47  test    ebx, ebx
0x100481e49  js      short loc_100481E92
0x100481e4b  lfence
0x100481e4e  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100481e54  lea     rcx, [rdi+1810h]; Buffer
0x100481e5b  mov     edx, 104h; unsigned __int64
0x100481e60  mov     r9, rax; struct __crt_locale_pointers *
0x100481e63  lea     r8, aLsLs_0; "%ls\\%ls"
0x100481e6a  lea     rax, aSqldumperExe; "SQLDUMPER.EXE"
0x100481e71  mov     [rsp+88h+lpcbData], rax
0x100481e76  mov     [rsp+88h+phkResult], rsi
0x100481e7b  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100481e80  mov     rcx, [rsp+88h+hKey]; hKey
0x100481e88  mov     ebx, eax
0x100481e8a  call    cs:__imp_RegCloseKey
0x100481e90  jmp     short loc_100481EC4
0x100481e92  cmp     ebx, 80070002h
0x100481e98  jnz     short loc_100481EA7
0x100481e9a  lfence
0x100481e9d  mov     rcx, rdi; this
0x100481ea0  call    ?GetDefaultDir@CDmpClient@@AEAAJXZ; CDmpClient::GetDefaultDir(void)
0x100481ea5  mov     ebx, eax
0x100481ea7  mov     rcx, [rsp+88h+hKey]; hKey
0x100481eaf  call    cs:__imp_RegCloseKey
0x100481eb5  jmp     short loc_100481EC4
0x100481eb7  lfence
0x100481eba  mov     rcx, rdi; this
0x100481ebd  call    ?GetDefaultDir@CDmpClient@@AEAAJXZ; CDmpClient::GetDefaultDir(void)
0x100481ec2  mov     ebx, eax
0x100481ec4  test    ebx, ebx
0x100481ec6  jns     short loc_100481EDC
0x100481ec8  lea     rcx, [rdi+1810h]; void *
0x100481ecf  xor     edx, edx; Val
0x100481ed1  mov     r8d, 410h; Size
0x100481ed7  call    memset_0
0x100481edc  mov     [rdi+0Ch], ebx
0x100481edf  mov     eax, ebp
0x100481ee1  lock cmpxchg [rdi+8], r14d
0x100481ee7  mov     r14, [rsp+88h+var_28]
0x100481eec  mov     rsi, [rsp+88h+var_20]
0x100481ef1  jmp     short loc_100481F10
0x100481ef3  mov     eax, [rcx+8]
0x100481ef6  cmp     eax, 2
0x100481ef9  jz      short loc_100481F10
0x100481efb  nop     dword ptr [rax+rax+00h]
0x100481f00  mov     ecx, ebp; dwMilliseconds
0x100481f02  call    cs:__imp_Sleep
0x100481f08  mov     eax, [rdi+8]
0x100481f0b  cmp     eax, 2
0x100481f0e  jnz     short loc_100481F00
0x100481f10  xor     edx, edx; hFile
0x100481f12  lea     rcx, aPsapiDll; "psapi.dll"
0x100481f19  mov     r8d, 800h; dwFlags
0x100481f1f  call    cs:__imp_LoadLibraryExW
0x100481f25  mov     rcx, rax; hModule
0x100481f28  lea     rdx, aQueryworkingse; "QueryWorkingSetEx"
0x100481f2f  mov     rbx, rax
0x100481f32  call    cs:__imp_GetProcAddress
0x100481f38  mov     rbp, [rsp+88h+var_18]
0x100481f3d  mov     cs:?s_QueryWorkingSetExRoutine@@3P6AHPEAX0K@ZEA, rax; int (*s_QueryWorkingSetExRoutine)(void *,void *,ulong)
0x100481f44  test    rax, rax
0x100481f47  jnz     short loc_100481F57
0x100481f49  test    rbx, rbx
0x100481f4c  jz      short loc_100481F57
0x100481f4e  mov     rcx, rbx; hLibModule
0x100481f51  call    cs:__imp_FreeLibrary
0x100481f57  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x100481f5c  call    cs:__imp_GetSystemInfo
0x100481f62  mov     eax, [rsp+88h+SystemInfo.dwPageSize]
0x100481f66  mov     cs:?s_dwPageSize@@3KA, eax; ulong s_dwPageSize
0x100481f6c  mov     eax, [rdi+0Ch]
0x100481f6f  add     rsp, 78h
0x100481f73  pop     rdi
0x100481f74  pop     rbx
0x100481f75  retn
```
