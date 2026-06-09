# CRegistryEventRequest::SetCommonProperties(IWbemClassObject *)

- ea: `0x18000a68c`
- end: `0x18000a710`
- name: `?SetCommonProperties@CRegistryEventRequest@@IEAAJPEAUIWbemClassObject@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(CRegistryEventRequest *__hidden this, struct IWbemClassObject *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000af80`
- `0x18000b380`

## callees

- `0x180017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a6c7`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a6c7`
- `OLEAUT32!__imp_VariantInit` at `0x18000a6b0`
- `OLEAUT32!__imp_VariantInit` at `0x18000a6b0`
- `OLEAUT32!__imp_VariantClear` at `0x18000a6fd`
- `OLEAUT32!__imp_VariantClear` at `0x18000a6fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegistryEventRequest::SetCommonProperties(CRegistryEventRequest *this, struct IWbemClassObject *a2)
{
  const OLECHAR *v4; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = (const OLECHAR *)*((_QWORD *)this + 16);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v4);
  ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
    a2,
    L"Hive",
    0,
    &pvarg,
    0);
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x18000a68c  mov     [rsp+arg_0], rbx
0x18000a691  push    rdi
0x18000a692  sub     rsp, 50h
0x18000a696  mov     rbx, rcx
0x18000a699  xorps   xmm0, xmm0
0x18000a69c  xor     eax, eax
0x18000a69e  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18000a6a3  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x18000a6a8  mov     qword ptr [rsp+58h+pvarg+10h], rax
0x18000a6ad  mov     rdi, rdx
0x18000a6b0  call    cs:__imp_VariantInit
0x18000a6b6  mov     rcx, [rbx+80h]; psz
0x18000a6bd  mov     eax, 8
0x18000a6c2  mov     word ptr [rsp+58h+pvarg], ax
0x18000a6c7  call    cs:__imp_SysAllocString
0x18000a6cd  lea     r9, [rsp+58h+pvarg]
0x18000a6d2  mov     [rsp+58h+var_38], 0
0x18000a6da  mov     qword ptr [rsp+58h+pvarg+8], rax
0x18000a6df  lea     rdx, aHive; "Hive"
0x18000a6e6  mov     rax, [rdi]
0x18000a6e9  xor     r8d, r8d
0x18000a6ec  mov     rcx, rdi
0x18000a6ef  mov     rax, [rax+28h]
0x18000a6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6f8  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18000a6fd  call    cs:__imp_VariantClear
0x18000a703  mov     rbx, [rsp+58h+arg_0]
0x18000a708  xor     eax, eax
0x18000a70a  add     rsp, 50h
0x18000a70e  pop     rdi
0x18000a70f  retn
```
