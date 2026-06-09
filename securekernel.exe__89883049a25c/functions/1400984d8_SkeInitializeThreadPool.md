# SkeInitializeThreadPool

- ea: `0x1400984d8`
- end: `0x14009864c`
- name: `SkeInitializeThreadPool`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140092184`
- `0x1400b82ec`

## callees

- `0x14002341c`
- `0x14004f7c8`
- `0x140092d7c`
- `0x1400984d8`
- `0x140098abc`
- `0x140098d58`

## pseudocode

```c
char __fastcall SkeInitializeThreadPool(int a1)
{
  __int64 KernelStack; // rax
  unsigned int v3; // edi
  __int64 Thread; // rax
  __int64 v5; // rdx

  if ( a1 != 1 )
  {
    v3 = 2;
    while ( 1 )
    {
      Thread = SkiCreateThread(v3, 0);
      if ( !Thread )
        break;
      *(_QWORD *)(Thread + 72) = PsIumSystemProcess;
      *(_QWORD *)(Thread + 80) = PsIumSystemProcess;
      _InterlockedOr(&SkiThreadPoolMask, 1 << v3);
      _InterlockedAdd(&SkiThreadPoolCount, 1u);
      if ( ++v3 > 8 )
      {
        LOBYTE(v5) = 1;
        if ( (int)SkeAllocateSystemXSaveArea(qword_14014ED80, v5) < 0 )
          return 0;
        qword_14014EC88 = PsIumSystemProcess;
        qword_14014EC90 = PsIumSystemProcess;
        return 1;
      }
    }
    return 0;
  }
  SkiThreadTableExpansionLock = 0;
  if ( (int)SkmmCreateSparseTable((__int64)&SkiThreadTable, 0x40000u, 8u) < 0 )
  {
    if ( !word_140109002 )
    {
      *(_DWORD *)SkInitFailure = *(_DWORD *)SkInitFailure & 0xFFFFFFF0 | 1;
      word_140109002 = 1;
LABEL_8:
      *(_DWORD *)SkInitFailure = *(_DWORD *)SkInitFailure & 0xFFFF000F | 0x90;
      return 0;
    }
    return 0;
  }
  KernelStack = SkmmAllocateKernelStack((unsigned int)SkeKernelStackSize, 1);
  if ( !KernelStack )
  {
    if ( !word_140109002 )
    {
      *(_DWORD *)SkInitFailure = *(_DWORD *)SkInitFailure & 0xFFFFFFF0 | 1;
      word_140109002 = 3;
      goto LABEL_8;
    }
    return 0;
  }
  SkiInitializeThread(SkiInitThread, KernelStack, 0);
  dword_14014ECE8 = 1;
  *(_QWORD *)(SkiThreadTable + 8) = SkiInitThread;
  _InterlockedOr(&SkiThreadPoolMask, 2u);
  _InterlockedAdd(&SkiThreadPoolCount, 1u);
  return 1;
}

```

## disassembly

```asm
0x1400984d8  mov     [rsp+arg_0], rbx
0x1400984dd  mov     [rsp+arg_8], rsi
0x1400984e2  push    rdi
0x1400984e3  sub     rsp, 20h
0x1400984e7  mov     esi, 1
0x1400984ec  cmp     ecx, esi
0x1400984ee  jnz     loc_1400985D4
0x1400984f4  xor     ebx, ebx
0x1400984f6  lea     r8d, [rsi+7]
0x1400984fa  mov     edx, 40000h
0x1400984ff  mov     cs:SkiThreadTableExpansionLock, ebx
0x140098505  lea     rcx, SkiThreadTable
0x14009850c  call    SkmmCreateSparseTable
0x140098511  test    eax, eax
0x140098513  jns     short loc_140098538
0x140098515  cmp     cs:word_140109002, bx
0x14009851c  jnz     short loc_140098586
0x14009851e  mov     eax, dword ptr cs:SkInitFailure
0x140098524  and     eax, 0FFFFFFF1h
0x140098527  or      eax, esi
0x140098529  mov     dword ptr cs:SkInitFailure, eax
0x14009852f  mov     cs:word_140109002, si
0x140098536  jmp     short loc_140098570
0x140098538  mov     ecx, cs:SkeKernelStackSize
0x14009853e  mov     edx, esi
0x140098540  call    SkmmAllocateKernelStack
0x140098545  test    rax, rax
0x140098548  jnz     short loc_140098599
0x14009854a  cmp     cs:word_140109002, bx
0x140098551  jnz     short loc_140098586
0x140098553  mov     eax, dword ptr cs:SkInitFailure
0x140098559  and     eax, 0FFFFFFF1h
0x14009855c  or      eax, esi
0x14009855e  mov     dword ptr cs:SkInitFailure, eax
0x140098564  mov     eax, 3
0x140098569  mov     cs:word_140109002, ax
0x140098570  mov     eax, dword ptr cs:SkInitFailure
0x140098576  and     eax, 0FFFF009Fh
0x14009857b  or      eax, 90h
0x140098580  mov     dword ptr cs:SkInitFailure, eax
0x140098586  xor     al, al
0x140098588  mov     rbx, [rsp+28h+arg_0]
0x14009858d  mov     rsi, [rsp+28h+arg_8]
0x140098592  add     rsp, 20h
0x140098596  pop     rdi
0x140098597  retn
0x140098599  lea     rbx, SkiInitThread
0x1400985a0  xor     r8d, r8d
0x1400985a3  mov     rcx, rbx
0x1400985a6  mov     rdx, rax
0x1400985a9  call    SkiInitializeThread
0x1400985ae  mov     rax, cs:SkiThreadTable
0x1400985b5  mov     edi, 2
0x1400985ba  mov     cs:dword_14014ECE8, esi
0x1400985c0  mov     [rax+8], rbx
0x1400985c4  lock or cs:SkiThreadPoolMask, edi
0x1400985cb  lock add cs:SkiThreadPoolCount, esi
0x1400985d2  jmp     short loc_140098644
0x1400985d4  mov     edi, 2
0x1400985d9  xor     edx, edx
0x1400985db  mov     ecx, edi
0x1400985dd  call    SkiCreateThread
0x1400985e2  test    rax, rax
0x1400985e5  jz      short loc_140098586
0x1400985e7  mov     rcx, cs:PsIumSystemProcess
0x1400985ee  mov     [rax+48h], rcx
0x1400985f2  mov     rcx, cs:PsIumSystemProcess
0x1400985f9  mov     [rax+50h], rcx
0x1400985fd  mov     ecx, edi
0x1400985ff  mov     eax, esi
0x140098601  shl     eax, cl
0x140098603  lock or cs:SkiThreadPoolMask, eax
0x14009860a  lock add cs:SkiThreadPoolCount, esi
0x140098611  add     edi, esi
0x140098613  cmp     edi, 8
0x140098616  jbe     short loc_1400985D9
0x140098618  mov     dl, sil
0x14009861b  lea     rcx, qword_14014ED80
0x140098622  call    SkeAllocateSystemXSaveArea
0x140098627  test    eax, eax
0x140098629  js      loc_140098586
0x14009862f  mov     rcx, cs:PsIumSystemProcess
0x140098636  mov     cs:qword_14014EC88, rcx
0x14009863d  mov     cs:qword_14014EC90, rcx
0x140098644  mov     al, sil
0x140098647  jmp     loc_140098588
```
