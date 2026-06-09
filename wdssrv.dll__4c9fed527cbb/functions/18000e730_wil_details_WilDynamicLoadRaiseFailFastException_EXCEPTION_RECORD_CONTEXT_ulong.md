# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000e730`
- end: `0x18000e795`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e730`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000e74f`
- `KERNEL32!GetModuleHandleW` at `0x18000e74f`
- `KERNEL32!GetProcAddress` at `0x18000e765`
- `KERNEL32!GetProcAddress` at `0x18000e765`

## string_xrefs

- `0x18000e745`: `kernelbase.dll`

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
0x18000e730  mov     [rsp+arg_0], rbx
0x18000e735  mov     [rsp+arg_8], rsi
0x18000e73a  push    rdi
0x18000e73b  sub     rsp, 20h
0x18000e73f  mov     rsi, rcx
0x18000e742  mov     ebx, r8d
0x18000e745  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000e74c  mov     rdi, rdx
0x18000e74f  call    cs:__imp_GetModuleHandleW
0x18000e756  nop     dword ptr [rax+rax+00h]
0x18000e75b  mov     rcx, rax; hModule
0x18000e75e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000e765  call    cs:__imp_GetProcAddress
0x18000e76c  nop     dword ptr [rax+rax+00h]
0x18000e771  test    rax, rax
0x18000e774  jz      short loc_18000E784
0x18000e776  mov     r8d, ebx
0x18000e779  mov     rdx, rdi
0x18000e77c  mov     rcx, rsi
0x18000e77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e784  mov     rbx, [rsp+28h+arg_0]
0x18000e789  mov     rsi, [rsp+28h+arg_8]
0x18000e78e  add     rsp, 20h
0x18000e792  pop     rdi
0x18000e793  retn
```
