# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006940`
- end: `0x140006998`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006940`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000695f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000695f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000696f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000696f`

## string_xrefs

- `0x140006955`: `kernelbase.dll`

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
0x140006940  mov     [rsp+arg_0], rbx
0x140006945  mov     [rsp+arg_8], rsi
0x14000694a  push    rdi
0x14000694b  sub     rsp, 20h
0x14000694f  mov     rsi, rcx
0x140006952  mov     ebx, r8d
0x140006955  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000695c  mov     rdi, rdx
0x14000695f  call    cs:__imp_GetModuleHandleW
0x140006965  mov     rcx, rax; hModule
0x140006968  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000696f  call    cs:__imp_GetProcAddress
0x140006975  test    rax, rax
0x140006978  jz      short loc_140006988
0x14000697a  mov     r8d, ebx
0x14000697d  mov     rdx, rdi
0x140006980  mov     rcx, rsi
0x140006983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006988  mov     rbx, [rsp+28h+arg_0]
0x14000698d  mov     rsi, [rsp+28h+arg_8]
0x140006992  add     rsp, 20h
0x140006996  pop     rdi
0x140006997  retn
```
