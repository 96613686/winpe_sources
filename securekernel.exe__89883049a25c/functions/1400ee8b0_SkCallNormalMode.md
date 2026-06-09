# SkCallNormalMode

- ea: `0x1400ee8b0`
- end: `0x1400eedc7`
- name: `SkCallNormalMode`
- size: `1303`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `71`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x140014dd0`
- `0x14001bcfc`
- `0x14001d0ac`
- `0x14001ed6c`
- `0x140026240`
- `0x140029308`
- `0x140035474`
- `0x140035c9c`
- `0x140036b08`
- `0x140036ea8`
- `0x140037c60`
- `0x14003acd8`
- `0x14003fb54`
- `0x14003fe40`
- `0x140040250`
- `0x1400406a4`
- `0x140043d4c`
- `0x140047ac8`
- `0x14004b838`
- `0x140050a88`
- `0x140052970`
- `0x14005585c`
- `0x140058538`
- `0x14005b9e4`
- `0x14005e098`
- `0x14005e660`
- `0x14005ef50`
- `0x140060ad4`
- `0x140060bd4`
- `0x140061170`
- `0x1400622bc`
- `0x140063578`
- `0x140063720`
- `0x1400651cc`
- `0x140065d00`
- `0x1400661e4`
- `0x140066464`
- `0x1400668b8`
- `0x140067054`
- `0x140068c2c`
- `0x14006962c`
- `0x14006a4b8`
- `0x14006a9a0`
- `0x14006bfa0`
- `0x14006da74`
- `0x14006fab4`
- `0x140070cd8`
- `0x1400710a0`
- `0x140071374`
- `0x140075a20`

## callees

- `0x140014dd0`
- `0x140020360`
- `0x140098b68`
- `0x140098c58`
- `0x140099078`
- `0x1400b7058`
- `0x1400ee8b0`
- `0x1400ef220`
- `0x1400f1860`
- `0x1400f4040`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
__int64 __fastcall SkCallNormalMode(unsigned int *a1)
{
  __int64 *v1; // rbp
  unsigned int *v2; // r15
  PEXCEPTION_ROUTINE StackBase; // rsi
  __int64 i; // rbx
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // r14
  __int64 v6; // rbx
  __m128i v7; // xmm10
  __m128i v8; // xmm11
  __m128i v9; // xmm12
  __m128i v10; // xmm13
  __m128i v11; // xmm14
  __m128i v12; // xmm15
  bool v13; // zf
  __int64 v14; // rbp
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 j; // rcx
  __int64 v21; // rdx
  _QWORD *StackLimit; // rax
  __int64 v23; // rcx
  unsigned __int16 v24; // ax
  _DWORD *v25; // rax
  __int64 v26; // rcx
  unsigned __int64 v27; // rcx
  unsigned __int64 v29; // rax
  struct _EXCEPTION_REGISTRATION_RECORD *v30; // r14
  unsigned __int64 v31; // rbx
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rcx
  struct _EXCEPTION_REGISTRATION_RECORD *v36; // r14
  struct _EXCEPTION_REGISTRATION_RECORD *v37; // rax
  __int64 result; // rax
  __int64 v39; // [rsp-8h] [rbp-70h] BYREF
  __int64 v40; // [rsp+58h] [rbp-10h] BYREF
  __int64 v41; // [rsp+60h] [rbp-8h]
  __int64 vars0; // [rsp+68h] [rbp+0h]
  __int64 vars8; // [rsp+70h] [rbp+8h]
  __int64 vars20; // [rsp+88h] [rbp+20h]

  v1 = &v40;
  KeGetCurrentIrql();
  v2 = a1;
  StackBase = (PEXCEPTION_ROUTINE)KeGetPcr()->NtTib.StackBase;
  for ( i = *((unsigned int *)StackBase + 42); ; i = *((unsigned int *)StackBase + 42) )
  {
    _disable();
    ExceptionList = KeGetPcr()->NtTib.ExceptionList;
    if ( BYTE6(ExceptionList[11].Handler) )
    {
      _fxsave(*((void **)StackBase + 14));
      _fxrstor(SkeDefaultNpxState);
      BYTE6(ExceptionList[11].Handler) = 0;
    }
    if ( (*((_DWORD *)StackBase + 43) & 0x800) != 0 && ExceptionList[4].Handler == StackBase )
    {
      *((_QWORD *)StackBase + 23) = __readmsr(0xC0000102);
      *((_QWORD *)StackBase + 22) = __readmsr(0xC0000100);
    }
    ((void (__fastcall *)(struct _EXCEPTION_REGISTRATION_RECORD *, PEXCEPTION_ROUTINE, __int64 *))SkiDeselectThread)(
      ExceptionList,
      StackBase,
      v1);
    v6 = *v2 | (unsigned __int64)(i << 32);
    v7 = _mm_loadu_si128((const __m128i *)(v2 + 2));
    v8 = _mm_loadu_si128((const __m128i *)(v2 + 6));
    v9 = _mm_loadu_si128((const __m128i *)(v2 + 10));
    v10 = _mm_loadu_si128((const __m128i *)(v2 + 14));
    v11 = _mm_loadu_si128((const __m128i *)(v2 + 18));
    v12 = _mm_loadu_si128((const __m128i *)(v2 + 22));
    v13 = *((_DWORD *)StackBase + 42) == 0;
    *((_QWORD *)StackBase + 16) = v1;
    if ( !v13 )
      ((void (__fastcall *)(PEXCEPTION_ROUTINE, __int64 *))SkiDetachThread)(StackBase, v1);
    while ( 1 )
    {
      while ( 1 )
      {
        v14 = 0;
        v15 = __readcr4();
        if ( (v15 & 0x40000) != 0 )
        {
          v16 = *(_QWORD *)&KeGetPcr()[6].PcrAlign1[2];
          if ( v16 != SkeEnabledXStateFeatures && (v16 & 3) != 0 )
            __asm { xsetbv }
        }
        v17 = 0;
        v18 = 0;
        v19 = 0;
        __writecr2(0);
        for ( j = 1; ; j = 0 )
        {
          if ( (KeGetPcr()->HalReserved[3] & 2) != 0 && (KeGetPcr()[7].PcrAlign1[16] & 0x40) != 0 )
          {
            ((void (__fastcall *)(__int64, __int64, __int64, __int64))SkiFlushBhb)(j, v17, v18, v19);
            j = (unsigned int)v41;
          }
          if ( SkiBarrierWait )
          {
            _InterlockedDecrement64(&SkiBarrierWait);
            do
            {
              v13 = SkiBarrierWait == 0;
              _mm_pause();
            }
            while ( !v13 );
            if ( (_BYTE)SkpHibernateResume )
              ((void (__fastcall *)(__int64, __int64, __int64, __int64))SkpVtl1ResumeAp)(j, v17, v18, v19);
          }
          v41 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))ShvlpVtlReturn)(j, v17, v18, v19);
          vars0 = v14;
          vars8 = v21;
          StackLimit = KeGetPcr()->NtTib.StackLimit;
          StackLimit[2] = v23;
          StackLimit[1] = v41;
          __writegsbyte(0xCCu, KeGetPcr()->HalReserved[3] & 0xF9);
          if ( (KeGetPcr()[7].PcrAlign1[16] & 1) != 0 )
          {
            v24 = HIWORD(KeGetPcr()[7].PcrAlign1[16]);
            if ( LOWORD(KeGetPcr()[7].PcrAlign1[18]) != v24 )
            {
              __writegsword(0xBA8u, v24);
              __writemsr(0x48u, v24);
            }
            if ( (KeGetPcr()[7].PcrAlign1[16] & 4) != 0 )
              __writemsr(0x49u, 1u);
          }
          _mm_lfence();
          v25 = KeGetPcr()->NtTib.StackLimit;
          v17 = vars8;
          v26 = (unsigned int)(*v25 - 1);
          if ( *v25 == 1 )
            break;
          __readcr2();
          v27 = __readdr(6u);
          _enable();
          if ( _bittestandreset(MK_FP(__GS__, 204), 3u) )
            v29 = ((__int64 (__fastcall *)(unsigned __int64, __int64))SkiDeliverIntercept)(v27, v17);
          _disable();
          __writedr(6u, v27);
          __writecr2(v29);
          v14 = vars0;
        }
        _mm_setcsr(SkiInitialMxCsr);
        v30 = KeGetPcr()->NtTib.ExceptionList;
        HIDWORD(v30[158].Handler) = v19;
        v31 = v6 & 0xFFFFFFFFFFFFFF7FuLL;
        if ( (_BYTE)v31 != 3 )
          break;
        LOBYTE(v26) = -1;
        SkeFlushEntireTb(v26, 0);
        v6 = 256;
      }
      v32 = __readcr4();
      if ( (v32 & 0x40000) != 0 )
      {
        __asm { xgetbv }
        v33 = v32 | (v17 << 32);
        if ( !*(_QWORD *)&KeGetPcr()[6].PcrAlign1[2] )
          __writegsqword(0x9F0u, v33);
        if ( v33 != SkeEnabledXStateFeatures )
        {
          __writegsqword(0x9F0u, v33);
          __asm { xsetbv }
        }
      }
      vars20 = v7.m128i_i64[1];
      v34 = SkiSelectThread(HIDWORD(v31), v31, v18, 0, v7.m128i_i64[0]);
      if ( (int)v34 >= 0 )
        break;
      v7 = (__m128i)(unsigned __int64)v34;
      v8 = 0;
      v9 = 0;
      v10 = 0;
      v11 = 0;
      v12 = 0;
      v6 = 256;
    }
    StackBase = v30->Handler;
    v1 = (__int64 *)*((_QWORD *)StackBase + 16);
    if ( _bittest64(v1 + 26, 9u) )
      _enable();
    v2 = (unsigned int *)v1[36];
    if ( (_BYTE)v31 )
      v2 = (unsigned int *)&v39;
    if ( v2 )
    {
      *(_QWORD *)v2 = v31;
      *(__m128i *)(v2 + 2) = v7;
      *(__m128i *)(v2 + 6) = v8;
      *(__m128i *)(v2 + 10) = v9;
      *(__m128i *)(v2 + 14) = v10;
      *(__m128i *)(v2 + 18) = v11;
      *(__m128i *)(v2 + 22) = v12;
    }
    if ( !(_BYTE)v31 )
      break;
    _enable();
    if ( IumInvokeSecureService((__int64)v2, (__int64)v1) )
      break;
  }
  _disable();
  v36 = KeGetPcr()->NtTib.ExceptionList;
  v37 = (struct _EXCEPTION_REGISTRATION_RECORD *)*((_QWORD *)StackBase + 14);
  if ( v36[4].Handler != StackBase )
  {
    if ( !SkiKvaShadow )
      *(struct _EXCEPTION_REGISTRATION_RECORD **)((char *)&v36[2].Next->Next + 4) = v37;
    v36[4].Handler = StackBase;
    v36[263].Next = v37;
    if ( (__GS__ & (unsigned __int16)(__ES__ & __DS__)) != 43 )
    {
      __DS__ = 43;
      __asm { swapgs }
      __asm { swapgs }
    }
    __writemsr(0xC0000100, *((_QWORD *)StackBase + 22));
    v35 = 3221225730LL;
    __writemsr(0xC0000102, *((_QWORD *)StackBase + 23));
  }
  result = ((__int64 (__fastcall *)(__int64))SkpSyncUserSharedData)(v35);
  if ( _bittest64(v1 + 26, 9u) )
    _enable();
  return result;
}

```

## disassembly

```asm
0x1400ee8b0  push    r15
0x1400ee8b2  push    r14
0x1400ee8b4  push    r13
0x1400ee8b6  push    r12
0x1400ee8b8  push    rbx
0x1400ee8b9  push    rsi
0x1400ee8ba  push    rdi
0x1400ee8bb  push    rbp
0x1400ee8bc  pushfq
0x1400ee8bd  sub     rsp, 0D0h
0x1400ee8c4  movaps  [rsp+8+var_s28], xmm6
0x1400ee8c9  movaps  [rsp+8+var_s38], xmm7
0x1400ee8ce  movaps  [rsp+8+var_s48], xmm8
0x1400ee8d4  movaps  [rsp+8+var_s58], xmm9
0x1400ee8da  movaps  [rsp+8+var_s68], xmm10
0x1400ee8e0  movaps  [rsp+8+var_s78], xmm11
0x1400ee8e9  movaps  [rsp+8+var_s88], xmm12
0x1400ee8f2  movaps  [rsp+8+var_s98], xmm13
0x1400ee8fb  movaps  [rsp+8+var_sA8], xmm14
0x1400ee904  movaps  [rsp+8+var_sB8], xmm15
0x1400ee90d  mov     rbp, rsp
0x1400ee910  mov     r8, cr8
0x1400ee914  and     [rbp+arg_10], 0
0x1400ee91c  mov     [rbp+arg_12], r8b
0x1400ee923  xor     edi, edi
0x1400ee925  xor     r12, r12
0x1400ee928  xor     r13, r13
0x1400ee92b  xorps   xmm6, xmm6
0x1400ee92e  xorps   xmm7, xmm7
0x1400ee931  xorps   xmm8, xmm8
0x1400ee935  xorps   xmm9, xmm9
0x1400ee939  mov     [rbp+arg_8], rcx
0x1400ee940  mov     r15, rcx
0x1400ee943  mov     rsi, gs:8
0x1400ee94c  cmp     byte ptr [r15+1], 5
0x1400ee951  mov     ebx, [rsi+0A8h]
0x1400ee957  jnz     short SkpPrepareForNormalCall
0x1400ee959  or      byte ptr [rbp+arg_10+1], 1
0x1400ee960  cli
0x1400ee961  mov     r14, gs:0
0x1400ee96a  cmp     byte ptr [r14+0BEh], 0
0x1400ee972  jz      short loc_1400EE98D
0x1400ee974  mov     rcx, [rsi+70h]
0x1400ee978  lea     rax, SkeDefaultNpxState
0x1400ee97f  fxsave  dword ptr [rcx]
0x1400ee982  fxrstor dword ptr [rax]
0x1400ee985  and     byte ptr [r14+0BEh], 0
0x1400ee98d  test    dword ptr [rsi+0ACh], 800h
0x1400ee997  jz      short loc_1400EE9C5
0x1400ee999  cmp     [r14+48h], rsi
0x1400ee99d  jnz     short loc_1400EE9C5
0x1400ee99f  mov     ecx, 0C0000102h
0x1400ee9a4  rdmsr
0x1400ee9a6  mov     [rsi+0B8h], eax
0x1400ee9ac  mov     [rsi+0BCh], edx
0x1400ee9b2  mov     ecx, 0C0000100h
0x1400ee9b7  rdmsr
0x1400ee9b9  mov     [rsi+0B0h], eax
0x1400ee9bf  mov     [rsi+0B4h], edx
0x1400ee9c5  mov     r8, rbp
0x1400ee9c8  mov     rdx, rsi
0x1400ee9cb  mov     rcx, r14
0x1400ee9ce  call    SkiDeselectThread
0x1400ee9d3  mov     eax, [r15]
0x1400ee9d6  shl     rbx, 20h
0x1400ee9da  or      rbx, rax
0x1400ee9dd  movdqu  xmm10, xmmword ptr [r15+8]
0x1400ee9e3  movdqu  xmm11, xmmword ptr [r15+18h]
0x1400ee9e9  movdqu  xmm12, xmmword ptr [r15+28h]
0x1400ee9ef  movdqu  xmm13, xmmword ptr [r15+38h]
0x1400ee9f5  movdqu  xmm14, xmmword ptr [r15+48h]
0x1400ee9fb  movdqu  xmm15, xmmword ptr [r15+58h]
0x1400eea01  mov     rsp, rbp
0x1400eea04  cmp     dword ptr [rsi+0A8h], 0
0x1400eea0b  mov     [rsi+80h], rbp
0x1400eea12  jz      short loc_1400EEA26
0x1400eea14  mov     rdx, rbp
0x1400eea17  mov     rsp, [r14+30h]
0x1400eea1b  mov     rbp, rsp
0x1400eea1e  mov     rcx, rsi
0x1400eea21  call    SkiDetachThread
0x1400eea26  xor     esi, esi
0x1400eea28  xor     r15, r15
0x1400eea2b  xor     r14, r14
0x1400eea2e  xor     ebp, ebp
0x1400eea30  mov     rax, cr4
0x1400eea33  test    rax, 40000h
0x1400eea39  jz      short loc_1400EEA64
0x1400eea3b  mov     rax, cs:SkeEnabledXStateFeatures
0x1400eea42  mov     rdx, gs:9F0h
0x1400eea4b  cmp     rdx, rax
0x1400eea4e  jz      short loc_1400EEA64
0x1400eea50  mov     rax, rdx
0x1400eea53  and     eax, 3
0x1400eea56  jz      short loc_1400EEA64
0x1400eea58  mov     rax, rdx
0x1400eea5b  shr     rdx, 20h
0x1400eea5f  xor     ecx, ecx
0x1400eea61  xsetbv
0x1400eea64  xor     edx, edx
0x1400eea66  xor     r8, r8
0x1400eea69  xor     r9, r9
0x1400eea6c  xor     r10, r10
0x1400eea6f  xor     r11, r11
0x1400eea72  xorps   xmm0, xmm0
0x1400eea75  xorps   xmm1, xmm1
0x1400eea78  xorps   xmm2, xmm2
0x1400eea7b  xorps   xmm3, xmm3
0x1400eea7e  xorps   xmm4, xmm4
0x1400eea81  xorps   xmm5, xmm5
0x1400eea84  mov     cr2, rdx
0x1400eea87  mov     ecx, 1
0x1400eea8c  mov     al, gs:0CCh
0x1400eea94  test    al, 2
0x1400eea96  jz      short loc_1400EEAAF
0x1400eea98  mov     al, gs:0BA0h
0x1400eeaa0  test    al, 40h
0x1400eeaa2  jz      short loc_1400EEAAF
0x1400eeaa4  mov     dword ptr [rsp+var_s0], ecx
0x1400eeaa7  call    SkiFlushBhb
0x1400eeaac  mov     ecx, dword ptr [rsp+var_s0]
0x1400eeaaf  cmp     cs:SkiBarrierWait, 0
0x1400eeab7  jz      short loc_1400EEADB
0x1400eeab9  lock dec cs:SkiBarrierWait
0x1400eeac1  cmp     cs:SkiBarrierWait, 0
0x1400eeac9  pause
0x1400eeacb  jnz     short loc_1400EEAC1
0x1400eeacd  cmp     byte ptr cs:SkpHibernateResume, 0
0x1400eead4  jz      short loc_1400EEADB
0x1400eead6  call    SkpVtl1ResumeAp
0x1400eeadb  mov     rax, cs:ShvlpVtlReturn
0x1400eeae2  call    rax ; ShvlpVtlReturn
0x1400eeae4  mov     [rsp+var_s0], rax
0x1400eeae8  mov     [rsp+var_s8], rbp
0x1400eeaed  mov     [rsp+var_s10], rdx
0x1400eeaf2  mov     rax, gs:10h
0x1400eeafb  mov     rbp, rsp
0x1400eeafe  mov     [rax+10h], rcx
0x1400eeb02  mov     rcx, [rsp+var_s0]
0x1400eeb06  mov     [rax+8], rcx
0x1400eeb0a  and     byte ptr gs:0CCh, 0F9h
0x1400eeb13  test    byte ptr gs:0BA0h, 1
0x1400eeb1c  jz      short loc_1400EEB63
0x1400eeb1e  movzx   eax, word ptr gs:0BA2h
0x1400eeb27  cmp     gs:0BA8h, ax
0x1400eeb30  jz      short loc_1400EEB44
0x1400eeb32  mov     gs:0BA8h, ax
0x1400eeb3b  mov     ecx, 48h ; 'H'
0x1400eeb40  xor     edx, edx
0x1400eeb42  wrmsr
0x1400eeb44  movzx   edx, byte ptr gs:0BA0h
0x1400eeb4d  test    edx, 4
0x1400eeb53  jz      short loc_1400EEB63
0x1400eeb55  mov     eax, 1
0x1400eeb5a  xor     edx, edx
0x1400eeb5c  mov     ecx, 49h ; 'I'
0x1400eeb61  wrmsr
0x1400eeb63  lfence
0x1400eeb66  mov     rax, gs:10h
0x1400eeb6f  mov     rdx, [rsp+var_s10]
0x1400eeb74  mov     ecx, [rax]
0x1400eeb76  dec     ecx
0x1400eeb78  jz      short loc_1400EEBA6
0x1400eeb7a  mov     rax, cr2
0x1400eeb7d  mov     rcx, dr6
0x1400eeb80  sti
0x1400eeb81  nop
0x1400eeb82  btr     dword ptr gs:0CCh, 3
0x1400eeb8c  jnb     short loc_1400EEB93
0x1400eeb8e  call    SkiDeliverIntercept
0x1400eeb93  cli
0x1400eeb94  mov     dr6, rcx
0x1400eeb97  mov     cr2, rax
0x1400eeb9a  mov     rbp, [rsp+var_s8]
0x1400eeb9f  xor     ecx, ecx
0x1400eeba1  jmp     loc_1400EEA8C
0x1400eeba6  ldmxcsr cs:SkiInitialMxCsr
0x1400eebad  mov     r14, gs:0
0x1400eebb6  mov     [r14+9ECh], r9d
0x1400eebbd  btr     rbx, 7
0x1400eebc2  cmp     bl, 3
0x1400eebc5  jnz     short loc_1400EEBDA
0x1400eebc7  mov     cl, 0FFh
0x1400eebc9  xor     edx, edx
0x1400eebcb  call    SkeFlushEntireTb
0x1400eebd0  mov     ebx, 100h
0x1400eebd5  jmp     loc_1400EEA2B
0x1400eebda  mov     rax, cr4
0x1400eebdd  test    rax, 40000h
0x1400eebe3  jz      short loc_1400EEC29
0x1400eebe5  xor     ecx, ecx
0x1400eebe7  xgetbv
0x1400eebea  shl     rdx, 20h
0x1400eebee  or      rdx, rax
0x1400eebf1  mov     rax, gs:9F0h
0x1400eebfa  test    rax, rax
0x1400eebfd  jnz     short loc_1400EEC08
0x1400eebff  mov     gs:9F0h, rdx
0x1400eec08  mov     rax, cs:SkeEnabledXStateFeatures
0x1400eec0f  cmp     rdx, rax
0x1400eec12  jz      short loc_1400EEC29
0x1400eec14  mov     gs:9F0h, rdx
0x1400eec1d  mov     rdx, rax
0x1400eec20  shr     rdx, 20h
0x1400eec24  xor     ecx, ecx
0x1400eec26  xsetbv
0x1400eec29  movaps  xmmword ptr [rsp+20h], xmm10
0x1400eec2f  mov     rcx, rbx
0x1400eec32  mov     edx, ebx
0x1400eec34  shr     rcx, 20h
0x1400eec38  mov     r9, rdi
0x1400eec3b  call    SkiSelectThread
0x1400eec40  test    eax, eax
0x1400eec42  jns     short loc_1400EEC67
0x1400eec44  movq    xmm10, rax
0x1400eec49  xorps   xmm11, xmm11
0x1400eec4d  xorps   xmm12, xmm12
0x1400eec51  xorps   xmm13, xmm13
0x1400eec55  xorps   xmm14, xmm14
0x1400eec59  xorps   xmm15, xmm15
0x1400eec5d  mov     ebx, 100h
0x1400eec62  jmp     loc_1400EEA2B
0x1400eec67  mov     rsi, [r14+8]
0x1400eec6b  mov     rbp, [rsi+80h]
0x1400eec72  mov     rsp, rbp
0x1400eec75  bt      [rbp+var_sD0], 9
0x1400eec7e  jnb     short loc_1400EEC81
0x1400eec80  sti
0x1400eec81  mov     r15, [rbp+arg_8]
0x1400eec88  cmp     bl, 0
0x1400eec8b  jz      short loc_1400EEC99
0x1400eec8d  sub     rsp, 90h
0x1400eec94  lea     r15, [rsp+90h+var_68]
0x1400eec99  test    r15, r15
0x1400eec9c  jz      short loc_1400EECC5
0x1400eec9e  mov     [r15], rbx
0x1400eeca1  movdqu  xmmword ptr [r15+8], xmm10
0x1400eeca7  movdqu  xmmword ptr [r15+18h], xmm11
0x1400eecad  movdqu  xmmword ptr [r15+28h], xmm12
0x1400eecb3  movdqu  xmmword ptr [r15+38h], xmm13
0x1400eecb9  movdqu  xmmword ptr [r15+48h], xmm14
0x1400eecbf  movdqu  xmmword ptr [r15+58h], xmm15
0x1400eecc5  cmp     bl, 0
0x1400eecc8  jz      short loc_1400EECE5
0x1400eecca  mov     rcx, r15
0x1400eeccd  mov     rdx, rbp
0x1400eecd0  sti
0x1400eecd1  call    IumInvokeSecureService
0x1400eecd6  test    al, al
0x1400eecd8  jnz     short loc_1400EECE5
0x1400eecda  mov     ebx, [rsi+0A8h]
0x1400eece0  jmp     SkpPrepareForNormalCall
0x1400eece5  cli
0x1400eece6  mov     r14, gs:0
0x1400eecef  cmp     [r14+48h], rsi
0x1400eecf3  mov     rax, [rsi+70h]
0x1400eecf7  jz      short loc_1400EED63
0x1400eecf9  cmp     cs:SkiKvaShadow, 0
0x1400eed00  jnz     short loc_1400EED0A
0x1400eed02  mov     rdx, [r14+20h]
0x1400eed06  mov     [rdx+4], rax
0x1400eed0a  mov     [r14+48h], rsi
0x1400eed0e  mov     [r14+1070h], rax
0x1400eed15  mov     eax, ds
0x1400eed17  mov     edx, es
0x1400eed19  and     eax, edx
0x1400eed1b  mov     edx, gs
0x1400eed1d  and     eax, edx
0x1400eed1f  cmp     ax, 2Bh ; '+'
0x1400eed23  jz      short loc_1400EED36
0x1400eed25  mov     edx, 2Bh ; '+'
0x1400eed2a  mov     ds, edx
0x1400eed2c  mov     es, edx
0x1400eed2e  swapgs
0x1400eed31  mov     gs, edx
0x1400eed33  swapgs
0x1400eed36  mov     eax, 53h ; 'S'
0x1400eed3b  mov     fs, eax
0x1400eed3d  mov     eax, [rsi+0B0h]
0x1400eed43  mov     edx, [rsi+0B4h]
0x1400eed49  mov     ecx, 0C0000100h
0x1400eed4e  wrmsr
0x1400eed50  mov     eax, [rsi+0B8h]
0x1400eed56  mov     edx, [rsi+0BCh]
0x1400eed5c  mov     ecx, 0C0000102h
0x1400eed61  wrmsr
0x1400eed63  call    SkpSyncUserSharedData
0x1400eed68  bt      [rbp+var_sD0], 9
0x1400eed71  jnb     short loc_1400EED74
0x1400eed73  sti
0x1400eed74  movaps  xmm6, [rbp+var_s28+8]
0x1400eed78  movaps  xmm7, [rbp+var_s38+8]
0x1400eed7c  movaps  xmm8, [rbp+var_s48+8]
0x1400eed81  movaps  xmm9, [rbp+var_s58+8]
0x1400eed86  movaps  xmm10, [rbp+var_s68+8]
0x1400eed8b  movaps  xmm11, [rbp+var_s78+8]
0x1400eed93  movaps  xmm12, [rbp+var_s88+8]
0x1400eed9b  movaps  xmm13, [rbp+var_s98+8]
0x1400eeda3  movaps  xmm14, [rbp+var_sA8+8]
0x1400eedab  movaps  xmm15, [rbp+var_sB8+8]
  ... truncated ...
```
