# PALMEMOBJ::bCreatePalette(ulong,ulong,ulong const *,ulong,ulong,ulong,ulong,int)

- ea: `0x140029cd0`
- end: `0x14002a620`
- name: `?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z`
- size: `2384`
- prototype: `__int64 __fastcall(PALMEMOBJ *__hidden this, unsigned int, unsigned int, const unsigned int *, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `6`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14002ac20`
- `0x14010c69c`
- `0x140175b70`
- `0x1401b06e0`
- `0x1401e5298`
- `0x1402d9008`

## callees

- `0x140009cfc`
- `0x14000bc78`
- `0x14000c544`
- `0x140029510`
- `0x140029cd0`
- `0x14002a628`
- `0x14002a66c`
- `0x14004a0d0`
- `0x14004a360`
- `0x14004b3a0`
- `0x1401acde0`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140029e31`
- `ntoskrnl!ExAllocatePool2` at `0x14002a217`
- `ntoskrnl!ExAllocatePool2` at `0x14002a39a`
- `ntoskrnl!ExAllocatePool2` at `0x140029e31`
- `ntoskrnl!ExAllocatePool2` at `0x14002a217`
- `ntoskrnl!ExAllocatePool2` at `0x14002a39a`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14002a265`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14002a265`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002a15f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002a15f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140029dca`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140029dca`
- `WIN32K!W32GetSessionState` at `0x140029cfa`
- `WIN32K!W32GetSessionState` at `0x140029da2`
- `WIN32K!W32GetSessionState` at `0x14002a10f`
- `WIN32K!W32GetSessionState` at `0x140029cfa`
- `WIN32K!W32GetSessionState` at `0x140029da2`
- `WIN32K!W32GetSessionState` at `0x14002a10f`
- `WIN32K!W32GetUserSessionState` at `0x140029deb`
- `WIN32K!W32GetUserSessionState` at `0x140029deb`

## pseudocode

```c
__int64 __fastcall PALMEMOBJ::bCreatePalette(
        struct OBJECT **this,
        int a2,
        unsigned int a3,
        const unsigned int *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  __int64 SessionState; // rax
  unsigned int v13; // r13d
  unsigned int v14; // r15d
  unsigned int v15; // ebx
  unsigned int v16; // esi
  unsigned int v17; // edi
  __int64 v18; // rcx
  struct OBJECT *v19; // rax
  __int64 UserSessionState; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // r13
  int v23; // eax
  __int64 Pool2; // rcx
  _DWORD *v25; // r8
  int k; // ecx
  int v27; // eax
  unsigned int v28; // edx
  int v29; // eax
  int v30; // r9d
  unsigned int v31; // eax
  _DWORD *v32; // r10
  int m; // ecx
  int v34; // eax
  unsigned int v35; // edx
  int v36; // eax
  int v37; // r8d
  _DWORD *v38; // r9
  int n; // ecx
  int v40; // eax
  unsigned int v41; // edx
  int v42; // eax
  struct Gre::Base::SESSION_GLOBALS *v43; // rsi
  int v44; // r8d
  struct OBJECT *v45; // rax
  int v46; // ecx
  int v47; // ecx
  struct HOBJ__ *inserted; // rax
  struct OBJECT *v49; // rbx
  unsigned int v50; // r8d
  void *v52; // rcx
  struct OBJECT *v53; // rbx
  __int64 v54; // rcx
  _DWORD *v55; // rdx
  int v56; // r12d
  _DWORD *v57; // rcx
  const unsigned int *v58; // r9
  _QWORD *v59; // rax
  unsigned int j; // r8d
  int v61; // eax
  unsigned __int64 i; // rax
  int v63; // r12d
  unsigned __int64 Buffer; // [rsp+20h] [rbp-148h]
  __int64 Buffera; // [rsp+20h] [rbp-148h]
  PVOID Bufferb; // [rsp+20h] [rbp-148h]
  struct Gre::Base::SESSION_GLOBALS *v67; // [rsp+28h] [rbp-140h]
  unsigned __int64 v68; // [rsp+30h] [rbp-138h]
  _BYTE v70[32]; // [rsp+60h] [rbp-108h] BYREF
  struct OBJECT *v71; // [rsp+80h] [rbp-E8h]
  PVOID BackTrace[27]; // [rsp+90h] [rbp-D8h] BYREF
  char v73; // [rsp+178h] [rbp+10h]
  unsigned int v74; // [rsp+180h] [rbp+18h]

  v74 = a3;
  SessionState = W32GetSessionState(this);
  if ( a2 != 16 )
  {
    if ( a2 == 1 )
    {
      v13 = 4 * a3 + 4;
      if ( !a3 )
        return 0;
      v14 = a8 & 0x3102F00;
      goto LABEL_8;
    }
    if ( a2 == 2 )
    {
      v15 = a5;
      if ( !a5 )
        return 0;
      v17 = a7;
      if ( !a7 )
        return 0;
      v16 = a6;
      if ( !a6 )
        return 0;
      v14 = a8 & 0x3100300;
      v74 = 0;
      v13 = 52;
      goto LABEL_9;
    }
    if ( a2 != 4 && a2 != 8 )
      return 0;
  }
  v13 = 4;
  v14 = a8 & 0x3100100 | 0x200;
  v74 = 0;
  if ( a2 != 16 )
  {
    if ( a2 == 4 )
    {
      v15 = 255;
      v16 = 65280;
      v17 = 16711680;
    }
    else
    {
      v15 = 16711680;
      v16 = 65280;
      v17 = 255;
    }
    v13 = 52;
    goto LABEL_9;
  }
LABEL_8:
  v15 = a5;
  v16 = a6;
  v17 = a7;
LABEL_9:
  v67 = *(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88);
  v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetSessionState(v67) + 88) + 4384LL) + 8LL);
  if ( v18 )
    v19 = (struct OBJECT *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v18 + 48));
  else
    v19 = 0;
  *this = v19;
  if ( !v19 )
    return 0;
  if ( !v13 )
    goto LABEL_80;
  UserSessionState = W32GetUserSessionState(v18);
  v21 = v13;
  Buffer = v13;
  v22 = UserSessionState + 72016;
  v23 = *(_DWORD *)(UserSessionState + 72016);
  if ( !v23 )
    goto LABEL_14;
  if ( v23 != 1 )
  {
    if ( v23 == 2 )
    {
      if ( (*(_DWORD *)(v22 + 80) & 0x6C706147) != 0x6C706147 )
      {
LABEL_14:
        Pool2 = ExAllocatePool2(256, v21, 1819304263);
        if ( Pool2 )
          _InterlockedIncrement64((volatile signed __int64 *)(v22 + 112));
        goto LABEL_16;
      }
      for ( i = 0; ; ++i )
      {
        v68 = i;
        if ( i >= *(unsigned int *)(v22 + 84) )
          goto LABEL_14;
        if ( *(_DWORD *)(v22 + 4 * i + 48) == 1819304263 )
          break;
      }
      if ( v21 < 0x1000 || (v73 = 0, (v21 & 0xFFF) != 0) )
      {
        v73 = 1;
        v21 += 16LL;
      }
      Buffera = ExAllocatePool2(256, v21, 1819304263);
      if ( Buffera )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v22 + 128));
        memset(BackTrace, 0, 0xA0u);
        RtlCaptureStackBackTrace(0, 0x14u, BackTrace, 0);
        if ( v73 && (unsigned __int64)(Buffera & 0xFFF) + 16 < 0x1000 )
        {
          if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(
                                  v22,
                                  Buffera,
                                  v68,
                                  BackTrace) )
          {
            Pool2 = Buffera + 16;
            goto LABEL_16;
          }
        }
        else if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(
                                     v22,
                                     Buffera,
                                     v68,
                                     BackTrace) )
        {
          Pool2 = Buffera;
          goto LABEL_16;
        }
        _InterlockedIncrement64((volatile signed __int64 *)(v22 + 136));
        _lambda_2af9a864ca5eb776d3057466a2e51944_::_lambda_invoker_cdecl_<void *>((PVOID)Buffera);
        goto LABEL_80;
      }
    }
    goto LABEL_80;
  }
  if ( !NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(
          (NSInstrumentation::CLeakTrackingAllocator *)v22,
          0x6C706147u)
    || Buffer + 16 < Buffer )
  {
LABEL_80:
    Pool2 = 0;
    goto LABEL_16;
  }
  v59 = (_QWORD *)ExAllocatePool2(256, Buffer + 16, 1819304263);
  if ( !v59 )
  {
    Bufferb = 0;
    goto LABEL_95;
  }
  _InterlockedIncrement64((volatile signed __int64 *)(v22 + 112));
  *v59 = 1819304263;
  Pool2 = (__int64)(v59 + 2);
  Bufferb = v59 + 2;
  if ( v59 == (_QWORD *)-16LL )
  {
LABEL_95:
    NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(
      *(NSInstrumentation::CPointerHashTable **)(v22 + 8),
      (const void *)0x6C706147);
    Pool2 = (__int64)Bufferb;
  }
LABEL_16:
  *((_QWORD *)*this + 16) = Pool2;
  if ( *((_QWORD *)*this + 16) )
  {
    *((_DWORD *)*this + 6) = v14 | a2;
    *((_DWORD *)*this + 7) = v74;
    *((_DWORD *)*this + 8) = _InterlockedIncrement((volatile signed __int32 *)v67 + 944);
    *((_QWORD *)*this + 5) = 0;
    *((_QWORD *)*this + 6) = 0;
    *((_DWORD *)*this + 15) = 0;
    *((_DWORD *)*this + 14) = 0;
    *((_QWORD *)*this + 9) = 0;
    *((_QWORD *)*this + 10) = 0;
    *((_QWORD *)*this + 11) = 0;
    *((_DWORD *)*this + 9) = 0;
    *((_QWORD *)*this + 13) = 0;
    *((_QWORD *)*this + 15) = *this;
    *((_QWORD *)*this + 14) = *((_QWORD *)*this + 16);
    if ( a2 != 8 )
    {
      v56 = a2 - 1;
      if ( !v56 )
      {
        v57 = (_DWORD *)*((_QWORD *)*this + 14);
        v58 = a4;
        if ( a4 )
        {
          for ( j = 0; j < v74; ++j )
          {
            v61 = *v58++;
            *v57++ = v61;
          }
          v44 = 4;
          v43 = v67;
LABEL_48:
          v45 = *this;
          if ( *((_DWORD *)*this + 7) )
          {
            v47 = 2;
            v44 = 1;
LABEL_53:
            *((_DWORD *)v45 + 25) = v44;
            *((_DWORD *)*this + 24) = v47;
            HmgInsertObjectHelper::HmgInsertObjectHelper((HmgInsertObjectHelper *)v70);
            inserted = 0;
            if ( !v71 )
            {
              v49 = *this;
              v50 = 11;
              if ( !a9 )
                v50 = 3;
              inserted = HmgInsertObjectInternal(v43, *this, v50, 8u);
              if ( !inserted )
              {
LABEL_60:
                HmgInsertObjectHelper::~HmgInsertObjectHelper((HmgInsertObjectHelper *)v70);
                v52 = (void *)*((_QWORD *)*this + 16);
                if ( v52 )
                  GreDeleteFastMutex(v52);
                v53 = *this;
                v54 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetSessionState(v52) + 88) + 4384LL) + 8LL);
                if ( v54 )
                {
                  *(_OWORD *)v53 = 0;
                  *((_OWORD *)v53 + 1) = 0;
                  *((_OWORD *)v53 + 2) = 0;
                  *((_OWORD *)v53 + 3) = 0;
                  *((_OWORD *)v53 + 4) = 0;
                  *((_OWORD *)v53 + 5) = 0;
                  *((_OWORD *)v53 + 6) = 0;
                  *((_OWORD *)v53 + 7) = 0;
                  *((_OWORD *)v53 + 8) = 0;
                  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v54 + 48), v53);
                }
                *this = 0;
                return 0;
              }
              v71 = v49;
            }
            if ( inserted )
            {
              HmgInsertObjectHelper::~HmgInsertObjectHelper((HmgInsertObjectHelper *)v70);
              return 1;
            }
            goto LABEL_60;
          }
          v46 = *((_DWORD *)v45 + 6);
          if ( (v46 & 2) == 0 )
          {
            if ( (v46 & 8) != 0 )
              v44 = 6;
            else
              v44 = 8 - ((v46 & 0x10) != 0);
            goto LABEL_52;
          }
          v55 = (_DWORD *)*((_QWORD *)v45 + 14);
          if ( v55[2] == 31 )
          {
            if ( v55[1] == 2016 && *v55 == 63488 )
            {
              v44 = 3;
              goto LABEL_52;
            }
            if ( v55[1] == 992 && *v55 == 31744 )
              goto LABEL_52;
          }
          v44 = 5;
LABEL_52:
          v47 = v44;
          goto LABEL_53;
        }
        if ( !v74 )
        {
          v43 = v67;
          goto LABEL_47;
        }
        memset(v57, 0, 4LL * v74);
LABEL_46:
        v43 = v67;
LABEL_47:
        v44 = 4;
        goto LABEL_48;
      }
      v63 = v56 - 1;
      if ( v63 && v63 != 2 )
      {
        v43 = v67;
        goto LABEL_47;
      }
    }
    **((_DWORD **)*this + 14) = v15;
    *(_DWORD *)(*((_QWORD *)*this + 14) + 4LL) = v16;
    *(_DWORD *)(*((_QWORD *)*this + 14) + 8LL) = v17;
    if ( v15 == 255 && v16 == 65280 && v17 == 16711680 )
    {
      *((_DWORD *)*this + 6) |= 4u;
    }
    else if ( v15 == 63488 && v16 == 2016 && v17 == 31 )
    {
      *((_DWORD *)*this + 6) |= 0x400000u;
    }
    else if ( v15 == 31744 && v16 == 992 && v17 == 31 )
    {
      *((_DWORD *)*this + 6) |= 0x200000u;
    }
    v25 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( k = 0; (v15 & 1) == 0; ++k )
      v15 >>= 1;
    v27 = k;
    do
    {
      v15 >>= 1;
      ++v27;
    }
    while ( (v15 & 1) != 0 );
    v28 = v27 - k;
    v25[9] = v27 - k;
    v29 = v27 - 8;
    if ( v28 <= 8 )
      v29 = k;
    v25[6] = v29;
    v30 = 8;
    if ( v28 > 8 )
      v31 = 0;
    else
      v31 = 8 - v28;
    v25[3] = v31;
    v32 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( m = 0; (v16 & 1) == 0; ++m )
      v16 >>= 1;
    v34 = m;
    do
    {
      v16 >>= 1;
      ++v34;
    }
    while ( (v16 & 1) != 0 );
    v35 = v34 - m;
    v32[10] = v34 - m;
    v36 = v34 - 8;
    if ( v35 <= 8 )
      v36 = m;
    v32[7] = v36;
    v37 = 16;
    if ( v35 <= 8 )
      v30 = 16 - v35;
    v32[4] = v30;
    v38 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( n = 0; (v17 & 1) == 0; ++n )
      v17 >>= 1;
    v40 = n;
    do
    {
      v17 >>= 1;
      ++v40;
    }
    while ( (v17 & 1) != 0 );
    v41 = v40 - n;
    v38[11] = v40 - n;
    v42 = v40 - 8;
    if ( v41 <= 8 )
      v42 = n;
    v38[8] = v42;
    if ( v41 <= 8 )
      v37 = 24 - v41;
    v38[5] = v37;
    goto LABEL_46;
  }
  XEPALOBJ_FreePaletteMemory(this);
  return 0;
}

```

## disassembly

```asm
0x140029cd0  mov     [rsp+arg_10], r8d
0x140029cd5  mov     [rsp+arg_0], rcx
0x140029cda  push    rbx
0x140029cdb  push    rsi
0x140029cdc  push    rdi
0x140029cdd  push    r12
0x140029cdf  push    r13
0x140029ce1  push    r14
0x140029ce3  push    r15
0x140029ce5  sub     rsp, 130h
0x140029cec  mov     [rsp+168h+var_118], r9
0x140029cf1  mov     ebx, r8d
0x140029cf4  mov     r12d, edx
0x140029cf7  mov     r14, rcx
0x140029cfa  call    cs:__imp_W32GetSessionState
0x140029d01  nop     dword ptr [rax+rax+00h]
0x140029d06  cmp     r12d, 10h
0x140029d0a  jnz     loc_14002A190
0x140029d10  mov     r13d, 4
0x140029d16  mov     r15d, [rsp+168h+arg_38]
0x140029d1e  and     r15d, 3100100h
0x140029d25  bts     r15d, 9
0x140029d2a  mov     [rsp+168h+arg_10], 0
0x140029d35  cmp     r12d, 10h
0x140029d39  jz      short loc_140029D84
0x140029d3b  cmp     r12d, r13d
0x140029d3e  jz      loc_14002A342
0x140029d44  cmp     r12d, 8
0x140029d48  jnz     loc_14002A587
0x140029d4e  mov     ebx, 0FF0000h
0x140029d53  mov     esi, 0FF00h
0x140029d58  mov     edi, 0FFh
0x140029d5d  mov     r13d, 34h ; '4'
0x140029d63  jmp     short loc_140029D99
0x140029d65  lea     r13d, ds:4[rbx*4]
0x140029d6d  test    ebx, ebx
0x140029d6f  jz      loc_14002A16E
0x140029d75  mov     r15d, [rsp+168h+arg_38]
0x140029d7d  and     r15d, 3102F00h
0x140029d84  mov     ebx, [rsp+168h+arg_20]
0x140029d8b  mov     esi, [rsp+168h+arg_28]
0x140029d92  mov     edi, [rsp+168h+arg_30]
0x140029d99  mov     rcx, [rax+58h]
0x140029d9d  mov     [rsp+168h+var_140], rcx
0x140029da2  call    cs:__imp_W32GetSessionState
0x140029da9  nop     dword ptr [rax+rax+00h]
0x140029dae  mov     rcx, [rax+58h]
0x140029db2  mov     rax, [rcx+1120h]
0x140029db9  mov     rcx, [rax+8]
0x140029dbd  test    rcx, rcx
0x140029dc0  jz      loc_14002A5A1
0x140029dc6  add     rcx, 30h ; '0'; Lookaside
0x140029dca  call    cs:__imp_ExAllocateFromLookasideListEx
0x140029dd1  nop     dword ptr [rax+rax+00h]
0x140029dd6  mov     [r14], rax
0x140029dd9  test    rax, rax
0x140029ddc  jz      loc_14002A16E
0x140029de2  test    r13d, r13d
0x140029de5  jz      loc_14002A2B6
0x140029deb  call    cs:__imp_W32GetUserSessionState
0x140029df2  nop     dword ptr [rax+rax+00h]
0x140029df7  add     rax, 11950h
0x140029dfd  mov     [rsp+168h+var_130], 6C706147h
0x140029e05  mov     [rsp+168h+var_120], 100h
0x140029e0e  mov     ecx, r13d
0x140029e11  mov     [rsp+168h+Buffer], rcx
0x140029e16  mov     r13, rax
0x140029e19  mov     eax, [rax]
0x140029e1b  test    eax, eax
0x140029e1d  jnz     loc_14002A35C
0x140029e23  mov     r8d, 6C706147h
0x140029e29  mov     rdx, rcx
0x140029e2c  mov     ecx, 100h
0x140029e31  call    cs:__imp_ExAllocatePool2
0x140029e38  nop     dword ptr [rax+rax+00h]
0x140029e3d  mov     rcx, rax
0x140029e40  test    rax, rax
0x140029e43  jz      short loc_140029E4A
0x140029e45  lock inc qword ptr [r13+70h]
0x140029e4a  xor     r13d, r13d
0x140029e4d  mov     rax, [r14]
0x140029e50  mov     [rax+80h], rcx
0x140029e57  mov     rcx, [r14]
0x140029e5a  cmp     qword ptr [rcx+80h], 0
0x140029e62  jz      loc_14002A5C3
0x140029e68  mov     r10, [rsp+168h+var_140]
0x140029e6d  mov     [rsp+168h+var_120], r10
0x140029e72  mov     r9d, 1
0x140029e78  mov     eax, r12d
0x140029e7b  or      eax, r15d
0x140029e7e  mov     [rcx+18h], eax
0x140029e81  mov     rax, [r14]
0x140029e84  mov     edx, [rsp+168h+arg_10]
0x140029e8b  mov     [rax+1Ch], edx
0x140029e8e  mov     ecx, r9d
0x140029e91  lock xadd [r10+0EC0h], ecx
0x140029e9a  inc     ecx
0x140029e9c  mov     rax, [r14]
0x140029e9f  mov     [rax+20h], ecx
0x140029ea2  mov     rax, [r14]
0x140029ea5  mov     [rax+28h], r13
0x140029ea9  mov     rax, [r14]
0x140029eac  mov     [rax+30h], r13
0x140029eb0  mov     rax, [r14]
0x140029eb3  mov     [rax+3Ch], r13d
0x140029eb7  mov     rax, [r14]
0x140029eba  mov     [rax+38h], r13d
0x140029ebe  mov     rax, [r14]
0x140029ec1  mov     [rax+48h], r13
0x140029ec5  mov     rax, [r14]
0x140029ec8  mov     [rax+50h], r13
0x140029ecc  mov     rax, [r14]
0x140029ecf  mov     [rax+58h], r13
0x140029ed3  mov     rax, [r14]
0x140029ed6  mov     [rax+24h], r13d
0x140029eda  mov     rax, [r14]
0x140029edd  mov     [rax+68h], r13
0x140029ee1  mov     rax, [r14]
0x140029ee4  mov     [rax+78h], rax
0x140029ee8  mov     rcx, [r14]
0x140029eeb  mov     rax, [rcx+80h]
0x140029ef2  mov     [rcx+70h], rax
0x140029ef6  cmp     r12d, 8
0x140029efa  jnz     loc_14002A2E3
0x140029f00  mov     rax, [r14]
0x140029f03  mov     rcx, [rax+70h]
0x140029f07  mov     [rcx], ebx
0x140029f09  mov     rax, [r14]
0x140029f0c  mov     rcx, [rax+70h]
0x140029f10  mov     [rcx+4], esi
0x140029f13  mov     rax, [r14]
0x140029f16  mov     rcx, [rax+70h]
0x140029f1a  mov     [rcx+8], edi
0x140029f1d  cmp     ebx, 0FFh
0x140029f23  jz      loc_14002A5EB
0x140029f29  cmp     ebx, 0F800h
0x140029f2f  jz      loc_14002A495
0x140029f35  cmp     ebx, 7C00h
0x140029f3b  jz      loc_14002A404
0x140029f41  mov     rax, [r14]
0x140029f44  mov     r8, [rax+70h]
0x140029f48  mov     ecx, r13d
0x140029f4b  test    r9b, bl
0x140029f4e  jnz     short loc_140029F59
0x140029f50  shr     ebx, 1
0x140029f52  inc     ecx
0x140029f54  test    r9b, bl
0x140029f57  jz      short loc_140029F50
0x140029f59  mov     eax, ecx
0x140029f5b  nop     dword ptr [rax+rax+00h]
0x140029f60  shr     ebx, 1
0x140029f62  inc     eax
0x140029f64  test    r9b, bl
0x140029f67  jnz     short loc_140029F60
0x140029f69  mov     edx, eax
0x140029f6b  sub     edx, ecx
0x140029f6d  mov     [r8+24h], edx
0x140029f71  add     eax, 0FFFFFFF8h
0x140029f74  cmp     edx, 8
0x140029f77  cmovbe  eax, ecx
0x140029f7a  mov     [r8+18h], eax
0x140029f7e  mov     r9d, 8
0x140029f84  ja      loc_14002A48D
0x140029f8a  mov     eax, r9d
0x140029f8d  sub     eax, edx
0x140029f8f  mov     [r8+0Ch], eax
0x140029f93  mov     rax, [r14]
0x140029f96  mov     r10, [rax+70h]
0x140029f9a  mov     ecx, r13d
0x140029f9d  test    sil, 1
0x140029fa1  jnz     short loc_140029FAD
0x140029fa3  shr     esi, 1
0x140029fa5  inc     ecx
0x140029fa7  test    sil, 1
0x140029fab  jz      short loc_140029FA3
0x140029fad  mov     eax, ecx
0x140029faf  nop
0x140029fb0  shr     esi, 1
0x140029fb2  inc     eax
0x140029fb4  test    sil, 1
0x140029fb8  jnz     short loc_140029FB0
0x140029fba  mov     edx, eax
0x140029fbc  sub     edx, ecx
0x140029fbe  mov     [r10+28h], edx
0x140029fc2  add     eax, 0FFFFFFF8h
0x140029fc5  cmp     edx, 8
0x140029fc8  cmovbe  eax, ecx
0x140029fcb  mov     [r10+1Ch], eax
0x140029fcf  mov     r8d, 10h
0x140029fd5  ja      short loc_140029FDD
0x140029fd7  mov     r9d, r8d
0x140029fda  sub     r9d, edx
0x140029fdd  mov     [r10+10h], r9d
0x140029fe1  mov     rax, [r14]
0x140029fe4  mov     r9, [rax+70h]
0x140029fe8  mov     ecx, r13d
0x140029feb  test    dil, 1
0x140029fef  jnz     short loc_140029FFB
0x140029ff1  shr     edi, 1
0x140029ff3  inc     ecx
0x140029ff5  test    dil, 1
0x140029ff9  jz      short loc_140029FF1
0x140029ffb  mov     eax, ecx
0x140029ffd  nop     dword ptr [rax]
0x14002a000  shr     edi, 1
0x14002a002  inc     eax
0x14002a004  test    dil, 1
0x14002a008  jnz     short loc_14002A000
0x14002a00a  mov     edx, eax
0x14002a00c  sub     edx, ecx
0x14002a00e  mov     [r9+2Ch], edx
0x14002a012  add     eax, 0FFFFFFF8h
0x14002a015  cmp     edx, 8
0x14002a018  cmovbe  eax, ecx
0x14002a01b  mov     [r9+20h], eax
0x14002a01f  ja      short loc_14002A02A
0x14002a021  mov     r8d, 18h
0x14002a027  sub     r8d, edx
0x14002a02a  mov     [r9+14h], r8d
0x14002a02e  mov     rsi, [rsp+168h+var_140]
0x14002a033  mov     r9d, 1
0x14002a039  mov     r8d, 4
0x14002a03f  mov     rax, [r14]
0x14002a042  cmp     dword ptr [rax+1Ch], 0
0x14002a046  jnz     loc_14002A2C1
0x14002a04c  mov     ecx, [rax+18h]
0x14002a04f  test    cl, 2
0x14002a052  jnz     loc_14002A175
0x14002a058  test    cl, 8
0x14002a05b  jz      loc_14002A60F
0x14002a061  mov     r8d, 6
0x14002a067  mov     edi, 3
0x14002a06c  mov     ecx, r8d
0x14002a06f  mov     [rax+64h], r8d
0x14002a073  mov     rax, [r14]
0x14002a076  mov     [rax+60h], ecx
0x14002a079  test    r9d, r9d
0x14002a07c  jz      short loc_14002A0F8
0x14002a07e  lea     rcx, [rsp+168h+var_108]; this
0x14002a083  call    ??0HmgInsertObjectHelper@@QEAA@XZ; HmgInsertObjectHelper::HmgInsertObjectHelper(void)
0x14002a088  mov     rax, r13
0x14002a08b  cmp     [rsp+168h+var_E8], 0
0x14002a094  jnz     short loc_14002A0C6
0x14002a096  mov     rbx, [r14]
0x14002a099  mov     r8d, 0Bh
0x14002a09f  cmp     [rsp+168h+arg_40], 0
0x14002a0a7  cmovz   r8d, edi; unsigned int
0x14002a0ab  mov     r9b, 8; unsigned __int8
0x14002a0ae  mov     rdx, rbx; struct OBJECT *
0x14002a0b1  mov     rcx, rsi; struct Gre::Base::SESSION_GLOBALS *
0x14002a0b4  call    ?HmgInsertObjectInternal@@YAPEAUHOBJ__@@AEAUSESSION_GLOBALS@Base@Gre@@PEAXKE@Z; HmgInsertObjectInternal(Gre::Base::SESSION_GLOBALS &,void *,ulong,uchar)
0x14002a0b9  test    rax, rax
0x14002a0bc  jz      short loc_14002A0EE
0x14002a0be  mov     [rsp+168h+var_E8], rbx
0x14002a0c6  test    rax, rax
0x14002a0c9  jz      short loc_14002A0EE
0x14002a0cb  lea     rcx, [rsp+168h+var_108]; this
0x14002a0d0  call    ??1HmgInsertObjectHelper@@QEAA@XZ; HmgInsertObjectHelper::~HmgInsertObjectHelper(void)
0x14002a0d5  mov     eax, 1
0x14002a0da  add     rsp, 130h
0x14002a0e1  pop     r15
0x14002a0e3  pop     r14
0x14002a0e5  pop     r13
0x14002a0e7  pop     r12
0x14002a0e9  pop     rdi
0x14002a0ea  pop     rsi
0x14002a0eb  pop     rbx
0x14002a0ec  retn
0x14002a0ee  lea     rcx, [rsp+168h+var_108]; this
0x14002a0f3  call    ??1HmgInsertObjectHelper@@QEAA@XZ; HmgInsertObjectHelper::~HmgInsertObjectHelper(void)
0x14002a0f8  mov     rax, [r14]
0x14002a0fb  mov     rcx, [rax+80h]; Buffer
0x14002a102  test    rcx, rcx
0x14002a105  jz      short loc_14002A10C
0x14002a107  call    GreDeleteFastMutex
0x14002a10c  mov     rbx, [r14]
0x14002a10f  call    cs:__imp_W32GetSessionState
0x14002a116  nop     dword ptr [rax+rax+00h]
0x14002a11b  mov     rcx, [rax+58h]
0x14002a11f  mov     rax, [rcx+1120h]
0x14002a126  mov     rcx, [rax+8]
0x14002a12a  test    rcx, rcx
0x14002a12d  jz      short loc_14002A16B
0x14002a12f  xorps   xmm0, xmm0
0x14002a132  movups  xmmword ptr [rbx], xmm0
0x14002a135  movups  xmmword ptr [rbx+10h], xmm0
0x14002a139  movups  xmmword ptr [rbx+20h], xmm0
0x14002a13d  movups  xmmword ptr [rbx+30h], xmm0
0x14002a141  movups  xmmword ptr [rbx+40h], xmm0
0x14002a145  movups  xmmword ptr [rbx+50h], xmm0
0x14002a149  movups  xmmword ptr [rbx+60h], xmm0
0x14002a14d  movups  xmmword ptr [rbx+70h], xmm0
0x14002a151  movups  xmmword ptr [rbx+80h], xmm0
0x14002a158  add     rcx, 30h ; '0'; Lookaside
0x14002a15c  mov     rdx, rbx; Entry
0x14002a15f  call    cs:__imp_ExFreeToLookasideListEx
0x14002a166  nop     dword ptr [rax+rax+00h]
0x14002a16b  mov     [r14], r13
0x14002a16e  xor     eax, eax
0x14002a170  jmp     loc_14002A0DA
  ... truncated ...
```
