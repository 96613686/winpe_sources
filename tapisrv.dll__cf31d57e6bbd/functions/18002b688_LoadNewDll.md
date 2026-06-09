# LoadNewDll

- ea: `0x18002b688`
- end: `0x18002b85a`
- name: `LoadNewDll`
- size: `466`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002bc98`

## callees

- `0x18002b688`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18002b847`
- `KERNEL32!FreeLibrary` at `0x18002b847`
- `KERNEL32!GetProcAddress` at `0x18002b6ef`
- `KERNEL32!GetProcAddress` at `0x18002b70c`
- `KERNEL32!GetProcAddress` at `0x18002b729`
- `KERNEL32!GetProcAddress` at `0x18002b746`
- `KERNEL32!GetProcAddress` at `0x18002b769`
- `KERNEL32!GetProcAddress` at `0x18002b6ef`
- `KERNEL32!GetProcAddress` at `0x18002b70c`
- `KERNEL32!GetProcAddress` at `0x18002b729`
- `KERNEL32!GetProcAddress` at `0x18002b746`
- `KERNEL32!GetProcAddress` at `0x18002b769`
- `KERNEL32!LoadLibraryW` at `0x18002b6ae`
- `KERNEL32!LoadLibraryW` at `0x18002b6ae`
- `KERNEL32!GetLastError` at `0x18002b6c3`
- `KERNEL32!GetLastError` at `0x18002b6c3`

## string_xrefs

- `0x18002b6cc`: `LoadLibrary failed for management DLL %ls - error x%lx`
- `0x18002b822`: `Management DLL %ls does not export Load, Free, ClientIntialize or ClientShutdown`
- `0x18002b833`: `  The DLL will not be used`
- `0x18002b7b2`: `Management DLL %ls returned %xlx from TAPICLIENT_Load`
- `0x18002b7c6`: `   The DLL will not be used`
- `0x18002b7e7`: `Management DLL %ls returned an invalid API version - x%lx`

## pseudocode

```c
__int64 __fastcall LoadNewDll(__int64 a1)
{
  const WCHAR *v2; // rcx
  HMODULE LibraryW; // rax
  const wchar_t *v4; // rbx
  DWORD LastError; // eax
  FARPROC ProcAddress; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  __int64 i; // rdi
  _DWORD *v11; // rdi
  int v12; // eax

  if ( !a1 )
    return 0;
  v2 = *(const WCHAR **)(a1 + 232);
  if ( !v2 )
    return 0;
  LibraryW = LoadLibraryW(v2);
  *(_QWORD *)a1 = LibraryW;
  if ( !LibraryW )
  {
    v4 = *(const wchar_t **)(a1 + 232);
    LastError = GetLastError();
    TRACELogPrint(65538, "LoadLibrary failed for management DLL %ls - error x%lx", v4, LastError);
    return 0;
  }
  ProcAddress = GetProcAddress(LibraryW, "TAPICLIENT_ClientInitialize");
  *(_QWORD *)(a1 + 32) = ProcAddress;
  if ( !ProcAddress
    || (v7 = GetProcAddress(*(HMODULE *)a1, "TAPICLIENT_ClientShutdown"), (*(_QWORD *)(a1 + 40) = v7) == 0)
    || (v8 = GetProcAddress(*(HMODULE *)a1, gaszTCFuncNames), (*(_QWORD *)(a1 + 16) = v8) == 0)
    || (v9 = GetProcAddress(*(HMODULE *)a1, "TAPICLIENT_Free"), (*(_QWORD *)(a1 + 24) = v9) == 0) )
  {
    TRACELogPrint(
      65538,
      "Management DLL %ls does not export Load, Free, ClientIntialize or ClientShutdown",
      *(const wchar_t **)(a1 + 232));
    TRACELogPrint(65538, "  The DLL will not be used");
    goto LABEL_17;
  }
  for ( i = 0; i != 27; ++i )
    *(_QWORD *)(a1 + 8 * i + 16) = GetProcAddress(*(HMODULE *)a1, (&gaszTCFuncNames)[i]);
  v11 = (_DWORD *)(a1 + 240);
  *(_DWORD *)(a1 + 240) = 196609;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(), __int64 (__fastcall *)(), _QWORD))(a1 + 16))(
          a1 + 240,
          ManagementAddPhoneProc,
          ManagementAddPhoneProc,
          0);
  if ( v12 )
  {
    TRACELogPrint(65538, "Management DLL %ls returned %xlx from TAPICLIENT_Load", *(const wchar_t **)(a1 + 232), v12);
    TRACELogPrint(65538, "   The DLL will not be used");
LABEL_17:
    FreeLibrary(*(HMODULE *)a1);
    return 0;
  }
  if ( (unsigned int)(*v11 - 131073) > 0x10000 )
  {
    TRACELogPrint(
      262146,
      "Management DLL %ls returned an invalid API version - x%lx",
      *(const wchar_t **)(a1 + 232),
      *v11);
    TRACELogPrint(262146, "   Will use version x%lx", 196609);
    *v11 = 196609;
  }
  return 1;
}

```

## disassembly

```asm
0x18002b688  mov     [rsp+arg_0], rbx
0x18002b68d  push    rdi
0x18002b68e  sub     rsp, 30h
0x18002b692  mov     rbx, rcx
0x18002b695  test    rcx, rcx
0x18002b698  jz      loc_18002B84D
0x18002b69e  mov     rcx, [rcx+0E8h]; lpLibFileName
0x18002b6a5  test    rcx, rcx
0x18002b6a8  jz      loc_18002B84D
0x18002b6ae  call    cs:__imp_LoadLibraryW
0x18002b6b4  mov     [rbx], rax
0x18002b6b7  test    rax, rax
0x18002b6ba  jnz     short loc_18002B6E5
0x18002b6bc  mov     rbx, [rbx+0E8h]
0x18002b6c3  call    cs:__imp_GetLastError
0x18002b6c9  mov     r8, rbx
0x18002b6cc  lea     rdx, aLoadlibraryFai; "LoadLibrary failed for management DLL %"...
0x18002b6d3  mov     r9d, eax
0x18002b6d6  mov     ecx, 10002h
0x18002b6db  call    TRACELogPrint
0x18002b6e0  jmp     loc_18002B84D
0x18002b6e5  mov     rdx, cs:off_180041740; lpProcName
0x18002b6ec  mov     rcx, rax; hModule
0x18002b6ef  call    cs:__imp_GetProcAddress
0x18002b6f5  mov     [rbx+20h], rax
0x18002b6f9  test    rax, rax
0x18002b6fc  jz      loc_18002B81B
0x18002b702  mov     rdx, cs:off_180041748; lpProcName
0x18002b709  mov     rcx, [rbx]; hModule
0x18002b70c  call    cs:__imp_GetProcAddress
0x18002b712  mov     [rbx+28h], rax
0x18002b716  test    rax, rax
0x18002b719  jz      loc_18002B81B
0x18002b71f  mov     rdx, cs:gaszTCFuncNames; lpProcName
0x18002b726  mov     rcx, [rbx]; hModule
0x18002b729  call    cs:__imp_GetProcAddress
0x18002b72f  mov     [rbx+10h], rax
0x18002b733  test    rax, rax
0x18002b736  jz      loc_18002B81B
0x18002b73c  mov     rdx, cs:off_180041738; lpProcName
0x18002b743  mov     rcx, [rbx]; hModule
0x18002b746  call    cs:__imp_GetProcAddress
0x18002b74c  mov     [rbx+18h], rax
0x18002b750  test    rax, rax
0x18002b753  jz      loc_18002B81B
0x18002b759  xor     edi, edi
0x18002b75b  mov     rcx, [rbx]; hModule
0x18002b75e  lea     rdx, gaszTCFuncNames
0x18002b765  mov     rdx, [rdx+rdi*8]; lpProcName
0x18002b769  call    cs:__imp_GetProcAddress
0x18002b76f  mov     [rbx+rdi*8+10h], rax
0x18002b774  inc     rdi
0x18002b777  cmp     rdi, 1Bh
0x18002b77b  jnz     short loc_18002B75B
0x18002b77d  lea     rdi, [rbx+0F0h]
0x18002b784  xor     r9d, r9d
0x18002b787  mov     dword ptr [rdi], 30001h
0x18002b78d  lea     r8, ManagementAddPhoneProc
0x18002b794  mov     rax, [rbx+10h]
0x18002b798  lea     rdx, ManagementAddPhoneProc
0x18002b79f  mov     rcx, rdi
0x18002b7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7a7  test    eax, eax
0x18002b7a9  jz      short loc_18002B7CF
0x18002b7ab  mov     r8, [rbx+0E8h]
0x18002b7b2  lea     rdx, aManagementDllL_0; "Management DLL %ls returned %xlx from T"...
0x18002b7b9  mov     r9d, eax
0x18002b7bc  mov     ecx, 10002h
0x18002b7c1  call    TRACELogPrint
0x18002b7c6  lea     rdx, aTheDllWillNotB_0; "   The DLL will not be used"
0x18002b7cd  jmp     short loc_18002B83A
0x18002b7cf  mov     r9d, [rdi]
0x18002b7d2  lea     eax, [r9-20001h]
0x18002b7d9  cmp     eax, 10000h
0x18002b7de  jbe     short loc_18002B814
0x18002b7e0  mov     r8, [rbx+0E8h]
0x18002b7e7  lea     rdx, aManagementDllL_1; "Management DLL %ls returned an invalid "...
0x18002b7ee  mov     ebx, 40002h
0x18002b7f3  mov     ecx, ebx
0x18002b7f5  call    TRACELogPrint
0x18002b7fa  mov     r8d, 30001h
0x18002b800  lea     rdx, aWillUseVersion; "   Will use version x%lx"
0x18002b807  mov     ecx, ebx
0x18002b809  call    TRACELogPrint
0x18002b80e  mov     dword ptr [rdi], 30001h
0x18002b814  mov     eax, 1
0x18002b819  jmp     short loc_18002B84F
0x18002b81b  mov     r8, [rbx+0E8h]
0x18002b822  lea     rdx, aManagementDllL; "Management DLL %ls does not export Load"...
0x18002b829  mov     ecx, 10002h
0x18002b82e  call    TRACELogPrint
0x18002b833  lea     rdx, aTheDllWillNotB; "  The DLL will not be used"
0x18002b83a  mov     ecx, 10002h
0x18002b83f  call    TRACELogPrint
0x18002b844  mov     rcx, [rbx]; hLibModule
0x18002b847  call    cs:__imp_FreeLibrary
0x18002b84d  xor     eax, eax
0x18002b84f  mov     rbx, [rsp+38h+arg_0]
0x18002b854  add     rsp, 30h
0x18002b858  pop     rdi
0x18002b859  retn
```
