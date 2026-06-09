# SkpsInitializeScpCfgPages

- ea: `0x1400224e4`
- end: `0x14002264b`
- name: `SkpsInitializeScpCfgPages`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140023ee8`

## callees

- `0x1400224e4`
- `0x1400f9780`
- `0x1400f9a80`
- `0x1400fcc24`

## string_xrefs

- `0x1400224fd`: `RtlpScpCfgNtdllExports`

## pseudocode

```c
__int64 __fastcall SkpsInitializeScpCfgPages(__int64 a1)
{
  __int64 ExportedRoutineByName; // rax
  unsigned __int64 v3; // rdx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rax
  unsigned int i; // edx
  _BYTE *v8; // r10
  _BYTE *v9; // r9
  __int64 j; // rbx
  unsigned int v11; // edi
  void *Src[2]; // [rsp+20h] [rbp-88h]
  __int128 v13; // [rsp+30h] [rbp-78h]
  __int128 v14; // [rsp+40h] [rbp-68h]
  __int128 v15; // [rsp+50h] [rbp-58h]
  __int128 v16; // [rsp+60h] [rbp-48h]
  __int128 v17; // [rsp+70h] [rbp-38h]
  __int64 v18; // [rsp+80h] [rbp-28h]

  ExportedRoutineByName = RtlFindExportedRoutineByName(qword_14016A020, "RtlpScpCfgNtdllExports");
  v3 = ExportedRoutineByName;
  if ( !ExportedRoutineByName )
    return 3221225594LL;
  v5 = qword_14016A020 + (unsigned int)dword_14016A028;
  if ( v5 <= qword_14016A020 )
    return 3221225485LL;
  v6 = ExportedRoutineByName + 104;
  if ( v6 <= v3 || v3 < qword_14016A020 || v6 > v5 )
    return 3221225485LL;
  *(_OWORD *)Src = *(_OWORD *)v3;
  v13 = *(_OWORD *)(v3 + 16);
  v14 = *(_OWORD *)(v3 + 32);
  v15 = *(_OWORD *)(v3 + 48);
  v16 = *(_OWORD *)(v3 + 64);
  v17 = *(_OWORD *)(v3 + 80);
  v18 = *(_QWORD *)(v3 + 96);
  for ( i = 0; i < 4; ++i )
  {
    v8 = Src[2 * i];
    v9 = Src[2 * i + 1];
    if ( v9 <= v8
      || (unsigned __int64)(v9 - v8) > 0x1000
      || v5 <= qword_14016A020
      || (unsigned __int64)v8 < qword_14016A020
      || (unsigned __int64)v9 > v5 )
    {
      return 3221225485LL;
    }
  }
  for ( j = 0; !(_DWORD)j; j = 1 )
  {
    v11 = LODWORD(Src[1]) - LODWORD(Src[0]);
    memmove(*(void **)(a1 + 8 * j), Src[0], (unsigned int)(LODWORD(Src[1]) - LODWORD(Src[0])));
    if ( v11 != 4096 )
      memset_0((void *)(v11 + *(_QWORD *)(a1 + 8 * j)), 204, 4096 - v11);
  }
  return 0;
}

```

## disassembly

```asm
0x1400224e4  mov     [rsp+arg_8], rbx
0x1400224e9  mov     [rsp+arg_10], rsi
0x1400224ee  push    rdi
0x1400224ef  push    r14
0x1400224f1  push    r15
0x1400224f3  sub     rsp, 90h
0x1400224fa  mov     r15, rcx
0x1400224fd  lea     rdx, aRtlpscpcfgntdl; "RtlpScpCfgNtdllExports"
0x140022504  mov     rcx, cs:qword_14016A020
0x14002250b  call    RtlFindExportedRoutineByName
0x140022510  mov     rdx, rax
0x140022513  test    rax, rax
0x140022516  jnz     short loc_140022522
0x140022518  mov     eax, 0C000007Ah
0x14002251d  jmp     loc_140022631
0x140022522  mov     rcx, cs:qword_14016A020
0x140022529  mov     r8d, cs:dword_14016A028
0x140022530  add     r8, rcx
0x140022533  cmp     r8, rcx
0x140022536  jbe     loc_14002262C
0x14002253c  add     rax, 68h ; 'h'
0x140022540  cmp     rax, rdx
0x140022543  jbe     loc_14002262C
0x140022549  cmp     rdx, rcx
0x14002254c  jb      loc_14002262C
0x140022552  cmp     rax, r8
0x140022555  ja      loc_14002262C
0x14002255b  movups  xmm0, xmmword ptr [rdx]
0x14002255e  movaps  xmmword ptr [rsp+0A8h+Src], xmm0
0x140022563  movups  xmm1, xmmword ptr [rdx+10h]
0x140022567  movaps  [rsp+0A8h+var_78], xmm1
0x14002256c  movups  xmm0, xmmword ptr [rdx+20h]
0x140022570  movaps  [rsp+0A8h+var_68], xmm0
0x140022575  movups  xmm1, xmmword ptr [rdx+30h]
0x140022579  movaps  [rsp+0A8h+var_58], xmm1
0x14002257e  movups  xmm0, xmmword ptr [rdx+40h]
0x140022582  movaps  [rsp+0A8h+var_48], xmm0
0x140022587  movups  xmm1, xmmword ptr [rdx+50h]
0x14002258b  movaps  [rsp+0A8h+var_38], xmm1
0x140022590  movsd   xmm0, qword ptr [rdx+60h]
0x140022595  movsd   [rsp+0A8h+var_28], xmm0
0x14002259e  xor     edx, edx
0x1400225a0  cmp     edx, 4
0x1400225a3  jnb     short loc_1400225DA
0x1400225a5  mov     eax, edx
0x1400225a7  add     rax, rax
0x1400225aa  mov     r10, [rsp+rax*8+0A8h+Src]
0x1400225af  mov     r9, [rsp+rax*8+0A8h+Src+8]
0x1400225b4  cmp     r9, r10
0x1400225b7  jbe     short loc_14002262C
0x1400225b9  mov     rax, r9
0x1400225bc  sub     rax, r10
0x1400225bf  cmp     rax, 1000h
0x1400225c5  ja      short loc_14002262C
0x1400225c7  cmp     r8, rcx
0x1400225ca  jbe     short loc_14002262C
0x1400225cc  cmp     r10, rcx
0x1400225cf  jb      short loc_14002262C
0x1400225d1  cmp     r9, r8
0x1400225d4  ja      short loc_14002262C
0x1400225d6  inc     edx
0x1400225d8  jmp     short loc_1400225A0
0x1400225da  xor     ebx, ebx
0x1400225dc  cmp     ebx, 1
0x1400225df  jnb     short loc_140022626
0x1400225e1  mov     edx, ebx
0x1400225e3  shl     rdx, 4
0x1400225e7  mov     edi, dword ptr [rsp+rdx+0A8h+Src+8]
0x1400225eb  sub     edi, dword ptr [rsp+rdx+0A8h+Src]
0x1400225ef  mov     r14d, edi
0x1400225f2  mov     r8d, edi; Size
0x1400225f5  mov     rdx, [rsp+rdx+0A8h+Src]; Src
0x1400225fa  mov     rcx, [r15+rbx*8]; void *
0x1400225fe  call    memmove
0x140022603  nop
0x140022604  mov     r8d, 1000h
0x14002260a  sub     r8d, edi; Size
0x14002260d  jz      short loc_140022620
0x14002260f  mov     rcx, [r15+rbx*8]
0x140022613  add     rcx, r14; void *
0x140022616  mov     edx, 0CCh; Val
0x14002261b  call    memset_0
0x140022620  inc     ebx
0x140022622  jmp     short loc_1400225DC
0x140022624  jmp     short loc_140022631
0x140022626  xor     eax, eax
0x140022628  jmp     short loc_140022631
0x14002262a  jmp     short loc_140022631
0x14002262c  mov     eax, 0C000000Dh
0x140022631  lea     r11, [rsp+0A8h+var_18]
0x140022639  mov     rbx, [r11+28h]
0x14002263d  mov     rsi, [r11+30h]
0x140022641  mov     rsp, r11
0x140022644  pop     r15
0x140022646  pop     r14
0x140022648  pop     rdi
0x140022649  retn
```
