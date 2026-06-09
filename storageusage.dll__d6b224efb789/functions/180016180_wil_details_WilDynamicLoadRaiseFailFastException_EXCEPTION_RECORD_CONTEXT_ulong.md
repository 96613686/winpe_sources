# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180016180`
- end: `0x1800161d0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000dcec`
- `0x180016180`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001619f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001619f`

## string_xrefs

- `0x180016195`: `kernelbase.dll`

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
0x180016180  mov     [rsp+arg_0], rbx
0x180016185  mov     [rsp+arg_8], rsi
0x18001618a  push    rdi
0x18001618b  sub     rsp, 20h
0x18001618f  mov     rsi, rcx
0x180016192  mov     ebx, r8d
0x180016195  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001619c  mov     rdi, rdx
0x18001619f  call    cs:__imp_GetModuleHandleW
0x1800161a5  mov     rcx, rax
0x1800161a8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800161ad  test    rax, rax
0x1800161b0  jz      short loc_1800161C0
0x1800161b2  mov     r8d, ebx
0x1800161b5  mov     rdx, rdi
0x1800161b8  mov     rcx, rsi
0x1800161bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161c0  mov     rbx, [rsp+28h+arg_0]
0x1800161c5  mov     rsi, [rsp+28h+arg_8]
0x1800161ca  add     rsp, 20h
0x1800161ce  pop     rdi
0x1800161cf  retn
```
