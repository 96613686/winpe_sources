# GrepCreateCompatibleBitmap(OPTAPIDCOBJ &,int,int,ulong,_LUID *,ushort *)

- ea: `0x140093684`
- end: `0x140093ced`
- name: `?GrepCreateCompatibleBitmap@@YAPEAUHBITMAP__@@AEAVOPTAPIDCOBJ@@HHKPEAU_LUID@@PEAG@Z`
- size: `1641`
- prototype: `HBITMAP __usercall@<rax>(struct OPTAPIDCOBJ *this@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, struct _LUID *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140093450`
- `0x1400935a0`
- `0x140167e30`
- `0x1401f96f8`

## callees

- `0x14005fb0c`
- `0x140062148`
- `0x1400661bc`
- `0x14007eef8`
- `0x140080590`
- `0x140093684`
- `0x140093cf4`
- `0x14009510c`
- `0x14009519c`
- `0x1400954f4`
- `0x1401df150`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140093c99`
- `ntoskrnl!DbgPrint` at `0x140093c99`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400937c8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400937f5`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14009397a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400937c8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400937f5`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14009397a`
- `win32kbase!PopThreadGuardedObject` at `0x14009399d`
- `win32kbase!PopThreadGuardedObject` at `0x14009399d`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14009398d`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14009398d`
- `win32kbase!PushThreadGuardedObject` at `0x140093770`
- `win32kbase!PushThreadGuardedObject` at `0x140093796`
- `win32kbase!PushThreadGuardedObject` at `0x140093770`
- `win32kbase!PushThreadGuardedObject` at `0x140093796`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400939e2`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400939e2`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400939cd`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400939cd`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x1400937e4`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x1400937e4`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400939b6`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400939b6`
- `win32kbase!HmgSetOwner` at `0x140093961`
- `win32kbase!HmgSetOwner` at `0x140093961`
- `win32kbase!EngSetLastError` at `0x140093b19`
- `win32kbase!EngSetLastError` at `0x140093b19`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAXAEAVXDCOBJ@@@Z` at `0x140093824`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAXAEAVXDCOBJ@@@Z` at `0x140093824`
- `win32kbase!GreGetScaledLogPixels` at `0x140093baf`
- `win32kbase!GreGetScaledLogPixels` at `0x140093baf`
- `win32kbase!GreCreateBitmap` at `0x140093b54`
- `win32kbase!GreCreateBitmap` at `0x140093b54`

## string_xrefs

- `0x140093c92`: `GreCreateCompatibleBitmap: got CCB_KMSECTIONVIEW without CCB_NOVIDEOMEMORY...ignoring CCB_KMSECTIONVIEW\n`

## pseudocode

```c
__int64 __fastcall GrepCreateCompatibleBitmap(
        struct OPTAPIDCOBJ *this,
        int a2,
        int a3,
        unsigned int a4,
        struct _LUID *a5,
        unsigned __int16 *a6)
{
  __int64 v6; // r14
  __int64 v8; // rdi
  __int64 v9; // rsi
  int v11; // r13d
  int v12; // r12d
  BOOL v13; // eax
  int v14; // r15d
  Gre::Base *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rbx
  Gre::Base *v18; // rcx
  struct Gre::Base::SESSION_GLOBALS *v19; // rax
  __int64 v20; // r14
  __int64 v21; // r10
  __int64 v22; // r13
  int v23; // r14d
  __int64 *v24; // rax
  float v25; // xmm6_4
  float v26; // xmm8_4
  int v27; // eax
  Gre::Base *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rbx
  struct Gre::Base::SESSION_GLOBALS *v32; // rax
  __m128i v34; // xmm0
  int v35; // r9d
  __m128i v36; // xmm1
  unsigned int v37; // r8d
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // r8d
  unsigned int v41; // ecx
  __int64 v42; // rax
  __int64 v43; // rax
  struct _LUID *v44; // rcx
  unsigned __int16 ScaledLogPixels; // ax
  struct SURFACE *v46; // rax
  int v47; // r8d
  __int64 *v48; // rax
  unsigned int v49; // [rsp+88h] [rbp-80h]
  int v50; // [rsp+8Ch] [rbp-7Ch]
  int v51; // [rsp+90h] [rbp-78h]
  _BYTE v52[32]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-50h]
  __int64 v54; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v55[8]; // [rsp+C8h] [rbp-40h] BYREF
  HSEMAPHORE v56; // [rsp+D0h] [rbp-38h]
  __int64 v57; // [rsp+D8h] [rbp-30h] BYREF
  int v58; // [rsp+E0h] [rbp-28h]
  __int64 v59; // [rsp+E8h] [rbp-20h]
  __int64 v60; // [rsp+F0h] [rbp-18h]
  _OWORD v61[2]; // [rsp+F8h] [rbp-10h] BYREF
  _OWORD v62[2]; // [rsp+118h] [rbp+10h] BYREF
  char v63; // [rsp+138h] [rbp+30h]
  _BYTE v64[224]; // [rsp+148h] [rbp+40h] BYREF
  int v65; // [rsp+278h] [rbp+170h]
  int v66; // [rsp+280h] [rbp+178h]

  v6 = 0;
  v8 = a3;
  v9 = a2;
  v66 = 0;
  v11 = 0;
  v49 = (a4 & 0x1000000) == 0;
  if ( (a4 & 0x2000000) != 0 )
  {
    if ( (a4 & 0x1000000) != 0 )
    {
      v11 = 1;
      v66 = 1;
    }
    else
    {
      DbgPrint("GreCreateCompatibleBitmap: got CCB_KMSECTIONVIEW without CCB_NOVIDEOMEMORY...ignoring CCB_KMSECTIONVIEW\n");
    }
  }
  v12 = a4 & 0x4000000;
  v13 = (a4 & 0x4000000) != 0;
  v14 = (a4 >> 27) & 1;
  v65 = v13;
  if ( (int)v9 <= 0 || (int)v8 <= 0 || (unsigned __int64)(v8 * v9) > 0x3FFFFFFF )
  {
    EngSetLastError(0x57u);
    return 0;
  }
  if ( *((_QWORD *)this + 12) )
  {
    if ( OPTAPIDCOBJ::bValid(this) )
    {
      v59 = *((_QWORD *)this + 2);
      v60 = 0;
      v57 = 0;
      memset(v61, 0, sizeof(v61));
      v58 = 0;
      PushThreadGuardedObject(
        v61,
        &v57,
        UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
      memset(v62, 0, sizeof(v62));
      PushThreadGuardedObject(
        v62,
        &v57,
        UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
      v16 = *(_QWORD *)this;
      v63 = 0;
      v57 = v16;
      v17 = *(_QWORD *)(v16 + 48);
      v54 = v17;
      if ( (*(_DWORD *)(v17 + 40) & 0x8000) != 0 )
      {
        v46 = XDCOBJ::pSurfaceEff((XDCOBJ *)&v57);
        if ( *(_DWORD *)(v57 + 32) == 1 )
        {
          v47 = *((_DWORD *)v46 + 24);
          v31 = 0;
          v48 = (__int64 *)*((_QWORD *)v46 + 22);
          if ( v48 )
            v6 = *v48;
        }
        else
        {
          v47 = *(_DWORD *)(v17 + 2092);
          if ( (*(_DWORD *)(v17 + 2156) & 0x100) == 0 )
            v6 = **(_QWORD **)(v17 + 1792);
          v31 = 0;
        }
        CreateCompatibleSurface(
          (__int64)v52,
          *(_QWORD *)(v57 + 48),
          v47,
          v6,
          v9,
          v8,
          v49,
          v11,
          v65,
          0,
          0,
          0,
          v14,
          0,
          0,
          0);
        if ( v53 )
        {
          SURFREF::vSetPID((SURFREF *)v52, 0x80000002);
          v31 = *(_QWORD *)(v53 + 32);
        }
        SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v52);
        goto LABEL_26;
      }
      v50 = v9;
      v51 = v8;
      v56 = (HSEMAPHORE)(*(_QWORD *)Gre::Base::Globals(v15) + 624LL);
      GreAcquireSemaphoreSharedInternal(v56);
      GrepAcquireLockValidate<1>();
      v19 = Gre::Base::Globals(v18);
      v20 = *(_QWORD *)(v57 + 496);
      if ( v20 )
      {
        if ( v60 )
          v20 = v60;
      }
      else
      {
        v20 = *((_QWORD *)v19 + 547);
      }
      NEEDGRELOCK::vLock((NEEDGRELOCK *)v55, (struct XDCOBJ *)&v57);
      DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v64, (struct PDEVOBJ *)&v54);
      v21 = v57;
      v22 = 0;
      if ( *(_DWORD *)(v57 + 32) == 1 )
      {
        v24 = *(__int64 **)(v20 + 176);
        v23 = *(_DWORD *)(v20 + 96);
        if ( !v24 )
        {
LABEL_14:
          v25 = 0.0;
          v26 = 0.0;
          if ( a6 )
          {
            if ( *a6 != 96 )
            {
              ScaledLogPixels = GreGetScaledLogPixels();
              v21 = v57;
              v25 = (float)ScaledLogPixels / 96.0;
              v26 = v25;
              goto LABEL_31;
            }
          }
          else
          {
            v27 = *(_DWORD *)(v57 + 520);
            if ( (v27 & 1) != 0 && (v27 & 2) == 0 )
            {
              v25 = *(float *)(v57 + 524);
              v26 = *(float *)(v57 + 528);
LABEL_31:
              if ( v25 != 0.0 )
                goto LABEL_32;
            }
          }
          if ( v26 == 0.0 )
          {
LABEL_17:
            if ( v12 )
            {
              if ( (*(_DWORD *)(v17 + 40) & 0x4000000) != 0 )
              {
                if ( a5 )
                {
                  v44 = *(struct _LUID **)(v17 + 1784);
                  if ( v44 )
                  {
                    v44[13] = *a5;
                    v21 = v57;
                  }
                }
              }
            }
            CreateCompatibleSurface(
              (__int64)v52,
              *(_QWORD *)(v21 + 48),
              v23,
              v22,
              v9,
              v8,
              v49,
              v66,
              v65,
              0,
              0,
              0,
              v14,
              0,
              0,
              0);
            v30 = v53;
            if ( v53 )
            {
              if ( v25 != 0.0 || v26 != 0.0 )
              {
                *(_DWORD *)(v53 + 164) |= 0x800u;
                *(_DWORD *)(v30 + 716) = v50;
                *(_DWORD *)(v30 + 720) = v51;
                *(float *)(v30 + 708) = v25;
                *(float *)(v30 + 712) = v26;
                v30 = v53;
              }
              LOBYTE(v29) = 5;
              HmgSetOwner(*(_QWORD *)(v30 + 32), 2147483650LL, v29);
              v30 = v53;
              v31 = *(_QWORD *)(v53 + 32);
            }
            else
            {
              v31 = 0;
            }
            if ( v30 )
            {
              v32 = Gre::Base::Globals(v28);
              DEC_SHARE_REF_CNT(v32, v53);
            }
            PopThreadGuardedObject(v52);
            DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v64);
            NEEDGRELOCK::vUnlock((NEEDGRELOCK *)v55);
            EtwTraceGreLockReleaseSemaphore(L"DynamicModeChange", v56);
            GrepReleaseLockValidate<1>();
            GreReleaseSemaphoreSharedInternal(v56);
LABEL_26:
            APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v57);
            return v31;
          }
LABEL_32:
          v34 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v9);
          *(float *)v34.m128i_i32 = *(float *)v34.m128i_i32 * v25;
          v36 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v8);
          v35 = _mm_cvtsi128_si32(v34);
          *(float *)v36.m128i_i32 = *(float *)v36.m128i_i32 * v26;
          v37 = (unsigned __int8)(v35 >> 23);
          if ( v37 <= 0x9E )
          {
            v38 = v35 & 0x7FFFFF | 0x800000LL;
            v39 = v37 < 0x76 ? v38 >> (118 - (unsigned __int8)v37) : v38 << ((unsigned __int8)v37 - 118);
            v9 = (v39 + 0x80000000LL) >> 32;
            if ( v35 < 0 )
              LODWORD(v9) = -(int)v9;
          }
          v40 = _mm_cvtsi128_si32(v36);
          v41 = (unsigned __int8)(v40 >> 23);
          if ( v41 <= 0x9E )
          {
            v42 = v40 & 0x7FFFFF | 0x800000LL;
            v43 = v41 < 0x76 ? v42 >> (118 - (unsigned __int8)v41) : v42 << ((unsigned __int8)v41 - 118);
            v8 = (v43 + 0x80000000LL) >> 32;
            if ( v40 < 0 )
              LODWORD(v8) = -(int)v8;
          }
          goto LABEL_17;
        }
      }
      else
      {
        v23 = *(_DWORD *)(v17 + 2092);
        if ( (*(_DWORD *)(v17 + 2156) & 0x100) != 0 )
          goto LABEL_14;
        v24 = *(__int64 **)(v17 + 1792);
      }
      v22 = *v24;
      goto LABEL_14;
    }
    return 0;
  }
  return GreCreateBitmap((unsigned int)v9, (unsigned int)v8, 1, 1, 0);
}

```

## disassembly

```asm
0x140093684  mov     rax, rsp
0x140093687  mov     [rax+8], rbx
0x14009368b  push    rbp
0x14009368c  push    rsi
0x14009368d  push    rdi
0x14009368e  push    r12
0x140093690  push    r13
0x140093692  push    r14
0x140093694  push    r15
0x140093696  lea     rbp, [rax-158h]
0x14009369d  sub     rsp, 220h
0x1400936a4  xor     r14d, r14d
0x1400936a7  movaps  xmmword ptr [rax-48h], xmm6
0x1400936ab  movaps  xmmword ptr [rax-58h], xmm7
0x1400936af  mov     rbx, rcx
0x1400936b2  movaps  xmmword ptr [rax-68h], xmm8
0x1400936b7  mov     ecx, r14d
0x1400936ba  mov     eax, r9d
0x1400936bd  movsxd  rdi, r8d
0x1400936c0  and     eax, 1000000h
0x1400936c5  movsxd  rsi, edx
0x1400936c8  mov     r15d, r9d
0x1400936cb  mov     [rbp+150h+arg_18], r14d
0x1400936d2  setz    cl
0x1400936d5  mov     r13d, r14d
0x1400936d8  mov     [rbp+150h+var_1D0], ecx
0x1400936db  bt      r9d, 19h
0x1400936e0  jb      loc_140093C7C
0x1400936e6  mov     r12d, r15d
0x1400936e9  mov     eax, r14d
0x1400936ec  and     r12d, 4000000h
0x1400936f3  setnz   al
0x1400936f6  shr     r15d, 1Bh
0x1400936fa  and     r15d, 1
0x1400936fe  mov     [rbp+150h+arg_10], eax
0x140093704  test    esi, esi
0x140093706  jle     loc_140093B14
0x14009370c  test    edi, edi
0x14009370e  jle     loc_140093B14
0x140093714  mov     rcx, rsi
0x140093717  imul    rcx, rdi
0x14009371b  cmp     rcx, 3FFFFFFFh
0x140093722  ja      loc_140093B14
0x140093728  cmp     [rbx+60h], r14
0x14009372c  jz      loc_140093B42
0x140093732  mov     rcx, rbx; this
0x140093735  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x14009373a  test    al, al
0x14009373c  jz      loc_140093B25
0x140093742  mov     rax, [rbx+10h]
0x140093746  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14009374d  xorps   xmm0, xmm0
0x140093750  mov     [rbp+150h+var_170], rax
0x140093754  lea     rdx, [rbp+150h+var_180]
0x140093758  mov     [rbp+150h+var_168], r14
0x14009375c  lea     rcx, [rbp+150h+var_160]
0x140093760  mov     [rbp+150h+var_180], r14
0x140093764  movups  [rbp+150h+var_160], xmm0
0x140093768  mov     [rbp+150h+var_178], r14d
0x14009376c  movups  [rbp+150h+var_150], xmm0
0x140093770  call    cs:__imp_PushThreadGuardedObject
0x140093777  nop     dword ptr [rax+rax+00h]
0x14009377c  xorps   xmm0, xmm0
0x14009377f  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140093786  lea     rdx, [rbp+150h+var_180]
0x14009378a  lea     rcx, [rbp+150h+var_140]
0x14009378e  movups  [rbp+150h+var_140], xmm0
0x140093792  movups  [rbp+150h+var_130], xmm0
0x140093796  call    cs:__imp_PushThreadGuardedObject
0x14009379d  nop     dword ptr [rax+rax+00h]
0x1400937a2  mov     rbx, [rbx]
0x1400937a5  mov     [rbp+150h+var_120], r14b
0x1400937a9  mov     [rbp+150h+var_180], rbx
0x1400937ad  mov     rbx, [rbx+30h]
0x1400937b1  mov     [rbp+150h+var_198], rbx
0x1400937b5  test    dword ptr [rbx+28h], 8000h
0x1400937bc  jnz     loc_140093BDD
0x1400937c2  mov     [rbp+150h+var_1CC], esi
0x1400937c5  mov     [rbp+150h+var_1C8], edi
0x1400937c8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400937cf  nop     dword ptr [rax+rax+00h]
0x1400937d4  mov     rax, [rax]
0x1400937d7  add     rax, 270h
0x1400937dd  mov     rcx, rax
0x1400937e0  mov     [rbp+150h+var_188], rax
0x1400937e4  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400937eb  nop     dword ptr [rax+rax+00h]
0x1400937f0  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x1400937f5  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400937fc  nop     dword ptr [rax+rax+00h]
0x140093801  mov     rcx, [rbp+150h+var_180]
0x140093805  mov     r14, [rcx+1F0h]
0x14009380c  test    r14, r14
0x14009380f  jnz     loc_140093A25
0x140093815  mov     r14, [rax+1118h]
0x14009381c  lea     rdx, [rbp+150h+var_180]
0x140093820  lea     rcx, [rbp+150h+var_190]
0x140093824  call    cs:__imp_?vLock@NEEDGRELOCK@@QEAAXAEAVXDCOBJ@@@Z; NEEDGRELOCK::vLock(XDCOBJ &)
0x14009382b  nop     dword ptr [rax+rax+00h]
0x140093830  lea     rdx, [rbp+150h+var_198]; struct PDEVOBJ *
0x140093834  lea     rcx, [rbp+150h+var_110]; this
0x140093838  call    ??0DEVLOCKOBJ@@QEAA@AEAVPDEVOBJ@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(PDEVOBJ &)
0x14009383d  mov     r10, [rbp+150h+var_180]
0x140093841  xor     r11d, r11d
0x140093844  mov     r13d, r11d
0x140093847  cmp     dword ptr [r10+20h], 1
0x14009384c  jz      loc_140093AF8
0x140093852  test    dword ptr [rbx+86Ch], 100h
0x14009385c  mov     r14d, [rbx+82Ch]
0x140093863  jnz     short loc_14009386F
0x140093865  mov     rax, [rbx+700h]
0x14009386c  mov     r13, [rax]
0x14009386f  mov     rax, [rbp+150h+arg_28]
0x140093876  xorps   xmm7, xmm7
0x140093879  xorps   xmm6, xmm6
0x14009387c  xorps   xmm8, xmm8
0x140093880  test    rax, rax
0x140093883  jnz     loc_140093BA2
0x140093889  mov     eax, [r10+208h]
0x140093890  test    al, 1
0x140093892  jnz     loc_140093CCE
0x140093898  ucomiss xmm8, xmm7
0x14009389c  jp      loc_140093A47
0x1400938a2  jnz     loc_140093A47
0x1400938a8  test    r12d, r12d
0x1400938ab  jnz     loc_140093B65
0x1400938b1  mov     eax, [rbp+150h+arg_10]
0x1400938b7  lea     rcx, [rbp+150h+var_1C0]
0x1400938bb  mov     rdx, [r10+30h]
0x1400938bf  mov     r9, r13
0x1400938c2  mov     [rsp+250h+var_1D8], r11
0x1400938c7  mov     r8d, r14d
0x1400938ca  mov     dword ptr [rsp+250h+var_1E0], r11d
0x1400938cf  mov     [rsp+250h+var_1E8], r11d
0x1400938d4  mov     [rsp+250h+var_1F0], r15d
0x1400938d9  mov     [rsp+250h+var_1F8], r11d
0x1400938de  mov     [rsp+250h+var_200], r11d
0x1400938e3  mov     [rsp+250h+var_208], r11d
0x1400938e8  mov     [rsp+250h+var_210], eax
0x1400938ec  mov     eax, [rbp+150h+arg_18]
0x1400938f2  mov     [rsp+250h+var_218], eax
0x1400938f6  mov     eax, [rbp+150h+var_1D0]
0x1400938f9  mov     [rsp+250h+var_220], eax
0x1400938fd  mov     [rsp+250h+var_228], edi
0x140093901  mov     [rsp+250h+var_230], esi
0x140093905  call    ?CreateCompatibleSurface@@YA?AVSURFREF@@PEAUHDEV__@@KPEAUHPALETTE__@@HHHHHHHHHKKPEAX@Z; CreateCompatibleSurface(HDEV__ *,ulong,HPALETTE__ *,int,int,int,int,int,int,int,int,int,ulong,ulong,void *)
0x14009390a  mov     rax, [rbp+150h+var_1A0]
0x14009390e  test    rax, rax
0x140093911  jz      loc_140093A35
0x140093917  ucomiss xmm6, xmm7
0x14009391a  jp      short loc_140093926
0x14009391c  jnz     short loc_140093926
0x14009391e  ucomiss xmm8, xmm7
0x140093922  jp      short loc_140093926
0x140093924  jz      short loc_140093955
0x140093926  mov     ecx, [rbp+150h+var_1CC]
0x140093929  bts     dword ptr [rax+0A4h], 0Bh
0x140093931  mov     [rax+2CCh], ecx
0x140093937  mov     ecx, [rbp+150h+var_1C8]
0x14009393a  mov     [rax+2D0h], ecx
0x140093940  movss   dword ptr [rax+2C4h], xmm6
0x140093948  movss   dword ptr [rax+2C8h], xmm8
0x140093951  mov     rax, [rbp+150h+var_1A0]
0x140093955  mov     rcx, [rax+20h]
0x140093959  mov     r8b, 5
0x14009395c  mov     edx, 80000002h
0x140093961  call    cs:__imp_HmgSetOwner
0x140093968  nop     dword ptr [rax+rax+00h]
0x14009396d  mov     rax, [rbp+150h+var_1A0]
0x140093971  mov     rbx, [rax+20h]
0x140093975  test    rax, rax
0x140093978  jz      short loc_140093999
0x14009397a  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140093981  nop     dword ptr [rax+rax+00h]
0x140093986  mov     rdx, [rbp+150h+var_1A0]
0x14009398a  mov     rcx, rax
0x14009398d  call    cs:__imp_DEC_SHARE_REF_CNT
0x140093994  nop     dword ptr [rax+rax+00h]
0x140093999  lea     rcx, [rbp+150h+var_1C0]
0x14009399d  call    cs:__imp_PopThreadGuardedObject
0x1400939a4  nop     dword ptr [rax+rax+00h]
0x1400939a9  lea     rcx, [rbp+150h+var_110]; this
0x1400939ad  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x1400939b2  lea     rcx, [rbp+150h+var_190]
0x1400939b6  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ; NEEDGRELOCK::vUnlock(void)
0x1400939bd  nop     dword ptr [rax+rax+00h]
0x1400939c2  mov     rdx, [rbp+150h+var_188]
0x1400939c6  lea     rcx, aDynamicmodecha; "DynamicModeChange"
0x1400939cd  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x1400939d4  nop     dword ptr [rax+rax+00h]
0x1400939d9  call    ??$GrepReleaseLockValidate@$00@@YAXXZ; GrepReleaseLockValidate<1>(void)
0x1400939de  mov     rcx, [rbp+150h+var_188]
0x1400939e2  call    cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400939e9  nop     dword ptr [rax+rax+00h]
0x1400939ee  lea     rcx, [rbp+150h+var_180]; this
0x1400939f2  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x1400939f7  mov     rax, rbx
0x1400939fa  lea     r11, [rsp+250h+var_30]
0x140093a02  mov     rbx, [r11+40h]
0x140093a06  movaps  xmm6, xmmword ptr [r11-10h]
0x140093a0b  movaps  xmm7, xmmword ptr [r11-20h]
0x140093a10  movaps  xmm8, xmmword ptr [r11-30h]
0x140093a15  mov     rsp, r11
0x140093a18  pop     r15
0x140093a1a  pop     r14
0x140093a1c  pop     r13
0x140093a1e  pop     r12
0x140093a20  pop     rdi
0x140093a21  pop     rsi
0x140093a22  pop     rbp
0x140093a23  retn
0x140093a25  mov     rax, [rbp+150h+var_168]
0x140093a29  test    rax, rax
0x140093a2c  cmovnz  r14, rax
0x140093a30  jmp     loc_14009381C
0x140093a35  xor     ebx, ebx
0x140093a37  jmp     loc_140093975
0x140093a3c  ucomiss xmm6, xmm7
0x140093a3f  jp      short loc_140093A47
0x140093a41  jz      loc_140093898
0x140093a47  movd    xmm0, esi
0x140093a4b  mov     edx, 76h ; 'v'
0x140093a50  cvtdq2ps xmm0, xmm0
0x140093a53  movd    xmm1, edi
0x140093a57  mulss   xmm0, xmm6
0x140093a5b  cvtdq2ps xmm1, xmm1
0x140093a5e  movd    r9d, xmm0
0x140093a63  mulss   xmm1, xmm8
0x140093a68  mov     eax, r9d
0x140093a6b  sar     eax, 17h
0x140093a6e  movzx   r8d, al
0x140093a72  cmp     r8d, 9Eh
0x140093a79  ja      short loc_140093AAB
0x140093a7b  mov     eax, r9d
0x140093a7e  and     eax, 7FFFFFh
0x140093a83  bts     rax, 17h
0x140093a88  cmp     r8d, edx
0x140093a8b  jb      loc_140093B2C
0x140093a91  lea     ecx, [r8-76h]
0x140093a95  shl     rax, cl
0x140093a98  mov     esi, 80000000h
0x140093a9d  add     rsi, rax
0x140093aa0  sar     rsi, 20h
0x140093aa4  test    r9d, r9d
0x140093aa7  jns     short loc_140093AAB
0x140093aa9  neg     esi
0x140093aab  movd    r8d, xmm1
0x140093ab0  mov     eax, r8d
0x140093ab3  sar     eax, 17h
0x140093ab6  movzx   ecx, al
0x140093ab9  cmp     ecx, 9Eh
0x140093abf  ja      loc_1400938A8
0x140093ac5  mov     eax, r8d
0x140093ac8  and     eax, 7FFFFFh
0x140093acd  bts     rax, 17h
0x140093ad2  cmp     ecx, edx
0x140093ad4  jb      short loc_140093B39
0x140093ad6  add     ecx, 0FFFFFF8Ah
0x140093ad9  shl     rax, cl
0x140093adc  mov     edi, 80000000h
0x140093ae1  add     rdi, rax
0x140093ae4  sar     rdi, 20h
0x140093ae8  test    r8d, r8d
0x140093aeb  jns     loc_1400938A8
0x140093af1  neg     edi
0x140093af3  jmp     loc_1400938A8
0x140093af8  mov     rax, [r14+0B0h]
0x140093aff  mov     ecx, [r14+60h]
0x140093b03  mov     r14d, ecx
0x140093b06  test    rax, rax
0x140093b09  jnz     loc_14009386C
0x140093b0f  jmp     loc_14009386F
0x140093b14  mov     ecx, 57h ; 'W'; iError
0x140093b19  call    cs:__imp_EngSetLastError
0x140093b20  nop     dword ptr [rax+rax+00h]
0x140093b25  xor     eax, eax
0x140093b27  jmp     loc_1400939FA
0x140093b2c  mov     ecx, edx
0x140093b2e  sub     ecx, r8d
0x140093b31  sar     rax, cl
0x140093b34  jmp     loc_140093A98
0x140093b39  sub     edx, ecx
0x140093b3b  mov     cl, dl
0x140093b3d  sar     rax, cl
0x140093b40  jmp     short loc_140093ADC
0x140093b42  mov     r9d, 1
0x140093b48  mov     qword ptr [rsp+250h+var_230], r14
0x140093b4d  mov     r8d, r9d
0x140093b50  mov     edx, edi
0x140093b52  mov     ecx, esi
0x140093b54  call    cs:__imp_GreCreateBitmap
0x140093b5b  nop     dword ptr [rax+rax+00h]
0x140093b60  jmp     loc_1400939FA
0x140093b65  test    dword ptr [rbx+28h], 4000000h
0x140093b6c  jz      loc_1400938B1
0x140093b72  mov     rax, [rbp+150h+arg_20]
0x140093b79  test    rax, rax
0x140093b7c  jz      loc_1400938B1
0x140093b82  mov     rcx, [rbx+6F8h]
0x140093b89  test    rcx, rcx
  ... truncated ...
```
