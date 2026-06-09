# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006bf0`
- end: `0x180006c40`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003148`
- `0x180006bf0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c0f`

## string_xrefs

- `0x180006c05`: `kernelbase.dll`

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
0x180006bf0  mov     [rsp+arg_0], rbx
0x180006bf5  mov     [rsp+arg_8], rsi
0x180006bfa  push    rdi
0x180006bfb  sub     rsp, 20h
0x180006bff  mov     rsi, rcx
0x180006c02  mov     ebx, r8d
0x180006c05  lea     rcx, ModuleName; "kernelbase.dll"
0x180006c0c  mov     rdi, rdx
0x180006c0f  call    cs:__imp_GetModuleHandleW
0x180006c15  mov     rcx, rax
0x180006c18  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180006c1d  test    rax, rax
0x180006c20  jz      short loc_180006C30
0x180006c22  mov     r8d, ebx
0x180006c25  mov     rdx, rdi
0x180006c28  mov     rcx, rsi
0x180006c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c30  mov     rbx, [rsp+28h+arg_0]
0x180006c35  mov     rsi, [rsp+28h+arg_8]
0x180006c3a  add     rsp, 20h
0x180006c3e  pop     rdi
0x180006c3f  retn
```
