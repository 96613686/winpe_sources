# PkWritePacketFooter

- ea: `0x140003ea0`
- end: `0x140003f33`
- name: `PkWritePacketFooter`
- size: `147`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400037e0`
- `0x140003f40`
- `0x1400042b0`
- `0x140004cc0`
- `0x140005300`
- `0x140005750`
- `0x140005fe0`
- `0x14001172c`

## callees

- `0x140003ea0`

## pseudocode

```c
__int64 __fastcall PkWritePacketFooter(__int64 *a1, int a2, unsigned int a3)
{
  unsigned int v3; // r11d
  unsigned int v4; // edi
  __int64 v5; // r8
  __int64 result; // rax
  _QWORD *v7; // r9
  __int64 v8; // rax
  __int64 v9; // [rsp+20h] [rbp+8h]

  v3 = *((_DWORD *)a1 + 4);
  v4 = a3;
  if ( (a3 & 7) != 0 )
  {
    v7 = (_QWORD *)(a1[1] + a2 + (a3 & 0xFFFFFFF8));
    *v7 &= (1LL << (8 * (a3 & 7))) - 1;
    v4 = (a3 + 7) & 0xFFFFFFF8;
  }
  v5 = a2 + v4;
  HIDWORD(v9) = a2;
  LODWORD(v9) = 0;
  *(_QWORD *)(v5 + a1[1]) = v9;
  if ( *((_DWORD *)a1 + 34) )
  {
    v8 = *a1;
    *((_DWORD *)a1 + 34) = 0;
    *(_DWORD *)(v8 + 12) = 0;
  }
  result = (_DWORD)v5 + 8 - v3;
  if ( (int)v5 + 8 < v3 )
    return (unsigned int)(v5 + 8);
  return result;
}

```

## disassembly

```asm
0x140003ea0  push    rbx
0x140003ea2  push    rsi
0x140003ea3  push    rdi
0x140003ea4  mov     r11d, [rcx+10h]
0x140003ea8  mov     ebx, r8d
0x140003eab  mov     edi, r8d
0x140003eae  mov     esi, edx
0x140003eb0  mov     r10, rcx
0x140003eb3  and     ebx, 7
0x140003eb6  jnz     short loc_140003EF2
0x140003eb8  mov     rcx, [r10+8]
0x140003ebc  lea     r8d, [rsi+rdi]
0x140003ec0  xor     r9d, r9d
0x140003ec3  mov     dword ptr [rsp+18h+arg_0+4], esi
0x140003ec7  mov     dword ptr [rsp+18h+arg_0], r9d
0x140003ecc  mov     rax, [rsp+18h+arg_0]
0x140003ed1  mov     [r8+rcx], rax
0x140003ed5  cmp     [r10+88h], r9d
0x140003edc  jnz     short loc_140003F23
0x140003ede  lea     ecx, [r8+8]
0x140003ee2  mov     eax, ecx
0x140003ee4  sub     eax, r11d
0x140003ee7  cmp     ecx, r11d
0x140003eea  cmovb   eax, ecx
0x140003eed  pop     rdi
0x140003eee  pop     rsi
0x140003eef  pop     rbx
0x140003ef0  retn
0x140003ef2  mov     r9d, edi
0x140003ef5  mov     edx, 1
0x140003efa  and     r9d, 0FFFFFFF8h
0x140003efe  add     edi, 7
0x140003f01  add     r9d, esi
0x140003f04  add     r9, [rcx+8]
0x140003f08  lea     ecx, ds:0[rbx*8]
0x140003f0f  shl     rdx, cl
0x140003f12  dec     rdx
0x140003f15  mov     r8, [r9]
0x140003f18  and     rdx, r8
0x140003f1b  mov     [r9], rdx
0x140003f1e  and     edi, 0FFFFFFF8h
0x140003f21  jmp     short loc_140003EB8
0x140003f23  mov     rax, [r10]
0x140003f26  mov     [r10+88h], r9d
0x140003f2d  mov     [rax+0Ch], r9d
0x140003f31  jmp     short loc_140003EDE
```
