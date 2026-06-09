# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180049c80`
- end: `0x180049cd7`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800479fc`
- `0x180049c80`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180049c9f`
- `KERNEL32!GetModuleHandleW` at `0x180049c9f`

## string_xrefs

- `0x180049c95`: `kernelbase.dll`

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
0x180049c80  mov     [rsp+arg_0], rbx
0x180049c85  mov     [rsp+arg_8], rsi
0x180049c8a  push    rdi
0x180049c8b  sub     rsp, 20h
0x180049c8f  mov     rsi, rcx
0x180049c92  mov     ebx, r8d
0x180049c95  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180049c9c  mov     rdi, rdx
0x180049c9f  call    cs:__imp_GetModuleHandleW
0x180049ca6  nop     dword ptr [rax+rax+00h]
0x180049cab  mov     rcx, rax
0x180049cae  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180049cb3  test    rax, rax
0x180049cb6  jz      short loc_180049CC6
0x180049cb8  mov     r8d, ebx
0x180049cbb  mov     rdx, rdi
0x180049cbe  mov     rcx, rsi
0x180049cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cc6  mov     rbx, [rsp+28h+arg_0]
0x180049ccb  mov     rsi, [rsp+28h+arg_8]
0x180049cd0  add     rsp, 20h
0x180049cd4  pop     rdi
0x180049cd5  retn
```
