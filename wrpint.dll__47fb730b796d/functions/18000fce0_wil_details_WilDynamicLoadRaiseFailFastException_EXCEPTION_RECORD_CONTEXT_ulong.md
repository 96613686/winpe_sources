# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000fce0`
- end: `0x18000fd38`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000fce0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fd0f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fd0f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000fcff`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000fcff`

## string_xrefs

- `0x18000fcf5`: `kernelbase.dll`

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
0x18000fce0  mov     [rsp+arg_0], rbx
0x18000fce5  mov     [rsp+arg_8], rsi
0x18000fcea  push    rdi
0x18000fceb  sub     rsp, 20h
0x18000fcef  mov     rsi, rcx
0x18000fcf2  mov     ebx, r8d
0x18000fcf5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000fcfc  mov     rdi, rdx
0x18000fcff  call    cs:__imp_GetModuleHandleW
0x18000fd05  mov     rcx, rax; hModule
0x18000fd08  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000fd0f  call    cs:__imp_GetProcAddress
0x18000fd15  test    rax, rax
0x18000fd18  jz      short loc_18000FD28
0x18000fd1a  mov     r8d, ebx
0x18000fd1d  mov     rdx, rdi
0x18000fd20  mov     rcx, rsi
0x18000fd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd28  mov     rbx, [rsp+28h+arg_0]
0x18000fd2d  mov     rsi, [rsp+28h+arg_8]
0x18000fd32  add     rsp, 20h
0x18000fd36  pop     rdi
0x18000fd37  retn
```
