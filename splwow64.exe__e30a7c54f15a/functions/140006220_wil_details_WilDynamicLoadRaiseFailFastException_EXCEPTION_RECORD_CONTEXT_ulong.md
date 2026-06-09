# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006220`
- end: `0x140006278`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006220`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000624f`
- `KERNEL32!GetProcAddress` at `0x14000624f`
- `KERNEL32!GetModuleHandleW` at `0x14000623f`
- `KERNEL32!GetModuleHandleW` at `0x14000623f`

## string_xrefs

- `0x140006235`: `kernelbase.dll`

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
0x140006220  mov     [rsp+arg_0], rbx
0x140006225  mov     [rsp+arg_8], rsi
0x14000622a  push    rdi
0x14000622b  sub     rsp, 20h
0x14000622f  mov     rsi, rcx
0x140006232  mov     ebx, r8d
0x140006235  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000623c  mov     rdi, rdx
0x14000623f  call    cs:__imp_GetModuleHandleW
0x140006245  mov     rcx, rax; hModule
0x140006248  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000624f  call    cs:__imp_GetProcAddress
0x140006255  test    rax, rax
0x140006258  jz      short loc_140006268
0x14000625a  mov     r8d, ebx
0x14000625d  mov     rdx, rdi
0x140006260  mov     rcx, rsi
0x140006263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006268  mov     rbx, [rsp+28h+arg_0]
0x14000626d  mov     rsi, [rsp+28h+arg_8]
0x140006272  add     rsp, 20h
0x140006276  pop     rdi
0x140006277  retn
```
