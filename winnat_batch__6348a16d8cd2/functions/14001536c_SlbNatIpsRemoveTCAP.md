# SlbNatIpsRemoveTCAP

- ea: `0x14001536c`
- end: `0x1400153fa`
- name: `SlbNatIpsRemoveTCAP`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140033514`

## callees

- `0x14000a638`
- `0x14001536c`
- `0x140033394`
- `0x140034678`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400153cd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400153cd`

## pseudocode

```c
void __fastcall SlbNatIpsRemoveTCAP(__int64 a1, __int64 a2)
{
  _DWORD *TCAP; // rax
  _DWORD *v4; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  TCAP = (_DWORD *)SlbNatIpsFindTCAP(a1, 0, a2);
  v4 = TCAP;
  if ( TCAP )
  {
    if ( (*TCAP)-- == 1 )
    {
      RtlAcquireScalableWriteLock((__int64)&SlbNatIpsDataPathState, &LockHandle);
      v4[1] = 0;
      *((_QWORD *)v4 + 1) = 0;
      --*(_DWORD *)(a1 + 40);
      ++dword_140026840;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( !*(_DWORD *)(a1 + 40) )
      {
        SlbNatIpsClearInterfaceContext(a1);
        *(_DWORD *)(a1 + 24) = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x14001536c  mov     [rsp+arg_0], rbx
0x140015371  push    rdi
0x140015372  sub     rsp, 40h
0x140015376  xor     eax, eax
0x140015378  mov     r8, rdx
0x14001537b  xorps   xmm0, xmm0
0x14001537e  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140015383  xor     edx, edx
0x140015385  mov     rdi, rcx
0x140015388  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14001538d  call    SlbNatIpsFindTCAP
0x140015392  mov     rbx, rax
0x140015395  test    rax, rax
0x140015398  jz      short loc_1400153EE
0x14001539a  sub     dword ptr [rax], 1
0x14001539d  jnz     short loc_1400153EE
0x14001539f  lea     rdx, [rsp+48h+LockHandle]
0x1400153a4  lea     rcx, SlbNatIpsDataPathState
0x1400153ab  call    RtlAcquireScalableWriteLock
0x1400153b0  mov     dword ptr [rbx+4], 0
0x1400153b7  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x1400153bc  mov     qword ptr [rbx+8], 0
0x1400153c4  dec     dword ptr [rdi+28h]
0x1400153c7  inc     cs:dword_140026840
0x1400153cd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400153d4  nop     dword ptr [rax+rax+00h]
0x1400153d9  cmp     dword ptr [rdi+28h], 0
0x1400153dd  jnz     short loc_1400153EE
0x1400153df  mov     rcx, rdi
0x1400153e2  call    SlbNatIpsClearInterfaceContext
0x1400153e7  mov     dword ptr [rdi+18h], 0
0x1400153ee  mov     rbx, [rsp+48h+arg_0]
0x1400153f3  add     rsp, 40h
0x1400153f7  pop     rdi
0x1400153f8  retn
```
