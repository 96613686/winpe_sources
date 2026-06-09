# CImpDyn::Initialize(ushort *,long,ushort *,ushort *,IWbemServices *,IWbemContext *,IWbemProviderInitSink *)

- ea: `0x18000b310`
- end: `0x18000b349`
- name: `?Initialize@CImpDyn@@UEAAJPEAGJ00PEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemProviderInitSink@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(CImpDyn *this, unsigned __int16 *, __int64, unsigned __int16 *, unsigned __int16 *, struct IWbemServices *, struct IWbemContext *, struct IWbemProviderInitSink *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall CImpDyn::Initialize(
        CImpDyn *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IWbemServices *a6,
        struct IWbemContext *a7,
        struct IWbemProviderInitSink *a8)
{
  *((_QWORD *)this + 2) = a6;
  ((void (__fastcall *)(struct IWbemServices *, struct IWbemServices *, __int64, unsigned __int16 *))a6->lpVtbl->AddRef)(
    a6,
    a6,
    a3,
    a4);
  ((void (__fastcall *)(struct IWbemProviderInitSink *, _QWORD, _QWORD))a8->lpVtbl->SetStatus)(a8, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18000b310  sub     rsp, 28h
0x18000b314  mov     rdx, [rsp+28h+arg_28]
0x18000b319  mov     [rcx+10h], rdx
0x18000b31d  mov     rcx, rdx
0x18000b320  mov     rax, [rdx]
0x18000b323  mov     rax, [rax+8]
0x18000b327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b32c  mov     rcx, [rsp+28h+arg_38]
0x18000b331  xor     r8d, r8d
0x18000b334  xor     edx, edx
0x18000b336  mov     rax, [rcx]
0x18000b339  mov     rax, [rax+18h]
0x18000b33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b342  xor     eax, eax
0x18000b344  add     rsp, 28h
0x18000b348  retn
```
