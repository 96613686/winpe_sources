# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000cfd0`
- end: `0x18000d028`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000cfd0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cfef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cfef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cfff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cfff`

## string_xrefs

- `0x18000cfe5`: `kernelbase.dll`

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
0x18000cfd0  mov     [rsp+arg_0], rbx
0x18000cfd5  mov     [rsp+arg_8], rsi
0x18000cfda  push    rdi
0x18000cfdb  sub     rsp, 20h
0x18000cfdf  mov     rsi, rcx
0x18000cfe2  mov     ebx, r8d
0x18000cfe5  lea     rcx, LibFileName; "kernelbase.dll"
0x18000cfec  mov     rdi, rdx
0x18000cfef  call    cs:__imp_GetModuleHandleW
0x18000cff5  mov     rcx, rax; hModule
0x18000cff8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000cfff  call    cs:__imp_GetProcAddress
0x18000d005  test    rax, rax
0x18000d008  jz      short loc_18000D018
0x18000d00a  mov     r8d, ebx
0x18000d00d  mov     rdx, rdi
0x18000d010  mov     rcx, rsi
0x18000d013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d018  mov     rbx, [rsp+28h+arg_0]
0x18000d01d  mov     rsi, [rsp+28h+arg_8]
0x18000d022  add     rsp, 20h
0x18000d026  pop     rdi
0x18000d027  retn
```
