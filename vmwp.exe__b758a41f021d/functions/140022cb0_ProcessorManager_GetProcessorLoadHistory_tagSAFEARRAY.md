# ProcessorManager::GetProcessorLoadHistory(tagSAFEARRAY * *)

- ea: `0x140022cb0`
- end: `0x140022f52`
- name: `?GetProcessorLoadHistory@ProcessorManager@@UEAAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `674`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140022cb0`
- `0x140022f58`
- `0x140023de0`
- `0x140078628`
- `0x14011ea40`
- `0x140121a35`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x140022e45`
- `OLEAUT32!__imp_VariantClear` at `0x140022e45`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140022d64`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140022dd5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140022d64`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140022dd5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022e09`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022e86`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022e09`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022e86`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140022d2e`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140022da6`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140022d2e`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140022da6`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x140022e2a`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x140022e2a`

## string_xrefs

- `0x140022ed0`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140022ee5`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140022f24`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140022f40`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140022efa`: `onecore\vm\common\vml\VmVariant.h`
- `0x140022f0f`: `onecore\vm\common\vml\VmVariant.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ProcessorManager::GetProcessorLoadHistory(ProcessorManager *this, struct tagSAFEARRAY **a2)
{
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY *v4; // r15
  HRESULT v5; // eax
  VARIANTARG *v6; // rdi
  __int64 i; // rbx
  __int64 v8; // r14
  SAFEARRAY *v9; // rax
  SAFEARRAY *v10; // rsi
  HRESULT v11; // eax
  HRESULT Vartype; // eax
  HRESULT v13; // eax
  SAFEARRAY *psa; // [rsp+20h] [rbp-60h]
  void *v15; // [rsp+28h] [rbp-58h] BYREF
  SAFEARRAY *v16; // [rsp+30h] [rbp-50h]
  SAFEARRAY *v17; // [rsp+38h] [rbp-48h]
  VARTYPE pvt; // [rsp+40h] [rbp-40h] BYREF
  __int128 v19; // [rsp+48h] [rbp-38h] BYREF
  __int64 v20; // [rsp+58h] [rbp-28h]
  void *ppvData[2]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a2 = 0;
  v16 = 0;
  v19 = 0;
  v20 = 0;
  VpStatistics::GetProcessorLoadHistory(*((_QWORD *)this + 93), &v19);
  Vector = SafeArrayCreateVectorEx(
             0xCu,
             0,
             -1431655765 * (unsigned int)((__int64)(*((_QWORD *)&v19 + 1) - v19) >> 3),
             0);
  v4 = Vector;
  if ( !Vector )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)0x8007000ELL,
      (int)psa);
  v16 = Vector;
  ppvData[0] = Vector;
  ppvData[1] = 0;
  v5 = SafeArrayAccessData(Vector, &ppvData[1]);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B2,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)(unsigned int)v5,
      (int)psa);
  v6 = (VARIANTARG *)ppvData[1];
  for ( i = v19; i != *((_QWORD *)&v19 + 1); i += 24 )
  {
    v8 = (__int64)(*(_QWORD *)(i + 8) - *(_QWORD *)i) >> 2;
    v9 = SafeArrayCreateVectorEx(0x13u, 0, v8, 0);
    v10 = v9;
    v17 = v9;
    if ( !v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)0x8007000ELL,
        (int)psa);
    psa = v9;
    v15 = 0;
    v11 = SafeArrayAccessData(v9, &v15);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B2,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v11,
        (int)psa);
    memcpy_0(v15, *(const void **)i, 4LL * (unsigned int)v8);
    SafeArrayUnaccessData(psa);
    v17 = 0;
    pvt = 0;
    Vartype = SafeArrayGetVartype(v10, &pvt);
    if ( Vartype < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6ED,
        (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
        (const char *)(unsigned int)Vartype,
        (int)psa);
    v13 = VariantClear(v6);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x723,
        (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
        (const char *)(unsigned int)v13,
        (int)psa);
    v6->vt = pvt | 0x2000;
    v6->llVal = (LONGLONG)v10;
    ++v6;
  }
  *a2 = v4;
  if ( ppvData[0] )
    SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
  std::vector<std::vector<unsigned long>>::_Tidy(&v19);
}

```

## disassembly

```asm
0x140022cb0  mov     [rsp-28h+arg_10], rbx
0x140022cb5  mov     [rsp-28h+arg_18], rsi
0x140022cba  push    rbp
0x140022cbb  push    rdi
0x140022cbc  push    r12
0x140022cbe  push    r14
0x140022cc0  push    r15
0x140022cc2  mov     rbp, rsp
0x140022cc5  sub     rsp, 80h
0x140022ccc  mov     rax, cs:__security_cookie
0x140022cd3  xor     rax, rsp
0x140022cd6  mov     [rbp+var_10], rax
0x140022cda  mov     r12, rdx
0x140022cdd  mov     qword ptr [rdx], 0
0x140022ce4  mov     [rbp+var_50], 0
0x140022cec  xor     eax, eax
0x140022cee  xorps   xmm1, xmm1
0x140022cf1  movdqu  [rbp+var_38], xmm1
0x140022cf6  mov     [rbp+var_28], rax
0x140022cfa  lea     rdx, [rbp+var_38]
0x140022cfe  mov     rcx, [rcx+2E8h]
0x140022d05  call    ?GetProcessorLoadHistory@VpStatistics@@UEBAXAEAV?$vector@V?$vector@KV?$allocator@K@std@@@std@@V?$allocator@V?$vector@KV?$allocator@K@std@@@std@@@2@@std@@@Z; VpStatistics::GetProcessorLoadHistory(std::vector<std::vector<ulong>> &)
0x140022d0a  mov     r8, qword ptr [rbp+var_38+8]
0x140022d0e  sub     r8, qword ptr [rbp+var_38]
0x140022d12  sar     r8, 3
0x140022d16  mov     rax, 0AAAAAAAAAAAAAAABh
0x140022d20  imul    r8, rax; cElements
0x140022d24  mov     ecx, 0Ch; vt
0x140022d29  xor     r9d, r9d; pvExtra
0x140022d2c  xor     edx, edx; lLbound
0x140022d2e  call    cs:__imp_SafeArrayCreateVectorEx
0x140022d35  nop     dword ptr [rax+rax+00h]
0x140022d3a  mov     r15, rax
0x140022d3d  test    rax, rax
0x140022d40  jz      loc_140022EC6
0x140022d46  mov     [rbp+var_50], rax
0x140022d4a  xorps   xmm0, xmm0
0x140022d4d  movups  xmmword ptr [rbp+ppvData], xmm0
0x140022d51  mov     [rbp+ppvData], rax
0x140022d55  mov     [rbp+ppvData+8], 0
0x140022d5d  lea     rdx, [rbp+ppvData+8]; ppvData
0x140022d61  mov     rcx, rax; psa
0x140022d64  call    cs:__imp_SafeArrayAccessData
0x140022d6b  nop     dword ptr [rax+rax+00h]
0x140022d70  mov     rcx, [rbp+28h]; this
0x140022d74  test    eax, eax
0x140022d76  js      loc_140022EE2
0x140022d7c  mov     rdi, [rbp+ppvData+8]
0x140022d80  mov     rbx, qword ptr [rbp+var_38]
0x140022d84  cmp     rbx, qword ptr [rbp+var_38+8]
0x140022d88  jz      loc_140022E79
0x140022d8e  mov     r14, [rbx+8]
0x140022d92  sub     r14, [rbx]
0x140022d95  sar     r14, 2
0x140022d99  mov     ecx, 13h; vt
0x140022d9e  xor     r9d, r9d; pvExtra
0x140022da1  mov     r8d, r14d; cElements
0x140022da4  xor     edx, edx; lLbound
0x140022da6  call    cs:__imp_SafeArrayCreateVectorEx
0x140022dad  nop     dword ptr [rax+rax+00h]
0x140022db2  mov     rsi, rax
0x140022db5  mov     [rbp+var_48], rax
0x140022db9  test    rax, rax
0x140022dbc  jz      loc_140022F36
0x140022dc2  mov     [rbp+psa], rax
0x140022dc6  mov     [rbp+var_58], 0
0x140022dce  lea     rdx, [rbp+var_58]; ppvData
0x140022dd2  mov     rcx, rax; psa
0x140022dd5  call    cs:__imp_SafeArrayAccessData
0x140022ddc  nop     dword ptr [rax+rax+00h]
0x140022de1  mov     rcx, [rbp+28h]; this
0x140022de5  test    eax, eax
0x140022de7  js      loc_140022F21
0x140022ded  mov     r8d, r14d
0x140022df0  shl     r8, 2; Size
0x140022df4  mov     rdx, [rbx]; Src
0x140022df7  mov     rcx, [rbp+var_58]; void *
0x140022dfb  call    memcpy_0
0x140022e00  mov     rcx, [rbp+psa]; psa
0x140022e04  test    rcx, rcx
0x140022e07  jz      short loc_140022E15
0x140022e09  call    cs:__imp_SafeArrayUnaccessData
0x140022e10  nop     dword ptr [rax+rax+00h]
0x140022e15  mov     [rbp+var_48], 0
0x140022e1d  xor     eax, eax
0x140022e1f  mov     [rbp+pvt], ax
0x140022e23  lea     rdx, [rbp+pvt]; pvt
0x140022e27  mov     rcx, rsi; psa
0x140022e2a  call    cs:__imp_SafeArrayGetVartype
0x140022e31  nop     dword ptr [rax+rax+00h]
0x140022e36  mov     rcx, [rbp+28h]; this
0x140022e3a  test    eax, eax
0x140022e3c  js      loc_140022F0C
0x140022e42  mov     rcx, rdi; pvarg
0x140022e45  call    cs:__imp_VariantClear
0x140022e4c  nop     dword ptr [rax+rax+00h]
0x140022e51  mov     rcx, [rbp+28h]; this
0x140022e55  test    eax, eax
0x140022e57  js      loc_140022EF7
0x140022e5d  movzx   eax, [rbp+pvt]
0x140022e61  or      ax, 2000h
0x140022e65  mov     [rdi], ax
0x140022e68  mov     [rdi+8], rsi
0x140022e6c  add     rbx, 18h
0x140022e70  add     rdi, 18h
0x140022e74  jmp     loc_140022D84
0x140022e79  mov     [r12], r15
0x140022e7d  mov     rcx, [rbp+ppvData]; psa
0x140022e81  test    rcx, rcx
0x140022e84  jz      short loc_140022E93
0x140022e86  call    cs:__imp_SafeArrayUnaccessData
0x140022e8d  nop     dword ptr [rax+rax+00h]
0x140022e92  nop
0x140022e93  lea     rcx, [rbp+var_38]
0x140022e97  call    ?_Tidy@?$vector@V?$vector@KV?$allocator@K@std@@@std@@V?$allocator@V?$vector@KV?$allocator@K@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::vector<ulong>>::_Tidy(void)
0x140022e9c  nop
0x140022e9d  mov     rcx, [rbp+var_10]
0x140022ea1  xor     rcx, rsp; StackCookie
0x140022ea4  call    __security_check_cookie
0x140022ea9  lea     r11, [rsp+80h+var_s0]
0x140022eb1  mov     rbx, [r11+40h]
0x140022eb5  mov     rsi, [r11+48h]
0x140022eb9  mov     rsp, r11
0x140022ebc  pop     r15
0x140022ebe  pop     r14
0x140022ec0  pop     r12
0x140022ec2  pop     rdi
0x140022ec3  pop     rbp
0x140022ec4  retn
0x140022ec6  mov     rcx, [rbp+28h]; this
0x140022eca  mov     r9d, 8007000Eh; char *
0x140022ed0  lea     r8, aOnecoreVmCommo_53; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140022ed7  mov     edx, 250h; void *
0x140022edc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022ee2  mov     r9d, eax; char *
0x140022ee5  lea     r8, aOnecoreVmCommo_53; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140022eec  mov     edx, 7B2h; void *
0x140022ef1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022ef7  mov     r9d, eax; char *
0x140022efa  lea     r8, aOnecoreVmCommo_41; "onecore\\vm\\common\\vml\\VmVariant.h"
0x140022f01  mov     edx, 723h; void *
0x140022f06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022f0c  mov     r9d, eax; char *
0x140022f0f  lea     r8, aOnecoreVmCommo_41; "onecore\\vm\\common\\vml\\VmVariant.h"
0x140022f16  mov     edx, 6EDh; void *
0x140022f1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022f21  mov     r9d, eax; char *
0x140022f24  lea     r8, aOnecoreVmCommo_53; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140022f2b  mov     edx, 7B2h; void *
0x140022f30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022f36  mov     rcx, [rbp+28h]; this
0x140022f3a  mov     r9d, 8007000Eh; char *
0x140022f40  lea     r8, aOnecoreVmCommo_53; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140022f47  mov     edx, 1D9h; void *
0x140022f4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
