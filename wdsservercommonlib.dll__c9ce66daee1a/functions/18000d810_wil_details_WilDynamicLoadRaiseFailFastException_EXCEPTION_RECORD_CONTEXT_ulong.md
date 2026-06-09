# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000d810`
- end: `0x18000d875`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d810`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d845`
- `KERNEL32!GetProcAddress` at `0x18000d845`
- `KERNEL32!GetModuleHandleW` at `0x18000d82f`
- `KERNEL32!GetModuleHandleW` at `0x18000d82f`

## string_xrefs

- `0x18000d825`: `kernelbase.dll`

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
0x18000d810  mov     [rsp+arg_0], rbx
0x18000d815  mov     [rsp+arg_8], rsi
0x18000d81a  push    rdi
0x18000d81b  sub     rsp, 20h
0x18000d81f  mov     rsi, rcx
0x18000d822  mov     ebx, r8d
0x18000d825  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d82c  mov     rdi, rdx
0x18000d82f  call    cs:__imp_GetModuleHandleW
0x18000d836  nop     dword ptr [rax+rax+00h]
0x18000d83b  mov     rcx, rax; hModule
0x18000d83e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000d845  call    cs:__imp_GetProcAddress
0x18000d84c  nop     dword ptr [rax+rax+00h]
0x18000d851  test    rax, rax
0x18000d854  jz      short loc_18000D864
0x18000d856  mov     r8d, ebx
0x18000d859  mov     rdx, rdi
0x18000d85c  mov     rcx, rsi
0x18000d85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d864  mov     rbx, [rsp+28h+arg_0]
0x18000d869  mov     rsi, [rsp+28h+arg_8]
0x18000d86e  add     rsp, 20h
0x18000d872  pop     rdi
0x18000d873  retn
```
