# COleScript::Initialize(void)

- ea: `0x18002bab4`
- end: `0x18002bb8f`
- name: `?Initialize@COleScript@@QEAAHXZ`
- size: `219`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180019380`
- `0x18002b640`
- `0x180074f00`

## callees

- `0x18002bab4`
- `0x180077010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002bada`
- `KERNEL32!LoadLibraryExW` at `0x18002bada`
- `KERNEL32!InitializeCriticalSection` at `0x18002bb61`
- `KERNEL32!InitializeCriticalSection` at `0x18002bb61`
- `KERNEL32!GetProcAddress` at `0x18002baf6`
- `KERNEL32!GetProcAddress` at `0x18002bb0d`
- `KERNEL32!GetProcAddress` at `0x18002baf6`
- `KERNEL32!GetProcAddress` at `0x18002bb0d`

## string_xrefs

- `0x18002bad3`: `amsi.dll`
- `0x18002baff`: `AmsiScanString`
- `0x18002baec`: `AmsiInitialize`

## pseudocode

```c
__int64 __fastcall COleScript::Initialize(COleScript *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v4; // rax

  Library = LoadLibraryExW(L"amsi.dll", 0, 0x800u);
  *((_QWORD *)this + 120) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AmsiInitialize");
    v4 = GetProcAddress(*((HMODULE *)this + 120), "AmsiScanString");
    *((_QWORD *)this + 117) = v4;
    if ( ProcAddress )
    {
      if ( v4 && ((int (__fastcall *)(_QWORD, char *))ProcAddress)(*((_QWORD *)this + 21), (char *)this + 928) < 0 )
        *((_QWORD *)this + 116) = 0;
    }
  }
  *((_DWORD *)this + 132) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  return *((unsigned int *)this + 132);
}

```

## disassembly

```asm
0x18002bab4  mov     [rsp+arg_10], rbx
0x18002bab9  mov     [rsp+arg_18], rsi
0x18002babe  mov     [rsp+arg_0], rcx
0x18002bac3  push    rdi
0x18002bac4  sub     rsp, 20h
0x18002bac8  mov     rdi, rcx
0x18002bacb  xor     edx, edx; hFile
0x18002bacd  mov     r8d, 800h; dwFlags
0x18002bad3  lea     rcx, LibFileName; "amsi.dll"
0x18002bada  call    cs:__imp_LoadLibraryExW
0x18002bae0  mov     [rdi+3C0h], rax
0x18002bae7  test    rax, rax
0x18002baea  jz      short loc_18002BB48
0x18002baec  lea     rdx, aAmsiinitialize; "AmsiInitialize"
0x18002baf3  mov     rcx, rax; hModule
0x18002baf6  call    cs:__imp_GetProcAddress
0x18002bafc  mov     rsi, rax
0x18002baff  lea     rdx, aAmsiscanstring; "AmsiScanString"
0x18002bb06  mov     rcx, [rdi+3C0h]; hModule
0x18002bb0d  call    cs:__imp_GetProcAddress
0x18002bb13  mov     [rdi+3A8h], rax
0x18002bb1a  test    rsi, rsi
0x18002bb1d  jz      short loc_18002BB48
0x18002bb1f  test    rax, rax
0x18002bb22  jz      short loc_18002BB48
0x18002bb24  lea     rbx, [rdi+3A0h]
0x18002bb2b  mov     rdx, rbx
0x18002bb2e  mov     rcx, [rdi+0A8h]
0x18002bb35  mov     rax, rsi
0x18002bb38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb3d  test    eax, eax
0x18002bb3f  jns     short loc_18002BB48
0x18002bb41  mov     qword ptr [rbx], 0
0x18002bb48  lea     rbx, [rdi+210h]
0x18002bb4f  mov     [rsp+28h+arg_8], rbx
0x18002bb54  mov     dword ptr [rbx], 1
0x18002bb5a  lea     rcx, [rdi+218h]; lpCriticalSection
0x18002bb61  call    cs:__imp_InitializeCriticalSection
0x18002bb67  jmp     short loc_18002BB7D
0x18002bb69  mov     rax, [rsp+28h+arg_0]
0x18002bb6e  mov     dword ptr [rax+210h], 0
0x18002bb78  mov     rbx, [rsp+28h+arg_8]
0x18002bb7d  mov     eax, [rbx]
0x18002bb7f  mov     rbx, [rsp+28h+arg_10]
0x18002bb84  mov     rsi, [rsp+28h+arg_18]
0x18002bb89  add     rsp, 20h
0x18002bb8d  pop     rdi
0x18002bb8e  retn
```
