# DirectComposition::CBatch::EnsureBatchBuffer(DirectComposition::CBatch * *,unsigned __int64,void * *)

- ea: `0x140085fe0`
- end: `0x140086448`
- name: `?EnsureBatchBuffer@CBatch@DirectComposition@@SA_NPEAPEAV12@_KPEAPEAX@Z`
- size: `1128`
- prototype: `char __fastcall(struct DirectComposition::CBatch **, unsigned __int64, void **)`
- caller_count: `576`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140071100`
- `0x140085e68`
- `0x1400866dc`
- `0x140086848`
- `0x140087214`
- `0x140087294`
- `0x140087510`
- `0x140087600`
- `0x140087688`
- `0x1400877b0`
- `0x140087b38`
- `0x140087bcc`
- `0x140087c28`
- `0x140087cc4`
- `0x140087eb0`
- `0x14008809c`
- `0x140088120`
- `0x140088904`
- `0x140088c18`
- `0x140088cac`
- `0x140088d3c`
- `0x1400e323c`
- `0x1400e3ad0`
- `0x1400e4770`
- `0x1400e4800`
- `0x1400e4900`
- `0x1400e4968`
- `0x1400e49c4`
- `0x1400e4a30`
- `0x1400e4a98`
- `0x1400e4af4`
- `0x1400e4b50`
- `0x1400e4bb0`
- `0x1400e4cf4`
- `0x1400e4d78`
- `0x1400e4e44`
- `0x1400f3f80`
- `0x1400f4548`
- `0x1400f45c4`
- `0x1400f4644`
- `0x1400f46c0`
- `0x1400f4744`
- `0x1400f47f8`
- `0x1400f4878`
- `0x1400f4900`
- `0x1400f4984`
- `0x1400f4a04`
- `0x1400f4a84`
- `0x1400f4b0c`
- `0x1400f4b8c`

## callees

- `0x1400856f8`
- `0x140085cd0`
- `0x140085fe0`
- `0x140086450`
- `0x140098800`
- `0x14021cbac`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400862cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400862cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140086321`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140086321`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400863b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400863b2`
- `ntoskrnl!KeResetEvent` at `0x140086074`
- `ntoskrnl!KeResetEvent` at `0x140086302`
- `ntoskrnl!KeResetEvent` at `0x140086074`
- `ntoskrnl!KeResetEvent` at `0x140086302`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400862dc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400862dc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140086087`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400862b1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140086087`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400862b1`
- `ntoskrnl!KeBugCheck` at `0x14008625b`
- `ntoskrnl!KeBugCheck` at `0x14008625b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140086315`
- `ntoskrnl!ExReleaseResourceLite` at `0x140086315`

## pseudocode

```c
char __fastcall DirectComposition::CBatch::EnsureBatchBuffer(
        struct DirectComposition::CBatch **a1,
        unsigned __int64 a2,
        void **a3)
{
  _QWORD *v5; // rdx
  __int64 v7; // r9
  __int64 v8; // r10
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  void *v11; // rcx
  struct DirectComposition::CBatch *v12; // rdi
  __int64 v13; // rsi
  __int64 v14; // rdx
  PSLIST_ENTRY i; // rbx
  struct DirectComposition::CBatch *v16; // rdx
  struct DirectComposition::CBatchSharedMemoryPool *v17; // r14
  struct DirectComposition::CBatchSharedMemoryPool *j; // rbx
  __int64 v19; // r15
  struct DirectComposition::CBatchSharedMemoryPool **v20; // rax
  struct DirectComposition::CBatchSharedMemoryPool *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  struct _ERESOURCE *v24; // rbx
  struct DirectComposition::CBatch **v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned __int64 v28; // rbp
  __int64 v29; // r8
  void *v30; // r8
  struct _SLIST_ENTRY *Next; // rax
  char v33; // di
  char v34; // al
  struct DirectComposition::CBatch *v35; // [rsp+30h] [rbp-58h] BYREF
  struct DirectComposition::CBatchSharedMemoryPool *v36; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v37; // [rsp+40h] [rbp-48h]
  char v39; // [rsp+A0h] [rbp+18h]
  int v40; // [rsp+A8h] [rbp+20h]

  v5 = *a1;
  v7 = *((_QWORD *)*a1 + 17);
  v8 = *(_QWORD *)(v7 + 40);
  v9 = 4096 - v8;
  if ( a3 )
  {
    if ( a2 <= v9 )
    {
      v10 = *(_QWORD *)(v7 + 56);
      *(_QWORD *)(v7 + 40) = v8 + a2;
      v11 = (void *)(v8 + v10);
      if ( v11 )
      {
        *a3 = v11;
        v5[19] += a2;
        return 1;
      }
    }
  }
  else if ( a2 <= v9 )
  {
    return 1;
  }
  v37 = *a1;
  v12 = 0;
  v35 = 0;
  v13 = v37[1];
  v40 = *((_DWORD *)v37 + 4);
  v39 = *((_BYTE *)v37 + 32);
  KeResetEvent(*(PRKEVENT *)(*(_QWORD *)(v13 + 240) + 8LL));
  for ( i = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v13 + 208));
        i;
        i = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v13 + 208)) )
  {
    --*(_DWORD *)(v13 + 252);
    Next = i[4].Next;
    if ( (unsigned __int64)Next > *(_QWORD *)(v13 + 256) )
    {
      *(_BYTE *)(v13 + 264) |= 2u;
      *(_QWORD *)(v13 + 256) = Next;
    }
    DirectComposition::CBatch::Clear((DirectComposition::CBatch *)i, v14);
    i->Next = *(struct _SLIST_ENTRY **)(v13 + 200);
    *(_QWORD *)(v13 + 200) = i;
  }
  v16 = *(struct DirectComposition::CBatch **)(v13 + 184);
  if ( v16 )
  {
    v12 = *(struct DirectComposition::CBatch **)(v13 + 184);
    *(_QWORD *)(v13 + 184) = 0;
LABEL_25:
    *((_DWORD *)v16 + 4) = v40;
    *((_BYTE *)v16 + 32) ^= (v39 ^ *((_BYTE *)v16 + 32)) & 1;
    *(_QWORD *)v12 = 0;
    ++*(_DWORD *)(v13 + 252);
    *(_BYTE *)(v13 + 264) |= 8u;
    v24 = *(struct _ERESOURCE **)(v13 + 392);
    if ( v24 )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(v24, 1u);
      if ( ++*(_DWORD *)(v13 + 248) == 1 )
        KeResetEvent(*(PRKEVENT *)(*(_QWORD *)(v13 + 384) + 8LL));
      ExReleaseResourceLite(*(PERESOURCE *)(v13 + 392));
      KeLeaveCriticalRegion();
    }
  }
  else
  {
    v17 = (struct DirectComposition::CBatchSharedMemoryPool *)(v13 + 2648);
    v36 = 0;
    for ( j = *(struct DirectComposition::CBatchSharedMemoryPool **)(v13 + 2648);
          ;
          j = *(struct DirectComposition::CBatchSharedMemoryPool **)j )
    {
      if ( j == v17 )
      {
        if ( (int)DirectComposition::CBatchSharedMemoryPool::Create(
                    (struct DirectComposition::CBatchSharedMemoryPoolSet *)(v13 + 2648),
                    *(_BYTE *)(v13 + 2672),
                    &v36) < 0 )
          goto LABEL_26;
        j = v36;
        v19 = 0;
        if ( !*((_BYTE *)v36 + 64) && (unsigned __int64)(4096LL - *((_QWORD *)v36 + 5)) >= 0x228 )
        {
          v19 = *((_QWORD *)v36 + 5);
          *((_BYTE *)v36 + 64) = 1;
        }
        v22 = *(_QWORD *)v17;
        if ( *(struct DirectComposition::CBatchSharedMemoryPool **)(*(_QWORD *)v17 + 8LL) != v17 )
LABEL_15:
          __fastfail(3u);
        goto LABEL_17;
      }
      if ( !*((_BYTE *)j + 64) )
      {
        v19 = *((_QWORD *)j + 5);
        if ( (unsigned __int64)(4096 - v19) >= 0x228 )
          break;
      }
    }
    *((_BYTE *)j + 64) = 1;
    v20 = (struct DirectComposition::CBatchSharedMemoryPool **)*((_QWORD *)j + 1);
    if ( v20 == (struct DirectComposition::CBatchSharedMemoryPool **)v17 )
      goto LABEL_18;
    v21 = *(struct DirectComposition::CBatchSharedMemoryPool **)j;
    if ( *(struct DirectComposition::CBatchSharedMemoryPool **)(*(_QWORD *)j + 8LL) != j )
      goto LABEL_15;
    if ( *v20 != j )
      goto LABEL_15;
    *v20 = v21;
    *((_QWORD *)v21 + 1) = v20;
    v22 = *(_QWORD *)v17;
    if ( *(struct DirectComposition::CBatchSharedMemoryPool **)(*(_QWORD *)v17 + 8LL) != v17 )
      goto LABEL_15;
LABEL_17:
    *(_QWORD *)j = v22;
    *((_QWORD *)j + 1) = v17;
    *(_QWORD *)(v22 + 8) = j;
    *(_QWORD *)v17 = j;
LABEL_18:
    if ( !j )
      goto LABEL_26;
    v23 = *((_QWORD *)j + 5);
    if ( (unsigned __int64)(4096 - v23) >= 0x28 )
      *((_QWORD *)j + 5) = v23 + 40;
    v12 = *(struct DirectComposition::CBatch **)(v13 + 200);
    if ( v12 )
    {
      *(_QWORD *)(v13 + 200) = *(_QWORD *)v12;
    }
    else
    {
      if ( (int)DirectComposition::CApplicationChannel::CreateBatch((DirectComposition::CApplicationChannel *)v13, &v35) < 0
        && *(int *)(v13 + 252) > 0 )
      {
        v33 = 1;
        v34 = 0;
        while ( *(int *)(v13 + 252) > 0 )
        {
          if ( v34
            && DirectComposition::CConnection::ShouldWaitForReturnedBatches(*(DirectComposition::CConnection **)(v13 + 40))
            && KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v13 + 240) + 8LL), UserRequest, 0, 1u, 0) )
          {
            v33 = 0;
          }
          if ( (unsigned __int8)DirectComposition::CApplicationChannel::ProcessReturnedBatches((union _SLIST_HEADER *)v13) )
          {
            v12 = *(struct DirectComposition::CBatch **)(v13 + 200);
            *(_QWORD *)(v13 + 200) = *(_QWORD *)v12;
            goto LABEL_23;
          }
          v34 = 1;
          if ( !v33 )
            break;
        }
      }
      v12 = v35;
    }
LABEL_23:
    if ( v12 )
    {
      *((_QWORD *)v12 + 18) = v19;
      v16 = v12;
      *((_QWORD *)v12 + 17) = j;
      goto LABEL_25;
    }
    *((_BYTE *)j + 64) = 0;
  }
LABEL_26:
  if ( v12 )
  {
    v25 = (struct DirectComposition::CBatch **)v37;
    *(_BYTE *)(v37[17] + 64LL) = 0;
    *v25 = v12;
    *a1 = v12;
    v26 = *((_QWORD *)v12 + 17);
    v27 = *(_QWORD *)(v26 + 40);
    v28 = 4096 - v27;
    if ( a3 )
    {
      if ( a2 <= v28 )
      {
        v29 = *(_QWORD *)(v26 + 56);
        *(_QWORD *)(v26 + 40) = v27 + a2;
        v30 = (void *)(v27 + v29);
        if ( v30 )
        {
          *a3 = v30;
          *((_QWORD *)v12 + 19) += a2;
          return 1;
        }
      }
    }
    else if ( a2 <= v28 )
    {
      return 1;
    }
    KeBugCheck(0xC000000D);
  }
  return 0;
}

```

## disassembly

```asm
0x140085fe0  mov     [rsp+arg_8], rbx
0x140085fe5  mov     [rsp+arg_0], rcx
0x140085fea  push    rbp
0x140085feb  push    rsi
0x140085fec  push    rdi
0x140085fed  push    r12
0x140085fef  push    r13
0x140085ff1  push    r14
0x140085ff3  push    r15
0x140085ff5  sub     rsp, 50h
0x140085ff9  mov     r13, r8
0x140085ffc  mov     r12, rdx
0x140085fff  mov     rdx, [rcx]
0x140086002  mov     ebp, 1000h
0x140086007  mov     eax, ebp
0x140086009  mov     r8, rcx
0x14008600c  mov     r9, [rdx+88h]
0x140086013  mov     r10, [r9+28h]
0x140086017  sub     rax, r10
0x14008601a  test    r13, r13
0x14008601d  jz      loc_140086332
0x140086023  cmp     r12, rax
0x140086026  ja      short loc_14008603D
0x140086028  mov     rcx, [r9+38h]
0x14008602c  lea     rax, [r10+r12]
0x140086030  mov     [r9+28h], rax
0x140086034  add     rcx, r10
0x140086037  jnz     loc_140086116
0x14008603d  mov     rax, [r8]
0x140086040  xor     r15d, r15d
0x140086043  mov     [rsp+88h+var_48], rax
0x140086048  mov     edi, r15d
0x14008604b  mov     [rsp+88h+var_58], r15
0x140086050  mov     ecx, [rax+10h]
0x140086053  mov     rsi, [rax+8]
0x140086057  movzx   eax, byte ptr [rax+20h]
0x14008605b  mov     [rsp+88h+arg_18], ecx
0x140086062  mov     [rsp+88h+arg_10], al
0x140086069  mov     rcx, [rsi+0F0h]
0x140086070  mov     rcx, [rcx+8]; Event
0x140086074  call    cs:__imp_KeResetEvent
0x14008607b  nop     dword ptr [rax+rax+00h]
0x140086080  lea     rcx, [rsi+0D0h]; ListHead
0x140086087  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008608e  nop     dword ptr [rax+rax+00h]
0x140086093  mov     rbx, rax
0x140086096  test    rax, rax
0x140086099  jnz     loc_140086270
0x14008609f  mov     rdx, [rsi+0B8h]
0x1400860a6  test    rdx, rdx
0x1400860a9  jnz     loc_140086242
0x1400860af  lea     r14, [rsi+0A58h]
0x1400860b6  mov     [rsp+88h+var_50], r15
0x1400860bb  mov     rbx, [r14]
0x1400860be  cmp     rbx, r14
0x1400860c1  jz      loc_1400863DF
0x1400860c7  cmp     [rbx+40h], dil
0x1400860cb  jnz     short loc_1400860DF
0x1400860cd  mov     r15, [rbx+28h]
0x1400860d1  mov     rax, rbp
0x1400860d4  sub     rax, r15
0x1400860d7  cmp     rax, 228h
0x1400860dd  jnb     short loc_1400860E4
0x1400860df  mov     rbx, [rbx]
0x1400860e2  jmp     short loc_1400860BE
0x1400860e4  mov     byte ptr [rbx+40h], 1
0x1400860e8  mov     rax, [rbx+8]
0x1400860ec  cmp     rax, r14
0x1400860ef  jz      short loc_140086134
0x1400860f1  mov     rcx, [rbx]
0x1400860f4  cmp     [rcx+8], rbx
0x1400860f8  jnz     short loc_14008610F
0x1400860fa  cmp     [rax], rbx
0x1400860fd  jnz     short loc_14008610F
0x1400860ff  mov     [rax], rcx
0x140086102  mov     [rcx+8], rax
0x140086106  mov     rax, [r14]
0x140086109  cmp     [rax+8], r14
0x14008610d  jz      short loc_140086126
0x14008610f  mov     ecx, 3
0x140086114  int     29h; Win8: RtlFailFast(ecx)
0x140086116  mov     [r13+0], rcx
0x14008611a  add     [rdx+98h], r12
0x140086121  jmp     loc_140086227
0x140086126  mov     [rbx], rax
0x140086129  mov     [rbx+8], r14
0x14008612d  mov     [rax+8], rbx
0x140086131  mov     [r14], rbx
0x140086134  test    rbx, rbx
0x140086137  jz      loc_1400861CC
0x14008613d  mov     rcx, [rbx+28h]
0x140086141  mov     rax, rbp
0x140086144  sub     rax, rcx
0x140086147  cmp     rax, 28h ; '('
0x14008614b  jb      short loc_140086155
0x14008614d  lea     rax, [rcx+28h]
0x140086151  mov     [rbx+28h], rax
0x140086155  mov     rdi, [rsi+0C8h]
0x14008615c  test    rdi, rdi
0x14008615f  jz      loc_140086350
0x140086165  mov     rax, [rdi]
0x140086168  mov     [rsi+0C8h], rax
0x14008616f  test    rdi, rdi
0x140086172  jz      loc_140086340
0x140086178  mov     [rdi+90h], r15
0x14008617f  mov     rdx, rdi
0x140086182  xor     r15d, r15d
0x140086185  mov     [rdi+88h], rbx
0x14008618c  mov     eax, [rsp+88h+arg_18]
0x140086193  mov     [rdx+10h], eax
0x140086196  movzx   eax, byte ptr [rdx+20h]
0x14008619a  movzx   ecx, al
0x14008619d  xor     cl, [rsp+88h+arg_10]
0x1400861a4  and     cl, 1
0x1400861a7  xor     cl, al
0x1400861a9  mov     [rdx+20h], cl
0x1400861ac  mov     [rdi], r15
0x1400861af  inc     dword ptr [rsi+0FCh]
0x1400861b5  or      byte ptr [rsi+108h], 8
0x1400861bc  mov     rbx, [rsi+188h]
0x1400861c3  test    rbx, rbx
0x1400861c6  jnz     loc_1400862CB
0x1400861cc  test    rdi, rdi
0x1400861cf  jz      loc_140086268
0x1400861d5  mov     rcx, [rsp+88h+var_48]
0x1400861da  mov     rax, [rcx+88h]
0x1400861e1  mov     byte ptr [rax+40h], 0
0x1400861e5  mov     rax, [rsp+88h+arg_0]
0x1400861ed  mov     [rcx], rdi
0x1400861f0  mov     [rax], rdi
0x1400861f3  mov     rcx, [rdi+88h]
0x1400861fa  mov     rdx, [rcx+28h]
0x1400861fe  sub     rbp, rdx
0x140086201  test    r13, r13
0x140086204  jz      short loc_140086251
0x140086206  cmp     r12, rbp
0x140086209  ja      short loc_140086256
0x14008620b  mov     r8, [rcx+38h]
0x14008620f  lea     rax, [rdx+r12]
0x140086213  mov     [rcx+28h], rax
0x140086217  add     r8, rdx
0x14008621a  jz      short loc_140086256
0x14008621c  mov     [r13+0], r8
0x140086220  add     [rdi+98h], r12
0x140086227  mov     al, 1
0x140086229  mov     rbx, [rsp+88h+arg_8]
0x140086231  add     rsp, 50h
0x140086235  pop     r15
0x140086237  pop     r14
0x140086239  pop     r13
0x14008623b  pop     r12
0x14008623d  pop     rdi
0x14008623e  pop     rsi
0x14008623f  pop     rbp
0x140086240  retn
0x140086242  mov     rdi, rdx
0x140086245  mov     [rsi+0B8h], r15
0x14008624c  jmp     loc_14008618C
0x140086251  cmp     r12, rbp
0x140086254  jbe     short loc_140086227
0x140086256  mov     ecx, 0C000000Dh; BugCheckCode
0x14008625b  call    cs:__imp_KeBugCheck
0x140086268  xor     al, al
0x14008626a  jmp     short loc_140086229
0x140086270  dec     dword ptr [rsi+0FCh]
0x140086276  mov     rax, [rbx+40h]
0x14008627a  cmp     rax, [rsi+100h]
0x140086281  jbe     short loc_140086291
0x140086283  or      byte ptr [rsi+108h], 2
0x14008628a  mov     [rsi+100h], rax
0x140086291  mov     rcx, rbx; this
0x140086294  call    ?Clear@CBatch@DirectComposition@@QEAAXXZ; DirectComposition::CBatch::Clear(void)
0x140086299  mov     rax, [rsi+0C8h]
0x1400862a0  lea     rcx, [rsi+0D0h]; ListHead
0x1400862a7  mov     [rbx], rax
0x1400862aa  mov     [rsi+0C8h], rbx
0x1400862b1  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400862b8  nop     dword ptr [rax+rax+00h]
0x1400862bd  mov     rbx, rax
0x1400862c0  test    rax, rax
0x1400862c3  jz      loc_14008609F
0x1400862c9  jmp     short loc_140086270
0x1400862cb  call    cs:__imp_KeEnterCriticalRegion
0x1400862d2  nop     dword ptr [rax+rax+00h]
0x1400862d7  mov     dl, 1; Wait
0x1400862d9  mov     rcx, rbx; Resource
0x1400862dc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400862e3  nop     dword ptr [rax+rax+00h]
0x1400862e8  inc     dword ptr [rsi+0F8h]
0x1400862ee  cmp     dword ptr [rsi+0F8h], 1
0x1400862f5  jnz     short loc_14008630E
0x1400862f7  mov     rcx, [rsi+180h]
0x1400862fe  mov     rcx, [rcx+8]; Event
0x140086302  call    cs:__imp_KeResetEvent
0x140086309  nop     dword ptr [rax+rax+00h]
0x14008630e  mov     rcx, [rsi+188h]; Resource
0x140086315  call    cs:__imp_ExReleaseResourceLite
0x14008631c  nop     dword ptr [rax+rax+00h]
0x140086321  call    cs:__imp_KeLeaveCriticalRegion
0x140086328  nop     dword ptr [rax+rax+00h]
0x14008632d  jmp     loc_1400861CC
0x140086332  cmp     r12, rax
0x140086335  ja      loc_14008603D
0x14008633b  jmp     loc_140086227
0x140086340  mov     byte ptr [rbx+40h], 0
0x140086344  jmp     loc_1400861CC
0x140086350  lea     rdx, [rsp+88h+var_58]; struct DirectComposition::CBatch **
0x140086355  mov     rcx, rsi; this
0x140086358  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x14008635d  test    eax, eax
0x14008635f  js      short loc_14008636B
0x140086361  mov     rdi, [rsp+88h+var_58]
0x140086366  jmp     loc_14008616F
0x14008636b  cmp     dword ptr [rsi+0FCh], 0
0x140086372  jle     short loc_140086361
0x140086374  mov     dil, 1
0x140086377  xor     al, al
0x140086379  cmp     dword ptr [rsi+0FCh], 0
0x140086380  jle     short loc_140086361
0x140086382  test    al, al
0x140086384  jz      short loc_1400863CA
0x140086386  mov     rcx, [rsi+28h]; this
0x14008638a  call    ?ShouldWaitForReturnedBatches@CConnection@DirectComposition@@QEAA_NXZ; DirectComposition::CConnection::ShouldWaitForReturnedBatches(void)
0x14008638f  test    al, al
0x140086391  jz      short loc_1400863CA
0x140086393  mov     rcx, [rsi+0F0h]
0x14008639a  mov     r9b, 1; Alertable
0x14008639d  xor     r8d, r8d; WaitMode
0x1400863a0  mov     [rsp+88h+Timeout], 0; Timeout
0x1400863a9  mov     edx, 6; WaitReason
0x1400863ae  mov     rcx, [rcx+8]; Object
0x1400863b2  call    cs:__imp_KeWaitForSingleObject
0x1400863b9  nop     dword ptr [rax+rax+00h]
0x1400863be  test    eax, eax
0x1400863c0  jz      short loc_1400863CA
0x1400863c2  sub     eax, 0C0h
0x1400863c7  xor     dil, dil
0x1400863ca  mov     rcx, rsi; this
0x1400863cd  call    ?ProcessReturnedBatches@CApplicationChannel@DirectComposition@@IEAA_NXZ; DirectComposition::CApplicationChannel::ProcessReturnedBatches(void)
0x1400863d2  test    al, al
0x1400863d4  jnz     short loc_140086432
0x1400863d6  mov     al, 1
0x1400863d8  test    dil, dil
0x1400863db  jnz     short loc_140086379
0x1400863dd  jmp     short loc_140086361
0x1400863df  movzx   edx, byte ptr [r14+18h]; bool
0x1400863e4  lea     r8, [rsp+88h+var_50]; struct DirectComposition::CBatchSharedMemoryPool **
0x1400863e9  mov     rcx, r14; struct DirectComposition::CBatchSharedMemoryPoolSet *
0x1400863ec  call    ?Create@CBatchSharedMemoryPool@DirectComposition@@SAJPEAVCBatchSharedMemoryPoolSet@2@_NPEAPEAV12@@Z; DirectComposition::CBatchSharedMemoryPool::Create(DirectComposition::CBatchSharedMemoryPoolSet *,bool,DirectComposition::CBatchSharedMemoryPool * *)
0x1400863f1  test    eax, eax
0x1400863f3  js      loc_1400861CC
0x1400863f9  mov     rbx, [rsp+88h+var_50]
0x1400863fe  xor     r15d, r15d
0x140086401  cmp     [rbx+40h], dil
0x140086405  jnz     short loc_140086420
0x140086407  mov     rcx, [rbx+28h]
0x14008640b  mov     rax, rbp
0x14008640e  sub     rax, rcx
0x140086411  cmp     rax, 228h
0x140086417  jb      short loc_140086420
0x140086419  mov     r15, rcx
0x14008641c  mov     byte ptr [rbx+40h], 1
0x140086420  mov     rax, [r14]
0x140086423  cmp     [rax+8], r14
0x140086427  jnz     loc_14008610F
0x14008642d  jmp     loc_140086126
0x140086432  mov     rdi, [rsi+0C8h]
0x140086439  mov     rax, [rdi]
0x14008643c  mov     [rsi+0C8h], rax
0x140086443  jmp     loc_14008616F
```
