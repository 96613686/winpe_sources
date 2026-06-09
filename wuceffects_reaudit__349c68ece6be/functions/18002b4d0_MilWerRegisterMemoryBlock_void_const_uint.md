# MilWerRegisterMemoryBlock(void const *,uint)

- ea: `0x18002b4d0`
- end: `0x18002b51b`
- name: `?MilWerRegisterMemoryBlock@@YAXPEBXI@Z`
- size: `75`
- prototype: `void __fastcall(const void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002b188`

## callees

- `0x18002b4d0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b4e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b4e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b4fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b4fb`

## string_xrefs

- `0x18002b4df`: `kernel32.dll`

## pseudocode

```c
void __fastcall MilWerRegisterMemoryBlock(const void *a1, unsigned int a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "WerRegisterMemoryBlock");
    if ( ProcAddress )
      ((void (__fastcall *)(const void *, _QWORD))ProcAddress)(a1, a2);
  }
}

```

## disassembly

```asm
0x18002b4d0  mov     [rsp+arg_0], rbx
0x18002b4d5  push    rdi
0x18002b4d6  sub     rsp, 20h
0x18002b4da  mov     rdi, rcx
0x18002b4dd  mov     ebx, edx
0x18002b4df  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18002b4e6  call    cs:__imp_GetModuleHandleW
0x18002b4ec  test    rax, rax
0x18002b4ef  jz      short loc_18002B510
0x18002b4f1  lea     rdx, aWerregistermem; "WerRegisterMemoryBlock"
0x18002b4f8  mov     rcx, rax; hModule
0x18002b4fb  call    cs:__imp_GetProcAddress
0x18002b501  test    rax, rax
0x18002b504  jz      short loc_18002B510
0x18002b506  mov     edx, ebx
0x18002b508  mov     rcx, rdi
0x18002b50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b510  mov     rbx, [rsp+28h+arg_0]
0x18002b515  add     rsp, 20h
0x18002b519  pop     rdi
0x18002b51a  retn
```
