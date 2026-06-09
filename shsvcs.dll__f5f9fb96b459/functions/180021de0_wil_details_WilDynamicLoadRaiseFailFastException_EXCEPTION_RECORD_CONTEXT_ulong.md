# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180021de0`
- end: `0x180021e30`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c82c`
- `0x180021de0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021dff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021dff`

## string_xrefs

- `0x180021df5`: `kernelbase.dll`

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
0x180021de0  mov     [rsp+arg_0], rbx
0x180021de5  mov     [rsp+arg_8], rsi
0x180021dea  push    rdi
0x180021deb  sub     rsp, 20h
0x180021def  mov     rsi, rcx
0x180021df2  mov     ebx, r8d
0x180021df5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180021dfc  mov     rdi, rdx
0x180021dff  call    cs:__imp_GetModuleHandleW
0x180021e05  mov     rcx, rax
0x180021e08  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180021e0d  test    rax, rax
0x180021e10  jz      short loc_180021E20
0x180021e12  mov     r8d, ebx
0x180021e15  mov     rdx, rdi
0x180021e18  mov     rcx, rsi
0x180021e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e20  mov     rbx, [rsp+28h+arg_0]
0x180021e25  mov     rsi, [rsp+28h+arg_8]
0x180021e2a  add     rsp, 20h
0x180021e2e  pop     rdi
0x180021e2f  retn
```
