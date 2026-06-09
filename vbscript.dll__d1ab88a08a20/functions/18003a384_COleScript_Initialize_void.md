# COleScript::Initialize(void)

- ea: `0x18003a384`
- end: `0x18003a478`
- name: `?Initialize@COleScript@@QEAAHXZ`
- size: `244`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180013fb0`
- `0x180039f10`
- `0x180077ad0`

## callees

- `0x18003a384`
- `0x18007a010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18003a3aa`
- `KERNEL32!LoadLibraryExW` at `0x18003a3aa`
- `KERNEL32!InitializeCriticalSection` at `0x18003a443`
- `KERNEL32!InitializeCriticalSection` at `0x18003a443`
- `KERNEL32!GetProcAddress` at `0x18003a3cc`
- `KERNEL32!GetProcAddress` at `0x18003a3e9`
- `KERNEL32!GetProcAddress` at `0x18003a3cc`
- `KERNEL32!GetProcAddress` at `0x18003a3e9`

## string_xrefs

- `0x18003a3a3`: `amsi.dll`
- `0x18003a3db`: `AmsiScanString`
- `0x18003a3c2`: `AmsiInitialize`

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
0x18003a384  mov     [rsp+arg_10], rbx
0x18003a389  mov     [rsp+arg_18], rsi
0x18003a38e  mov     [rsp+arg_0], rcx
0x18003a393  push    rdi
0x18003a394  sub     rsp, 20h
0x18003a398  mov     rdi, rcx
0x18003a39b  xor     edx, edx; hFile
0x18003a39d  mov     r8d, 800h; dwFlags
0x18003a3a3  lea     rcx, LibFileName; "amsi.dll"
0x18003a3aa  call    cs:__imp_LoadLibraryExW
0x18003a3b1  nop     dword ptr [rax+rax+00h]
0x18003a3b6  mov     [rdi+3C0h], rax
0x18003a3bd  test    rax, rax
0x18003a3c0  jz      short loc_18003A42A
0x18003a3c2  lea     rdx, aAmsiinitialize; "AmsiInitialize"
0x18003a3c9  mov     rcx, rax; hModule
0x18003a3cc  call    cs:__imp_GetProcAddress
0x18003a3d3  nop     dword ptr [rax+rax+00h]
0x18003a3d8  mov     rsi, rax
0x18003a3db  lea     rdx, aAmsiscanstring; "AmsiScanString"
0x18003a3e2  mov     rcx, [rdi+3C0h]; hModule
0x18003a3e9  call    cs:__imp_GetProcAddress
0x18003a3f0  nop     dword ptr [rax+rax+00h]
0x18003a3f5  mov     [rdi+3A8h], rax
0x18003a3fc  test    rsi, rsi
0x18003a3ff  jz      short loc_18003A42A
0x18003a401  test    rax, rax
0x18003a404  jz      short loc_18003A42A
0x18003a406  lea     rbx, [rdi+3A0h]
0x18003a40d  mov     rdx, rbx
0x18003a410  mov     rcx, [rdi+0A8h]
0x18003a417  mov     rax, rsi
0x18003a41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a41f  test    eax, eax
0x18003a421  jns     short loc_18003A42A
0x18003a423  mov     qword ptr [rbx], 0
0x18003a42a  lea     rbx, [rdi+210h]
0x18003a431  mov     [rsp+28h+arg_8], rbx
0x18003a436  mov     dword ptr [rbx], 1
0x18003a43c  lea     rcx, [rdi+218h]; lpCriticalSection
0x18003a443  call    cs:__imp_InitializeCriticalSection
0x18003a44a  nop     dword ptr [rax+rax+00h]
0x18003a44f  jmp     short loc_18003A465
0x18003a451  mov     rax, [rsp+28h+arg_0]
0x18003a456  mov     dword ptr [rax+210h], 0
0x18003a460  mov     rbx, [rsp+28h+arg_8]
0x18003a465  mov     eax, [rbx]
0x18003a467  mov     rbx, [rsp+28h+arg_10]
0x18003a46c  mov     rsi, [rsp+28h+arg_18]
0x18003a471  add     rsp, 20h
0x18003a475  pop     rdi
0x18003a476  retn
```
