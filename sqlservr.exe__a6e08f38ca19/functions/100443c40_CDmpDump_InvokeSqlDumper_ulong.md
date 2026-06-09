# CDmpDump::InvokeSqlDumper(ulong)

- ea: `0x100443c40`
- end: `0x100443fcf`
- name: `?InvokeSqlDumper@CDmpDump@@UEAAJK@Z`
- size: `911`
- prototype: `__int64 __fastcall(CDmpDump *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x100401580`
- `0x100401aa0`
- `0x100404a30`
- `0x100443c40`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x100443eb8`
- `KERNEL32!WaitForSingleObject` at `0x100443eb8`
- `KERNEL32!CreateProcessW` at `0x100443e92`
- `KERNEL32!CreateProcessW` at `0x100443e92`
- `KERNEL32!GetExitCodeProcess` at `0x100443f0f`
- `KERNEL32!GetExitCodeProcess` at `0x100443f0f`
- `KERNEL32!CloseHandle` at `0x100443f6d`
- `KERNEL32!CloseHandle` at `0x100443f81`
- `KERNEL32!CloseHandle` at `0x100443f6d`
- `KERNEL32!CloseHandle` at `0x100443f81`
- `KERNEL32!GetLastError` at `0x100443f90`
- `KERNEL32!GetLastError` at `0x100443f90`
- `KERNEL32!GetTickCount` at `0x100443e4c`
- `KERNEL32!GetTickCount` at `0x100443ed0`
- `KERNEL32!GetTickCount` at `0x100443e4c`
- `KERNEL32!GetTickCount` at `0x100443ed0`
- `KERNEL32!GetStartupInfoW` at `0x100443e38`
- `KERNEL32!GetStartupInfoW` at `0x100443e38`
- `ole32!StringFromGUID2` at `0x100443d5f`
- `ole32!StringFromGUID2` at `0x100443d5f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100443ce8`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100443d80`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100443ddc`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100443ce8`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100443d80`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100443ddc`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100443f41`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100443f41`

## pseudocode

```c
__int64 __fastcall CDmpDump::InvokeSqlDumper(CDmpDump *this, int a2)
{
  int v4; // eax
  WCHAR *v5; // r15
  int v6; // edi
  int v7; // ebx
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v9; // eax
  const GUID *v10; // rcx
  struct __crt_locale_pointers *v11; // rax
  struct __crt_locale_pointers *v12; // rax
  unsigned int v13; // ebx
  HANDLE *v14; // rdi
  DWORD v15; // ebx
  signed int LastError; // eax
  DWORD TickCount; // [rsp+64h] [rbp-D4h]
  wchar_t Buffer[8]; // [rsp+80h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+90h] [rbp-A8h]
  __int64 v21; // [rsp+A0h] [rbp-98h]
  OLECHAR sz; // [rsp+B0h] [rbp-88h] BYREF
  _BYTE v23[72]; // [rsp+B2h] [rbp-86h] BYREF
  __int16 v24; // [rsp+FAh] [rbp-3Eh]

  *(_OWORD *)Buffer = 0;
  v20 = 0;
  v21 = 0;
  v4 = *((_DWORD *)this + 1258);
  if ( v4 != 4 )
    StringCchPrintfW(Buffer, 20, L"-Upload:%ls", off_10045A890[v4]);
  if ( a2 )
  {
    v5 = (WCHAR *)((char *)this + 5152);
    v6 = *((_DWORD *)this + 44) & ~*((_DWORD *)this + 45);
    v7 = *((_DWORD *)this + 42) & ~*((_DWORD *)this + 43);
    DefaultLocale = GetDefaultLocale();
    v9 = StringCchPrintf_lW(
           (wchar_t *)this + 2576,
           260,
           L"%ls %ld 0 %x:%x %ld \"%s\" %ls",
           DefaultLocale,
           L"SQLDUMPER.EXE",
           a2,
           v7,
           v6,
           0,
           *((_QWORD *)this + 8),
           Buffer);
  }
  else
  {
    v10 = (const GUID *)*((_QWORD *)this + 627);
    if ( v10 && StringFromGUID2(v10, &sz, 39) > 0 )
    {
      v24 = 0;
      v5 = (WCHAR *)((char *)this + 5152);
      v11 = GetDefaultLocale();
      v9 = StringCchPrintf_lW(
             (wchar_t *)this + 2576,
             260,
             L"%ls %ld 0 0:0 %p -DumpUID:%ls %ls",
             v11,
             L"SQLDUMPER.EXE",
             *((_DWORD *)this + 30),
             (char *)this + 24,
             v23,
             Buffer);
    }
    else
    {
      v5 = (WCHAR *)((char *)this + 5152);
      v12 = GetDefaultLocale();
      v9 = StringCchPrintf_lW(
             (wchar_t *)this + 2576,
             260,
             L"%ls %ld 0 0:0 %p %ls",
             v12,
             L"SQLDUMPER.EXE",
             *((_DWORD *)this + 30),
             (char *)this + 24,
             Buffer);
    }
  }
  v13 = v9;
  if ( v9 >= 0 )
  {
    _mm_lfence();
    GetStartupInfoW((LPSTARTUPINFOW)((char *)this + 5672));
    *((_QWORD *)this + 710) = 0;
    *((_QWORD *)this + 712) = 0;
    TickCount = GetTickCount();
    v14 = (HANDLE *)((char *)this + 5776);
    if ( CreateProcessW(
           (LPCWSTR)(*((_QWORD *)this + 2) + 6160LL),
           v5,
           0,
           0,
           0,
           0xC008010u,
           0,
           0,
           (LPSTARTUPINFOW)((char *)this + 5672),
           (LPPROCESS_INFORMATION)((char *)this + 5776)) )
    {
      do
        v15 = WaitForSingleObject(*v14, 0x64u);
      while ( v15 == 258 && (*((_DWORD *)this + 1280) == -1 || GetTickCount() - TickCount < *((_DWORD *)this + 1280)) );
      _mm_lfence();
      *((_DWORD *)this + 1283) = v15 == 258;
      *((_DWORD *)this + 1284) = 1;
      if ( GetExitCodeProcess(*v14, (LPDWORD)this + 1281) && *((_DWORD *)this + 1281) != 259 )
        *((_QWORD *)this + 641) = 1;
      _mm_lfence();
      v13 = 0;
      CloseHandle(*((HANDLE *)this + 723));
      *((_QWORD *)this + 723) = 0;
      CloseHandle(*((HANDLE *)this + 722));
      *((_QWORD *)this + 722) = 0;
    }
    else
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x100443c40  mov     [rsp+arg_10], rbx
0x100443c45  push    rsi
0x100443c46  push    rdi
0x100443c47  push    r12
0x100443c49  push    r14
0x100443c4b  push    r15
0x100443c4d  sub     rsp, 110h
0x100443c54  mov     rax, cs:__security_cookie
0x100443c5b  xor     rax, rsp
0x100443c5e  mov     [rsp+138h+var_38], rax
0x100443c66  mov     r12d, edx
0x100443c69  mov     rsi, rcx
0x100443c6c  mov     [rsp+138h+var_D0], rcx
0x100443c71  xorps   xmm0, xmm0
0x100443c74  xor     eax, eax
0x100443c76  movups  xmmword ptr [rsp+138h+Buffer], xmm0
0x100443c7e  movups  [rsp+138h+var_A8], xmm0
0x100443c86  mov     [rsp+138h+var_98], rax
0x100443c8e  mov     eax, [rcx+13A8h]
0x100443c94  cmp     eax, 4
0x100443c97  jz      short loc_100443CC0
0x100443c99  mov     r9d, eax
0x100443c9c  lea     rax, off_10045A890; "WERAPI"
0x100443ca3  mov     r9, [rax+r9*8]
0x100443ca7  lea     r8, aUploadLs; "-Upload:%ls"
0x100443cae  mov     edx, 14h; unsigned __int64
0x100443cb3  lea     rcx, [rsp+138h+Buffer]; Buffer
0x100443cbb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100443cc0  test    r12d, r12d
0x100443cc3  jz      short loc_100443D41
0x100443cc5  lea     r15, [rsi+1420h]
0x100443ccc  mov     edi, [rsi+0B4h]
0x100443cd2  not     edi
0x100443cd4  and     edi, [rsi+0B0h]
0x100443cda  mov     ebx, [rsi+0ACh]
0x100443ce0  not     ebx
0x100443ce2  and     ebx, [rsi+0A8h]
0x100443ce8  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100443cee  mov     r9, rax; struct __crt_locale_pointers *
0x100443cf1  lea     rax, [rsp+138h+Buffer]
0x100443cf9  mov     [rsp+138h+var_E8], rax
0x100443cfe  mov     rax, [rsi+40h]
0x100443d02  mov     [rsp+138h+lpProcessInformation], rax
0x100443d07  xor     r14d, r14d
0x100443d0a  mov     [rsp+138h+lpStartupInfo], r14
0x100443d0f  mov     dword ptr [rsp+138h+lpCurrentDirectory], edi
0x100443d13  mov     dword ptr [rsp+138h+lpEnvironment], ebx
0x100443d17  mov     [rsp+138h+dwCreationFlags], r12d
0x100443d1c  lea     rax, aSqldumperExe_0; "SQLDUMPER.EXE"
0x100443d23  mov     qword ptr [rsp+138h+bInheritHandles], rax
0x100443d28  lea     r8, aLsLd0XXLdSLs; "%ls %ld 0 %x:%x %ld \"%s\" %ls"
0x100443d2f  mov     edx, 104h; unsigned __int64
0x100443d34  mov     rcx, r15; Buffer
0x100443d37  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100443d3c  jmp     loc_100443E21
0x100443d41  mov     rcx, [rsi+1398h]; rguid
0x100443d48  test    rcx, rcx
0x100443d4b  jz      loc_100443DD1
0x100443d51  mov     r8d, 27h ; '''; cchMax
0x100443d57  lea     rdx, [rsp+138h+sz]; lpsz
0x100443d5f  call    cs:__imp_StringFromGUID2
0x100443d65  test    eax, eax
0x100443d67  jle     short loc_100443DD1
0x100443d69  xor     r14d, r14d
0x100443d6c  mov     [rsp+138h+var_3E], r14w
0x100443d75  lea     r15, [rsi+1420h]
0x100443d7c  lea     rbx, [rsi+18h]
0x100443d80  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100443d86  mov     r9, rax; struct __crt_locale_pointers *
0x100443d89  lea     rax, [rsp+138h+Buffer]
0x100443d91  mov     [rsp+138h+lpStartupInfo], rax
0x100443d96  lea     rax, [rsp+138h+var_86]
0x100443d9e  mov     [rsp+138h+lpCurrentDirectory], rax
0x100443da3  mov     [rsp+138h+lpEnvironment], rbx
0x100443da8  mov     eax, [rsi+78h]
0x100443dab  mov     [rsp+138h+dwCreationFlags], eax
0x100443daf  lea     rax, aSqldumperExe_0; "SQLDUMPER.EXE"
0x100443db6  mov     qword ptr [rsp+138h+bInheritHandles], rax
0x100443dbb  lea     r8, aLsLd000PDumpui; "%ls %ld 0 0:0 %p -DumpUID:%ls %ls"
0x100443dc2  mov     edx, 104h; unsigned __int64
0x100443dc7  mov     rcx, r15; Buffer
0x100443dca  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100443dcf  jmp     short loc_100443E21
0x100443dd1  lea     r15, [rsi+1420h]
0x100443dd8  lea     rbx, [rsi+18h]
0x100443ddc  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100443de2  mov     r9, rax; struct __crt_locale_pointers *
0x100443de5  lea     rax, [rsp+138h+Buffer]
0x100443ded  mov     [rsp+138h+lpCurrentDirectory], rax
0x100443df2  mov     [rsp+138h+lpEnvironment], rbx
0x100443df7  mov     eax, [rsi+78h]
0x100443dfa  mov     [rsp+138h+dwCreationFlags], eax
0x100443dfe  lea     rax, aSqldumperExe_0; "SQLDUMPER.EXE"
0x100443e05  mov     qword ptr [rsp+138h+bInheritHandles], rax
0x100443e0a  lea     r8, aLsLd000PLs; "%ls %ld 0 0:0 %p %ls"
0x100443e11  mov     edx, 104h; unsigned __int64
0x100443e16  mov     rcx, r15; Buffer
0x100443e19  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100443e1e  xor     r14d, r14d
0x100443e21  mov     ebx, eax
0x100443e23  test    eax, eax
0x100443e25  js      loc_100443FA5
0x100443e2b  lfence
0x100443e2e  lea     rbx, [rsi+1628h]
0x100443e35  mov     rcx, rbx; lpStartupInfo
0x100443e38  call    cs:__imp_GetStartupInfoW
0x100443e3e  mov     [rsi+1630h], r14
0x100443e45  mov     [rsi+1640h], r14
0x100443e4c  call    cs:__imp_GetTickCount
0x100443e52  mov     [rsp+138h+var_D4], eax
0x100443e56  lea     rdi, [rsi+1690h]
0x100443e5d  mov     rcx, [rsi+10h]
0x100443e61  add     rcx, 1810h; lpApplicationName
0x100443e68  mov     [rsp+138h+lpProcessInformation], rdi; lpProcessInformation
0x100443e6d  mov     [rsp+138h+lpStartupInfo], rbx; lpStartupInfo
0x100443e72  mov     [rsp+138h+lpCurrentDirectory], r14; lpCurrentDirectory
0x100443e77  mov     [rsp+138h+lpEnvironment], r14; lpEnvironment
0x100443e7c  mov     [rsp+138h+dwCreationFlags], 0C008010h; dwCreationFlags
0x100443e84  mov     [rsp+138h+bInheritHandles], r14d; bInheritHandles
0x100443e89  xor     r9d, r9d; lpThreadAttributes
0x100443e8c  xor     r8d, r8d; lpProcessAttributes
0x100443e8f  mov     rdx, r15; lpCommandLine
0x100443e92  call    cs:__imp_CreateProcessW
0x100443e98  test    eax, eax
0x100443e9a  jz      loc_100443F90
0x100443ea0  mov     [rsp+138h+var_D8], r14d
0x100443ea5  mov     eax, [rsp+138h+var_D4]
0x100443ea9  mov     [rsp+138h+var_D4], eax
0x100443ead  nop     dword ptr [rax]
0x100443eb0  mov     edx, 64h ; 'd'; dwMilliseconds
0x100443eb5  mov     rcx, [rdi]; hHandle
0x100443eb8  call    cs:__imp_WaitForSingleObject
0x100443ebe  mov     ebx, eax
0x100443ec0  cmp     eax, 102h
0x100443ec5  jnz     short loc_100443EE6
0x100443ec7  cmp     dword ptr [rsi+1400h], 0FFFFFFFFh
0x100443ece  jz      short loc_100443EE4
0x100443ed0  call    cs:__imp_GetTickCount
0x100443ed6  mov     ecx, [rsp+138h+var_D4]
0x100443eda  sub     eax, ecx
0x100443edc  cmp     eax, [rsi+1400h]
0x100443ee2  jnb     short loc_100443EE6
0x100443ee4  jmp     short loc_100443EB0
0x100443ee6  lfence
0x100443ee9  mov     eax, r14d
0x100443eec  cmp     ebx, 102h
0x100443ef2  setz    al
0x100443ef5  mov     [rsi+140Ch], eax
0x100443efb  mov     dword ptr [rsi+1410h], 1
0x100443f05  lea     rdx, [rsi+1404h]; lpExitCode
0x100443f0c  mov     rcx, [rdi]; hProcess
0x100443f0f  call    cs:__imp_GetExitCodeProcess
0x100443f15  test    eax, eax
0x100443f17  jz      short loc_100443F30
0x100443f19  cmp     dword ptr [rsi+1404h], 103h
0x100443f23  jz      short loc_100443F30
0x100443f25  mov     qword ptr [rsi+1408h], 1
0x100443f30  jmp     short loc_100443F5F
0x100443f32  mov     [rsp+138h+var_D8], eax
0x100443f36  mov     eax, [rsp+138h+var_D8]
0x100443f3a  cmp     eax, 0C00000FDh
0x100443f3f  jnz     short loc_100443F47
0x100443f41  call    cs:__imp__resetstkoflw
0x100443f47  mov     eax, [rsp+138h+var_D8]
0x100443f4b  test    eax, eax
0x100443f4d  js      short loc_100443F57
0x100443f4f  mov     [rsp+138h+var_D8], 80004005h
0x100443f57  xor     r14d, r14d
0x100443f5a  mov     rsi, [rsp+138h+var_D0]
0x100443f5f  lfence
0x100443f62  mov     ebx, [rsp+138h+var_D8]
0x100443f66  mov     rcx, [rsi+1698h]; hObject
0x100443f6d  call    cs:__imp_CloseHandle
0x100443f73  mov     [rsi+1698h], r14
0x100443f7a  mov     rcx, [rsi+1690h]; hObject
0x100443f81  call    cs:__imp_CloseHandle
0x100443f87  mov     [rsi+1690h], r14
0x100443f8e  jmp     short loc_100443FA5
0x100443f90  call    cs:__imp_GetLastError
0x100443f96  mov     ebx, eax
0x100443f98  test    eax, eax
0x100443f9a  jle     short loc_100443FA5
0x100443f9c  movzx   ebx, ax
0x100443f9f  or      ebx, 80070000h
0x100443fa5  mov     eax, ebx
0x100443fa7  mov     rcx, [rsp+138h+var_38]
0x100443faf  xor     rcx, rsp; StackCookie
0x100443fb2  call    __security_check_cookie
0x100443fb7  mov     rbx, [rsp+138h+arg_10]
0x100443fbf  add     rsp, 110h
0x100443fc6  pop     r15
0x100443fc8  pop     r14
0x100443fca  pop     r12
0x100443fcc  pop     rdi
0x100443fcd  pop     rsi
0x100443fce  retn
0x100456770  push    rbp
0x100456772  sub     rsp, 60h
0x100456776  mov     rbp, rdx
0x100456779  mov     [rbp+70h], rcx
0x10045677d  mov     [rbp+78h], rcx
0x100456781  mov     eax, 1
0x100456786  add     rsp, 60h
0x10045678a  pop     rbp
0x10045678b  retn
```
