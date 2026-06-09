# mlib::KernelAPIs::LoadLibraryW(void)

- ea: `0x140056cec`
- end: `0x140056d96`
- name: `?LoadLibraryW@KernelAPIs@mlib@@QEAAKXZ`
- size: `170`
- prototype: `unsigned int __fastcall(mlib::KernelAPIs *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x14001a54c`
- `0x14003bdf4`
- `0x1400475e4`
- `0x140048138`

## callees

- `0x140056cec`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140056d20`
- `KERNEL32!GetProcAddress` at `0x140056d39`
- `KERNEL32!GetProcAddress` at `0x140056d52`
- `KERNEL32!GetProcAddress` at `0x140056d6b`
- `KERNEL32!GetProcAddress` at `0x140056d84`
- `KERNEL32!GetProcAddress` at `0x140056d20`
- `KERNEL32!GetProcAddress` at `0x140056d39`
- `KERNEL32!GetProcAddress` at `0x140056d52`
- `KERNEL32!GetProcAddress` at `0x140056d6b`
- `KERNEL32!GetProcAddress` at `0x140056d84`
- `KERNEL32!LoadLibraryW` at `0x140056cfc`
- `KERNEL32!LoadLibraryW` at `0x140056cfc`
- `KERNEL32!GetLastError` at `0x140056d0f`

## string_xrefs

- `0x140056cf5`: `Kernel32.dll`
- `0x140056d32`: `SetThreadPreferredUILanguages`
- `0x140056d7d`: `GetPhysicallyInstalledSystemMemory`

## pseudocode

```c
DWORD __fastcall mlib::KernelAPIs::LoadLibraryW(mlib::KernelAPIs *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax

  LibraryW = LoadLibraryW(L"Kernel32.dll");
  *(_QWORD *)this = LibraryW;
  if ( !LibraryW )
    return GetLastError();
  ProcAddress = GetProcAddress(LibraryW, "GetLogicalProcessorInformation");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !ProcAddress )
    return GetLastError();
  v5 = GetProcAddress(*(HMODULE *)this, "SetThreadPreferredUILanguages");
  *((_QWORD *)this + 2) = v5;
  if ( !v5 )
    return GetLastError();
  v6 = GetProcAddress(*(HMODULE *)this, "GetLocaleInfoEx");
  *((_QWORD *)this + 3) = v6;
  if ( !v6 )
    return GetLastError();
  v7 = GetProcAddress(*(HMODULE *)this, "GetNumberFormatEx");
  *((_QWORD *)this + 4) = v7;
  if ( !v7 )
    return GetLastError();
  *((_QWORD *)this + 5) = GetProcAddress(*(HMODULE *)this, "GetPhysicallyInstalledSystemMemory");
  return 0;
}

```

## disassembly

```asm
0x140056cec  push    rbx
0x140056cee  sub     rsp, 20h
0x140056cf2  mov     rbx, rcx
0x140056cf5  lea     rcx, aKernel32Dll_0; "Kernel32.dll"
0x140056cfc  call    cs:__imp_LoadLibraryW
0x140056d02  mov     [rbx], rax
0x140056d05  test    rax, rax
0x140056d08  jnz     short loc_140056D16
0x140056d0a  add     rsp, 20h
0x140056d0e  pop     rbx
0x140056d0f  jmp     cs:__imp_GetLastError
0x140056d16  lea     rdx, aGetlogicalproc; "GetLogicalProcessorInformation"
0x140056d1d  mov     rcx, rax; hModule
0x140056d20  call    cs:__imp_GetProcAddress
0x140056d26  mov     [rbx+8], rax
0x140056d2a  test    rax, rax
0x140056d2d  jz      short loc_140056D0A
0x140056d2f  mov     rcx, [rbx]; hModule
0x140056d32  lea     rdx, aSetthreadprefe; "SetThreadPreferredUILanguages"
0x140056d39  call    cs:__imp_GetProcAddress
0x140056d3f  mov     [rbx+10h], rax
0x140056d43  test    rax, rax
0x140056d46  jz      short loc_140056D0A
0x140056d48  mov     rcx, [rbx]; hModule
0x140056d4b  lea     rdx, aGetlocaleinfoe; "GetLocaleInfoEx"
0x140056d52  call    cs:__imp_GetProcAddress
0x140056d58  mov     [rbx+18h], rax
0x140056d5c  test    rax, rax
0x140056d5f  jz      short loc_140056D0A
0x140056d61  mov     rcx, [rbx]; hModule
0x140056d64  lea     rdx, aGetnumberforma; "GetNumberFormatEx"
0x140056d6b  call    cs:__imp_GetProcAddress
0x140056d71  mov     [rbx+20h], rax
0x140056d75  test    rax, rax
0x140056d78  jz      short loc_140056D0A
0x140056d7a  mov     rcx, [rbx]; hModule
0x140056d7d  lea     rdx, aGetphysicallyi; "GetPhysicallyInstalledSystemMemory"
0x140056d84  call    cs:__imp_GetProcAddress
0x140056d8a  mov     [rbx+28h], rax
0x140056d8e  xor     eax, eax
0x140056d90  add     rsp, 20h
0x140056d94  pop     rbx
0x140056d95  retn
```
