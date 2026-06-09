# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006bf0`
- end: `0x140006c48`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006bf0`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140006c1f`
- `KERNEL32!GetProcAddress` at `0x140006c1f`
- `KERNEL32!GetModuleHandleW` at `0x140006c0f`
- `KERNEL32!GetModuleHandleW` at `0x140006c0f`

## string_xrefs

- `0x140006c05`: `kernelbase.dll`

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
0x140006bf0  mov     [rsp+arg_0], rbx
0x140006bf5  mov     [rsp+arg_8], rsi
0x140006bfa  push    rdi
0x140006bfb  sub     rsp, 20h
0x140006bff  mov     rsi, rcx
0x140006c02  mov     ebx, r8d
0x140006c05  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140006c0c  mov     rdi, rdx
0x140006c0f  call    cs:__imp_GetModuleHandleW
0x140006c15  mov     rcx, rax; hModule
0x140006c18  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140006c1f  call    cs:__imp_GetProcAddress
0x140006c25  test    rax, rax
0x140006c28  jz      short loc_140006C38
0x140006c2a  mov     r8d, ebx
0x140006c2d  mov     rdx, rdi
0x140006c30  mov     rcx, rsi
0x140006c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c38  mov     rbx, [rsp+28h+arg_0]
0x140006c3d  mov     rsi, [rsp+28h+arg_8]
0x140006c42  add     rsp, 20h
0x140006c46  pop     rdi
0x140006c47  retn
```
