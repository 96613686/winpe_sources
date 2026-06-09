# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180027010`
- end: `0x180027060`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180024124`
- `0x180027010`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002702f`
- `KERNEL32!GetModuleHandleW` at `0x18002702f`

## string_xrefs

- `0x180027025`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x180027010  mov     [rsp+arg_0], rbx
0x180027015  mov     [rsp+arg_8], rsi
0x18002701a  push    rdi
0x18002701b  sub     rsp, 20h
0x18002701f  mov     rsi, rcx
0x180027022  mov     ebx, r8d
0x180027025  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002702c  mov     rdi, rdx
0x18002702f  call    cs:__imp_GetModuleHandleW
0x180027035  mov     rcx, rax
0x180027038  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18002703d  test    rax, rax
0x180027040  jz      short loc_180027050
0x180027042  mov     r8d, ebx
0x180027045  mov     rdx, rdi
0x180027048  mov     rcx, rsi
0x18002704b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027050  mov     rbx, [rsp+28h+arg_0]
0x180027055  mov     rsi, [rsp+28h+arg_8]
0x18002705a  add     rsp, 20h
0x18002705e  pop     rdi
0x18002705f  retn
```
