# ProcessorManager::GetProcessorLoadHistory(tagSAFEARRAY * *)

- ea: `0x140022740`
- end: `0x1400229e2`
- name: `?GetProcessorLoadHistory@ProcessorManager@@UEAAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `674`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140022740`
- `0x1400229e8`
- `0x140023870`
- `0x14006af58`
- `0x140132960`
- `0x140135955`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1400228d5`
- `OLEAUT32!__imp_VariantClear` at `0x1400228d5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400227f4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140022865`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400227f4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140022865`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022899`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022916`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022899`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022916`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x1400227be`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140022836`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x1400227be`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140022836`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1400228ba`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1400228ba`

## string_xrefs

- `0x140022960`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140022975`: `onecore\vm\common\vml\VmAutomation.h`
- `0x1400229b4`: `onecore\vm\common\vml\VmAutomation.h`
- `0x1400229d0`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14002298a`: `onecore\vm\common\vml\VmVariant.h`
- `0x14002299f`: `onecore\vm\common\vml\VmVariant.h`

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
0x140022740  mov     [rsp-28h+arg_10], rbx
0x140022745  mov     [rsp-28h+arg_18], rsi
0x14002274a  push    rbp
0x14002274b  push    rdi
0x14002274c  push    r12
0x14002274e  push    r14
0x140022750  push    r15
0x140022752  mov     rbp, rsp
0x140022755  sub     rsp, 80h
0x14002275c  mov     rax, cs:__security_cookie
0x140022763  xor     rax, rsp
0x140022766  mov     [rbp+var_10], rax
0x14002276a  mov     r12, rdx
0x14002276d  mov     qword ptr [rdx], 0
0x140022774  mov     [rbp+var_50], 0
0x14002277c  xor     eax, eax
0x14002277e  xorps   xmm1, xmm1
0x140022781  movdqu  [rbp+var_38], xmm1
0x140022786  mov     [rbp+var_28], rax
0x14002278a  lea     rdx, [rbp+var_38]
0x14002278e  mov     rcx, [rcx+2E8h]
0x140022795  call    ?GetProcessorLoadHistory@VpStatistics@@UEBAXAEAV?$vector@V?$vector@KV?$allocator@K@std@@@std@@V?$allocator@V?$vector@KV?$allocator@K@std@@@std@@@2@@std@@@Z; VpStatistics::GetProcessorLoadHistory(std::vector<std::vector<ulong>> &)
0x14002279a  mov     r8, qword ptr [rbp+var_38+8]
0x14002279e  sub     r8, qword ptr [rbp+var_38]
0x1400227a2  sar     r8, 3
0x1400227a6  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400227b0  imul    r8, rax; cElements
0x1400227b4  mov     ecx, 0Ch; vt
0x1400227b9  xor     r9d, r9d; pvExtra
0x1400227bc  xor     edx, edx; lLbound
0x1400227be  call    cs:__imp_SafeArrayCreateVectorEx
0x1400227c5  nop     dword ptr [rax+rax+00h]
0x1400227ca  mov     r15, rax
0x1400227cd  test    rax, rax
0x1400227d0  jz      loc_140022956
0x1400227d6  mov     [rbp+var_50], rax
0x1400227da  xorps   xmm0, xmm0
0x1400227dd  movups  xmmword ptr [rbp+ppvData], xmm0
0x1400227e1  mov     [rbp+ppvData], rax
0x1400227e5  mov     [rbp+ppvData+8], 0
0x1400227ed  lea     rdx, [rbp+ppvData+8]; ppvData
0x1400227f1  mov     rcx, rax; psa
0x1400227f4  call    cs:__imp_SafeArrayAccessData
0x1400227fb  nop     dword ptr [rax+rax+00h]
0x140022800  mov     rcx, [rbp+28h]; this
0x140022804  test    eax, eax
0x140022806  js      loc_140022972
0x14002280c  mov     rdi, [rbp+ppvData+8]
0x140022810  mov     rbx, qword ptr [rbp+var_38]
0x140022814  cmp     rbx, qword ptr [rbp+var_38+8]
0x140022818  jz      loc_140022909
0x14002281e  mov     r14, [rbx+8]
0x140022822  sub     r14, [rbx]
0x140022825  sar     r14, 2
0x140022829  mov     ecx, 13h; vt
0x14002282e  xor     r9d, r9d; pvExtra
0x140022831  mov     r8d, r14d; cElements
0x140022834  xor     edx, edx; lLbound
0x140022836  call    cs:__imp_SafeArrayCreateVectorEx
0x14002283d  nop     dword ptr [rax+rax+00h]
0x140022842  mov     rsi, rax
0x140022845  mov     [rbp+var_48], rax
0x140022849  test    rax, rax
0x14002284c  jz      loc_1400229C6
0x140022852  mov     [rbp+psa], rax
0x140022856  mov     [rbp+var_58], 0
0x14002285e  lea     rdx, [rbp+var_58]; ppvData
0x140022862  mov     rcx, rax; psa
0x140022865  call    cs:__imp_SafeArrayAccessData
0x14002286c  nop     dword ptr [rax+rax+00h]
0x140022871  mov     rcx, [rbp+28h]; this
0x140022875  test    eax, eax
0x140022877  js      loc_1400229B1
0x14002287d  mov     r8d, r14d
0x140022880  shl     r8, 2; Size
0x140022884  mov     rdx, [rbx]; Src
0x140022887  mov     rcx, [rbp+var_58]; void *
0x14002288b  call    memcpy_0
0x140022890  mov     rcx, [rbp+psa]; psa
0x140022894  test    rcx, rcx
0x140022897  jz      short loc_1400228A5
0x140022899  call    cs:__imp_SafeArrayUnaccessData
0x1400228a0  nop     dword ptr [rax+rax+00h]
0x1400228a5  mov     [rbp+var_48], 0
0x1400228ad  xor     eax, eax
0x1400228af  mov     [rbp+pvt], ax
0x1400228b3  lea     rdx, [rbp+pvt]; pvt
0x1400228b7  mov     rcx, rsi; psa
0x1400228ba  call    cs:__imp_SafeArrayGetVartype
0x1400228c1  nop     dword ptr [rax+rax+00h]
0x1400228c6  mov     rcx, [rbp+28h]; this
0x1400228ca  test    eax, eax
0x1400228cc  js      loc_14002299C
0x1400228d2  mov     rcx, rdi; pvarg
0x1400228d5  call    cs:__imp_VariantClear
0x1400228dc  nop     dword ptr [rax+rax+00h]
0x1400228e1  mov     rcx, [rbp+28h]; this
0x1400228e5  test    eax, eax
0x1400228e7  js      loc_140022987
0x1400228ed  movzx   eax, [rbp+pvt]
0x1400228f1  or      ax, 2000h
0x1400228f5  mov     [rdi], ax
0x1400228f8  mov     [rdi+8], rsi
0x1400228fc  add     rbx, 18h
0x140022900  add     rdi, 18h
0x140022904  jmp     loc_140022814
0x140022909  mov     [r12], r15
0x14002290d  mov     rcx, [rbp+ppvData]; psa
0x140022911  test    rcx, rcx
0x140022914  jz      short loc_140022923
0x140022916  call    cs:__imp_SafeArrayUnaccessData
0x14002291d  nop     dword ptr [rax+rax+00h]
0x140022922  nop
0x140022923  lea     rcx, [rbp+var_38]
0x140022927  call    ?_Tidy@?$vector@V?$vector@KV?$allocator@K@std@@@std@@V?$allocator@V?$vector@KV?$allocator@K@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::vector<ulong>>::_Tidy(void)
0x14002292c  nop
0x14002292d  mov     rcx, [rbp+var_10]
0x140022931  xor     rcx, rsp; StackCookie
0x140022934  call    __security_check_cookie
0x140022939  lea     r11, [rsp+80h+var_s0]
0x140022941  mov     rbx, [r11+40h]
0x140022945  mov     rsi, [r11+48h]
0x140022949  mov     rsp, r11
0x14002294c  pop     r15
0x14002294e  pop     r14
0x140022950  pop     r12
0x140022952  pop     rdi
0x140022953  pop     rbp
0x140022954  retn
0x140022956  mov     rcx, [rbp+28h]; this
0x14002295a  mov     r9d, 8007000Eh; char *
0x140022960  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140022967  mov     edx, 250h; void *
0x14002296c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022972  mov     r9d, eax; char *
0x140022975  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14002297c  mov     edx, 7B2h; void *
0x140022981  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022987  mov     r9d, eax; char *
0x14002298a  lea     r8, aOnecoreVmCommo_42; "onecore\\vm\\common\\vml\\VmVariant.h"
0x140022991  mov     edx, 723h; void *
0x140022996  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002299c  mov     r9d, eax; char *
0x14002299f  lea     r8, aOnecoreVmCommo_42; "onecore\\vm\\common\\vml\\VmVariant.h"
0x1400229a6  mov     edx, 6EDh; void *
0x1400229ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400229b1  mov     r9d, eax; char *
0x1400229b4  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x1400229bb  mov     edx, 7B2h; void *
0x1400229c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400229c6  mov     rcx, [rbp+28h]; this
0x1400229ca  mov     r9d, 8007000Eh; char *
0x1400229d0  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x1400229d7  mov     edx, 1D9h; void *
0x1400229dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
