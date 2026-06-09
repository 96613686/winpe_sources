# readTileHeaderLP

- ea: `0x180031110`
- end: `0x1800312bd`
- name: `readTileHeaderLP`
- size: `429`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800093ac`
- `0x18000a220`

## callees

- `0x180002644`
- `0x180011738`
- `0x1800118d8`
- `0x180031110`
- `0x180034df4`
- `0x18003dfe0`
- `0x18003ef7c`

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
  __int64 v10; // r8
  char v11; // r8
  __int64 v12; // rcx
  unsigned int *v13; // rdx
  unsigned __int32 v14; // eax
  __int64 v15; // r8
  unsigned __int8 i; // r15
  char Quantizer; // al
  int v19; // edx

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
    v11 = (*(_DWORD *)(a2 + 4) >> 28) + 1;
    v12 = (*(_BYTE *)(a2 + 8) + 4) & 0xF;
    v13 = (unsigned int *)(*(int *)(a2 + 12)
                         & (*(_QWORD *)(a2 + 24) + ((unsigned __int64)(unsigned int)(*(_DWORD *)(a2 + 8) + 4) >> 3)));
    *(_DWORD *)(a2 + 8) = v12;
    *(_QWORD *)(a2 + 24) = v13;
    v14 = _byteswap_ulong(*v13) << v12;
    LOBYTE(v12) = v11;
    *(_DWORD *)(a2 + 4) = v14;
    *(_BYTE *)(v5 + 384) = v11;
    *(_BYTE *)(v5 + 386) = dquantBits(v12);
    if ( !(unsigned int)allocateQuantizer(v5 + 128, *(_QWORD *)(a1 + 34240), v15) )
    {
      for ( i = 0; i < *(_BYTE *)(v5 + 384); ++i )
      {
        Quantizer = readQuantizer(v5 + 128, a2, *(_QWORD *)(a1 + 34240), i);
        *(_BYTE *)(i + v5 + 397) = Quantizer;
        LOBYTE(v19) = Quantizer;
        formatQuantizer(v5 + 128, v19, *(_QWORD *)(a1 + 34240), i, 1, *(_DWORD *)(a1 + 34224));
      }
      return 0;
    }
    return 0xFFFFFFFFLL;
  }
  if ( (unsigned int)allocateQuantizer(v5 + 128, *(_QWORD *)(a1 + 34240), *(unsigned __int8 *)(v5 + 384)) )
    return 0xFFFFFFFFLL;
  useDCQuantizer(a1, *(_QWORD *)(a1 + 34392), v10);
  return 0;
}

```

## disassembly

```asm
0x180031110  push    rbx
0x180031112  push    rbp
0x180031113  push    rsi
0x180031114  push    rdi
0x180031115  push    r14
0x180031117  push    r15
0x180031119  sub     rsp, 38h
0x18003111d  cmp     dword ptr [rcx+0BCh], 3
0x180031124  mov     r14, rdx
0x180031127  mov     rdi, rcx
0x18003112a  jz      loc_1800312AE
0x180031130  test    byte ptr [rcx+85ECh], 2
0x180031137  jz      loc_1800312AE
0x18003113d  imul    rsi, [rcx+8658h], 1B0h
0x180031148  mov     r8d, [rdx+4]
0x18003114c  xor     ebx, ebx
0x18003114e  add     rsi, [rcx+86A0h]
0x180031155  mov     ecx, [rdx+8]
0x180031158  movsxd  rax, dword ptr [r14+0Ch]
0x18003115c  inc     ecx
0x18003115e  mov     edx, ecx
0x180031160  and     ecx, 0Fh
0x180031163  mov     [r14+8], ecx
0x180031167  lea     rbp, [rsi+80h]
0x18003116e  shr     rdx, 3
0x180031172  add     rdx, [r14+18h]
0x180031176  and     rdx, rax
0x180031179  shr     r8d, 1Fh
0x18003117d  mov     [r14+18h], rdx
0x180031181  mov     eax, [rdx]
0x180031183  bswap   eax
0x180031185  shl     eax, cl
0x180031187  mov     [r14+4], eax
0x18003118b  mov     [rsi+184h], r8d
0x180031192  mov     [rsi+182h], bl
0x180031198  mov     byte ptr [rsi+180h], 1
0x18003119f  cmp     [rdi+8650h], rbx
0x1800311a6  jbe     short loc_1800311B0
0x1800311a8  mov     rcx, rbp
0x1800311ab  call    freeQuantizer
0x1800311b0  cmp     dword ptr [rsi+184h], 1
0x1800311b7  jnz     short loc_1800311E8
0x1800311b9  movzx   r8d, byte ptr [rsi+180h]
0x1800311c1  mov     rcx, rbp
0x1800311c4  mov     rdx, [rdi+85C0h]
0x1800311cb  call    allocateQuantizer
0x1800311d0  test    eax, eax
0x1800311d2  jnz     short loc_18003124C
0x1800311d4  mov     rdx, [rdi+8658h]
0x1800311db  mov     rcx, rdi
0x1800311de  call    useDCQuantizer
0x1800311e3  jmp     loc_1800312AE
0x1800311e8  movsxd  rax, dword ptr [r14+0Ch]
0x1800311ec  mov     r8d, [r14+4]
0x1800311f0  mov     ecx, [r14+8]
0x1800311f4  add     ecx, 4
0x1800311f7  shr     r8d, 1Ch
0x1800311fb  mov     edx, ecx
0x1800311fd  inc     r8b
0x180031200  and     ecx, 0Fh
0x180031203  shr     rdx, 3
0x180031207  add     rdx, [r14+18h]
0x18003120b  and     rdx, rax
0x18003120e  mov     [r14+8], ecx
0x180031212  mov     [r14+18h], rdx
0x180031216  movzx   r8d, r8b
0x18003121a  mov     eax, [rdx]
0x18003121c  bswap   eax
0x18003121e  shl     eax, cl
0x180031220  mov     cl, r8b
0x180031223  mov     [r14+4], eax
0x180031227  mov     [rsi+180h], r8b
0x18003122e  call    dquantBits
0x180031233  mov     [rsi+182h], al
0x180031239  mov     rcx, rbp
0x18003123c  mov     rdx, [rdi+85C0h]
0x180031243  call    allocateQuantizer
0x180031248  test    eax, eax
0x18003124a  jz      short loc_180031251
0x18003124c  or      eax, 0FFFFFFFFh
0x18003124f  jmp     short loc_1800312B0
0x180031251  mov     r15b, bl
0x180031254  cmp     [rsi+180h], bl
0x18003125a  jbe     short loc_1800312AE
0x18003125c  mov     r8, [rdi+85C0h]
0x180031263  mov     rdx, r14
0x180031266  movzx   ebx, r15b
0x18003126a  mov     rcx, rbp
0x18003126d  mov     r9d, ebx
0x180031270  call    readQuantizer
0x180031275  mov     [rbx+rsi+18Dh], al
0x18003127c  mov     r9d, ebx
0x18003127f  mov     ecx, [rdi+85B0h]
0x180031285  mov     dl, al
0x180031287  mov     r8, [rdi+85C0h]
0x18003128e  mov     [rsp+68h+var_40], ecx
0x180031292  mov     rcx, rbp
0x180031295  mov     [rsp+68h+var_48], 1
0x18003129d  call    formatQuantizer
0x1800312a2  inc     r15b
0x1800312a5  cmp     r15b, [rsi+180h]
0x1800312ac  jb      short loc_18003125C
0x1800312ae  xor     eax, eax
0x1800312b0  add     rsp, 38h
0x1800312b4  pop     r15
0x1800312b6  pop     r14
0x1800312b8  pop     rdi
0x1800312b9  pop     rsi
0x1800312ba  pop     rbp
0x1800312bb  pop     rbx
0x1800312bc  retn
```
