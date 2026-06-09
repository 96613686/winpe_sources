# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005990`
- end: `0x1800059e8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005990`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800059bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800059bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059af`

## string_xrefs

- `0x1800059a5`: `kernelbase.dll`

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
0x180005990  mov     [rsp+arg_0], rbx
0x180005995  mov     [rsp+arg_8], rsi
0x18000599a  push    rdi
0x18000599b  sub     rsp, 20h
0x18000599f  mov     rsi, rcx
0x1800059a2  mov     ebx, r8d
0x1800059a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800059ac  mov     rdi, rdx
0x1800059af  call    cs:__imp_GetModuleHandleW
0x1800059b5  mov     rcx, rax; hModule
0x1800059b8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800059bf  call    cs:__imp_GetProcAddress
0x1800059c5  test    rax, rax
0x1800059c8  jz      short loc_1800059D8
0x1800059ca  mov     r8d, ebx
0x1800059cd  mov     rdx, rdi
0x1800059d0  mov     rcx, rsi
0x1800059d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d8  mov     rbx, [rsp+28h+arg_0]
0x1800059dd  mov     rsi, [rsp+28h+arg_8]
0x1800059e2  add     rsp, 20h
0x1800059e6  pop     rdi
0x1800059e7  retn
```
