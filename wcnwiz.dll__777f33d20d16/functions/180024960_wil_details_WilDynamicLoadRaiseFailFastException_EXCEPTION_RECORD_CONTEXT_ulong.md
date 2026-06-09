# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180024960`
- end: `0x1800249b0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800217dc`
- `0x180024960`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002497f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002497f`

## string_xrefs

- `0x180024975`: `kernelbase.dll`

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
0x180024960  mov     [rsp+arg_0], rbx
0x180024965  mov     [rsp+arg_8], rsi
0x18002496a  push    rdi
0x18002496b  sub     rsp, 20h
0x18002496f  mov     rsi, rcx
0x180024972  mov     ebx, r8d
0x180024975  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002497c  mov     rdi, rdx
0x18002497f  call    cs:__imp_GetModuleHandleW
0x180024985  mov     rcx, rax
0x180024988  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18002498d  test    rax, rax
0x180024990  jz      short loc_1800249A0
0x180024992  mov     r8d, ebx
0x180024995  mov     rdx, rdi
0x180024998  mov     rcx, rsi
0x18002499b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249a0  mov     rbx, [rsp+28h+arg_0]
0x1800249a5  mov     rsi, [rsp+28h+arg_8]
0x1800249aa  add     rsp, 20h
0x1800249ae  pop     rdi
0x1800249af  retn
```
