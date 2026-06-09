# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180026e00`
- end: `0x180026e58`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180026e00`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180026e2f`
- `KERNEL32!GetProcAddress` at `0x180026e2f`
- `KERNEL32!GetModuleHandleW` at `0x180026e1f`
- `KERNEL32!GetModuleHandleW` at `0x180026e1f`

## string_xrefs

- `0x180026e15`: `kernelbase.dll`

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
0x180026e00  mov     [rsp+arg_0], rbx
0x180026e05  mov     [rsp+arg_8], rsi
0x180026e0a  push    rdi
0x180026e0b  sub     rsp, 20h
0x180026e0f  mov     rsi, rcx
0x180026e12  mov     ebx, r8d
0x180026e15  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180026e1c  mov     rdi, rdx
0x180026e1f  call    cs:__imp_GetModuleHandleW
0x180026e25  mov     rcx, rax; hModule
0x180026e28  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180026e2f  call    cs:__imp_GetProcAddress
0x180026e35  test    rax, rax
0x180026e38  jz      short loc_180026E48
0x180026e3a  mov     r8d, ebx
0x180026e3d  mov     rdx, rdi
0x180026e40  mov     rcx, rsi
0x180026e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e48  mov     rbx, [rsp+28h+arg_0]
0x180026e4d  mov     rsi, [rsp+28h+arg_8]
0x180026e52  add     rsp, 20h
0x180026e56  pop     rdi
0x180026e57  retn
```
