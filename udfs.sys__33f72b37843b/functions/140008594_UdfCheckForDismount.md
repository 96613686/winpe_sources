# UdfCheckForDismount

- ea: `0x140008594`
- end: `0x140008783`
- name: `UdfCheckForDismount`
- size: `495`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: ``

## callers

- `0x140008790`
- `0x140009b94`
- `0x140035ca4`
- `0x1400375d8`
- `0x140037770`
- `0x14003787c`
- `0x14003a7a4`
- `0x14004b734`
- `0x140053260`
- `0x140055060`

## callees

- `0x140008594`
- `0x140008790`
- `0x14000ca54`
- `0x140010b14`
- `0x140018740`
- `0x14002c008`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000875c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000875c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400085e7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400085e7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008662`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400086c9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008748`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008662`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400086c9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008748`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140008696`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140008696`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400086af`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400086e8`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400086af`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400086e8`

## pseudocode

```c
char __fastcall UdfCheckForDismount(__int64 a1, __int64 a2, char a3)
{
  struct _ERESOURCE *v3; // r12
  char v6; // si
  char v8; // di
  __int64 v9; // r9
  bool v10; // zf
  KIRQL Irql; // [rsp+58h] [rbp+10h] BYREF

  v3 = (struct _ERESOURCE *)(a2 + 1480);
  Irql = 0;
  v6 = 1;
  v8 = 1;
  UdfAcquireResource(a1, a2 + 1480, 0, 0);
  UdfFspClose(a2);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  v10 = *(_DWORD *)(a2 + 52) == 4;
  *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
  if ( v10 )
  {
    if ( !*(_DWORD *)(a2 + 256) )
    {
      IoAcquireVpbSpinLock(&Irql);
      if ( *(_DWORD *)(*(_QWORD *)(a2 + 8) + 28LL) == 1 )
      {
        IoReleaseVpbSpinLock(Irql);
        *(_QWORD *)(a2 + 1640) = 0;
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
        v6 = 0;
        UdfDeleteVcb(a1, a2);
        v8 = 0;
      }
      else
      {
        IoReleaseVpbSpinLock(Irql);
      }
    }
  }
  else if ( *(_DWORD *)(a2 + 260) <= *(_DWORD *)(a2 + 268) || a3 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) != 0 )
    {
      WPP_SF_q(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        13,
        WPP_cfa131fbcd1c3915a000ec1f7ee12854_Traceguids,
        a2);
    }
    *(_QWORD *)(a2 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
    v6 = 0;
    v8 = UdfDismountVcb(a1);
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200000) != 0 )
  {
    LOBYTE(v9) = v8 != 0 ? 89 : 78;
    WPP_SF_c(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      14,
      WPP_cfa131fbcd1c3915a000ec1f7ee12854_Traceguids,
      v9);
  }
  if ( v6 )
  {
    *(_QWORD *)(a2 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  }
  if ( v8 )
    ExReleaseResourceLite(v3);
  return v8;
}

```

## disassembly

```asm
0x140008594  mov     [rsp+arg_0], rbx
0x140008599  mov     [rsp+arg_10], rbp
0x14000859e  push    rsi
0x14000859f  push    rdi
0x1400085a0  push    r12
0x1400085a2  push    r14
0x1400085a4  push    r15
0x1400085a6  sub     rsp, 20h
0x1400085aa  lea     r12, [rdx+5C8h]
0x1400085b1  mov     [rsp+48h+Irql], 0
0x1400085b6  mov     r14b, r8b
0x1400085b9  mov     rbx, rdx
0x1400085bc  mov     esi, 1
0x1400085c1  mov     rdx, r12
0x1400085c4  xor     r9d, r9d
0x1400085c7  xor     r8d, r8d
0x1400085ca  mov     r15, rcx
0x1400085cd  mov     dil, sil
0x1400085d0  call    UdfAcquireResource
0x1400085d5  mov     rcx, rbx
0x1400085d8  call    UdfFspClose
0x1400085dd  lea     rbp, [rbx+630h]
0x1400085e4  mov     rcx, rbp; FastMutex
0x1400085e7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400085ee  nop     dword ptr [rax+rax+00h]
0x1400085f3  mov     rax, gs:188h
0x1400085fc  cmp     dword ptr [rbx+34h], 4
0x140008600  mov     [rbx+668h], rax
0x140008607  jz      short loc_140008688
0x140008609  mov     eax, [rbx+10Ch]
0x14000860f  cmp     [rbx+104h], eax
0x140008615  jbe     short loc_140008620
0x140008617  test    r14b, r14b
0x14000861a  jz      loc_1400086F4
0x140008620  mov     rcx, cs:WPP_GLOBAL_Control
0x140008627  lea     rax, WPP_GLOBAL_Control
0x14000862e  cmp     rcx, rax
0x140008631  jz      short loc_140008654
0x140008633  test    dword ptr [rcx+2Ch], 200000h
0x14000863a  jz      short loc_140008654
0x14000863c  mov     rcx, [rcx+18h]
0x140008640  lea     r8, WPP_cfa131fbcd1c3915a000ec1f7ee12854_Traceguids
0x140008647  mov     edx, 0Dh
0x14000864c  mov     r9, rbx
0x14000864f  call    WPP_SF_q
0x140008654  mov     rcx, rbp; FastMutex
0x140008657  mov     qword ptr [rbx+668h], 0
0x140008662  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140008669  nop     dword ptr [rax+rax+00h]
0x14000866e  xor     sil, sil
0x140008671  mov     rdx, rbx
0x140008674  test    r14b, r14b
0x140008677  mov     rcx, r15
0x14000867a  setz    r8b
0x14000867e  call    UdfDismountVcb
0x140008683  mov     dil, al
0x140008686  jmp     short loc_1400086F4
0x140008688  cmp     dword ptr [rbx+100h], 0
0x14000868f  jnz     short loc_1400086F4
0x140008691  lea     rcx, [rsp+48h+Irql]; Irql
0x140008696  call    cs:__imp_IoAcquireVpbSpinLock
0x14000869d  nop     dword ptr [rax+rax+00h]
0x1400086a2  mov     rax, [rbx+8]
0x1400086a6  mov     cl, [rsp+48h+Irql]; Irql
0x1400086aa  cmp     [rax+1Ch], esi
0x1400086ad  jnz     short loc_1400086E8
0x1400086af  call    cs:__imp_IoReleaseVpbSpinLock
0x1400086b6  nop     dword ptr [rax+rax+00h]
0x1400086bb  mov     rcx, rbp; FastMutex
0x1400086be  mov     qword ptr [rbx+668h], 0
0x1400086c9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400086d0  nop     dword ptr [rax+rax+00h]
0x1400086d5  mov     rdx, rbx
0x1400086d8  mov     rcx, r15
0x1400086db  xor     sil, sil
0x1400086de  call    UdfDeleteVcb
0x1400086e3  xor     dil, dil
0x1400086e6  jmp     short loc_1400086F4
0x1400086e8  call    cs:__imp_IoReleaseVpbSpinLock
0x1400086ef  nop     dword ptr [rax+rax+00h]
0x1400086f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086fb  lea     rax, WPP_GLOBAL_Control
0x140008702  cmp     rcx, rax
0x140008705  jz      short loc_140008735
0x140008707  test    dword ptr [rcx+2Ch], 200000h
0x14000870e  jz      short loc_140008735
0x140008710  mov     rcx, [rcx+18h]
0x140008714  lea     r8, WPP_cfa131fbcd1c3915a000ec1f7ee12854_Traceguids
0x14000871b  mov     al, dil
0x14000871e  mov     edx, 0Eh
0x140008723  neg     al
0x140008725  sbb     r9b, r9b
0x140008728  and     r9b, 0Bh
0x14000872c  add     r9b, 4Eh ; 'N'
0x140008730  call    WPP_SF_c
0x140008735  test    sil, sil
0x140008738  jz      short loc_140008754
0x14000873a  mov     rcx, rbp; FastMutex
0x14000873d  mov     qword ptr [rbx+668h], 0
0x140008748  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000874f  nop     dword ptr [rax+rax+00h]
0x140008754  test    dil, dil
0x140008757  jz      short loc_140008768
0x140008759  mov     rcx, r12; Resource
0x14000875c  call    cs:__imp_ExReleaseResourceLite
0x140008763  nop     dword ptr [rax+rax+00h]
0x140008768  mov     rbx, [rsp+48h+arg_0]
0x14000876d  mov     al, dil
0x140008770  mov     rbp, [rsp+48h+arg_10]
0x140008775  add     rsp, 20h
0x140008779  pop     r15
0x14000877b  pop     r14
0x14000877d  pop     r12
0x14000877f  pop     rdi
0x140008780  pop     rsi
0x140008781  retn
```
