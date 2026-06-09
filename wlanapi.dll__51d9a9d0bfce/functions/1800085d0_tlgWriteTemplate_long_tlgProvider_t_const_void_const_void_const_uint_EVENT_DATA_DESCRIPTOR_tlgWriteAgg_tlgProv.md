# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800085d0`
- end: `0x180008a1e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@32@Z`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180005990`

## callees

- `0x1800085d0`
- `0x180008e60`
- `0x180011de8`
- `0x180011f68`
- `0x1800145d0`
- `0x180019a20`
- `0x18001a80c`
- `0x18005f4fc`
- `0x180060130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000882a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000882a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008788`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008788`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // r15
  unsigned __int8 v8; // r12
  unsigned __int64 v9; // r9
  char *v10; // rcx
  char v11; // al
  char *v14; // rax
  char v15; // r8
  __int64 v16; // rax
  __int64 v17; // r13
  RTL_SRWLOCK *v18; // rdi
  int v19; // esi
  int v20; // edx
  volatile signed __int64 *i; // rbx
  volatile signed __int64 v22; // rbx
  int v23; // ecx
  int v24; // eax
  __int64 v25; // r14
  unsigned int j; // edi
  int NewEventEntry; // r14d
  unsigned __int8 v29; // r12
  char v30; // r10
  unsigned int v31; // eax
  int v32; // [rsp+30h] [rbp-81h]
  signed __int64 v33; // [rsp+38h] [rbp-79h]
  signed __int64 v34; // [rsp+40h] [rbp-71h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int8 *Buf1; // [rsp+70h] [rbp-41h] BYREF
  int v38; // [rsp+78h] [rbp-39h]
  int v39; // [rsp+7Ch] [rbp-35h]
  __int64 v40; // [rsp+80h] [rbp-31h]
  _QWORD v41[7]; // [rsp+88h] [rbp-29h]

  v41[5] = a7;
  v7 = 2;
  v41[3] = a6;
  v41[1] = a5;
  *(_DWORD *)&EventDescriptor.Id = *(unsigned __int8 *)a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180084010;
  v41[6] = 8;
  v41[4] = 4;
  v41[2] = 4;
  v40 = a4;
  v41[0] = 8;
  UserData.Size = (unsigned __int16)*off_180084010;
  v38 = *(unsigned __int16 *)(a2 + 11);
  Buf1 = (unsigned __int8 *)(a2 + 11);
  UserData.Reserved = 2;
  v39 = 1;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180084030 != TlgAggregateInternalRegisteredProviderEtwCallback )
    return -1073741811;
  v8 = 0;
  v9 = (unsigned __int64)&Buf1[v38];
  v10 = (char *)(Buf1 + 2);
  do
    v11 = *v10++;
  while ( v11 < 0 );
  while ( *v10++ )
    ;
  while ( (unsigned __int64)v10 < v9 )
  {
    while ( *v10++ )
      ;
    if ( *v10 >= 0 )
      break;
    v14 = v10 + 1;
    v15 = *v10 & 0x7F;
    v10 += 2;
    if ( *v14 >= 0 )
      break;
    while ( 1 )
    {
      a2 = (unsigned __int8)*v10;
      if ( (a2 & 0x80u) == 0LL )
        break;
      if ( (_BYTE)a2 != 0x80 )
        goto LABEL_15;
      ++v10;
    }
    if ( v15 != 9 || (unsigned __int8)(a2 - 113) > 2u )
      break;
    v16 = 2LL * v8++;
    BYTE5(v41[v16]) = a2;
  }
LABEL_15:
  if ( !v8 )
    return EventWriteTransfer_0(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  LOBYTE(a2) = 6;
  v17 = qword_180084038;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v18 = (RTL_SRWLOCK *)(qword_180084038 + 264);
  v19 = ComputeEventEntryHash(v8, a2, &UserData);
  AcquireSRWLockShared(v18);
  for ( i = (volatile signed __int64 *)(v17 + 8LL * (v19 & 0x1F));
        ;
        i = (volatile signed __int64 *)((((__int64)v24 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + v22 + 32) )
  {
    if ( !*i )
    {
      if ( *(_DWORD *)(v17 + 256) >= 0x400u )
      {
        ++*(_DWORD *)(v17 + 300);
        NewEventEntry = 234;
        goto LABEL_29;
      }
      if ( !v33 )
      {
        LOBYTE(v20) = 6;
        NewEventEntry = CreateNewEventEntry(
                          (unsigned int)&EventDescriptor,
                          v20,
                          (unsigned int)&UserData,
                          v8,
                          v19,
                          (__int64)&v34);
        v32 = NewEventEntry;
        v33 = v34;
        if ( !v34 )
        {
          if ( NewEventEntry == 8 )
            ++*(_DWORD *)(v17 + 304);
          else
            ++*(_DWORD *)(v17 + 308);
          goto LABEL_29;
        }
      }
      if ( !_InterlockedCompareExchange64(i, v33, 0) )
        break;
    }
    v22 = *i;
    v23 = *(_DWORD *)(v22 + 40);
    if ( v19 == v23 )
    {
      v25 = *(_QWORD *)(v22 + 16);
      v24 = memcmp_0(&Buf1, (const void *)(v25 + 16), 8u);
      if ( v24 )
        continue;
      for ( j = *(unsigned __int8 *)(v22 + 45) + 2; j < 6; ++j )
      {
        v24 = *(&UserData.Size + 4 * j) - *(_DWORD *)(16LL * j + v25 + 8);
        if ( v24 )
          goto LABEL_26;
        v24 = memcmp_0(
                *((const void **)&UserData.Ptr + 2 * j),
                *(const void **)(16LL * j + v25),
                *(&UserData.Size + 4 * j));
        if ( v24 )
          goto LABEL_26;
      }
      v24 = 0;
LABEL_26:
      v18 = (RTL_SRWLOCK *)(v17 + 264);
    }
    else
    {
      v24 = v19 - v23;
    }
    if ( !v24 )
    {
      if ( v22 )
      {
        v29 = v8 + 2;
        if ( v29 > 2u )
        {
          do
          {
            AggregateField(
              *(_QWORD *)(*(_QWORD *)(v22 + 16) + 16 * v7),
              **((_QWORD **)&UserData.Ptr + 2 * v7),
              *(unsigned __int8 *)(*(_QWORD *)(v22 + 16) + 16 * v7 + 13));
            ++v7;
          }
          while ( (unsigned __int8)(v30 + 1) < v29 );
        }
      }
      NewEventEntry = v32;
      goto LABEL_29;
    }
  }
  v33 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v17 + 256)) == 1 )
    EnableFlushTimer(*(struct _TP_TIMER **)(v17 + 344), *(_DWORD *)(v17 + 352));
  v31 = *(_DWORD *)(v17 + 256);
  NewEventEntry = v32;
  if ( *(_DWORD *)(v17 + 288) < v31 )
    *(_DWORD *)(v17 + 288) = v31;
LABEL_29:
  ReleaseSRWLockShared(v18);
  if ( v33 )
    DestroyEventEntry(v33);
  return NewEventEntry;
}

```

## disassembly

```asm
0x1800085d0  push    rbp
0x1800085d2  push    r15
0x1800085d4  lea     rbp, [rsp-37h]
0x1800085d9  sub     rsp, 0E8h
0x1800085e0  mov     rax, cs:__security_cookie
0x1800085e7  xor     rax, rsp
0x1800085ea  mov     [rbp+3Fh+var_30], rax
0x1800085ee  mov     rax, [rbp+3Fh+arg_30]
0x1800085f2  lea     rcx, [rdx+0Bh]
0x1800085f6  mov     [rbp+3Fh+var_40], rax
0x1800085fa  mov     r15d, 2
0x180008600  mov     rax, [rbp+3Fh+arg_28]
0x180008604  mov     [rbp+3Fh+var_50], rax
0x180008608  mov     rax, [rbp+3Fh+arg_20]
0x18000860c  mov     [rbp+3Fh+var_60], rax
0x180008610  movzx   eax, byte ptr [rdx]
0x180008613  shl     eax, 18h
0x180008616  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x180008619  movzx   eax, word ptr [rdx+1]
0x18000861d  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x180008620  mov     rax, [rdx+3]
0x180008624  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x180008628  mov     rax, cs:off_180084010
0x18000862f  mov     [rbp+3Fh+var_90.Ptr], rax
0x180008633  mov     [rbp+3Fh+var_38], 8
0x18000863b  mov     [rbp+3Fh+var_48], 4
0x180008643  mov     [rbp+3Fh+var_58], 4
0x18000864b  mov     [rbp+3Fh+var_70], r9
0x18000864f  mov     [rbp+3Fh+var_68], 8
0x180008657  movzx   eax, word ptr [rax]
0x18000865a  mov     [rbp+3Fh+var_90.Size], eax
0x18000865d  movzx   eax, word ptr [rcx]
0x180008660  mov     [rbp+3Fh+var_78], eax
0x180008663  lea     rax, _TraceLoggingMetadataEnd
0x18000866a  mov     [rbp+3Fh+Buf1], rcx
0x18000866e  lea     rcx, _TraceLoggingMetadata
0x180008675  sub     eax, ecx
0x180008677  mov     dword ptr [rbp+3Fh+var_90.0Ch], r15d
0x18000867b  mov     [rbp+3Fh+var_74], 1
0x180008682  mov     [rsp+0F0h+var_C0], eax
0x180008686  mov     eax, [rsp+0F0h+var_C0]
0x18000868a  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180008691  cmp     cs:qword_180084030, rax
0x180008698  jnz     loc_180008A14
0x18000869e  mov     rax, [rbp+3Fh+Buf1]
0x1800086a2  mov     r9d, [rbp+3Fh+var_78]
0x1800086a6  mov     [rsp+0F0h+var_10], r12
0x1800086ae  xor     r12b, r12b
0x1800086b1  add     r9, rax
0x1800086b4  lea     rcx, [rax+2]
0x1800086b8  movzx   eax, byte ptr [rcx]
0x1800086bb  inc     rcx
0x1800086be  test    al, al
0x1800086c0  js      short loc_1800086B8
0x1800086c2  movzx   eax, byte ptr [rcx]
0x1800086c5  inc     rcx
0x1800086c8  test    al, al
0x1800086ca  jnz     short loc_1800086C2
0x1800086cc  cmp     rcx, r9
0x1800086cf  jnb     short loc_180008723
0x1800086d1  movzx   eax, byte ptr [rcx]
0x1800086d4  inc     rcx
0x1800086d7  test    al, al
0x1800086d9  jnz     short loc_1800086D1
0x1800086db  movzx   r8d, byte ptr [rcx]
0x1800086df  test    r8b, r8b
0x1800086e2  jns     short loc_180008723
0x1800086e4  lea     rax, [rcx+1]
0x1800086e8  and     r8b, 7Fh
0x1800086ec  add     rcx, r15
0x1800086ef  cmp     byte ptr [rax], 0
0x1800086f2  jge     short loc_180008723
0x1800086f4  movzx   edx, byte ptr [rcx]
0x1800086f7  test    dl, dl
0x1800086f9  jns     short loc_180008705
0x1800086fb  cmp     dl, 80h
0x1800086fe  jnz     short loc_180008723
0x180008700  inc     rcx
0x180008703  jmp     short loc_1800086F4
0x180008705  cmp     r8b, 9
0x180008709  jnz     short loc_180008723
0x18000870b  lea     eax, [rdx-71h]
0x18000870e  cmp     al, r15b
0x180008711  ja      short loc_180008723
0x180008713  movzx   eax, r12b
0x180008717  add     rax, rax
0x18000871a  inc     r12b
0x18000871d  mov     byte ptr [rbp+rax*8+3Fh+var_68+5], dl
0x180008721  jmp     short loc_1800086CC
0x180008723  test    r12b, r12b
0x180008726  jz      loc_1800089E8
0x18000872c  mov     [rsp+0F0h+arg_0], rbx
0x180008734  lea     r8, [rbp+3Fh+var_90]
0x180008738  mov     [rsp+0F0h+arg_8], rsi
0x180008740  xor     eax, eax
0x180008742  mov     [rsp+0F0h+arg_10], rdi
0x18000874a  mov     dl, 6
0x18000874c  mov     [rsp+0F0h+var_18], r13
0x180008754  movzx   ecx, r12b
0x180008758  mov     r13, cs:qword_180084038
0x18000875f  mov     [rsp+0F0h+var_20], r14
0x180008767  xor     r14d, r14d
0x18000876a  mov     [rsp+0F0h+var_C0], r14d
0x18000876f  mov     [rbp+3Fh+var_B8], rax
0x180008773  mov     [rbp+3Fh+var_B0], rax
0x180008777  call    ComputeEventEntryHash
0x18000877c  lea     rdi, [r13+108h]
0x180008783  mov     esi, eax
0x180008785  mov     rcx, rdi; SRWLock
0x180008788  call    cs:__imp_AcquireSRWLockShared
0x18000878e  mov     eax, esi
0x180008790  and     eax, 1Fh
0x180008793  lea     rbx, ds:0[rax*8]
0x18000879b  add     rbx, r13
0x18000879e  xchg    ax, ax
0x1800087a0  cmp     qword ptr [rbx], 0
0x1800087a4  jz      loc_1800088D1
0x1800087aa  mov     rbx, [rbx]
0x1800087ad  mov     ecx, [rbx+28h]
0x1800087b0  cmp     esi, ecx
0x1800087b2  jz      short loc_1800087D0
0x1800087b4  mov     eax, esi
0x1800087b6  sub     eax, ecx
0x1800087b8  test    eax, eax
0x1800087ba  jz      short loc_18000881D
0x1800087bc  movsxd  rcx, eax
0x1800087bf  add     rbx, 20h ; ' '
0x1800087c3  sar     rcx, 3Fh
0x1800087c7  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800087cb  add     rbx, rcx
0x1800087ce  jmp     short loc_1800087A0
0x1800087d0  mov     r14, [rbx+10h]
0x1800087d4  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x1800087d8  mov     r8d, 8; Size
0x1800087de  lea     rdx, [r14+10h]; Buf2
0x1800087e2  call    memcmp_0
0x1800087e7  test    eax, eax
0x1800087e9  jnz     short loc_1800087BC
0x1800087eb  movzx   edi, byte ptr [rbx+2Dh]
0x1800087ef  add     edi, r15d
0x1800087f2  cmp     edi, 6
0x1800087f5  jnb     loc_1800089B6
0x1800087fb  mov     ecx, edi
0x1800087fd  shl     rcx, 4
0x180008801  mov     r8d, [rbp+rcx+3Fh+var_90.Size]; Size
0x180008806  mov     eax, r8d
0x180008809  sub     eax, [rcx+r14+8]
0x18000880e  jz      loc_180008999
0x180008814  lea     rdi, [r13+108h]
0x18000881b  jmp     short loc_1800087B8
0x18000881d  test    rbx, rbx
0x180008820  jnz     short loc_180008887
0x180008822  mov     r14d, [rsp+0F0h+var_C0]
0x180008827  mov     rcx, rdi; SRWLock
0x18000882a  call    cs:__imp_ReleaseSRWLockShared
0x180008830  mov     rax, [rbp+3Fh+var_B8]
0x180008834  mov     r13, [rsp+0F0h+var_18]
0x18000883c  mov     rdi, [rsp+0F0h+arg_10]
0x180008844  mov     rsi, [rsp+0F0h+arg_8]
0x18000884c  mov     rbx, [rsp+0F0h+arg_0]
0x180008854  test    rax, rax
0x180008857  jnz     loc_1800089DB
0x18000885d  mov     eax, r14d
0x180008860  mov     r14, [rsp+0F0h+var_20]
0x180008868  mov     r12, [rsp+0F0h+var_10]
0x180008870  mov     rcx, [rbp+3Fh+var_30]
0x180008874  xor     rcx, rsp; StackCookie
0x180008877  call    __security_check_cookie
0x18000887c  add     rsp, 0E8h
0x180008883  pop     r15
0x180008885  pop     rbp
0x180008886  retn
0x180008887  add     r12b, r15b
0x18000888a  movzx   r10d, r15b
0x18000888e  cmp     r12b, r15b
0x180008891  jbe     short loc_180008822
0x180008893  nop     dword ptr [rax+00h]
0x180008897  nop     word ptr [rax+rax+00000000h]
0x1800088a0  mov     rax, [rbx+10h]
0x1800088a4  mov     rcx, r15
0x1800088a7  add     rcx, rcx
0x1800088aa  mov     rdx, [rbp+rcx*8+3Fh+var_90.Ptr]
0x1800088af  movzx   r8d, byte ptr [rax+rcx*8+0Dh]
0x1800088b5  mov     rcx, [rax+rcx*8]
0x1800088b9  mov     rdx, [rdx]
0x1800088bc  call    AggregateField
0x1800088c1  inc     r10b
0x1800088c4  inc     r15
0x1800088c7  cmp     r10b, r12b
0x1800088ca  jb      short loc_1800088A0
0x1800088cc  jmp     loc_180008822
0x1800088d1  cmp     dword ptr [r13+100h], 400h
0x1800088dc  jnb     loc_1800089C9
0x1800088e2  cmp     [rbp+3Fh+var_B8], 0
0x1800088e7  jnz     short loc_180008933
0x1800088e9  lea     rax, [rbp+3Fh+var_B0]
0x1800088ed  movzx   r9d, r12b
0x1800088f1  mov     [rsp+0F0h+UserData], rax
0x1800088f6  lea     r8, [rbp+3Fh+var_90]
0x1800088fa  mov     dl, 6
0x1800088fc  mov     [rsp+0F0h+UserDataCount], esi
0x180008900  lea     rcx, [rbp+3Fh+EventDescriptor]
0x180008904  call    CreateNewEventEntry
0x180008909  mov     r14d, eax
0x18000890c  mov     [rsp+0F0h+var_C0], eax
0x180008910  mov     rax, [rbp+3Fh+var_B0]
0x180008914  mov     [rbp+3Fh+var_B8], rax
0x180008918  test    rax, rax
0x18000891b  jnz     short loc_180008933
0x18000891d  cmp     r14d, 8
0x180008921  jnz     loc_1800089BD
0x180008927  inc     dword ptr [r13+130h]
0x18000892e  jmp     loc_180008827
0x180008933  mov     rcx, [rbp+3Fh+var_B8]
0x180008937  xor     eax, eax
0x180008939  lock cmpxchg [rbx], rcx
0x18000893e  jnz     loc_1800087AA
0x180008944  mov     [rbp+3Fh+var_B8], 0
0x18000894c  mov     eax, 1
0x180008951  lock xadd [r13+100h], eax
0x18000895a  inc     eax
0x18000895c  cmp     eax, 1
0x18000895f  jnz     short loc_180008974
0x180008961  mov     edx, [r13+160h]
0x180008968  mov     rcx, [r13+158h]
0x18000896f  call    EnableFlushTimer
0x180008974  mov     eax, [r13+100h]
0x18000897b  mov     r14d, [rsp+0F0h+var_C0]
0x180008980  cmp     [r13+120h], eax
0x180008987  jnb     loc_180008827
0x18000898d  mov     [r13+120h], eax
0x180008994  jmp     loc_180008827
0x180008999  mov     rdx, [rcx+r14]; Buf2
0x18000899d  mov     rcx, [rbp+rcx+3Fh+var_90.Ptr]; Buf1
0x1800089a2  call    memcmp_0
0x1800089a7  test    eax, eax
0x1800089a9  jnz     loc_180008814
0x1800089af  inc     edi
0x1800089b1  jmp     loc_1800087F2
0x1800089b6  xor     eax, eax
0x1800089b8  jmp     loc_180008814
0x1800089bd  inc     dword ptr [r13+134h]
0x1800089c4  jmp     loc_180008827
0x1800089c9  inc     dword ptr [r13+12Ch]
0x1800089d0  mov     r14d, 0EAh
0x1800089d6  jmp     loc_180008827
0x1800089db  mov     rcx, rax
0x1800089de  call    DestroyEventEntry
0x1800089e3  jmp     loc_18000885D
0x1800089e8  mov     rcx, cs:RegHandle; RegHandle
0x1800089ef  lea     rax, [rbp+3Fh+var_90]
0x1800089f3  mov     [rsp+0F0h+UserData], rax; UserData
0x1800089f8  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x1800089fc  xor     r9d, r9d; RelatedActivityId
0x1800089ff  mov     [rsp+0F0h+UserDataCount], 6; UserDataCount
0x180008a07  xor     r8d, r8d; ActivityId
0x180008a0a  call    EventWriteTransfer_0
0x180008a0f  jmp     loc_180008868
0x180008a14  mov     eax, 0C000000Dh
0x180008a19  jmp     loc_180008870
```
