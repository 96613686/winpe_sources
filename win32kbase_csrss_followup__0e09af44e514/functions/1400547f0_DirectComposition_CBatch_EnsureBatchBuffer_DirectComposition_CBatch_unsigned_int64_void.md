# DirectComposition::CBatch::EnsureBatchBuffer(DirectComposition::CBatch * *,unsigned __int64,void * *)

- ea: `0x1400547f0`
- end: `0x140054c58`
- name: `?EnsureBatchBuffer@CBatch@DirectComposition@@SA_NPEAPEAV12@_KPEAPEAX@Z`
- size: `1128`
- prototype: `bool __fastcall(struct DirectComposition::CBatch **, unsigned __int64, void **)`
- caller_count: `576`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140034a50`
- `0x140054678`
- `0x140054eec`
- `0x140055058`
- `0x140055a24`
- `0x140055aa4`
- `0x140055d20`
- `0x140055e10`
- `0x140055e98`
- `0x140055fc0`
- `0x140056348`
- `0x1400563dc`
- `0x140056438`
- `0x1400564d4`
- `0x1400566c0`
- `0x1400568ac`
- `0x140056930`
- `0x140057114`
- `0x140057428`
- `0x1400574bc`
- `0x14005754c`
- `0x1400e8b3c`
- `0x1400e93d0`
- `0x1400ea070`
- `0x1400ea100`
- `0x1400ea200`
- `0x1400ea268`
- `0x1400ea2c4`
- `0x1400ea330`
- `0x1400ea398`
- `0x1400ea3f4`
- `0x1400ea450`
- `0x1400ea4b0`
- `0x1400ea5f4`
- `0x1400ea678`
- `0x1400ea744`
- `0x1400ee160`
- `0x1400ee728`
- `0x1400ee7a4`
- `0x1400ee824`
- `0x1400ee8a0`
- `0x1400ee924`
- `0x1400ee9d8`
- `0x1400eea58`
- `0x1400eeae0`
- `0x1400eeb64`
- `0x1400eebe4`
- `0x1400eec64`
- `0x1400eecec`
- `0x1400eed6c`

## callees

- `0x140053f08`
- `0x1400544e0`
- `0x1400547f0`
- `0x140054c60`
- `0x140060ac0`
- `0x14021c2fc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140054adb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140054adb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054b31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054b31`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054bc2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054bc2`
- `ntoskrnl!KeResetEvent` at `0x140054884`
- `ntoskrnl!KeResetEvent` at `0x140054b12`
- `ntoskrnl!KeResetEvent` at `0x140054884`
- `ntoskrnl!KeResetEvent` at `0x140054b12`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140054aec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140054aec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140054897`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140054ac1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140054897`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140054ac1`
- `ntoskrnl!KeBugCheck` at `0x140054a6b`
- `ntoskrnl!KeBugCheck` at `0x140054a6b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054b25`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054b25`

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
  PSLIST_ENTRY i; // rbx
  struct DirectComposition::CBatch *v15; // rdx
  struct DirectComposition::CBatchSharedMemoryPool *v16; // r14
  struct DirectComposition::CBatchSharedMemoryPool *j; // rbx
  __int64 v18; // r15
  struct DirectComposition::CBatchSharedMemoryPool **v19; // rax
  struct DirectComposition::CBatchSharedMemoryPool *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  struct _ERESOURCE *v23; // rbx
  struct DirectComposition::CBatch **v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdx
  unsigned __int64 v27; // rbp
  __int64 v28; // r8
  void *v29; // r8
  struct _SLIST_ENTRY *Next; // rax
  char v32; // di
  char v33; // al
  struct DirectComposition::CBatch *v34; // [rsp+30h] [rbp-58h] BYREF
  struct DirectComposition::CBatchSharedMemoryPool *v35; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v36; // [rsp+40h] [rbp-48h]
  char v38; // [rsp+A0h] [rbp+18h]
  int v39; // [rsp+A8h] [rbp+20h]

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
  v36 = *a1;
  v12 = 0;
  v34 = 0;
  v13 = v36[1];
  v39 = *((_DWORD *)v36 + 4);
  v38 = *((_BYTE *)v36 + 32);
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
    DirectComposition::CBatch::Clear((DirectComposition::CBatch *)i);
    i->Next = *(struct _SLIST_ENTRY **)(v13 + 200);
    *(_QWORD *)(v13 + 200) = i;
  }
  v15 = *(struct DirectComposition::CBatch **)(v13 + 184);
  if ( v15 )
  {
    v12 = *(struct DirectComposition::CBatch **)(v13 + 184);
    *(_QWORD *)(v13 + 184) = 0;
LABEL_25:
    *((_DWORD *)v15 + 4) = v39;
    *((_BYTE *)v15 + 32) ^= (v38 ^ *((_BYTE *)v15 + 32)) & 1;
    *(_QWORD *)v12 = 0;
    ++*(_DWORD *)(v13 + 252);
    *(_BYTE *)(v13 + 264) |= 8u;
    v23 = *(struct _ERESOURCE **)(v13 + 392);
    if ( v23 )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(v23, 1u);
      if ( ++*(_DWORD *)(v13 + 248) == 1 )
        KeResetEvent(*(PRKEVENT *)(*(_QWORD *)(v13 + 384) + 8LL));
      ExReleaseResourceLite(*(PERESOURCE *)(v13 + 392));
      KeLeaveCriticalRegion();
    }
  }
  else
  {
    v16 = (struct DirectComposition::CBatchSharedMemoryPool *)(v13 + 2648);
    v35 = 0;
    for ( j = *(struct DirectComposition::CBatchSharedMemoryPool **)(v13 + 2648);
          ;
          j = *(struct DirectComposition::CBatchSharedMemoryPool **)j )
    {
      if ( j == v16 )
      {
        if ( (int)DirectComposition::CBatchSharedMemoryPool::Create(
                    (struct DirectComposition::CBatchSharedMemoryPoolSet *)(v13 + 2648),
                    *(_BYTE *)(v13 + 2672),
                    &v35) < 0 )
          goto LABEL_26;
        j = v35;
        v18 = 0;
        if ( !*((_BYTE *)v35 + 64) && (unsigned __int64)(4096LL - *((_QWORD *)v35 + 5)) >= 0x228 )
        {
          v18 = *((_QWORD *)v35 + 5);
          *((_BYTE *)v35 + 64) = 1;
        }
        v21 = *(_QWORD *)v16;
        if ( *(struct DirectComposition::CBatchSharedMemoryPool **)(*(_QWORD *)v16 + 8LL) != v16 )
LABEL_15:
          __fastfail(3u);
        goto LABEL_17;
      }
      if ( !*((_BYTE *)j + 64) )
      {
        v18 = *((_QWORD *)j + 5);
        if ( (unsigned __int64)(4096 - v18) >= 0x228 )
          break;
      }
    }
    *((_BYTE *)j + 64) = 1;
    v19 = (struct DirectComposition::CBatchSharedMemoryPool **)*((_QWORD *)j + 1);
    if ( v19 == (struct DirectComposition::CBatchSharedMemoryPool **)v16 )
      goto LABEL_18;
    v20 = *(struct DirectComposition::CBatchSharedMemoryPool **)j;
    if ( *(struct DirectComposition::CBatchSharedMemoryPool **)(*(_QWORD *)j + 8LL) != j )
      goto LABEL_15;
    if ( *v19 != j )
      goto LABEL_15;
    *v19 = v20;
    *((_QWORD *)v20 + 1) = v19;
    v21 = *(_QWORD *)v16;
    if ( *(struct DirectComposition::CBatchSharedMemoryPool **)(*(_QWORD *)v16 + 8LL) != v16 )
      goto LABEL_15;
LABEL_17:
    *(_QWORD *)j = v21;
    *((_QWORD *)j + 1) = v16;
    *(_QWORD *)(v21 + 8) = j;
    *(_QWORD *)v16 = j;
LABEL_18:
    if ( !j )
      goto LABEL_26;
    v22 = *((_QWORD *)j + 5);
    if ( (unsigned __int64)(4096 - v22) >= 0x28 )
      *((_QWORD *)j + 5) = v22 + 40;
    v12 = *(struct DirectComposition::CBatch **)(v13 + 200);
    if ( v12 )
    {
      *(_QWORD *)(v13 + 200) = *(_QWORD *)v12;
    }
    else
    {
      if ( (int)DirectComposition::CApplicationChannel::CreateBatch((DirectComposition::CApplicationChannel *)v13, &v34) < 0
        && *(int *)(v13 + 252) > 0 )
      {
        v32 = 1;
        v33 = 0;
        while ( *(int *)(v13 + 252) > 0 )
        {
          if ( v33
            && DirectComposition::CConnection::ShouldWaitForReturnedBatches(*(DirectComposition::CConnection **)(v13 + 40))
            && KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v13 + 240) + 8LL), UserRequest, 0, 1u, 0) )
          {
            v32 = 0;
          }
          if ( DirectComposition::CApplicationChannel::ProcessReturnedBatches((DirectComposition::CApplicationChannel *)v13) )
          {
            v12 = *(struct DirectComposition::CBatch **)(v13 + 200);
            *(_QWORD *)(v13 + 200) = *(_QWORD *)v12;
            goto LABEL_23;
          }
          v33 = 1;
          if ( !v32 )
            break;
        }
      }
      v12 = v34;
    }
LABEL_23:
    if ( v12 )
    {
      *((_QWORD *)v12 + 18) = v18;
      v15 = v12;
      *((_QWORD *)v12 + 17) = j;
      goto LABEL_25;
    }
    *((_BYTE *)j + 64) = 0;
  }
LABEL_26:
  if ( v12 )
  {
    v24 = (struct DirectComposition::CBatch **)v36;
    *(_BYTE *)(v36[17] + 64LL) = 0;
    *v24 = v12;
    *a1 = v12;
    v25 = *((_QWORD *)v12 + 17);
    v26 = *(_QWORD *)(v25 + 40);
    v27 = 4096 - v26;
    if ( a3 )
    {
      if ( a2 <= v27 )
      {
        v28 = *(_QWORD *)(v25 + 56);
        *(_QWORD *)(v25 + 40) = v26 + a2;
        v29 = (void *)(v26 + v28);
        if ( v29 )
        {
          *a3 = v29;
          *((_QWORD *)v12 + 19) += a2;
          return 1;
        }
      }
    }
    else if ( a2 <= v27 )
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
0x1400547f0  mov     [rsp+arg_8], rbx
0x1400547f5  mov     [rsp+arg_0], rcx
0x1400547fa  push    rbp
0x1400547fb  push    rsi
0x1400547fc  push    rdi
0x1400547fd  push    r12
0x1400547ff  push    r13
0x140054801  push    r14
0x140054803  push    r15
0x140054805  sub     rsp, 50h
0x140054809  mov     r13, r8
0x14005480c  mov     r12, rdx
0x14005480f  mov     rdx, [rcx]
0x140054812  mov     ebp, 1000h
0x140054817  mov     eax, ebp
0x140054819  mov     r8, rcx
0x14005481c  mov     r9, [rdx+88h]
0x140054823  mov     r10, [r9+28h]
0x140054827  sub     rax, r10
0x14005482a  test    r13, r13
0x14005482d  jz      loc_140054B42
0x140054833  cmp     r12, rax
0x140054836  ja      short loc_14005484D
0x140054838  mov     rcx, [r9+38h]
0x14005483c  lea     rax, [r10+r12]
0x140054840  mov     [r9+28h], rax
0x140054844  add     rcx, r10
0x140054847  jnz     loc_140054926
0x14005484d  mov     rax, [r8]
0x140054850  xor     r15d, r15d
0x140054853  mov     [rsp+88h+var_48], rax
0x140054858  mov     edi, r15d
0x14005485b  mov     [rsp+88h+var_58], r15
0x140054860  mov     ecx, [rax+10h]
0x140054863  mov     rsi, [rax+8]
0x140054867  movzx   eax, byte ptr [rax+20h]
0x14005486b  mov     [rsp+88h+arg_18], ecx
0x140054872  mov     [rsp+88h+arg_10], al
0x140054879  mov     rcx, [rsi+0F0h]
0x140054880  mov     rcx, [rcx+8]; Event
0x140054884  call    cs:__imp_KeResetEvent
0x14005488b  nop     dword ptr [rax+rax+00h]
0x140054890  lea     rcx, [rsi+0D0h]; ListHead
0x140054897  call    cs:__imp_ExpInterlockedPopEntrySList
0x14005489e  nop     dword ptr [rax+rax+00h]
0x1400548a3  mov     rbx, rax
0x1400548a6  test    rax, rax
0x1400548a9  jnz     loc_140054A80
0x1400548af  mov     rdx, [rsi+0B8h]
0x1400548b6  test    rdx, rdx
0x1400548b9  jnz     loc_140054A52
0x1400548bf  lea     r14, [rsi+0A58h]
0x1400548c6  mov     [rsp+88h+var_50], r15
0x1400548cb  mov     rbx, [r14]
0x1400548ce  cmp     rbx, r14
0x1400548d1  jz      loc_140054BEF
0x1400548d7  cmp     [rbx+40h], dil
0x1400548db  jnz     short loc_1400548EF
0x1400548dd  mov     r15, [rbx+28h]
0x1400548e1  mov     rax, rbp
0x1400548e4  sub     rax, r15
0x1400548e7  cmp     rax, 228h
0x1400548ed  jnb     short loc_1400548F4
0x1400548ef  mov     rbx, [rbx]
0x1400548f2  jmp     short loc_1400548CE
0x1400548f4  mov     byte ptr [rbx+40h], 1
0x1400548f8  mov     rax, [rbx+8]
0x1400548fc  cmp     rax, r14
0x1400548ff  jz      short loc_140054944
0x140054901  mov     rcx, [rbx]
0x140054904  cmp     [rcx+8], rbx
0x140054908  jnz     short loc_14005491F
0x14005490a  cmp     [rax], rbx
0x14005490d  jnz     short loc_14005491F
0x14005490f  mov     [rax], rcx
0x140054912  mov     [rcx+8], rax
0x140054916  mov     rax, [r14]
0x140054919  cmp     [rax+8], r14
0x14005491d  jz      short loc_140054936
0x14005491f  mov     ecx, 3
0x140054924  int     29h; Win8: RtlFailFast(ecx)
0x140054926  mov     [r13+0], rcx
0x14005492a  add     [rdx+98h], r12
0x140054931  jmp     loc_140054A37
0x140054936  mov     [rbx], rax
0x140054939  mov     [rbx+8], r14
0x14005493d  mov     [rax+8], rbx
0x140054941  mov     [r14], rbx
0x140054944  test    rbx, rbx
0x140054947  jz      loc_1400549DC
0x14005494d  mov     rcx, [rbx+28h]
0x140054951  mov     rax, rbp
0x140054954  sub     rax, rcx
0x140054957  cmp     rax, 28h ; '('
0x14005495b  jb      short loc_140054965
0x14005495d  lea     rax, [rcx+28h]
0x140054961  mov     [rbx+28h], rax
0x140054965  mov     rdi, [rsi+0C8h]
0x14005496c  test    rdi, rdi
0x14005496f  jz      loc_140054B60
0x140054975  mov     rax, [rdi]
0x140054978  mov     [rsi+0C8h], rax
0x14005497f  test    rdi, rdi
0x140054982  jz      loc_140054B50
0x140054988  mov     [rdi+90h], r15
0x14005498f  mov     rdx, rdi
0x140054992  xor     r15d, r15d
0x140054995  mov     [rdi+88h], rbx
0x14005499c  mov     eax, [rsp+88h+arg_18]
0x1400549a3  mov     [rdx+10h], eax
0x1400549a6  movzx   eax, byte ptr [rdx+20h]
0x1400549aa  movzx   ecx, al
0x1400549ad  xor     cl, [rsp+88h+arg_10]
0x1400549b4  and     cl, 1
0x1400549b7  xor     cl, al
0x1400549b9  mov     [rdx+20h], cl
0x1400549bc  mov     [rdi], r15
0x1400549bf  inc     dword ptr [rsi+0FCh]
0x1400549c5  or      byte ptr [rsi+108h], 8
0x1400549cc  mov     rbx, [rsi+188h]
0x1400549d3  test    rbx, rbx
0x1400549d6  jnz     loc_140054ADB
0x1400549dc  test    rdi, rdi
0x1400549df  jz      loc_140054A78
0x1400549e5  mov     rcx, [rsp+88h+var_48]
0x1400549ea  mov     rax, [rcx+88h]
0x1400549f1  mov     byte ptr [rax+40h], 0
0x1400549f5  mov     rax, [rsp+88h+arg_0]
0x1400549fd  mov     [rcx], rdi
0x140054a00  mov     [rax], rdi
0x140054a03  mov     rcx, [rdi+88h]
0x140054a0a  mov     rdx, [rcx+28h]
0x140054a0e  sub     rbp, rdx
0x140054a11  test    r13, r13
0x140054a14  jz      short loc_140054A61
0x140054a16  cmp     r12, rbp
0x140054a19  ja      short loc_140054A66
0x140054a1b  mov     r8, [rcx+38h]
0x140054a1f  lea     rax, [rdx+r12]
0x140054a23  mov     [rcx+28h], rax
0x140054a27  add     r8, rdx
0x140054a2a  jz      short loc_140054A66
0x140054a2c  mov     [r13+0], r8
0x140054a30  add     [rdi+98h], r12
0x140054a37  mov     al, 1
0x140054a39  mov     rbx, [rsp+88h+arg_8]
0x140054a41  add     rsp, 50h
0x140054a45  pop     r15
0x140054a47  pop     r14
0x140054a49  pop     r13
0x140054a4b  pop     r12
0x140054a4d  pop     rdi
0x140054a4e  pop     rsi
0x140054a4f  pop     rbp
0x140054a50  retn
0x140054a52  mov     rdi, rdx
0x140054a55  mov     [rsi+0B8h], r15
0x140054a5c  jmp     loc_14005499C
0x140054a61  cmp     r12, rbp
0x140054a64  jbe     short loc_140054A37
0x140054a66  mov     ecx, 0C000000Dh; BugCheckCode
0x140054a6b  call    cs:__imp_KeBugCheck
0x140054a78  xor     al, al
0x140054a7a  jmp     short loc_140054A39
0x140054a80  dec     dword ptr [rsi+0FCh]
0x140054a86  mov     rax, [rbx+40h]
0x140054a8a  cmp     rax, [rsi+100h]
0x140054a91  jbe     short loc_140054AA1
0x140054a93  or      byte ptr [rsi+108h], 2
0x140054a9a  mov     [rsi+100h], rax
0x140054aa1  mov     rcx, rbx; this
0x140054aa4  call    ?Clear@CBatch@DirectComposition@@QEAAXXZ; DirectComposition::CBatch::Clear(void)
0x140054aa9  mov     rax, [rsi+0C8h]
0x140054ab0  lea     rcx, [rsi+0D0h]; ListHead
0x140054ab7  mov     [rbx], rax
0x140054aba  mov     [rsi+0C8h], rbx
0x140054ac1  call    cs:__imp_ExpInterlockedPopEntrySList
0x140054ac8  nop     dword ptr [rax+rax+00h]
0x140054acd  mov     rbx, rax
0x140054ad0  test    rax, rax
0x140054ad3  jz      loc_1400548AF
0x140054ad9  jmp     short loc_140054A80
0x140054adb  call    cs:__imp_KeEnterCriticalRegion
0x140054ae2  nop     dword ptr [rax+rax+00h]
0x140054ae7  mov     dl, 1; Wait
0x140054ae9  mov     rcx, rbx; Resource
0x140054aec  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140054af3  nop     dword ptr [rax+rax+00h]
0x140054af8  inc     dword ptr [rsi+0F8h]
0x140054afe  cmp     dword ptr [rsi+0F8h], 1
0x140054b05  jnz     short loc_140054B1E
0x140054b07  mov     rcx, [rsi+180h]
0x140054b0e  mov     rcx, [rcx+8]; Event
0x140054b12  call    cs:__imp_KeResetEvent
0x140054b19  nop     dword ptr [rax+rax+00h]
0x140054b1e  mov     rcx, [rsi+188h]; Resource
0x140054b25  call    cs:__imp_ExReleaseResourceLite
0x140054b2c  nop     dword ptr [rax+rax+00h]
0x140054b31  call    cs:__imp_KeLeaveCriticalRegion
0x140054b38  nop     dword ptr [rax+rax+00h]
0x140054b3d  jmp     loc_1400549DC
0x140054b42  cmp     r12, rax
0x140054b45  ja      loc_14005484D
0x140054b4b  jmp     loc_140054A37
0x140054b50  mov     byte ptr [rbx+40h], 0
0x140054b54  jmp     loc_1400549DC
0x140054b60  lea     rdx, [rsp+88h+var_58]; struct DirectComposition::CBatch **
0x140054b65  mov     rcx, rsi; this
0x140054b68  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x140054b6d  test    eax, eax
0x140054b6f  js      short loc_140054B7B
0x140054b71  mov     rdi, [rsp+88h+var_58]
0x140054b76  jmp     loc_14005497F
0x140054b7b  cmp     dword ptr [rsi+0FCh], 0
0x140054b82  jle     short loc_140054B71
0x140054b84  mov     dil, 1
0x140054b87  xor     al, al
0x140054b89  cmp     dword ptr [rsi+0FCh], 0
0x140054b90  jle     short loc_140054B71
0x140054b92  test    al, al
0x140054b94  jz      short loc_140054BDA
0x140054b96  mov     rcx, [rsi+28h]; this
0x140054b9a  call    ?ShouldWaitForReturnedBatches@CConnection@DirectComposition@@QEAA_NXZ; DirectComposition::CConnection::ShouldWaitForReturnedBatches(void)
0x140054b9f  test    al, al
0x140054ba1  jz      short loc_140054BDA
0x140054ba3  mov     rcx, [rsi+0F0h]
0x140054baa  mov     r9b, 1; Alertable
0x140054bad  xor     r8d, r8d; WaitMode
0x140054bb0  mov     [rsp+88h+Timeout], 0; Timeout
0x140054bb9  mov     edx, 6; WaitReason
0x140054bbe  mov     rcx, [rcx+8]; Object
0x140054bc2  call    cs:__imp_KeWaitForSingleObject
0x140054bc9  nop     dword ptr [rax+rax+00h]
0x140054bce  test    eax, eax
0x140054bd0  jz      short loc_140054BDA
0x140054bd2  sub     eax, 0C0h
0x140054bd7  xor     dil, dil
0x140054bda  mov     rcx, rsi; this
0x140054bdd  call    ?ProcessReturnedBatches@CApplicationChannel@DirectComposition@@IEAA_NXZ; DirectComposition::CApplicationChannel::ProcessReturnedBatches(void)
0x140054be2  test    al, al
0x140054be4  jnz     short loc_140054C42
0x140054be6  mov     al, 1
0x140054be8  test    dil, dil
0x140054beb  jnz     short loc_140054B89
0x140054bed  jmp     short loc_140054B71
0x140054bef  movzx   edx, byte ptr [r14+18h]; bool
0x140054bf4  lea     r8, [rsp+88h+var_50]; struct DirectComposition::CBatchSharedMemoryPool **
0x140054bf9  mov     rcx, r14; struct DirectComposition::CBatchSharedMemoryPoolSet *
0x140054bfc  call    ?Create@CBatchSharedMemoryPool@DirectComposition@@SAJPEAVCBatchSharedMemoryPoolSet@2@_NPEAPEAV12@@Z; DirectComposition::CBatchSharedMemoryPool::Create(DirectComposition::CBatchSharedMemoryPoolSet *,bool,DirectComposition::CBatchSharedMemoryPool * *)
0x140054c01  test    eax, eax
0x140054c03  js      loc_1400549DC
0x140054c09  mov     rbx, [rsp+88h+var_50]
0x140054c0e  xor     r15d, r15d
0x140054c11  cmp     [rbx+40h], dil
0x140054c15  jnz     short loc_140054C30
0x140054c17  mov     rcx, [rbx+28h]
0x140054c1b  mov     rax, rbp
0x140054c1e  sub     rax, rcx
0x140054c21  cmp     rax, 228h
0x140054c27  jb      short loc_140054C30
0x140054c29  mov     r15, rcx
0x140054c2c  mov     byte ptr [rbx+40h], 1
0x140054c30  mov     rax, [r14]
0x140054c33  cmp     [rax+8], r14
0x140054c37  jnz     loc_14005491F
0x140054c3d  jmp     loc_140054936
0x140054c42  mov     rdi, [rsi+0C8h]
0x140054c49  mov     rax, [rdi]
0x140054c4c  mov     [rsi+0C8h], rax
0x140054c53  jmp     loc_14005497F
```
