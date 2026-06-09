# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800057d0`
- end: `0x180005828`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800057d0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057ef`

## string_xrefs

- `0x1800057e5`: `kernelbase.dll`

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
0x1800057d0  mov     [rsp+arg_0], rbx
0x1800057d5  mov     [rsp+arg_8], rsi
0x1800057da  push    rdi
0x1800057db  sub     rsp, 20h
0x1800057df  mov     rsi, rcx
0x1800057e2  mov     ebx, r8d
0x1800057e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800057ec  mov     rdi, rdx
0x1800057ef  call    cs:__imp_GetModuleHandleW
0x1800057f5  mov     rcx, rax; hModule
0x1800057f8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800057ff  call    cs:__imp_GetProcAddress
0x180005805  test    rax, rax
0x180005808  jz      short loc_180005818
0x18000580a  mov     r8d, ebx
0x18000580d  mov     rdx, rdi
0x180005810  mov     rcx, rsi
0x180005813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005818  mov     rbx, [rsp+28h+arg_0]
0x18000581d  mov     rsi, [rsp+28h+arg_8]
0x180005822  add     rsp, 20h
0x180005826  pop     rdi
0x180005827  retn
```
