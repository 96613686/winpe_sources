# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180011bb0`
- end: `0x180011c0a`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011bb0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011bcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011bcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011be0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011be0`

## string_xrefs

- `0x180011bc8`: `kernelbase.dll`

## pseudocode

```c
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
0x180011bb0  mov     [rsp+arg_0], rbx
0x180011bb5  mov     [rsp+arg_8], rsi
0x180011bba  push    rdi
0x180011bbb  sub     rsp, 20h
0x180011bbf  mov     ebx, r8d
0x180011bc2  mov     rdi, rdx
0x180011bc5  mov     rsi, rcx
0x180011bc8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180011bcf  call    cs:__imp_GetModuleHandleW
0x180011bd5  nop
0x180011bd6  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180011bdd  mov     rcx, rax; hModule
0x180011be0  call    cs:__imp_GetProcAddress
0x180011be6  nop
0x180011be7  test    rax, rax
0x180011bea  jz      short loc_180011BFA
0x180011bec  mov     r8d, ebx
0x180011bef  mov     rdx, rdi
0x180011bf2  mov     rcx, rsi
0x180011bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bfa  mov     rbx, [rsp+28h+arg_0]
0x180011bff  mov     rsi, [rsp+28h+arg_8]
0x180011c04  add     rsp, 20h
0x180011c08  pop     rdi
0x180011c09  retn
```
