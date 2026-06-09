# CShellSnapComponent::SetDockThreshold(void)

- ea: `0x180120fe8`
- end: `0x180121146`
- name: `?SetDockThreshold@CShellSnapComponent@@AEAAXXZ`
- size: `350`
- prototype: `void __fastcall(CShellSnapComponent *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1805b68e0`

## callees

- `0x180120fe8`
- `0x18012114c`
- `0x1805b2f38`
- `0x1805b2fe8`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180121062`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180121075`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180121088`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18012109c`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801210b0`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801210d5`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801210ea`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801210fc`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18012110d`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180121122`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180121062`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180121075`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180121088`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18012109c`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801210b0`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801210d5`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801210ea`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801210fc`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18012110d`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180121122`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18012113f`

## pseudocode

```c
void __fastcall CShellSnapComponent::SetDockThreshold(CShellSnapComponent *this, __int64 a2)
{
  int v3; // edx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  UINT v7; // edx
  UINT v8; // ecx

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DITest>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DITest>::GetImpl'::`2'::impl,
    a2);
  if ( *((_BYTE *)this + 1156) )
  {
    CSnapComponentTelemetry::SetDockThreshold<long &,long &,long &,long &,long &,long &>(
      (_DWORD)this + 1160,
      (_DWORD)this + 1164,
      (_DWORD)this + 1168,
      (_DWORD)this + 1172,
      (__int64)this + 1176,
      (__int64)this + 1180);
    SystemParametersInfoW(0x8Bu, *((_DWORD *)this + 295), 0, 0);
    SystemParametersInfoW(0x89u, *((_DWORD *)this + 292), 0, 0);
    SystemParametersInfoW(0x87u, *((_DWORD *)this + 294), 0, 0);
    SystemParametersInfoW(0x85u, *((_DWORD *)this + 291), 0, 0);
    SystemParametersInfoW(0x81u, *((_DWORD *)this + 293), 0, 0);
    v7 = *((_DWORD *)this + 290);
    v8 = 127;
  }
  else
  {
    CSnapComponentTelemetry::SetDockThreshold<int const &,int const &,int const &,int const &,int const &,int const &>(
      v4,
      v3,
      v5,
      v6);
    SystemParametersInfoW(0x7Fu, 1u, 0, 0);
    SystemParametersInfoW(0x81u, 0x1Eu, 0, 0);
    SystemParametersInfoW(0x85u, 0x18u, 0, 0);
    SystemParametersInfoW(0x87u, 0x1Eu, 0, 0);
    SystemParametersInfoW(0x89u, 0x32u, 0, 0);
    v7 = 50;
    v8 = 139;
  }
  SystemParametersInfoW(v8, v7, 0, 0);
}

```

## disassembly

```asm
0x180120fe8  push    rbx
0x180120fea  push    rbp
0x180120feb  push    rsi
0x180120fec  push    rdi
0x180120fed  push    r14
0x180120fef  push    r15
0x180120ff1  sub     rsp, 38h
0x180120ff5  mov     rbp, rcx
0x180120ff8  mov     dl, 1
0x180120ffa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DITest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DITest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DITest> `wil::Feature<__WilFeatureTraits_Feature_DITest>::GetImpl(void)'::`2'::impl
0x180121001  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DITest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DITest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180121006  cmp     byte ptr [rbp+484h], 0
0x18012100d  jz      loc_1801210C3
0x180121013  lea     rbx, [rbp+49Ch]
0x18012101a  lea     rsi, [rbp+498h]
0x180121021  lea     r15, [rbp+494h]
0x180121028  lea     rdi, [rbp+490h]
0x18012102f  lea     r14, [rbp+48Ch]
0x180121036  mov     [rsp+68h+var_40], rbx
0x18012103b  mov     [rsp+68h+var_48], rsi
0x180121040  mov     r9, r15
0x180121043  mov     r8, rdi
0x180121046  mov     rdx, r14
0x180121049  lea     rcx, [rbp+488h]
0x180121050  call    ??$SetDockThreshold@AEAJAEAJAEAJAEAJAEAJAEAJ@CSnapComponentTelemetry@@SAXAEAJ00000@Z; CSnapComponentTelemetry::SetDockThreshold<long &,long &,long &,long &,long &,long &>(long &,long &,long &,long &,long &,long &)
0x180121055  xor     r9d, r9d; fWinIni
0x180121058  xor     r8d, r8d; pvParam
0x18012105b  mov     edx, [rbx]; uiParam
0x18012105d  mov     ecx, 8Bh; uiAction
0x180121062  call    cs:__imp_SystemParametersInfoW
0x180121068  xor     r9d, r9d; fWinIni
0x18012106b  xor     r8d, r8d; pvParam
0x18012106e  mov     edx, [rdi]; uiParam
0x180121070  mov     ecx, 89h; uiAction
0x180121075  call    cs:__imp_SystemParametersInfoW
0x18012107b  xor     r9d, r9d; fWinIni
0x18012107e  xor     r8d, r8d; pvParam
0x180121081  mov     edx, [rsi]; uiParam
0x180121083  mov     ecx, 87h; uiAction
0x180121088  call    cs:__imp_SystemParametersInfoW
0x18012108e  xor     r9d, r9d; fWinIni
0x180121091  xor     r8d, r8d; pvParam
0x180121094  mov     edx, [r14]; uiParam
0x180121097  mov     ecx, 85h; uiAction
0x18012109c  call    cs:__imp_SystemParametersInfoW
0x1801210a2  xor     r9d, r9d; fWinIni
0x1801210a5  xor     r8d, r8d; pvParam
0x1801210a8  mov     edx, [r15]; uiParam
0x1801210ab  mov     ecx, 81h; uiAction
0x1801210b0  call    cs:__imp_SystemParametersInfoW
0x1801210b6  mov     edx, [rbp+488h]
0x1801210bc  mov     ecx, 7Fh
0x1801210c1  jmp     short loc_18012112D
0x1801210c3  call    ??$SetDockThreshold@AEBHAEBHAEBHAEBHAEBHAEBH@CSnapComponentTelemetry@@SAXAEBH00000@Z; CSnapComponentTelemetry::SetDockThreshold<int const &,int const &,int const &,int const &,int const &,int const &>(int const &,int const &,int const &,int const &,int const &,int const &)
0x1801210c8  xor     r9d, r9d; fWinIni
0x1801210cb  xor     r8d, r8d; pvParam
0x1801210ce  lea     edx, [r9+1]; uiParam
0x1801210d2  lea     ecx, [rdx+7Eh]; uiAction
0x1801210d5  call    cs:__imp_SystemParametersInfoW
0x1801210db  xor     r9d, r9d; fWinIni
0x1801210de  xor     r8d, r8d; pvParam
0x1801210e1  lea     ebx, [r9+1Eh]
0x1801210e5  mov     edx, ebx; uiParam
0x1801210e7  lea     ecx, [rbx+63h]; uiAction
0x1801210ea  call    cs:__imp_SystemParametersInfoW
0x1801210f0  xor     r9d, r9d; fWinIni
0x1801210f3  xor     r8d, r8d; pvParam
0x1801210f6  lea     edx, [rbx-6]; uiParam
0x1801210f9  lea     ecx, [rbx+67h]; uiAction
0x1801210fc  call    cs:__imp_SystemParametersInfoW
0x180121102  xor     r9d, r9d; fWinIni
0x180121105  xor     r8d, r8d; pvParam
0x180121108  mov     edx, ebx; uiParam
0x18012110a  lea     ecx, [rbx+69h]; uiAction
0x18012110d  call    cs:__imp_SystemParametersInfoW
0x180121113  xor     r9d, r9d; fWinIni
0x180121116  xor     r8d, r8d; pvParam
0x180121119  lea     ebx, [r9+32h]
0x18012111d  mov     edx, ebx; uiParam
0x18012111f  lea     ecx, [rbx+57h]; uiAction
0x180121122  call    cs:__imp_SystemParametersInfoW
0x180121128  mov     edx, ebx
0x18012112a  lea     ecx, [rbx+59h]
0x18012112d  xor     r9d, r9d
0x180121130  xor     r8d, r8d
0x180121133  add     rsp, 38h
0x180121137  pop     r15
0x180121139  pop     r14
0x18012113b  pop     rdi
0x18012113c  pop     rsi
0x18012113d  pop     rbp
0x18012113e  pop     rbx
0x18012113f  jmp     cs:__imp_SystemParametersInfoW
```
