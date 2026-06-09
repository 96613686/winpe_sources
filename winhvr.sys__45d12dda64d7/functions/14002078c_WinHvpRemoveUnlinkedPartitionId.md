# WinHvpRemoveUnlinkedPartitionId

- ea: `0x14002078c`
- end: `0x1400207ec`
- name: `WinHvpRemoveUnlinkedPartitionId`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001f2d0`
- `0x1400204a4`

## callees

- `0x14002078c`

## pseudocode

```c
__int64 __fastcall WinHvpRemoveUnlinkedPartitionId(__int64 a1)
{
  int v1; // edx
  int v2; // r8d
  __int64 v3; // r9
  __int64 result; // rax

  if ( a1 )
  {
    v1 = dword_14001620C;
    v2 = 0;
    if ( dword_14001620C > 0 )
    {
      v3 = qword_140016210;
      while ( *(_QWORD *)(qword_140016210 + 8LL * v2) != a1 )
      {
        if ( ++v2 >= dword_14001620C )
          return result;
      }
      if ( dword_14001620C - v2 > 1 )
      {
        *(_QWORD *)(qword_140016210 + 8LL * v2) = *(_QWORD *)(qword_140016210 + 8LL * (dword_14001620C - 1));
        v1 = dword_14001620C;
      }
      result = (unsigned int)(v1 - 1);
      *(_QWORD *)(v3 + 8LL * (int)result) = 0;
      _InterlockedDecrement(&dword_14001620C);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002078c  test    rcx, rcx
0x14002078f  jz      short locret_1400207EB
0x140020791  mov     edx, cs:dword_14001620C
0x140020797  xor     r8d, r8d
0x14002079a  test    edx, edx
0x14002079c  jle     short locret_1400207EB
0x14002079e  mov     r9, cs:qword_140016210
0x1400207a5  movsxd  r10, r8d
0x1400207a8  cmp     [r9+r10*8], rcx
0x1400207ac  jz      short loc_1400207B8
0x1400207ae  inc     r8d
0x1400207b1  cmp     r8d, edx
0x1400207b4  jl      short loc_1400207A5
0x1400207b6  retn
0x1400207b8  mov     eax, edx
0x1400207ba  sub     eax, r8d
0x1400207bd  cmp     eax, 1
0x1400207c0  jle     short loc_1400207D6
0x1400207c2  lea     eax, [rdx-1]
0x1400207c5  movsxd  rcx, eax
0x1400207c8  mov     rax, [r9+rcx*8]
0x1400207cc  mov     [r9+r10*8], rax
0x1400207d0  mov     edx, cs:dword_14001620C
0x1400207d6  lea     eax, [rdx-1]
0x1400207d9  movsxd  rcx, eax
0x1400207dc  mov     qword ptr [r9+rcx*8], 0
0x1400207e4  lock dec cs:dword_14001620C
0x1400207eb  retn
```
