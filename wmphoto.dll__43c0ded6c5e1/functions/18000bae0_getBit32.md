# getBit32

- ea: `0x18000bae0`
- end: `0x18000bb6f`
- name: `getBit32`
- size: `143`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800093ac`
- `0x18000a220`
- `0x180027fd8`
- `0x18002820c`

## callees

- `0x18000bae0`

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
0x18000bae0  push    rbx
0x18000bae2  push    rsi
0x18000bae3  push    rdi
0x18000bae4  xor     esi, esi
0x18000bae6  lea     r10, [rcx+4]
0x18000baea  lea     rax, [rcx+8]
0x18000baee  mov     edi, edx
0x18000baf0  lea     r11, [rcx+18h]
0x18000baf4  lea     rbx, [rcx+0Ch]
0x18000baf8  cmp     edx, 10h
0x18000bafb  ja      short loc_18000BB3A
0x18000bafd  add     [rax], edi
0x18000baff  mov     ecx, 20h ; ' '
0x18000bb04  mov     r9d, [r10]
0x18000bb07  sub     ecx, edi
0x18000bb09  movsxd  rdx, dword ptr [rbx]
0x18000bb0c  shr     r9d, cl
0x18000bb0f  mov     ecx, [rax]
0x18000bb11  mov     r8d, ecx
0x18000bb14  and     ecx, 0Fh
0x18000bb17  shr     r8, 3
0x18000bb1b  add     r8, [r11]
0x18000bb1e  and     r8, rdx
0x18000bb21  mov     [rax], ecx
0x18000bb23  mov     [r11], r8
0x18000bb26  mov     edx, [r8]
0x18000bb29  bswap   edx
0x18000bb2b  shl     edx, cl
0x18000bb2d  or      r9d, esi
0x18000bb30  mov     [r10], edx
0x18000bb33  mov     eax, r9d
0x18000bb36  pop     rdi
0x18000bb37  pop     rsi
0x18000bb38  pop     rbx
0x18000bb39  retn
0x18000bb3a  mov     ecx, [rax]
0x18000bb3c  add     edi, 0FFFFFFF0h
0x18000bb3f  movsxd  rdx, dword ptr [rbx]
0x18000bb42  add     ecx, 10h
0x18000bb45  movzx   esi, word ptr [r10+2]
0x18000bb4a  mov     r8d, ecx
0x18000bb4d  and     ecx, 0Fh
0x18000bb50  shr     r8, 3
0x18000bb54  add     r8, [r11]
0x18000bb57  and     r8, rdx
0x18000bb5a  mov     [rax], ecx
0x18000bb5c  mov     [r11], r8
0x18000bb5f  mov     edx, [r8]
0x18000bb62  bswap   edx
0x18000bb64  shl     edx, cl
0x18000bb66  mov     ecx, edi
0x18000bb68  shl     esi, cl
0x18000bb6a  mov     [r10], edx
0x18000bb6d  jmp     short loc_18000BAFD
```
