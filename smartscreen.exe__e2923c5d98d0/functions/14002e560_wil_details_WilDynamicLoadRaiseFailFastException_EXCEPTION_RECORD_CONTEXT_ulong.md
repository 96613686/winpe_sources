# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14002e560`
- end: `0x14002e5b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14002e560`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002e58f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002e58f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002e57f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002e57f`

## string_xrefs

- `0x14002e575`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x14002e560  mov     [rsp+arg_0], rbx
0x14002e565  mov     [rsp+arg_8], rsi
0x14002e56a  push    rdi
0x14002e56b  sub     rsp, 20h
0x14002e56f  mov     rsi, rcx
0x14002e572  mov     ebx, r8d
0x14002e575  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14002e57c  mov     rdi, rdx
0x14002e57f  call    cs:__imp_GetModuleHandleW
0x14002e585  mov     rcx, rax; hModule
0x14002e588  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14002e58f  call    cs:__imp_GetProcAddress
0x14002e595  test    rax, rax
0x14002e598  jz      short loc_14002E5A8
0x14002e59a  mov     r8d, ebx
0x14002e59d  mov     rdx, rdi
0x14002e5a0  mov     rcx, rsi
0x14002e5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e5a8  mov     rbx, [rsp+28h+arg_0]
0x14002e5ad  mov     rsi, [rsp+28h+arg_8]
0x14002e5b2  add     rsp, 20h
0x14002e5b6  pop     rdi
0x14002e5b7  retn
```
