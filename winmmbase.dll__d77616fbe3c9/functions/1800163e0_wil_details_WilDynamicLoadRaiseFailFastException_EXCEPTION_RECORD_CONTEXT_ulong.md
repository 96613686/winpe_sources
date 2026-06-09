# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800163e0`
- end: `0x180016430`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012ff8`
- `0x1800163e0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800163ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800163ff`

## string_xrefs

- `0x1800163f5`: `kernelbase.dll`

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
0x1800163e0  mov     [rsp+arg_0], rbx
0x1800163e5  mov     [rsp+arg_8], rsi
0x1800163ea  push    rdi
0x1800163eb  sub     rsp, 20h
0x1800163ef  mov     rsi, rcx
0x1800163f2  mov     ebx, r8d
0x1800163f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800163fc  mov     rdi, rdx
0x1800163ff  call    cs:__imp_GetModuleHandleW
0x180016405  mov     rcx, rax
0x180016408  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18001640d  test    rax, rax
0x180016410  jz      short loc_180016420
0x180016412  mov     r8d, ebx
0x180016415  mov     rdx, rdi
0x180016418  mov     rcx, rsi
0x18001641b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016420  mov     rbx, [rsp+28h+arg_0]
0x180016425  mov     rsi, [rsp+28h+arg_8]
0x18001642a  add     rsp, 20h
0x18001642e  pop     rdi
0x18001642f  retn
```
