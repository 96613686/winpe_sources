# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000b5c0`
- end: `0x18000b625`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b5f5`
- `KERNEL32!GetProcAddress` at `0x18000b5f5`
- `KERNEL32!GetModuleHandleW` at `0x18000b5df`
- `KERNEL32!GetModuleHandleW` at `0x18000b5df`

## string_xrefs

- `0x18000b5d5`: `kernelbase.dll`

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
0x18000b5c0  mov     [rsp+arg_0], rbx
0x18000b5c5  mov     [rsp+arg_8], rsi
0x18000b5ca  push    rdi
0x18000b5cb  sub     rsp, 20h
0x18000b5cf  mov     rsi, rcx
0x18000b5d2  mov     ebx, r8d
0x18000b5d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b5dc  mov     rdi, rdx
0x18000b5df  call    cs:__imp_GetModuleHandleW
0x18000b5e6  nop     dword ptr [rax+rax+00h]
0x18000b5eb  mov     rcx, rax; hModule
0x18000b5ee  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000b5f5  call    cs:__imp_GetProcAddress
0x18000b5fc  nop     dword ptr [rax+rax+00h]
0x18000b601  test    rax, rax
0x18000b604  jz      short loc_18000B614
0x18000b606  mov     r8d, ebx
0x18000b609  mov     rdx, rdi
0x18000b60c  mov     rcx, rsi
0x18000b60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b614  mov     rbx, [rsp+28h+arg_0]
0x18000b619  mov     rsi, [rsp+28h+arg_8]
0x18000b61e  add     rsp, 20h
0x18000b622  pop     rdi
0x18000b623  retn
```
