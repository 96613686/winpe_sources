# CRegistryTreeEventRequest::CreateNewEvent(IWbemClassObject * *)

- ea: `0x180008e20`
- end: `0x180008f6a`
- name: `?CreateNewEvent@CRegistryTreeEventRequest@@UEAAJPEAPEAUIWbemClassObject@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(CRegistryTreeEventRequest *__hidden this, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180008e20`
- `0x180017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008ea0`
- `OLEAUT32!__imp_SysAllocString` at `0x180008eff`
- `OLEAUT32!__imp_SysAllocString` at `0x180008ea0`
- `OLEAUT32!__imp_SysAllocString` at `0x180008eff`
- `OLEAUT32!__imp_VariantInit` at `0x180008e89`
- `OLEAUT32!__imp_VariantInit` at `0x180008eed`
- `OLEAUT32!__imp_VariantInit` at `0x180008e89`
- `OLEAUT32!__imp_VariantInit` at `0x180008eed`
- `OLEAUT32!__imp_VariantClear` at `0x180008ed3`
- `OLEAUT32!__imp_VariantClear` at `0x180008f37`
- `OLEAUT32!__imp_VariantClear` at `0x180008ed3`
- `OLEAUT32!__imp_VariantClear` at `0x180008f37`

## string_xrefs

- `0x180008f17`: `RootPath`

## pseudocode

```c
__int64 __fastcall CRegistryTreeEventRequest::CreateNewEvent(
        CRegistryTreeEventRequest *this,
        struct IWbemClassObject **a2)
{
  __int64 v3; // rax
  struct IWbemClassObject *v5; // rdi
  const OLECHAR *v6; // rcx
  const OLECHAR *v7; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG v10; // [rsp+48h] [rbp-30h] BYREF
  struct IWbemClassObject *v11; // [rsp+80h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = *((_QWORD *)this + 2);
  v11 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, struct IWbemClassObject **))(**(_QWORD **)(v3 + 56) + 120LL))(
         *(_QWORD *)(v3 + 56),
         0,
         &v11) < 0 )
    return 2147749894LL;
  v5 = v11;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = (const OLECHAR *)*((_QWORD *)this + 16);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v6);
  ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v5->lpVtbl->Put)(
    v5,
    L"Hive",
    0,
    &pvarg,
    0);
  VariantClear(&pvarg);
  memset(&v10, 0, sizeof(v10));
  VariantInit(&v10);
  v7 = (const OLECHAR *)*((_QWORD *)this + 17);
  v10.vt = 8;
  v10.llVal = (LONGLONG)SysAllocString(v7);
  ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v11->lpVtbl->Put)(
    v11,
    L"RootPath",
    0,
    &v10,
    0);
  VariantClear(&v10);
  *a2 = v11;
  return 0;
}

```

## disassembly

```asm
0x180008e20  mov     r11, rsp
0x180008e23  push    rbx
0x180008e24  push    rsi
0x180008e25  push    r14
0x180008e27  sub     rsp, 60h
0x180008e2b  xor     r14d, r14d
0x180008e2e  lea     r8, [r11+8]
0x180008e32  mov     [rdx], r14
0x180008e35  mov     rbx, rcx
0x180008e38  mov     rax, [rcx+10h]
0x180008e3c  mov     rsi, rdx
0x180008e3f  mov     [r11+8], r14
0x180008e43  xor     edx, edx
0x180008e45  mov     rcx, [rax+38h]
0x180008e49  mov     rax, [rcx]
0x180008e4c  mov     rax, [rax+78h]
0x180008e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e55  test    eax, eax
0x180008e57  js      loc_180008F63
0x180008e5d  xorps   xmm0, xmm0
0x180008e60  mov     [rsp+78h+arg_8], rbp
0x180008e68  xor     eax, eax
0x180008e6a  mov     [rsp+78h+arg_10], rdi
0x180008e72  mov     rdi, [rsp+78h+arg_0]
0x180008e7a  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180008e7f  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x180008e84  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x180008e89  call    cs:__imp_VariantInit
0x180008e8f  mov     rcx, [rbx+80h]; psz
0x180008e96  mov     ebp, 8
0x180008e9b  mov     word ptr [rsp+78h+pvarg], bp
0x180008ea0  call    cs:__imp_SysAllocString
0x180008ea6  lea     r9, [rsp+78h+pvarg]
0x180008eab  mov     [rsp+78h+var_58], r14d
0x180008eb0  mov     qword ptr [rsp+78h+pvarg+8], rax
0x180008eb5  lea     rdx, aHive; "Hive"
0x180008ebc  mov     rax, [rdi]
0x180008ebf  xor     r8d, r8d
0x180008ec2  mov     rcx, rdi
0x180008ec5  mov     rax, [rax+28h]
0x180008ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ece  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180008ed3  call    cs:__imp_VariantClear
0x180008ed9  xorps   xmm0, xmm0
0x180008edc  lea     rcx, [rsp+78h+var_30]; pvarg
0x180008ee1  xor     eax, eax
0x180008ee3  movups  xmmword ptr [rsp+78h+var_30], xmm0
0x180008ee8  mov     qword ptr [rsp+78h+var_30+10h], rax
0x180008eed  call    cs:__imp_VariantInit
0x180008ef3  mov     rcx, [rbx+88h]; psz
0x180008efa  mov     word ptr [rsp+78h+var_30], bp
0x180008eff  call    cs:__imp_SysAllocString
0x180008f05  mov     rcx, [rsp+78h+arg_0]
0x180008f0d  lea     r9, [rsp+78h+var_30]
0x180008f12  mov     qword ptr [rsp+78h+var_30+8], rax
0x180008f17  lea     rdx, aRootpath; "RootPath"
0x180008f1e  xor     r8d, r8d
0x180008f21  mov     [rsp+78h+var_58], r14d
0x180008f26  mov     rax, [rcx]
0x180008f29  mov     rax, [rax+28h]
0x180008f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f32  lea     rcx, [rsp+78h+var_30]; pvarg
0x180008f37  call    cs:__imp_VariantClear
0x180008f3d  mov     rax, [rsp+78h+arg_0]
0x180008f45  mov     rdi, [rsp+78h+arg_10]
0x180008f4d  mov     rbp, [rsp+78h+arg_8]
0x180008f55  mov     [rsi], rax
0x180008f58  xor     eax, eax
0x180008f5a  add     rsp, 60h
0x180008f5e  pop     r14
0x180008f60  pop     rsi
0x180008f61  pop     rbx
0x180008f62  retn
0x180008f63  mov     eax, 80041006h
0x180008f68  jmp     short loc_180008F5A
```
