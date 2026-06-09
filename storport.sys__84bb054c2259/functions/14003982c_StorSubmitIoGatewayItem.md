# StorSubmitIoGatewayItem

- ea: `0x14003982c`
- end: `0x140039cb2`
- name: `StorSubmitIoGatewayItem`
- size: `1158`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140014420`
- `0x140021bf0`
- `0x14002c1c0`
- `0x14002e3d0`
- `0x1400343e0`

## callees

- `0x14002d780`
- `0x14003982c`
- `0x140039cb8`
- `0x14004a580`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400398d9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140039a75`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140039b81`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400398d9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140039a75`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140039b81`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140039b24`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140039b24`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039a91`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039bf8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039a91`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039bf8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039ab5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039afb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039ab5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039afb`

## pseudocode

```c
char __fastcall StorSubmitIoGatewayItem(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbx
  ULONG v7; // r9d
  __int64 v8; // rbx
  _QWORD *v9; // rsi
  int v10; // r9d
  unsigned int v11; // r8d
  __int64 v12; // rax
  int v13; // r15d
  PSLIST_ENTRY IoResource; // rdx
  unsigned int v15; // ecx
  PSLIST_ENTRY v16; // rbx
  void *v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rdi
  char result; // al
  _QWORD *v21; // rcx
  unsigned int v22; // ebx
  ULONG v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // r14d
  PSLIST_ENTRY v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rbx
  _QWORD *v30; // rdx
  _QWORD *v31; // rax
  _QWORD *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rbx
  _QWORD *v36; // rdx
  _QWORD *v37; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-58h] BYREF

  v3 = *(_QWORD *)(a1 + 48);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v7 = 0;
  if ( *(_DWORD *)(v3 + 1032) > 1u )
  {
    v22 = *(_DWORD *)(v3 + 1040);
    v7 = KeGetCurrentProcessorNumberEx(0) / v22;
    v23 = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 1032LL);
    if ( v7 >= v23 )
      v7 %= v23;
  }
  v8 = a1 + 320LL * v7;
  if ( v8 && *(_DWORD *)(*(_QWORD *)(v8 + 48) + 1052LL) || *(_DWORD *)(v8 + 40) )
  {
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v8, &LockHandle);
    if ( (unsigned __int8)StorIsIoGatewayPaused(v8) || *(_DWORD *)(v8 + 40) )
    {
      v21 = *(_QWORD **)(v8 + 16);
      if ( *v21 != v8 + 8 )
        goto LABEL_19;
      *(_QWORD *)a2 = v8 + 8;
      *(_QWORD *)(a2 + 8) = v21;
      *v21 = a2;
      *(_QWORD *)(v8 + 16) = a2;
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 24));
      if ( (*(_BYTE *)(a2 + 22) & 0x20) != 0 )
      {
        v27 = 96;
        v28 = *(_QWORD *)(*(_QWORD *)(a2 + 64) + 8LL);
        if ( *(_BYTE *)(v28 + 2) != 40 )
          v27 = 48;
        v29 = v8 + 264;
        v30 = *(_QWORD **)(v29 + 8);
        if ( *v30 != v29 )
          goto LABEL_19;
        v31 = (_QWORD *)(*(_QWORD *)(v27 + v28) + 24LL);
        v31[1] = v30;
        *v31 = v29;
        *v30 = v31;
        *(_QWORD *)(v29 + 8) = v31;
      }
LABEL_21:
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      return 1;
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v9 = (_QWORD *)(v8 + 64);
  v10 = *(_DWORD *)(v8 + 128);
  if ( v10 )
  {
    v11 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 152) + 64LL) + 1040LL);
    v12 = v10 * (HIDWORD(KeGetPcr()[1].LockArray) % v11) / v11;
    v13 = v12;
    IoResource = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*v9 + 8 * v12));
    if ( !IoResource )
    {
      v24 = *(_DWORD *)(v8 + 128);
      if ( v24 <= 1 )
        goto LABEL_8;
      v25 = 1;
      while ( !IoResource )
      {
        v26 = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*v9 + 8LL * ((v25 + v13) % v24)));
        v24 = *(_DWORD *)(v8 + 128);
        ++v25;
        IoResource = v26;
        if ( v25 >= v24 )
        {
          if ( v26 )
            break;
          goto LABEL_8;
        }
      }
    }
    LODWORD(IoResource->Next) = v13;
  }
  else
  {
    IoResource = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v8 + 64));
  }
LABEL_8:
  if ( !IoResource )
  {
    if ( *(_DWORD *)(v8 + 136) >= *(_DWORD *)(v8 + 144)
      || (RaAttemptHighWaterMarkIncrease((PVOID)v8), (IoResource = (PSLIST_ENTRY)RaAllocateIoResource(v8 + 64)) == 0) )
    {
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v8, &LockHandle);
      v32 = *(_QWORD **)(v8 + 16);
      if ( *v32 != v8 + 8 )
        goto LABEL_19;
      *(_QWORD *)a2 = v8 + 8;
      *(_QWORD *)(a2 + 8) = v32;
      *v32 = a2;
      *(_QWORD *)(v8 + 16) = a2;
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 24));
      *(_DWORD *)(v8 + 40) = 1699901262;
      if ( (*(_BYTE *)(a2 + 22) & 0x20) != 0 )
      {
        v33 = 96;
        v34 = *(_QWORD *)(*(_QWORD *)(a2 + 64) + 8LL);
        if ( *(_BYTE *)(v34 + 2) != 40 )
          v33 = 48;
        v35 = v8 + 264;
        v36 = *(_QWORD **)(v35 + 8);
        if ( *v36 == v35 )
        {
          v37 = (_QWORD *)(*(_QWORD *)(v33 + v34) + 24LL);
          v37[1] = v36;
          *v37 = v35;
          *v36 = v37;
          *(_QWORD *)(v35 + 8) = v37;
          goto LABEL_21;
        }
LABEL_19:
        __fastfail(3u);
      }
      goto LABEL_21;
    }
  }
  v15 = *(_DWORD *)(v8 + 36);
  if ( _InterlockedIncrement((volatile signed __int32 *)(v8 + 192)) >= v15 )
    *(_DWORD *)(v8 + 36) = *(_DWORD *)(v8 + 192);
  v16 = IoResource + 3;
  a3[2] = IoResource + 3;
  a3[3] = IoResource + 59;
  a3[1] = IoResource + 75;
  v17 = (void *)*((_QWORD *)&IoResource[50].Next + 1);
  v18 = *((_DWORD *)&IoResource[49].Next + 2);
  LOBYTE(IoResource[4].Next) &= 0x9Cu;
  v19 = *((_QWORD *)&IoResource[52].Next + 1);
  LODWORD(IoResource[3].Next) = 523124044;
  *((_QWORD *)&IoResource[3].Next + 1) = 0;
  WORD2(IoResource[4].Next) = -1;
  BYTE6(IoResource[4].Next) = -1;
  *((_DWORD *)&IoResource[4].Next + 2) = 0;
  *((_QWORD *)&IoResource[9].Next + 1) = 0;
  IoResource[10].Next = 0;
  *((_QWORD *)&IoResource[11].Next + 1) = 0;
  *((_QWORD *)&IoResource[12].Next + 1) = 0;
  IoResource[12].Next = 0;
  IoResource[15].Next = 0;
  IoResource[13].Next = 0;
  *((_QWORD *)&IoResource[13].Next + 1) = 0;
  *((_QWORD *)&IoResource[16].Next + 1) = 0;
  IoResource[17].Next = 0;
  *((_QWORD *)&IoResource[10].Next + 1) = 0;
  *((_QWORD *)&IoResource[46].Next + 1) = 0;
  IoResource[47].Next = 0;
  *((_QWORD *)&IoResource[47].Next + 1) = 0;
  IoResource[48].Next = 0;
  *((_DWORD *)&IoResource[49].Next + 2) = v18;
  *((_QWORD *)&IoResource[50].Next + 1) = v17;
  if ( v17 )
    memset_0(v17, 0, v18);
  LOBYTE(v16[1].Next) &= ~0x80u;
  BYTE1(v16[1].Next) &= 0x70u;
  LODWORD(v16[50].Next) = -1;
  result = 0;
  v16[48].Next = 0;
  *((_DWORD *)&v16[46].Next + 3) = 0;
  *((_DWORD *)&v16[48].Next + 2) = 0;
  *((_QWORD *)&v16[49].Next + 1) = v19;
  *((_WORD *)&v16[48].Next + 6) = -1;
  v16[49].Next = 0;
  *((_DWORD *)&v16[50].Next + 2) = 0;
  LODWORD(v16[51].Next) = 0;
  *((_QWORD *)&v16[51].Next + 1) = 0;
  v16[52] = 0;
  v16[53].Next = 0;
  *((_QWORD *)&v16[53].Next + 1) = 0;
  v16[54].Next = 0;
  *((_QWORD *)&v16[54].Next + 1) = 0;
  LODWORD(v16[55].Next) = -1;
  return result;
}

```

## disassembly

```asm
0x14003982c  push    rbx
0x14003982e  push    rbp
0x14003982f  push    rsi
0x140039830  push    rdi
0x140039831  push    r12
0x140039833  push    r14
0x140039835  push    r15
0x140039837  sub     rsp, 40h
0x14003983b  mov     rbx, [rcx+30h]
0x14003983f  xor     eax, eax
0x140039841  xor     r12d, r12d
0x140039844  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x140039849  xorps   xmm0, xmm0
0x14003984c  mov     rbp, r8
0x14003984f  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140039854  cmp     dword ptr [rbx+408h], 1
0x14003985b  mov     rdi, rdx
0x14003985e  mov     rsi, rcx
0x140039861  mov     r9d, r12d
0x140039864  ja      loc_140039B1C
0x14003986a  mov     eax, r9d
0x14003986d  lea     rbx, [rax+rax*4]
0x140039871  shl     rbx, 6
0x140039875  add     rbx, rsi
0x140039878  jz      short loc_14003988C
0x14003987a  mov     rax, [rbx+30h]
0x14003987e  mov     ecx, [rax+41Ch]
0x140039884  test    ecx, ecx
0x140039886  jnz     loc_140039A89
0x14003988c  mov     eax, [rbx+28h]
0x14003988f  test    eax, eax
0x140039891  jnz     loc_140039A89
0x140039897  lea     rsi, [rbx+40h]
0x14003989b  mov     r9d, [rsi+40h]
0x14003989f  test    r9d, r9d
0x1400398a2  jz      loc_140039A72
0x1400398a8  mov     rax, [rsi+58h]
0x1400398ac  xor     edx, edx
0x1400398ae  mov     rcx, [rax+40h]
0x1400398b2  mov     eax, gs:1A4h
0x1400398ba  mov     r8d, [rcx+410h]
0x1400398c1  mov     rcx, [rsi]
0x1400398c4  div     r8d
0x1400398c7  mov     eax, edx
0x1400398c9  xor     edx, edx
0x1400398cb  imul    eax, r9d
0x1400398cf  div     r8d
0x1400398d2  mov     r15d, eax
0x1400398d5  mov     rcx, [rcx+rax*8]; ListHead
0x1400398d9  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400398e0  nop     dword ptr [rax+rax+00h]
0x1400398e5  mov     rdx, rax
0x1400398e8  test    rax, rax
0x1400398eb  jz      loc_140039B59
0x1400398f1  mov     [rdx], r15d
0x1400398f4  test    rdx, rdx
0x1400398f7  jz      loc_140039C7F
0x1400398fd  mov     ecx, [rbx+24h]
0x140039900  mov     eax, 1
0x140039905  lock xadd [rbx+0C0h], eax
0x14003990d  inc     eax
0x14003990f  cmp     eax, ecx
0x140039911  jnb     loc_140039B0E
0x140039917  lea     rbx, [rdx+30h]
0x14003991b  mov     esi, 0FFFFh
0x140039920  mov     [rbp+10h], rbx
0x140039924  lea     rax, [rdx+3B0h]
0x14003992b  mov     [rbp+18h], rax
0x14003992f  lea     rax, [rdx+4B0h]
0x140039936  mov     [rbp+8], rax
0x14003993a  mov     rcx, [rdx+328h]; void *
0x140039941  mov     eax, [rdx+318h]
0x140039947  and     byte ptr [rbx+10h], 9Ch
0x14003994b  mov     rdi, [rbx+318h]
0x140039952  mov     dword ptr [rbx], 1F2E3D4Ch
0x140039958  mov     [rbx+8], r12
0x14003995c  mov     [rbx+14h], si
0x140039960  mov     byte ptr [rbx+16h], 0FFh
0x140039964  mov     [rbx+18h], r12d
0x140039968  mov     [rbx+68h], r12
0x14003996c  mov     [rbx+70h], r12
0x140039970  mov     [rbx+88h], r12
0x140039977  mov     [rbx+98h], r12
0x14003997e  mov     [rbx+90h], r12
0x140039985  mov     [rbx+0C0h], r12
0x14003998c  mov     [rbx+0A0h], r12
0x140039993  mov     [rbx+0A8h], r12
0x14003999a  mov     [rbx+0D8h], r12
0x1400399a1  mov     [rbx+0E0h], r12
0x1400399a8  mov     [rbx+78h], r12
0x1400399ac  mov     [rbx+2B8h], r12
0x1400399b3  mov     [rbx+2C0h], r12
0x1400399ba  mov     [rbx+2C8h], r12
0x1400399c1  mov     [rbx+2D0h], r12
0x1400399c8  mov     [rbx+2E8h], eax
0x1400399ce  mov     [rbx+2F8h], rcx
0x1400399d5  test    rcx, rcx
0x1400399d8  jz      short loc_1400399E4
0x1400399da  mov     r8d, eax; Size
0x1400399dd  xor     edx, edx; Val
0x1400399df  call    memset_0
0x1400399e4  and     byte ptr [rbx+10h], 7Fh
0x1400399e8  or      ecx, 0FFFFFFFFh
0x1400399eb  and     byte ptr [rbx+11h], 70h
0x1400399ef  xorps   xmm0, xmm0
0x1400399f2  mov     [rbx+320h], ecx
0x1400399f8  xor     al, al
0x1400399fa  mov     [rbx+300h], r12
0x140039a01  mov     [rbx+2ECh], r12d
0x140039a08  mov     [rbx+308h], r12d
0x140039a0f  mov     [rbx+318h], rdi
0x140039a16  mov     [rbx+30Ch], si
0x140039a1d  mov     [rbx+310h], r12
0x140039a24  mov     [rbx+328h], r12d
0x140039a2b  mov     [rbx+330h], r12d
0x140039a32  mov     [rbx+338h], r12
0x140039a39  movups  xmmword ptr [rbx+340h], xmm0
0x140039a40  mov     [rbx+350h], r12
0x140039a47  mov     [rbx+358h], r12
0x140039a4e  mov     [rbx+360h], r12
0x140039a55  mov     [rbx+368h], r12
0x140039a5c  mov     [rbx+370h], ecx
0x140039a62  add     rsp, 40h
0x140039a66  pop     r15
0x140039a68  pop     r14
0x140039a6a  pop     r12
0x140039a6c  pop     rdi
0x140039a6d  pop     rsi
0x140039a6e  pop     rbp
0x140039a6f  pop     rbx
0x140039a70  retn
0x140039a72  mov     rcx, rsi; ListHead
0x140039a75  call    cs:__imp_ExpInterlockedPopEntrySList
0x140039a7c  nop     dword ptr [rax+rax+00h]
0x140039a81  mov     rdx, rax
0x140039a84  jmp     loc_1400398F4
0x140039a89  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140039a8e  mov     rcx, rbx; SpinLock
0x140039a91  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140039a98  nop     dword ptr [rax+rax+00h]
0x140039a9d  mov     rcx, rbx
0x140039aa0  call    StorIsIoGatewayPaused
0x140039aa5  test    al, al
0x140039aa7  jnz     short loc_140039AC6
0x140039aa9  mov     eax, [rbx+28h]
0x140039aac  test    eax, eax
0x140039aae  jnz     short loc_140039AC6
0x140039ab0  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140039ab5  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140039abc  nop     dword ptr [rax+rax+00h]
0x140039ac1  jmp     loc_140039897
0x140039ac6  lea     rax, [rbx+8]
0x140039aca  mov     rcx, [rax+8]
0x140039ace  cmp     [rcx], rax
0x140039ad1  jz      short loc_140039ADA
0x140039ad3  mov     ecx, 3
0x140039ad8  int     29h; Win8: RtlFailFast(ecx)
0x140039ada  mov     [rdi], rax
0x140039add  mov     [rdi+8], rcx
0x140039ae1  mov     [rcx], rdi
0x140039ae4  mov     [rax+8], rdi
0x140039ae8  lock inc dword ptr [rbx+18h]
0x140039aec  test    byte ptr [rdi+16h], 20h
0x140039af0  jnz     loc_140039BA9
0x140039af6  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140039afb  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140039b02  nop     dword ptr [rax+rax+00h]
0x140039b07  mov     al, 1
0x140039b09  jmp     loc_140039A62
0x140039b0e  mov     eax, [rbx+0C0h]
0x140039b14  mov     [rbx+24h], eax
0x140039b17  jmp     loc_140039917
0x140039b1c  mov     ebx, [rbx+410h]
0x140039b22  xor     ecx, ecx; ProcNumber
0x140039b24  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140039b2b  nop     dword ptr [rax+rax+00h]
0x140039b30  xor     edx, edx
0x140039b32  div     ebx
0x140039b34  mov     r9d, eax
0x140039b37  mov     rax, [rsi+30h]
0x140039b3b  mov     ecx, [rax+408h]
0x140039b41  cmp     r9d, ecx
0x140039b44  jb      loc_14003986A
0x140039b4a  mov     eax, r9d
0x140039b4d  xor     edx, edx
0x140039b4f  div     ecx
0x140039b51  mov     r9d, edx
0x140039b54  jmp     loc_14003986A
0x140039b59  mov     ecx, [rsi+40h]
0x140039b5c  cmp     ecx, 1
0x140039b5f  jbe     loc_1400398F4
0x140039b65  mov     r14d, 1
0x140039b6b  test    rdx, rdx
0x140039b6e  jnz     loc_1400398F1
0x140039b74  lea     eax, [r14+r15]
0x140039b78  div     ecx
0x140039b7a  mov     rcx, [rsi]
0x140039b7d  mov     rcx, [rcx+rdx*8]; ListHead
0x140039b81  call    cs:__imp_ExpInterlockedPopEntrySList
0x140039b88  nop     dword ptr [rax+rax+00h]
0x140039b8d  mov     ecx, [rsi+40h]
0x140039b90  inc     r14d
0x140039b93  mov     rdx, rax
0x140039b96  cmp     r14d, ecx
0x140039b99  jb      short loc_140039B6B
0x140039b9b  test    rax, rax
0x140039b9e  jnz     loc_1400398F1
0x140039ba4  jmp     loc_1400398F4
0x140039ba9  mov     rax, [rdi+40h]
0x140039bad  mov     ecx, 60h ; '`'
0x140039bb2  mov     r8, [rax+8]
0x140039bb6  lea     eax, [rcx-30h]
0x140039bb9  cmp     byte ptr [r8+2], 28h ; '('
0x140039bbe  cmovnz  ecx, eax
0x140039bc1  add     rbx, 108h
0x140039bc8  mov     rdx, [rbx+8]
0x140039bcc  cmp     [rdx], rbx
0x140039bcf  jnz     loc_140039AD3
0x140039bd5  mov     rax, [rcx+r8]
0x140039bd9  add     rax, 18h
0x140039bdd  mov     [rax+8], rdx
0x140039be1  mov     [rax], rbx
0x140039be4  mov     [rdx], rax
0x140039be7  mov     [rbx+8], rax
0x140039beb  jmp     loc_140039AF6
0x140039bf0  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140039bf5  mov     rcx, rbx; SpinLock
0x140039bf8  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140039bff  nop     dword ptr [rax+rax+00h]
0x140039c04  lea     rax, [rbx+8]
0x140039c08  mov     rcx, [rax+8]
0x140039c0c  cmp     [rcx], rax
0x140039c0f  jnz     loc_140039AD3
0x140039c15  mov     [rdi], rax
0x140039c18  mov     [rdi+8], rcx
0x140039c1c  mov     [rcx], rdi
0x140039c1f  mov     [rax+8], rdi
0x140039c23  lock inc dword ptr [rbx+18h]
0x140039c27  mov     dword ptr [rbx+28h], 65526F4Eh
0x140039c2e  test    byte ptr [rdi+16h], 20h
0x140039c32  jz      loc_140039AF6
0x140039c38  mov     rax, [rdi+40h]
0x140039c3c  mov     ecx, 60h ; '`'
0x140039c41  mov     r8, [rax+8]
0x140039c45  lea     eax, [rcx-30h]
0x140039c48  cmp     byte ptr [r8+2], 28h ; '('
0x140039c4d  cmovnz  ecx, eax
0x140039c50  add     rbx, 108h
0x140039c57  mov     rdx, [rbx+8]
0x140039c5b  cmp     [rdx], rbx
0x140039c5e  jnz     loc_140039AD3
0x140039c64  mov     rcx, [rcx+r8]
0x140039c68  add     rcx, 18h
0x140039c6c  mov     [rcx+8], rdx
0x140039c70  mov     [rcx], rbx
0x140039c73  mov     [rdx], rcx
0x140039c76  mov     [rbx+8], rcx
0x140039c7a  jmp     loc_140039AF6
0x140039c7f  mov     eax, [rbx+90h]
0x140039c85  cmp     [rbx+88h], eax
0x140039c8b  jnb     loc_140039BF0
0x140039c91  mov     rcx, rbx; Context
0x140039c94  call    RaAttemptHighWaterMarkIncrease
0x140039c99  mov     rcx, rsi
0x140039c9c  call    RaAllocateIoResource
0x140039ca1  mov     rdx, rax
0x140039ca4  test    rax, rax
0x140039ca7  jnz     loc_1400398FD
0x140039cad  jmp     loc_140039BF0
```
