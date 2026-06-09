# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180048700`
- end: `0x180048750`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800465d0`
- `0x180048700`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18004871f`
- `KERNEL32!GetModuleHandleW` at `0x18004871f`

## string_xrefs

- `0x180048715`: `kernelbase.dll`

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
0x180048700  mov     [rsp+arg_0], rbx
0x180048705  mov     [rsp+arg_8], rsi
0x18004870a  push    rdi
0x18004870b  sub     rsp, 20h
0x18004870f  mov     rsi, rcx
0x180048712  mov     ebx, r8d
0x180048715  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18004871c  mov     rdi, rdx
0x18004871f  call    cs:__imp_GetModuleHandleW
0x180048725  mov     rcx, rax
0x180048728  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18004872d  test    rax, rax
0x180048730  jz      short loc_180048740
0x180048732  mov     r8d, ebx
0x180048735  mov     rdx, rdi
0x180048738  mov     rcx, rsi
0x18004873b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048740  mov     rbx, [rsp+28h+arg_0]
0x180048745  mov     rsi, [rsp+28h+arg_8]
0x18004874a  add     rsp, 20h
0x18004874e  pop     rdi
0x18004874f  retn
```
