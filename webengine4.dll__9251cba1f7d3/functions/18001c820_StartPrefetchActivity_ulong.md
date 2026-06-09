# StartPrefetchActivity(ulong)

- ea: `0x18001c820`
- end: `0x18001c8b7`
- name: `?StartPrefetchActivity@@YAJK@Z`
- size: `151`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001c820`
- `0x18004d030`
- `0x18004d350`
- `0x180065b60`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001c897`
- `KERNEL32!FreeLibrary` at `0x18001c897`
- `KERNEL32!GetProcAddress` at `0x18001c873`
- `KERNEL32!GetProcAddress` at `0x18001c873`
- `KERNEL32!LoadLibraryW` at `0x18001c852`
- `KERNEL32!LoadLibraryW` at `0x18001c852`

## string_xrefs

- `0x18001c83f`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall StartPrefetchActivity(int a1)
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
    ProcAddress = GetProcAddress(LibraryW, "OperationStart");
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
0x18001c820  mov     [rsp+arg_8], rbx
0x18001c825  push    rdi
0x18001c826  sub     rsp, 40h
0x18001c82a  mov     rax, cs:__security_cookie
0x18001c831  xor     rax, rsp
0x18001c834  mov     [rsp+48h+var_18], rax
0x18001c839  mov     [rsp+48h+var_24], ecx
0x18001c83d  xor     ebx, ebx
0x18001c83f  lea     rcx, LibFileName; "advapi32.dll"
0x18001c846  mov     [rsp+48h+var_20], ebx
0x18001c84a  mov     [rsp+48h+var_28], 1
0x18001c852  call    cs:__imp_LoadLibraryW
0x18001c858  mov     rdi, rax
0x18001c85b  test    rax, rax
0x18001c85e  jnz     short loc_18001C869
0x18001c860  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001c865  mov     ebx, eax
0x18001c867  jmp     short loc_18001C89D
0x18001c869  lea     rdx, aOperationstart; "OperationStart"
0x18001c870  mov     rcx, rdi; hModule
0x18001c873  call    cs:__imp_GetProcAddress
0x18001c879  test    rax, rax
0x18001c87c  jz      short loc_18001C88D
0x18001c87e  lea     rcx, [rsp+48h+var_28]
0x18001c883  call    cs:__guard_dispatch_icall_fptr
0x18001c889  test    eax, eax
0x18001c88b  jnz     short loc_18001C894
0x18001c88d  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001c892  mov     ebx, eax
0x18001c894  mov     rcx, rdi; hLibModule
0x18001c897  call    cs:__imp_FreeLibrary
0x18001c89d  mov     eax, ebx
0x18001c89f  mov     rcx, [rsp+48h+var_18]
0x18001c8a4  xor     rcx, rsp; StackCookie
0x18001c8a7  call    __security_check_cookie
0x18001c8ac  mov     rbx, [rsp+48h+arg_8]
0x18001c8b1  add     rsp, 40h
0x18001c8b5  pop     rdi
0x18001c8b6  retn
```
