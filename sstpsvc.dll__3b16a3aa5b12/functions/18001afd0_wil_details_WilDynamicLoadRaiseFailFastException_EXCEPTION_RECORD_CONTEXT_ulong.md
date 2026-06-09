# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18001afd0`
- end: `0x18001b028`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001afd0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001afef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001afef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001afff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001afff`

## string_xrefs

- `0x18001afe5`: `kernelbase.dll`

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
0x18001afd0  mov     [rsp+arg_0], rbx
0x18001afd5  mov     [rsp+arg_8], rsi
0x18001afda  push    rdi
0x18001afdb  sub     rsp, 20h
0x18001afdf  mov     rsi, rcx
0x18001afe2  mov     ebx, r8d
0x18001afe5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001afec  mov     rdi, rdx
0x18001afef  call    cs:__imp_GetModuleHandleW
0x18001aff5  mov     rcx, rax; hModule
0x18001aff8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001afff  call    cs:__imp_GetProcAddress
0x18001b005  test    rax, rax
0x18001b008  jz      short loc_18001B018
0x18001b00a  mov     r8d, ebx
0x18001b00d  mov     rdx, rdi
0x18001b010  mov     rcx, rsi
0x18001b013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b018  mov     rbx, [rsp+28h+arg_0]
0x18001b01d  mov     rsi, [rsp+28h+arg_8]
0x18001b022  add     rsp, 20h
0x18001b026  pop     rdi
0x18001b027  retn
```
