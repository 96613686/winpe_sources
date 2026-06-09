# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005c70`
- end: `0x180005cc8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005c70`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c8f`

## string_xrefs

- `0x180005c85`: `kernelbase.dll`

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
0x180005c70  mov     [rsp+arg_0], rbx
0x180005c75  mov     [rsp+arg_8], rsi
0x180005c7a  push    rdi
0x180005c7b  sub     rsp, 20h
0x180005c7f  mov     rsi, rcx
0x180005c82  mov     ebx, r8d
0x180005c85  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005c8c  mov     rdi, rdx
0x180005c8f  call    cs:__imp_GetModuleHandleW
0x180005c95  mov     rcx, rax; hModule
0x180005c98  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180005c9f  call    cs:__imp_GetProcAddress
0x180005ca5  test    rax, rax
0x180005ca8  jz      short loc_180005CB8
0x180005caa  mov     r8d, ebx
0x180005cad  mov     rdx, rdi
0x180005cb0  mov     rcx, rsi
0x180005cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cb8  mov     rbx, [rsp+28h+arg_0]
0x180005cbd  mov     rsi, [rsp+28h+arg_8]
0x180005cc2  add     rsp, 20h
0x180005cc6  pop     rdi
0x180005cc7  retn
```
