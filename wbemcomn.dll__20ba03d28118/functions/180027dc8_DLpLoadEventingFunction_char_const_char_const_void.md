# DLpLoadEventingFunction(char const *,char const *,void * *)

- ea: `0x180027dc8`
- end: `0x180027e8e`
- name: `?DLpLoadEventingFunction@@YAKPEBD0PEAPEAX@Z`
- size: `198`
- prototype: `unsigned int __fastcall(LPCSTR lpProcName, const char *, FARPROC *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800048e8`
- `0x180027bd0`
- `0x180027c30`
- `0x180027d30`
- `0x180043d60`
- `0x180043dc0`

## callees

- `0x180027dc8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180027e23`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180027e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027e00`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027e5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027e5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027e37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027e37`

## string_xrefs

- `0x180027e30`: `ntdll.dll`
- `0x180027e54`: `advapi32.dll`

## pseudocode

```c
unsigned int __fastcall DLpLoadEventingFunction(LPCSTR lpProcName, const char *a2, FARPROC *a3)
{
  HMODULE ModuleHandleW; // rax
  char v7; // cl
  FARPROC ProcAddress; // rcx
  unsigned int result; // eax

  ModuleHandleW = hModule;
  if ( hModule )
  {
    v7 = byte_180070280;
  }
  else
  {
    if ( GetVersion() >= 0x6010000 )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      hModule = ModuleHandleW;
      if ( ModuleHandleW )
      {
        byte_180070280 = 1;
        goto LABEL_5;
      }
    }
    ModuleHandleW = LoadLibraryExW(L"advapi32.dll", 0, 8u);
    hModule = ModuleHandleW;
    if ( !ModuleHandleW )
      return GetLastError();
    v7 = 0;
    byte_180070280 = 0;
  }
  if ( !v7 )
    lpProcName = a2;
LABEL_5:
  ProcAddress = GetProcAddress(ModuleHandleW, lpProcName);
  if ( ProcAddress )
  {
    result = 0;
    *a3 = ProcAddress;
    return result;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180027dc8  mov     [rsp+arg_0], rbx
0x180027dcd  mov     [rsp+arg_8], rsi
0x180027dd2  push    rdi
0x180027dd3  sub     rsp, 20h
0x180027dd7  mov     rax, cs:hModule
0x180027dde  mov     rsi, r8
0x180027de1  mov     rdi, rdx
0x180027de4  mov     rbx, rcx
0x180027de7  test    rax, rax
0x180027dea  jz      short loc_180027E23
0x180027dec  mov     cl, cs:byte_180070280
0x180027df2  test    cl, cl
0x180027df4  jz      loc_180027E86
0x180027dfa  mov     rdx, rbx; lpProcName
0x180027dfd  mov     rcx, rax; hModule
0x180027e00  call    cs:__imp_GetProcAddress
0x180027e06  mov     rcx, rax
0x180027e09  test    rax, rax
0x180027e0c  jz      short loc_180027E71
0x180027e0e  xor     eax, eax
0x180027e10  mov     [rsi], rcx
0x180027e13  mov     rbx, [rsp+28h+arg_0]
0x180027e18  mov     rsi, [rsp+28h+arg_8]
0x180027e1d  add     rsp, 20h
0x180027e21  pop     rdi
0x180027e22  retn
0x180027e23  call    cs:__imp_GetVersion
0x180027e29  cmp     eax, 6010000h
0x180027e2e  jb      short loc_180027E52
0x180027e30  lea     rcx, ModuleName; "ntdll.dll"
0x180027e37  call    cs:__imp_GetModuleHandleW
0x180027e3d  mov     cs:hModule, rax
0x180027e44  test    rax, rax
0x180027e47  jz      short loc_180027E52
0x180027e49  mov     cs:byte_180070280, 1
0x180027e50  jmp     short loc_180027DFA
0x180027e52  xor     edx, edx; hFile
0x180027e54  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180027e5b  lea     r8d, [rdx+8]; dwFlags
0x180027e5f  call    cs:__imp_LoadLibraryExW
0x180027e65  mov     cs:hModule, rax
0x180027e6c  test    rax, rax
0x180027e6f  jnz     short loc_180027E79
0x180027e71  call    cs:__imp_GetLastError
0x180027e77  jmp     short loc_180027E13
0x180027e79  xor     cl, cl
0x180027e7b  mov     cs:byte_180070280, cl
0x180027e81  jmp     loc_180027DF2
0x180027e86  mov     rbx, rdi
0x180027e89  jmp     loc_180027DFA
```
