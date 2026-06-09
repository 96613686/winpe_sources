# getBit32

- ea: `0x18000bbf0`
- end: `0x18000bc80`
- name: `getBit32`
- size: `144`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800094bc`
- `0x18000a330`
- `0x18002823c`
- `0x180028470`

## callees

- `0x18000bbf0`

## pseudocode

```c
__int64 __fastcall getBit32(__int64 a1, unsigned int a2)
{
  int v2; // esi
  _DWORD *v3; // r10
  _BYTE *v4; // rax
  unsigned int v5; // edi
  unsigned int **v6; // r11
  int *v7; // rbx
  unsigned int v8; // r9d
  int v9; // ecx
  unsigned int *v10; // r8
  int v12; // esi
  int v13; // ecx
  unsigned int *v14; // r8

  v2 = 0;
  v3 = (_DWORD *)(a1 + 4);
  v4 = (_BYTE *)(a1 + 8);
  v5 = a2;
  v6 = (unsigned int **)(a1 + 24);
  v7 = (int *)(a1 + 12);
  if ( a2 > 0x10 )
  {
    v5 = a2 - 16;
    v12 = *(unsigned __int16 *)(a1 + 6);
    v13 = (*v4 + 16) & 0xF;
    v14 = (unsigned int *)(*v7 & ((unsigned __int64)*v6 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v4 + 16) >> 3)));
    *(_DWORD *)v4 = v13;
    *v6 = v14;
    v2 = v12 << (a2 - 16);
    *v3 = _byteswap_ulong(*v14) << v13;
  }
  *(_DWORD *)v4 += v5;
  v8 = *v3 >> (32 - v5);
  v9 = *(_DWORD *)v4 & 0xF;
  v10 = (unsigned int *)(*v7 & ((unsigned __int64)*v6 + ((unsigned __int64)*(unsigned int *)v4 >> 3)));
  *(_DWORD *)v4 = v9;
  *v6 = v10;
  *v3 = _byteswap_ulong(*v10) << v9;
  return v2 | v8;
}

```

## disassembly

```asm
0x18000bbf0  push    rbx
0x18000bbf2  push    rsi
0x18000bbf3  push    rdi
0x18000bbf4  xor     esi, esi
0x18000bbf6  lea     r10, [rcx+4]
0x18000bbfa  lea     rax, [rcx+8]
0x18000bbfe  mov     edi, edx
0x18000bc00  lea     r11, [rcx+18h]
0x18000bc04  lea     rbx, [rcx+0Ch]
0x18000bc08  cmp     edx, 10h
0x18000bc0b  ja      short loc_18000BC4B
0x18000bc0d  add     [rax], edi
0x18000bc0f  mov     ecx, 20h ; ' '
0x18000bc14  mov     r9d, [r10]
0x18000bc17  sub     ecx, edi
0x18000bc19  movsxd  rdx, dword ptr [rbx]
0x18000bc1c  shr     r9d, cl
0x18000bc1f  mov     ecx, [rax]
0x18000bc21  mov     r8d, ecx
0x18000bc24  and     ecx, 0Fh
0x18000bc27  shr     r8, 3
0x18000bc2b  add     r8, [r11]
0x18000bc2e  and     r8, rdx
0x18000bc31  mov     [rax], ecx
0x18000bc33  mov     [r11], r8
0x18000bc36  mov     edx, [r8]
0x18000bc39  bswap   edx
0x18000bc3b  shl     edx, cl
0x18000bc3d  or      r9d, esi
0x18000bc40  mov     [r10], edx
0x18000bc43  mov     eax, r9d
0x18000bc46  pop     rdi
0x18000bc47  pop     rsi
0x18000bc48  pop     rbx
0x18000bc49  retn
0x18000bc4b  mov     ecx, [rax]
0x18000bc4d  add     edi, 0FFFFFFF0h
0x18000bc50  movsxd  rdx, dword ptr [rbx]
0x18000bc53  add     ecx, 10h
0x18000bc56  movzx   esi, word ptr [r10+2]
0x18000bc5b  mov     r8d, ecx
0x18000bc5e  and     ecx, 0Fh
0x18000bc61  shr     r8, 3
0x18000bc65  add     r8, [r11]
0x18000bc68  and     r8, rdx
0x18000bc6b  mov     [rax], ecx
0x18000bc6d  mov     [r11], r8
0x18000bc70  mov     edx, [r8]
0x18000bc73  bswap   edx
0x18000bc75  shl     edx, cl
0x18000bc77  mov     ecx, edi
0x18000bc79  shl     esi, cl
0x18000bc7b  mov     [r10], edx
0x18000bc7e  jmp     short loc_18000BC0D
```
