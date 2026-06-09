# _unnamed_type_WinDiag_::Initialize(void)

- ea: `0x180020ba4`
- end: `0x180020dbd`
- name: `?Initialize@_unnamed_type_WinDiag_@@QEAAJXZ`
- size: `537`
- prototype: `__int64 __fastcall(_unnamed_type_WinDiag_ *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000b380`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x180009024`
- `0x180009044`
- `0x180009478`
- `0x180020ba4`
- `0x180024748`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180020be1`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180020be1`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180020c3d`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180020d52`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180020d90`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180020c3d`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180020d52`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180020d90`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020d3f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020d7d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020d3f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020d7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020ca9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020ccc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020cef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020ca9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020ccc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020cef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020c06`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020c06`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180020c89`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180020c89`

## string_xrefs

- `0x180020c4a`: `\windiag.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _unnamed_type_WinDiag_::Initialize(_unnamed_type_WinDiag_ *this)
{
  char *v1; // rbx
  const char *v2; // r9
  __int64 v3; // rdx
  unsigned int LastError; // edi
  int v6; // eax
  HMODULE LibraryW; // rax
  HMODULE v8; // rdi
  const char *v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  unsigned int v12; // esi
  char *v13; // rsi
  HMODULE v14; // rcx
  int Buffer[156]; // [rsp+20h] [rbp-288h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v1 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes2D>::GetImpl'::`2'::impl) )
    v1 = (char *)HeapCreate(0, 0, 0);
  memset_0(Buffer, 0, 0x26Cu);
  if ( GetSystemDirectoryW((LPWSTR)Buffer, 0x104u) - 1 > 0x103 )
  {
    v3 = 115;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v3,
                  (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
                  v2);
LABEL_6:
    if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      HeapDestroy(v1);
    return LastError;
  }
  v6 = StringCchCatW((unsigned __int16 *)Buffer, 0x136u, L"\\windiag.dll");
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)(unsigned int)v6,
      Buffer[0]);
    goto LABEL_6;
  }
  LibraryW = LoadLibraryW((LPCWSTR)Buffer);
  v8 = LibraryW;
  if ( !LibraryW )
  {
    v3 = 120;
    goto LABEL_5;
  }
  WinDiag = (__int64)GetProcAddress(LibraryW, "WinDiagnosticsRequest");
  if ( WinDiag )
  {
    qword_180034DD8 = (__int64)GetProcAddress(v8, "WinDiagnosticsResume");
    if ( qword_180034DD8 )
    {
      qword_180034DE0 = (__int64)GetProcAddress(v8, "WinDiagnosticsFree");
      if ( qword_180034DE0 )
        goto LABEL_23;
      v10 = 154;
    }
    else
    {
      v10 = 153;
    }
  }
  else
  {
    v10 = 152;
  }
  v11 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)v10,
          (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
          v9);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)(unsigned int)v11,
      Buffer[0]);
    FreeLibrary(v8);
    if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      HeapDestroy(v1);
    return v12;
  }
LABEL_23:
  v13 = (char *)hHeap;
  hHeap = v1;
  v14 = hLibModule;
  hLibModule = v8;
  if ( v14 )
    FreeLibrary(v14);
  if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    HeapDestroy(v13);
  return 0;
}

```

## disassembly

```asm
0x180020ba4  mov     [rsp+arg_0], rbx
0x180020ba9  mov     [rsp+arg_8], rsi
0x180020bae  push    rdi
0x180020baf  sub     rsp, 2A0h
0x180020bb6  mov     rax, cs:__security_cookie
0x180020bbd  xor     rax, rsp
0x180020bc0  mov     [rsp+2A8h+var_18], rax
0x180020bc8  xor     ebx, ebx
0x180020bca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes2D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes2D>::GetImpl(void)'::`2'::impl
0x180020bd1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::__private_IsEnabled(void)
0x180020bd6  test    al, al
0x180020bd8  jz      short loc_180020BEA
0x180020bda  xor     r8d, r8d; dwMaximumSize
0x180020bdd  xor     edx, edx; dwInitialSize
0x180020bdf  xor     ecx, ecx; flOptions
0x180020be1  call    cs:__imp_HeapCreate
0x180020be7  mov     rbx, rax
0x180020bea  xor     edx, edx; Val
0x180020bec  mov     r8d, 26Ch; Size
0x180020bf2  lea     rcx, [rsp+2A8h+Buffer]; void *
0x180020bf7  call    memset_0
0x180020bfc  mov     edx, 104h; uSize
0x180020c01  lea     rcx, [rsp+2A8h+Buffer]; lpBuffer
0x180020c06  call    cs:__imp_GetSystemDirectoryW
0x180020c0c  dec     eax
0x180020c0e  cmp     eax, 103h
0x180020c13  jbe     short loc_180020C4A
0x180020c15  mov     edx, 73h ; 's'; void *
0x180020c1a  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180020c21  mov     rcx, [rsp+2A8h]; this
0x180020c29  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020c2e  mov     edi, eax
0x180020c30  lea     rcx, [rbx-1]
0x180020c34  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180020c38  ja      short loc_180020C43
0x180020c3a  mov     rcx, rbx; hHeap
0x180020c3d  call    cs:__imp_HeapDestroy
0x180020c43  mov     eax, edi
0x180020c45  jmp     loc_180020D98
0x180020c4a  lea     r8, aWindiagDll; "\\windiag.dll"
0x180020c51  mov     edx, 136h; unsigned __int64
0x180020c56  lea     rcx, [rsp+2A8h+Buffer]; unsigned __int16 *
0x180020c5b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020c60  mov     edi, eax
0x180020c62  test    eax, eax
0x180020c64  jns     short loc_180020C84
0x180020c66  mov     rcx, [rsp+2A8h]; this
0x180020c6e  mov     r9d, eax; char *
0x180020c71  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180020c78  mov     edx, 74h ; 't'; void *
0x180020c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c82  jmp     short loc_180020C30
0x180020c84  lea     rcx, [rsp+2A8h+Buffer]; lpLibFileName
0x180020c89  call    cs:__imp_LoadLibraryW
0x180020c8f  mov     rdi, rax
0x180020c92  test    rax, rax
0x180020c95  jnz     short loc_180020C9F
0x180020c97  lea     edx, [rax+78h]
0x180020c9a  jmp     loc_180020C1A
0x180020c9f  lea     rdx, aWindiagnostics_1; "WinDiagnosticsRequest"
0x180020ca6  mov     rcx, rdi; hModule
0x180020ca9  call    cs:__imp_GetProcAddress
0x180020caf  mov     cs:?WinDiag@@3U_unnamed_type_WinDiag_@@A, rax; _unnamed_type_WinDiag_ WinDiag
0x180020cb6  test    rax, rax
0x180020cb9  jnz     short loc_180020CC2
0x180020cbb  mov     edx, 98h
0x180020cc0  jmp     short loc_180020D06
0x180020cc2  lea     rdx, aWindiagnostics_0; "WinDiagnosticsResume"
0x180020cc9  mov     rcx, rdi; hModule
0x180020ccc  call    cs:__imp_GetProcAddress
0x180020cd2  mov     cs:qword_180034DD8, rax
0x180020cd9  test    rax, rax
0x180020cdc  jnz     short loc_180020CE5
0x180020cde  mov     edx, 99h
0x180020ce3  jmp     short loc_180020D06
0x180020ce5  lea     rdx, aWindiagnostics; "WinDiagnosticsFree"
0x180020cec  mov     rcx, rdi; hModule
0x180020cef  call    cs:__imp_GetProcAddress
0x180020cf5  mov     cs:qword_180034DE0, rax
0x180020cfc  test    rax, rax
0x180020cff  jnz     short loc_180020D5C
0x180020d01  mov     edx, 9Ah; void *
0x180020d06  mov     rcx, [rsp+2A8h]; this
0x180020d0e  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180020d15  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020d1a  mov     esi, eax
0x180020d1c  test    eax, eax
0x180020d1e  jns     short loc_180020D5C
0x180020d20  mov     rcx, [rsp+2A8h]; this
0x180020d28  mov     r9d, eax; char *
0x180020d2b  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180020d32  mov     edx, 79h ; 'y'; void *
0x180020d37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d3c  mov     rcx, rdi; hLibModule
0x180020d3f  call    cs:__imp_FreeLibrary
0x180020d45  lea     rcx, [rbx-1]
0x180020d49  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180020d4d  ja      short loc_180020D58
0x180020d4f  mov     rcx, rbx; hHeap
0x180020d52  call    cs:__imp_HeapDestroy
0x180020d58  mov     eax, esi
0x180020d5a  jmp     short loc_180020D98
0x180020d5c  mov     rsi, cs:hHeap
0x180020d63  mov     cs:hHeap, rbx
0x180020d6a  mov     rcx, cs:hLibModule; hLibModule
0x180020d71  mov     cs:hLibModule, rdi
0x180020d78  test    rcx, rcx
0x180020d7b  jz      short loc_180020D83
0x180020d7d  call    cs:__imp_FreeLibrary
0x180020d83  lea     rax, [rsi-1]
0x180020d87  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020d8b  ja      short loc_180020D96
0x180020d8d  mov     rcx, rsi; hHeap
0x180020d90  call    cs:__imp_HeapDestroy
0x180020d96  xor     eax, eax
0x180020d98  mov     rcx, [rsp+2A8h+var_18]
0x180020da0  xor     rcx, rsp; StackCookie
0x180020da3  call    __security_check_cookie
0x180020da8  lea     r11, [rsp+2A8h+var_8]
0x180020db0  mov     rbx, [r11+10h]
0x180020db4  mov     rsi, [r11+18h]
0x180020db8  mov     rsp, r11
0x180020dbb  pop     rdi
0x180020dbc  retn
```
