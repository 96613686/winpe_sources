# SlbNatIpsRemoveTCAP

- ea: `0x140015ce8`
- end: `0x140015d76`
- name: `SlbNatIpsRemoveTCAP`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140034644`

## callees

- `0x14000a638`
- `0x140015ce8`
- `0x1400344c4`
- `0x140035988`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015d49`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015d49`

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
      ++dword_140027840;
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
0x140015ce8  mov     [rsp+arg_0], rbx
0x140015ced  push    rdi
0x140015cee  sub     rsp, 40h
0x140015cf2  xor     eax, eax
0x140015cf4  mov     r8, rdx
0x140015cf7  xorps   xmm0, xmm0
0x140015cfa  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140015cff  xor     edx, edx
0x140015d01  mov     rdi, rcx
0x140015d04  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140015d09  call    SlbNatIpsFindTCAP
0x140015d0e  mov     rbx, rax
0x140015d11  test    rax, rax
0x140015d14  jz      short loc_140015D6A
0x140015d16  sub     dword ptr [rax], 1
0x140015d19  jnz     short loc_140015D6A
0x140015d1b  lea     rdx, [rsp+48h+LockHandle]
0x140015d20  lea     rcx, SlbNatIpsDataPathState
0x140015d27  call    RtlAcquireScalableWriteLock
0x140015d2c  mov     dword ptr [rbx+4], 0
0x140015d33  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140015d38  mov     qword ptr [rbx+8], 0
0x140015d40  dec     dword ptr [rdi+28h]
0x140015d43  inc     cs:dword_140027840
0x140015d49  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140015d50  nop     dword ptr [rax+rax+00h]
0x140015d55  cmp     dword ptr [rdi+28h], 0
0x140015d59  jnz     short loc_140015D6A
0x140015d5b  mov     rcx, rdi
0x140015d5e  call    SlbNatIpsClearInterfaceContext
0x140015d63  mov     dword ptr [rdi+18h], 0
0x140015d6a  mov     rbx, [rsp+48h+arg_0]
0x140015d6f  add     rsp, 40h
0x140015d73  pop     rdi
0x140015d74  retn
```
