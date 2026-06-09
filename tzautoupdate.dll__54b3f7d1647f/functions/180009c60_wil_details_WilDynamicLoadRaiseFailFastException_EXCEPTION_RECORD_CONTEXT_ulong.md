# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009c60`
- end: `0x180009cb0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003384`
- `0x180009c60`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009c7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009c7f`

## string_xrefs

- `0x180009c75`: `kernelbase.dll`

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
0x180009c60  mov     [rsp+arg_0], rbx
0x180009c65  mov     [rsp+arg_8], rsi
0x180009c6a  push    rdi
0x180009c6b  sub     rsp, 20h
0x180009c6f  mov     rsi, rcx
0x180009c72  mov     ebx, r8d
0x180009c75  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009c7c  mov     rdi, rdx
0x180009c7f  call    cs:__imp_GetModuleHandleW
0x180009c85  mov     rcx, rax
0x180009c88  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180009c8d  test    rax, rax
0x180009c90  jz      short loc_180009CA0
0x180009c92  mov     r8d, ebx
0x180009c95  mov     rdx, rdi
0x180009c98  mov     rcx, rsi
0x180009c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ca0  mov     rbx, [rsp+28h+arg_0]
0x180009ca5  mov     rsi, [rsp+28h+arg_8]
0x180009caa  add     rsp, 20h
0x180009cae  pop     rdi
0x180009caf  retn
```
