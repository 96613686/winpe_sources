# EndPrefetchActivity(ulong)

- ea: `0x18001c780`
- end: `0x18001c817`
- name: `?EndPrefetchActivity@@YAJK@Z`
- size: `151`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001c780`
- `0x18004d030`
- `0x18004d350`
- `0x180065b60`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001c7f7`
- `KERNEL32!FreeLibrary` at `0x18001c7f7`
- `KERNEL32!GetProcAddress` at `0x18001c7d3`
- `KERNEL32!GetProcAddress` at `0x18001c7d3`
- `KERNEL32!LoadLibraryW` at `0x18001c7b2`
- `KERNEL32!LoadLibraryW` at `0x18001c7b2`

## string_xrefs

- `0x18001c79f`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall EndPrefetchActivity(int a1)
{
  unsigned int LastWin32Error; // ebx
  HMODULE LibraryW; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  _DWORD v6[4]; // [rsp+20h] [rbp-28h] BYREF

  v6[1] = a1;
  LastWin32Error = 0;
  v6[2] = 0;
  v6[0] = 1;
  LibraryW = LoadLibraryW(L"advapi32.dll");
  v3 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "OperationEnd");
    if ( !ProcAddress || !((unsigned int (__fastcall *)(_DWORD *))ProcAddress)(v6) )
      LastWin32Error = GetLastWin32Error();
    FreeLibrary(v3);
  }
  else
  {
    return (unsigned int)GetLastWin32Error();
  }
  return LastWin32Error;
}

```

## disassembly

```asm
0x18001c780  mov     [rsp+arg_8], rbx
0x18001c785  push    rdi
0x18001c786  sub     rsp, 40h
0x18001c78a  mov     rax, cs:__security_cookie
0x18001c791  xor     rax, rsp
0x18001c794  mov     [rsp+48h+var_18], rax
0x18001c799  mov     [rsp+48h+var_24], ecx
0x18001c79d  xor     ebx, ebx
0x18001c79f  lea     rcx, LibFileName; "advapi32.dll"
0x18001c7a6  mov     [rsp+48h+var_20], ebx
0x18001c7aa  mov     [rsp+48h+var_28], 1
0x18001c7b2  call    cs:__imp_LoadLibraryW
0x18001c7b8  mov     rdi, rax
0x18001c7bb  test    rax, rax
0x18001c7be  jnz     short loc_18001C7C9
0x18001c7c0  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001c7c5  mov     ebx, eax
0x18001c7c7  jmp     short loc_18001C7FD
0x18001c7c9  lea     rdx, aOperationend; "OperationEnd"
0x18001c7d0  mov     rcx, rdi; hModule
0x18001c7d3  call    cs:__imp_GetProcAddress
0x18001c7d9  test    rax, rax
0x18001c7dc  jz      short loc_18001C7ED
0x18001c7de  lea     rcx, [rsp+48h+var_28]
0x18001c7e3  call    cs:__guard_dispatch_icall_fptr
0x18001c7e9  test    eax, eax
0x18001c7eb  jnz     short loc_18001C7F4
0x18001c7ed  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001c7f2  mov     ebx, eax
0x18001c7f4  mov     rcx, rdi; hLibModule
0x18001c7f7  call    cs:__imp_FreeLibrary
0x18001c7fd  mov     eax, ebx
0x18001c7ff  mov     rcx, [rsp+48h+var_18]
0x18001c804  xor     rcx, rsp; StackCookie
0x18001c807  call    __security_check_cookie
0x18001c80c  mov     rbx, [rsp+48h+arg_8]
0x18001c811  add     rsp, 40h
0x18001c815  pop     rdi
0x18001c816  retn
```
