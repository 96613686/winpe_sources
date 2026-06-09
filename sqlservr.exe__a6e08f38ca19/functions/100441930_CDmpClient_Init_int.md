# CDmpClient::Init(int)

- ea: `0x100441930`
- end: `0x100441cc6`
- name: `?Init@CDmpClient@@UEAAJH@Z`
- size: `918`
- prototype: `__int64 __fastcall(CDmpClient *__hidden this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x100401aa0`
- `0x100440ce0`
- `0x100441610`
- `0x1004417c0`
- `0x100441930`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!Sleep` at `0x100441c52`
- `KERNEL32!Sleep` at `0x100441c52`
- `KERNEL32!GetProcAddress` at `0x100441c82`
- `KERNEL32!GetProcAddress` at `0x100441c82`
- `KERNEL32!FreeLibrary` at `0x100441ca1`
- `KERNEL32!FreeLibrary` at `0x100441ca1`
- `KERNEL32!GetLastError` at `0x10044199e`
- `KERNEL32!GetLastError` at `0x1004419d2`
- `KERNEL32!GetLastError` at `0x100441a05`
- `KERNEL32!GetLastError` at `0x100441a39`
- `KERNEL32!GetLastError` at `0x10044199e`
- `KERNEL32!GetLastError` at `0x1004419d2`
- `KERNEL32!GetLastError` at `0x100441a05`
- `KERNEL32!GetLastError` at `0x100441a39`
- `KERNEL32!CreateMutexW` at `0x10044198f`
- `KERNEL32!CreateMutexW` at `0x1004419f6`
- `KERNEL32!CreateMutexW` at `0x10044198f`
- `KERNEL32!CreateMutexW` at `0x1004419f6`
- `KERNEL32!SetHandleInformation` at `0x1004419c8`
- `KERNEL32!SetHandleInformation` at `0x100441a2f`
- `KERNEL32!SetHandleInformation` at `0x1004419c8`
- `KERNEL32!SetHandleInformation` at `0x100441a2f`
- `KERNEL32!LoadLibraryExW` at `0x100441c6f`
- `KERNEL32!LoadLibraryExW` at `0x100441c6f`
- `KERNEL32!GetSystemInfo` at `0x100441cac`
- `KERNEL32!GetSystemInfo` at `0x100441cac`
- `ADVAPI32!RegCloseKey` at `0x100441bda`
- `ADVAPI32!RegCloseKey` at `0x100441bff`
- `ADVAPI32!RegCloseKey` at `0x100441bda`
- `ADVAPI32!RegCloseKey` at `0x100441bff`
- `ADVAPI32!RegOpenKeyExW` at `0x100441a9e`
- `ADVAPI32!RegOpenKeyExW` at `0x100441a9e`
- `ADVAPI32!RegQueryValueExW` at `0x100441b3e`
- `ADVAPI32!RegQueryValueExW` at `0x100441b3e`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100441b9e`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100441b9e`

## string_xrefs

- `0x100441c62`: `psapi.dll`

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
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-58h] BYREF
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
      v14 = *(_WORD *)((char *)v12 + (char *)&dword_10045ADE4 - ((char *)this + 6680));
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
0x100441930  push    rbx
0x100441932  push    rdi
0x100441933  sub     rsp, 78h
0x100441937  mov     [rsp+88h+var_18], rbp
0x10044193c  mov     ebp, 1
0x100441941  mov     rdi, rcx
0x100441944  test    edx, edx
0x100441946  jz      short loc_10044194E
0x100441948  mov     [rcx+3C20h], ebp
0x10044194e  xor     eax, eax
0x100441950  lock cmpxchg [rcx+8], ebp
0x100441955  jnz     loc_100441C44
0x10044195b  mov     [rsp+88h+var_20], rsi
0x100441960  lea     rsi, [rcx+10h]
0x100441964  mov     rcx, rsi; this
0x100441967  mov     [rsp+88h+var_28], r14
0x10044196c  call    ?Init@DmpHeap@@QEAAJXZ; DmpHeap::Init(void)
0x100441971  mov     ebx, eax
0x100441973  mov     r14d, 2
0x100441979  test    eax, eax
0x10044197b  js      loc_100441C2C
0x100441981  xor     r8d, r8d; lpName
0x100441984  mov     [rdi+150h], rsi
0x10044198b  xor     edx, edx; bInitialOwner
0x10044198d  xor     ecx, ecx; lpMutexAttributes
0x10044198f  call    cs:__imp_CreateMutexW
0x100441995  mov     [rdi+18h], rax
0x100441999  test    rax, rax
0x10044199c  jnz     short loc_1004419BB
0x10044199e  call    cs:__imp_GetLastError
0x1004419a4  mov     ebx, eax
0x1004419a6  test    eax, eax
0x1004419a8  jle     short loc_1004419B3
0x1004419aa  movzx   ebx, ax
0x1004419ad  or      ebx, 80070000h
0x1004419b3  test    ebx, ebx
0x1004419b5  js      loc_100441C2C
0x1004419bb  lfence
0x1004419be  mov     rcx, [rdi+18h]; hObject
0x1004419c2  mov     r8d, r14d; dwFlags
0x1004419c5  mov     edx, r14d; dwMask
0x1004419c8  call    cs:__imp_SetHandleInformation
0x1004419ce  test    eax, eax
0x1004419d0  jnz     short loc_1004419EF
0x1004419d2  call    cs:__imp_GetLastError
0x1004419d8  mov     ebx, eax
0x1004419da  test    eax, eax
0x1004419dc  jle     short loc_1004419E7
0x1004419de  movzx   ebx, ax
0x1004419e1  or      ebx, 80070000h
0x1004419e7  test    ebx, ebx
0x1004419e9  js      loc_100441C2C
0x1004419ef  xor     r8d, r8d; lpName
0x1004419f2  xor     edx, edx; bInitialOwner
0x1004419f4  xor     ecx, ecx; lpMutexAttributes
0x1004419f6  call    cs:__imp_CreateMutexW
0x1004419fc  mov     [rdi+20h], rax
0x100441a00  test    rax, rax
0x100441a03  jnz     short loc_100441A22
0x100441a05  call    cs:__imp_GetLastError
0x100441a0b  mov     ebx, eax
0x100441a0d  test    eax, eax
0x100441a0f  jle     short loc_100441A1A
0x100441a11  movzx   ebx, ax
0x100441a14  or      ebx, 80070000h
0x100441a1a  test    ebx, ebx
0x100441a1c  js      loc_100441C2C
0x100441a22  lfence
0x100441a25  mov     rcx, [rdi+20h]; hObject
0x100441a29  mov     r8d, r14d; dwFlags
0x100441a2c  mov     edx, r14d; dwMask
0x100441a2f  call    cs:__imp_SetHandleInformation
0x100441a35  test    eax, eax
0x100441a37  jnz     short loc_100441A56
0x100441a39  call    cs:__imp_GetLastError
0x100441a3f  mov     ebx, eax
0x100441a41  test    eax, eax
0x100441a43  jle     short loc_100441A4E
0x100441a45  movzx   ebx, ax
0x100441a48  or      ebx, 80070000h
0x100441a4e  test    ebx, ebx
0x100441a50  js      loc_100441C2C
0x100441a56  cmp     dword ptr [rdi+3C20h], 0
0x100441a5d  jz      short loc_100441A73
0x100441a5f  lfence
0x100441a62  xor     edx, edx; wchar_t *
0x100441a64  mov     rcx, rdi; this
0x100441a67  call    ?InitPaths@CDmpClient@@AEAAJPEB_W@Z; CDmpClient::InitPaths(wchar_t const *)
0x100441a6c  mov     ebx, eax
0x100441a6e  jmp     loc_100441C2C
0x100441a73  lea     rax, [rsp+88h+hKey]
0x100441a7b  xor     ebx, ebx
0x100441a7d  mov     r9d, ebp; samDesired
0x100441a80  mov     [rsp+88h+hKey], rbx
0x100441a88  xor     r8d, r8d; ulOptions
0x100441a8b  mov     [rsp+88h+phkResult], rax; phkResult
0x100441a90  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0x100441a97  mov     rcx, 0FFFFFFFF80000002h; hKey
0x100441a9e  call    cs:__imp_RegOpenKeyExW
0x100441aa4  test    eax, eax
0x100441aa6  jnz     loc_100441C07
0x100441aac  lea     rsi, [rdi+1A18h]
0x100441ab3  mov     [rsp+88h+Type], ebx
0x100441aba  lea     r8, dword_10045ADE4
0x100441ac1  mov     [rsp+88h+cbData], 208h
0x100441acc  mov     rcx, rsi
0x100441acf  sub     r8, rsi
0x100441ad2  mov     edx, 104h
0x100441ad7  nop     word ptr [rax+rax+00000000h]
0x100441ae0  lea     rax, [rdx+7FFFFEFAh]
0x100441ae7  test    rax, rax
0x100441aea  jz      short loc_100441B01
0x100441aec  movzx   eax, word ptr [r8+rcx]
0x100441af1  test    ax, ax
0x100441af4  jz      short loc_100441B01
0x100441af6  mov     [rcx], ax
0x100441af9  add     rcx, r14
0x100441afc  sub     rdx, rbp
0x100441aff  jnz     short loc_100441AE0
0x100441b01  test    rdx, rdx
0x100441b04  lea     rax, [rcx-2]
0x100441b08  cmovnz  rax, rcx
0x100441b0c  mov     [rax], bx
0x100441b0f  lfence
0x100441b12  mov     rcx, [rsp+88h+hKey]; hKey
0x100441b1a  lea     rax, [rsp+88h+cbData]
0x100441b22  mov     [rsp+88h+lpcbData], rax; lpcbData
0x100441b27  lea     r9, [rsp+88h+Type]; lpType
0x100441b2f  xor     r8d, r8d; lpReserved
0x100441b32  mov     [rsp+88h+phkResult], rsi; lpData
0x100441b37  lea     rdx, aSharedcode; "SharedCode"
0x100441b3e  call    cs:__imp_RegQueryValueExW
0x100441b44  test    eax, eax
0x100441b46  jnz     short loc_100441B88
0x100441b48  cmp     [rsp+88h+Type], ebp
0x100441b4f  jnz     short loc_100441B81
0x100441b51  mov     eax, [rsp+88h+cbData]
0x100441b58  test    bpl, al
0x100441b5b  jnz     short loc_100441B81
0x100441b5d  cmp     eax, r14d
0x100441b60  jb      short loc_100441B81
0x100441b62  shr     rax, 1
0x100441b65  cmp     [rsi+rax*2-2], bx
0x100441b6a  jz      short loc_100441B97
0x100441b6c  cmp     rax, 104h
0x100441b72  jnb     short loc_100441B7A
0x100441b74  mov     [rsi+rax*2], bx
0x100441b78  jmp     short loc_100441B9B
0x100441b7a  mov     ebx, 8007007Ah
0x100441b7f  jmp     short loc_100441B97
0x100441b81  mov     ebx, 8007000Bh
0x100441b86  jmp     short loc_100441B97
0x100441b88  jg      short loc_100441B8E
0x100441b8a  mov     ebx, eax
0x100441b8c  jmp     short loc_100441B97
0x100441b8e  movzx   ebx, ax
0x100441b91  or      ebx, 80070000h
0x100441b97  test    ebx, ebx
0x100441b99  js      short loc_100441BE2
0x100441b9b  lfence
0x100441b9e  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100441ba4  lea     rcx, [rdi+1810h]; Buffer
0x100441bab  mov     edx, 104h; unsigned __int64
0x100441bb0  mov     r9, rax; struct __crt_locale_pointers *
0x100441bb3  lea     r8, aLsLs_1; "%ls\\%ls"
0x100441bba  lea     rax, aSqldumperExe; "SQLDUMPER.EXE"
0x100441bc1  mov     [rsp+88h+lpcbData], rax
0x100441bc6  mov     [rsp+88h+phkResult], rsi
0x100441bcb  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100441bd0  mov     rcx, [rsp+88h+hKey]; hKey
0x100441bd8  mov     ebx, eax
0x100441bda  call    cs:__imp_RegCloseKey
0x100441be0  jmp     short loc_100441C14
0x100441be2  cmp     ebx, 80070002h
0x100441be8  jnz     short loc_100441BF7
0x100441bea  lfence
0x100441bed  mov     rcx, rdi; this
0x100441bf0  call    ?GetDefaultDir@CDmpClient@@AEAAJXZ; CDmpClient::GetDefaultDir(void)
0x100441bf5  mov     ebx, eax
0x100441bf7  mov     rcx, [rsp+88h+hKey]; hKey
0x100441bff  call    cs:__imp_RegCloseKey
0x100441c05  jmp     short loc_100441C14
0x100441c07  lfence
0x100441c0a  mov     rcx, rdi; this
0x100441c0d  call    ?GetDefaultDir@CDmpClient@@AEAAJXZ; CDmpClient::GetDefaultDir(void)
0x100441c12  mov     ebx, eax
0x100441c14  test    ebx, ebx
0x100441c16  jns     short loc_100441C2C
0x100441c18  lea     rcx, [rdi+1810h]; void *
0x100441c1f  xor     edx, edx; Val
0x100441c21  mov     r8d, 410h; Size
0x100441c27  call    memset_0
0x100441c2c  mov     [rdi+0Ch], ebx
0x100441c2f  mov     eax, ebp
0x100441c31  lock cmpxchg [rdi+8], r14d
0x100441c37  mov     r14, [rsp+88h+var_28]
0x100441c3c  mov     rsi, [rsp+88h+var_20]
0x100441c41  jmp     short loc_100441C60
0x100441c44  mov     eax, [rcx+8]
0x100441c47  cmp     eax, 2
0x100441c4a  jz      short loc_100441C60
0x100441c4c  nop     dword ptr [rax+rax]
0x100441c50  mov     ecx, ebp; dwMilliseconds
0x100441c52  call    cs:__imp_Sleep
0x100441c58  mov     eax, [rdi+8]
0x100441c5b  cmp     eax, 2
0x100441c5e  jnz     short loc_100441C50
0x100441c60  xor     edx, edx; hFile
0x100441c62  lea     rcx, aPsapiDll; "psapi.dll"
0x100441c69  mov     r8d, 800h; dwFlags
0x100441c6f  call    cs:__imp_LoadLibraryExW
0x100441c75  mov     rcx, rax; hModule
0x100441c78  lea     rdx, aQueryworkingse; "QueryWorkingSetEx"
0x100441c7f  mov     rbx, rax
0x100441c82  call    cs:__imp_GetProcAddress
0x100441c88  mov     rbp, [rsp+88h+var_18]
0x100441c8d  mov     cs:?s_QueryWorkingSetExRoutine@@3P6AHPEAX0K@ZEA, rax; int (*s_QueryWorkingSetExRoutine)(void *,void *,ulong)
0x100441c94  test    rax, rax
0x100441c97  jnz     short loc_100441CA7
0x100441c99  test    rbx, rbx
0x100441c9c  jz      short loc_100441CA7
0x100441c9e  mov     rcx, rbx; hLibModule
0x100441ca1  call    cs:__imp_FreeLibrary
0x100441ca7  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x100441cac  call    cs:__imp_GetSystemInfo
0x100441cb2  mov     eax, [rsp+88h+SystemInfo.dwPageSize]
0x100441cb6  mov     cs:?s_dwPageSize@@3KA, eax; ulong s_dwPageSize
0x100441cbc  mov     eax, [rdi+0Ch]
0x100441cbf  add     rsp, 78h
0x100441cc3  pop     rdi
0x100441cc4  pop     rbx
0x100441cc5  retn
```
