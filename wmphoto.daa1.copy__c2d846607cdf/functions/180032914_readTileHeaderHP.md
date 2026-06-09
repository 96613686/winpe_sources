# readTileHeaderHP

- ea: `0x180032914`
- end: `0x180032ad0`
- name: `readTileHeaderHP`
- size: `444`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800093ac`
- `0x180011eb0`

## callees

- `0x180002644`
- `0x180011738`
- `0x1800118d8`
- `0x180032914`
- `0x180034d3c`
- `0x18003dfe0`
- `0x18003ef7c`

## pseudocode

```c
__int64 __fastcall readTileHeaderHP(__int64 a1, __int64 a2)
{
  unsigned int v4; // r8d
  __int64 v5; // rsi
  __int64 v6; // rax
  unsigned __int64 v7; // rdx
  char v8; // cl
  unsigned int *v9; // rdx
  unsigned __int64 v10; // r8
  char v11; // r8
  __int64 v12; // rcx
  unsigned int *v13; // rdx
  unsigned __int32 v14; // eax
  unsigned __int64 v15; // r8
  unsigned __int8 i; // r14
  char Quantizer; // al
  int v19; // edx

  if ( (unsigned int)(*(_DWORD *)(a1 + 188) - 2) <= 1 || (*(_BYTE *)(a1 + 34284) & 4) == 0 )
    return 0;
  v4 = *(_DWORD *)(a2 + 4);
  v5 = *(_QWORD *)(a1 + 34464) + 432LL * *(_QWORD *)(a1 + 34392);
  v6 = *(int *)(a2 + 12);
  v7 = (unsigned int)(*(_DWORD *)(a2 + 8) + 1);
  v8 = v7 & 0xF;
  *(_DWORD *)(a2 + 8) = v7 & 0xF;
  v9 = (unsigned int *)(v6 & (*(_QWORD *)(a2 + 24) + (v7 >> 3)));
  *(_QWORD *)(a2 + 24) = v9;
  *(_DWORD *)(a2 + 4) = _byteswap_ulong(*v9) << v8;
  *(_DWORD *)(v5 + 392) = v4 >> 31;
  *(_BYTE *)(v5 + 387) = 0;
  *(_BYTE *)(v5 + 385) = 1;
  if ( *(_QWORD *)(a1 + 34384) )
    freeQuantizer(v5 + 256);
  if ( *(_DWORD *)(v5 + 392) != 1 )
  {
    v11 = (*(_DWORD *)(a2 + 4) >> 28) + 1;
    v12 = (*(_BYTE *)(a2 + 8) + 4) & 0xF;
    v13 = (unsigned int *)(*(int *)(a2 + 12)
                         & (*(_QWORD *)(a2 + 24) + ((unsigned __int64)(unsigned int)(*(_DWORD *)(a2 + 8) + 4) >> 3)));
    *(_DWORD *)(a2 + 8) = v12;
    *(_QWORD *)(a2 + 24) = v13;
    v14 = _byteswap_ulong(*v13) << v12;
    LOBYTE(v12) = v11;
    *(_DWORD *)(a2 + 4) = v14;
    *(_BYTE *)(v5 + 385) = v11;
    *(_BYTE *)(v5 + 387) = dquantBits(v12);
    if ( !(unsigned int)allocateQuantizer((_QWORD *)(v5 + 256), *(_QWORD *)(a1 + 34240), v15) )
    {
      for ( i = 0; i < *(_BYTE *)(v5 + 385); ++i )
      {
        Quantizer = readQuantizer(v5 + 256, a2, *(_QWORD *)(a1 + 34240), i);
        *(_BYTE *)(i + v5 + 413) = Quantizer;
        LOBYTE(v19) = Quantizer;
        formatQuantizer(v5 + 256, v19, *(_QWORD *)(a1 + 34240), i, 0, *(_DWORD *)(a1 + 34224));
      }
      return 0;
    }
    return 0xFFFFFFFFLL;
  }
  v10 = *(unsigned __int8 *)(v5 + 384);
  *(_BYTE *)(v5 + 385) = v10;
  if ( (unsigned int)allocateQuantizer((_QWORD *)(v5 + 256), *(_QWORD *)(a1 + 34240), v10) )
    return 0xFFFFFFFFLL;
  useLPQuantizer(a1, *(unsigned __int8 *)(v5 + 385), *(_QWORD *)(a1 + 34392));
  return 0;
}

```

## disassembly

```asm
0x180032914  push    rbx
0x180032916  push    rbp
0x180032917  push    rsi
0x180032918  push    rdi
0x180032919  push    r14
0x18003291b  push    r15
0x18003291d  sub     rsp, 38h
0x180032921  mov     eax, [rcx+0BCh]
0x180032927  mov     rbp, rdx
0x18003292a  sub     eax, 2
0x18003292d  mov     rdi, rcx
0x180032930  cmp     eax, 1
0x180032933  jbe     loc_180032AC1
0x180032939  test    byte ptr [rcx+85ECh], 4
0x180032940  jz      loc_180032AC1
0x180032946  imul    rsi, [rcx+8658h], 1B0h
0x180032951  mov     r8d, [rdx+4]
0x180032955  add     rsi, [rcx+86A0h]
0x18003295c  mov     ecx, [rdx+8]
0x18003295f  movsxd  rax, dword ptr [rbp+0Ch]
0x180032963  inc     ecx
0x180032965  mov     edx, ecx
0x180032967  and     ecx, 0Fh
0x18003296a  mov     [rbp+8], ecx
0x18003296d  lea     r15, [rsi+100h]
0x180032974  shr     rdx, 3
0x180032978  add     rdx, [rbp+18h]
0x18003297c  and     rdx, rax
0x18003297f  shr     r8d, 1Fh
0x180032983  mov     [rbp+18h], rdx
0x180032987  mov     eax, [rdx]
0x180032989  bswap   eax
0x18003298b  shl     eax, cl
0x18003298d  mov     [rbp+4], eax
0x180032990  mov     [rsi+188h], r8d
0x180032997  mov     byte ptr [rsi+183h], 0
0x18003299e  mov     byte ptr [rsi+181h], 1
0x1800329a5  cmp     qword ptr [rdi+8650h], 0
0x1800329ad  jbe     short loc_1800329B7
0x1800329af  mov     rcx, r15
0x1800329b2  call    freeQuantizer
0x1800329b7  cmp     dword ptr [rsi+188h], 1
0x1800329be  jnz     short loc_1800329FD
0x1800329c0  movzx   r8d, byte ptr [rsi+180h]
0x1800329c8  mov     rcx, r15
0x1800329cb  mov     [rsi+181h], r8b
0x1800329d2  mov     rdx, [rdi+85C0h]
0x1800329d9  call    allocateQuantizer
0x1800329de  test    eax, eax
0x1800329e0  jnz     short loc_180032A5E
0x1800329e2  movzx   edx, byte ptr [rsi+181h]
0x1800329e9  mov     rcx, rdi
0x1800329ec  mov     r8, [rdi+8658h]
0x1800329f3  call    useLPQuantizer
0x1800329f8  jmp     loc_180032AC1
0x1800329fd  movsxd  rax, dword ptr [rbp+0Ch]
0x180032a01  mov     r8d, [rbp+4]
0x180032a05  mov     ecx, [rbp+8]
0x180032a08  add     ecx, 4
0x180032a0b  shr     r8d, 1Ch
0x180032a0f  mov     edx, ecx
0x180032a11  inc     r8b
0x180032a14  and     ecx, 0Fh
0x180032a17  shr     rdx, 3
0x180032a1b  add     rdx, [rbp+18h]
0x180032a1f  and     rdx, rax
0x180032a22  mov     [rbp+8], ecx
0x180032a25  mov     [rbp+18h], rdx
0x180032a29  movzx   r8d, r8b
0x180032a2d  mov     eax, [rdx]
0x180032a2f  bswap   eax
0x180032a31  shl     eax, cl
0x180032a33  mov     cl, r8b
0x180032a36  mov     [rbp+4], eax
0x180032a39  mov     [rsi+181h], r8b
0x180032a40  call    dquantBits
0x180032a45  mov     [rsi+183h], al
0x180032a4b  mov     rcx, r15
0x180032a4e  mov     rdx, [rdi+85C0h]
0x180032a55  call    allocateQuantizer
0x180032a5a  test    eax, eax
0x180032a5c  jz      short loc_180032A63
0x180032a5e  or      eax, 0FFFFFFFFh
0x180032a61  jmp     short loc_180032AC3
0x180032a63  xor     r14b, r14b
0x180032a66  cmp     [rsi+181h], r14b
0x180032a6d  jbe     short loc_180032AC1
0x180032a6f  mov     r8, [rdi+85C0h]
0x180032a76  mov     rdx, rbp
0x180032a79  movzx   ebx, r14b
0x180032a7d  mov     rcx, r15
0x180032a80  mov     r9d, ebx
0x180032a83  call    readQuantizer
0x180032a88  mov     [rbx+rsi+19Dh], al
0x180032a8f  mov     r9d, ebx
0x180032a92  mov     ecx, [rdi+85B0h]
0x180032a98  mov     dl, al
0x180032a9a  mov     r8, [rdi+85C0h]
0x180032aa1  mov     [rsp+68h+var_40], ecx
0x180032aa5  mov     rcx, r15
0x180032aa8  mov     [rsp+68h+var_48], 0
0x180032ab0  call    formatQuantizer
0x180032ab5  inc     r14b
0x180032ab8  cmp     r14b, [rsi+181h]
0x180032abf  jb      short loc_180032A6F
0x180032ac1  xor     eax, eax
0x180032ac3  add     rsp, 38h
0x180032ac7  pop     r15
0x180032ac9  pop     r14
0x180032acb  pop     rdi
0x180032acc  pop     rsi
0x180032acd  pop     rbp
0x180032ace  pop     rbx
0x180032acf  retn
```
