# try_cor_exit_process

- ea: `0x10041a384`
- end: `0x10041a3f3`
- name: `try_cor_exit_process`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10041a258`
- `0x10041a324`

## callees

- `0x10041a384`
- `0x1004245a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x10041a3e6`
- `KERNEL32!FreeLibrary` at `0x10041a3e6`
- `KERNEL32!GetProcAddress` at `0x10041a3bf`
- `KERNEL32!GetProcAddress` at `0x10041a3bf`
- `KERNEL32!GetModuleHandleExW` at `0x10041a3a9`
- `KERNEL32!GetModuleHandleExW` at `0x10041a3a9`

## string_xrefs

- `0x10041a3a0`: `mscoree.dll`

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
0x10041a384  push    rbx
0x10041a386  sub     rsp, 30h
0x10041a38a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10041a393  mov     ebx, ecx
0x10041a395  and     [rsp+38h+phModule], 0
0x10041a39b  lea     r8, [rsp+38h+phModule]; phModule
0x10041a3a0  lea     rdx, ModuleName; "mscoree.dll"
0x10041a3a7  xor     ecx, ecx; dwFlags
0x10041a3a9  call    cs:__imp_GetModuleHandleExW
0x10041a3af  mov     rcx, [rsp+38h+phModule]; hModule
0x10041a3b4  test    eax, eax
0x10041a3b6  jz      short loc_10041A3E1
0x10041a3b8  lea     rdx, ProcName; "CorExitProcess"
0x10041a3bf  call    cs:__imp_GetProcAddress
0x10041a3c5  test    rax, rax
0x10041a3c8  jz      short loc_10041A3DC
0x10041a3ca  mov     r10, 0A201879B5E5A7B70h
0x10041a3d4  mov     ecx, ebx
0x10041a3d6  call    cs:__guard_xfg_dispatch_icall_fptr
0x10041a3dc  mov     rcx, [rsp+38h+phModule]; hLibModule
0x10041a3e1  test    rcx, rcx
0x10041a3e4  jz      short loc_10041A3ED
0x10041a3e6  call    cs:__imp_FreeLibrary
0x10041a3ec  nop
0x10041a3ed  add     rsp, 30h
0x10041a3f1  pop     rbx
0x10041a3f2  retn
```
