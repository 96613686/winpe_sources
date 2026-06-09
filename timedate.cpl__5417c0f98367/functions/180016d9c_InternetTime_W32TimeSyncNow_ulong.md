# InternetTime_W32TimeSyncNow(ulong)

- ea: `0x180016d9c`
- end: `0x180016e22`
- name: `?InternetTime_W32TimeSyncNow@@YAJK@Z`
- size: `134`
- prototype: `int(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d8b0`

## callees

- `0x1800092c4`
- `0x1800166b0`
- `0x180016d9c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016e0a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016e0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016dce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016dce`

## string_xrefs

- `0x180016db2`: `w32time.DLL`
- `0x180016df3`: `shell\cpls\utc\inettimecommon.cpp`

## pseudocode

```c
__int64 __fastcall InternetTime_W32TimeSyncNow(unsigned int a1)
{
  unsigned int v2; // ebx
  HMODULE LibraryW; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  int v6; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = -2147467259;
  LibraryW = IsolationAwareLoadLibraryW(L"w32time.DLL");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x19);
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD))ProcAddress)(0, 1, a1);
      v2 = v6;
      if ( v6 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
          (const char *)(unsigned int)v6,
          v8);
    }
    FreeLibrary(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x180016d9c  mov     [rsp+arg_0], rbx
0x180016da1  mov     [rsp+arg_8], rsi
0x180016da6  push    rdi; int
0x180016da7  sub     rsp, 20h
0x180016dab  mov     esi, ecx
0x180016dad  mov     ebx, 80004005h
0x180016db2  lea     rcx, aW32timeDll; "w32time.DLL"
0x180016db9  call    IsolationAwareLoadLibraryW
0x180016dbe  mov     rdi, rax
0x180016dc1  test    rax, rax
0x180016dc4  jz      short loc_180016E10
0x180016dc6  mov     edx, 19h; lpProcName
0x180016dcb  mov     rcx, rax; hModule
0x180016dce  call    cs:__imp_GetProcAddress
0x180016dd4  test    rax, rax
0x180016dd7  jz      short loc_180016E07
0x180016dd9  mov     r8d, esi
0x180016ddc  mov     edx, 1
0x180016de1  xor     ecx, ecx
0x180016de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016de8  mov     ebx, eax
0x180016dea  test    eax, eax
0x180016dec  jns     short loc_180016E07
0x180016dee  mov     rcx, [rsp+28h]; this
0x180016df3  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x180016dfa  mov     r9d, eax; char *
0x180016dfd  mov     edx, 5Bh ; '['; void *
0x180016e02  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016e07  mov     rcx, rdi; hLibModule
0x180016e0a  call    cs:__imp_FreeLibrary
0x180016e10  mov     rsi, [rsp+28h+arg_8]
0x180016e15  mov     eax, ebx
0x180016e17  mov     rbx, [rsp+28h+arg_0]
0x180016e1c  add     rsp, 20h
0x180016e20  pop     rdi
0x180016e21  retn
```
