# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180008190`
- end: `0x1800085bc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2@Z`
- size: `1068`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180014fc0`
- `0x1800152e0`
- `0x180015f60`
- `0x1800160d0`
- `0x180028320`
- `0x18002b1a0`

## callees

- `0x180008190`
- `0x180008e60`
- `0x180011de8`
- `0x180011f68`
- `0x1800145d0`
- `0x180019a20`
- `0x18001a80c`
- `0x18005f4fc`
- `0x180060130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800083c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800083c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008326`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008326`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // r15
  unsigned __int8 v6; // r12
  unsigned __int64 v7; // r9
  char *v8; // rcx
  char v9; // al
  char *v12; // rax
  char v13; // r8
  __int64 v14; // rax
  __int64 v15; // r13
  RTL_SRWLOCK *v16; // rdi
  int v17; // esi
  int v18; // edx
  volatile signed __int64 *i; // rbx
  volatile signed __int64 v20; // rbx
  int v21; // ecx
  __int64 v22; // r14
  int v23; // eax
  unsigned int j; // edi
  int NewEventEntry; // r14d
  unsigned __int8 v27; // r12
  char v28; // r10
  unsigned int v29; // eax
  int v30; // [rsp+30h] [rbp-51h]
  signed __int64 v31; // [rsp+38h] [rbp-49h]
  signed __int64 v32; // [rsp+40h] [rbp-41h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int8 *Buf1; // [rsp+70h] [rbp-11h] BYREF
  int v36; // [rsp+78h] [rbp-9h]
  int v37; // [rsp+7Ch] [rbp-5h]
  __int64 v38; // [rsp+80h] [rbp-1h]
  _QWORD v39[3]; // [rsp+88h] [rbp+7h]

  v39[1] = a5;
  v5 = 2;
  *(_DWORD *)&EventDescriptor.Id = *(unsigned __int8 *)a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180084010;
  v39[2] = 8;
  v38 = a4;
  v39[0] = 8;
  UserData.Size = (unsigned __int16)*off_180084010;
  v36 = *(unsigned __int16 *)(a2 + 11);
  Buf1 = (unsigned __int8 *)(a2 + 11);
  UserData.Reserved = 2;
  v37 = 1;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180084030 != TlgAggregateInternalRegisteredProviderEtwCallback )
    return -1073741811;
  v6 = 0;
  v7 = (unsigned __int64)&Buf1[v36];
  v8 = (char *)(Buf1 + 2);
  do
    v9 = *v8++;
  while ( v9 < 0 );
  while ( *v8++ )
    ;
  while ( (unsigned __int64)v8 < v7 )
  {
    while ( *v8++ )
      ;
    if ( *v8 >= 0 )
      break;
    v12 = v8 + 1;
    v13 = *v8 & 0x7F;
    v8 += 2;
    if ( *v12 >= 0 )
      break;
    while ( 1 )
    {
      a2 = (unsigned __int8)*v8;
      if ( (a2 & 0x80u) == 0LL )
        break;
      if ( (_BYTE)a2 != 0x80 )
        goto LABEL_15;
      ++v8;
    }
    if ( v13 != 9 || (unsigned __int8)(a2 - 113) > 2u )
      break;
    v14 = 2LL * v6++;
    BYTE5(v39[v14]) = a2;
  }
LABEL_15:
  if ( !v6 )
    return EventWriteTransfer_0(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  LOBYTE(a2) = 4;
  v15 = qword_180084038;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v16 = (RTL_SRWLOCK *)(qword_180084038 + 264);
  v17 = ComputeEventEntryHash(v6, a2, &UserData);
  AcquireSRWLockShared(v16);
  for ( i = (volatile signed __int64 *)(v15 + 8LL * (v17 & 0x1F));
        ;
        i = (volatile signed __int64 *)((((__int64)v23 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + v20 + 32) )
  {
    if ( !*i )
    {
      if ( *(_DWORD *)(v15 + 256) >= 0x400u )
      {
        ++*(_DWORD *)(v15 + 300);
        NewEventEntry = 234;
        goto LABEL_29;
      }
      if ( !v31 )
      {
        LOBYTE(v18) = 4;
        NewEventEntry = CreateNewEventEntry(
                          (unsigned int)&EventDescriptor,
                          v18,
                          (unsigned int)&UserData,
                          v6,
                          v17,
                          (__int64)&v32);
        v30 = NewEventEntry;
        v31 = v32;
        if ( !v32 )
        {
          if ( NewEventEntry == 8 )
            ++*(_DWORD *)(v15 + 304);
          else
            ++*(_DWORD *)(v15 + 308);
          goto LABEL_29;
        }
      }
      if ( !_InterlockedCompareExchange64(i, v31, 0) )
        break;
    }
    v20 = *i;
    v21 = *(_DWORD *)(v20 + 40);
    if ( v17 == v21 )
    {
      v22 = *(_QWORD *)(v20 + 16);
      v23 = memcmp_0(&Buf1, (const void *)(v22 + 16), 8u);
      if ( v23 )
        continue;
      for ( j = *(unsigned __int8 *)(v20 + 45) + 2; j < 4; ++j )
      {
        v23 = *(&UserData.Size + 4 * j) - *(_DWORD *)(16LL * j + v22 + 8);
        if ( v23 )
          goto LABEL_23;
        v23 = memcmp_0(
                *((const void **)&UserData.Ptr + 2 * j),
                *(const void **)(16LL * j + v22),
                *(&UserData.Size + 4 * j));
        if ( v23 )
          goto LABEL_23;
      }
      v23 = 0;
LABEL_23:
      v16 = (RTL_SRWLOCK *)(v15 + 264);
    }
    else
    {
      v23 = v17 - v21;
    }
    if ( !v23 )
    {
      if ( v20 )
      {
        v27 = v6 + 2;
        if ( v27 > 2u )
        {
          do
          {
            AggregateField(
              *(_QWORD *)(*(_QWORD *)(v20 + 16) + 16 * v5),
              **((_QWORD **)&UserData.Ptr + 2 * v5),
              *(unsigned __int8 *)(*(_QWORD *)(v20 + 16) + 16 * v5 + 13));
            ++v5;
          }
          while ( (unsigned __int8)(v28 + 1) < v27 );
        }
      }
      NewEventEntry = v30;
      goto LABEL_29;
    }
  }
  v31 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v15 + 256)) == 1 )
    EnableFlushTimer(*(struct _TP_TIMER **)(v15 + 344), *(_DWORD *)(v15 + 352));
  v29 = *(_DWORD *)(v15 + 256);
  NewEventEntry = v30;
  if ( *(_DWORD *)(v15 + 288) < v29 )
    *(_DWORD *)(v15 + 288) = v29;
LABEL_29:
  ReleaseSRWLockShared(v16);
  if ( v31 )
    DestroyEventEntry(v31);
  return NewEventEntry;
}

```

## disassembly

```asm
0x180008190  push    rbp
0x180008192  push    r15
0x180008194  lea     rbp, [rsp-47h]
0x180008199  sub     rsp, 0C8h
0x1800081a0  mov     rax, cs:__security_cookie
0x1800081a7  xor     rax, rsp
0x1800081aa  mov     [rbp+4Fh+var_30], rax
0x1800081ae  mov     rax, [rbp+4Fh+arg_20]
0x1800081b2  lea     rcx, [rdx+0Bh]
0x1800081b6  mov     [rbp+4Fh+var_40], rax
0x1800081ba  mov     r15d, 2
0x1800081c0  movzx   eax, byte ptr [rdx]
0x1800081c3  shl     eax, 18h
0x1800081c6  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], eax
0x1800081c9  movzx   eax, word ptr [rdx+1]
0x1800081cd  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x1800081d0  mov     rax, [rdx+3]
0x1800081d4  mov     [rbp+4Fh+EventDescriptor.Keyword], rax
0x1800081d8  mov     rax, cs:off_180084010
0x1800081df  mov     [rbp+4Fh+var_70.Ptr], rax
0x1800081e3  mov     [rbp+4Fh+var_38], 8
0x1800081eb  mov     [rbp+4Fh+var_50], r9
0x1800081ef  mov     [rbp+4Fh+var_48], 8
0x1800081f7  movzx   eax, word ptr [rax]
0x1800081fa  mov     [rbp+4Fh+var_70.Size], eax
0x1800081fd  movzx   eax, word ptr [rcx]
0x180008200  mov     [rbp+4Fh+var_58], eax
0x180008203  lea     rax, _TraceLoggingMetadataEnd
0x18000820a  mov     [rbp+4Fh+Buf1], rcx
0x18000820e  lea     rcx, _TraceLoggingMetadata
0x180008215  sub     eax, ecx
0x180008217  mov     dword ptr [rbp+4Fh+var_70.0Ch], r15d
0x18000821b  mov     [rbp+4Fh+var_54], 1
0x180008222  mov     [rbp+4Fh+var_A0], eax
0x180008225  mov     eax, [rbp+4Fh+var_A0]
0x180008228  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000822f  cmp     cs:qword_180084030, rax
0x180008236  jnz     loc_1800085B2
0x18000823c  mov     rax, [rbp+4Fh+Buf1]
0x180008240  mov     r9d, [rbp+4Fh+var_58]
0x180008244  mov     [rsp+0D0h+var_10], r12
0x18000824c  xor     r12b, r12b
0x18000824f  add     r9, rax
0x180008252  lea     rcx, [rax+2]
0x180008256  movzx   eax, byte ptr [rcx]
0x180008259  inc     rcx
0x18000825c  test    al, al
0x18000825e  js      short loc_180008256
0x180008260  movzx   eax, byte ptr [rcx]
0x180008263  inc     rcx
0x180008266  test    al, al
0x180008268  jnz     short loc_180008260
0x18000826a  cmp     rcx, r9
0x18000826d  jnb     short loc_1800082C2
0x18000826f  nop
0x180008270  movzx   eax, byte ptr [rcx]
0x180008273  inc     rcx
0x180008276  test    al, al
0x180008278  jnz     short loc_180008270
0x18000827a  movzx   r8d, byte ptr [rcx]
0x18000827e  test    r8b, r8b
0x180008281  jns     short loc_1800082C2
0x180008283  lea     rax, [rcx+1]
0x180008287  and     r8b, 7Fh
0x18000828b  add     rcx, r15
0x18000828e  cmp     byte ptr [rax], 0
0x180008291  jge     short loc_1800082C2
0x180008293  movzx   edx, byte ptr [rcx]
0x180008296  test    dl, dl
0x180008298  jns     short loc_1800082A4
0x18000829a  cmp     dl, 80h
0x18000829d  jnz     short loc_1800082C2
0x18000829f  inc     rcx
0x1800082a2  jmp     short loc_180008293
0x1800082a4  cmp     r8b, 9
0x1800082a8  jnz     short loc_1800082C2
0x1800082aa  lea     eax, [rdx-71h]
0x1800082ad  cmp     al, r15b
0x1800082b0  ja      short loc_1800082C2
0x1800082b2  movzx   eax, r12b
0x1800082b6  add     rax, rax
0x1800082b9  inc     r12b
0x1800082bc  mov     byte ptr [rbp+rax*8+4Fh+var_48+5], dl
0x1800082c0  jmp     short loc_18000826A
0x1800082c2  test    r12b, r12b
0x1800082c5  jz      loc_180008586
0x1800082cb  mov     [rsp+0D0h+arg_0], rbx
0x1800082d3  lea     r8, [rbp+4Fh+var_70]
0x1800082d7  mov     [rsp+0D0h+arg_8], rsi
0x1800082df  xor     eax, eax
0x1800082e1  mov     [rsp+0D0h+arg_10], rdi
0x1800082e9  mov     dl, 4
0x1800082eb  mov     [rsp+0D0h+var_18], r13
0x1800082f3  movzx   ecx, r12b
0x1800082f7  mov     r13, cs:qword_180084038
0x1800082fe  mov     [rsp+0D0h+var_20], r14
0x180008306  xor     r14d, r14d
0x180008309  mov     [rbp+4Fh+var_A0], r14d
0x18000830d  mov     [rbp+4Fh+var_98], rax
0x180008311  mov     [rbp+4Fh+var_90], rax
0x180008315  call    ComputeEventEntryHash
0x18000831a  lea     rdi, [r13+108h]
0x180008321  mov     esi, eax
0x180008323  mov     rcx, rdi; SRWLock
0x180008326  call    cs:__imp_AcquireSRWLockShared
0x18000832c  mov     eax, esi
0x18000832e  and     eax, 1Fh
0x180008331  lea     rbx, ds:0[rax*8]
0x180008339  add     rbx, r13
0x18000833c  nop     dword ptr [rax+00h]
0x180008340  cmp     qword ptr [rbx], 0
0x180008344  jz      loc_180008471
0x18000834a  mov     rbx, [rbx]
0x18000834d  mov     ecx, [rbx+28h]
0x180008350  cmp     esi, ecx
0x180008352  jnz     short loc_1800083A1
0x180008354  mov     r14, [rbx+10h]
0x180008358  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000835c  mov     r8d, 8; Size
0x180008362  lea     rdx, [r14+10h]; Buf2
0x180008366  call    memcmp_0
0x18000836b  test    eax, eax
0x18000836d  jnz     short loc_1800083A9
0x18000836f  movzx   edi, byte ptr [rbx+2Dh]
0x180008373  add     edi, r15d
0x180008376  cmp     edi, 4
0x180008379  jnb     loc_180008554
0x18000837f  mov     ecx, edi
0x180008381  shl     rcx, 4
0x180008385  mov     r8d, [rbp+rcx+4Fh+var_70.Size]; Size
0x18000838a  mov     eax, r8d
0x18000838d  sub     eax, [rcx+r14+8]
0x180008392  jz      loc_180008537
0x180008398  lea     rdi, [r13+108h]
0x18000839f  jmp     short loc_1800083A5
0x1800083a1  mov     eax, esi
0x1800083a3  sub     eax, ecx
0x1800083a5  test    eax, eax
0x1800083a7  jz      short loc_1800083BD
0x1800083a9  movsxd  rcx, eax
0x1800083ac  add     rbx, 20h ; ' '
0x1800083b0  sar     rcx, 3Fh
0x1800083b4  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800083b8  add     rbx, rcx
0x1800083bb  jmp     short loc_180008340
0x1800083bd  test    rbx, rbx
0x1800083c0  jnz     short loc_180008426
0x1800083c2  mov     r14d, [rbp+4Fh+var_A0]
0x1800083c6  mov     rcx, rdi; SRWLock
0x1800083c9  call    cs:__imp_ReleaseSRWLockShared
0x1800083cf  mov     rax, [rbp+4Fh+var_98]
0x1800083d3  mov     r13, [rsp+0D0h+var_18]
0x1800083db  mov     rdi, [rsp+0D0h+arg_10]
0x1800083e3  mov     rsi, [rsp+0D0h+arg_8]
0x1800083eb  mov     rbx, [rsp+0D0h+arg_0]
0x1800083f3  test    rax, rax
0x1800083f6  jnz     loc_180008579
0x1800083fc  mov     eax, r14d
0x1800083ff  mov     r14, [rsp+0D0h+var_20]
0x180008407  mov     r12, [rsp+0D0h+var_10]
0x18000840f  mov     rcx, [rbp+4Fh+var_30]
0x180008413  xor     rcx, rsp; StackCookie
0x180008416  call    __security_check_cookie
0x18000841b  add     rsp, 0C8h
0x180008422  pop     r15
0x180008424  pop     rbp
0x180008425  retn
0x180008426  add     r12b, r15b
0x180008429  movzx   r10d, r15b
0x18000842d  cmp     r12b, r15b
0x180008430  jbe     short loc_1800083C2
0x180008432  nop     dword ptr [rax+00h]
0x180008436  nop     word ptr [rax+rax+00000000h]
0x180008440  mov     rax, [rbx+10h]
0x180008444  mov     rcx, r15
0x180008447  add     rcx, rcx
0x18000844a  mov     rdx, [rbp+rcx*8+4Fh+var_70.Ptr]
0x18000844f  movzx   r8d, byte ptr [rax+rcx*8+0Dh]
0x180008455  mov     rcx, [rax+rcx*8]
0x180008459  mov     rdx, [rdx]
0x18000845c  call    AggregateField
0x180008461  inc     r10b
0x180008464  inc     r15
0x180008467  cmp     r10b, r12b
0x18000846a  jb      short loc_180008440
0x18000846c  jmp     loc_1800083C2
0x180008471  cmp     dword ptr [r13+100h], 400h
0x18000847c  jnb     loc_180008567
0x180008482  cmp     [rbp+4Fh+var_98], 0
0x180008487  jnz     short loc_1800084D2
0x180008489  lea     rax, [rbp+4Fh+var_90]
0x18000848d  movzx   r9d, r12b
0x180008491  mov     [rsp+0D0h+UserData], rax
0x180008496  lea     r8, [rbp+4Fh+var_70]
0x18000849a  mov     dl, 4
0x18000849c  mov     [rsp+0D0h+UserDataCount], esi
0x1800084a0  lea     rcx, [rbp+4Fh+EventDescriptor]
0x1800084a4  call    CreateNewEventEntry
0x1800084a9  mov     r14d, eax
0x1800084ac  mov     [rbp+4Fh+var_A0], eax
0x1800084af  mov     rax, [rbp+4Fh+var_90]
0x1800084b3  mov     [rbp+4Fh+var_98], rax
0x1800084b7  test    rax, rax
0x1800084ba  jnz     short loc_1800084D2
0x1800084bc  cmp     r14d, 8
0x1800084c0  jnz     loc_18000855B
0x1800084c6  inc     dword ptr [r13+130h]
0x1800084cd  jmp     loc_1800083C6
0x1800084d2  mov     rcx, [rbp+4Fh+var_98]
0x1800084d6  xor     eax, eax
0x1800084d8  lock cmpxchg [rbx], rcx
0x1800084dd  jnz     loc_18000834A
0x1800084e3  mov     [rbp+4Fh+var_98], 0
0x1800084eb  mov     eax, 1
0x1800084f0  lock xadd [r13+100h], eax
0x1800084f9  inc     eax
0x1800084fb  cmp     eax, 1
0x1800084fe  jnz     short loc_180008513
0x180008500  mov     edx, [r13+160h]
0x180008507  mov     rcx, [r13+158h]
0x18000850e  call    EnableFlushTimer
0x180008513  mov     eax, [r13+100h]
0x18000851a  mov     r14d, [rbp+4Fh+var_A0]
0x18000851e  cmp     [r13+120h], eax
0x180008525  jnb     loc_1800083C6
0x18000852b  mov     [r13+120h], eax
0x180008532  jmp     loc_1800083C6
0x180008537  mov     rdx, [rcx+r14]; Buf2
0x18000853b  mov     rcx, [rbp+rcx+4Fh+var_70.Ptr]; Buf1
0x180008540  call    memcmp_0
0x180008545  test    eax, eax
0x180008547  jnz     loc_180008398
0x18000854d  inc     edi
0x18000854f  jmp     loc_180008376
0x180008554  xor     eax, eax
0x180008556  jmp     loc_180008398
0x18000855b  inc     dword ptr [r13+134h]
0x180008562  jmp     loc_1800083C6
0x180008567  inc     dword ptr [r13+12Ch]
0x18000856e  mov     r14d, 0EAh
0x180008574  jmp     loc_1800083C6
0x180008579  mov     rcx, rax
0x18000857c  call    DestroyEventEntry
0x180008581  jmp     loc_1800083FC
0x180008586  mov     rcx, cs:RegHandle; RegHandle
0x18000858d  lea     rax, [rbp+4Fh+var_70]
0x180008591  mov     [rsp+0D0h+UserData], rax; UserData
0x180008596  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x18000859a  xor     r9d, r9d; RelatedActivityId
0x18000859d  mov     [rsp+0D0h+UserDataCount], 4; UserDataCount
0x1800085a5  xor     r8d, r8d; ActivityId
0x1800085a8  call    EventWriteTransfer_0
0x1800085ad  jmp     loc_180008407
0x1800085b2  mov     eax, 0C000000Dh
0x1800085b7  jmp     loc_18000840F
```
