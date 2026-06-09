# PipeTryWriteDeferred

- ea: `0x140016994`
- end: `0x140016aa7`
- name: `PipeTryWriteDeferred`
- size: `275`
- prototype: `__int64 __fastcall(__int64, int, unsigned int *, char, int *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001617c`
- `0x140016ab0`

## callees

- `0x14001514c`
- `0x140016994`

## pseudocode

```c
__int64 __fastcall PipeTryWriteDeferred(__int64 a1, int a2, unsigned int *a3, char a4, int *a5, _QWORD *a6, __int64 a7)
{
  unsigned int v7; // edi
  __int64 v11; // rbx
  __int64 v12; // rsi
  __int64 result; // rax
  __int64 v14; // r9
  _QWORD *v15; // rax
  __int64 v16; // rcx
  signed __int32 v17[18]; // [rsp+0h] [rbp-48h] BYREF
  __int64 v18; // [rsp+50h] [rbp+8h] BYREF

  v7 = *a3;
  v18 = 0;
  if ( a4 && v7 > 0x4000 )
    v7 = 0x4000;
  v11 = a7;
  v12 = v7 + 16;
  *(_DWORD *)(a7 + 32) = 16;
  if ( *(_BYTE *)(a1 + 272) )
  {
    v12 = v7 + 24;
    *(_DWORD *)(v11 + 32) = 24;
  }
  result = PkGetSendBuffer((__int64 *)(a1 + 64), a5, v12, (int)&v18);
  if ( (_DWORD)result == -2147483643 )
  {
    v14 = *(_QWORD *)(a1 + 88);
    if ( (*(_BYTE *)(v14 + 64) & 1) != 0 )
      return result;
    *(_DWORD *)(v14 + 8) = 0;
    _InterlockedOr(v17, 0);
    result = PkGetSendBuffer((__int64 *)(a1 + 64), a5, v12, (int)&v18);
  }
  if ( (int)result >= 0 )
  {
    *(_QWORD *)(v11 + 24) = v18;
    *(_WORD *)(v11 + 6) = 0;
    *(_WORD *)(v11 + 4) = (unsigned __int64)(v12 + 7) >> 3;
    *(_DWORD *)v11 = 131078;
    *(_QWORD *)(v11 + 8) = 0;
    if ( *(_BYTE *)(a1 + 272) )
    {
      *(_DWORD *)(v11 + 16) = a2;
      *(_DWORD *)(v11 + 20) = v7;
    }
    v15 = a6;
    v16 = *(_QWORD *)(v11 + 24) + *(unsigned int *)(v11 + 32);
    *a3 = v7;
    *v15 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140016994  mov     [rsp+arg_8], rbx
0x140016999  mov     [rsp+arg_10], rbp
0x14001699e  push    rsi
0x14001699f  push    rdi
0x1400169a0  push    r12
0x1400169a2  push    r14
0x1400169a4  push    r15
0x1400169a6  sub     rsp, 20h
0x1400169aa  mov     edi, [r8]
0x1400169ad  mov     r14, r8
0x1400169b0  mov     [rsp+48h+arg_0], 0
0x1400169b9  mov     r12d, edx
0x1400169bc  mov     rbp, rcx
0x1400169bf  test    r9b, r9b
0x1400169c2  jz      short loc_1400169CE
0x1400169c4  mov     eax, 4000h
0x1400169c9  cmp     edi, eax
0x1400169cb  cmova   edi, eax
0x1400169ce  mov     rbx, [rsp+48h+arg_30]
0x1400169d6  lea     esi, [rdi+10h]
0x1400169d9  mov     dword ptr [rbx+20h], 10h
0x1400169e0  cmp     byte ptr [rcx+110h], 0
0x1400169e7  jz      short loc_1400169F3
0x1400169e9  add     esi, 8
0x1400169ec  mov     dword ptr [rbx+20h], 18h
0x1400169f3  mov     rdx, [rsp+48h+arg_20]
0x1400169f8  lea     r9, [rsp+48h+arg_0]
0x1400169fd  mov     r8d, esi
0x140016a00  add     rcx, 40h ; '@'
0x140016a04  call    PkGetSendBuffer
0x140016a09  cmp     eax, 80000005h
0x140016a0e  jnz     short loc_140016A3E
0x140016a10  mov     r9, [rbp+58h]
0x140016a14  test    byte ptr [r9+40h], 1
0x140016a19  jnz     short loc_140016A8F
0x140016a1b  mov     dword ptr [r9+8], 0
0x140016a23  lock or [rsp+48h+var_48], 0
0x140016a28  mov     rdx, [rsp+48h+arg_20]
0x140016a2d  lea     r9, [rsp+48h+arg_0]
0x140016a32  mov     r8d, esi
0x140016a35  lea     rcx, [rbp+40h]
0x140016a39  call    PkGetSendBuffer
0x140016a3e  test    eax, eax
0x140016a40  js      short loc_140016A8F
0x140016a42  mov     rax, [rsp+48h+arg_0]
0x140016a47  mov     [rbx+18h], rax
0x140016a4b  xor     eax, eax
0x140016a4d  mov     [rbx+6], ax
0x140016a51  lea     rax, [rsi+7]
0x140016a55  shr     rax, 3
0x140016a59  mov     [rbx+4], ax
0x140016a5d  mov     dword ptr [rbx], 20006h
0x140016a63  mov     qword ptr [rbx+8], 0
0x140016a6b  cmp     byte ptr [rbp+110h], 0
0x140016a72  jz      short loc_140016A7B
0x140016a74  mov     [rbx+10h], r12d
0x140016a78  mov     [rbx+14h], edi
0x140016a7b  mov     rax, [rsp+48h+arg_28]
0x140016a80  mov     ecx, [rbx+20h]
0x140016a83  add     rcx, [rbx+18h]
0x140016a87  mov     [r14], edi
0x140016a8a  mov     [rax], rcx
0x140016a8d  xor     eax, eax
0x140016a8f  mov     rbx, [rsp+48h+arg_8]
0x140016a94  mov     rbp, [rsp+48h+arg_10]
0x140016a99  add     rsp, 20h
0x140016a9d  pop     r15
0x140016a9f  pop     r14
0x140016aa1  pop     r12
0x140016aa3  pop     rdi
0x140016aa4  pop     rsi
0x140016aa5  retn
```
