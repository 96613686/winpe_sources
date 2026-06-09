# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000cb90`
- end: `0x14000cbe8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000cb90`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000cbaf`
- `KERNEL32!GetModuleHandleW` at `0x14000cbaf`
- `KERNEL32!GetProcAddress` at `0x14000cbbf`
- `KERNEL32!GetProcAddress` at `0x14000cbbf`

## string_xrefs

- `0x14000cba5`: `kernelbase.dll`

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
0x14000cb90  mov     [rsp+arg_0], rbx
0x14000cb95  mov     [rsp+arg_8], rsi
0x14000cb9a  push    rdi
0x14000cb9b  sub     rsp, 20h
0x14000cb9f  mov     rsi, rcx
0x14000cba2  mov     ebx, r8d
0x14000cba5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000cbac  mov     rdi, rdx
0x14000cbaf  call    cs:__imp_GetModuleHandleW
0x14000cbb5  mov     rcx, rax; hModule
0x14000cbb8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000cbbf  call    cs:__imp_GetProcAddress
0x14000cbc5  test    rax, rax
0x14000cbc8  jz      short loc_14000CBD8
0x14000cbca  mov     r8d, ebx
0x14000cbcd  mov     rdx, rdi
0x14000cbd0  mov     rcx, rsi
0x14000cbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbd8  mov     rbx, [rsp+28h+arg_0]
0x14000cbdd  mov     rsi, [rsp+28h+arg_8]
0x14000cbe2  add     rsp, 20h
0x14000cbe6  pop     rdi
0x14000cbe7  retn
```
