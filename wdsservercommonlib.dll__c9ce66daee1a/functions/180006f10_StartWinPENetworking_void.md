# StartWinPENetworking(void)

- ea: `0x180006f10`
- end: `0x180006ff3`
- name: `?StartWinPENetworking@@YAJXZ`
- size: `227`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006f10`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006f3a`
- `KERNEL32!GetLastError` at `0x180006f7c`
- `KERNEL32!GetLastError` at `0x180006f3a`
- `KERNEL32!GetLastError` at `0x180006f7c`
- `KERNEL32!LoadLibraryW` at `0x180006f26`
- `KERNEL32!LoadLibraryW` at `0x180006f26`
- `KERNEL32!GetProcAddress` at `0x180006f68`
- `KERNEL32!GetProcAddress` at `0x180006fa3`
- `KERNEL32!GetProcAddress` at `0x180006f68`
- `KERNEL32!GetProcAddress` at `0x180006fa3`
- `KERNEL32!FreeLibrary` at `0x180006fd4`
- `KERNEL32!FreeLibrary` at `0x180006fd4`

## string_xrefs

- `0x180006f1f`: `wpeutil.dll`
- `0x180006f5e`: `WpeSetComputerName`

## pseudocode

```c
__int64 StartWinPENetworking(void)
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rdi
  signed int v2; // eax
  signed int v3; // ebx
  FARPROC ProcAddress; // rbx
  signed int LastError; // eax
  __int64 (*v6)(void); // rsi

  LibraryW = LoadLibraryW(L"wpeutil.dll");
  v1 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "WpeSetComputerName");
    if ( ProcAddress && (v6 = GetProcAddress(v1, "WpeInitializeNetwork")) != 0 )
    {
      v3 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
      if ( v3 >= 0 )
        v3 = v6();
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    FreeLibrary(v1);
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006f10  mov     [rsp+arg_0], rbx
0x180006f15  mov     [rsp+arg_8], rsi
0x180006f1a  push    rdi
0x180006f1b  sub     rsp, 20h
0x180006f1f  lea     rcx, LibFileName; "wpeutil.dll"
0x180006f26  call    cs:__imp_LoadLibraryW
0x180006f2d  nop     dword ptr [rax+rax+00h]
0x180006f32  mov     rdi, rax
0x180006f35  test    rax, rax
0x180006f38  jnz     short loc_180006F5E
0x180006f3a  call    cs:__imp_GetLastError
0x180006f41  nop     dword ptr [rax+rax+00h]
0x180006f46  mov     ebx, eax
0x180006f48  test    eax, eax
0x180006f4a  jle     loc_180006FE0
0x180006f50  movzx   ebx, ax
0x180006f53  or      ebx, 80070000h
0x180006f59  jmp     loc_180006FE0
0x180006f5e  lea     rdx, ProcName; "WpeSetComputerName"
0x180006f65  mov     rcx, rdi; hModule
0x180006f68  call    cs:__imp_GetProcAddress
0x180006f6f  nop     dword ptr [rax+rax+00h]
0x180006f74  mov     rbx, rax
0x180006f77  test    rax, rax
0x180006f7a  jnz     short loc_180006F99
0x180006f7c  call    cs:__imp_GetLastError
0x180006f83  nop     dword ptr [rax+rax+00h]
0x180006f88  mov     ebx, eax
0x180006f8a  test    eax, eax
0x180006f8c  jle     short loc_180006FD1
0x180006f8e  movzx   ebx, ax
0x180006f91  or      ebx, 80070000h
0x180006f97  jmp     short loc_180006FD1
0x180006f99  lea     rdx, aWpeinitializen; "WpeInitializeNetwork"
0x180006fa0  mov     rcx, rdi; hModule
0x180006fa3  call    cs:__imp_GetProcAddress
0x180006faa  nop     dword ptr [rax+rax+00h]
0x180006faf  mov     rsi, rax
0x180006fb2  test    rax, rax
0x180006fb5  jz      short loc_180006F7C
0x180006fb7  xor     ecx, ecx
0x180006fb9  mov     rax, rbx
0x180006fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc1  mov     ebx, eax
0x180006fc3  test    eax, eax
0x180006fc5  js      short loc_180006FD1
0x180006fc7  mov     rax, rsi
0x180006fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fcf  mov     ebx, eax
0x180006fd1  mov     rcx, rdi; hLibModule
0x180006fd4  call    cs:__imp_FreeLibrary
0x180006fdb  nop     dword ptr [rax+rax+00h]
0x180006fe0  mov     rsi, [rsp+28h+arg_8]
0x180006fe5  mov     eax, ebx
0x180006fe7  mov     rbx, [rsp+28h+arg_0]
0x180006fec  add     rsp, 20h
0x180006ff0  pop     rdi
0x180006ff1  retn
```
