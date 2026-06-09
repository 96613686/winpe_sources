# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009c50`
- end: `0x180009ca8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009c50`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009c6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009c6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009c7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009c7f`

## string_xrefs

- `0x180009c65`: `kernelbase.dll`

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
0x180009c50  mov     [rsp+arg_0], rbx
0x180009c55  mov     [rsp+arg_8], rsi
0x180009c5a  push    rdi
0x180009c5b  sub     rsp, 20h
0x180009c5f  mov     rsi, rcx
0x180009c62  mov     ebx, r8d
0x180009c65  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009c6c  mov     rdi, rdx
0x180009c6f  call    cs:__imp_GetModuleHandleW
0x180009c75  mov     rcx, rax; hModule
0x180009c78  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180009c7f  call    cs:__imp_GetProcAddress
0x180009c85  test    rax, rax
0x180009c88  jz      short loc_180009C98
0x180009c8a  mov     r8d, ebx
0x180009c8d  mov     rdx, rdi
0x180009c90  mov     rcx, rsi
0x180009c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c98  mov     rbx, [rsp+28h+arg_0]
0x180009c9d  mov     rsi, [rsp+28h+arg_8]
0x180009ca2  add     rsp, 20h
0x180009ca6  pop     rdi
0x180009ca7  retn
```
