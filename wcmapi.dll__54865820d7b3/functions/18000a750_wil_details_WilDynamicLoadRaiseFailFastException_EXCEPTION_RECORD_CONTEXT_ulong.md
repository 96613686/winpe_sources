# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a750`
- end: `0x18000a7a7`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009730`
- `0x18000a750`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a76f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a76f`

## string_xrefs

- `0x18000a765`: `kernelbase.dll`

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
0x18000a750  mov     [rsp+arg_0], rbx
0x18000a755  mov     [rsp+arg_8], rsi
0x18000a75a  push    rdi
0x18000a75b  sub     rsp, 20h
0x18000a75f  mov     rsi, rcx
0x18000a762  mov     ebx, r8d
0x18000a765  lea     rcx, ModuleName; "kernelbase.dll"
0x18000a76c  mov     rdi, rdx
0x18000a76f  call    cs:__imp_GetModuleHandleW
0x18000a776  nop     dword ptr [rax+rax+00h]
0x18000a77b  mov     rcx, rax
0x18000a77e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000a783  test    rax, rax
0x18000a786  jz      short loc_18000A796
0x18000a788  mov     r8d, ebx
0x18000a78b  mov     rdx, rdi
0x18000a78e  mov     rcx, rsi
0x18000a791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a796  mov     rbx, [rsp+28h+arg_0]
0x18000a79b  mov     rsi, [rsp+28h+arg_8]
0x18000a7a0  add     rsp, 20h
0x18000a7a4  pop     rdi
0x18000a7a5  retn
```
