# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140009390`
- end: `0x1400093e7`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400037d4`
- `0x140009390`
- `0x140029010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400093af`
- `KERNEL32!GetModuleHandleW` at `0x1400093af`

## string_xrefs

- `0x1400093a5`: `kernelbase.dll`

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
0x140009390  mov     [rsp+arg_0], rbx
0x140009395  mov     [rsp+arg_8], rsi
0x14000939a  push    rdi
0x14000939b  sub     rsp, 20h
0x14000939f  mov     rsi, rcx
0x1400093a2  mov     ebx, r8d
0x1400093a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400093ac  mov     rdi, rdx
0x1400093af  call    cs:__imp_GetModuleHandleW
0x1400093b6  nop     dword ptr [rax+rax+00h]
0x1400093bb  mov     rcx, rax
0x1400093be  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1400093c3  test    rax, rax
0x1400093c6  jz      short loc_1400093D6
0x1400093c8  mov     r8d, ebx
0x1400093cb  mov     rdx, rdi
0x1400093ce  mov     rcx, rsi
0x1400093d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093d6  mov     rbx, [rsp+28h+arg_0]
0x1400093db  mov     rsi, [rsp+28h+arg_8]
0x1400093e0  add     rsp, 20h
0x1400093e4  pop     rdi
0x1400093e5  retn
```
