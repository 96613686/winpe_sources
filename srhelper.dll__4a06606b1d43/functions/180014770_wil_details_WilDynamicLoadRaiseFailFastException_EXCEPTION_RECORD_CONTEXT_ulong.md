# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180014770`
- end: `0x1800147c8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014770`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001479f`
- `KERNEL32!GetProcAddress` at `0x18001479f`
- `KERNEL32!GetModuleHandleW` at `0x18001478f`
- `KERNEL32!GetModuleHandleW` at `0x18001478f`

## string_xrefs

- `0x180014785`: `kernelbase.dll`

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
0x180014770  mov     [rsp+arg_0], rbx
0x180014775  mov     [rsp+arg_8], rsi
0x18001477a  push    rdi
0x18001477b  sub     rsp, 20h
0x18001477f  mov     rsi, rcx
0x180014782  mov     ebx, r8d
0x180014785  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001478c  mov     rdi, rdx
0x18001478f  call    cs:__imp_GetModuleHandleW
0x180014795  mov     rcx, rax; hModule
0x180014798  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001479f  call    cs:__imp_GetProcAddress
0x1800147a5  test    rax, rax
0x1800147a8  jz      short loc_1800147B8
0x1800147aa  mov     r8d, ebx
0x1800147ad  mov     rdx, rdi
0x1800147b0  mov     rcx, rsi
0x1800147b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147b8  mov     rbx, [rsp+28h+arg_0]
0x1800147bd  mov     rsi, [rsp+28h+arg_8]
0x1800147c2  add     rsp, 20h
0x1800147c6  pop     rdi
0x1800147c7  retn
```
