# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1400031c0`
- end: `0x140003218`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400031c0`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400031ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400031ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400031df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400031df`

## string_xrefs

- `0x1400031d5`: `kernelbase.dll`

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
0x1400031c0  mov     [rsp+arg_0], rbx
0x1400031c5  mov     [rsp+arg_8], rsi
0x1400031ca  push    rdi
0x1400031cb  sub     rsp, 20h
0x1400031cf  mov     rsi, rcx
0x1400031d2  mov     ebx, r8d
0x1400031d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400031dc  mov     rdi, rdx
0x1400031df  call    cs:__imp_GetModuleHandleW
0x1400031e5  mov     rcx, rax; hModule
0x1400031e8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1400031ef  call    cs:__imp_GetProcAddress
0x1400031f5  test    rax, rax
0x1400031f8  jz      short loc_140003208
0x1400031fa  mov     r8d, ebx
0x1400031fd  mov     rdx, rdi
0x140003200  mov     rcx, rsi
0x140003203  call    _guard_dispatch_icall
0x140003208  mov     rbx, [rsp+28h+arg_0]
0x14000320d  mov     rsi, [rsp+28h+arg_8]
0x140003212  add     rsp, 20h
0x140003216  pop     rdi
0x140003217  retn
```
