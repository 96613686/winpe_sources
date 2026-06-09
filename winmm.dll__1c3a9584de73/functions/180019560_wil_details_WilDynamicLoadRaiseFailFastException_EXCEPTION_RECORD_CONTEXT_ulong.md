# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180019560`
- end: `0x1800195ba`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180019560`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019590`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019590`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001957f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001957f`

## string_xrefs

- `0x180019578`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v3 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v3);
}

```

## disassembly

```asm
0x180019560  mov     [rsp+arg_0], rbx
0x180019565  mov     [rsp+arg_8], rsi
0x18001956a  push    rdi
0x18001956b  sub     rsp, 20h
0x18001956f  mov     ebx, r8d
0x180019572  mov     rdi, rdx
0x180019575  mov     rsi, rcx
0x180019578  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001957f  call    cs:__imp_GetModuleHandleW
0x180019585  nop
0x180019586  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001958d  mov     rcx, rax; hModule
0x180019590  call    cs:__imp_GetProcAddress
0x180019596  nop
0x180019597  test    rax, rax
0x18001959a  jz      short loc_1800195AA
0x18001959c  mov     r8d, ebx
0x18001959f  mov     rdx, rdi
0x1800195a2  mov     rcx, rsi
0x1800195a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195aa  mov     rbx, [rsp+28h+arg_0]
0x1800195af  mov     rsi, [rsp+28h+arg_8]
0x1800195b4  add     rsp, 20h
0x1800195b8  pop     rdi
0x1800195b9  retn
```
