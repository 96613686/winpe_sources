# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180028230`
- end: `0x1800282a1`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `113`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180028230`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180028270`
- `KERNEL32!GetProcAddress` at `0x180028270`
- `KERNEL32!GetModuleHandleW` at `0x180028259`
- `KERNEL32!GetModuleHandleW` at `0x180028259`

## string_xrefs

- `0x180028252`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v3 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v3);
}

```

## disassembly

```asm
0x180028230  push    rdi
0x180028232  sub     rsp, 30h
0x180028236  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002823f  mov     [rsp+38h+arg_0], rbx
0x180028244  mov     [rsp+38h+arg_8], rsi
0x180028249  mov     ebx, r8d
0x18002824c  mov     rdi, rdx
0x18002824f  mov     rsi, rcx
0x180028252  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180028259  call    cs:__imp_GetModuleHandleW
0x180028260  nop     dword ptr [rax+rax+00h]
0x180028265  nop
0x180028266  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18002826d  mov     rcx, rax; hModule
0x180028270  call    cs:__imp_GetProcAddress
0x180028277  nop     dword ptr [rax+rax+00h]
0x18002827c  nop
0x18002827d  test    rax, rax
0x180028280  jz      short loc_180028290
0x180028282  mov     r8d, ebx
0x180028285  mov     rdx, rdi
0x180028288  mov     rcx, rsi
0x18002828b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028290  mov     rbx, [rsp+38h+arg_0]
0x180028295  mov     rsi, [rsp+38h+arg_8]
0x18002829a  add     rsp, 30h
0x18002829e  pop     rdi
0x18002829f  retn
```
