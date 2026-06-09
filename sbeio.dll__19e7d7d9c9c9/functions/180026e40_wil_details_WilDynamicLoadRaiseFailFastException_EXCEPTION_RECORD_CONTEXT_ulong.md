# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180026e40`
- end: `0x180026e98`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180026e40`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180026e6f`
- `KERNEL32!GetProcAddress` at `0x180026e6f`
- `KERNEL32!GetModuleHandleW` at `0x180026e5f`
- `KERNEL32!GetModuleHandleW` at `0x180026e5f`

## string_xrefs

- `0x180026e55`: `kernelbase.dll`

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
0x180026e40  mov     [rsp+arg_0], rbx
0x180026e45  mov     [rsp+arg_8], rsi
0x180026e4a  push    rdi
0x180026e4b  sub     rsp, 20h
0x180026e4f  mov     rsi, rcx
0x180026e52  mov     ebx, r8d
0x180026e55  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180026e5c  mov     rdi, rdx
0x180026e5f  call    cs:__imp_GetModuleHandleW
0x180026e65  mov     rcx, rax; hModule
0x180026e68  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180026e6f  call    cs:__imp_GetProcAddress
0x180026e75  test    rax, rax
0x180026e78  jz      short loc_180026E88
0x180026e7a  mov     r8d, ebx
0x180026e7d  mov     rdx, rdi
0x180026e80  mov     rcx, rsi
0x180026e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e88  mov     rbx, [rsp+28h+arg_0]
0x180026e8d  mov     rsi, [rsp+28h+arg_8]
0x180026e92  add     rsp, 20h
0x180026e96  pop     rdi
0x180026e97  retn
```
