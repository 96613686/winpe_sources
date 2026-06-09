# GrepCreateCompatibleBitmap(OPTAPIDCOBJ &,int,int,ulong,_LUID *,ushort *)

- ea: `0x1400a9c94`
- end: `0x1400aa2fd`
- name: `?GrepCreateCompatibleBitmap@@YAPEAUHBITMAP__@@AEAVOPTAPIDCOBJ@@HHKPEAU_LUID@@PEAG@Z`
- size: `1641`
- prototype: `__int64 __fastcall(struct OPTAPIDCOBJ *this, __int64, __int64, unsigned int, struct _LUID *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400659b0`
- `0x1400a9a54`
- `0x1400a9bb0`
- `0x1401156c8`

## callees

- `0x14005b820`
- `0x14005d010`
- `0x140062138`
- `0x1400698fc`
- `0x14009a40c`
- `0x1400a9c94`
- `0x1400aa304`
- `0x1400ab71c`
- `0x1400ab7ac`
- `0x1400abb04`
- `0x1401dc480`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1400aa2a9`
- `ntoskrnl!DbgPrint` at `0x1400aa2a9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a9dd8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a9e05`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a9f8a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a9dd8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a9e05`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a9f8a`
- `win32kbase!PopThreadGuardedObject` at `0x1400a9fad`
- `win32kbase!PopThreadGuardedObject` at `0x1400a9fad`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x1400a9f9d`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x1400a9f9d`
- `win32kbase!PushThreadGuardedObject` at `0x1400a9d80`
- `win32kbase!PushThreadGuardedObject` at `0x1400a9da6`
- `win32kbase!PushThreadGuardedObject` at `0x1400a9d80`
- `win32kbase!PushThreadGuardedObject` at `0x1400a9da6`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400a9ff2`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400a9ff2`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400a9fdd`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400a9fdd`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x1400a9df4`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x1400a9df4`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400a9fc6`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400a9fc6`
- `win32kbase!HmgSetOwner` at `0x1400a9f71`
- `win32kbase!HmgSetOwner` at `0x1400a9f71`
- `win32kbase!EngSetLastError` at `0x1400aa129`
- `win32kbase!EngSetLastError` at `0x1400aa129`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAXAEAVXDCOBJ@@@Z` at `0x1400a9e34`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAXAEAVXDCOBJ@@@Z` at `0x1400a9e34`
- `win32kbase!GreGetScaledLogPixels` at `0x1400aa1bf`
- `win32kbase!GreGetScaledLogPixels` at `0x1400aa1bf`
- `win32kbase!GreCreateBitmap` at `0x1400aa164`
- `win32kbase!GreCreateBitmap` at `0x1400aa164`

## string_xrefs

- `0x1400aa2a2`: `GreCreateCompatibleBitmap: got CCB_KMSECTIONVIEW without CCB_NOVIDEOMEMORY...ignoring CCB_KMSECTIONVIEW\n`

## pseudocode

```c
__int64 __fastcall GrepCreateCompatibleBitmap(
        struct OPTAPIDCOBJ *this,
        __int64 a2,
        __int64 a3,
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
  unsigned int v23; // r14d
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
  __int64 v45; // rcx
  unsigned __int16 ScaledLogPixels; // ax
  struct SURFACE *v47; // rax
  __int64 v48; // r8
  __int64 *v49; // rax
  BOOL v50; // [rsp+88h] [rbp-80h]
  int v51; // [rsp+8Ch] [rbp-7Ch]
  int v52; // [rsp+90h] [rbp-78h]
  _BYTE v53[32]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-50h]
  __int64 v55; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v56[8]; // [rsp+C8h] [rbp-40h] BYREF
  HSEMAPHORE v57; // [rsp+D0h] [rbp-38h]
  __int64 v58; // [rsp+D8h] [rbp-30h] BYREF
  int v59; // [rsp+E0h] [rbp-28h]
  __int64 v60; // [rsp+E8h] [rbp-20h]
  __int64 v61; // [rsp+F0h] [rbp-18h]
  _OWORD v62[2]; // [rsp+F8h] [rbp-10h] BYREF
  _OWORD v63[2]; // [rsp+118h] [rbp+10h] BYREF
  char v64; // [rsp+138h] [rbp+30h]
  HDC v65[26]; // [rsp+148h] [rbp+40h] BYREF
  BOOL v66; // [rsp+268h] [rbp+160h]
  int v67; // [rsp+270h] [rbp+168h]

  v6 = 0;
  v8 = (int)a3;
  v9 = (int)a2;
  v67 = 0;
  v11 = 0;
  v50 = (a4 & 0x1000000) == 0;
  if ( (a4 & 0x2000000) != 0 )
  {
    if ( (a4 & 0x1000000) != 0 )
    {
      v11 = 1;
      v67 = 1;
    }
    else
    {
      DbgPrint("GreCreateCompatibleBitmap: got CCB_KMSECTIONVIEW without CCB_NOVIDEOMEMORY...ignoring CCB_KMSECTIONVIEW\n");
    }
  }
  v12 = a4 & 0x4000000;
  v13 = (a4 & 0x4000000) != 0;
  v14 = (a4 >> 27) & 1;
  v66 = v13;
  if ( (int)v9 <= 0 || (int)v8 <= 0 || (unsigned __int64)(v8 * v9) > 0x3FFFFFFF )
  {
    EngSetLastError(0x57u);
    return 0;
  }
  if ( *((_QWORD *)this + 12) )
  {
    if ( OPTAPIDCOBJ::bValid(this, a2, a3) )
    {
      v60 = *((_QWORD *)this + 2);
      v61 = 0;
      v58 = 0;
      memset(v62, 0, sizeof(v62));
      v59 = 0;
      PushThreadGuardedObject(
        v62,
        &v58,
        UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
      memset(v63, 0, sizeof(v63));
      PushThreadGuardedObject(
        v63,
        &v58,
        UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
      v16 = *(_QWORD *)this;
      v64 = 0;
      v58 = v16;
      v17 = *(_QWORD *)(v16 + 48);
      v55 = v17;
      if ( (*(_DWORD *)(v17 + 40) & 0x8000) != 0 )
      {
        v47 = XDCOBJ::pSurfaceEff((XDCOBJ *)&v58);
        if ( *(_DWORD *)(v58 + 32) == 1 )
        {
          v48 = *((unsigned int *)v47 + 24);
          v31 = 0;
          v49 = (__int64 *)*((_QWORD *)v47 + 20);
          if ( v49 )
            v6 = *v49;
        }
        else
        {
          v48 = *(unsigned int *)(v17 + 2092);
          if ( (*(_DWORD *)(v17 + 2156) & 0x100) == 0 )
            v6 = **(_QWORD **)(v17 + 1792);
          v31 = 0;
        }
        CreateCompatibleSurface(v53, *(_QWORD *)(v58 + 48), v48, v6, v9, v8, v50, v11, v66, 0, 0, 0, v14, 0, 0, 0);
        if ( v54 )
        {
          SURFREF::vSetPID((SURFREF *)v53, 0x80000002);
          v31 = *(_QWORD *)(v54 + 32);
        }
        SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v53);
        goto LABEL_26;
      }
      v51 = v9;
      v52 = v8;
      v57 = (HSEMAPHORE)(*(_QWORD *)Gre::Base::Globals(v15) + 624LL);
      GreAcquireSemaphoreSharedInternal(v57);
      GrepAcquireLockValidate<1>();
      v19 = Gre::Base::Globals(v18);
      v20 = *(_QWORD *)(v58 + 496);
      if ( v20 )
      {
        if ( v61 )
          v20 = v61;
      }
      else
      {
        v20 = *((_QWORD *)v19 + 547);
      }
      NEEDGRELOCK::vLock((NEEDGRELOCK *)v56, (struct XDCOBJ *)&v58);
      DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v65, (struct PDEVOBJ *)&v55);
      v21 = v58;
      v22 = 0;
      if ( *(_DWORD *)(v58 + 32) == 1 )
      {
        v24 = *(__int64 **)(v20 + 160);
        v23 = *(_DWORD *)(v20 + 96);
        if ( !v24 )
        {
LABEL_14:
          v25 = 0.0;
          v26 = 0.0;
          if ( a6 )
          {
            v45 = *a6;
            if ( (_WORD)v45 != 96 )
            {
              ScaledLogPixels = GreGetScaledLogPixels(v45);
              v21 = v58;
              v25 = (float)ScaledLogPixels / 96.0;
              v26 = v25;
              goto LABEL_31;
            }
          }
          else
          {
            v27 = *(_DWORD *)(v58 + 520);
            if ( (v27 & 1) != 0 && (v27 & 2) == 0 )
            {
              v25 = *(float *)(v58 + 524);
              v26 = *(float *)(v58 + 528);
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
                    v21 = v58;
                  }
                }
              }
            }
            CreateCompatibleSurface(v53, *(_QWORD *)(v21 + 48), v23, v22, v9, v8, v50, v67, v66, 0, 0, 0, v14, 0, 0, 0);
            v30 = v54;
            if ( v54 )
            {
              if ( v25 != 0.0 || v26 != 0.0 )
              {
                *(_DWORD *)(v54 + 148) |= 0x800u;
                *(_DWORD *)(v30 + 700) = v51;
                *(_DWORD *)(v30 + 704) = v52;
                *(float *)(v30 + 692) = v25;
                *(float *)(v30 + 696) = v26;
                v30 = v54;
              }
              LOBYTE(v29) = 5;
              HmgSetOwner(*(_QWORD *)(v30 + 32), 2147483650LL, v29);
              v30 = v54;
              v31 = *(_QWORD *)(v54 + 32);
            }
            else
            {
              v31 = 0;
            }
            if ( v30 )
            {
              v32 = Gre::Base::Globals(v28);
              DEC_SHARE_REF_CNT(v32, v54);
            }
            PopThreadGuardedObject(v53);
            DEVLOCKOBJ::~DEVLOCKOBJ(v65);
            NEEDGRELOCK::vUnlock((NEEDGRELOCK *)v56);
            EtwTraceGreLockReleaseSemaphore(L"DynamicModeChange", v57);
            GrepReleaseLockValidate<1>();
            GreReleaseSemaphoreSharedInternal(v57);
LABEL_26:
            APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v58);
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
0x1400a9c94  mov     rax, rsp
0x1400a9c97  mov     [rax+8], rbx
0x1400a9c9b  push    rbp
0x1400a9c9c  push    rsi
0x1400a9c9d  push    rdi
0x1400a9c9e  push    r12
0x1400a9ca0  push    r13
0x1400a9ca2  push    r14
0x1400a9ca4  push    r15
0x1400a9ca6  lea     rbp, [rax-148h]
0x1400a9cad  sub     rsp, 210h
0x1400a9cb4  xor     r14d, r14d
0x1400a9cb7  movaps  xmmword ptr [rax-48h], xmm6
0x1400a9cbb  movaps  xmmword ptr [rax-58h], xmm7
0x1400a9cbf  mov     rbx, rcx
0x1400a9cc2  movaps  xmmword ptr [rax-68h], xmm8
0x1400a9cc7  mov     ecx, r14d
0x1400a9cca  mov     eax, r9d
0x1400a9ccd  movsxd  rdi, r8d
0x1400a9cd0  and     eax, 1000000h
0x1400a9cd5  movsxd  rsi, edx
0x1400a9cd8  mov     r15d, r9d
0x1400a9cdb  mov     [rbp+140h+arg_18], r14d
0x1400a9ce2  setz    cl
0x1400a9ce5  mov     r13d, r14d
0x1400a9ce8  mov     [rbp+140h+var_1C0], ecx
0x1400a9ceb  bt      r9d, 19h
0x1400a9cf0  jb      loc_1400AA28C
0x1400a9cf6  mov     r12d, r15d
0x1400a9cf9  mov     eax, r14d
0x1400a9cfc  and     r12d, 4000000h
0x1400a9d03  setnz   al
0x1400a9d06  shr     r15d, 1Bh
0x1400a9d0a  and     r15d, 1
0x1400a9d0e  mov     [rbp+140h+arg_10], eax
0x1400a9d14  test    esi, esi
0x1400a9d16  jle     loc_1400AA124
0x1400a9d1c  test    edi, edi
0x1400a9d1e  jle     loc_1400AA124
0x1400a9d24  mov     rcx, rsi
0x1400a9d27  imul    rcx, rdi
0x1400a9d2b  cmp     rcx, 3FFFFFFFh
0x1400a9d32  ja      loc_1400AA124
0x1400a9d38  cmp     [rbx+60h], r14
0x1400a9d3c  jz      loc_1400AA152
0x1400a9d42  mov     rcx, rbx; this
0x1400a9d45  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x1400a9d4a  test    al, al
0x1400a9d4c  jz      loc_1400AA135
0x1400a9d52  mov     rax, [rbx+10h]
0x1400a9d56  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x1400a9d5d  xorps   xmm0, xmm0
0x1400a9d60  mov     [rbp+140h+var_160], rax
0x1400a9d64  lea     rdx, [rbp+140h+var_170]
0x1400a9d68  mov     [rbp+140h+var_158], r14
0x1400a9d6c  lea     rcx, [rbp+140h+var_150]
0x1400a9d70  mov     [rbp+140h+var_170], r14
0x1400a9d74  movups  [rbp+140h+var_150], xmm0
0x1400a9d78  mov     [rbp+140h+var_168], r14d
0x1400a9d7c  movups  [rbp+140h+var_140], xmm0
0x1400a9d80  call    cs:__imp_PushThreadGuardedObject
0x1400a9d87  nop     dword ptr [rax+rax+00h]
0x1400a9d8c  xorps   xmm0, xmm0
0x1400a9d8f  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400a9d96  lea     rdx, [rbp+140h+var_170]
0x1400a9d9a  lea     rcx, [rbp+140h+var_130]
0x1400a9d9e  movups  [rbp+140h+var_130], xmm0
0x1400a9da2  movups  [rbp+140h+var_120], xmm0
0x1400a9da6  call    cs:__imp_PushThreadGuardedObject
0x1400a9dad  nop     dword ptr [rax+rax+00h]
0x1400a9db2  mov     rbx, [rbx]
0x1400a9db5  mov     [rbp+140h+var_110], r14b
0x1400a9db9  mov     [rbp+140h+var_170], rbx
0x1400a9dbd  mov     rbx, [rbx+30h]
0x1400a9dc1  mov     [rbp+140h+var_188], rbx
0x1400a9dc5  test    dword ptr [rbx+28h], 8000h
0x1400a9dcc  jnz     loc_1400AA1ED
0x1400a9dd2  mov     [rbp+140h+var_1BC], esi
0x1400a9dd5  mov     [rbp+140h+var_1B8], edi
0x1400a9dd8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a9ddf  nop     dword ptr [rax+rax+00h]
0x1400a9de4  mov     rax, [rax]
0x1400a9de7  add     rax, 270h
0x1400a9ded  mov     rcx, rax
0x1400a9df0  mov     [rbp+140h+var_178], rax
0x1400a9df4  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400a9dfb  nop     dword ptr [rax+rax+00h]
0x1400a9e00  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x1400a9e05  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a9e0c  nop     dword ptr [rax+rax+00h]
0x1400a9e11  mov     rcx, [rbp+140h+var_170]
0x1400a9e15  mov     r14, [rcx+1F0h]
0x1400a9e1c  test    r14, r14
0x1400a9e1f  jnz     loc_1400AA035
0x1400a9e25  mov     r14, [rax+1118h]
0x1400a9e2c  lea     rdx, [rbp+140h+var_170]
0x1400a9e30  lea     rcx, [rbp+140h+var_180]
0x1400a9e34  call    cs:__imp_?vLock@NEEDGRELOCK@@QEAAXAEAVXDCOBJ@@@Z; NEEDGRELOCK::vLock(XDCOBJ &)
0x1400a9e3b  nop     dword ptr [rax+rax+00h]
0x1400a9e40  lea     rdx, [rbp+140h+var_188]; struct PDEVOBJ *
0x1400a9e44  lea     rcx, [rbp+140h+var_100]; this
0x1400a9e48  call    ??0DEVLOCKOBJ@@QEAA@AEAVPDEVOBJ@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(PDEVOBJ &)
0x1400a9e4d  mov     r10, [rbp+140h+var_170]
0x1400a9e51  xor     r11d, r11d
0x1400a9e54  mov     r13d, r11d
0x1400a9e57  cmp     dword ptr [r10+20h], 1
0x1400a9e5c  jz      loc_1400AA108
0x1400a9e62  test    dword ptr [rbx+86Ch], 100h
0x1400a9e6c  mov     r14d, [rbx+82Ch]
0x1400a9e73  jnz     short loc_1400A9E7F
0x1400a9e75  mov     rax, [rbx+700h]
0x1400a9e7c  mov     r13, [rax]
0x1400a9e7f  mov     rax, [rbp+140h+arg_28]
0x1400a9e86  xorps   xmm7, xmm7
0x1400a9e89  xorps   xmm6, xmm6
0x1400a9e8c  xorps   xmm8, xmm8
0x1400a9e90  test    rax, rax
0x1400a9e93  jnz     loc_1400AA1B2
0x1400a9e99  mov     eax, [r10+208h]
0x1400a9ea0  test    al, 1
0x1400a9ea2  jnz     loc_1400AA2DE
0x1400a9ea8  ucomiss xmm8, xmm7
0x1400a9eac  jp      loc_1400AA057
0x1400a9eb2  jnz     loc_1400AA057
0x1400a9eb8  test    r12d, r12d
0x1400a9ebb  jnz     loc_1400AA175
0x1400a9ec1  mov     eax, [rbp+140h+arg_10]
0x1400a9ec7  lea     rcx, [rbp+140h+var_1B0]
0x1400a9ecb  mov     rdx, [r10+30h]
0x1400a9ecf  mov     r9, r13
0x1400a9ed2  mov     [rsp+240h+var_1C8], r11
0x1400a9ed7  mov     r8d, r14d
0x1400a9eda  mov     dword ptr [rsp+240h+var_1D0], r11d
0x1400a9edf  mov     [rsp+240h+var_1D8], r11d
0x1400a9ee4  mov     [rsp+240h+var_1E0], r15d
0x1400a9ee9  mov     [rsp+240h+var_1E8], r11d
0x1400a9eee  mov     [rsp+240h+var_1F0], r11d
0x1400a9ef3  mov     [rsp+240h+var_1F8], r11d
0x1400a9ef8  mov     [rsp+240h+var_200], eax
0x1400a9efc  mov     eax, [rbp+140h+arg_18]
0x1400a9f02  mov     [rsp+240h+var_208], eax
0x1400a9f06  mov     eax, [rbp+140h+var_1C0]
0x1400a9f09  mov     [rsp+240h+var_210], eax
0x1400a9f0d  mov     [rsp+240h+var_218], edi
0x1400a9f11  mov     [rsp+240h+var_220], esi
0x1400a9f15  call    ?CreateCompatibleSurface@@YA?AVSURFREF@@PEAUHDEV__@@KPEAUHPALETTE__@@HHHHHHHHHKKPEAX@Z; CreateCompatibleSurface(HDEV__ *,ulong,HPALETTE__ *,int,int,int,int,int,int,int,int,int,ulong,ulong,void *)
0x1400a9f1a  mov     rax, [rbp+140h+var_190]
0x1400a9f1e  test    rax, rax
0x1400a9f21  jz      loc_1400AA045
0x1400a9f27  ucomiss xmm6, xmm7
0x1400a9f2a  jp      short loc_1400A9F36
0x1400a9f2c  jnz     short loc_1400A9F36
0x1400a9f2e  ucomiss xmm8, xmm7
0x1400a9f32  jp      short loc_1400A9F36
0x1400a9f34  jz      short loc_1400A9F65
0x1400a9f36  mov     ecx, [rbp+140h+var_1BC]
0x1400a9f39  bts     dword ptr [rax+94h], 0Bh
0x1400a9f41  mov     [rax+2BCh], ecx
0x1400a9f47  mov     ecx, [rbp+140h+var_1B8]
0x1400a9f4a  mov     [rax+2C0h], ecx
0x1400a9f50  movss   dword ptr [rax+2B4h], xmm6
0x1400a9f58  movss   dword ptr [rax+2B8h], xmm8
0x1400a9f61  mov     rax, [rbp+140h+var_190]
0x1400a9f65  mov     rcx, [rax+20h]
0x1400a9f69  mov     r8b, 5
0x1400a9f6c  mov     edx, 80000002h
0x1400a9f71  call    cs:__imp_HmgSetOwner
0x1400a9f78  nop     dword ptr [rax+rax+00h]
0x1400a9f7d  mov     rax, [rbp+140h+var_190]
0x1400a9f81  mov     rbx, [rax+20h]
0x1400a9f85  test    rax, rax
0x1400a9f88  jz      short loc_1400A9FA9
0x1400a9f8a  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a9f91  nop     dword ptr [rax+rax+00h]
0x1400a9f96  mov     rdx, [rbp+140h+var_190]
0x1400a9f9a  mov     rcx, rax
0x1400a9f9d  call    cs:__imp_DEC_SHARE_REF_CNT
0x1400a9fa4  nop     dword ptr [rax+rax+00h]
0x1400a9fa9  lea     rcx, [rbp+140h+var_1B0]
0x1400a9fad  call    cs:__imp_PopThreadGuardedObject
0x1400a9fb4  nop     dword ptr [rax+rax+00h]
0x1400a9fb9  lea     rcx, [rbp+140h+var_100]; this
0x1400a9fbd  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x1400a9fc2  lea     rcx, [rbp+140h+var_180]
0x1400a9fc6  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ; NEEDGRELOCK::vUnlock(void)
0x1400a9fcd  nop     dword ptr [rax+rax+00h]
0x1400a9fd2  mov     rdx, [rbp+140h+var_178]
0x1400a9fd6  lea     rcx, aDynamicmodecha; "DynamicModeChange"
0x1400a9fdd  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x1400a9fe4  nop     dword ptr [rax+rax+00h]
0x1400a9fe9  call    ??$GrepReleaseLockValidate@$00@@YAXXZ; GrepReleaseLockValidate<1>(void)
0x1400a9fee  mov     rcx, [rbp+140h+var_178]
0x1400a9ff2  call    cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400a9ff9  nop     dword ptr [rax+rax+00h]
0x1400a9ffe  lea     rcx, [rbp+140h+var_170]; this
0x1400aa002  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x1400aa007  mov     rax, rbx
0x1400aa00a  lea     r11, [rsp+240h+var_30]
0x1400aa012  mov     rbx, [r11+40h]
0x1400aa016  movaps  xmm6, xmmword ptr [r11-10h]
0x1400aa01b  movaps  xmm7, xmmword ptr [r11-20h]
0x1400aa020  movaps  xmm8, xmmword ptr [r11-30h]
0x1400aa025  mov     rsp, r11
0x1400aa028  pop     r15
0x1400aa02a  pop     r14
0x1400aa02c  pop     r13
0x1400aa02e  pop     r12
0x1400aa030  pop     rdi
0x1400aa031  pop     rsi
0x1400aa032  pop     rbp
0x1400aa033  retn
0x1400aa035  mov     rax, [rbp+140h+var_158]
0x1400aa039  test    rax, rax
0x1400aa03c  cmovnz  r14, rax
0x1400aa040  jmp     loc_1400A9E2C
0x1400aa045  xor     ebx, ebx
0x1400aa047  jmp     loc_1400A9F85
0x1400aa04c  ucomiss xmm6, xmm7
0x1400aa04f  jp      short loc_1400AA057
0x1400aa051  jz      loc_1400A9EA8
0x1400aa057  movd    xmm0, esi
0x1400aa05b  mov     edx, 76h ; 'v'
0x1400aa060  cvtdq2ps xmm0, xmm0
0x1400aa063  movd    xmm1, edi
0x1400aa067  mulss   xmm0, xmm6
0x1400aa06b  cvtdq2ps xmm1, xmm1
0x1400aa06e  movd    r9d, xmm0
0x1400aa073  mulss   xmm1, xmm8
0x1400aa078  mov     eax, r9d
0x1400aa07b  sar     eax, 17h
0x1400aa07e  movzx   r8d, al
0x1400aa082  cmp     r8d, 9Eh
0x1400aa089  ja      short loc_1400AA0BB
0x1400aa08b  mov     eax, r9d
0x1400aa08e  and     eax, 7FFFFFh
0x1400aa093  bts     rax, 17h
0x1400aa098  cmp     r8d, edx
0x1400aa09b  jb      loc_1400AA13C
0x1400aa0a1  lea     ecx, [r8-76h]
0x1400aa0a5  shl     rax, cl
0x1400aa0a8  mov     esi, 80000000h
0x1400aa0ad  add     rsi, rax
0x1400aa0b0  sar     rsi, 20h
0x1400aa0b4  test    r9d, r9d
0x1400aa0b7  jns     short loc_1400AA0BB
0x1400aa0b9  neg     esi
0x1400aa0bb  movd    r8d, xmm1
0x1400aa0c0  mov     eax, r8d
0x1400aa0c3  sar     eax, 17h
0x1400aa0c6  movzx   ecx, al
0x1400aa0c9  cmp     ecx, 9Eh
0x1400aa0cf  ja      loc_1400A9EB8
0x1400aa0d5  mov     eax, r8d
0x1400aa0d8  and     eax, 7FFFFFh
0x1400aa0dd  bts     rax, 17h
0x1400aa0e2  cmp     ecx, edx
0x1400aa0e4  jb      short loc_1400AA149
0x1400aa0e6  add     ecx, 0FFFFFF8Ah
0x1400aa0e9  shl     rax, cl
0x1400aa0ec  mov     edi, 80000000h
0x1400aa0f1  add     rdi, rax
0x1400aa0f4  sar     rdi, 20h
0x1400aa0f8  test    r8d, r8d
0x1400aa0fb  jns     loc_1400A9EB8
0x1400aa101  neg     edi
0x1400aa103  jmp     loc_1400A9EB8
0x1400aa108  mov     rax, [r14+0A0h]
0x1400aa10f  mov     ecx, [r14+60h]
0x1400aa113  mov     r14d, ecx
0x1400aa116  test    rax, rax
0x1400aa119  jnz     loc_1400A9E7C
0x1400aa11f  jmp     loc_1400A9E7F
0x1400aa124  mov     ecx, 57h ; 'W'; iError
0x1400aa129  call    cs:__imp_EngSetLastError
0x1400aa130  nop     dword ptr [rax+rax+00h]
0x1400aa135  xor     eax, eax
0x1400aa137  jmp     loc_1400AA00A
0x1400aa13c  mov     ecx, edx
0x1400aa13e  sub     ecx, r8d
0x1400aa141  sar     rax, cl
0x1400aa144  jmp     loc_1400AA0A8
0x1400aa149  sub     edx, ecx
0x1400aa14b  mov     cl, dl
0x1400aa14d  sar     rax, cl
0x1400aa150  jmp     short loc_1400AA0EC
0x1400aa152  mov     r9d, 1
0x1400aa158  mov     qword ptr [rsp+240h+var_220], r14
0x1400aa15d  mov     r8d, r9d
0x1400aa160  mov     edx, edi
0x1400aa162  mov     ecx, esi
0x1400aa164  call    cs:__imp_GreCreateBitmap
0x1400aa16b  nop     dword ptr [rax+rax+00h]
0x1400aa170  jmp     loc_1400AA00A
0x1400aa175  test    dword ptr [rbx+28h], 4000000h
0x1400aa17c  jz      loc_1400A9EC1
0x1400aa182  mov     rax, [rbp+140h+arg_20]
0x1400aa189  test    rax, rax
0x1400aa18c  jz      loc_1400A9EC1
0x1400aa192  mov     rcx, [rbx+6F8h]
0x1400aa199  test    rcx, rcx
  ... truncated ...
```
