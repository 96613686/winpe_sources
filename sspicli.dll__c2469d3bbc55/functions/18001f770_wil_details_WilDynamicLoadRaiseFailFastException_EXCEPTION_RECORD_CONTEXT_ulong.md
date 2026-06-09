# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18001f770`
- end: `0x18001f7c8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001f770`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f79f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f79f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f78f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f78f`

## string_xrefs

- `0x18001f785`: `kernelbase.dll`

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
0x18001f770  mov     [rsp+arg_0], rbx
0x18001f775  mov     [rsp+arg_8], rsi
0x18001f77a  push    rdi
0x18001f77b  sub     rsp, 20h
0x18001f77f  mov     rsi, rcx
0x18001f782  mov     ebx, r8d
0x18001f785  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001f78c  mov     rdi, rdx
0x18001f78f  call    cs:__imp_GetModuleHandleW
0x18001f795  mov     rcx, rax; hModule
0x18001f798  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001f79f  call    cs:__imp_GetProcAddress
0x18001f7a5  test    rax, rax
0x18001f7a8  jz      short loc_18001F7B8
0x18001f7aa  mov     r8d, ebx
0x18001f7ad  mov     rdx, rdi
0x18001f7b0  mov     rcx, rsi
0x18001f7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7b8  mov     rbx, [rsp+28h+arg_0]
0x18001f7bd  mov     rsi, [rsp+28h+arg_8]
0x18001f7c2  add     rsp, 20h
0x18001f7c6  pop     rdi
0x18001f7c7  retn
```
