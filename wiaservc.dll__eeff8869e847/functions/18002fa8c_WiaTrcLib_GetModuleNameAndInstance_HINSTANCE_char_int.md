# WiaTrcLib::GetModuleNameAndInstance(HINSTANCE__ *,char *,int)

- ea: `0x18002fa8c`
- end: `0x18002fbb0`
- name: `?GetModuleNameAndInstance@WiaTrcLib@@YAPEAUHINSTANCE__@@PEAU2@PEADH@Z`
- size: `292`
- prototype: `HINSTANCE(WiaTrcLib *__hidden this, HINSTANCE, char *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800151c4`

## callees

- `0x1800156e0`
- `0x18002fa8c`
- `0x180033cc0`
- `0x180034658`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x18002fb6b`
- `KERNEL32!GetModuleFileNameA` at `0x18002fb6b`
- `KERNEL32!FreeLibrary` at `0x18002fb3d`
- `KERNEL32!FreeLibrary` at `0x18002fb82`
- `KERNEL32!FreeLibrary` at `0x18002fb3d`
- `KERNEL32!FreeLibrary` at `0x18002fb82`
- `KERNEL32!GetModuleHandleW` at `0x18002fb4f`
- `KERNEL32!GetModuleHandleW` at `0x18002fb4f`
- `KERNEL32!GetProcAddress` at `0x18002fb1b`
- `KERNEL32!GetProcAddress` at `0x18002fb1b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002fb03`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002fb03`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x18002fad9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x18002fad9`

## string_xrefs

- `0x18002fae3`: `\kernel32.dll`

## pseudocode

```c
HINSTANCE __fastcall WiaTrcLib::GetModuleNameAndInstance(WiaTrcLib *this, CHAR *a2, char *a3)
{
  int v4; // edi
  HMODULE Library; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  HMODULE v9; // rbx
  HMODULE hModule[2]; // [rsp+20h] [rbp-138h] BYREF
  CHAR Buffer[272]; // [rsp+30h] [rbp-128h] BYREF

  hModule[0] = 0;
  v4 = 0;
  memset_0(Buffer, 0, 0x104u);
  if ( GetSystemDirectoryA(Buffer, 0x104u) )
  {
    StringCchCatA(Buffer, 0x104u, "\\kernel32.dll");
    Library = LoadLibraryExA(Buffer, 0, 0x800u);
    v6 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetModuleHandleExA");
      if ( ProcAddress )
        ((void (__fastcall *)(__int64, const char *, HMODULE *))ProcAddress)(4, "WiaTrace_Init_Trace", hModule);
      FreeLibrary(v6);
    }
  }
  ModuleHandleW = hModule[0];
  if ( !hModule[0] )
  {
    ModuleHandleW = GetModuleHandleW(0);
    hModule[0] = ModuleHandleW;
    v4 = 1;
  }
  GetModuleFileNameA(ModuleHandleW, a2, 0x105u);
  v9 = hModule[0];
  if ( hModule[0] && !v4 )
    FreeLibrary(hModule[0]);
  return v9;
}

```

## disassembly

```asm
0x18002fa8c  mov     [rsp+arg_0], rbx
0x18002fa91  mov     [rsp+arg_10], rsi
0x18002fa96  push    rdi
0x18002fa97  sub     rsp, 150h
0x18002fa9e  mov     rax, cs:__security_cookie
0x18002faa5  xor     rax, rsp
0x18002faa8  mov     [rsp+158h+var_18], rax
0x18002fab0  mov     rsi, rdx
0x18002fab3  mov     [rsp+158h+hModule], 0
0x18002fabc  mov     ebx, 104h
0x18002fac1  lea     rcx, [rsp+158h+Buffer]; void *
0x18002fac6  mov     r8d, ebx; Size
0x18002fac9  xor     edx, edx; Val
0x18002facb  xor     edi, edi
0x18002facd  call    memset_0
0x18002fad2  mov     edx, ebx; uSize
0x18002fad4  lea     rcx, [rsp+158h+Buffer]; lpBuffer
0x18002fad9  call    cs:__imp_GetSystemDirectoryA
0x18002fadf  test    eax, eax
0x18002fae1  jz      short loc_18002FB43
0x18002fae3  lea     r8, aKernel32Dll_0; "\\kernel32.dll"
0x18002faea  mov     edx, ebx; unsigned __int64
0x18002faec  lea     rcx, [rsp+158h+Buffer]; char *
0x18002faf1  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18002faf6  xor     edx, edx; hFile
0x18002faf8  lea     rcx, [rsp+158h+Buffer]; lpLibFileName
0x18002fafd  mov     r8d, 800h; dwFlags
0x18002fb03  call    cs:__imp_LoadLibraryExA
0x18002fb09  mov     rbx, rax
0x18002fb0c  test    rax, rax
0x18002fb0f  jz      short loc_18002FB43
0x18002fb11  lea     rdx, aGetmodulehandl; "GetModuleHandleExA"
0x18002fb18  mov     rcx, rax; hModule
0x18002fb1b  call    cs:__imp_GetProcAddress
0x18002fb21  test    rax, rax
0x18002fb24  jz      short loc_18002FB3A
0x18002fb26  lea     r8, [rsp+158h+hModule]
0x18002fb2b  lea     rdx, aWiatraceInitTr; "WiaTrace_Init_Trace"
0x18002fb32  lea     ecx, [rdi+4]
0x18002fb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb3a  mov     rcx, rbx; hLibModule
0x18002fb3d  call    cs:__imp_FreeLibrary
0x18002fb43  mov     rax, [rsp+158h+hModule]
0x18002fb48  test    rax, rax
0x18002fb4b  jnz     short loc_18002FB5F
0x18002fb4d  xor     ecx, ecx; lpModuleName
0x18002fb4f  call    cs:__imp_GetModuleHandleW
0x18002fb55  mov     [rsp+158h+hModule], rax
0x18002fb5a  mov     edi, 1
0x18002fb5f  mov     r8d, 105h; nSize
0x18002fb65  mov     rdx, rsi; lpFilename
0x18002fb68  mov     rcx, rax; hModule
0x18002fb6b  call    cs:__imp_GetModuleFileNameA
0x18002fb71  mov     rbx, [rsp+158h+hModule]
0x18002fb76  test    rbx, rbx
0x18002fb79  jz      short loc_18002FB88
0x18002fb7b  test    edi, edi
0x18002fb7d  jnz     short loc_18002FB88
0x18002fb7f  mov     rcx, rbx; hLibModule
0x18002fb82  call    cs:__imp_FreeLibrary
0x18002fb88  mov     rax, rbx
0x18002fb8b  mov     rcx, [rsp+158h+var_18]
0x18002fb93  xor     rcx, rsp; StackCookie
0x18002fb96  call    __security_check_cookie
0x18002fb9b  lea     r11, [rsp+158h+var_8]
0x18002fba3  mov     rbx, [r11+10h]
0x18002fba7  mov     rsi, [r11+20h]
0x18002fbab  mov     rsp, r11
0x18002fbae  pop     rdi
0x18002fbaf  retn
```
