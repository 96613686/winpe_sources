# DoBootActivities(void)

- ea: `0x140005e30`
- end: `0x140005f8f`
- name: `?DoBootActivities@@YAJXZ`
- size: `351`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000e49c`

## callees

- `0x140005e30`
- `0x140008c40`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005eb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005eb5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140005e49`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140005e49`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140005f28`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140005f7c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140005f28`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140005f7c`

## string_xrefs

- `0x140005e42`: `offdmpsvc.dll`
- `0x140005e7d`: `LoadLibraryExW for offdmpsvc failed`

## pseudocode

```c
__int64 DoBootActivities(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  signed int v2; // eax
  bool v3; // sf
  __int64 (*ProcAddress)(void); // rax
  signed int LastError; // eax
  bool v6; // sf
  __int64 v7; // rdx
  signed int v8; // eax
  signed int v9; // ebx
  wil::details *v11; // [rsp+20h] [rbp-18h]
  wil::details *v12; // [rsp+20h] [rbp-18h]
  const char *v13; // [rsp+28h] [rbp-10h]
  const char *v14; // [rsp+30h] [rbp-8h]
  const char *v15; // [rsp+30h] [rbp-8h]
  wil::details::in1diag4 *retaddr; // [rsp+38h] [rbp+0h]

  Library = LoadLibraryExW(L"offdmpsvc.dll", 0, 0x800u);
  v1 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CheckAndSubmitOfflineCrash");
    if ( ProcAddress )
    {
      LastError = ProcAddress();
      if ( LastError >= 0 )
      {
        FreeLibrary(v1);
        return 0;
      }
      v13 = "CheckAndSubmitOfflineCrash failed";
      v7 = 725;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v6 = LastError < 0;
      }
      if ( !v6 )
        LastError = -2147467259;
      v13 = "GetProcAddress for CheckAndSubmitOfflineCrash failed";
      v7 = 718;
    }
    LODWORD(v11) = LastError;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "CollectOfflineCrash",
      v11,
      (int)v13,
      v14);
    FreeLibrary(v1);
  }
  else
  {
    v2 = GetLastError();
    v3 = v2 < 0;
    if ( v2 > 0 )
    {
      v2 = (unsigned __int16)v2 | 0x80070000;
      v3 = v2 < 0;
    }
    if ( !v3 )
      v2 = -2147467259;
    LODWORD(v11) = v2;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x2C6,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "CollectOfflineCrash",
      v11,
      (int)"LoadLibraryExW for offdmpsvc failed",
      v14);
  }
  v8 = GetLastError();
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
    v9 = -2147467259;
  LODWORD(v12) = v9;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x2F2,
    (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
    "DoBootActivities",
    v12,
    (int)"CollectOfflineCrash failed",
    v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140005e30  mov     [rsp+arg_8], rbx
0x140005e35  push    rsi; char *
0x140005e36  sub     rsp, 30h
0x140005e3a  xor     edx, edx; hFile
0x140005e3c  mov     r8d, 800h; dwFlags
0x140005e42  lea     rcx, LibFileName; "offdmpsvc.dll"
0x140005e49  call    cs:__imp_LoadLibraryExW
0x140005e4f  mov     rbx, rax
0x140005e52  mov     [rsp+38h+arg_0], rax
0x140005e57  mov     esi, 80004005h
0x140005e5c  test    rax, rax
0x140005e5f  jnz     short loc_140005EAB
0x140005e61  call    cs:__imp_GetLastError
0x140005e67  test    eax, eax
0x140005e69  jle     short loc_140005E75
0x140005e6b  movzx   eax, ax
0x140005e6e  or      eax, 80070000h
0x140005e73  test    eax, eax
0x140005e75  cmovns  eax, esi
0x140005e78  mov     rcx, [rsp+38h]; this
0x140005e7d  lea     rdx, aLoadlibraryexw; "LoadLibraryExW for offdmpsvc failed"
0x140005e84  mov     qword ptr [rsp+38h+var_10], rdx; int
0x140005e89  mov     dword ptr [rsp+38h+var_18], eax; wil::details *
0x140005e8d  lea     r9, aCollectoffline; "CollectOfflineCrash"
0x140005e94  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005e9b  mov     edx, 2C6h; void *
0x140005ea0  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005ea5  nop
0x140005ea6  jmp     loc_140005F2E
0x140005eab  lea     rdx, aCheckandsubmit_0; "CheckAndSubmitOfflineCrash"
0x140005eb2  mov     rcx, rbx; hModule
0x140005eb5  call    cs:__imp_GetProcAddress
0x140005ebb  test    rax, rax
0x140005ebe  jnz     short loc_140005EEA
0x140005ec0  call    cs:__imp_GetLastError
0x140005ec6  test    eax, eax
0x140005ec8  jle     short loc_140005ED4
0x140005eca  movzx   eax, ax
0x140005ecd  or      eax, 80070000h
0x140005ed2  test    eax, eax
0x140005ed4  cmovns  eax, esi
0x140005ed7  lea     rdx, aGetprocaddress; "GetProcAddress for CheckAndSubmitOfflin"...
0x140005ede  mov     qword ptr [rsp+38h+var_10], rdx
0x140005ee3  mov     edx, 2CEh
0x140005ee8  jmp     short loc_140005F08
0x140005eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eef  test    eax, eax
0x140005ef1  jns     loc_140005F79
0x140005ef7  lea     rdx, aCheckandsubmit; "CheckAndSubmitOfflineCrash failed"
0x140005efe  mov     qword ptr [rsp+38h+var_10], rdx; int
0x140005f03  mov     edx, 2D5h; void *
0x140005f08  mov     dword ptr [rsp+38h+var_18], eax; wil::details *
0x140005f0c  lea     r9, aCollectoffline; "CollectOfflineCrash"
0x140005f13  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005f1a  mov     rcx, [rsp+38h]; this
0x140005f1f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005f24  nop
0x140005f25  mov     rcx, rbx; hLibModule
0x140005f28  call    cs:__imp_FreeLibrary
0x140005f2e  call    cs:__imp_GetLastError
0x140005f34  mov     ebx, eax
0x140005f36  test    eax, eax
0x140005f38  jle     short loc_140005F43
0x140005f3a  movzx   ebx, ax
0x140005f3d  or      ebx, 80070000h
0x140005f43  test    ebx, ebx
0x140005f45  cmovns  ebx, esi
0x140005f48  mov     rcx, [rsp+38h]; this
0x140005f4d  lea     rax, aCollectoffline_0; "CollectOfflineCrash failed"
0x140005f54  mov     qword ptr [rsp+38h+var_10], rax; int
0x140005f59  mov     dword ptr [rsp+38h+var_18], ebx; wil::details *
0x140005f5d  lea     r9, aDobootactiviti; "DoBootActivities"
0x140005f64  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005f6b  mov     edx, 2F2h; void *
0x140005f70  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005f75  mov     eax, ebx
0x140005f77  jmp     short loc_140005F84
0x140005f79  mov     rcx, rbx; hLibModule
0x140005f7c  call    cs:__imp_FreeLibrary
0x140005f82  xor     eax, eax
0x140005f84  mov     rbx, [rsp+38h+arg_8]
0x140005f89  add     rsp, 30h
0x140005f8d  pop     rsi
0x140005f8e  retn
```
