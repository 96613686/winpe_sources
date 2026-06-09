# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009fe0`
- end: `0x18000a038`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009fe0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009fff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009fff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a00f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a00f`

## string_xrefs

- `0x180009ff5`: `kernelbase.dll`

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
0x180009fe0  mov     [rsp+arg_0], rbx
0x180009fe5  mov     [rsp+arg_8], rsi
0x180009fea  push    rdi
0x180009feb  sub     rsp, 20h
0x180009fef  mov     rsi, rcx
0x180009ff2  mov     ebx, r8d
0x180009ff5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009ffc  mov     rdi, rdx
0x180009fff  call    cs:__imp_GetModuleHandleW
0x18000a005  mov     rcx, rax; hModule
0x18000a008  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000a00f  call    cs:__imp_GetProcAddress
0x18000a015  test    rax, rax
0x18000a018  jz      short loc_18000A028
0x18000a01a  mov     r8d, ebx
0x18000a01d  mov     rdx, rdi
0x18000a020  mov     rcx, rsi
0x18000a023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a028  mov     rbx, [rsp+28h+arg_0]
0x18000a02d  mov     rsi, [rsp+28h+arg_8]
0x18000a032  add     rsp, 20h
0x18000a036  pop     rdi
0x18000a037  retn
```
