# CPropertyTree::SetNameAndValue(Prop *,SPPHRASEPROPERTY const *)

- ea: `0x180088edc`
- end: `0x180088fcb`
- name: `?SetNameAndValue@CPropertyTree@@QEAAXPEAUProp@@PEBUSPPHRASEPROPERTY@@@Z`
- size: `239`
- prototype: `void __fastcall(CPropertyTree *__hidden this, struct Prop *, const struct SPPHRASEPROPERTY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180088b84`

## callees

- `0x1800172c8`
- `0x18008881c`
- `0x180088860`
- `0x180088edc`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180088efa`
- `OLEAUT32!__imp_VariantInit` at `0x180088efa`
- `OLEAUT32!__imp_VariantClear` at `0x180088fba`
- `OLEAUT32!__imp_VariantClear` at `0x180088fba`
- `OLEAUT32!__imp_VariantCopy` at `0x180088f69`
- `OLEAUT32!__imp_VariantCopy` at `0x180088f69`
- `OLEAUT32!__imp_VariantChangeType` at `0x180088f9c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180088f9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPropertyTree::SetNameAndValue(CPropertyTree *this, struct Prop *a2, const struct SPPHRASEPROPERTY *a3)
{
  __int64 v5; // rcx
  LONGLONG llVal; // rdx
  VARIANT *p_vValue; // rdx
  HRESULT v8; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF

  if ( a2 )
  {
    VariantInit(&pvarg);
    *((_QWORD *)a2 + 5) = a3;
    if ( *((_QWORD *)a2 + 3) )
    {
      if ( a3 && a3->pszValue && a3->pszName )
        ((void (*)(void))ATL::CComBSTR::operator=)();
      else
        ATL::CComBSTR::operator=();
    }
    v5 = *((_QWORD *)a2 + 4);
    if ( !v5 )
      goto LABEL_19;
    if ( !a3 || (llVal = (LONGLONG)a3->pszValue) == 0 )
    {
      ATL::CComBSTR::operator=();
      if ( !a3 )
        goto LABEL_19;
      p_vValue = &a3->vValue;
      if ( !a3->vValue.vt )
        goto LABEL_19;
      if ( &pvarg != p_vValue )
      {
        v8 = VariantCopy(&pvarg, p_vValue);
        if ( v8 < 0 )
        {
          pvarg.vt = 10;
          pvarg.lVal = v8;
          ATL::AtlThrowImpl(v8);
        }
      }
      if ( VariantChangeType(&pvarg, &pvarg, 0, 8u) < 0 )
        goto LABEL_19;
      llVal = pvarg.llVal;
      v5 = *((_QWORD *)a2 + 4);
    }
    ATL::CComBSTR::operator=(v5, llVal);
LABEL_19:
    VariantClear(&pvarg);
  }
}

```

## disassembly

```asm
0x180088edc  test    rdx, rdx
0x180088edf  jz      locret_180088FCA
0x180088ee5  mov     [rsp+arg_0], rbx
0x180088eea  push    rdi
0x180088eeb  sub     rsp, 40h
0x180088eef  mov     rbx, r8
0x180088ef2  mov     rdi, rdx
0x180088ef5  lea     rcx, [rsp+48h+pvarg]; pvarg
0x180088efa  call    cs:__imp_VariantInit
0x180088f00  nop
0x180088f01  mov     [rdi+28h], rbx
0x180088f05  mov     rcx, [rdi+18h]
0x180088f09  test    rcx, rcx
0x180088f0c  jz      short loc_180088F2E
0x180088f0e  test    rbx, rbx
0x180088f11  jz      short loc_180088F29
0x180088f13  cmp     qword ptr [rbx+10h], 0
0x180088f18  jz      short loc_180088F29
0x180088f1a  mov     rdx, [rbx]
0x180088f1d  test    rdx, rdx
0x180088f20  jz      short loc_180088F29
0x180088f22  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180088f27  jmp     short loc_180088F2E
0x180088f29  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBD@Z; ATL::CComBSTR::operator=(char const *)
0x180088f2e  mov     rcx, [rdi+20h]
0x180088f32  test    rcx, rcx
0x180088f35  jz      short loc_180088FB5
0x180088f37  test    rbx, rbx
0x180088f3a  jz      short loc_180088F45
0x180088f3c  mov     rdx, [rbx+10h]
0x180088f40  test    rdx, rdx
0x180088f43  jnz     short loc_180088FAF
0x180088f45  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBD@Z; ATL::CComBSTR::operator=(char const *)
0x180088f4a  test    rbx, rbx
0x180088f4d  jz      short loc_180088FB5
0x180088f4f  lea     rdx, [rbx+18h]; pvargSrc
0x180088f53  xor     eax, eax
0x180088f55  cmp     ax, [rdx]
0x180088f58  jz      short loc_180088FB5
0x180088f5a  lea     rax, [rsp+48h+pvarg]
0x180088f5f  cmp     rax, rdx
0x180088f62  jz      short loc_180088F89
0x180088f64  lea     rcx, [rsp+48h+pvarg]; pvargDest
0x180088f69  call    cs:__imp_VariantCopy
0x180088f6f  test    eax, eax
0x180088f71  jns     short loc_180088F89
0x180088f73  mov     ecx, 0Ah
0x180088f78  mov     word ptr [rsp+48h+pvarg], cx
0x180088f7d  mov     dword ptr [rsp+48h+pvarg+8], eax
0x180088f81  mov     ecx, eax; int
0x180088f83  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180088f89  mov     r9d, 8; vt
0x180088f8f  xor     r8d, r8d; wFlags
0x180088f92  lea     rdx, [rsp+48h+pvarg]; pvarSrc
0x180088f97  lea     rcx, [rsp+48h+pvarg]; pvargDest
0x180088f9c  call    cs:__imp_VariantChangeType
0x180088fa2  test    eax, eax
0x180088fa4  js      short loc_180088FB5
0x180088fa6  mov     rdx, qword ptr [rsp+48h+pvarg+8]
0x180088fab  mov     rcx, [rdi+20h]
0x180088faf  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180088fb4  nop
0x180088fb5  lea     rcx, [rsp+48h+pvarg]; pvarg
0x180088fba  call    cs:__imp_VariantClear
0x180088fc0  mov     rbx, [rsp+48h+arg_0]
0x180088fc5  add     rsp, 40h
0x180088fc9  pop     rdi
0x180088fca  retn
```
