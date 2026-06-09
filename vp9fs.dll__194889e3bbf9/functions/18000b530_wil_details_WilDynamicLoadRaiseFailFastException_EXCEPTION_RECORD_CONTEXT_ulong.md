# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000b530`
- end: `0x18000b588`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b530`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b55f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b55f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b54f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b54f`

## string_xrefs

- `0x18000b545`: `kernelbase.dll`

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
0x18000b530  mov     [rsp+arg_0], rbx
0x18000b535  mov     [rsp+arg_8], rsi
0x18000b53a  push    rdi
0x18000b53b  sub     rsp, 20h
0x18000b53f  mov     rsi, rcx
0x18000b542  mov     ebx, r8d
0x18000b545  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b54c  mov     rdi, rdx
0x18000b54f  call    cs:__imp_GetModuleHandleW
0x18000b555  mov     rcx, rax; hModule
0x18000b558  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000b55f  call    cs:__imp_GetProcAddress
0x18000b565  test    rax, rax
0x18000b568  jz      short loc_18000B578
0x18000b56a  mov     r8d, ebx
0x18000b56d  mov     rdx, rdi
0x18000b570  mov     rcx, rsi
0x18000b573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b578  mov     rbx, [rsp+28h+arg_0]
0x18000b57d  mov     rsi, [rsp+28h+arg_8]
0x18000b582  add     rsp, 20h
0x18000b586  pop     rdi
0x18000b587  retn
```
