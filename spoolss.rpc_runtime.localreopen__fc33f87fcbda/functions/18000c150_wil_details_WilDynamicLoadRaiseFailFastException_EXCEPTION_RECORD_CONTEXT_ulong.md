# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c150`
- end: `0x18000c1a7`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006a94`
- `0x18000c150`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c16f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c16f`

## string_xrefs

- `0x18000c165`: `kernelbase.dll`

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
0x18000c150  mov     [rsp+arg_0], rbx
0x18000c155  mov     [rsp+arg_8], rsi
0x18000c15a  push    rdi
0x18000c15b  sub     rsp, 20h
0x18000c15f  mov     rsi, rcx
0x18000c162  mov     ebx, r8d
0x18000c165  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c16c  mov     rdi, rdx
0x18000c16f  call    cs:__imp_GetModuleHandleW
0x18000c176  nop     dword ptr [rax+rax+00h]
0x18000c17b  mov     rcx, rax
0x18000c17e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000c183  test    rax, rax
0x18000c186  jz      short loc_18000C196
0x18000c188  mov     r8d, ebx
0x18000c18b  mov     rdx, rdi
0x18000c18e  mov     rcx, rsi
0x18000c191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c196  mov     rbx, [rsp+28h+arg_0]
0x18000c19b  mov     rsi, [rsp+28h+arg_8]
0x18000c1a0  add     rsp, 20h
0x18000c1a4  pop     rdi
0x18000c1a5  retn
```
