# try_cor_exit_process

- ea: `0x10042a314`
- end: `0x10042a383`
- name: `try_cor_exit_process`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10042a1e8`
- `0x10042a2b4`

## callees

- `0x10042a314`
- `0x100439e10`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x10042a376`
- `KERNEL32!FreeLibrary` at `0x10042a376`
- `KERNEL32!GetProcAddress` at `0x10042a34f`
- `KERNEL32!GetProcAddress` at `0x10042a34f`
- `KERNEL32!GetModuleHandleExW` at `0x10042a339`
- `KERNEL32!GetModuleHandleExW` at `0x10042a339`

## string_xrefs

- `0x10042a330`: `mscoree.dll`

## pseudocode

```c
int __fastcall try_cor_exit_process(unsigned int a1)
{
  FARPROC ProcAddress; // rax
  HMODULE v3; // rcx
  HMODULE phModule; // [rsp+48h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExW(0, L"mscoree.dll", &phModule);
  v3 = phModule;
  if ( (_DWORD)ProcAddress )
  {
    ProcAddress = GetProcAddress(phModule, "CorExitProcess");
    if ( ProcAddress )
      LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
    v3 = phModule;
  }
  if ( v3 )
    LODWORD(ProcAddress) = FreeLibrary(v3);
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x10042a314  push    rbx
0x10042a316  sub     rsp, 30h
0x10042a31a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10042a323  mov     ebx, ecx
0x10042a325  and     [rsp+38h+phModule], 0
0x10042a32b  lea     r8, [rsp+38h+phModule]; phModule
0x10042a330  lea     rdx, ModuleName; "mscoree.dll"
0x10042a337  xor     ecx, ecx; dwFlags
0x10042a339  call    cs:__imp_GetModuleHandleExW
0x10042a33f  mov     rcx, [rsp+38h+phModule]; hModule
0x10042a344  test    eax, eax
0x10042a346  jz      short loc_10042A371
0x10042a348  lea     rdx, ProcName; "CorExitProcess"
0x10042a34f  call    cs:__imp_GetProcAddress
0x10042a355  test    rax, rax
0x10042a358  jz      short loc_10042A36C
0x10042a35a  mov     r10, 0A201879B5E5A7B70h
0x10042a364  mov     ecx, ebx
0x10042a366  call    cs:__guard_xfg_dispatch_icall_fptr
0x10042a36c  mov     rcx, [rsp+38h+phModule]; hLibModule
0x10042a371  test    rcx, rcx
0x10042a374  jz      short loc_10042A37D
0x10042a376  call    cs:__imp_FreeLibrary
0x10042a37c  nop
0x10042a37d  add     rsp, 30h
0x10042a381  pop     rbx
0x10042a382  retn
```
