# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140014780`
- end: `0x1400147d8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140014780`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400147af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400147af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001479f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001479f`

## string_xrefs

- `0x140014795`: `kernelbase.dll`

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
0x140014780  mov     [rsp+arg_0], rbx
0x140014785  mov     [rsp+arg_8], rsi
0x14001478a  push    rdi
0x14001478b  sub     rsp, 20h
0x14001478f  mov     rsi, rcx
0x140014792  mov     ebx, r8d
0x140014795  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001479c  mov     rdi, rdx
0x14001479f  call    cs:__imp_GetModuleHandleW
0x1400147a5  mov     rcx, rax; hModule
0x1400147a8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1400147af  call    cs:__imp_GetProcAddress
0x1400147b5  test    rax, rax
0x1400147b8  jz      short loc_1400147C8
0x1400147ba  mov     r8d, ebx
0x1400147bd  mov     rdx, rdi
0x1400147c0  mov     rcx, rsi
0x1400147c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400147c8  mov     rbx, [rsp+28h+arg_0]
0x1400147cd  mov     rsi, [rsp+28h+arg_8]
0x1400147d2  add     rsp, 20h
0x1400147d6  pop     rdi
0x1400147d7  retn
```
