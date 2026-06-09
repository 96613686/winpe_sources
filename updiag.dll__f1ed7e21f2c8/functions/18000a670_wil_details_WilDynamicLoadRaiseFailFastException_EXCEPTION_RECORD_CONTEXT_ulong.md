# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a670`
- end: `0x18000a6c8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a670`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a68f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a68f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a69f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a69f`

## string_xrefs

- `0x18000a685`: `kernelbase.dll`

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
0x18000a670  mov     [rsp+arg_0], rbx
0x18000a675  mov     [rsp+arg_8], rsi
0x18000a67a  push    rdi
0x18000a67b  sub     rsp, 20h
0x18000a67f  mov     rsi, rcx
0x18000a682  mov     ebx, r8d
0x18000a685  lea     rcx, ModuleName; "kernelbase.dll"
0x18000a68c  mov     rdi, rdx
0x18000a68f  call    cs:__imp_GetModuleHandleW
0x18000a695  mov     rcx, rax; hModule
0x18000a698  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000a69f  call    cs:__imp_GetProcAddress
0x18000a6a5  test    rax, rax
0x18000a6a8  jz      short loc_18000A6B8
0x18000a6aa  mov     r8d, ebx
0x18000a6ad  mov     rdx, rdi
0x18000a6b0  mov     rcx, rsi
0x18000a6b3  call    _guard_dispatch_icall
0x18000a6b8  mov     rbx, [rsp+28h+arg_0]
0x18000a6bd  mov     rsi, [rsp+28h+arg_8]
0x18000a6c2  add     rsp, 20h
0x18000a6c6  pop     rdi
0x18000a6c7  retn
```
