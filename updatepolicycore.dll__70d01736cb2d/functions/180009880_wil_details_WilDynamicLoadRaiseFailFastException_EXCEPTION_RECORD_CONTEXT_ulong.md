# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009880`
- end: `0x1800098d8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009880`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000989f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000989f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800098af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800098af`

## string_xrefs

- `0x180009895`: `kernelbase.dll`

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
0x180009880  mov     [rsp+arg_0], rbx
0x180009885  mov     [rsp+arg_8], rsi
0x18000988a  push    rdi
0x18000988b  sub     rsp, 20h
0x18000988f  mov     rsi, rcx
0x180009892  mov     ebx, r8d
0x180009895  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000989c  mov     rdi, rdx
0x18000989f  call    cs:__imp_GetModuleHandleW
0x1800098a5  mov     rcx, rax; hModule
0x1800098a8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800098af  call    cs:__imp_GetProcAddress
0x1800098b5  test    rax, rax
0x1800098b8  jz      short loc_1800098C8
0x1800098ba  mov     r8d, ebx
0x1800098bd  mov     rdx, rdi
0x1800098c0  mov     rcx, rsi
0x1800098c3  call    _guard_dispatch_icall
0x1800098c8  mov     rbx, [rsp+28h+arg_0]
0x1800098cd  mov     rsi, [rsp+28h+arg_8]
0x1800098d2  add     rsp, 20h
0x1800098d6  pop     rdi
0x1800098d7  retn
```
