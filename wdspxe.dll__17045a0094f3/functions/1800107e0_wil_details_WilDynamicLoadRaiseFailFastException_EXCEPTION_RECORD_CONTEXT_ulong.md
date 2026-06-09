# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800107e0`
- end: `0x180010845`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800107e0`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180010815`
- `KERNEL32!GetProcAddress` at `0x180010815`
- `KERNEL32!GetModuleHandleW` at `0x1800107ff`
- `KERNEL32!GetModuleHandleW` at `0x1800107ff`

## string_xrefs

- `0x1800107f5`: `kernelbase.dll`

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
0x1800107e0  mov     [rsp+arg_0], rbx
0x1800107e5  mov     [rsp+arg_8], rsi
0x1800107ea  push    rdi
0x1800107eb  sub     rsp, 20h
0x1800107ef  mov     rsi, rcx
0x1800107f2  mov     ebx, r8d
0x1800107f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800107fc  mov     rdi, rdx
0x1800107ff  call    cs:__imp_GetModuleHandleW
0x180010806  nop     dword ptr [rax+rax+00h]
0x18001080b  mov     rcx, rax; hModule
0x18001080e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180010815  call    cs:__imp_GetProcAddress
0x18001081c  nop     dword ptr [rax+rax+00h]
0x180010821  test    rax, rax
0x180010824  jz      short loc_180010834
0x180010826  mov     r8d, ebx
0x180010829  mov     rdx, rdi
0x18001082c  mov     rcx, rsi
0x18001082f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010834  mov     rbx, [rsp+28h+arg_0]
0x180010839  mov     rsi, [rsp+28h+arg_8]
0x18001083e  add     rsp, 20h
0x180010842  pop     rdi
0x180010843  retn
```
