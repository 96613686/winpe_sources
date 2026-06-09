# WinHvpAddUnlinkedPartitionId

- ea: `0x14001fea8`
- end: `0x14001ff2d`
- name: `WinHvpAddUnlinkedPartitionId`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400204a4`

## callees

- `0x14001fea8`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14001fefa`
- `HAL!KeQueryPerformanceCounter` at `0x14001fefa`

## pseudocode

```c
void __fastcall WinHvpAddUnlinkedPartitionId(__int64 a1)
{
  __int64 v1; // rbx

  if ( a1 )
  {
    if ( (unsigned __int64)dword_14001620C < 0x200 )
    {
      *(_QWORD *)(qword_140016210 + 8LL * dword_14001620C) = a1;
      _InterlockedIncrement(&dword_14001620C);
    }
    else if ( *(_QWORD *)&WinHvpBlackbox )
    {
      v1 = 2LL * (_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&WinHvpBlackbox + 4LL), 1u) & 0x3F);
      *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v1 + 8) = 7;
      *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v1 + 12) = a1;
      *(LARGE_INTEGER *)(*(_QWORD *)&WinHvpBlackbox + 8 * v1 + 16) = KeQueryPerformanceCounter(0);
    }
  }
}

```

## disassembly

```asm
0x14001fea8  test    rcx, rcx
0x14001feab  jz      short locret_14001FF2B
0x14001fead  push    rbx
0x14001feae  sub     rsp, 20h
0x14001feb2  movsxd  rdx, cs:dword_14001620C
0x14001feb9  cmp     rdx, 200h
0x14001fec0  jb      short loc_14001FF14
0x14001fec2  mov     rdx, cs:WinHvpBlackbox
0x14001fec9  test    rdx, rdx
0x14001fecc  jz      short loc_14001FF26
0x14001fece  mov     ebx, 1
0x14001fed3  lock xadd [rdx+4], ebx
0x14001fed8  mov     rax, cs:WinHvpBlackbox
0x14001fedf  and     ebx, 3Fh
0x14001fee2  add     rbx, rbx
0x14001fee5  mov     dword ptr [rax+rbx*8+8], 7
0x14001feed  mov     rax, cs:WinHvpBlackbox
0x14001fef4  mov     [rax+rbx*8+0Ch], ecx
0x14001fef8  xor     ecx, ecx; PerformanceFrequency
0x14001fefa  call    cs:__imp_KeQueryPerformanceCounter
0x14001ff01  nop     dword ptr [rax+rax+00h]
0x14001ff06  mov     rcx, cs:WinHvpBlackbox
0x14001ff0d  mov     [rcx+rbx*8+10h], rax
0x14001ff12  jmp     short loc_14001FF26
0x14001ff14  mov     rax, cs:qword_140016210
0x14001ff1b  mov     [rax+rdx*8], rcx
0x14001ff1f  lock inc cs:dword_14001620C
0x14001ff26  add     rsp, 20h
0x14001ff2a  pop     rbx
0x14001ff2b  retn
```
