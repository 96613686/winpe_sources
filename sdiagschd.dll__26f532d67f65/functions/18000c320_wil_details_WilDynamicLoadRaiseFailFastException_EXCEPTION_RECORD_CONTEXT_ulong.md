# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c320`
- end: `0x18000c385`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c320`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000c33f`
- `KERNEL32!GetModuleHandleW` at `0x18000c33f`
- `KERNEL32!GetProcAddress` at `0x18000c355`
- `KERNEL32!GetProcAddress` at `0x18000c355`

## string_xrefs

- `0x18000c335`: `kernelbase.dll`

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
0x18000c320  mov     [rsp+arg_0], rbx
0x18000c325  mov     [rsp+arg_8], rsi
0x18000c32a  push    rdi
0x18000c32b  sub     rsp, 20h
0x18000c32f  mov     rsi, rcx
0x18000c332  mov     ebx, r8d
0x18000c335  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c33c  mov     rdi, rdx
0x18000c33f  call    cs:__imp_GetModuleHandleW
0x18000c346  nop     dword ptr [rax+rax+00h]
0x18000c34b  mov     rcx, rax; hModule
0x18000c34e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000c355  call    cs:__imp_GetProcAddress
0x18000c35c  nop     dword ptr [rax+rax+00h]
0x18000c361  test    rax, rax
0x18000c364  jz      short loc_18000C374
0x18000c366  mov     r8d, ebx
0x18000c369  mov     rdx, rdi
0x18000c36c  mov     rcx, rsi
0x18000c36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c374  mov     rbx, [rsp+28h+arg_0]
0x18000c379  mov     rsi, [rsp+28h+arg_8]
0x18000c37e  add     rsp, 20h
0x18000c382  pop     rdi
0x18000c383  retn
```
