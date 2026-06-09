# GeneralizeForImaging(void)

- ea: `0x18000c0b0`
- end: `0x18000c1d0`
- name: `?GeneralizeForImaging@@YAKXZ`
- size: `288`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800026d0`
- `0x180002adc`
- `0x1800081ec`
- `0x180008b08`
- `0x1800096cc`
- `0x18000a1dc`
- `0x18000c0b0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c142`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c142`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c161`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c161`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c11b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c11b`

## string_xrefs

- `0x18000c1ae`: `onecore\enduser\windowsupdate\muse\orchestrator\core\usosvc\servicedll\safeimaging.cpp`
- `0x18000c1bf`: `onecore\enduser\windowsupdate\muse\orchestrator\core\usosvc\servicedll\safeimaging.cpp`

## pseudocode

```c
__int64 GeneralizeForImaging(void)
{
  uus::Session *v0; // rax
  void (__fastcall ***v1)(_QWORD, __int64); // rdi
  const WCHAR *v2; // rcx
  HMODULE Library; // rbx
  const char *v4; // r9
  FARPROC ProcAddress; // rax
  const char *v6; // r9
  unsigned int v7; // esi
  __int64 result; // rax
  LPCWSTR lpLibFileName[4]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    v0 = (uus::Session *)operator new(0x10u);
    v1 = (void (__fastcall ***)(_QWORD, __int64))uus::Session::Session(v0, L"usosvc.UsoSvcImpl");
    uus::Session::GetFullPath(v1, lpLibFileName);
    v2 = (const WCHAR *)lpLibFileName;
    if ( lpLibFileName[3] > (LPCWSTR)7 )
      v2 = lpLibFileName[0];
    Library = LoadLibraryExW(v2, 0, 0x800u);
    if ( !Library )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x11,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\core\\usosvc\\servicedll\\safeimaging.cpp",
        v4);
    ProcAddress = GetProcAddress(Library, "GeneralizeForImaging");
    if ( !ProcAddress )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x14,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\core\\usosvc\\servicedll\\safeimaging.cpp",
        v6);
    v7 = ((__int64 (__fastcall *)(wil::details::in1diag3 *))ProcAddress)(retaddr);
    FreeLibrary(Library);
    std::wstring::~wstring(lpLibFileName);
    if ( v1 )
      (**v1)(v1, 1);
    result = v7;
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c0b0  mov     [rsp+arg_0], rbx
0x18000c0b5  mov     [rsp+arg_8], rsi
0x18000c0ba  push    rdi
0x18000c0bb  sub     rsp, 60h
0x18000c0bf  mov     rax, cs:__security_cookie
0x18000c0c6  xor     rax, rsp
0x18000c0c9  mov     [rsp+68h+var_18], rax
0x18000c0ce  mov     ecx, 10h; Size
0x18000c0d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c0d8  mov     [rsp+68h+var_48], rax
0x18000c0dd  lea     rdx, aUsosvcUsosvcim; "usosvc.UsoSvcImpl"
0x18000c0e4  mov     rcx, rax; this
0x18000c0e7  call    ??0Session@uus@@QEAA@PEBG@Z; uus::Session::Session(ushort const *)
0x18000c0ec  mov     rdi, rax
0x18000c0ef  mov     [rsp+68h+var_48], rax
0x18000c0f4  lea     rdx, [rsp+68h+lpLibFileName]
0x18000c0f9  mov     rcx, rax
0x18000c0fc  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEBG@Z; uus::Session::GetFullPath(ushort const *)
0x18000c101  nop
0x18000c102  lea     rcx, [rsp+68h+lpLibFileName]
0x18000c107  cmp     [rsp+68h+var_20], 7
0x18000c10d  cmova   rcx, [rsp+68h+lpLibFileName]; lpLibFileName
0x18000c113  xor     edx, edx; hFile
0x18000c115  mov     r8d, 800h; dwFlags
0x18000c11b  call    cs:__imp_LoadLibraryExW
0x18000c121  mov     rbx, rax
0x18000c124  mov     [rsp+68h+var_40], rax
0x18000c129  test    rax, rax
0x18000c12c  setz    al
0x18000c12f  mov     rcx, [rsp+68h]; this
0x18000c134  test    al, al
0x18000c136  jnz     short loc_18000C1AE
0x18000c138  lea     rdx, aGeneralizefori_0; "GeneralizeForImaging"
0x18000c13f  mov     rcx, rbx; hModule
0x18000c142  call    cs:__imp_GetProcAddress
0x18000c148  mov     rcx, [rsp+68h]; this
0x18000c14d  test    rax, rax
0x18000c150  jz      short loc_18000C1BF
0x18000c152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c157  mov     esi, eax
0x18000c159  test    rbx, rbx
0x18000c15c  jz      short loc_18000C168
0x18000c15e  mov     rcx, rbx; hLibModule
0x18000c161  call    cs:__imp_FreeLibrary
0x18000c167  nop
0x18000c168  lea     rcx, [rsp+68h+lpLibFileName]
0x18000c16d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c172  nop
0x18000c173  test    rdi, rdi
0x18000c176  jz      short loc_18000C18B
0x18000c178  mov     rax, [rdi]
0x18000c17b  mov     edx, 1
0x18000c180  mov     rcx, rdi
0x18000c183  mov     rax, [rax]
0x18000c186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c18b  mov     eax, esi
0x18000c18d  jmp     short loc_18000C191
0x18000c18f  xor     eax, eax
0x18000c191  mov     rcx, [rsp+68h+var_18]
0x18000c196  xor     rcx, rsp; StackCookie
0x18000c199  call    __security_check_cookie
0x18000c19e  mov     rbx, [rsp+68h+arg_0]
0x18000c1a3  mov     rsi, [rsp+68h+arg_8]
0x18000c1a8  add     rsp, 60h
0x18000c1ac  pop     rdi
0x18000c1ad  retn
0x18000c1ae  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18000c1b5  mov     edx, 11h; void *
0x18000c1ba  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c1bf  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18000c1c6  lea     edx, [rax+14h]; void *
0x18000c1c9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
