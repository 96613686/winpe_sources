# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008af0`
- end: `0x180008b48`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008af0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b1f`

## string_xrefs

- `0x180008b05`: `kernelbase.dll`

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
0x180008af0  mov     [rsp+arg_0], rbx
0x180008af5  mov     [rsp+arg_8], rsi
0x180008afa  push    rdi
0x180008afb  sub     rsp, 20h
0x180008aff  mov     rsi, rcx
0x180008b02  mov     ebx, r8d
0x180008b05  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008b0c  mov     rdi, rdx
0x180008b0f  call    cs:__imp_GetModuleHandleW
0x180008b15  mov     rcx, rax; hModule
0x180008b18  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180008b1f  call    cs:__imp_GetProcAddress
0x180008b25  test    rax, rax
0x180008b28  jz      short loc_180008B38
0x180008b2a  mov     r8d, ebx
0x180008b2d  mov     rdx, rdi
0x180008b30  mov     rcx, rsi
0x180008b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b38  mov     rbx, [rsp+28h+arg_0]
0x180008b3d  mov     rsi, [rsp+28h+arg_8]
0x180008b42  add     rsp, 20h
0x180008b46  pop     rdi
0x180008b47  retn
```
