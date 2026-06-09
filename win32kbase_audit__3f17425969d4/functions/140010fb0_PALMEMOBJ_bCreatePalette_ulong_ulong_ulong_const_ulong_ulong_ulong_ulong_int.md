# PALMEMOBJ::bCreatePalette(ulong,ulong,ulong const *,ulong,ulong,ulong,ulong,int)

- ea: `0x140010fb0`
- end: `0x140011900`
- name: `?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z`
- size: `2384`
- prototype: `__int64 __fastcall(struct OBJECT **this, __int64, __int64, const unsigned int *, unsigned int, unsigned int, unsigned int, unsigned int, int)`
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
        __int64 a2,
        __int64 a3,
        const unsigned int *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  int v9; // ebx
  int v10; // r12d
  __int64 SessionState; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // r13d
  unsigned int v17; // r15d
  unsigned int v18; // ebx
  unsigned int v19; // esi
  unsigned int v20; // edi
  __int64 v21; // rdx
  __int64 v22; // rcx
  struct OBJECT *v23; // rax
  __int64 UserSessionState; // rax
  unsigned __int64 v25; // rcx
  __int64 v26; // r13
  int v27; // eax
  __int64 Pool2; // rcx
  _DWORD *v29; // r8
  int k; // ecx
  int v31; // eax
  unsigned int v32; // edx
  int v33; // eax
  int v34; // r9d
  unsigned int v35; // eax
  _DWORD *v36; // r10
  int m; // ecx
  int v38; // eax
  unsigned int v39; // edx
  int v40; // eax
  int v41; // r8d
  _DWORD *v42; // r9
  int n; // ecx
  int v44; // eax
  unsigned int v45; // edx
  int v46; // eax
  struct Gre::Base::SESSION_GLOBALS *v47; // rsi
  int v48; // r8d
  struct OBJECT *v49; // rax
  int v50; // ecx
  int v51; // ecx
  struct HOBJ__ *inserted; // rax
  struct OBJECT *v53; // rbx
  unsigned int v54; // r8d
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  void *v59; // rcx
  struct OBJECT *v60; // rbx
  __int64 v61; // rcx
  _DWORD *v62; // rdx
  int v63; // r12d
  _DWORD *v64; // rcx
  const unsigned int *v65; // r9
  _QWORD *v66; // rax
  unsigned int j; // r8d
  int v68; // eax
  unsigned __int64 i; // rax
  int v70; // r12d
  unsigned __int64 Buffer; // [rsp+20h] [rbp-148h]
  __int64 Buffera; // [rsp+20h] [rbp-148h]
  PVOID Bufferb; // [rsp+20h] [rbp-148h]
  struct Gre::Base::SESSION_GLOBALS *v74; // [rsp+28h] [rbp-140h]
  __int64 v75; // [rsp+30h] [rbp-138h]
  _BYTE v77[32]; // [rsp+60h] [rbp-108h] BYREF
  struct OBJECT *v78; // [rsp+80h] [rbp-E8h]
  PVOID BackTrace[27]; // [rsp+90h] [rbp-D8h] BYREF
  char v80; // [rsp+178h] [rbp+10h]
  unsigned int v81; // [rsp+180h] [rbp+18h]

  v81 = a3;
  v9 = a3;
  v10 = a2;
  SessionState = W32GetSessionState(this, a2, a3, a4);
  if ( v10 != 16 )
  {
    if ( v10 == 1 )
    {
      v16 = 4 * v9 + 4;
      if ( !v9 )
        return 0;
      v17 = a8 & 0x3102F00;
      goto LABEL_8;
    }
    if ( v10 == 2 )
    {
      v18 = a5;
      if ( !a5 )
        return 0;
      v20 = a7;
      if ( !a7 )
        return 0;
      v19 = a6;
      if ( !a6 )
        return 0;
      v17 = a8 & 0x3100300;
      v81 = 0;
      v16 = 52;
      goto LABEL_9;
    }
    if ( v10 != 4 && v10 != 8 )
      return 0;
  }
  v16 = 4;
  v17 = a8 & 0x3100100 | 0x200;
  v81 = 0;
  if ( v10 != 16 )
  {
    if ( v10 == 4 )
    {
      v18 = 255;
      v19 = 65280;
      v20 = 16711680;
    }
    else
    {
      v18 = 16711680;
      v19 = 65280;
      v20 = 255;
    }
    v16 = 52;
    goto LABEL_9;
  }
LABEL_8:
  v18 = a5;
  v19 = a6;
  v20 = a7;
LABEL_9:
  v74 = *(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88);
  v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetSessionState(v74, v13, v14, v15) + 88) + 4384LL) + 8LL);
  if ( v22 )
    v23 = (struct OBJECT *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v22 + 48));
  else
    v23 = 0;
  *this = v23;
  if ( !v23 )
    return 0;
  if ( !v16 )
    goto LABEL_80;
  UserSessionState = W32GetUserSessionState(v22, v21);
  v25 = v16;
  Buffer = v16;
  v26 = UserSessionState + 72016;
  v27 = *(_DWORD *)(UserSessionState + 72016);
  if ( !v27 )
    goto LABEL_14;
  if ( v27 != 1 )
  {
    if ( v27 == 2 )
    {
      if ( (*(_DWORD *)(v26 + 80) & 0x6C706147) != 0x6C706147 )
      {
LABEL_14:
        Pool2 = ExAllocatePool2(256, v25, 1819304263);
        if ( Pool2 )
          _InterlockedIncrement64((volatile signed __int64 *)(v26 + 112));
        goto LABEL_16;
      }
      for ( i = 0; ; ++i )
      {
        v75 = i;
        if ( i >= *(unsigned int *)(v26 + 84) )
          goto LABEL_14;
        if ( *(_DWORD *)(v26 + 4 * i + 48) == 1819304263 )
          break;
      }
      if ( v25 < 0x1000 || (v80 = 0, (v25 & 0xFFF) != 0) )
      {
        v80 = 1;
        v25 += 16LL;
      }
      Buffera = ExAllocatePool2(256, v25, 1819304263);
      if ( Buffera )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v26 + 128));
        memset(BackTrace, 0, 0xA0u);
        RtlCaptureStackBackTrace(0, 0x14u, BackTrace, 0);
        if ( v80 && (unsigned __int64)(Buffera & 0xFFF) + 16 < 0x1000 )
        {
          if ( NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(
                 v26,
                 (const void *)Buffera,
                 v75,
                 (NSInstrumentation::CBackTrace *)BackTrace) )
          {
            Pool2 = Buffera + 16;
            goto LABEL_16;
          }
        }
        else if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(
                                     v26,
                                     Buffera,
                                     v75,
                                     BackTrace) )
        {
          Pool2 = Buffera;
          goto LABEL_16;
        }
        _InterlockedIncrement64((volatile signed __int64 *)(v26 + 136));
        _lambda_2af9a864ca5eb776d3057466a2e51944_::_lambda_invoker_cdecl_<void *>((PVOID)Buffera);
        goto LABEL_80;
      }
    }
    goto LABEL_80;
  }
  if ( !NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(
          (NSInstrumentation::CLeakTrackingAllocator *)v26,
          0x6C706147u)
    || Buffer + 16 < Buffer )
  {
LABEL_80:
    Pool2 = 0;
    goto LABEL_16;
  }
  v66 = (_QWORD *)ExAllocatePool2(256, Buffer + 16, 1819304263);
  if ( !v66 )
  {
    Bufferb = 0;
    goto LABEL_95;
  }
  _InterlockedIncrement64((volatile signed __int64 *)(v26 + 112));
  *v66 = 1819304263;
  Pool2 = (__int64)(v66 + 2);
  Bufferb = v66 + 2;
  if ( v66 == (_QWORD *)-16LL )
  {
LABEL_95:
    NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(
      *(NSInstrumentation::CPointerHashTable **)(v26 + 8),
      0x6C706147u);
    Pool2 = (__int64)Bufferb;
  }
LABEL_16:
  *((_QWORD *)*this + 16) = Pool2;
  if ( *((_QWORD *)*this + 16) )
  {
    *((_DWORD *)*this + 6) = v17 | v10;
    *((_DWORD *)*this + 7) = v81;
    *((_DWORD *)*this + 8) = _InterlockedIncrement((volatile signed __int32 *)v74 + 944);
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
    if ( v10 != 8 )
    {
      v63 = v10 - 1;
      if ( !v63 )
      {
        v64 = (_DWORD *)*((_QWORD *)*this + 14);
        v65 = a4;
        if ( a4 )
        {
          for ( j = 0; j < v81; ++j )
          {
            v68 = *v65++;
            *v64++ = v68;
          }
          v48 = 4;
          v47 = v74;
LABEL_48:
          v49 = *this;
          if ( *((_DWORD *)*this + 7) )
          {
            v51 = 2;
            v48 = 1;
LABEL_53:
            *((_DWORD *)v49 + 25) = v48;
            *((_DWORD *)*this + 24) = v51;
            HmgInsertObjectHelper::HmgInsertObjectHelper((HmgInsertObjectHelper *)v77);
            inserted = 0;
            if ( !v78 )
            {
              v53 = *this;
              v54 = 11;
              if ( !a9 )
                v54 = 3;
              inserted = HmgInsertObjectInternal(v47, *this, v54, 8u);
              if ( !inserted )
              {
LABEL_60:
                HmgInsertObjectHelper::~HmgInsertObjectHelper((HmgInsertObjectHelper *)v77);
                v59 = (void *)*((_QWORD *)*this + 16);
                if ( v59 )
                  GreDeleteFastMutex(v59);
                v60 = *this;
                v61 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetSessionState(v59, v56, v57, v58) + 88) + 4384LL) + 8LL);
                if ( v61 )
                {
                  *(_OWORD *)v60 = 0;
                  *((_OWORD *)v60 + 1) = 0;
                  *((_OWORD *)v60 + 2) = 0;
                  *((_OWORD *)v60 + 3) = 0;
                  *((_OWORD *)v60 + 4) = 0;
                  *((_OWORD *)v60 + 5) = 0;
                  *((_OWORD *)v60 + 6) = 0;
                  *((_OWORD *)v60 + 7) = 0;
                  *((_OWORD *)v60 + 8) = 0;
                  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v61 + 48), v60);
                }
                *this = 0;
                return 0;
              }
              v78 = v53;
            }
            if ( inserted )
            {
              HmgInsertObjectHelper::~HmgInsertObjectHelper((HmgInsertObjectHelper *)v77);
              return 1;
            }
            goto LABEL_60;
          }
          v50 = *((_DWORD *)v49 + 6);
          if ( (v50 & 2) == 0 )
          {
            if ( (v50 & 8) != 0 )
              v48 = 6;
            else
              v48 = 8 - ((v50 & 0x10) != 0);
            goto LABEL_52;
          }
          v62 = (_DWORD *)*((_QWORD *)v49 + 14);
          if ( v62[2] == 31 )
          {
            if ( v62[1] == 2016 && *v62 == 63488 )
            {
              v48 = 3;
              goto LABEL_52;
            }
            if ( v62[1] == 992 && *v62 == 31744 )
              goto LABEL_52;
          }
          v48 = 5;
LABEL_52:
          v51 = v48;
          goto LABEL_53;
        }
        if ( !v81 )
        {
          v47 = v74;
          goto LABEL_47;
        }
        memset(v64, 0, 4LL * v81);
LABEL_46:
        v47 = v74;
LABEL_47:
        v48 = 4;
        goto LABEL_48;
      }
      v70 = v63 - 1;
      if ( v70 && v70 != 2 )
      {
        v47 = v74;
        goto LABEL_47;
      }
    }
    **((_DWORD **)*this + 14) = v18;
    *(_DWORD *)(*((_QWORD *)*this + 14) + 4LL) = v19;
    *(_DWORD *)(*((_QWORD *)*this + 14) + 8LL) = v20;
    if ( v18 == 255 && v19 == 65280 && v20 == 16711680 )
    {
      *((_DWORD *)*this + 6) |= 4u;
    }
    else if ( v18 == 63488 && v19 == 2016 && v20 == 31 )
    {
      *((_DWORD *)*this + 6) |= 0x400000u;
    }
    else if ( v18 == 31744 && v19 == 992 && v20 == 31 )
    {
      *((_DWORD *)*this + 6) |= 0x200000u;
    }
    v29 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( k = 0; (v18 & 1) == 0; ++k )
      v18 >>= 1;
    v31 = k;
    do
    {
      v18 >>= 1;
      ++v31;
    }
    while ( (v18 & 1) != 0 );
    v32 = v31 - k;
    v29[9] = v31 - k;
    v33 = v31 - 8;
    if ( v32 <= 8 )
      v33 = k;
    v29[6] = v33;
    v34 = 8;
    if ( v32 > 8 )
      v35 = 0;
    else
      v35 = 8 - v32;
    v29[3] = v35;
    v36 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( m = 0; (v19 & 1) == 0; ++m )
      v19 >>= 1;
    v38 = m;
    do
    {
      v19 >>= 1;
      ++v38;
    }
    while ( (v19 & 1) != 0 );
    v39 = v38 - m;
    v36[10] = v38 - m;
    v40 = v38 - 8;
    if ( v39 <= 8 )
      v40 = m;
    v36[7] = v40;
    v41 = 16;
    if ( v39 <= 8 )
      v34 = 16 - v39;
    v36[4] = v34;
    v42 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( n = 0; (v20 & 1) == 0; ++n )
      v20 >>= 1;
    v44 = n;
    do
    {
      v20 >>= 1;
      ++v44;
    }
    while ( (v20 & 1) != 0 );
    v45 = v44 - n;
    v42[11] = v44 - n;
    v46 = v44 - 8;
    if ( v45 <= 8 )
      v46 = n;
    v42[8] = v46;
    if ( v45 <= 8 )
      v41 = 24 - v45;
    v42[5] = v41;
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
