# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009b20`
- end: `0x180009b77`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006c20`
- `0x180009b20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009b3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009b3f`

## string_xrefs

- `0x180009b35`: `kernelbase.dll`

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
0x180009b20  mov     [rsp+arg_0], rbx
0x180009b25  mov     [rsp+arg_8], rsi
0x180009b2a  push    rdi
0x180009b2b  sub     rsp, 20h
0x180009b2f  mov     rsi, rcx
0x180009b32  mov     ebx, r8d
0x180009b35  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009b3c  mov     rdi, rdx
0x180009b3f  call    cs:__imp_GetModuleHandleW
0x180009b46  nop     dword ptr [rax+rax+00h]
0x180009b4b  mov     rcx, rax
0x180009b4e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180009b53  test    rax, rax
0x180009b56  jz      short loc_180009B66
0x180009b58  mov     r8d, ebx
0x180009b5b  mov     rdx, rdi
0x180009b5e  mov     rcx, rsi
0x180009b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b66  mov     rbx, [rsp+28h+arg_0]
0x180009b6b  mov     rsi, [rsp+28h+arg_8]
0x180009b70  add     rsp, 20h
0x180009b74  pop     rdi
0x180009b75  retn
```
