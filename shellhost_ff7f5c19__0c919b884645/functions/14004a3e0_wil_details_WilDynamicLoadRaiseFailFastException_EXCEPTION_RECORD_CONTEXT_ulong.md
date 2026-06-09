# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14004a3e0`
- end: `0x14004a438`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14004a3e0`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004a40f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004a40f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14004a3ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14004a3ff`

## string_xrefs

- `0x14004a3f5`: `kernelbase.dll`

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
0x14004a3e0  mov     [rsp+arg_0], rbx
0x14004a3e5  mov     [rsp+arg_8], rsi
0x14004a3ea  push    rdi
0x14004a3eb  sub     rsp, 20h
0x14004a3ef  mov     rsi, rcx
0x14004a3f2  mov     ebx, r8d
0x14004a3f5  lea     rcx, ModuleName; "kernelbase.dll"
0x14004a3fc  mov     rdi, rdx
0x14004a3ff  call    cs:__imp_GetModuleHandleW
0x14004a405  mov     rcx, rax; hModule
0x14004a408  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14004a40f  call    cs:__imp_GetProcAddress
0x14004a415  test    rax, rax
0x14004a418  jz      short loc_14004A428
0x14004a41a  mov     r8d, ebx
0x14004a41d  mov     rdx, rdi
0x14004a420  mov     rcx, rsi
0x14004a423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a428  mov     rbx, [rsp+28h+arg_0]
0x14004a42d  mov     rsi, [rsp+28h+arg_8]
0x14004a432  add     rsp, 20h
0x14004a436  pop     rdi
0x14004a437  retn
```
