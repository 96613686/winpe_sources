# HasIfStateChanged(_IF_STATE,int)

- ea: `0x180002650`
- end: `0x180002b9d`
- name: `?HasIfStateChanged@@YAHU_IF_STATE@@H@Z`
- size: `1357`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002060`

## callees

- `0x180002650`
- `0x1800082b4`
- `0x180008300`
- `0x180009ee8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002684`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002684`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000274f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000274f`

## pseudocode

```c
__int64 __fastcall HasIfStateChanged(__int64 a1, int a2)
{
  int v3; // r12d
  int v4; // ebx
  int v5; // r15d
  __int64 v6; // rdi
  char *v7; // rsi
  __int64 v8; // r9
  unsigned int v9; // r15d
  unsigned int v10; // r8d
  int v11; // r13d
  _QWORD *v12; // rcx
  signed int TickCount; // edx
  int v14; // edi
  __int128 v15; // xmm1
  __int64 v16; // xmm0_8
  int v18; // ebx
  int v19; // ebx
  __int128 v20; // xmm1
  __int64 v21; // rbx
  struct _IF_STATE *v22; // xmm0_8
  unsigned int v23; // eax
  unsigned int v24; // ecx
  unsigned int v25; // edx
  unsigned int v26; // r10d
  unsigned int v27; // r11d
  unsigned int v28; // r14d
  unsigned int v29; // r12d
  unsigned int v30; // r13d
  __int128 v31; // xmm1
  __int64 v32; // xmm0_8
  unsigned int v33; // [rsp+40h] [rbp-48h]
  unsigned int v34; // [rsp+44h] [rbp-44h]
  unsigned int v35; // [rsp+48h] [rbp-40h]

  v3 = 0;
  v4 = 0;
  v5 = a2;
  EnterCriticalSection(&gSensLock);
  while ( 1 )
  {
    if ( v4 >= 5 )
    {
      v14 = 0;
      goto LABEL_18;
    }
    v6 = 40LL * v4;
    v7 = (char *)&gIfState + v6;
    if ( *(_DWORD *)((char *)&gIfState + v6) == 1 )
    {
      v8 = *(unsigned int *)((char *)&gIfState + v6 + 4);
      if ( (_DWORD)v8 == *(_DWORD *)(a1 + 4) )
        break;
    }
    ++v4;
  }
  if ( v5 )
  {
    *(_DWORD *)v7 = 0;
    goto LABEL_44;
  }
  v9 = *(_DWORD *)(a1 + 8);
  v10 = *(_DWORD *)((char *)&gIfState + v6 + 8);
  if ( v9 <= v10 )
  {
    v23 = *(_DWORD *)(a1 + 12);
    v24 = *(_DWORD *)((char *)&gIfState + v6 + 12);
    if ( v23 <= v24 )
    {
      v25 = *(_DWORD *)(a1 + 16);
      v26 = *(_DWORD *)((char *)&gIfState + v6 + 16);
      if ( v25 <= v26 )
      {
        v27 = *(_DWORD *)(a1 + 20);
        v28 = *(_DWORD *)((char *)&gIfState + v6 + 20);
        if ( v27 <= v28 )
        {
          v33 = *(_DWORD *)((char *)&gIfState + v6 + 24);
          if ( *(_DWORD *)(a1 + 24) <= v33 )
          {
            v34 = *(_DWORD *)((char *)&gIfState + v6 + 28);
            if ( *(_DWORD *)(a1 + 28) <= v34 )
            {
              v35 = *(_DWORD *)((char *)&gIfState + v6 + 32);
              if ( *(_DWORD *)(a1 + 32) <= v35 )
              {
                v29 = *(_DWORD *)(a1 + 36);
                v30 = *(_DWORD *)((char *)&gIfState + v6 + 36);
                if ( v29 <= v30 )
                {
                  if ( v9 < v10
                    || v23 < v24
                    || v25 < v26
                    || v27 < v28
                    || *(_DWORD *)(a1 + 24) < v33
                    || *(_DWORD *)(a1 + 28) < v34
                    || *(_DWORD *)(a1 + 32) < v35
                    || v29 < v30 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        22,
                        WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids,
                        v8);
                    }
                    v31 = *(_OWORD *)(a1 + 16);
                    *(_OWORD *)v7 = *(_OWORD *)a1;
                    v32 = *(_QWORD *)(a1 + 32);
                    *((_OWORD *)v7 + 1) = v31;
                    *((_QWORD *)v7 + 4) = v32;
                    *(_DWORD *)v7 = 1;
                  }
                  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      23,
                      WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids,
                      v8);
                  }
LABEL_44:
                  LeaveCriticalSection(&gSensLock);
                  return 0;
                }
              }
            }
          }
          v3 = 0;
        }
      }
    }
  }
  v11 = *(_DWORD *)(a1 + 20)
      - *(_DWORD *)((char *)&gIfState + v6 + 20)
      - (*(_DWORD *)(a1 + 16)
       - *(_DWORD *)((char *)&gIfState + v6 + 16));
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ddddd(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v12 = WPP_GLOBAL_Control;
  }
  if ( v9 == *(_DWORD *)((char *)&gIfState + v6 + 8) && (unsigned int)(v11 + 2) <= 4 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
      WPP_SF_dd(
        v12[2],
        19,
        WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids,
        *(unsigned int *)((char *)&gIfState + v6 + 4),
        v11);
    v14 = 1;
  }
  else
  {
    dword_1800110D0 = v4;
    v3 = 1;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
      WPP_SF_d(
        v12[2],
        20,
        WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids,
        *(unsigned int *)((char *)&gIfState + v6 + 4));
    TickCount = GetTickCount();
    gdwLastLANTime = TickCount;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids,
        (unsigned int)(TickCount / 1000));
    }
    v14 = 0;
  }
  v15 = *(_OWORD *)(a1 + 16);
  v5 = a2;
  *(_OWORD *)v7 = *(_OWORD *)a1;
  v16 = *(_QWORD *)(a1 + 32);
  *((_OWORD *)v7 + 1) = v15;
  *((_QWORD *)v7 + 4) = v16;
  *(_DWORD *)v7 = 1;
LABEL_18:
  LeaveCriticalSection(&gSensLock);
  if ( v14 == 1 || v5 )
    return 0;
  if ( v3 != 1 )
  {
    v18 = dword_1800110D0;
    EnterCriticalSection(&gSensLock);
    v19 = (v18 + 1) % 5;
    if ( *((_DWORD *)&gIfState + 10 * v19) )
    {
      v19 = (v19 + 1) % 5;
      if ( *((_DWORD *)&gIfState + 10 * v19) )
      {
        v19 = (v19 + 1) % 5;
        if ( *((_DWORD *)&gIfState + 10 * v19) )
        {
          v19 = (v19 + 1) % 5;
          if ( *((_DWORD *)&gIfState + 10 * v19) )
            v19 = (v19 + 1) % 5;
        }
      }
    }
    v20 = *(_OWORD *)(a1 + 16);
    v21 = 40LL * v19;
    *(_OWORD *)((char *)&gIfState + v21) = *(_OWORD *)a1;
    v22 = *(struct _IF_STATE **)(a1 + 32);
    *(_OWORD *)((char *)&gIfState + v21 + 16) = v20;
    *(struct _IF_STATE near **)((char *)&gIfState + v21 + 32) = v22;
    *(_DWORD *)((char *)&gIfState + v21) = 1;
    LeaveCriticalSection(&gSensLock);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids,
        *(unsigned int *)((char *)&gIfState + v21 + 4));
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180002650  mov     [rsp+arg_8], edx
0x180002654  push    rbx
0x180002655  push    rbp
0x180002656  push    rdi
0x180002657  push    r12
0x180002659  push    r13
0x18000265b  push    r15
0x18000265d  sub     rsp, 58h
0x180002661  mov     rbp, rcx
0x180002664  xor     r12d, r12d
0x180002667  xor     edi, edi
0x180002669  mov     [rsp+88h+arg_18], r12d
0x180002671  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002678  mov     [rsp+88h+arg_10], edi
0x18000267f  xor     ebx, ebx
0x180002681  mov     r15d, edx
0x180002684  call    cs:__imp_EnterCriticalSection
0x18000268a  mov     [rsp+88h+arg_0], rsi
0x180002692  lea     r13, ?gIfState@@3PAU_IF_STATE@@A; _IF_STATE near * gIfState
0x180002699  mov     [rsp+88h+var_38], r14
0x18000269e  xchg    ax, ax
0x1800026a0  cmp     ebx, 5
0x1800026a3  jge     loc_1800027AA
0x1800026a9  movsxd  rax, ebx
0x1800026ac  lea     rcx, [rax+rax*4]
0x1800026b0  lea     rdi, ds:0[rcx*8]
0x1800026b8  cmp     dword ptr [rdi+r13], 1
0x1800026bd  lea     rsi, [rdi+r13]
0x1800026c1  jz      short loc_1800026C7
0x1800026c3  inc     ebx
0x1800026c5  jmp     short loc_1800026A0
0x1800026c7  mov     r9d, [rdi+r13+4]
0x1800026cc  cmp     r9d, [rbp+4]
0x1800026d0  jnz     short loc_1800026C3
0x1800026d2  test    r15d, r15d
0x1800026d5  jnz     loc_1800029CF
0x1800026db  mov     r15d, [rbp+8]
0x1800026df  mov     r8d, [rdi+r13+8]
0x1800026e4  cmp     r15d, r8d
0x1800026e7  jbe     loc_18000295F
0x1800026ed  mov     r10d, [rbp+14h]
0x1800026f1  sub     r10d, [rdi+r13+14h]
0x1800026f6  mov     r9d, [rbp+10h]
0x1800026fa  sub     r9d, [rdi+r13+10h]
0x1800026ff  mov     r13d, r10d
0x180002702  sub     r13d, r9d
0x180002705  mov     rcx, cs:WPP_GLOBAL_Control
0x18000270c  lea     r14, WPP_GLOBAL_Control
0x180002713  cmp     rcx, r14
0x180002716  jz      short loc_180002722
0x180002718  test    byte ptr [rcx+1Ch], 1
0x18000271c  jnz     loc_180002AC6
0x180002722  lea     r8, ?gIfState@@3PAU_IF_STATE@@A; _IF_STATE near * gIfState
0x180002729  cmp     r15d, [rdi+r8+8]
0x18000272e  jz      loc_180002939
0x180002734  mov     cs:dword_1800110D0, ebx
0x18000273a  mov     r12d, 1
0x180002740  cmp     rcx, r14
0x180002743  jz      short loc_18000274F
0x180002745  test    [rcx+1Ch], r12b
0x180002749  jnz     loc_180002B39
0x18000274f  call    cs:__imp_GetTickCount
0x180002755  mov     edx, eax
0x180002757  mov     cs:?gdwLastLANTime@@3JA, eax; long gdwLastLANTime
0x18000275d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002764  cmp     rcx, r14
0x180002767  jz      short loc_180002773
0x180002769  test    [rcx+1Ch], r12b
0x18000276d  jnz     loc_180002B62
0x180002773  mov     edi, [rsp+88h+arg_10]
0x18000277a  movaps  xmm0, xmmword ptr [rbp+0]
0x18000277e  lea     r13, ?gIfState@@3PAU_IF_STATE@@A; _IF_STATE near * gIfState
0x180002785  movaps  xmm1, xmmword ptr [rbp+10h]
0x180002789  mov     r15d, [rsp+88h+arg_8]
0x180002791  movups  xmmword ptr [rsi], xmm0
0x180002794  movsd   xmm0, qword ptr [rbp+20h]
0x180002799  movups  xmmword ptr [rsi+10h], xmm1
0x18000279d  movsd   qword ptr [rsi+20h], xmm0
0x1800027a2  mov     dword ptr [rsi], 1
0x1800027a8  jmp     short loc_1800027B4
0x1800027aa  lea     r14, WPP_GLOBAL_Control
0x1800027b1  mov     edi, r12d
0x1800027b4  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800027bb  call    cs:__imp_LeaveCriticalSection
0x1800027c1  cmp     edi, 1
0x1800027c4  jz      short loc_1800027CB
0x1800027c6  test    r15d, r15d
0x1800027c9  jz      short loc_1800027E8
0x1800027cb  xor     eax, eax
0x1800027cd  mov     r14, [rsp+88h+var_38]
0x1800027d2  mov     rsi, [rsp+88h+arg_0]
0x1800027da  add     rsp, 58h
0x1800027de  pop     r15
0x1800027e0  pop     r13
0x1800027e2  pop     r12
0x1800027e4  pop     rdi
0x1800027e5  pop     rbp
0x1800027e6  pop     rbx
0x1800027e7  retn
0x1800027e8  cmp     r12d, 1
0x1800027ec  jz      loc_180002907
0x1800027f2  mov     ebx, cs:dword_1800110D0
0x1800027f8  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800027ff  call    cs:__imp_EnterCriticalSection
0x180002805  inc     ebx
0x180002807  mov     eax, 66666667h
0x18000280c  imul    ebx
0x18000280e  sar     edx, 1
0x180002810  mov     eax, edx
0x180002812  shr     eax, 1Fh
0x180002815  add     edx, eax
0x180002817  lea     eax, [rdx+rdx*4]
0x18000281a  sub     ebx, eax
0x18000281c  movsxd  rax, ebx
0x18000281f  lea     rcx, [rax+rax*4]
0x180002823  cmp     dword ptr [r13+rcx*8+0], 0
0x180002829  jz      loc_1800028B8
0x18000282f  inc     ebx
0x180002831  mov     eax, 66666667h
0x180002836  imul    ebx
0x180002838  sar     edx, 1
0x18000283a  mov     eax, edx
0x18000283c  shr     eax, 1Fh
0x18000283f  add     edx, eax
0x180002841  lea     eax, [rdx+rdx*4]
0x180002844  sub     ebx, eax
0x180002846  movsxd  rax, ebx
0x180002849  lea     rcx, [rax+rax*4]
0x18000284d  cmp     dword ptr [r13+rcx*8+0], 0
0x180002853  jz      short loc_1800028B8
0x180002855  inc     ebx
0x180002857  mov     eax, 66666667h
0x18000285c  imul    ebx
0x18000285e  sar     edx, 1
0x180002860  mov     eax, edx
0x180002862  shr     eax, 1Fh
0x180002865  add     edx, eax
0x180002867  lea     eax, [rdx+rdx*4]
0x18000286a  sub     ebx, eax
0x18000286c  movsxd  rax, ebx
0x18000286f  lea     rcx, [rax+rax*4]
0x180002873  cmp     dword ptr [r13+rcx*8+0], 0
0x180002879  jz      short loc_1800028B8
0x18000287b  inc     ebx
0x18000287d  mov     eax, 66666667h
0x180002882  imul    ebx
0x180002884  sar     edx, 1
0x180002886  mov     ecx, edx
0x180002888  shr     ecx, 1Fh
0x18000288b  add     edx, ecx
0x18000288d  lea     ecx, [rdx+rdx*4]
0x180002890  sub     ebx, ecx
0x180002892  movsxd  rcx, ebx
0x180002895  lea     rdx, [rcx+rcx*4]
0x180002899  cmp     dword ptr [r13+rdx*8+0], 0
0x18000289f  jz      short loc_1800028B8
0x1800028a1  inc     ebx
0x1800028a3  mov     eax, 66666667h
0x1800028a8  imul    ebx
0x1800028aa  sar     edx, 1
0x1800028ac  mov     eax, edx
0x1800028ae  shr     eax, 1Fh
0x1800028b1  add     edx, eax
0x1800028b3  lea     eax, [rdx+rdx*4]
0x1800028b6  sub     ebx, eax
0x1800028b8  movaps  xmm0, xmmword ptr [rbp+0]
0x1800028bc  movaps  xmm1, xmmword ptr [rbp+10h]
0x1800028c0  movsxd  rax, ebx
0x1800028c3  lea     rcx, [rax+rax*4]
0x1800028c7  lea     rbx, ds:0[rcx*8]
0x1800028cf  movups  xmmword ptr [rbx+r13], xmm0
0x1800028d4  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800028db  movsd   xmm0, qword ptr [rbp+20h]
0x1800028e0  movups  xmmword ptr [rbx+r13+10h], xmm1
0x1800028e6  movsd   qword ptr [rbx+r13+20h], xmm0
0x1800028ed  mov     dword ptr [rbx+r13], 1
0x1800028f5  call    cs:__imp_LeaveCriticalSection
0x1800028fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180002902  cmp     rcx, r14
0x180002905  jnz     short loc_180002911
0x180002907  mov     eax, 1
0x18000290c  jmp     loc_1800027CD
0x180002911  test    byte ptr [rcx+1Ch], 1
0x180002915  jz      short loc_180002907
0x180002917  cmp     byte ptr [rcx+19h], 4
0x18000291b  jb      short loc_180002907
0x18000291d  mov     r9d, [rbx+r13+4]
0x180002922  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180002929  mov     rcx, [rcx+10h]
0x18000292d  mov     edx, 18h
0x180002932  call    WPP_SF_d
0x180002937  jmp     short loc_180002907
0x180002939  lea     eax, [r13+2]
0x18000293d  cmp     eax, 4
0x180002940  ja      loc_180002734
0x180002946  cmp     rcx, r14
0x180002949  jz      short loc_180002955
0x18000294b  test    byte ptr [rcx+1Ch], 1
0x18000294f  jnz     loc_180002B0B
0x180002955  mov     edi, 1
0x18000295a  jmp     loc_18000277A
0x18000295f  mov     eax, [rbp+0Ch]
0x180002962  mov     ecx, [rdi+r13+0Ch]
0x180002967  cmp     eax, ecx
0x180002969  ja      loc_1800026ED
0x18000296f  mov     edx, [rbp+10h]
0x180002972  mov     r10d, [rdi+r13+10h]
0x180002977  cmp     edx, r10d
0x18000297a  ja      loc_1800026ED
0x180002980  mov     r11d, [rbp+14h]
0x180002984  mov     r14d, [rdi+r13+14h]
0x180002989  cmp     r11d, r14d
0x18000298c  ja      loc_1800026ED
0x180002992  mov     r12d, [rdi+r13+18h]
0x180002997  mov     [rsp+88h+var_48], r12d
0x18000299c  cmp     [rbp+18h], r12d
0x1800029a0  ja      short loc_1800029C2
0x1800029a2  mov     r12d, [rdi+r13+1Ch]
0x1800029a7  mov     [rsp+88h+var_44], r12d
0x1800029ac  cmp     [rbp+1Ch], r12d
0x1800029b0  ja      short loc_1800029C2
0x1800029b2  mov     r12d, [rdi+r13+20h]
0x1800029b7  mov     [rsp+88h+var_40], r12d
0x1800029bc  cmp     [rbp+20h], r12d
0x1800029c0  jbe     short loc_1800029E4
0x1800029c2  mov     r12d, [rsp+88h+arg_18]
0x1800029ca  jmp     loc_1800026ED
0x1800029cf  mov     [rsi], r12d
0x1800029d2  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800029d9  call    cs:__imp_LeaveCriticalSection
0x1800029df  jmp     loc_1800027CB
0x1800029e4  mov     r12d, [rbp+24h]
0x1800029e8  mov     r13d, [rdi+r13+24h]
0x1800029ed  cmp     r12d, r13d
0x1800029f0  ja      loc_180002ABA
0x1800029f6  cmp     r15d, r8d
0x1800029f9  jb      short loc_180002A62
0x1800029fb  cmp     eax, ecx
0x1800029fd  jb      short loc_180002A62
0x1800029ff  cmp     edx, r10d
0x180002a02  jb      short loc_180002A62
0x180002a04  cmp     r11d, r14d
0x180002a07  jb      short loc_180002A62
0x180002a09  mov     eax, [rsp+88h+var_48]
0x180002a0d  cmp     [rbp+18h], eax
0x180002a10  jb      short loc_180002A62
0x180002a12  mov     eax, [rsp+88h+var_44]
0x180002a16  cmp     [rbp+1Ch], eax
0x180002a19  jb      short loc_180002A62
0x180002a1b  mov     eax, [rsp+88h+var_40]
0x180002a1f  cmp     [rbp+20h], eax
0x180002a22  jb      short loc_180002A62
0x180002a24  cmp     r12d, r13d
0x180002a27  jb      short loc_180002A62
0x180002a29  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a30  lea     r14, WPP_GLOBAL_Control
0x180002a37  cmp     rcx, r14
0x180002a3a  jz      short loc_1800029D2
0x180002a3c  test    byte ptr [rcx+1Ch], 1
0x180002a40  jz      short loc_1800029D2
0x180002a42  cmp     byte ptr [rcx+19h], 5
0x180002a46  jb      short loc_1800029D2
0x180002a48  mov     rcx, [rcx+10h]
0x180002a4c  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180002a53  mov     edx, 17h
0x180002a58  call    WPP_SF_d
0x180002a5d  jmp     loc_1800029D2
0x180002a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a69  lea     r14, WPP_GLOBAL_Control
0x180002a70  cmp     rcx, r14
0x180002a73  jz      short loc_180002A96
0x180002a75  test    byte ptr [rcx+1Ch], 1
0x180002a79  jz      short loc_180002A96
0x180002a7b  cmp     byte ptr [rcx+19h], 5
0x180002a7f  jb      short loc_180002A96
0x180002a81  mov     rcx, [rcx+10h]
0x180002a85  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180002a8c  mov     edx, 16h
0x180002a91  call    WPP_SF_d
0x180002a96  movaps  xmm0, xmmword ptr [rbp+0]
0x180002a9a  movaps  xmm1, xmmword ptr [rbp+10h]
0x180002a9e  movups  xmmword ptr [rsi], xmm0
0x180002aa1  movsd   xmm0, qword ptr [rbp+20h]
0x180002aa6  movups  xmmword ptr [rsi+10h], xmm1
0x180002aaa  movsd   qword ptr [rsi+20h], xmm0
0x180002aaf  mov     dword ptr [rsi], 1
0x180002ab5  jmp     loc_1800029D2
0x180002aba  lea     r13, ?gIfState@@3PAU_IF_STATE@@A; _IF_STATE near * gIfState
0x180002ac1  jmp     loc_1800029C2
0x180002ac6  cmp     byte ptr [rcx+19h], 5
0x180002aca  jb      loc_180002722
0x180002ad0  mov     edx, [rbp+0Ch]
0x180002ad3  lea     rax, ?gIfState@@3PAU_IF_STATE@@A; _IF_STATE near * gIfState
0x180002ada  sub     edx, [rdi+rax+0Ch]
0x180002ade  mov     eax, r15d
0x180002ae1  mov     rcx, [rcx+10h]
0x180002ae5  sub     eax, r8d
0x180002ae8  mov     [rsp+88h+var_50], edx
0x180002aec  mov     [rsp+88h+var_58], eax
0x180002af0  mov     [rsp+88h+var_60], r13d
  ... truncated ...
```
