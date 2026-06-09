# TmpSetNotificationResourceManager

- ea: `0x14001c010`
- end: `0x14001c3e9`
- name: `TmpSetNotificationResourceManager`
- size: `985`
- prototype: `__int64 __usercall@<rax>(PRKEVENT Event@<rcx>, int, size_t Size, void *Src)`
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140011300`
- `0x140012960`
- `0x14001904c`
- `0x14001b658`
- `0x14001bad0`
- `0x14001bea0`

## callees

- `0x1400025c0`
- `0x140002640`
- `0x140002940`
- `0x1400122b8`
- `0x140012ba4`
- `0x14001c010`
- `0x1400209fc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001c053`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c135`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c1c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c2b1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c053`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c135`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c1c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c2b1`
- `ntoskrnl!KeReleaseMutex` at `0x14001c0ad`
- `ntoskrnl!KeReleaseMutex` at `0x14001c157`
- `ntoskrnl!KeReleaseMutex` at `0x14001c1ef`
- `ntoskrnl!KeReleaseMutex` at `0x14001c39f`
- `ntoskrnl!KeReleaseMutex` at `0x14001c3be`
- `ntoskrnl!KeReleaseMutex` at `0x14001c0ad`
- `ntoskrnl!KeReleaseMutex` at `0x14001c157`
- `ntoskrnl!KeReleaseMutex` at `0x14001c1ef`
- `ntoskrnl!KeReleaseMutex` at `0x14001c39f`
- `ntoskrnl!KeReleaseMutex` at `0x14001c3be`
- `ntoskrnl!ObfReferenceObject` at `0x14001c258`
- `ntoskrnl!ObfReferenceObject` at `0x14001c258`
- `ntoskrnl!KeSetEvent` at `0x14001c38e`
- `ntoskrnl!KeSetEvent` at `0x14001c38e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001c213`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001c213`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c076`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c076`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c09c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c09c`
- `ntoskrnl!KeInsertQueue` at `0x14001c37a`
- `ntoskrnl!KeInsertQueue` at `0x14001c37a`

## pseudocode

```c
__int64 __fastcall TmpSetNotificationResourceManager(
        PRKEVENT Event,
        __int64 a2,
        __int64 a3,
        struct _LIST_ENTRY *a4,
        unsigned int a5,
        size_t Size,
        void *Src)
{
  struct _KMUTANT *p_Blink; // rdi
  __int64 v11; // rcx
  __int64 v12; // rcx
  struct _LIST_ENTRY *Flink; // r10
  struct _LIST_ENTRY *v14; // rbx
  unsigned int v15; // esi
  size_t v17; // rbx
  unsigned int v18; // r14d
  bool v19; // zf
  struct _LIST_ENTRY *v20; // rdi
  struct _LIST_ENTRY *PoolWithTag; // rax
  unsigned int v22; // r15d
  const void *v23; // rdx
  PRKEVENT v24; // r14
  _QWORD *v25; // rax
  char *i; // rbx
  char *v27; // rax
  char **v28; // rcx
  int v29; // edx
  char v30; // si
  __int64 v31; // rcx
  char **v32; // rax
  __int64 v33; // r8
  struct _LIST_ENTRY *v34; // [rsp+78h] [rbp+10h] BYREF

  p_Blink = (struct _KMUTANT *)&Event[1].Header.WaitListHead.Blink;
  v34 = 0;
  KeWaitForSingleObject(&Event[1].Header.WaitListHead.Blink, Executive, 0, 0, 0);
  v11 = *(_QWORD *)&Event[15].Header.Lock;
  if ( !v11 )
  {
    KeReleaseMutex(p_Blink, 0);
    return 3222863953LL;
  }
  ExAcquireFastMutex((PFAST_MUTEX)(v11 + 592));
  v12 = *(_QWORD *)&Event[15].Header.Lock;
  v34 = *(struct _LIST_ENTRY **)(v12 + 584);
  ExReleaseFastMutex((PFAST_MUTEX)(v12 + 592));
  KeReleaseMutex(p_Blink, 0);
  Flink = Event[12].Header.WaitListHead.Flink;
  if ( Flink && ((__int64)Event[1].Header.WaitListHead.Flink & 1) == 0 )
  {
    v14 = v34;
    v15 = ((__int64 (__fastcall *)(__int64, struct _LIST_ENTRY *, struct _LIST_ENTRY *, _QWORD, struct _LIST_ENTRY **, _DWORD, void *))Flink)(
            a3,
            Event[12].Header.WaitListHead.Blink,
            a4,
            a5,
            &v34,
            Size,
            Src);
    if ( v14 != v34 )
    {
      KeWaitForSingleObject(p_Blink, Executive, 0, 0, 0);
      TmpAdjustVirtualClock(*(_QWORD *)&Event[15].Header.Lock, &v34);
      KeReleaseMutex(p_Blink, 0);
    }
    return v15;
  }
  v17 = (unsigned int)Size;
  if ( (unsigned int)Size >= 0xFFFFDFFF )
    return 3221225485LL;
  v18 = a5;
  if ( !a3 )
    goto LABEL_18;
  if ( (*(_DWORD *)(a3 + 172) & 1) != 0 )
  {
    if ( a5 == 64 )
      goto LABEL_15;
    v19 = a5 == 8;
  }
  else
  {
    v19 = ((a5 - 4) & 0xFFFFFFFB) == 0;
  }
  if ( !v19 )
  {
LABEL_18:
    PoolWithTag = (struct _LIST_ENTRY *)ExAllocatePoolWithTag((POOL_TYPE)512, (unsigned int)(v17 + 56), 0x6F4E6D54u);
    v20 = PoolWithTag;
    if ( !PoolWithTag )
      return 3221225626LL;
    memset(PoolWithTag, 0, (unsigned int)(v17 + 56));
    goto LABEL_21;
  }
LABEL_15:
  v20 = 0;
  KeWaitForSingleObject((PVOID)(a3 + 64), Executive, 0, 0, 0);
  if ( (*(_DWORD *)(a3 + 172) & 8) == 0 )
  {
    v20 = *(struct _LIST_ENTRY **)(a3 + 232);
    _InterlockedOr((volatile signed __int32 *)(a3 + 172), 8u);
  }
  KeReleaseMutex((PRKMUTEX)(a3 + 64), 0);
  if ( !v20 )
    goto LABEL_18;
LABEL_21:
  v22 = v17 + 32;
  if ( a3 && Event[12].Header.WaitListHead.Flink )
  {
    v20[1].Flink = (struct _LIST_ENTRY *)a3;
    ObfReferenceObject((PVOID)a3);
  }
  else
  {
    v20[1].Flink = 0;
  }
  v23 = Src;
  v20[1].Blink = a4;
  LODWORD(v20[2].Flink) = v18;
  v20[2].Blink = v34;
  LODWORD(v20[3].Flink) = v17;
  memmove(&v20[3].Blink, v23, v17);
  KeWaitForSingleObject(&Event[9], Executive, 0, 0, 0);
  v24 = Event + 23;
  while ( 1 )
  {
    v25 = *(_QWORD **)&v24->Header.Lock;
    if ( *(PRKEVENT *)&v24->Header.Lock == v24 )
      break;
    for ( i = *(char **)&v24->Header.Lock; ; i = *(char **)i )
    {
      if ( i == (char *)v24 )
        goto LABEL_35;
      if ( *((_DWORD *)i + 6) >= v22 )
        break;
    }
    if ( i )
    {
      v27 = *(char **)i;
      if ( *(char **)(*(_QWORD *)i + 8LL) != i )
        goto LABEL_45;
      v28 = (char **)*((_QWORD *)i + 1);
      if ( *v28 != i )
        goto LABEL_45;
      v29 = 0;
      *v28 = v27;
      v30 = 0;
      *((_QWORD *)v27 + 1) = v28;
    }
    else
    {
LABEL_35:
      v31 = *v25;
      i = *(char **)&v24->Header.Lock;
      if ( *(_QWORD **)(*v25 + 8LL) != v25 || (v32 = (char **)v25[1], *v32 != i) )
LABEL_45:
        __fastfail(3u);
      *v32 = (char *)v31;
      v29 = -1073741789;
      *(_QWORD *)(v31 + 8) = v32;
      v30 = 1;
    }
    v33 = 0;
    if ( !v30 )
      v33 = (__int64)v20;
    if ( (unsigned __int8)TmpQueueCompletionNotificationRequest((__int64)i, v29, v33, v22) )
    {
      if ( !v30 )
        goto LABEL_44;
      break;
    }
    *((_DWORD *)i + 8) = -1073741536;
    TmpCompleteNotificationRequestPacket(i, 0);
  }
  KeInsertQueue((PRKQUEUE)&Event[6].Header.WaitListHead, v20);
  KeSetEvent(Event, 0, 0);
LABEL_44:
  KeReleaseMutex((PRKMUTEX)&Event[9], 0);
  return 259;
}

```

## disassembly

```asm
0x14001c010  mov     rax, rsp
0x14001c013  mov     [rax+8], rbx
0x14001c017  mov     [rax+18h], rbp
0x14001c01b  mov     [rax+10h], rdx
0x14001c01f  push    rsi
0x14001c020  push    rdi
0x14001c021  push    r12
0x14001c023  push    r14
0x14001c025  push    r15
0x14001c027  sub     rsp, 40h
0x14001c02b  lea     rdi, [rcx+28h]
0x14001c02f  mov     qword ptr [rax+10h], 0
0x14001c037  mov     r12, r9
0x14001c03a  mov     qword ptr [rax-48h], 0
0x14001c042  mov     rsi, r8
0x14001c045  mov     rbp, rcx
0x14001c048  mov     rcx, rdi; Object
0x14001c04b  xor     r9d, r9d; Alertable
0x14001c04e  xor     r8d, r8d; WaitMode
0x14001c051  xor     edx, edx; WaitReason
0x14001c053  call    cs:__imp_KeWaitForSingleObject
0x14001c05a  nop     dword ptr [rax+rax+00h]
0x14001c05f  mov     rcx, [rbp+168h]
0x14001c066  test    rcx, rcx
0x14001c069  jz      loc_14001C3B9
0x14001c06f  add     rcx, 250h; FastMutex
0x14001c076  call    cs:__imp_ExAcquireFastMutex
0x14001c07d  nop     dword ptr [rax+rax+00h]
0x14001c082  mov     rcx, [rbp+168h]
0x14001c089  mov     rax, [rcx+248h]
0x14001c090  add     rcx, 250h; FastMutex
0x14001c097  mov     [rsp+68h+arg_8], rax
0x14001c09c  call    cs:__imp_ExReleaseFastMutex
0x14001c0a3  nop     dword ptr [rax+rax+00h]
0x14001c0a8  xor     edx, edx; Wait
0x14001c0aa  mov     rcx, rdi; Mutex
0x14001c0ad  call    cs:__imp_KeReleaseMutex
0x14001c0b4  nop     dword ptr [rax+rax+00h]
0x14001c0b9  mov     r10, [rbp+128h]
0x14001c0c0  test    r10, r10
0x14001c0c3  jz      loc_14001C16A
0x14001c0c9  mov     eax, [rbp+20h]
0x14001c0cc  test    al, 1
0x14001c0ce  jnz     loc_14001C16A
0x14001c0d4  mov     rcx, [rsp+68h+Src]
0x14001c0dc  lea     rax, [rsp+68h+arg_8]
0x14001c0e1  mov     r9d, [rsp+68h+arg_20]
0x14001c0e9  mov     r8, r12
0x14001c0ec  mov     rdx, [rbp+130h]
0x14001c0f3  mov     rbx, [rsp+68h+arg_8]
0x14001c0f8  mov     [rsp+68h+var_38], rcx
0x14001c0fd  mov     ecx, dword ptr [rsp+68h+Size]
0x14001c104  mov     [rsp+68h+var_40], ecx
0x14001c108  mov     rcx, rsi
0x14001c10b  mov     [rsp+68h+Timeout], rax
0x14001c110  mov     rax, r10
0x14001c113  call    _guard_dispatch_icall
0x14001c118  mov     esi, eax
0x14001c11a  cmp     rbx, [rsp+68h+arg_8]
0x14001c11f  jz      short loc_14001C163
0x14001c121  xor     r9d, r9d; Alertable
0x14001c124  mov     [rsp+68h+Timeout], 0; Timeout
0x14001c12d  xor     r8d, r8d; WaitMode
0x14001c130  xor     edx, edx; WaitReason
0x14001c132  mov     rcx, rdi; Object
0x14001c135  call    cs:__imp_KeWaitForSingleObject
0x14001c13c  nop     dword ptr [rax+rax+00h]
0x14001c141  mov     rcx, [rbp+168h]
0x14001c148  lea     rdx, [rsp+68h+arg_8]
0x14001c14d  call    TmpAdjustVirtualClock
0x14001c152  xor     edx, edx; Wait
0x14001c154  mov     rcx, rdi; Mutex
0x14001c157  call    cs:__imp_KeReleaseMutex
0x14001c15e  nop     dword ptr [rax+rax+00h]
0x14001c163  mov     eax, esi
0x14001c165  jmp     loc_14001C3CF
0x14001c16a  mov     ebx, dword ptr [rsp+68h+Size]
0x14001c171  cmp     ebx, 0FFFFDFFFh
0x14001c177  jb      short loc_14001C183
0x14001c179  mov     eax, 0C000000Dh
0x14001c17e  jmp     loc_14001C3CF
0x14001c183  mov     r14d, [rsp+68h+arg_20]
0x14001c18b  test    rsi, rsi
0x14001c18e  jz      short loc_14001C200
0x14001c190  mov     eax, [rsi+0ACh]
0x14001c196  test    al, 1
0x14001c198  jz      short loc_14001C1A6
0x14001c19a  cmp     r14d, 40h ; '@'
0x14001c19e  jz      short loc_14001C1B1
0x14001c1a0  cmp     r14d, 8
0x14001c1a4  jmp     short loc_14001C1AF
0x14001c1a6  lea     eax, [r14-4]
0x14001c1aa  test    eax, 0FFFFFFFBh
0x14001c1af  jnz     short loc_14001C200
0x14001c1b1  xor     edi, edi
0x14001c1b3  lea     rcx, [rsi+40h]; Object
0x14001c1b7  xor     r9d, r9d; Alertable
0x14001c1ba  mov     [rsp+68h+Timeout], rdi; Timeout
0x14001c1bf  xor     r8d, r8d; WaitMode
0x14001c1c2  xor     edx, edx; WaitReason
0x14001c1c4  call    cs:__imp_KeWaitForSingleObject
0x14001c1cb  nop     dword ptr [rax+rax+00h]
0x14001c1d0  mov     eax, [rsi+0ACh]
0x14001c1d6  test    al, 8
0x14001c1d8  jnz     short loc_14001C1E9
0x14001c1da  mov     rdi, [rsi+0E8h]
0x14001c1e1  lock or dword ptr [rsi+0ACh], 8
0x14001c1e9  xor     edx, edx; Wait
0x14001c1eb  lea     rcx, [rsi+40h]; Mutex
0x14001c1ef  call    cs:__imp_KeReleaseMutex
0x14001c1f6  nop     dword ptr [rax+rax+00h]
0x14001c1fb  test    rdi, rdi
0x14001c1fe  jnz     short loc_14001C23E
0x14001c200  lea     eax, [rbx+38h]
0x14001c203  mov     r8d, 6F4E6D54h; Tag
0x14001c209  mov     edx, eax; NumberOfBytes
0x14001c20b  mov     ecx, 200h; PoolType
0x14001c210  mov     r15d, eax
0x14001c213  call    cs:__imp_ExAllocatePoolWithTag
0x14001c21a  nop     dword ptr [rax+rax+00h]
0x14001c21f  mov     rdi, rax
0x14001c222  test    rax, rax
0x14001c225  jnz     short loc_14001C231
0x14001c227  mov     eax, 0C000009Ah
0x14001c22c  jmp     loc_14001C3CF
0x14001c231  mov     r8, r15; Size
0x14001c234  xor     edx, edx; Val
0x14001c236  mov     rcx, rax; void *
0x14001c239  call    memset
0x14001c23e  lea     r15d, [rbx+20h]
0x14001c242  test    rsi, rsi
0x14001c245  jz      short loc_14001C266
0x14001c247  cmp     qword ptr [rbp+128h], 0
0x14001c24f  jz      short loc_14001C266
0x14001c251  mov     rcx, rsi; Object
0x14001c254  mov     [rdi+10h], rsi
0x14001c258  call    cs:__imp_ObfReferenceObject
0x14001c25f  nop     dword ptr [rax+rax+00h]
0x14001c264  jmp     short loc_14001C26E
0x14001c266  mov     qword ptr [rdi+10h], 0
0x14001c26e  mov     rdx, [rsp+68h+Src]; Src
0x14001c276  lea     rcx, [rdi+38h]; void *
0x14001c27a  mov     [rdi+18h], r12
0x14001c27e  mov     r8, rbx; Size
0x14001c281  mov     [rdi+20h], r14d
0x14001c285  mov     rax, [rsp+68h+arg_8]
0x14001c28a  mov     [rdi+28h], rax
0x14001c28e  mov     [rdi+30h], ebx
0x14001c291  call    memmove
0x14001c296  lea     r12, [rbp+0D8h]
0x14001c29d  mov     [rsp+68h+Timeout], 0; Timeout
0x14001c2a6  mov     rcx, r12; Object
0x14001c2a9  xor     r9d, r9d; Alertable
0x14001c2ac  xor     r8d, r8d; WaitMode
0x14001c2af  xor     edx, edx; WaitReason
0x14001c2b1  call    cs:__imp_KeWaitForSingleObject
0x14001c2b8  nop     dword ptr [rax+rax+00h]
0x14001c2bd  lea     r14, [rbp+228h]
0x14001c2c4  mov     rax, [r14]
0x14001c2c7  cmp     rax, r14
0x14001c2ca  jz      loc_14001C370
0x14001c2d0  mov     rbx, rax
0x14001c2d3  cmp     rbx, r14
0x14001c2d6  jz      short loc_14001C310
0x14001c2d8  cmp     [rbx+18h], r15d
0x14001c2dc  jnb     short loc_14001C2E3
0x14001c2de  mov     rbx, [rbx]
0x14001c2e1  jmp     short loc_14001C2D3
0x14001c2e3  test    rbx, rbx
0x14001c2e6  jz      short loc_14001C310
0x14001c2e8  mov     rax, [rbx]
0x14001c2eb  cmp     [rax+8], rbx
0x14001c2ef  jnz     loc_14001C3B2
0x14001c2f5  mov     rcx, [rbx+8]
0x14001c2f9  cmp     [rcx], rbx
0x14001c2fc  jnz     loc_14001C3B2
0x14001c302  xor     edx, edx
0x14001c304  mov     [rcx], rax
0x14001c307  xor     sil, sil
0x14001c30a  mov     [rax+8], rcx
0x14001c30e  jmp     short loc_14001C33C
0x14001c310  mov     rcx, [rax]
0x14001c313  mov     rbx, rax
0x14001c316  cmp     [rcx+8], rax
0x14001c31a  jnz     loc_14001C3B2
0x14001c320  mov     rax, [rax+8]
0x14001c324  cmp     [rax], rbx
0x14001c327  jnz     loc_14001C3B2
0x14001c32d  mov     [rax], rcx
0x14001c330  mov     edx, 0C0000023h
0x14001c335  mov     [rcx+8], rax
0x14001c339  mov     sil, 1
0x14001c33c  xor     r8d, r8d
0x14001c33f  mov     r9d, r15d
0x14001c342  test    sil, sil
0x14001c345  mov     rcx, rbx
0x14001c348  cmovz   r8, rdi
0x14001c34c  call    TmpQueueCompletionNotificationRequest
0x14001c351  test    al, al
0x14001c353  jnz     short loc_14001C36B
0x14001c355  xor     edx, edx
0x14001c357  mov     dword ptr [rbx+20h], 0C0000120h
0x14001c35e  mov     rcx, rbx; P
0x14001c361  call    TmpCompleteNotificationRequestPacket
0x14001c366  jmp     loc_14001C2C4
0x14001c36b  test    sil, sil
0x14001c36e  jz      short loc_14001C39A
0x14001c370  lea     rcx, [rbp+98h]; Queue
0x14001c377  mov     rdx, rdi; Entry
0x14001c37a  call    cs:__imp_KeInsertQueue
0x14001c381  nop     dword ptr [rax+rax+00h]
0x14001c386  xor     r8d, r8d; Wait
0x14001c389  xor     edx, edx; Increment
0x14001c38b  mov     rcx, rbp; Event
0x14001c38e  call    cs:__imp_KeSetEvent
0x14001c395  nop     dword ptr [rax+rax+00h]
0x14001c39a  xor     edx, edx; Wait
0x14001c39c  mov     rcx, r12; Mutex
0x14001c39f  call    cs:__imp_KeReleaseMutex
0x14001c3a6  nop     dword ptr [rax+rax+00h]
0x14001c3ab  mov     eax, 103h
0x14001c3b0  jmp     short loc_14001C3CF
0x14001c3b2  mov     ecx, 3
0x14001c3b7  int     29h; Win8: RtlFailFast(ecx)
0x14001c3b9  xor     edx, edx; Wait
0x14001c3bb  mov     rcx, rdi; Mutex
0x14001c3be  call    cs:__imp_KeReleaseMutex
0x14001c3c5  nop     dword ptr [rax+rax+00h]
0x14001c3ca  mov     eax, 0C0190051h
0x14001c3cf  lea     r11, [rsp+68h+var_28]
0x14001c3d4  mov     rbx, [r11+30h]
0x14001c3d8  mov     rbp, [r11+40h]
0x14001c3dc  mov     rsp, r11
0x14001c3df  pop     r15
0x14001c3e1  pop     r14
0x14001c3e3  pop     r12
0x14001c3e5  pop     rdi
0x14001c3e6  pop     rsi
0x14001c3e7  retn
```
