# ConfigMgr::GetArbitratorValues(ulong *,ulong *,ulong *,ulong *,double *,long *,double *,long *,double *,long *)

- ea: `0x18007df80`
- end: `0x18007e302`
- name: `?GetArbitratorValues@ConfigMgr@@SAHPEAK000PEANPEAJ1212@Z`
- size: `898`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, unsigned int *, unsigned int *, double *, int *, double *, int *, double *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180092a68`

## callees

- `0x18007df80`

## import_xrefs

- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18007dffb`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18007dffb`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e05a`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e089`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e0bf`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e103`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e139`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e17d`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e1b3`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e1f5`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e05a`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e089`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e0bf`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e103`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e139`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e17d`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e1b3`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18007e1f5`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18007e25f`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18007e25f`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e011`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e026`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e040`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e06f`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e0a5`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e0e9`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e11f`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e163`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e199`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e1db`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e011`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e026`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e040`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e06f`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e0a5`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e0e9`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e11f`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e163`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e199`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18007e1db`

## string_xrefs

- `0x18007e064`: `ArbTaskMaxIdle`
- `0x18007e07e`: `ArbTaskMaxIdle`
- `0x18007e035`: `ArbTaskMaxSleep`
- `0x18007e04f`: `ArbTaskMaxSleep`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConfigMgr::GetArbitratorValues(
        unsigned int *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        double *a5,
        int *a6,
        double *a7,
        int *a8,
        double *a9,
        int *a10)
{
  double v13; // xmm9_8
  double v14; // xmm8_8
  double v15; // xmm6_8
  unsigned int v17; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v18; // [rsp+24h] [rbp-5Ch] BYREF
  int v19; // [rsp+28h] [rbp-58h] BYREF
  int v20; // [rsp+2Ch] [rbp-54h] BYREF
  _BYTE v21[32]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int *v22; // [rsp+B0h] [rbp+30h] BYREF
  unsigned int v23; // [rsp+B8h] [rbp+38h] BYREF
  unsigned int v24; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v25; // [rsp+C8h] [rbp+48h] BYREF

  v22 = a1;
  if ( !g_lInitCount )
  {
    v19 = 1;
    v20 = 50;
    v23 = 300000;
    v24 = 1200000;
    v25 = 2;
    v17 = 3;
    v18 = 4;
    Registry::Registry((Registry *)v21, L"Software\\Microsoft\\WBEM\\CIMOM", 3u);
    Registry::GetDWORD((Registry *)v21, L"ArbThrottlingEnabled", (unsigned int *)&v19);
    if ( Registry::GetDWORD((Registry *)v21, L"ArbSystemHighMaxLimitFactor", (unsigned int *)&v20) == 1
      && Registry::GetDWORD((Registry *)v21, L"ArbTaskMaxSleep", &v23) == 1 )
    {
      Registry::SetDWORD((Registry *)v21, L"ArbTaskMaxSleep", v23);
    }
    if ( Registry::GetDWORD((Registry *)v21, L"ArbTaskMaxIdle", &v24) == 1 )
      Registry::SetDWORD((Registry *)v21, L"ArbTaskMaxIdle", v24);
    LODWORD(v22) = 90;
    if ( Registry::GetDWORD((Registry *)v21, L"ArbSystemHighThreshold1", (unsigned int *)&v22) == 1 )
      Registry::SetDWORD((Registry *)v21, L"ArbSystemHighThreshold1", (unsigned int)v22);
    v13 = (double)(int)v22 / 100.0;
    if ( Registry::GetDWORD((Registry *)v21, L"ArbSystemHighThreshold1Mult", &v25) == 1 )
      Registry::SetDWORD((Registry *)v21, L"ArbSystemHighThreshold1Mult", v25);
    LODWORD(v22) = 95;
    if ( Registry::GetDWORD((Registry *)v21, L"ArbSystemHighThreshold2", (unsigned int *)&v22) == 1 )
      Registry::SetDWORD((Registry *)v21, L"ArbSystemHighThreshold2", (unsigned int)v22);
    v14 = (double)(int)v22 / 100.0;
    if ( Registry::GetDWORD((Registry *)v21, L"ArbSystemHighThreshold2Mult", &v17) == 1 )
      Registry::SetDWORD((Registry *)v21, L"ArbSystemHighThreshold2Mult", v17);
    LODWORD(v22) = 98;
    if ( Registry::GetDWORD((Registry *)v21, L"ArbSystemHighThreshold3", (unsigned int *)&v22) == 1 )
      Registry::SetDWORD((Registry *)v21, L"ArbSystemHighThreshold3", (unsigned int)v22);
    v15 = (double)(int)v22 / 100.0;
    if ( Registry::GetDWORD((Registry *)v21, L"ArbSystemHighThreshold3Mult", &v18) == 1 )
      Registry::SetDWORD((Registry *)v21, L"ArbSystemHighThreshold3Mult", v18);
    dword_1801A2754 = v19;
    dword_1801A2764 = v20;
    dword_1801A2740 = v23;
    dword_1801A2744 = v24;
    qword_1801A2758 = *(_QWORD *)&v13;
    dword_1801A2778 = v25;
    qword_1801A2748 = *(_QWORD *)&v14;
    dword_1801A2770 = v17;
    qword_1801A2730 = *(_QWORD *)&v15;
    dword_1801A273C = v18;
    dword_1801ADB48 = 1;
    Registry::~Registry((Registry *)v21);
  }
  dword_1801A25D8 = dword_1801A2754;
  *a2 = dword_1801A2764;
  *a3 = dword_1801A2740;
  *a4 = dword_1801A2744;
  *(_QWORD *)a5 = qword_1801A2758;
  *a6 = dword_1801A2778;
  *(_QWORD *)a7 = qword_1801A2748;
  *a8 = dword_1801A2770;
  *(_QWORD *)a9 = qword_1801A2730;
  *a10 = dword_1801A273C;
  return (unsigned int)dword_1801ADB48;
}

```

## disassembly

```asm
0x18007df80  mov     rax, rsp
0x18007df83  mov     [rax+8], rcx
0x18007df87  push    rbp
0x18007df88  push    rbx
0x18007df89  push    rsi
0x18007df8a  push    rdi
0x18007df8b  push    r14
0x18007df8d  mov     rbp, rsp
0x18007df90  sub     rsp, 80h
0x18007df97  movaps  xmmword ptr [rax-38h], xmm6
0x18007df9b  movaps  xmmword ptr [rax-48h], xmm8
0x18007dfa0  movaps  xmmword ptr [rax-58h], xmm9
0x18007dfa5  mov     rbx, r9
0x18007dfa8  mov     rdi, r8
0x18007dfab  mov     rsi, rdx
0x18007dfae  cmp     cs:?g_lInitCount@@3JA, 0; long g_lInitCount
0x18007dfb5  jnz     loc_18007E265
0x18007dfbb  mov     r14d, 1
0x18007dfc1  mov     [rbp+var_58], r14d
0x18007dfc5  mov     [rbp+var_54], 32h ; '2'
0x18007dfcc  mov     [rbp+arg_8], 493E0h
0x18007dfd3  mov     [rbp+arg_10], 124F80h
0x18007dfda  mov     [rbp+arg_18], 2
0x18007dfe1  lea     r8d, [r14+2]
0x18007dfe5  mov     [rbp+var_60], r8d
0x18007dfe9  mov     [rbp+var_5C], 4
0x18007dff0  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\WBEM\\CIMOM"
0x18007dff7  lea     rcx, [rbp+var_50]
0x18007dffb  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x18007e001  nop
0x18007e002  lea     r8, [rbp+var_58]
0x18007e006  lea     rdx, aArbthrottlinge; "ArbThrottlingEnabled"
0x18007e00d  lea     rcx, [rbp+var_50]
0x18007e011  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e017  lea     r8, [rbp+var_54]
0x18007e01b  lea     rdx, aArbsystemhighm; "ArbSystemHighMaxLimitFactor"
0x18007e022  lea     rcx, [rbp+var_50]
0x18007e026  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e02c  cmp     eax, r14d
0x18007e02f  jnz     short loc_18007E060
0x18007e031  lea     r8, [rbp+arg_8]
0x18007e035  lea     rdx, aArbtaskmaxslee; "ArbTaskMaxSleep"
0x18007e03c  lea     rcx, [rbp+var_50]
0x18007e040  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e046  cmp     eax, r14d
0x18007e049  jnz     short loc_18007E060
0x18007e04b  mov     r8d, [rbp+arg_8]
0x18007e04f  lea     rdx, aArbtaskmaxslee; "ArbTaskMaxSleep"
0x18007e056  lea     rcx, [rbp+var_50]
0x18007e05a  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18007e060  lea     r8, [rbp+arg_10]
0x18007e064  lea     rdx, aArbtaskmaxidle; "ArbTaskMaxIdle"
0x18007e06b  lea     rcx, [rbp+var_50]
0x18007e06f  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e075  cmp     eax, r14d
0x18007e078  jnz     short loc_18007E08F
0x18007e07a  mov     r8d, [rbp+arg_10]
0x18007e07e  lea     rdx, aArbtaskmaxidle; "ArbTaskMaxIdle"
0x18007e085  lea     rcx, [rbp+var_50]
0x18007e089  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18007e08f  mov     dword ptr [rbp+arg_0], 5Ah ; 'Z'
0x18007e096  lea     r8, [rbp+arg_0]
0x18007e09a  lea     rdx, aArbsystemhight_0; "ArbSystemHighThreshold1"
0x18007e0a1  lea     rcx, [rbp+var_50]
0x18007e0a5  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e0ab  cmp     eax, r14d
0x18007e0ae  jnz     short loc_18007E0C5
0x18007e0b0  mov     r8d, dword ptr [rbp+arg_0]
0x18007e0b4  lea     rdx, aArbsystemhight_0; "ArbSystemHighThreshold1"
0x18007e0bb  lea     rcx, [rbp+var_50]
0x18007e0bf  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18007e0c5  mov     eax, dword ptr [rbp+arg_0]
0x18007e0c8  xorps   xmm9, xmm9
0x18007e0cc  cvtsi2sd xmm9, rax
0x18007e0d1  divsd   xmm9, cs:__real@4059000000000000
0x18007e0da  lea     r8, [rbp+arg_18]
0x18007e0de  lea     rdx, aArbsystemhight_4; "ArbSystemHighThreshold1Mult"
0x18007e0e5  lea     rcx, [rbp+var_50]
0x18007e0e9  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e0ef  cmp     eax, r14d
0x18007e0f2  jnz     short loc_18007E109
0x18007e0f4  mov     r8d, [rbp+arg_18]
0x18007e0f8  lea     rdx, aArbsystemhight_4; "ArbSystemHighThreshold1Mult"
0x18007e0ff  lea     rcx, [rbp+var_50]
0x18007e103  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18007e109  mov     dword ptr [rbp+arg_0], 5Fh ; '_'
0x18007e110  lea     r8, [rbp+arg_0]
0x18007e114  lea     rdx, aArbsystemhight_2; "ArbSystemHighThreshold2"
0x18007e11b  lea     rcx, [rbp+var_50]
0x18007e11f  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e125  cmp     eax, r14d
0x18007e128  jnz     short loc_18007E13F
0x18007e12a  mov     r8d, dword ptr [rbp+arg_0]
0x18007e12e  lea     rdx, aArbsystemhight_2; "ArbSystemHighThreshold2"
0x18007e135  lea     rcx, [rbp+var_50]
0x18007e139  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18007e13f  mov     eax, dword ptr [rbp+arg_0]
0x18007e142  xorps   xmm8, xmm8
0x18007e146  cvtsi2sd xmm8, rax
0x18007e14b  divsd   xmm8, cs:__real@4059000000000000
0x18007e154  lea     r8, [rbp+var_60]
0x18007e158  lea     rdx, aArbsystemhight; "ArbSystemHighThreshold2Mult"
0x18007e15f  lea     rcx, [rbp+var_50]
0x18007e163  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e169  cmp     eax, r14d
0x18007e16c  jnz     short loc_18007E183
0x18007e16e  mov     r8d, [rbp+var_60]
0x18007e172  lea     rdx, aArbsystemhight; "ArbSystemHighThreshold2Mult"
0x18007e179  lea     rcx, [rbp+var_50]
0x18007e17d  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18007e183  mov     dword ptr [rbp+arg_0], 62h ; 'b'
0x18007e18a  lea     r8, [rbp+arg_0]
0x18007e18e  lea     rdx, aArbsystemhight_1; "ArbSystemHighThreshold3"
0x18007e195  lea     rcx, [rbp+var_50]
0x18007e199  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e19f  cmp     eax, r14d
0x18007e1a2  jnz     short loc_18007E1B9
0x18007e1a4  mov     r8d, dword ptr [rbp+arg_0]
0x18007e1a8  lea     rdx, aArbsystemhight_1; "ArbSystemHighThreshold3"
0x18007e1af  lea     rcx, [rbp+var_50]
0x18007e1b3  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18007e1b9  mov     eax, dword ptr [rbp+arg_0]
0x18007e1bc  xorps   xmm6, xmm6
0x18007e1bf  cvtsi2sd xmm6, rax
0x18007e1c4  divsd   xmm6, cs:__real@4059000000000000
0x18007e1cc  lea     r8, [rbp+var_5C]
0x18007e1d0  lea     rdx, aArbsystemhight_3; "ArbSystemHighThreshold3Mult"
0x18007e1d7  lea     rcx, [rbp+var_50]
0x18007e1db  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18007e1e1  cmp     eax, r14d
0x18007e1e4  jnz     short loc_18007E1FB
0x18007e1e6  mov     r8d, [rbp+var_5C]
0x18007e1ea  lea     rdx, aArbsystemhight_3; "ArbSystemHighThreshold3Mult"
0x18007e1f1  lea     rcx, [rbp+var_50]
0x18007e1f5  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18007e1fb  mov     eax, [rbp+var_58]
0x18007e1fe  mov     cs:dword_1801A2754, eax
0x18007e204  mov     eax, [rbp+var_54]
0x18007e207  mov     cs:dword_1801A2764, eax
0x18007e20d  mov     eax, [rbp+arg_8]
0x18007e210  mov     cs:dword_1801A2740, eax
0x18007e216  mov     eax, [rbp+arg_10]
0x18007e219  mov     cs:dword_1801A2744, eax
0x18007e21f  movsd   cs:qword_1801A2758, xmm9
0x18007e228  mov     eax, [rbp+arg_18]
0x18007e22b  mov     cs:dword_1801A2778, eax
0x18007e231  movsd   cs:qword_1801A2748, xmm8
0x18007e23a  mov     eax, [rbp+var_60]
0x18007e23d  mov     cs:dword_1801A2770, eax
0x18007e243  movsd   cs:qword_1801A2730, xmm6
0x18007e24b  mov     eax, [rbp+var_5C]
0x18007e24e  mov     cs:dword_1801A273C, eax
0x18007e254  mov     cs:dword_1801ADB48, r14d
0x18007e25b  lea     rcx, [rbp+var_50]
0x18007e25f  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18007e265  mov     eax, cs:dword_1801A2754
0x18007e26b  mov     cs:dword_1801A25D8, eax
0x18007e271  mov     eax, cs:dword_1801A2764
0x18007e277  mov     [rsi], eax
0x18007e279  mov     eax, cs:dword_1801A2740
0x18007e27f  mov     [rdi], eax
0x18007e281  mov     eax, cs:dword_1801A2744
0x18007e287  mov     [rbx], eax
0x18007e289  mov     rax, [rbp+arg_20]
0x18007e28d  movsd   xmm0, cs:qword_1801A2758
0x18007e295  movsd   qword ptr [rax], xmm0
0x18007e299  mov     rcx, [rbp+arg_28]
0x18007e29d  mov     eax, cs:dword_1801A2778
0x18007e2a3  mov     [rcx], eax
0x18007e2a5  mov     rax, [rbp+arg_30]
0x18007e2a9  movsd   xmm0, cs:qword_1801A2748
0x18007e2b1  movsd   qword ptr [rax], xmm0
0x18007e2b5  mov     rcx, [rbp+arg_38]
0x18007e2b9  mov     eax, cs:dword_1801A2770
0x18007e2bf  mov     [rcx], eax
0x18007e2c1  mov     rax, [rbp+arg_40]
0x18007e2c5  movsd   xmm0, cs:qword_1801A2730
0x18007e2cd  movsd   qword ptr [rax], xmm0
0x18007e2d1  mov     rcx, [rbp+arg_48]
0x18007e2d5  mov     eax, cs:dword_1801A273C
0x18007e2db  mov     [rcx], eax
0x18007e2dd  mov     eax, cs:dword_1801ADB48
0x18007e2e3  movaps  xmm6, [rsp+80h+var_10]
0x18007e2e8  movaps  xmm8, [rsp+80h+var_20]
0x18007e2ee  movaps  xmm9, [rsp+80h+var_30]
0x18007e2f4  add     rsp, 80h
0x18007e2fb  pop     r14
0x18007e2fd  pop     rdi
0x18007e2fe  pop     rsi
0x18007e2ff  pop     rbx
0x18007e300  pop     rbp
0x18007e301  retn
```
