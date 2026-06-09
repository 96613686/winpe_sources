# CPicturePasswordGestureHelper::s_HeuristicMatch(CGestureSignatureArray const &,CGestureSignatureArray const &)

- ea: `0x18001517c`
- end: `0x180015301`
- name: `?s_HeuristicMatch@CPicturePasswordGestureHelper@@SA_NAEBVCGestureSignatureArray@@0@Z`
- size: `389`
- prototype: `bool __fastcall(const struct CGestureSignatureArray *, const struct CGestureSignatureArray *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f670`

## callees

- `0x180002610`
- `0x180002f70`
- `0x180002f7c`
- `0x180013f98`
- `0x180014540`
- `0x180014638`
- `0x18001517c`

## pseudocode

```c
bool __fastcall CPicturePasswordGestureHelper::s_HeuristicMatch(
        const struct CGestureSignatureArray *a1,
        const struct CGestureSignatureArray *a2)
{
  bool result; // al
  __int64 v5; // rbx
  __int64 v6; // r9
  int (*v7)(double, double, double, double, double, double, double); // r8
  unsigned __int64 v8; // rdx
  int v9; // ecx
  int v10; // ecx
  double v11; // xmm0_8
  double v12; // xmm1_8
  int v13; // eax
  double v14; // xmm0_8
  double v15; // xmm6_8
  double v16; // xmm0_8
  __int64 v17; // rdx
  double *v18; // rcx
  double v19[3]; // [rsp+20h] [rbp-38h] BYREF

  result = 0;
  if ( *((_QWORD *)a1 + 2) == 3 && *((_QWORD *)a2 + 2) == 3 )
  {
    v5 = 0;
    while ( 1 )
    {
      v6 = *((_QWORD *)a1 + 1);
      v7 = (int (*)(double, double, double, double, double, double, double))(5 * v5);
      v8 = *((_QWORD *)a2 + 1);
      v19[v5] = 0.0;
      v9 = *(_DWORD *)(v6 + 20 * v5);
      if ( v9 == *(_DWORD *)(v8 + 20 * v5) )
      {
        if ( !v9 )
        {
          v12 = (double)(*(_DWORD *)(v8 + 20 * v5 + 4) - *(_DWORD *)(v6 + 20 * v5 + 4));
          v13 = *(_DWORD *)(v8 + 20 * v5 + 8) - *(_DWORD *)(v6 + 20 * v5 + 8);
          v14 = sqrt((double)v13 * (double)v13 + v12 * v12);
          v15 = pow(v14, 2.0);
          v19[v5] = 1.0 - fmin(v15 / pow(3.0, 2.0) * 0.1000000238418579, 1.0);
          goto LABEL_12;
        }
        v10 = v9 - 1;
        if ( !v10 )
        {
          v11 = ScoreLineGesture(
                  (const struct GESTURE_SIGNATURE_LINE *)(v6 + 4 + 20 * v5),
                  (const struct GESTURE_SIGNATURE_LINE *)(v8 + 20 * v5 + 4),
                  v7);
          goto LABEL_9;
        }
        if ( v10 == 1 )
        {
          v11 = ScoreCircleGesture(
                  (const struct GESTURE_SIGNATURE_CIRCLE *)(v6 + 4 + 20 * v5),
                  (const struct GESTURE_SIGNATURE_CIRCLE *)(v8 + 20 * v5 + 4),
                  (int (*)(double, double, double, double))v7);
LABEL_9:
          v19[v5] = v11;
        }
      }
LABEL_12:
      if ( ++v5 == 3 )
      {
        v16 = AggregateScores(v19, v8);
        v17 = 24;
        v18 = v19;
        result = v16 >= 0.8999999761581421;
        do
        {
          *(_BYTE *)v18 = 0;
          v18 = (double *)((char *)v18 + 1);
          --v17;
        }
        while ( v17 );
        return result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001517c  mov     [rsp+arg_10], rbx
0x180015181  mov     [rsp+arg_18], rsi
0x180015186  push    rdi
0x180015187  sub     rsp, 50h
0x18001518b  movaps  [rsp+58h+var_18], xmm6
0x180015190  mov     rax, cs:__security_cookie
0x180015197  xor     rax, rsp
0x18001519a  mov     [rsp+58h+var_20], rax
0x18001519f  xor     al, al
0x1800151a1  mov     rdi, rdx
0x1800151a4  cmp     qword ptr [rcx+10h], 3
0x1800151a9  mov     rsi, rcx
0x1800151ac  jnz     loc_1800152DF
0x1800151b2  cmp     qword ptr [rdx+10h], 3
0x1800151b7  jnz     loc_1800152DF
0x1800151bd  xor     ebx, ebx
0x1800151bf  mov     r9, [rsi+8]
0x1800151c3  lea     r8, [rbx+rbx*4]; int (*)(double, double, double, double, double, double, double)
0x1800151c7  mov     rdx, [rdi+8]
0x1800151cb  mov     [rsp+rbx*8+58h+var_38], 0
0x1800151d4  mov     ecx, [r9+r8*4]
0x1800151d8  cmp     ecx, [rdx+r8*4]
0x1800151dc  jnz     loc_1800152A9
0x1800151e2  test    ecx, ecx
0x1800151e4  jz      short loc_18001522B
0x1800151e6  sub     ecx, 1
0x1800151e9  jz      short loc_180015214
0x1800151eb  cmp     ecx, 1
0x1800151ee  jnz     loc_1800152A9
0x1800151f4  add     r9, 4
0x1800151f8  lea     rdx, [rdx+r8*4]
0x1800151fc  add     rdx, 4; struct GESTURE_SIGNATURE_CIRCLE *
0x180015200  lea     rcx, [r9+r8*4]; struct GESTURE_SIGNATURE_CIRCLE *
0x180015204  call    ?ScoreCircleGesture@@YANAEBUGESTURE_SIGNATURE_CIRCLE@@0P6AJNNNN@Z@Z; ScoreCircleGesture(GESTURE_SIGNATURE_CIRCLE const &,GESTURE_SIGNATURE_CIRCLE const &,long (*)(double,double,double,double))
0x180015209  movsd   [rsp+rbx*8+58h+var_38], xmm0
0x18001520f  jmp     loc_1800152A9
0x180015214  add     r9, 4
0x180015218  lea     rdx, [rdx+r8*4]
0x18001521c  add     rdx, 4; struct GESTURE_SIGNATURE_LINE *
0x180015220  lea     rcx, [r9+r8*4]; struct GESTURE_SIGNATURE_LINE *
0x180015224  call    ?ScoreLineGesture@@YANAEBUGESTURE_SIGNATURE_LINE@@0P6AJNNNNNNN@Z@Z; ScoreLineGesture(GESTURE_SIGNATURE_LINE const &,GESTURE_SIGNATURE_LINE const &,long (*)(double,double,double,double,double,double,double))
0x180015229  jmp     short loc_180015209
0x18001522b  mov     eax, [rdx+r8*4+4]
0x180015230  xorps   xmm0, xmm0
0x180015233  sub     eax, [r9+r8*4+4]
0x180015238  xorps   xmm1, xmm1
0x18001523b  cvtsi2sd xmm1, eax
0x18001523f  mov     eax, [rdx+r8*4+8]
0x180015244  sub     eax, [r9+r8*4+8]
0x180015249  cvtsi2sd xmm0, eax
0x18001524d  mulsd   xmm1, xmm1
0x180015251  mulsd   xmm0, xmm0
0x180015255  addsd   xmm0, xmm1; X
0x180015259  call    sqrt
0x18001525e  movsd   xmm1, cs:__real@4000000000000000; Y
0x180015266  call    pow
0x18001526b  movsd   xmm1, cs:__real@4000000000000000; Y
0x180015273  movaps  xmm6, xmm0
0x180015276  movsd   xmm0, cs:__real@4008000000000000; X
0x18001527e  call    pow
0x180015283  movsd   xmm1, cs:__real@3ff0000000000000
0x18001528b  divsd   xmm6, xmm0
0x18001528f  mulsd   xmm6, cs:__real@3fb9999a00000000
0x180015297  minsd   xmm6, cs:__real@3ff0000000000000
0x18001529f  subsd   xmm1, xmm6
0x1800152a3  movsd   [rsp+rbx*8+58h+var_38], xmm1
0x1800152a9  inc     rbx
0x1800152ac  cmp     rbx, 3
0x1800152b0  jnz     loc_1800151BF
0x1800152b6  lea     rcx, [rsp+58h+var_38]; double *
0x1800152bb  call    ?AggregateScores@@YANPEAN_K@Z; AggregateScores(double *,unsigned __int64)
0x1800152c0  comisd  xmm0, cs:__real@3fecccccc0000000
0x1800152c8  lea     edx, [rbx+15h]
0x1800152cb  lea     rcx, [rsp+58h+var_38]
0x1800152d0  setnb   al
0x1800152d3  mov     byte ptr [rcx], 0
0x1800152d6  inc     rcx
0x1800152d9  sub     rdx, 1
0x1800152dd  jnz     short loc_1800152D3
0x1800152df  mov     rcx, [rsp+58h+var_20]
0x1800152e4  xor     rcx, rsp; StackCookie
0x1800152e7  call    __security_check_cookie
0x1800152ec  mov     rbx, [rsp+58h+arg_10]
0x1800152f1  mov     rsi, [rsp+58h+arg_18]
0x1800152f6  movaps  xmm6, [rsp+58h+var_18]
0x1800152fb  add     rsp, 50h
0x1800152ff  pop     rdi
0x180015300  retn
```
