# PkSendCompletion

- ea: `0x14001521c`
- end: `0x1400152d5`
- name: `PkSendCompletion`
- size: `185`
- prototype: `__int64 __fastcall(__int64, __int64, const void *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000ada0`

## callees

- `0x1400022f0`
- `0x140015034`
- `0x1400151a4`
- `0x14001521c`
- `0x140017240`

## pseudocode

```c
__int64 __fastcall PkSendCompletion(__int64 a1, __int64 a2, const void *a3, unsigned int a4, int a5)
{
  size_t v5; // rsi
  __int64 v9; // rbx
  __int64 result; // rax
  unsigned int v11; // ebp
  _DWORD *v12; // rcx
  int v13; // eax
  _DWORD *v14; // [rsp+30h] [rbp-48h] BYREF

  v5 = a4;
  v14 = 0;
  a5 = 0;
  v9 = a4 + 16;
  if ( (unsigned int)v9 > 0x7FFF8 )
    return 3221225485LL;
  v11 = *(_DWORD *)(a1 + 128);
  result = PkGetSendBufferEx(a1, v11, v9, &v14, &a5);
  if ( (int)result >= 0 )
  {
    v12 = v14;
    *v14 = 131083;
    *((_WORD *)v12 + 2) = (unsigned __int64)(v9 + 7) >> 3;
    *((_WORD *)v12 + 3) = 0;
    *((_QWORD *)v12 + 1) = a2;
    memmove(v12 + 4, a3, v5);
    v13 = PkWritePacketFooter((__int64 *)a1, v11, v9);
    return PkCompleteInsertion(a1, v13);
  }
  return result;
}

```

## disassembly

```asm
0x14001521c  mov     rax, rsp
0x14001521f  push    rbx
0x140015220  push    rbp
0x140015221  push    rsi
0x140015222  push    rdi
0x140015223  push    r14
0x140015225  push    r15
0x140015227  sub     rsp, 48h
0x14001522b  mov     esi, r9d
0x14001522e  mov     r14, r8
0x140015231  mov     r15, rdx
0x140015234  mov     qword ptr [rax-48h], 0
0x14001523c  mov     rdi, rcx
0x14001523f  mov     dword ptr [rax+28h], 0
0x140015246  lea     ebx, [rsi+10h]
0x140015249  cmp     ebx, 7FFF8h
0x14001524f  jbe     short loc_140015258
0x140015251  mov     eax, 0C000000Dh
0x140015256  jmp     short loc_1400152C7
0x140015258  mov     ebp, [rcx+80h]
0x14001525e  lea     rax, [rsp+78h+arg_20]
0x140015266  mov     edx, ebp
0x140015268  mov     [rsp+78h+var_58], rax
0x14001526d  lea     r9, [rsp+78h+var_48]
0x140015272  mov     r8d, ebx
0x140015275  call    PkGetSendBufferEx
0x14001527a  test    eax, eax
0x14001527c  js      short loc_1400152C7
0x14001527e  mov     rcx, [rsp+78h+var_48]
0x140015283  lea     rax, [rbx+7]
0x140015287  nop
0x140015288  shr     rax, 3
0x14001528c  mov     r8, rsi; Size
0x14001528f  mov     rdx, r14; Src
0x140015292  mov     dword ptr [rcx], 2000Bh
0x140015298  mov     [rcx+4], ax
0x14001529c  xor     eax, eax
0x14001529e  mov     [rcx+6], ax
0x1400152a2  mov     [rcx+8], r15
0x1400152a6  add     rcx, 10h; void *
0x1400152aa  call    memmove
0x1400152af  mov     r8d, ebx
0x1400152b2  mov     edx, ebp
0x1400152b4  mov     rcx, rdi
0x1400152b7  call    PkWritePacketFooter
0x1400152bc  mov     edx, eax
0x1400152be  mov     rcx, rdi
0x1400152c1  call    PkCompleteInsertion
0x1400152c6  nop
0x1400152c7  add     rsp, 48h
0x1400152cb  pop     r15
0x1400152cd  pop     r14
0x1400152cf  pop     rdi
0x1400152d0  pop     rsi
0x1400152d1  pop     rbp
0x1400152d2  pop     rbx
0x1400152d3  retn
```
