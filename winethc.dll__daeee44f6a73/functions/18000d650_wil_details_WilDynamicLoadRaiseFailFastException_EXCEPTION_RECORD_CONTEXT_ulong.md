# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000d650`
- end: `0x18000d6b5`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d650`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d685`
- `KERNEL32!GetProcAddress` at `0x18000d685`
- `KERNEL32!GetModuleHandleW` at `0x18000d66f`
- `KERNEL32!GetModuleHandleW` at `0x18000d66f`

## string_xrefs

- `0x18000d665`: `kernelbase.dll`

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
0x18000d650  mov     [rsp+arg_0], rbx
0x18000d655  mov     [rsp+arg_8], rsi
0x18000d65a  push    rdi
0x18000d65b  sub     rsp, 20h
0x18000d65f  mov     rsi, rcx
0x18000d662  mov     ebx, r8d
0x18000d665  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d66c  mov     rdi, rdx
0x18000d66f  call    cs:__imp_GetModuleHandleW
0x18000d676  nop     dword ptr [rax+rax+00h]
0x18000d67b  mov     rcx, rax; hModule
0x18000d67e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000d685  call    cs:__imp_GetProcAddress
0x18000d68c  nop     dword ptr [rax+rax+00h]
0x18000d691  test    rax, rax
0x18000d694  jz      short loc_18000D6A4
0x18000d696  mov     r8d, ebx
0x18000d699  mov     rdx, rdi
0x18000d69c  mov     rcx, rsi
0x18000d69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6a4  mov     rbx, [rsp+28h+arg_0]
0x18000d6a9  mov     rsi, [rsp+28h+arg_8]
0x18000d6ae  add     rsp, 20h
0x18000d6b2  pop     rdi
0x18000d6b3  retn
```
