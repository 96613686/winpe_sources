# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008060`
- end: `0x1800080b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008060`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000808f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000808f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000807f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000807f`

## string_xrefs

- `0x180008075`: `kernelbase.dll`

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
0x180008060  mov     [rsp+arg_0], rbx
0x180008065  mov     [rsp+arg_8], rsi
0x18000806a  push    rdi
0x18000806b  sub     rsp, 20h
0x18000806f  mov     rsi, rcx
0x180008072  mov     ebx, r8d
0x180008075  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000807c  mov     rdi, rdx
0x18000807f  call    cs:__imp_GetModuleHandleW
0x180008085  mov     rcx, rax; hModule
0x180008088  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000808f  call    cs:__imp_GetProcAddress
0x180008095  test    rax, rax
0x180008098  jz      short loc_1800080A8
0x18000809a  mov     r8d, ebx
0x18000809d  mov     rdx, rdi
0x1800080a0  mov     rcx, rsi
0x1800080a3  call    _guard_dispatch_icall
0x1800080a8  mov     rbx, [rsp+28h+arg_0]
0x1800080ad  mov     rsi, [rsp+28h+arg_8]
0x1800080b2  add     rsp, 20h
0x1800080b6  pop     rdi
0x1800080b7  retn
```
