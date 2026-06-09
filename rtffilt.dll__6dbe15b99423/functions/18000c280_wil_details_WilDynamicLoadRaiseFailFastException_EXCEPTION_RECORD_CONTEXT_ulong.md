# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c280`
- end: `0x18000c2d8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c280`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c29f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c29f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c2af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c2af`

## string_xrefs

- `0x18000c295`: `kernelbase.dll`

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
0x18000c280  mov     [rsp+arg_0], rbx
0x18000c285  mov     [rsp+arg_8], rsi
0x18000c28a  push    rdi
0x18000c28b  sub     rsp, 20h
0x18000c28f  mov     rsi, rcx
0x18000c292  mov     ebx, r8d
0x18000c295  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c29c  mov     rdi, rdx
0x18000c29f  call    cs:__imp_GetModuleHandleW
0x18000c2a5  mov     rcx, rax; hModule
0x18000c2a8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000c2af  call    cs:__imp_GetProcAddress
0x18000c2b5  test    rax, rax
0x18000c2b8  jz      short loc_18000C2C8
0x18000c2ba  mov     r8d, ebx
0x18000c2bd  mov     rdx, rdi
0x18000c2c0  mov     rcx, rsi
0x18000c2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2c8  mov     rbx, [rsp+28h+arg_0]
0x18000c2cd  mov     rsi, [rsp+28h+arg_8]
0x18000c2d2  add     rsp, 20h
0x18000c2d6  pop     rdi
0x18000c2d7  retn
```
