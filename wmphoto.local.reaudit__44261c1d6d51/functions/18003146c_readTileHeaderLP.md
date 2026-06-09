# readTileHeaderLP

- ea: `0x18003146c`
- end: `0x18003161a`
- name: `readTileHeaderLP`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800094bc`
- `0x18000a330`

## callees

- `0x1800026ac`
- `0x18001190c`
- `0x180011ab4`
- `0x18003146c`
- `0x1800353cc`
- `0x18003e798`
- `0x18003f748`

## pseudocode

```c
__int64 __fastcall readTileHeaderLP(__int64 a1, __int64 a2)
{
  unsigned int v4; // r8d
  __int64 v5; // rsi
  __int64 v6; // rax
  unsigned __int64 v7; // rdx
  char v8; // cl
  unsigned int *v9; // rdx
  char v10; // r8
  __int64 v11; // rcx
  unsigned int *v12; // rdx
  unsigned __int32 v13; // eax
  __int64 v14; // r8
  unsigned __int8 i; // r15
  char Quantizer; // al
  int v18; // edx

  if ( *(_DWORD *)(a1 + 188) == 3 || (*(_BYTE *)(a1 + 34284) & 2) == 0 )
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
  *(_DWORD *)(v5 + 388) = v4 >> 31;
  *(_BYTE *)(v5 + 386) = 0;
  *(_BYTE *)(v5 + 384) = 1;
  if ( *(_QWORD *)(a1 + 34384) )
    freeQuantizer(v5 + 128);
  if ( *(_DWORD *)(v5 + 388) != 1 )
  {
    v10 = (*(_DWORD *)(a2 + 4) >> 28) + 1;
    v11 = (*(_BYTE *)(a2 + 8) + 4) & 0xF;
    v12 = (unsigned int *)(*(int *)(a2 + 12)
                         & (*(_QWORD *)(a2 + 24) + ((unsigned __int64)(unsigned int)(*(_DWORD *)(a2 + 8) + 4) >> 3)));
    *(_DWORD *)(a2 + 8) = v11;
    *(_QWORD *)(a2 + 24) = v12;
    v13 = _byteswap_ulong(*v12) << v11;
    LOBYTE(v11) = v10;
    *(_DWORD *)(a2 + 4) = v13;
    *(_BYTE *)(v5 + 384) = v10;
    *(_BYTE *)(v5 + 386) = dquantBits(v11);
    if ( !(unsigned int)allocateQuantizer(v5 + 128, *(_QWORD *)(a1 + 34240), v14) )
    {
      for ( i = 0; i < *(_BYTE *)(v5 + 384); ++i )
      {
        Quantizer = readQuantizer(v5 + 128, a2, *(_QWORD *)(a1 + 34240), i);
        *(_BYTE *)(i + v5 + 397) = Quantizer;
        LOBYTE(v18) = Quantizer;
        formatQuantizer(v5 + 128, v18, *(_QWORD *)(a1 + 34240), i, 1, *(_DWORD *)(a1 + 34224));
      }
      return 0;
    }
    return 0xFFFFFFFFLL;
  }
  if ( (unsigned int)allocateQuantizer(v5 + 128, *(_QWORD *)(a1 + 34240), *(unsigned __int8 *)(v5 + 384)) )
    return 0xFFFFFFFFLL;
  useDCQuantizer(a1, *(_QWORD *)(a1 + 34392));
  return 0;
}

```

## disassembly

```asm
0x18003146c  push    rbx
0x18003146e  push    rbp
0x18003146f  push    rsi
0x180031470  push    rdi
0x180031471  push    r14
0x180031473  push    r15
0x180031475  sub     rsp, 38h
0x180031479  cmp     dword ptr [rcx+0BCh], 3
0x180031480  mov     r14, rdx
0x180031483  mov     rdi, rcx
0x180031486  jz      loc_18003160A
0x18003148c  test    byte ptr [rcx+85ECh], 2
0x180031493  jz      loc_18003160A
0x180031499  imul    rsi, [rcx+8658h], 1B0h
0x1800314a4  mov     r8d, [rdx+4]
0x1800314a8  xor     ebx, ebx
0x1800314aa  add     rsi, [rcx+86A0h]
0x1800314b1  mov     ecx, [rdx+8]
0x1800314b4  movsxd  rax, dword ptr [r14+0Ch]
0x1800314b8  inc     ecx
0x1800314ba  mov     edx, ecx
0x1800314bc  and     ecx, 0Fh
0x1800314bf  mov     [r14+8], ecx
0x1800314c3  lea     rbp, [rsi+80h]
0x1800314ca  shr     rdx, 3
0x1800314ce  add     rdx, [r14+18h]
0x1800314d2  and     rdx, rax
0x1800314d5  shr     r8d, 1Fh
0x1800314d9  mov     [r14+18h], rdx
0x1800314dd  mov     eax, [rdx]
0x1800314df  bswap   eax
0x1800314e1  shl     eax, cl
0x1800314e3  mov     [r14+4], eax
0x1800314e7  mov     [rsi+184h], r8d
0x1800314ee  mov     [rsi+182h], bl
0x1800314f4  mov     byte ptr [rsi+180h], 1
0x1800314fb  cmp     [rdi+8650h], rbx
0x180031502  jbe     short loc_18003150C
0x180031504  mov     rcx, rbp
0x180031507  call    freeQuantizer
0x18003150c  cmp     dword ptr [rsi+184h], 1
0x180031513  jnz     short loc_180031544
0x180031515  movzx   r8d, byte ptr [rsi+180h]
0x18003151d  mov     rcx, rbp
0x180031520  mov     rdx, [rdi+85C0h]
0x180031527  call    allocateQuantizer
0x18003152c  test    eax, eax
0x18003152e  jnz     short loc_1800315A8
0x180031530  mov     rdx, [rdi+8658h]
0x180031537  mov     rcx, rdi
0x18003153a  call    useDCQuantizer
0x18003153f  jmp     loc_18003160A
0x180031544  movsxd  rax, dword ptr [r14+0Ch]
0x180031548  mov     r8d, [r14+4]
0x18003154c  mov     ecx, [r14+8]
0x180031550  add     ecx, 4
0x180031553  shr     r8d, 1Ch
0x180031557  mov     edx, ecx
0x180031559  inc     r8b
0x18003155c  and     ecx, 0Fh
0x18003155f  shr     rdx, 3
0x180031563  add     rdx, [r14+18h]
0x180031567  and     rdx, rax
0x18003156a  mov     [r14+8], ecx
0x18003156e  mov     [r14+18h], rdx
0x180031572  movzx   r8d, r8b
0x180031576  mov     eax, [rdx]
0x180031578  bswap   eax
0x18003157a  shl     eax, cl
0x18003157c  mov     cl, r8b
0x18003157f  mov     [r14+4], eax
0x180031583  mov     [rsi+180h], r8b
0x18003158a  call    dquantBits
0x18003158f  mov     [rsi+182h], al
0x180031595  mov     rcx, rbp
0x180031598  mov     rdx, [rdi+85C0h]
0x18003159f  call    allocateQuantizer
0x1800315a4  test    eax, eax
0x1800315a6  jz      short loc_1800315AD
0x1800315a8  or      eax, 0FFFFFFFFh
0x1800315ab  jmp     short loc_18003160C
0x1800315ad  mov     r15b, bl
0x1800315b0  cmp     [rsi+180h], bl
0x1800315b6  jbe     short loc_18003160A
0x1800315b8  mov     r8, [rdi+85C0h]
0x1800315bf  mov     rdx, r14
0x1800315c2  movzx   ebx, r15b
0x1800315c6  mov     rcx, rbp
0x1800315c9  mov     r9d, ebx
0x1800315cc  call    readQuantizer
0x1800315d1  mov     [rbx+rsi+18Dh], al
0x1800315d8  mov     r9d, ebx
0x1800315db  mov     ecx, [rdi+85B0h]
0x1800315e1  mov     dl, al
0x1800315e3  mov     r8, [rdi+85C0h]
0x1800315ea  mov     [rsp+68h+var_40], ecx
0x1800315ee  mov     rcx, rbp
0x1800315f1  mov     [rsp+68h+var_48], 1
0x1800315f9  call    formatQuantizer
0x1800315fe  inc     r15b
0x180031601  cmp     r15b, [rsi+180h]
0x180031608  jb      short loc_1800315B8
0x18003160a  xor     eax, eax
0x18003160c  add     rsp, 38h
0x180031610  pop     r15
0x180031612  pop     r14
0x180031614  pop     rdi
0x180031615  pop     rsi
0x180031616  pop     rbp
0x180031617  pop     rbx
0x180031618  retn
```
