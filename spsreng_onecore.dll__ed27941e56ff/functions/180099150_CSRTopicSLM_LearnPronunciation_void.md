# CSRTopicSLM::LearnPronunciation(void)

- ea: `0x180099150`
- end: `0x180099387`
- name: `?LearnPronunciation@CSRTopicSLM@@AEAAJXZ`
- size: `567`
- prototype: `__int64 __fastcall(CSRTopicSLM *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180098e60`

## callees

- `0x180002470`
- `0x180002aac`
- `0x180004010`
- `0x180099150`
- `0x18009a55c`
- `0x18009d8b0`
- `0x18009ebfc`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009935e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009935e`

## pseudocode

```c
__int64 __fastcall CSRTopicSLM::LearnPronunciation(CSRTopicSLM *this)
{
  __int64 v2; // rcx
  int updated; // r15d
  _QWORD *v4; // rcx
  __int16 v5; // dx
  double v6; // xmm6_8
  int v7; // ebp
  double v8; // xmm0_8
  double v9; // xmm0_8
  unsigned int v10; // r12d
  int *v11; // rax
  int *v12; // rbx
  int v13; // ebp
  int *v14; // rdi
  unsigned __int64 i; // rcx
  const unsigned __int16 *v16; // rdi
  int v17; // r14d
  unsigned int v18; // edi
  int v19; // r13d
  __int64 v20; // rbp
  int UnigramLProb; // eax
  int *v22; // rdx
  LPVOID pv[2]; // [rsp+30h] [rbp-78h] BYREF
  _QWORD *v25; // [rsp+40h] [rbp-68h]
  int *v26; // [rsp+B0h] [rbp+8h] BYREF

  v25 = 0;
  v2 = *((_QWORD *)this + 3);
  *(_OWORD *)pv = 0;
  updated = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPVOID *, int))(*(_QWORD *)v2 + 64LL))(
              v2,
              *((_QWORD *)this + 12),
              4294959103LL,
              pv,
              1);
  if ( updated >= 0 )
  {
    v4 = v25;
    v5 = 0;
    if ( v25 )
    {
      do
      {
        v4 = (_QWORD *)*v4;
        ++v5;
      }
      while ( v4 );
      if ( v5 )
      {
        v6 = (double)v5;
        if ( v6 > 0.0 )
        {
          v8 = o_log_0(v6) * 10000.50002500125;
          if ( v6 <= 1.0 )
            v9 = v8 - 0.5;
          else
            v9 = v8 + 0.5;
          v7 = (int)v9;
        }
        else
        {
          v7 = -690810000;
        }
        v10 = *(_DWORD *)(*((_QWORD *)this + 19) + 36LL);
        v11 = (int *)CWinHeap::Alloc(*((void ***)this + 18), 4LL * v10, 0);
        v26 = v11;
        v12 = v11;
        if ( v11 )
        {
          v13 = -v7;
          if ( v10 )
          {
            v14 = v11;
            for ( i = (4 * (unsigned __int64)v10) >> 2; i; --i )
              *v14++ = 1;
          }
          v16 = (const unsigned __int16 *)v25;
          if ( v25 )
          {
            while ( 1 )
            {
              updated = CSRTopicSLM::UpdateLMUnigramByPhoneIds(this, v16 + 10, &v26, v13);
              if ( updated < 0 )
                break;
              v16 = *(const unsigned __int16 **)v16;
              if ( !v16 )
              {
                v12 = v26;
                goto LABEL_21;
              }
            }
            v12 = v26;
          }
          else
          {
LABEL_21:
            v17 = (int)(o_log_0(0.1) * 10000.50002500125 - 0.5);
            v18 = 0;
            v19 = (int)(o_log_0(0.9) * 10000.50002500125 - 0.5);
            if ( v10 )
            {
              v20 = 0;
              do
              {
                UnigramLProb = CPPT::GetUnigramLProb(*((CPPT **)this + 19), v18);
                v22 = &v12[v20];
                if ( *v22 != 1 )
                {
                  UnigramLProb += v19;
                  if ( UnigramLProb <= v17 + *v22 )
                    UnigramLProb = v17 + *v22;
                }
                ++v18;
                *v22 = UnigramLProb;
                ++v20;
              }
              while ( v18 < v10 );
            }
            CPPT::AdjustUnigramLProbs(*((CPPT **)this + 19), v12, v10);
          }
        }
        else
        {
          updated = -2147024882;
        }
        if ( v12 )
          CWinHeap::Free(*((CWinHeap **)this + 18), v12);
      }
    }
  }
  if ( pv[1] )
    CoTaskMemFree(pv[1]);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180099150  push    rbx
0x180099152  push    rbp
0x180099153  push    rsi
0x180099154  push    rdi
0x180099155  push    r12
0x180099157  push    r13
0x180099159  push    r14
0x18009915b  push    r15
0x18009915d  sub     rsp, 68h
0x180099161  xor     eax, eax
0x180099163  movaps  [rsp+0A8h+var_58], xmm6
0x180099168  mov     rsi, rcx
0x18009916b  mov     [rsp+0A8h+var_68], rax
0x180099170  mov     rcx, [rcx+18h]
0x180099174  lea     r9, [rsp+0A8h+pv]
0x180099179  xorps   xmm0, xmm0
0x18009917c  mov     edi, 1
0x180099181  movups  xmmword ptr [rsp+0A8h+pv], xmm0
0x180099186  mov     rdx, [rsi+60h]
0x18009918a  mov     r8d, 0FFFFDFFFh
0x180099190  mov     rax, [rcx]
0x180099193  mov     [rsp+0A8h+var_88], edi
0x180099197  mov     rax, [rax+40h]
0x18009919b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800991a0  xor     r13d, r13d
0x1800991a3  mov     r15d, eax
0x1800991a6  test    eax, eax
0x1800991a8  js      loc_180099354
0x1800991ae  mov     rcx, [rsp+0A8h+var_68]
0x1800991b3  mov     edx, r13d
0x1800991b6  test    rcx, rcx
0x1800991b9  jz      loc_180099354
0x1800991bf  mov     rcx, [rcx]
0x1800991c2  add     dx, di
0x1800991c5  test    rcx, rcx
0x1800991c8  jnz     short loc_1800991BF
0x1800991ca  test    dx, dx
0x1800991cd  jz      loc_180099354
0x1800991d3  movsx   eax, dx
0x1800991d6  xorps   xmm0, xmm0
0x1800991d9  movd    xmm6, eax
0x1800991dd  cvtdq2pd xmm6, xmm6
0x1800991e1  comisd  xmm0, xmm6
0x1800991e5  jb      short loc_1800991EE
0x1800991e7  mov     ebp, 0D6D31370h
0x1800991ec  jmp     short loc_18009921E
0x1800991ee  movaps  xmm0, xmm6; X
0x1800991f1  call    _o_log_0
0x1800991f6  comisd  xmm6, cs:__real@3ff0000000000000
0x1800991fe  mulsd   xmm0, cs:__real@40c3884000d1b9c7
0x180099206  jbe     short loc_180099212
0x180099208  addsd   xmm0, cs:__real@3fe0000000000000
0x180099210  jmp     short loc_18009921A
0x180099212  subsd   xmm0, cs:__real@3fe0000000000000
0x18009921a  cvttsd2si ebp, xmm0
0x18009921e  mov     rax, [rsi+98h]
0x180099225  xor     r8d, r8d; bool
0x180099228  mov     rcx, [rsi+90h]; this
0x18009922f  mov     r12d, [rax+24h]
0x180099233  mov     r14d, r12d
0x180099236  shl     r14, 2
0x18009923a  mov     rdx, r14; unsigned __int64
0x18009923d  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x180099242  mov     [rsp+0A8h+arg_0], rax
0x18009924a  mov     rbx, rax
0x18009924d  test    rax, rax
0x180099250  jnz     short loc_18009925D
0x180099252  mov     r15d, 8007000Eh
0x180099258  jmp     loc_180099340
0x18009925d  neg     ebp
0x18009925f  test    r12d, r12d
0x180099262  jz      short loc_180099275
0x180099264  mov     rdi, rax
0x180099267  shr     r14, 2
0x18009926b  mov     rcx, r14
0x18009926e  mov     eax, 1
0x180099273  rep stosd
0x180099275  mov     rdi, [rsp+0A8h+var_68]
0x18009927a  test    rdi, rdi
0x18009927d  jz      short loc_1800992B1
0x18009927f  lea     rdx, [rdi+14h]; unsigned __int16 *
0x180099283  mov     r9d, ebp; int
0x180099286  lea     r8, [rsp+0A8h+arg_0]; int **
0x18009928e  mov     rcx, rsi; this
0x180099291  call    ?UpdateLMUnigramByPhoneIds@CSRTopicSLM@@AEAAJPEBGPEAPEAHH@Z; CSRTopicSLM::UpdateLMUnigramByPhoneIds(ushort const *,int * *,int)
0x180099296  mov     r15d, eax
0x180099299  test    eax, eax
0x18009929b  js      loc_18009937D
0x1800992a1  mov     rdi, [rdi]
0x1800992a4  test    rdi, rdi
0x1800992a7  jnz     short loc_18009927F
0x1800992a9  mov     rbx, [rsp+0A8h+arg_0]
0x1800992b1  movsd   xmm0, cs:__real@3fb999999999999a; X
0x1800992b9  call    _o_log_0
0x1800992be  mulsd   xmm0, cs:__real@40c3884000d1b9c7
0x1800992c6  subsd   xmm0, cs:__real@3fe0000000000000
0x1800992ce  cvttsd2si r14d, xmm0
0x1800992d3  movsd   xmm0, cs:__real@3feccccccccccccd; X
0x1800992db  call    _o_log_0
0x1800992e0  mulsd   xmm0, cs:__real@40c3884000d1b9c7
0x1800992e8  xor     edi, edi
0x1800992ea  subsd   xmm0, cs:__real@3fe0000000000000
0x1800992f2  cvttsd2si r13d, xmm0
0x1800992f7  test    r12d, r12d
0x1800992fa  jz      short loc_18009932E
0x1800992fc  xor     ebp, ebp
0x1800992fe  mov     rcx, [rsi+98h]; this
0x180099305  mov     edx, edi; unsigned int
0x180099307  call    ?GetUnigramLProb@CPPT@@QEAAHI@Z; CPPT::GetUnigramLProb(uint)
0x18009930c  lea     rdx, [rbx+rbp*4]
0x180099310  mov     ecx, [rdx]
0x180099312  cmp     ecx, 1
0x180099315  jz      short loc_180099322
0x180099317  add     ecx, r14d
0x18009931a  add     eax, r13d
0x18009931d  cmp     eax, ecx
0x18009931f  cmovle  eax, ecx
0x180099322  inc     edi
0x180099324  mov     [rdx], eax
0x180099326  inc     rbp
0x180099329  cmp     edi, r12d
0x18009932c  jb      short loc_1800992FE
0x18009932e  mov     rcx, [rsi+98h]; this
0x180099335  mov     r8d, r12d; unsigned int
0x180099338  mov     rdx, rbx; int *
0x18009933b  call    ?AdjustUnigramLProbs@CPPT@@QEAAJPEAHK@Z; CPPT::AdjustUnigramLProbs(int *,ulong)
0x180099340  test    rbx, rbx
0x180099343  jz      short loc_180099354
0x180099345  mov     rcx, [rsi+90h]; this
0x18009934c  mov     rdx, rbx; void *
0x18009934f  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180099354  mov     rcx, [rsp+0A8h+pv+8]; pv
0x180099359  test    rcx, rcx
0x18009935c  jz      short loc_180099364
0x18009935e  call    cs:__imp_CoTaskMemFree
0x180099364  movaps  xmm6, [rsp+0A8h+var_58]
0x180099369  mov     eax, r15d
0x18009936c  add     rsp, 68h
0x180099370  pop     r15
0x180099372  pop     r14
0x180099374  pop     r13
0x180099376  pop     r12
0x180099378  pop     rdi
0x180099379  pop     rsi
0x18009937a  pop     rbp
0x18009937b  pop     rbx
0x18009937c  retn
0x18009937d  mov     rbx, [rsp+0A8h+arg_0]
0x180099385  jmp     short loc_180099340
```
