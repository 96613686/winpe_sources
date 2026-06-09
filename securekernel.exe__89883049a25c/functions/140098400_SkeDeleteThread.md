# SkeDeleteThread

- ea: `0x140098400`
- end: `0x1400984d1`
- name: `SkeDeleteThread`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x140033b58`
- `0x14006b7a8`
- `0x1400afc38`
- `0x1400b0b38`

## callees

- `0x140002410`
- `0x1400202b0`
- `0x140029308`
- `0x140034154`
- `0x14003ac64`
- `0x140098400`
- `0x140098de4`
- `0x1400bb844`

## pseudocode

```c
__int64 __fastcall SkeDeleteThread(__int64 a1)
{
  __int64 i; // rdx
  __int64 v3; // rcx
  _QWORD *v4; // rcx
  __int64 *v5; // rdx

  for ( i = 0; (unsigned int)i < (unsigned int)SkeNumberProcessors; i = (unsigned int)(i + 1) )
  {
    v3 = SkeProcessorBlock[i];
    if ( *(_QWORD *)(v3 + 72) == a1 )
      *(_QWORD *)(v3 + 72) = 0;
  }
  SkiInvalidateThreadEntry(*(unsigned int *)(a1 + 168));
  SkReleaseRundownProtection(*(_QWORD *)(a1 + 72) + 80LL, 0);
  if ( KeGetCurrentIrql() != 2 )
    return SkiDeleteThread(a1);
  SkAcquireSpinLockExclusiveAtDpcLevel(&SkiThreadReaperLock);
  v4 = (_QWORD *)qword_14014EDD8;
  v5 = &SkiThreadReaperList;
  if ( *(__int64 **)qword_14014EDD8 != &SkiThreadReaperList )
    __fastfail(3u);
  *(_QWORD *)(a1 + 48) = &SkiThreadReaperList;
  *(_QWORD *)(a1 + 56) = v4;
  *v4 = a1 + 48;
  qword_14014EDD8 = a1 + 48;
  if ( !SkiThreadReaperWorkItem )
    SkQueueWorkItem(&SkiThreadReaperWorkItem);
  SkiThreadReaperLock = 0;
  SkTrackSpinLockRelease(v4, v5);
  return SkRequestWorkCallback();
}

```

## disassembly

```asm
0x140098400  push    rbx
0x140098402  sub     rsp, 20h
0x140098406  xor     edx, edx
0x140098408  mov     rbx, rcx
0x14009840b  cmp     cs:SkeNumberProcessors, edx
0x140098411  jbe     short loc_140098439
0x140098413  lea     rcx, SkeProcessorBlock
0x14009841a  mov     rcx, [rcx+rdx*8]
0x14009841e  mov     rax, [rcx+48h]
0x140098422  cmp     rax, rbx
0x140098425  jnz     short loc_14009842F
0x140098427  mov     qword ptr [rcx+48h], 0
0x14009842f  inc     edx
0x140098431  cmp     edx, cs:SkeNumberProcessors
0x140098437  jb      short loc_140098413
0x140098439  mov     ecx, [rbx+0A8h]
0x14009843f  call    SkiInvalidateThreadEntry
0x140098444  mov     rcx, [rbx+48h]
0x140098448  xor     edx, edx
0x14009844a  add     rcx, 50h ; 'P'
0x14009844e  call    SkReleaseRundownProtection
0x140098453  mov     rax, cr8
0x140098457  cmp     al, 2
0x140098459  jnz     short loc_1400984C2
0x14009845b  lea     rcx, SkiThreadReaperLock
0x140098462  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x140098467  mov     rcx, cs:qword_14014EDD8
0x14009846e  lea     rdx, SkiThreadReaperList
0x140098475  cmp     [rcx], rdx
0x140098478  jz      short loc_140098481
0x14009847a  mov     ecx, 3
0x14009847f  int     29h; Win8: RtlFailFast(ecx)
0x140098481  lea     rax, [rbx+30h]
0x140098485  mov     [rax], rdx
0x140098488  mov     [rax+8], rcx
0x14009848c  mov     [rcx], rax
0x14009848f  cmp     cs:SkiThreadReaperWorkItem, 0
0x140098497  mov     cs:qword_14014EDD8, rax
0x14009849e  jnz     short loc_1400984AC
0x1400984a0  lea     rcx, SkiThreadReaperWorkItem
0x1400984a7  call    SkQueueWorkItem
0x1400984ac  mov     cs:SkiThreadReaperLock, 0
0x1400984b6  call    SkTrackSpinLockRelease
0x1400984bb  call    SkRequestWorkCallback
0x1400984c0  jmp     short loc_1400984CA
0x1400984c2  mov     rcx, rbx
0x1400984c5  call    SkiDeleteThread
0x1400984ca  add     rsp, 20h
0x1400984ce  pop     rbx
0x1400984cf  retn
```
