# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180022a20`
- end: `0x180022a78`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180022a20`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022a3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022a3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022a4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022a4f`

## string_xrefs

- `0x180022a35`: `kernelbase.dll`

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
0x180022a20  mov     [rsp+arg_0], rbx
0x180022a25  mov     [rsp+arg_8], rsi
0x180022a2a  push    rdi
0x180022a2b  sub     rsp, 20h
0x180022a2f  mov     rsi, rcx
0x180022a32  mov     ebx, r8d
0x180022a35  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180022a3c  mov     rdi, rdx
0x180022a3f  call    cs:__imp_GetModuleHandleW
0x180022a45  mov     rcx, rax; hModule
0x180022a48  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180022a4f  call    cs:__imp_GetProcAddress
0x180022a55  test    rax, rax
0x180022a58  jz      short loc_180022A68
0x180022a5a  mov     r8d, ebx
0x180022a5d  mov     rdx, rdi
0x180022a60  mov     rcx, rsi
0x180022a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a68  mov     rbx, [rsp+28h+arg_0]
0x180022a6d  mov     rsi, [rsp+28h+arg_8]
0x180022a72  add     rsp, 20h
0x180022a76  pop     rdi
0x180022a77  retn
```
