# PkWritePacketFooter

- ea: `0x1400022f0`
- end: `0x140002378`
- name: `PkWritePacketFooter`
- size: `136`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140014e78`
- `0x14001514c`
- `0x14001521c`
- `0x1400152dc`

## callees

- `0x1400022f0`

## pseudocode

```c
__int64 __fastcall PkWritePacketFooter(__int64 *a1, int a2, unsigned int a3)
{
  unsigned int v3; // esi
  unsigned int v4; // r11d
  char v5; // bl
  _QWORD *v6; // r8
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 result; // rax
  __int64 v10; // [rsp+20h] [rbp+8h]

  v3 = *((_DWORD *)a1 + 4);
  v4 = a3;
  v5 = a3 & 7;
  if ( (a3 & 7) != 0 )
  {
    v6 = (_QWORD *)(a1[1] + a2 + (a3 & 0xFFFFFFF8));
    *v6 &= (1LL << (8 * v5)) - 1;
    v4 = (v4 + 7) & 0xFFFFFFF8;
  }
  v7 = a2 + v4;
  HIDWORD(v10) = a2;
  LODWORD(v10) = 0;
  *(_QWORD *)(v7 + a1[1]) = v10;
  if ( *((_DWORD *)a1 + 34) )
  {
    v8 = *a1;
    *((_DWORD *)a1 + 34) = 0;
    *(_DWORD *)(v8 + 12) = 0;
  }
  result = (_DWORD)v7 + 8 - v3;
  if ( (int)v7 + 8 < v3 )
    return (unsigned int)(v7 + 8);
  return result;
}

```

## disassembly

```asm
0x1400022f0  push    rbx
0x1400022f2  push    rsi
0x1400022f3  push    rdi
0x1400022f4  mov     esi, [rcx+10h]
0x1400022f7  mov     ebx, r8d
0x1400022fa  mov     r11d, r8d
0x1400022fd  mov     edi, edx
0x1400022ff  mov     r9, rcx
0x140002302  and     ebx, 7
0x140002305  jz      short loc_140002335
0x140002307  and     r8d, 0FFFFFFF8h
0x14000230b  mov     eax, 1
0x140002310  add     r8d, edx
0x140002313  add     r11d, 7
0x140002317  add     r8, [rcx+8]
0x14000231b  lea     ecx, ds:0[rbx*8]
0x140002322  shl     rax, cl
0x140002325  dec     rax
0x140002328  mov     rdx, [r8]
0x14000232b  and     rax, rdx
0x14000232e  mov     [r8], rax
0x140002331  and     r11d, 0FFFFFFF8h
0x140002335  mov     rcx, [r9+8]
0x140002339  lea     r8d, [rdi+r11]
0x14000233d  xor     ebx, ebx
0x14000233f  mov     dword ptr [rsp+18h+arg_0+4], edi
0x140002343  mov     dword ptr [rsp+18h+arg_0], ebx
0x140002347  mov     rax, [rsp+18h+arg_0]
0x14000234c  mov     [r8+rcx], rax
0x140002350  cmp     [r9+88h], ebx
0x140002357  jz      short loc_140002366
0x140002359  mov     rax, [r9]
0x14000235c  mov     [r9+88h], ebx
0x140002363  mov     [rax+0Ch], ebx
0x140002366  lea     ecx, [r8+8]
0x14000236a  mov     eax, ecx
0x14000236c  sub     eax, esi
0x14000236e  cmp     ecx, esi
0x140002370  cmovb   eax, ecx
0x140002373  pop     rdi
0x140002374  pop     rsi
0x140002375  pop     rbx
0x140002376  retn
```
