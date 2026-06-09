# CheckFileVersion(wchar_t const * const)

- ea: `0x10040e370`
- end: `0x10040e6c0`
- name: `?CheckFileVersion@@YAXQEB_W@Z`
- size: `848`
- prototype: `void __fastcall(const wchar_t *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x100416770`

## callees

- `0x100401580`
- `0x100401aa0`
- `0x100402ec0`
- `0x10040e370`
- `0x10041eac0`
- `0x1004403d0`
- `0x10044aad0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x10040e3c6`
- `KERNEL32!GetModuleFileNameW` at `0x10040e3c6`
- `KERNEL32!GetLastError` at `0x10040e3db`
- `KERNEL32!GetLastError` at `0x10040e3db`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040e48a`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040e48a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040e693`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040e693`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040e54f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040e54f`
- `sqldk!SystemThread_TlsOffset` at `0x10040e534`
- `sqldk!SystemThread_TlsIndex` at `0x10040e52b`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040e51c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040e5be`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040e609`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040e689`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040e51c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040e5be`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040e609`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040e689`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040e441`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040e490`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040e441`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040e490`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040e3ee`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040e3ee`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10040e578`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10040e578`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x10040e43b`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x10040e43b`
- `VERSION!VerQueryValueW` at `0x10040e5e2`
- `VERSION!VerQueryValueW` at `0x10040e5e2`
- `VERSION!GetFileVersionInfoW` at `0x10040e597`
- `VERSION!GetFileVersionInfoW` at `0x10040e597`
- `VERSION!GetFileVersionInfoSizeW` at `0x10040e4e5`
- `VERSION!GetFileVersionInfoSizeW` at `0x10040e4e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CheckFileVersion(const wchar_t *a1)
{
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  struct __crt_locale_pointers *DefaultLocale; // rax
  signed int v5; // eax
  signed int v6; // ebx
  struct __crt_locale_pointers *v7; // rax
  int v8; // eax
  char *v9; // rcx
  DWORD FileVersionInfoSizeW; // eax
  unsigned __int64 v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rdx
  void *v14; // rbx
  size_t DirCount; // [rsp+20h] [rbp-E0h]
  wchar_t *v16; // [rsp+28h] [rbp-D8h]
  size_t FilenameCount; // [rsp+30h] [rbp-D0h]
  wchar_t *Ext; // [rsp+38h] [rbp-C8h]
  size_t ExtCount; // [rsp+40h] [rbp-C0h]
  DWORD dwHandle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int puLen; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID lpBuffer[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[4096]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Drive[8]; // [rsp+1070h] [rbp+F70h] BYREF
  WCHAR Filename[264]; // [rsp+1080h] [rbp+F80h] BYREF
  WCHAR tstrFilename[264]; // [rsp+1290h] [rbp+1190h] BYREF
  wchar_t Dir[264]; // [rsp+14A0h] [rbp+13A0h] BYREF
  char Buffer[512]; // [rsp+16B0h] [rbp+15B0h] BYREF

  lpBuffer[1] = (LPVOID)-2LL;
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  Filename[259] = 0;
  if ( !ModuleFileNameW )
  {
    LastError = GetLastError();
    GetOSErrString(LastError, (struct ErrorStringHolder *)v23, 0, 0);
    scierrlog(0x283Eu, v23);
  }
  _wsplitpath_s(Filename, Drive, 4u, Dir, 0x101u, 0, 0, 0, 0);
  DefaultLocale = GetDefaultLocale();
  v5 = StringCchPrintf_lW(tstrFilename, 0x105u, L"%s%s%s", DefaultLocale, Drive, Dir, a1);
  v6 = v5;
  if ( v5 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v5);
    v7 = GetDefaultLocale();
    LODWORD(v16) = v6;
    v8 = StringCchPrintf_lA(Buffer, 0x200u, "%hs (HRESULT 0x%x)", v7, "String Format Error", v16);
    v9 = "String Format Error";
    if ( v8 >= 0 )
      v9 = Buffer;
    FailAndExit(v9);
  }
  dwHandle = 0;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(tstrFilename, &dwHandle);
  v11 = FileVersionInfoSizeW;
  if ( !FileVersionInfoSizeW )
  {
    scierrlog(0x19A1u, a1, Drive, Dir);
    SQLExit(292, 6561, 1066);
  }
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  v14 = operator new[](v11, *(struct IMemObj **)(v13 + 1000), "sql\\ntdbms\\ksource\\serverma.cpp", 1181, 6u);
  lpBuffer[2] = v14;
  if ( !GetFileVersionInfoW(tstrFilename, dwHandle, v11, v14) )
  {
    scierrlog(0x284Du, a1);
    SQLExit(383, 10317, 1066);
  }
  lpBuffer[0] = 0;
  puLen = 0;
  if ( !VerQueryValueW(v14, L"\\", lpBuffer, &puLen) )
  {
    scierrlog(0x284Du, a1);
    SQLExit(293, 10317, 1066);
  }
  if ( *((_DWORD *)lpBuffer[0] + 4) != 0x100000 || *((_WORD *)lpBuffer[0] + 11) != 1000 )
  {
    LODWORD(ExtCount) = *((unsigned __int16 *)lpBuffer[0] + 11);
    LODWORD(Ext) = (unsigned __int16)*((_DWORD *)lpBuffer[0] + 4);
    LODWORD(FilenameCount) = HIWORD(*((_DWORD *)lpBuffer[0] + 4));
    LODWORD(DirCount) = 1000;
    scierrlog(0x19A2u, Filename, 16, 0, DirCount, tstrFilename, FilenameCount, Ext, ExtCount);
    SQLExit(294, 10317, 1066);
  }
  operator delete[](v14);
}

```

## disassembly

```asm
0x10040e370  push    rbp
0x10040e372  push    rdi
0x10040e373  push    r14
0x10040e375  lea     rbp, [rsp-17C0h]
0x10040e37d  mov     eax, 18C0h
0x10040e382  call    _alloca_probe
0x10040e387  sub     rsp, rax
0x10040e38a  mov     [rsp+18D0h+var_1870], 0FFFFFFFFFFFFFFFEh
0x10040e393  mov     [rsp+18D0h+arg_8], rbx
0x10040e39b  mov     [rsp+18D0h+arg_10], rsi
0x10040e3a3  mov     rax, cs:__security_cookie
0x10040e3aa  xor     rax, rsp
0x10040e3ad  mov     [rbp+17D0h+var_20], rax
0x10040e3b4  mov     rdi, rcx
0x10040e3b7  mov     r8d, 104h; nSize
0x10040e3bd  lea     rdx, [rbp+17D0h+Filename]; lpFilename
0x10040e3c4  xor     ecx, ecx; hModule
0x10040e3c6  call    cs:__imp_GetModuleFileNameW
0x10040e3cc  xor     r14d, r14d
0x10040e3cf  mov     [rbp+17D0h+var_64A], r14w
0x10040e3d7  test    eax, eax
0x10040e3d9  jnz     short loc_10040E403
0x10040e3db  call    cs:__imp_GetLastError
0x10040e3e1  mov     ecx, eax
0x10040e3e3  xor     r9d, r9d
0x10040e3e6  xor     r8d, r8d
0x10040e3e9  lea     rdx, [rsp+18D0h+var_1860]
0x10040e3ee  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040e3f4  lea     rdx, [rsp+18D0h+var_1860]
0x10040e3f9  mov     ecx, 283Eh; unsigned int
0x10040e3fe  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040e403  mov     [rsp+18D0h+ExtCount], r14; ExtCount
0x10040e408  mov     [rsp+18D0h+Ext], r14; Ext
0x10040e40d  mov     [rsp+18D0h+FilenameCount], r14; FilenameCount
0x10040e412  mov     [rsp+18D0h+var_18A8], r14; Filename
0x10040e417  mov     [rsp+18D0h+DirCount], 101h; DirCount
0x10040e420  lea     r9, [rbp+17D0h+Dir]; Dir
0x10040e427  mov     r8d, 4; DriveCount
0x10040e42d  lea     rdx, [rbp+17D0h+Drive]; Drive
0x10040e434  lea     rcx, [rbp+17D0h+Filename]; FullPath
0x10040e43b  call    cs:__imp__wsplitpath_s
0x10040e441  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10040e447  mov     r9, rax; struct __crt_locale_pointers *
0x10040e44a  mov     [rsp+18D0h+FilenameCount], rdi
0x10040e44f  lea     rax, [rbp+17D0h+Dir]
0x10040e456  mov     [rsp+18D0h+var_18A8], rax
0x10040e45b  lea     rax, [rbp+17D0h+Drive]
0x10040e462  mov     [rsp+18D0h+DirCount], rax
0x10040e467  lea     r8, aSSS; "%s%s%s"
0x10040e46e  mov     edx, 105h; unsigned __int64
0x10040e473  lea     rcx, [rbp+17D0h+tstrFilename]; Buffer
0x10040e47a  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x10040e47f  mov     ebx, eax
0x10040e481  test    eax, eax
0x10040e483  jns     short loc_10040E4D4
0x10040e485  lfence
0x10040e488  mov     ecx, eax
0x10040e48a  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10040e490  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10040e496  mov     r9, rax; struct __crt_locale_pointers *
0x10040e499  mov     dword ptr [rsp+18D0h+var_18A8], ebx
0x10040e49d  lea     rbx, aStringFormatEr; "String Format Error"
0x10040e4a4  mov     [rsp+18D0h+DirCount], rbx
0x10040e4a9  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10040e4b0  mov     edx, 200h; unsigned __int64
0x10040e4b5  lea     rcx, [rbp+17D0h+Buffer]; Buffer
0x10040e4bc  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10040e4c1  test    eax, eax
0x10040e4c3  mov     rcx, rbx
0x10040e4c6  js      short loc_10040E4CF
0x10040e4c8  lea     rcx, [rbp+17D0h+Buffer]; char *
0x10040e4cf  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10040e4d4  mov     [rsp+18D0h+dwHandle], r14d
0x10040e4d9  lea     rdx, [rsp+18D0h+dwHandle]; lpdwHandle
0x10040e4de  lea     rcx, [rbp+17D0h+tstrFilename]; lptstrFilename
0x10040e4e5  call    cs:__imp_GetFileVersionInfoSizeW
0x10040e4eb  mov     esi, eax
0x10040e4ed  test    eax, eax
0x10040e4ef  jnz     short loc_10040E522
0x10040e4f1  lea     r9, [rbp+17D0h+Dir]
0x10040e4f8  lea     r8, [rbp+17D0h+Drive]
0x10040e4ff  mov     rdx, rdi
0x10040e502  mov     ecx, 19A1h; unsigned int
0x10040e507  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040e50c  mov     edx, 19A1h
0x10040e511  mov     ecx, 124h
0x10040e516  mov     r8d, 42Ah
0x10040e51c  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040e522  mov     rdx, gs:58h
0x10040e52b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040e532  mov     ecx, [rax]
0x10040e534  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040e53b  mov     ebx, [rax]
0x10040e53d  add     rbx, [rdx+rcx*8]
0x10040e541  mov     rdx, [rbx+100h]
0x10040e548  test    rdx, rdx
0x10040e54b  jnz     short loc_10040E55C
0x10040e54d  xor     ecx, ecx
0x10040e54f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040e555  mov     rdx, [rbx+100h]
0x10040e55c  mov     rcx, rsi
0x10040e55f  mov     byte ptr [rsp+18D0h+DirCount], 6
0x10040e564  mov     r9d, 49Dh
0x10040e56a  lea     r8, aSqlNtdbmsKsour_1; "sql\\ntdbms\\ksource\\serverma.cpp"
0x10040e571  mov     rdx, [rdx+3E8h]
0x10040e578  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10040e57e  mov     rbx, rax
0x10040e581  mov     [rsp+18D0h+var_1868], rax
0x10040e586  mov     r9, rax; lpData
0x10040e589  mov     r8d, esi; dwLen
0x10040e58c  mov     edx, [rsp+18D0h+dwHandle]; dwHandle
0x10040e590  lea     rcx, [rbp+17D0h+tstrFilename]; lptstrFilename
0x10040e597  call    cs:__imp_GetFileVersionInfoW
0x10040e59d  test    eax, eax
0x10040e59f  jnz     short loc_10040E5C4
0x10040e5a1  mov     rdx, rdi
0x10040e5a4  mov     ecx, 284Dh; unsigned int
0x10040e5a9  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040e5ae  mov     edx, 284Dh
0x10040e5b3  mov     ecx, 17Fh
0x10040e5b8  mov     r8d, 42Ah
0x10040e5be  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040e5c4  mov     [rsp+18D0h+lpBuffer], r14
0x10040e5c9  mov     [rsp+18D0h+puLen], r14d
0x10040e5ce  lea     r9, [rsp+18D0h+puLen]; puLen
0x10040e5d3  lea     r8, [rsp+18D0h+lpBuffer]; lplpBuffer
0x10040e5d8  lea     rdx, SubBlock; "\\"
0x10040e5df  mov     rcx, rbx; pBlock
0x10040e5e2  call    cs:__imp_VerQueryValueW
0x10040e5e8  test    eax, eax
0x10040e5ea  jnz     short loc_10040E60F
0x10040e5ec  mov     rdx, rdi
0x10040e5ef  mov     ecx, 284Dh; unsigned int
0x10040e5f4  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040e5f9  mov     edx, 284Dh
0x10040e5fe  mov     ecx, 125h
0x10040e603  mov     r8d, 42Ah
0x10040e609  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040e60f  mov     r10, [rsp+18D0h+lpBuffer]
0x10040e614  mov     eax, [r10+10h]
0x10040e618  mov     r9d, eax
0x10040e61b  shr     r9d, 10h
0x10040e61f  movzx   ecx, ax
0x10040e622  mov     edx, 3E8h
0x10040e627  mov     r8d, 10h
0x10040e62d  cmp     r8w, r9w
0x10040e631  jnz     short loc_10040E640
0x10040e633  cmp     r14w, ax
0x10040e637  jnz     short loc_10040E640
0x10040e639  cmp     dx, [r10+16h]
0x10040e63e  jz      short loc_10040E690
0x10040e640  movzx   eax, word ptr [r10+16h]
0x10040e645  movzx   ecx, cx
0x10040e648  mov     dword ptr [rsp+18D0h+ExtCount], eax
0x10040e64c  mov     dword ptr [rsp+18D0h+Ext], ecx
0x10040e650  mov     dword ptr [rsp+18D0h+FilenameCount], r9d
0x10040e655  lea     rax, [rbp+17D0h+tstrFilename]
0x10040e65c  mov     [rsp+18D0h+var_18A8], rax
0x10040e661  mov     dword ptr [rsp+18D0h+DirCount], edx
0x10040e665  xor     r9d, r9d
0x10040e668  lea     rdx, [rbp+17D0h+Filename]
0x10040e66f  mov     ecx, 19A2h; unsigned int
0x10040e674  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040e679  mov     edx, 284Dh
0x10040e67e  mov     ecx, 126h
0x10040e683  mov     r8d, 42Ah
0x10040e689  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040e68f  nop
0x10040e690  mov     rcx, rbx
0x10040e693  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10040e699  mov     rcx, [rbp+17D0h+var_20]
0x10040e6a0  xor     rcx, rsp; StackCookie
0x10040e6a3  call    __security_check_cookie
0x10040e6a8  lea     r11, [rsp+18D0h+var_10]
0x10040e6b0  mov     rbx, [r11+28h]
0x10040e6b4  mov     rsi, [r11+30h]
0x10040e6b8  mov     rsp, r11
0x10040e6bb  pop     r14
0x10040e6bd  pop     rdi
0x10040e6be  pop     rbp
0x10040e6bf  retn
```
