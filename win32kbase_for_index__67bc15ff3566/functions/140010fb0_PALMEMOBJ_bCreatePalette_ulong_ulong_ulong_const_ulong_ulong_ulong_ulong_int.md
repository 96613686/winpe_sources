# PALMEMOBJ::bCreatePalette(ulong,ulong,ulong const *,ulong,ulong,ulong,ulong,int)

- ea: `0x140010fb0`
- end: `0x140011900`
- name: `?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z`
- size: `2384`
- prototype: `__int64 __fastcall(PALMEMOBJ *__hidden this, unsigned int, unsigned int, const unsigned int *, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `6`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140010eb0`
- `0x14010dcbc`
- `0x140177800`
- `0x1401b18f0`
- `0x1401e5b88`
- `0x1402d9008`

## callees

- `0x14000988c`
- `0x14000b798`
- `0x14000c064`
- `0x140010fb0`
- `0x140011908`
- `0x14001194c`
- `0x1400119f0`
- `0x14007b930`
- `0x14007bbc0`
- `0x14007cc00`
- `0x1401ade20`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140011111`
- `ntoskrnl!ExAllocatePool2` at `0x1400114f7`
- `ntoskrnl!ExAllocatePool2` at `0x14001167a`
- `ntoskrnl!ExAllocatePool2` at `0x140011111`
- `ntoskrnl!ExAllocatePool2` at `0x1400114f7`
- `ntoskrnl!ExAllocatePool2` at `0x14001167a`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140011545`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140011545`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001143f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001143f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400110aa`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400110aa`
- `WIN32K!W32GetSessionState` at `0x140010fda`
- `WIN32K!W32GetSessionState` at `0x140011082`
- `WIN32K!W32GetSessionState` at `0x1400113ef`
- `WIN32K!W32GetSessionState` at `0x140010fda`
- `WIN32K!W32GetSessionState` at `0x140011082`
- `WIN32K!W32GetSessionState` at `0x1400113ef`
- `WIN32K!W32GetUserSessionState` at `0x1400110cb`
- `WIN32K!W32GetUserSessionState` at `0x1400110cb`

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
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  struct OBJECT *v21; // rax
  __int64 UserSessionState; // rax
  unsigned __int64 v23; // rcx
  __int64 v24; // r13
  int v25; // eax
  __int64 Pool2; // rcx
  _DWORD *v27; // r8
  int k; // ecx
  int v29; // eax
  unsigned int v30; // edx
  int v31; // eax
  int v32; // r9d
  unsigned int v33; // eax
  _DWORD *v34; // r10
  int m; // ecx
  int v36; // eax
  unsigned int v37; // edx
  int v38; // eax
  int v39; // r8d
  _DWORD *v40; // r9
  int n; // ecx
  int v42; // eax
  unsigned int v43; // edx
  int v44; // eax
  struct Gre::Base::SESSION_GLOBALS *v45; // rsi
  int v46; // r8d
  struct OBJECT *v47; // rax
  int v48; // ecx
  int v49; // ecx
  struct HOBJ__ *inserted; // rax
  struct OBJECT *v51; // rbx
  unsigned int v52; // r8d
  void *v54; // rcx
  struct OBJECT *v55; // rbx
  __int64 v56; // rcx
  _DWORD *v57; // rdx
  int v58; // r12d
  _DWORD *v59; // rcx
  const unsigned int *v60; // r9
  _QWORD *v61; // rax
  unsigned int j; // r8d
  int v63; // eax
  unsigned __int64 i; // rax
  int v65; // r12d
  unsigned __int64 Buffer; // [rsp+20h] [rbp-148h]
  __int64 Buffera; // [rsp+20h] [rbp-148h]
  PVOID Bufferb; // [rsp+20h] [rbp-148h]
  struct Gre::Base::SESSION_GLOBALS *v69; // [rsp+28h] [rbp-140h]
  unsigned __int64 v70; // [rsp+30h] [rbp-138h]
  _BYTE v72[32]; // [rsp+60h] [rbp-108h] BYREF
  struct OBJECT *v73; // [rsp+80h] [rbp-E8h]
  PVOID BackTrace[27]; // [rsp+90h] [rbp-D8h] BYREF
  char v75; // [rsp+178h] [rbp+10h]
  unsigned int v76; // [rsp+180h] [rbp+18h]

  v76 = a3;
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
      v76 = 0;
      v13 = 52;
      goto LABEL_9;
    }
    if ( a2 != 4 && a2 != 8 )
      return 0;
  }
  v13 = 4;
  v14 = a8 & 0x3100100 | 0x200;
  v76 = 0;
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
  v69 = *(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88);
  v19 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetSessionState(v69) + 88) + 4384LL) + 8LL);
  if ( v19 )
    v21 = (struct OBJECT *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v19 + 48));
  else
    v21 = 0;
  *this = v21;
  if ( !v21 )
    return 0;
  if ( !v13 )
    goto LABEL_80;
  UserSessionState = W32GetUserSessionState(v19, v18, v20);
  v23 = v13;
  Buffer = v13;
  v24 = UserSessionState + 72016;
  v25 = *(_DWORD *)(UserSessionState + 72016);
  if ( !v25 )
    goto LABEL_14;
  if ( v25 != 1 )
  {
    if ( v25 == 2 )
    {
      if ( (*(_DWORD *)(v24 + 80) & 0x6C706147) != 0x6C706147 )
      {
LABEL_14:
        Pool2 = ExAllocatePool2(256, v23, 1819304263);
        if ( Pool2 )
          _InterlockedIncrement64((volatile signed __int64 *)(v24 + 112));
        goto LABEL_16;
      }
      for ( i = 0; ; ++i )
      {
        v70 = i;
        if ( i >= *(unsigned int *)(v24 + 84) )
          goto LABEL_14;
        if ( *(_DWORD *)(v24 + 4 * i + 48) == 1819304263 )
          break;
      }
      if ( v23 < 0x1000 || (v75 = 0, (v23 & 0xFFF) != 0) )
      {
        v75 = 1;
        v23 += 16LL;
      }
      Buffera = ExAllocatePool2(256, v23, 1819304263);
      if ( Buffera )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v24 + 128));
        memset(BackTrace, 0, 0xA0u);
        RtlCaptureStackBackTrace(0, 0x14u, BackTrace, 0);
        if ( v75 && (unsigned __int64)(Buffera & 0xFFF) + 16 < 0x1000 )
        {
          if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(
                                  v24,
                                  Buffera,
                                  v70,
                                  BackTrace) )
          {
            Pool2 = Buffera + 16;
            goto LABEL_16;
          }
        }
        else if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(
                                     v24,
                                     Buffera,
                                     v70,
                                     BackTrace) )
        {
          Pool2 = Buffera;
          goto LABEL_16;
        }
        _InterlockedIncrement64((volatile signed __int64 *)(v24 + 136));
        _lambda_2af9a864ca5eb776d3057466a2e51944_::_lambda_invoker_cdecl_<void *>((PVOID)Buffera);
        goto LABEL_80;
      }
    }
    goto LABEL_80;
  }
  if ( !NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(
          (NSInstrumentation::CLeakTrackingAllocator *)v24,
          0x6C706147u)
    || Buffer + 16 < Buffer )
  {
LABEL_80:
    Pool2 = 0;
    goto LABEL_16;
  }
  v61 = (_QWORD *)ExAllocatePool2(256, Buffer + 16, 1819304263);
  if ( !v61 )
  {
    Bufferb = 0;
    goto LABEL_95;
  }
  _InterlockedIncrement64((volatile signed __int64 *)(v24 + 112));
  *v61 = 1819304263;
  Pool2 = (__int64)(v61 + 2);
  Bufferb = v61 + 2;
  if ( v61 == (_QWORD *)-16LL )
  {
LABEL_95:
    NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(
      *(NSInstrumentation::CPointerHashTable **)(v24 + 8),
      (const void *)0x6C706147);
    Pool2 = (__int64)Bufferb;
  }
LABEL_16:
  *((_QWORD *)*this + 16) = Pool2;
  if ( *((_QWORD *)*this + 16) )
  {
    *((_DWORD *)*this + 6) = v14 | a2;
    *((_DWORD *)*this + 7) = v76;
    *((_DWORD *)*this + 8) = _InterlockedIncrement((volatile signed __int32 *)v69 + 944);
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
      v58 = a2 - 1;
      if ( !v58 )
      {
        v59 = (_DWORD *)*((_QWORD *)*this + 14);
        v60 = a4;
        if ( a4 )
        {
          for ( j = 0; j < v76; ++j )
          {
            v63 = *v60++;
            *v59++ = v63;
          }
          v46 = 4;
          v45 = v69;
LABEL_48:
          v47 = *this;
          if ( *((_DWORD *)*this + 7) )
          {
            v49 = 2;
            v46 = 1;
LABEL_53:
            *((_DWORD *)v47 + 25) = v46;
            *((_DWORD *)*this + 24) = v49;
            HmgInsertObjectHelper::HmgInsertObjectHelper((HmgInsertObjectHelper *)v72);
            inserted = 0;
            if ( !v73 )
            {
              v51 = *this;
              v52 = 11;
              if ( !a9 )
                v52 = 3;
              inserted = HmgInsertObjectInternal(v45, *this, v52, 8u);
              if ( !inserted )
              {
LABEL_60:
                HmgInsertObjectHelper::~HmgInsertObjectHelper((HmgInsertObjectHelper *)v72);
                v54 = (void *)*((_QWORD *)*this + 16);
                if ( v54 )
                  GreDeleteFastMutex(v54);
                v55 = *this;
                v56 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetSessionState(v54) + 88) + 4384LL) + 8LL);
                if ( v56 )
                {
                  *(_OWORD *)v55 = 0;
                  *((_OWORD *)v55 + 1) = 0;
                  *((_OWORD *)v55 + 2) = 0;
                  *((_OWORD *)v55 + 3) = 0;
                  *((_OWORD *)v55 + 4) = 0;
                  *((_OWORD *)v55 + 5) = 0;
                  *((_OWORD *)v55 + 6) = 0;
                  *((_OWORD *)v55 + 7) = 0;
                  *((_OWORD *)v55 + 8) = 0;
                  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v56 + 48), v55);
                }
                *this = 0;
                return 0;
              }
              v73 = v51;
            }
            if ( inserted )
            {
              HmgInsertObjectHelper::~HmgInsertObjectHelper((HmgInsertObjectHelper *)v72);
              return 1;
            }
            goto LABEL_60;
          }
          v48 = *((_DWORD *)v47 + 6);
          if ( (v48 & 2) == 0 )
          {
            if ( (v48 & 8) != 0 )
              v46 = 6;
            else
              v46 = 8 - ((v48 & 0x10) != 0);
            goto LABEL_52;
          }
          v57 = (_DWORD *)*((_QWORD *)v47 + 14);
          if ( v57[2] == 31 )
          {
            if ( v57[1] == 2016 && *v57 == 63488 )
            {
              v46 = 3;
              goto LABEL_52;
            }
            if ( v57[1] == 992 && *v57 == 31744 )
              goto LABEL_52;
          }
          v46 = 5;
LABEL_52:
          v49 = v46;
          goto LABEL_53;
        }
        if ( !v76 )
        {
          v45 = v69;
          goto LABEL_47;
        }
        memset(v59, 0, 4LL * v76);
LABEL_46:
        v45 = v69;
LABEL_47:
        v46 = 4;
        goto LABEL_48;
      }
      v65 = v58 - 1;
      if ( v65 && v65 != 2 )
      {
        v45 = v69;
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
    v27 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( k = 0; (v15 & 1) == 0; ++k )
      v15 >>= 1;
    v29 = k;
    do
    {
      v15 >>= 1;
      ++v29;
    }
    while ( (v15 & 1) != 0 );
    v30 = v29 - k;
    v27[9] = v29 - k;
    v31 = v29 - 8;
    if ( v30 <= 8 )
      v31 = k;
    v27[6] = v31;
    v32 = 8;
    if ( v30 > 8 )
      v33 = 0;
    else
      v33 = 8 - v30;
    v27[3] = v33;
    v34 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( m = 0; (v16 & 1) == 0; ++m )
      v16 >>= 1;
    v36 = m;
    do
    {
      v16 >>= 1;
      ++v36;
    }
    while ( (v16 & 1) != 0 );
    v37 = v36 - m;
    v34[10] = v36 - m;
    v38 = v36 - 8;
    if ( v37 <= 8 )
      v38 = m;
    v34[7] = v38;
    v39 = 16;
    if ( v37 <= 8 )
      v32 = 16 - v37;
    v34[4] = v32;
    v40 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( n = 0; (v17 & 1) == 0; ++n )
      v17 >>= 1;
    v42 = n;
    do
    {
      v17 >>= 1;
      ++v42;
    }
    while ( (v17 & 1) != 0 );
    v43 = v42 - n;
    v40[11] = v42 - n;
    v44 = v42 - 8;
    if ( v43 <= 8 )
      v44 = n;
    v40[8] = v44;
    if ( v43 <= 8 )
      v39 = 24 - v43;
    v40[5] = v39;
    goto LABEL_46;
  }
  XEPALOBJ_FreePaletteMemory(this);
  return 0;
}

```

## disassembly

```asm
0x140010fb0  mov     [rsp+arg_10], r8d
0x140010fb5  mov     [rsp+arg_0], rcx
0x140010fba  push    rbx
0x140010fbb  push    rsi
0x140010fbc  push    rdi
0x140010fbd  push    r12
0x140010fbf  push    r13
0x140010fc1  push    r14
0x140010fc3  push    r15
0x140010fc5  sub     rsp, 130h
0x140010fcc  mov     [rsp+168h+var_118], r9
0x140010fd1  mov     ebx, r8d
0x140010fd4  mov     r12d, edx
0x140010fd7  mov     r14, rcx
0x140010fda  call    cs:__imp_W32GetSessionState
0x140010fe1  nop     dword ptr [rax+rax+00h]
0x140010fe6  cmp     r12d, 10h
0x140010fea  jnz     loc_140011470
0x140010ff0  mov     r13d, 4
0x140010ff6  mov     r15d, [rsp+168h+arg_38]
0x140010ffe  and     r15d, 3100100h
0x140011005  bts     r15d, 9
0x14001100a  mov     [rsp+168h+arg_10], 0
0x140011015  cmp     r12d, 10h
0x140011019  jz      short loc_140011064
0x14001101b  cmp     r12d, r13d
0x14001101e  jz      loc_140011622
0x140011024  cmp     r12d, 8
0x140011028  jnz     loc_140011867
0x14001102e  mov     ebx, 0FF0000h
0x140011033  mov     esi, 0FF00h
0x140011038  mov     edi, 0FFh
0x14001103d  mov     r13d, 34h ; '4'
0x140011043  jmp     short loc_140011079
0x140011045  lea     r13d, ds:4[rbx*4]
0x14001104d  test    ebx, ebx
0x14001104f  jz      loc_14001144E
0x140011055  mov     r15d, [rsp+168h+arg_38]
0x14001105d  and     r15d, 3102F00h
0x140011064  mov     ebx, [rsp+168h+arg_20]
0x14001106b  mov     esi, [rsp+168h+arg_28]
0x140011072  mov     edi, [rsp+168h+arg_30]
0x140011079  mov     rcx, [rax+58h]
0x14001107d  mov     [rsp+168h+var_140], rcx
0x140011082  call    cs:__imp_W32GetSessionState
0x140011089  nop     dword ptr [rax+rax+00h]
0x14001108e  mov     rcx, [rax+58h]
0x140011092  mov     rax, [rcx+1120h]
0x140011099  mov     rcx, [rax+8]
0x14001109d  test    rcx, rcx
0x1400110a0  jz      loc_140011881
0x1400110a6  add     rcx, 30h ; '0'; Lookaside
0x1400110aa  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400110b1  nop     dword ptr [rax+rax+00h]
0x1400110b6  mov     [r14], rax
0x1400110b9  test    rax, rax
0x1400110bc  jz      loc_14001144E
0x1400110c2  test    r13d, r13d
0x1400110c5  jz      loc_140011596
0x1400110cb  call    cs:__imp_W32GetUserSessionState
0x1400110d2  nop     dword ptr [rax+rax+00h]
0x1400110d7  add     rax, 11950h
0x1400110dd  mov     [rsp+168h+var_130], 6C706147h
0x1400110e5  mov     [rsp+168h+var_120], 100h
0x1400110ee  mov     ecx, r13d
0x1400110f1  mov     [rsp+168h+Buffer], rcx
0x1400110f6  mov     r13, rax
0x1400110f9  mov     eax, [rax]
0x1400110fb  test    eax, eax
0x1400110fd  jnz     loc_14001163C
0x140011103  mov     r8d, 6C706147h
0x140011109  mov     rdx, rcx
0x14001110c  mov     ecx, 100h
0x140011111  call    cs:__imp_ExAllocatePool2
0x140011118  nop     dword ptr [rax+rax+00h]
0x14001111d  mov     rcx, rax
0x140011120  test    rax, rax
0x140011123  jz      short loc_14001112A
0x140011125  lock inc qword ptr [r13+70h]
0x14001112a  xor     r13d, r13d
0x14001112d  mov     rax, [r14]
0x140011130  mov     [rax+80h], rcx
0x140011137  mov     rcx, [r14]
0x14001113a  cmp     qword ptr [rcx+80h], 0
0x140011142  jz      loc_1400118A3
0x140011148  mov     r10, [rsp+168h+var_140]
0x14001114d  mov     [rsp+168h+var_120], r10
0x140011152  mov     r9d, 1
0x140011158  mov     eax, r12d
0x14001115b  or      eax, r15d
0x14001115e  mov     [rcx+18h], eax
0x140011161  mov     rax, [r14]
0x140011164  mov     edx, [rsp+168h+arg_10]
0x14001116b  mov     [rax+1Ch], edx
0x14001116e  mov     ecx, r9d
0x140011171  lock xadd [r10+0EC0h], ecx
0x14001117a  inc     ecx
0x14001117c  mov     rax, [r14]
0x14001117f  mov     [rax+20h], ecx
0x140011182  mov     rax, [r14]
0x140011185  mov     [rax+28h], r13
0x140011189  mov     rax, [r14]
0x14001118c  mov     [rax+30h], r13
0x140011190  mov     rax, [r14]
0x140011193  mov     [rax+3Ch], r13d
0x140011197  mov     rax, [r14]
0x14001119a  mov     [rax+38h], r13d
0x14001119e  mov     rax, [r14]
0x1400111a1  mov     [rax+48h], r13
0x1400111a5  mov     rax, [r14]
0x1400111a8  mov     [rax+50h], r13
0x1400111ac  mov     rax, [r14]
0x1400111af  mov     [rax+58h], r13
0x1400111b3  mov     rax, [r14]
0x1400111b6  mov     [rax+24h], r13d
0x1400111ba  mov     rax, [r14]
0x1400111bd  mov     [rax+68h], r13
0x1400111c1  mov     rax, [r14]
0x1400111c4  mov     [rax+78h], rax
0x1400111c8  mov     rcx, [r14]
0x1400111cb  mov     rax, [rcx+80h]
0x1400111d2  mov     [rcx+70h], rax
0x1400111d6  cmp     r12d, 8
0x1400111da  jnz     loc_1400115C3
0x1400111e0  mov     rax, [r14]
0x1400111e3  mov     rcx, [rax+70h]
0x1400111e7  mov     [rcx], ebx
0x1400111e9  mov     rax, [r14]
0x1400111ec  mov     rcx, [rax+70h]
0x1400111f0  mov     [rcx+4], esi
0x1400111f3  mov     rax, [r14]
0x1400111f6  mov     rcx, [rax+70h]
0x1400111fa  mov     [rcx+8], edi
0x1400111fd  cmp     ebx, 0FFh
0x140011203  jz      loc_1400118CB
0x140011209  cmp     ebx, 0F800h
0x14001120f  jz      loc_140011775
0x140011215  cmp     ebx, 7C00h
0x14001121b  jz      loc_1400116E4
0x140011221  mov     rax, [r14]
0x140011224  mov     r8, [rax+70h]
0x140011228  mov     ecx, r13d
0x14001122b  test    r9b, bl
0x14001122e  jnz     short loc_140011239
0x140011230  shr     ebx, 1
0x140011232  inc     ecx
0x140011234  test    r9b, bl
0x140011237  jz      short loc_140011230
0x140011239  mov     eax, ecx
0x14001123b  nop     dword ptr [rax+rax+00h]
0x140011240  shr     ebx, 1
0x140011242  inc     eax
0x140011244  test    r9b, bl
0x140011247  jnz     short loc_140011240
0x140011249  mov     edx, eax
0x14001124b  sub     edx, ecx
0x14001124d  mov     [r8+24h], edx
0x140011251  add     eax, 0FFFFFFF8h
0x140011254  cmp     edx, 8
0x140011257  cmovbe  eax, ecx
0x14001125a  mov     [r8+18h], eax
0x14001125e  mov     r9d, 8
0x140011264  ja      loc_14001176D
0x14001126a  mov     eax, r9d
0x14001126d  sub     eax, edx
0x14001126f  mov     [r8+0Ch], eax
0x140011273  mov     rax, [r14]
0x140011276  mov     r10, [rax+70h]
0x14001127a  mov     ecx, r13d
0x14001127d  test    sil, 1
0x140011281  jnz     short loc_14001128D
0x140011283  shr     esi, 1
0x140011285  inc     ecx
0x140011287  test    sil, 1
0x14001128b  jz      short loc_140011283
0x14001128d  mov     eax, ecx
0x14001128f  nop
0x140011290  shr     esi, 1
0x140011292  inc     eax
0x140011294  test    sil, 1
0x140011298  jnz     short loc_140011290
0x14001129a  mov     edx, eax
0x14001129c  sub     edx, ecx
0x14001129e  mov     [r10+28h], edx
0x1400112a2  add     eax, 0FFFFFFF8h
0x1400112a5  cmp     edx, 8
0x1400112a8  cmovbe  eax, ecx
0x1400112ab  mov     [r10+1Ch], eax
0x1400112af  mov     r8d, 10h
0x1400112b5  ja      short loc_1400112BD
0x1400112b7  mov     r9d, r8d
0x1400112ba  sub     r9d, edx
0x1400112bd  mov     [r10+10h], r9d
0x1400112c1  mov     rax, [r14]
0x1400112c4  mov     r9, [rax+70h]
0x1400112c8  mov     ecx, r13d
0x1400112cb  test    dil, 1
0x1400112cf  jnz     short loc_1400112DB
0x1400112d1  shr     edi, 1
0x1400112d3  inc     ecx
0x1400112d5  test    dil, 1
0x1400112d9  jz      short loc_1400112D1
0x1400112db  mov     eax, ecx
0x1400112dd  nop     dword ptr [rax]
0x1400112e0  shr     edi, 1
0x1400112e2  inc     eax
0x1400112e4  test    dil, 1
0x1400112e8  jnz     short loc_1400112E0
0x1400112ea  mov     edx, eax
0x1400112ec  sub     edx, ecx
0x1400112ee  mov     [r9+2Ch], edx
0x1400112f2  add     eax, 0FFFFFFF8h
0x1400112f5  cmp     edx, 8
0x1400112f8  cmovbe  eax, ecx
0x1400112fb  mov     [r9+20h], eax
0x1400112ff  ja      short loc_14001130A
0x140011301  mov     r8d, 18h
0x140011307  sub     r8d, edx
0x14001130a  mov     [r9+14h], r8d
0x14001130e  mov     rsi, [rsp+168h+var_140]
0x140011313  mov     r9d, 1
0x140011319  mov     r8d, 4
0x14001131f  mov     rax, [r14]
0x140011322  cmp     dword ptr [rax+1Ch], 0
0x140011326  jnz     loc_1400115A1
0x14001132c  mov     ecx, [rax+18h]
0x14001132f  test    cl, 2
0x140011332  jnz     loc_140011455
0x140011338  test    cl, 8
0x14001133b  jz      loc_1400118EF
0x140011341  mov     r8d, 6
0x140011347  mov     edi, 3
0x14001134c  mov     ecx, r8d
0x14001134f  mov     [rax+64h], r8d
0x140011353  mov     rax, [r14]
0x140011356  mov     [rax+60h], ecx
0x140011359  test    r9d, r9d
0x14001135c  jz      short loc_1400113D8
0x14001135e  lea     rcx, [rsp+168h+var_108]; this
0x140011363  call    ??0HmgInsertObjectHelper@@QEAA@XZ; HmgInsertObjectHelper::HmgInsertObjectHelper(void)
0x140011368  mov     rax, r13
0x14001136b  cmp     [rsp+168h+var_E8], 0
0x140011374  jnz     short loc_1400113A6
0x140011376  mov     rbx, [r14]
0x140011379  mov     r8d, 0Bh
0x14001137f  cmp     [rsp+168h+arg_40], 0
0x140011387  cmovz   r8d, edi; unsigned int
0x14001138b  mov     r9b, 8; unsigned __int8
0x14001138e  mov     rdx, rbx; struct OBJECT *
0x140011391  mov     rcx, rsi; struct Gre::Base::SESSION_GLOBALS *
0x140011394  call    ?HmgInsertObjectInternal@@YAPEAUHOBJ__@@AEAUSESSION_GLOBALS@Base@Gre@@PEAXKE@Z; HmgInsertObjectInternal(Gre::Base::SESSION_GLOBALS &,void *,ulong,uchar)
0x140011399  test    rax, rax
0x14001139c  jz      short loc_1400113CE
0x14001139e  mov     [rsp+168h+var_E8], rbx
0x1400113a6  test    rax, rax
0x1400113a9  jz      short loc_1400113CE
0x1400113ab  lea     rcx, [rsp+168h+var_108]; this
0x1400113b0  call    ??1HmgInsertObjectHelper@@QEAA@XZ; HmgInsertObjectHelper::~HmgInsertObjectHelper(void)
0x1400113b5  mov     eax, 1
0x1400113ba  add     rsp, 130h
0x1400113c1  pop     r15
0x1400113c3  pop     r14
0x1400113c5  pop     r13
0x1400113c7  pop     r12
0x1400113c9  pop     rdi
0x1400113ca  pop     rsi
0x1400113cb  pop     rbx
0x1400113cc  retn
0x1400113ce  lea     rcx, [rsp+168h+var_108]; this
0x1400113d3  call    ??1HmgInsertObjectHelper@@QEAA@XZ; HmgInsertObjectHelper::~HmgInsertObjectHelper(void)
0x1400113d8  mov     rax, [r14]
0x1400113db  mov     rcx, [rax+80h]; Buffer
0x1400113e2  test    rcx, rcx
0x1400113e5  jz      short loc_1400113EC
0x1400113e7  call    GreDeleteFastMutex
0x1400113ec  mov     rbx, [r14]
0x1400113ef  call    cs:__imp_W32GetSessionState
0x1400113f6  nop     dword ptr [rax+rax+00h]
0x1400113fb  mov     rcx, [rax+58h]
0x1400113ff  mov     rax, [rcx+1120h]
0x140011406  mov     rcx, [rax+8]
0x14001140a  test    rcx, rcx
0x14001140d  jz      short loc_14001144B
0x14001140f  xorps   xmm0, xmm0
0x140011412  movups  xmmword ptr [rbx], xmm0
0x140011415  movups  xmmword ptr [rbx+10h], xmm0
0x140011419  movups  xmmword ptr [rbx+20h], xmm0
0x14001141d  movups  xmmword ptr [rbx+30h], xmm0
0x140011421  movups  xmmword ptr [rbx+40h], xmm0
0x140011425  movups  xmmword ptr [rbx+50h], xmm0
0x140011429  movups  xmmword ptr [rbx+60h], xmm0
0x14001142d  movups  xmmword ptr [rbx+70h], xmm0
0x140011431  movups  xmmword ptr [rbx+80h], xmm0
0x140011438  add     rcx, 30h ; '0'; Lookaside
0x14001143c  mov     rdx, rbx; Entry
0x14001143f  call    cs:__imp_ExFreeToLookasideListEx
0x140011446  nop     dword ptr [rax+rax+00h]
0x14001144b  mov     [r14], r13
0x14001144e  xor     eax, eax
0x140011450  jmp     loc_1400113BA
  ... truncated ...
```
