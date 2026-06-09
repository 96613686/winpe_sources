# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180010650`
- end: `0x1800106a0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000cb0c`
- `0x180010650`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001066f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001066f`

## string_xrefs

- `0x180010665`: `kernelbase.dll`

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
0x180010650  mov     [rsp+arg_0], rbx
0x180010655  mov     [rsp+arg_8], rsi
0x18001065a  push    rdi
0x18001065b  sub     rsp, 20h
0x18001065f  mov     rsi, rcx
0x180010662  mov     ebx, r8d
0x180010665  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001066c  mov     rdi, rdx
0x18001066f  call    cs:__imp_GetModuleHandleW
0x180010675  mov     rcx, rax
0x180010678  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18001067d  test    rax, rax
0x180010680  jz      short loc_180010690
0x180010682  mov     r8d, ebx
0x180010685  mov     rdx, rdi
0x180010688  mov     rcx, rsi
0x18001068b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010690  mov     rbx, [rsp+28h+arg_0]
0x180010695  mov     rsi, [rsp+28h+arg_8]
0x18001069a  add     rsp, 20h
0x18001069e  pop     rdi
0x18001069f  retn
```
