# StartWinPENetworking(void)

- ea: `0x180007a40`
- end: `0x180007b23`
- name: `?StartWinPENetworking@@YAJXZ`
- size: `227`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007a6a`
- `KERNEL32!GetLastError` at `0x180007aac`
- `KERNEL32!GetLastError` at `0x180007a6a`
- `KERNEL32!GetLastError` at `0x180007aac`
- `KERNEL32!LoadLibraryW` at `0x180007a56`
- `KERNEL32!LoadLibraryW` at `0x180007a56`
- `KERNEL32!GetProcAddress` at `0x180007a98`
- `KERNEL32!GetProcAddress` at `0x180007ad3`
- `KERNEL32!GetProcAddress` at `0x180007a98`
- `KERNEL32!GetProcAddress` at `0x180007ad3`
- `KERNEL32!FreeLibrary` at `0x180007b04`
- `KERNEL32!FreeLibrary` at `0x180007b04`

## string_xrefs

- `0x180007a4f`: `wpeutil.dll`
- `0x180007a8e`: `WpeSetComputerName`

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
0x180007a40  mov     [rsp+arg_0], rbx
0x180007a45  mov     [rsp+arg_8], rsi
0x180007a4a  push    rdi
0x180007a4b  sub     rsp, 20h
0x180007a4f  lea     rcx, LibFileName; "wpeutil.dll"
0x180007a56  call    cs:__imp_LoadLibraryW
0x180007a5d  nop     dword ptr [rax+rax+00h]
0x180007a62  mov     rdi, rax
0x180007a65  test    rax, rax
0x180007a68  jnz     short loc_180007A8E
0x180007a6a  call    cs:__imp_GetLastError
0x180007a71  nop     dword ptr [rax+rax+00h]
0x180007a76  mov     ebx, eax
0x180007a78  test    eax, eax
0x180007a7a  jle     loc_180007B10
0x180007a80  movzx   ebx, ax
0x180007a83  or      ebx, 80070000h
0x180007a89  jmp     loc_180007B10
0x180007a8e  lea     rdx, ProcName; "WpeSetComputerName"
0x180007a95  mov     rcx, rdi; hModule
0x180007a98  call    cs:__imp_GetProcAddress
0x180007a9f  nop     dword ptr [rax+rax+00h]
0x180007aa4  mov     rbx, rax
0x180007aa7  test    rax, rax
0x180007aaa  jnz     short loc_180007AC9
0x180007aac  call    cs:__imp_GetLastError
0x180007ab3  nop     dword ptr [rax+rax+00h]
0x180007ab8  mov     ebx, eax
0x180007aba  test    eax, eax
0x180007abc  jle     short loc_180007B01
0x180007abe  movzx   ebx, ax
0x180007ac1  or      ebx, 80070000h
0x180007ac7  jmp     short loc_180007B01
0x180007ac9  lea     rdx, aWpeinitializen; "WpeInitializeNetwork"
0x180007ad0  mov     rcx, rdi; hModule
0x180007ad3  call    cs:__imp_GetProcAddress
0x180007ada  nop     dword ptr [rax+rax+00h]
0x180007adf  mov     rsi, rax
0x180007ae2  test    rax, rax
0x180007ae5  jz      short loc_180007AAC
0x180007ae7  xor     ecx, ecx
0x180007ae9  mov     rax, rbx
0x180007aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af1  mov     ebx, eax
0x180007af3  test    eax, eax
0x180007af5  js      short loc_180007B01
0x180007af7  mov     rax, rsi
0x180007afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aff  mov     ebx, eax
0x180007b01  mov     rcx, rdi; hLibModule
0x180007b04  call    cs:__imp_FreeLibrary
0x180007b0b  nop     dword ptr [rax+rax+00h]
0x180007b10  mov     rsi, [rsp+28h+arg_8]
0x180007b15  mov     eax, ebx
0x180007b17  mov     rbx, [rsp+28h+arg_0]
0x180007b1c  add     rsp, 20h
0x180007b20  pop     rdi
0x180007b21  retn
```
