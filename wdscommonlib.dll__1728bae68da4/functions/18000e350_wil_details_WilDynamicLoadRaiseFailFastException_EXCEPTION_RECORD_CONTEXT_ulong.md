# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000e350`
- end: `0x18000e3b5`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e350`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000e385`
- `KERNEL32!GetProcAddress` at `0x18000e385`
- `KERNEL32!GetModuleHandleW` at `0x18000e36f`
- `KERNEL32!GetModuleHandleW` at `0x18000e36f`

## string_xrefs

- `0x18000e365`: `kernelbase.dll`

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
0x18000e350  mov     [rsp+arg_0], rbx
0x18000e355  mov     [rsp+arg_8], rsi
0x18000e35a  push    rdi
0x18000e35b  sub     rsp, 20h
0x18000e35f  mov     rsi, rcx
0x18000e362  mov     ebx, r8d
0x18000e365  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000e36c  mov     rdi, rdx
0x18000e36f  call    cs:__imp_GetModuleHandleW
0x18000e376  nop     dword ptr [rax+rax+00h]
0x18000e37b  mov     rcx, rax; hModule
0x18000e37e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000e385  call    cs:__imp_GetProcAddress
0x18000e38c  nop     dword ptr [rax+rax+00h]
0x18000e391  test    rax, rax
0x18000e394  jz      short loc_18000E3A4
0x18000e396  mov     r8d, ebx
0x18000e399  mov     rdx, rdi
0x18000e39c  mov     rcx, rsi
0x18000e39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3a4  mov     rbx, [rsp+28h+arg_0]
0x18000e3a9  mov     rsi, [rsp+28h+arg_8]
0x18000e3ae  add     rsp, 20h
0x18000e3b2  pop     rdi
0x18000e3b3  retn
```
