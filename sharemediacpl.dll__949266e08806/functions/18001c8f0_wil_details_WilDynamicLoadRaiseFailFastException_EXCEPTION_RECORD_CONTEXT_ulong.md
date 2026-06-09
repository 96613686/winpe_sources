# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18001c8f0`
- end: `0x18001c948`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c8f0`
- `0x18001e010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001c90f`
- `KERNEL32!GetModuleHandleW` at `0x18001c90f`
- `KERNEL32!GetProcAddress` at `0x18001c91f`
- `KERNEL32!GetProcAddress` at `0x18001c91f`

## string_xrefs

- `0x18001c905`: `kernelbase.dll`

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
0x18001c8f0  mov     [rsp+arg_0], rbx
0x18001c8f5  mov     [rsp+arg_8], rsi
0x18001c8fa  push    rdi
0x18001c8fb  sub     rsp, 20h
0x18001c8ff  mov     rsi, rcx
0x18001c902  mov     ebx, r8d
0x18001c905  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001c90c  mov     rdi, rdx
0x18001c90f  call    cs:__imp_GetModuleHandleW
0x18001c915  mov     rcx, rax; hModule
0x18001c918  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001c91f  call    cs:__imp_GetProcAddress
0x18001c925  test    rax, rax
0x18001c928  jz      short loc_18001C938
0x18001c92a  mov     r8d, ebx
0x18001c92d  mov     rdx, rdi
0x18001c930  mov     rcx, rsi
0x18001c933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c938  mov     rbx, [rsp+28h+arg_0]
0x18001c93d  mov     rsi, [rsp+28h+arg_8]
0x18001c942  add     rsp, 20h
0x18001c946  pop     rdi
0x18001c947  retn
```
