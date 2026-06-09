# SkmiAllocateSystemPtes

- ea: `0x140027ac0`
- end: `0x140027b41`
- name: `SkmiAllocateSystemPtes`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `38`
- callee_count: `4`
- tags: ``

## callers

- `0x140022a48`
- `0x14002341c`
- `0x140023b58`
- `0x140023ee8`
- `0x140024a1c`
- `0x140025090`
- `0x1400341c8`
- `0x1400365d8`
- `0x140045e4c`
- `0x140047244`
- `0x140048bfc`
- `0x140049618`
- `0x140049bec`
- `0x14004a168`
- `0x14004c5d4`
- `0x14004e088`
- `0x14004eb04`
- `0x14004f7c8`
- `0x1400500b4`
- `0x140053450`
- `0x140054118`
- `0x1400594e0`
- `0x14005cf30`
- `0x14006011c`
- `0x140063ca8`
- `0x140068924`
- `0x140069528`
- `0x14006dabc`
- `0x1400706f8`
- `0x140070cd8`
- `0x140071704`
- `0x14007b5a8`
- `0x14007b814`
- `0x140081004`
- `0x140081848`
- `0x1400826e8`
- `0x140082ac8`
- `0x14008662c`

## callees

- `0x14001be90`
- `0x140027ac0`
- `0x140027b48`
- `0x14004d96c`

## pseudocode

```c
__int64 __fastcall SkmiAllocateSystemPtes(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbp
  unsigned int ClearBits; // eax
  unsigned int v6; // r14d

  v2 = a2;
  do
  {
    while ( 1 )
    {
      v4 = *(_QWORD *)(a1 + 16);
      ClearBits = RtlFindClearBitsEx(a1 + 16, v2, *(unsigned int *)(a1 + 12));
      v6 = ClearBits;
      if ( ClearBits == -1 )
        break;
      if ( (unsigned int)RtlInterlockedSetClearRunEx(a1 + 16, ClearBits, v2) )
      {
        *(_DWORD *)(a1 + 12) = (unsigned __int64)(v6 + (unsigned int)v2) < *(_QWORD *)(a1 + 16) ? v6 + v2 : 0;
        return *(_QWORD *)a1 + 8LL * v6;
      }
    }
  }
  while ( (int)v2 + (int)v4 >= (unsigned int)v4 && (unsigned __int8)SkmiExpandPteRange(a1) );
  return 0;
}

```

## disassembly

```asm
0x140027ac0  push    rbx
0x140027ac2  push    rbp
0x140027ac3  push    rsi
0x140027ac4  push    rdi
0x140027ac5  push    r14
0x140027ac7  push    r15
0x140027ac9  sub     rsp, 28h
0x140027acd  mov     edi, edx
0x140027acf  mov     rbx, rcx
0x140027ad2  lea     rsi, [rbx+10h]
0x140027ad6  mov     rdx, rdi
0x140027ad9  mov     rbp, [rsi]
0x140027adc  mov     rcx, rsi
0x140027adf  mov     r8d, [rbx+0Ch]
0x140027ae3  call    RtlFindClearBitsEx
0x140027ae8  mov     r14, rax
0x140027aeb  cmp     eax, 0FFFFFFFFh
0x140027aee  jz      short loc_140027B1E
0x140027af0  mov     r8, rdi
0x140027af3  mov     edx, r14d
0x140027af6  mov     rcx, rsi
0x140027af9  mov     ebp, r14d
0x140027afc  call    RtlInterlockedSetClearRunEx
0x140027b01  test    eax, eax
0x140027b03  jz      short loc_140027AD2
0x140027b05  lea     ecx, [r14+rdi]
0x140027b09  mov     eax, ecx
0x140027b0b  cmp     rax, [rsi]
0x140027b0e  sbb     eax, eax
0x140027b10  and     eax, ecx
0x140027b12  mov     [rbx+0Ch], eax
0x140027b15  mov     rax, [rbx]
0x140027b18  lea     rax, [rax+rbp*8]
0x140027b1c  jmp     short loc_140027B33
0x140027b1e  lea     edx, [rdi+rbp]
0x140027b21  cmp     edx, ebp
0x140027b23  jb      short loc_140027B31
0x140027b25  mov     rcx, rbx
0x140027b28  call    SkmiExpandPteRange
0x140027b2d  test    al, al
0x140027b2f  jnz     short loc_140027AD2
0x140027b31  xor     eax, eax
0x140027b33  add     rsp, 28h
0x140027b37  pop     r15
0x140027b39  pop     r14
0x140027b3b  pop     rdi
0x140027b3c  pop     rsi
0x140027b3d  pop     rbp
0x140027b3e  pop     rbx
0x140027b3f  retn
```
