# AllocateEventData(void *)

- ea: `0x180003190`
- end: `0x180003687`
- name: `?AllocateEventData@@YAPEAXPEAX@Z`
- size: `1271`
- prototype: `_QWORD *__fastcall(int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180002e60`
- `0x1800030a0`

## callees

- `0x180003190`
- `0x180003aa0`
- `0x180004c20`
- `0x180008300`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800031dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000326a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003327`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800033cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003437`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003487`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800034c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800034f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003538`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000356d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800035cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800031dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000326a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003327`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800033cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003437`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003487`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800034c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800034f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003538`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000356d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800035cd`

## pseudocode

```c
_QWORD *__fastcall AllocateEventData(int *a1)
{
  _QWORD *v2; // r14
  __int64 v3; // r9
  _QWORD *v4; // rax
  _QWORD *v5; // rbp
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  bool v10; // zf
  unsigned __int64 v11; // rbx
  SIZE_T v12; // rax
  _WORD *v13; // rax
  _WORD *v14; // rdx
  _WORD *v15; // rcx
  _WORD *v16; // rcx
  __int64 v17; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // rbx
  SIZE_T v21; // rax
  _WORD *v22; // rax
  _WORD *v23; // r8
  _WORD *v24; // rdx
  __int64 v25; // rcx
  _WORD *v26; // rcx
  _QWORD *v27; // rax
  _QWORD *v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rax
  unsigned __int64 v31; // rdi
  SIZE_T v32; // rax
  unsigned __int16 *v33; // rax
  __int64 v34; // rcx
  unsigned __int64 v35; // rbx
  SIZE_T v36; // rax
  unsigned __int16 *v37; // rax
  _OWORD *v38; // rax
  _QWORD *v39; // rcx
  _DWORD *v40; // rax
  _QWORD *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  unsigned int v44; // edi
  SIZE_T v45; // rax
  unsigned __int64 v46; // kr40_8
  unsigned __int16 *v47; // rax

  v2 = 0;
  if ( a1 )
  {
    v3 = *a1;
    if ( (_DWORD)v3 == 11 )
    {
LABEL_3:
      v4 = HeapAlloc(ghSensHeap, 0, 0x38u);
      v5 = v4;
      if ( v4 )
      {
        v6 = 2147483646;
        *(_OWORD *)v4 = *(_OWORD *)a1;
        *((_OWORD *)v4 + 1) = *((_OWORD *)a1 + 1);
        *((_OWORD *)v4 + 2) = *((_OWORD *)a1 + 2);
        v4[6] = *((_QWORD *)a1 + 6);
        v4[2] = 0;
        v4[3] = 0;
        v4[4] = 0;
        v7 = *((_QWORD *)a1 + 2);
        if ( v7 )
        {
          v19 = -1;
          do
            v10 = *(_WORD *)(v7 + 2 * v19++ + 2) == 0;
          while ( !v10 );
          v20 = (unsigned int)(v19 + 1);
          v21 = 2 * v20;
          if ( !is_mul_ok(v20, 2u) )
            v21 = -1;
          v22 = HeapAlloc(ghSensHeap, 0, v21);
          v5[2] = v22;
          v23 = v22;
          if ( !v22 )
            goto LABEL_51;
          if ( v20 )
          {
            if ( v20 > 0x7FFFFFFF )
            {
              *v22 = 0;
            }
            else
            {
              v24 = (_WORD *)*((_QWORD *)a1 + 2);
              v25 = 2147483646;
              do
              {
                if ( !v25 )
                  break;
                if ( !*v24 )
                  break;
                *v23++ = *v24++;
                --v25;
                --v20;
              }
              while ( v20 );
              v26 = v23 - 1;
              if ( v20 )
                v26 = v23;
              *v26 = 0;
            }
          }
        }
        v8 = *((_QWORD *)a1 + 3);
        if ( v8 )
        {
          v9 = -1;
          do
            v10 = *(_WORD *)(v8 + 2 * v9++ + 2) == 0;
          while ( !v10 );
          v11 = (unsigned int)(v9 + 1);
          v12 = 2 * v11;
          if ( !is_mul_ok(v11, 2u) )
            v12 = -1;
          v13 = HeapAlloc(ghSensHeap, 0, v12);
          v5[3] = v13;
          v14 = v13;
          if ( !v13 )
            goto LABEL_51;
          if ( v11 )
          {
            if ( v11 > 0x7FFFFFFF )
            {
              *v13 = 0;
            }
            else
            {
              v15 = (_WORD *)*((_QWORD *)a1 + 3);
              do
              {
                if ( !v6 )
                  break;
                if ( !*v15 )
                  break;
                *v14++ = *v15++;
                --v6;
                --v11;
              }
              while ( v11 );
              v16 = v14 - 1;
              if ( v11 )
                v16 = v14;
              *v16 = 0;
            }
          }
        }
        v17 = *((_QWORD *)a1 + 4);
        if ( !v17 )
          return v5;
        v34 = -1;
        do
          v10 = *(_WORD *)(v17 + 2 * v34++ + 2) == 0;
        while ( !v10 );
        v35 = (unsigned int)(v34 + 1);
        v36 = 2 * v35;
        if ( !is_mul_ok(v35, 2u) )
          v36 = -1;
        v37 = (unsigned __int16 *)HeapAlloc(ghSensHeap, 0, v36);
        v5[4] = v37;
        if ( v37 )
        {
          StringCchCopyW(v37, v35, *((const unsigned __int16 **)a1 + 4));
          return v5;
        }
LABEL_51:
        FreeEventData(v5);
      }
    }
    else
    {
      switch ( (int)v3 )
      {
        case 0:
          v27 = HeapAlloc(ghSensHeap, 0, 0x20u);
          v28 = v27;
          if ( !v27 )
            return v2;
          *(_OWORD *)v27 = *(_OWORD *)a1;
          *((_OWORD *)v27 + 1) = *((_OWORD *)a1 + 1);
          v27[3] = 0;
          v29 = *((_QWORD *)a1 + 3);
          if ( !v29 )
            goto LABEL_68;
          v30 = -1;
          do
            v10 = *(_WORD *)(v29 + 2 * v30++ + 2) == 0;
          while ( !v10 );
          v31 = (unsigned int)(v30 + 1);
          v32 = 2 * v31;
          if ( !is_mul_ok(v31, 2u) )
            v32 = -1;
          v33 = (unsigned __int16 *)HeapAlloc(ghSensHeap, 0, v32);
          v28[3] = v33;
          if ( !v33 )
            goto LABEL_45;
          StringCchCopyW(v33, v31, *((const unsigned __int16 **)a1 + 3));
          v2 = v28;
          break;
        case 2:
        case 3:
        case 5:
        case 6:
        case 7:
        case 8:
        case 10:
        case 12:
        case 13:
          goto LABEL_3;
        case 14:
        case 15:
        case 16:
        case 17:
          v38 = HeapAlloc(ghSensHeap, 0, 0x10u);
          if ( v38 )
          {
            v2 = v38;
            *v38 = *(_OWORD *)a1;
          }
          return v2;
        case 18:
        case 19:
          v40 = HeapAlloc(ghSensHeap, 0, 0x14u);
          if ( v40 )
          {
            v2 = v40;
            *(_OWORD *)v40 = *(_OWORD *)a1;
            v40[4] = a1[4];
          }
          return v2;
        case 20:
        case 21:
        case 22:
        case 23:
        case 24:
          v39 = HeapAlloc(ghSensHeap, 0, 8u);
          if ( v39 )
          {
            v2 = v39;
            *v39 = *(_QWORD *)a1;
          }
          return v2;
        case 25:
        case 26:
          v41 = HeapAlloc(ghSensHeap, 0, 0x18u);
          v28 = v41;
          if ( !v41 )
            return v2;
          *(_OWORD *)v41 = *(_OWORD *)a1;
          v41[2] = *((_QWORD *)a1 + 2);
          v41[1] = 0;
          v42 = *((_QWORD *)a1 + 1);
          if ( !v42 )
            goto LABEL_68;
          v43 = -1;
          do
            v10 = *(_WORD *)(v42 + 2 * v43++ + 2) == 0;
          while ( !v10 );
          v44 = v43 + 1;
          v46 = (unsigned int)(v43 + 1);
          v45 = 2 * v46;
          if ( !is_mul_ok(v46, 2u) )
            v45 = -1;
          v47 = (unsigned __int16 *)HeapAlloc(ghSensHeap, 0, v45);
          v28[1] = v47;
          if ( v47 )
          {
            StringCchCopyW(v47, v44, *((const unsigned __int16 **)a1 + 1));
LABEL_68:
            v2 = v28;
          }
          else
          {
LABEL_45:
            FreeEventData(v28);
          }
          break;
        default:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids, v3);
          }
          return v2;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180003190  push    rsi
0x180003192  push    r12
0x180003194  push    r14
0x180003196  sub     rsp, 20h
0x18000319a  xor     r12d, r12d
0x18000319d  mov     rsi, rcx
0x1800031a0  mov     r14d, r12d
0x1800031a3  test    rcx, rcx
0x1800031a6  jz      loc_1800032EA
0x1800031ac  movsxd  r9, dword ptr [rcx]
0x1800031af  mov     [rsp+38h+arg_0], rbx
0x1800031b4  mov     [rsp+38h+arg_10], rdi
0x1800031b9  mov     [rsp+38h+arg_18], r15
0x1800031be  cmp     r9d, 0Bh
0x1800031c2  jnz     loc_180003396
0x1800031c8  mov     rcx, cs:?ghSensHeap@@3PEAXEA; jumptable 00000001800033BA cases 2,3,5-8,10,12,13
0x1800031cf  xor     edx, edx; dwFlags
0x1800031d1  mov     r8d, 38h ; '8'; dwBytes
0x1800031d7  mov     [rsp+38h+arg_8], rbp
0x1800031dc  call    cs:__imp_HeapAlloc
0x1800031e2  mov     rbp, rax
0x1800031e5  test    rax, rax
0x1800031e8  jz      loc_1800032D6
0x1800031ee  movups  xmm0, xmmword ptr [rsi]
0x1800031f1  mov     edi, 7FFFFFFEh
0x1800031f6  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800031fd  movups  xmmword ptr [rax], xmm0
0x180003200  movups  xmm1, xmmword ptr [rsi+10h]
0x180003204  movups  xmmword ptr [rax+10h], xmm1
0x180003208  movups  xmm0, xmmword ptr [rsi+20h]
0x18000320c  movups  xmmword ptr [rax+20h], xmm0
0x180003210  movsd   xmm1, qword ptr [rsi+30h]
0x180003215  movsd   qword ptr [rax+30h], xmm1
0x18000321a  mov     [rax+10h], r12
0x18000321e  mov     [rax+18h], r12
0x180003222  mov     [rax+20h], r12
0x180003226  mov     rcx, [rsi+10h]
0x18000322a  test    rcx, rcx
0x18000322d  jnz     loc_1800032F7
0x180003233  mov     rcx, [rsi+18h]
0x180003237  test    rcx, rcx
0x18000323a  jz      loc_1800032C6
0x180003240  mov     rax, r15
0x180003243  cmp     [rcx+rax*2+2], r12w
0x180003249  lea     rax, [rax+1]
0x18000324d  jnz     short loc_180003243
0x18000324f  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180003256  lea     ebx, [rax+1]
0x180003259  mov     eax, 2
0x18000325e  mul     rbx
0x180003261  cmovb   rax, r15
0x180003265  xor     edx, edx; dwFlags
0x180003267  mov     r8, rax; dwBytes
0x18000326a  call    cs:__imp_HeapAlloc
0x180003270  mov     [rbp+18h], rax
0x180003274  mov     rdx, rax
0x180003277  test    rax, rax
0x18000327a  jz      loc_180003496
0x180003280  test    rbx, rbx
0x180003283  jz      short loc_1800032C6
0x180003285  cmp     rbx, 7FFFFFFFh
0x18000328c  ja      loc_180003644
0x180003292  mov     rcx, [rsi+18h]
0x180003296  test    rdi, rdi
0x180003299  jz      short loc_1800032B7
0x18000329b  movzx   eax, word ptr [rcx]
0x18000329e  test    ax, ax
0x1800032a1  jz      short loc_1800032B7
0x1800032a3  mov     [rdx], ax
0x1800032a6  add     rcx, 2
0x1800032aa  add     rdx, 2
0x1800032ae  dec     rdi
0x1800032b1  sub     rbx, 1
0x1800032b5  jnz     short loc_180003296
0x1800032b7  test    rbx, rbx
0x1800032ba  lea     rcx, [rdx-2]
0x1800032be  cmovnz  rcx, rdx
0x1800032c2  mov     [rcx], r12w
0x1800032c6  mov     rax, [rsi+20h]
0x1800032ca  test    rax, rax
0x1800032cd  jnz     loc_180003453
0x1800032d3  mov     r14, rbp
0x1800032d6  mov     rbp, [rsp+38h+arg_8]
0x1800032db  mov     rdi, [rsp+38h+arg_10]
0x1800032e0  mov     rbx, [rsp+38h+arg_0]
0x1800032e5  mov     r15, [rsp+38h+arg_18]
0x1800032ea  mov     rax, r14
0x1800032ed  add     rsp, 20h
0x1800032f1  pop     r14
0x1800032f3  pop     r12
0x1800032f5  pop     rsi
0x1800032f6  retn
0x1800032f7  mov     rax, r15
0x1800032fa  nop     word ptr [rax+rax+00h]
0x180003300  cmp     [rcx+rax*2+2], r12w
0x180003306  lea     rax, [rax+1]
0x18000330a  jnz     short loc_180003300
0x18000330c  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180003313  lea     ebx, [rax+1]
0x180003316  mov     eax, 2
0x18000331b  mul     rbx
0x18000331e  cmovb   rax, r15
0x180003322  xor     edx, edx; dwFlags
0x180003324  mov     r8, rax; dwBytes
0x180003327  call    cs:__imp_HeapAlloc
0x18000332d  mov     [rbp+10h], rax
0x180003331  mov     r8, rax
0x180003334  test    rax, rax
0x180003337  jz      loc_180003496
0x18000333d  test    rbx, rbx
0x180003340  jz      loc_180003233
0x180003346  cmp     rbx, 7FFFFFFFh
0x18000334d  ja      loc_18000363B
0x180003353  mov     rdx, [rsi+10h]
0x180003357  mov     rcx, rdi
0x18000335a  nop     word ptr [rax+rax+00h]
0x180003360  test    rcx, rcx
0x180003363  jz      short loc_180003382
0x180003365  movzx   eax, word ptr [rdx]
0x180003368  test    ax, ax
0x18000336b  jz      short loc_180003382
0x18000336d  mov     [r8], ax
0x180003371  add     rdx, 2
0x180003375  add     r8, 2
0x180003379  dec     rcx
0x18000337c  sub     rbx, 1
0x180003380  jnz     short loc_180003360
0x180003382  test    rbx, rbx
0x180003385  lea     rcx, [r8-2]
0x180003389  cmovnz  rcx, r8
0x18000338d  mov     [rcx], r12w
0x180003391  jmp     loc_180003233
0x180003396  cmp     r9d, 1Ah; switch 27 cases
0x18000339a  ja      def_1800033BA; jumptable 00000001800033BA default case, cases 1,4,9,11
0x1800033a0  lea     rdx, __ImageBase
0x1800033a7  movzx   eax, ds:(byte_18000366C - 180000000h)[rdx+r9]
0x1800033b0  mov     ecx, ds:(jpt_1800033BA - 180000000h)[rdx+rax*4]
0x1800033b7  add     rcx, rdx
0x1800033ba  jmp     rcx; switch jump
0x1800033bc  mov     rcx, cs:?ghSensHeap@@3PEAXEA; jumptable 00000001800033BA case 0
0x1800033c3  xor     edx, edx; dwFlags
0x1800033c5  mov     r8d, 20h ; ' '; dwBytes
0x1800033cb  call    cs:__imp_HeapAlloc
0x1800033d1  mov     rbx, rax
0x1800033d4  test    rax, rax
0x1800033d7  jz      loc_1800032DB
0x1800033dd  movups  xmm0, xmmword ptr [rsi]
0x1800033e0  movups  xmmword ptr [rax], xmm0
0x1800033e3  movups  xmm1, xmmword ptr [rsi+10h]
0x1800033e7  movups  xmmword ptr [rax+10h], xmm1
0x1800033eb  mov     [rax+18h], r12
0x1800033ef  mov     rcx, [rsi+18h]
0x1800033f3  test    rcx, rcx
0x1800033f6  jz      loc_1800035EE
0x1800033fc  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180003403  mov     rax, r15
0x180003406  nop     word ptr [rax+rax+00000000h]
0x180003410  cmp     [rcx+rax*2+2], r12w
0x180003416  lea     rax, [rax+1]
0x18000341a  jnz     short loc_180003410
0x18000341c  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180003423  lea     edi, [rax+1]
0x180003426  mov     eax, 2
0x18000342b  mul     rdi
0x18000342e  cmovb   rax, r15
0x180003432  xor     edx, edx; dwFlags
0x180003434  mov     r8, rax; dwBytes
0x180003437  call    cs:__imp_HeapAlloc
0x18000343d  mov     [rbx+18h], rax
0x180003441  test    rax, rax
0x180003444  jnz     short loc_1800034A3
0x180003446  mov     rcx, rbx; lpMem
0x180003449  call    ?FreeEventData@@YAXPEAX@Z; FreeEventData(void *)
0x18000344e  jmp     loc_1800032DB
0x180003453  mov     rcx, r15
0x180003456  nop     word ptr [rax+rax+00000000h]
0x180003460  cmp     [rax+rcx*2+2], r12w
0x180003466  lea     rcx, [rcx+1]
0x18000346a  jnz     short loc_180003460
0x18000346c  lea     ebx, [rcx+1]
0x18000346f  mov     eax, 2
0x180003474  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x18000347b  mul     rbx
0x18000347e  cmovb   rax, r15
0x180003482  xor     edx, edx; dwFlags
0x180003484  mov     r8, rax; dwBytes
0x180003487  call    cs:__imp_HeapAlloc
0x18000348d  mov     [rbp+20h], rax
0x180003491  test    rax, rax
0x180003494  jnz     short loc_180003515
0x180003496  mov     rcx, rbp; lpMem
0x180003499  call    ?FreeEventData@@YAXPEAX@Z; FreeEventData(void *)
0x18000349e  jmp     loc_1800032D6
0x1800034a3  mov     r8, [rsi+18h]; unsigned __int16 *
0x1800034a7  mov     rdx, rdi; unsigned __int64
0x1800034aa  mov     rcx, rax; unsigned __int16 *
0x1800034ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800034b2  mov     r14, rbx
0x1800034b5  jmp     loc_1800032DB
0x1800034ba  mov     rcx, cs:?ghSensHeap@@3PEAXEA; jumptable 00000001800033BA cases 14-17
0x1800034c1  xor     edx, edx; dwFlags
0x1800034c3  mov     r8d, 10h; dwBytes
0x1800034c9  call    cs:__imp_HeapAlloc
0x1800034cf  test    rax, rax
0x1800034d2  jz      loc_1800032DB
0x1800034d8  movups  xmm0, xmmword ptr [rsi]
0x1800034db  mov     r14, rax
0x1800034de  movups  xmmword ptr [rax], xmm0
0x1800034e1  jmp     loc_1800032DB
0x1800034e6  mov     rcx, cs:?ghSensHeap@@3PEAXEA; jumptable 00000001800033BA cases 20-24
0x1800034ed  xor     edx, edx; dwFlags
0x1800034ef  mov     r8d, 8; dwBytes
0x1800034f5  call    cs:__imp_HeapAlloc
0x1800034fb  mov     rcx, rax
0x1800034fe  test    rax, rax
0x180003501  jz      loc_1800032DB
0x180003507  mov     rax, [rsi]
0x18000350a  mov     r14, rcx
0x18000350d  mov     [rcx], rax
0x180003510  jmp     loc_1800032DB
0x180003515  mov     r8, [rsi+20h]; unsigned __int16 *
0x180003519  mov     rdx, rbx; unsigned __int64
0x18000351c  mov     rcx, rax; unsigned __int16 *
0x18000351f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003524  jmp     loc_1800032D3
0x180003529  mov     rcx, cs:?ghSensHeap@@3PEAXEA; jumptable 00000001800033BA cases 18,19
0x180003530  xor     edx, edx; dwFlags
0x180003532  mov     r8d, 14h; dwBytes
0x180003538  call    cs:__imp_HeapAlloc
0x18000353e  mov     rcx, rax
0x180003541  test    rax, rax
0x180003544  jz      loc_1800032DB
0x18000354a  movups  xmm0, xmmword ptr [rsi]
0x18000354d  mov     r14, rcx
0x180003550  movups  xmmword ptr [rax], xmm0
0x180003553  mov     eax, [rsi+10h]
0x180003556  mov     [rcx+10h], eax
0x180003559  jmp     loc_1800032DB
0x18000355e  mov     rcx, cs:?ghSensHeap@@3PEAXEA; jumptable 00000001800033BA cases 25,26
0x180003565  xor     edx, edx; dwFlags
0x180003567  mov     r8d, 18h; dwBytes
0x18000356d  call    cs:__imp_HeapAlloc
0x180003573  mov     rbx, rax
0x180003576  test    rax, rax
0x180003579  jz      loc_1800032DB
0x18000357f  movups  xmm0, xmmword ptr [rsi]
0x180003582  movups  xmmword ptr [rax], xmm0
0x180003585  movsd   xmm1, qword ptr [rsi+10h]
0x18000358a  movsd   qword ptr [rax+10h], xmm1
0x18000358f  mov     [rax+8], r12
0x180003593  mov     rcx, [rsi+8]
0x180003597  test    rcx, rcx
0x18000359a  jz      short loc_1800035EE
0x18000359c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800035a3  mov     rax, r15
0x1800035a6  cmp     [rcx+rax*2+2], r12w
0x1800035ac  lea     rax, [rax+1]
0x1800035b0  jnz     short loc_1800035A6
0x1800035b2  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x1800035b9  lea     edi, [rax+1]
0x1800035bc  mov     eax, 2
0x1800035c1  mul     rdi
0x1800035c4  cmovb   rax, r15
0x1800035c8  xor     edx, edx; dwFlags
0x1800035ca  mov     r8, rax; dwBytes
0x1800035cd  call    cs:__imp_HeapAlloc
0x1800035d3  mov     [rbx+8], rax
0x1800035d7  test    rax, rax
0x1800035da  jz      loc_180003446
0x1800035e0  mov     r8, [rsi+8]; unsigned __int16 *
0x1800035e4  mov     edx, edi; unsigned __int64
0x1800035e6  mov     rcx, rax; unsigned __int16 *
0x1800035e9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800035ee  mov     r14, rbx
0x1800035f1  jmp     loc_1800032DB
0x1800035f6  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 00000001800033BA default case, cases 1,4,9,11
0x1800035fd  lea     rax, WPP_GLOBAL_Control
0x180003604  cmp     rcx, rax
0x180003607  jz      loc_1800032DB
0x18000360d  test    byte ptr [rcx+1Ch], 1
0x180003611  jz      loc_1800032DB
0x180003617  cmp     byte ptr [rcx+19h], 2
0x18000361b  jb      loc_1800032DB
0x180003621  mov     rcx, [rcx+10h]
0x180003625  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x18000362c  mov     edx, 16h
0x180003631  call    WPP_SF_d
0x180003636  jmp     loc_1800032DB
0x18000363b  mov     [rax], r12w
0x18000363f  jmp     loc_180003233
0x180003644  mov     [rax], r12w
0x180003648  jmp     loc_1800032C6
```
