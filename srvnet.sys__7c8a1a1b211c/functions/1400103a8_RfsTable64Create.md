# RfsTable64Create

- ea: `0x1400103a8`
- end: `0x140010563`
- name: `RfsTable64Create`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140024bb8`

## callees

- `0x1400103a8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001040a`
- `ntoskrnl!ExAllocatePool2` at `0x14001040a`

## pseudocode

```c
_QWORD *__fastcall RfsTable64Create(__int64 a1, _DWORD *a2, __int64 a3, unsigned int a4, __int64 a5)
{
  unsigned int v5; // r8d
  __int64 v6; // rdi
  __int64 i; // rcx
  int v9; // edx
  bool v10; // si
  _QWORD *Pool2; // rax
  _QWORD *v12; // r11
  __int64 v13; // r9
  __int64 j; // r8
  __int64 v15; // rdx
  unsigned int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 v19; // r10
  _QWORD *result; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx

  v5 = 0;
  v6 = a4;
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    v9 = a2[i];
    if ( (unsigned int)(v9 - 1) > 0x13 )
      return 0;
    v5 += v9;
  }
  v10 = v5 <= 0x20;
  if ( v5 + a4 > 0x3E )
    return 0;
  Pool2 = (_QWORD *)ExAllocatePool2(256, 8 * (1LL << *a2) + 184, 1382437708);
  v12 = Pool2;
  if ( !Pool2 )
    return 0;
  Pool2[19] = 256;
  v13 = 2;
  for ( j = 0; j != 3; ++j )
  {
    v15 = (unsigned int)a2[j];
    Pool2[j + 9] = v13;
    v13 += v15;
    Pool2[j + 3] = (1LL << v15) - 1;
  }
  Pool2[13] = v13;
  v16 = 0;
  Pool2[14] = v13 + v6;
  Pool2[7] = (1LL << v6) - 1;
  v17 = (1LL << (64 - ((unsigned __int8)v13 + (unsigned __int8)v6))) - 1;
  v12[8] = v17;
  *((_BYTE *)v12 + 169) = v10;
  v12[15] = ~(v17 << ((unsigned __int8)v13 + (unsigned __int8)v6));
  v12[20] = a5;
  v12[2] = v12 + 23;
  *((_DWORD *)v12 + 32) = 3;
  *((_BYTE *)v12 + 168) = 0;
  *v12 = 0;
  v18 = *((unsigned int *)v12 + 6);
  if ( (_DWORD)v18 != -1 )
  {
    do
    {
      v19 = v16++;
      *(_QWORD *)(v12[2] + 8 * v19) = ((v12[3] & v16) << v12[9]) | *(_QWORD *)(v12[2] + 8 * v19) & ~(v12[3] << v12[9]);
      *(_QWORD *)(v12[2] + 8 * v19) = *(_QWORD *)(v12[2] + 8 * v19) & 0xFFFFFFFFFFFFFFFCuLL | 1;
    }
    while ( v16 < (int)v18 + 1 );
  }
  result = v12;
  *(_QWORD *)(v12[2] + 8 * v18) = -1;
  v21 = v12[2];
  v12[17] = 1;
  v22 = v21 + 8 * v18;
  v23 = v12[14];
  v12[18] = v22;
  v12[22] = ~(v12[8] << v23);
  return result;
}

```

## disassembly

```asm
0x1400103a8  push    rbx
0x1400103aa  push    rbp
0x1400103ab  push    rsi
0x1400103ac  push    rdi
0x1400103ad  sub     rsp, 28h
0x1400103b1  xor     r8d, r8d
0x1400103b4  mov     edi, r9d
0x1400103b7  xor     ecx, ecx
0x1400103b9  mov     rbx, rdx
0x1400103bc  lea     ebp, [rcx+1]
0x1400103bf  cmp     ecx, 3
0x1400103c2  jnb     short loc_1400103DA
0x1400103c4  mov     edx, [rbx+rcx*4]
0x1400103c7  lea     eax, [rdx-1]
0x1400103ca  cmp     eax, 13h
0x1400103cd  ja      loc_140010557
0x1400103d3  add     r8d, edx
0x1400103d6  add     ecx, ebp
0x1400103d8  jmp     short loc_1400103BF
0x1400103da  cmp     r8d, 20h ; ' '
0x1400103de  lea     eax, [r8+rdi]
0x1400103e2  setbe   sil
0x1400103e6  cmp     eax, 3Eh ; '>'
0x1400103e9  ja      loc_140010557
0x1400103ef  mov     ecx, [rbx]
0x1400103f1  mov     rdx, rbp
0x1400103f4  shl     rdx, cl
0x1400103f7  mov     r8d, 5266534Ch
0x1400103fd  mov     ecx, 100h
0x140010402  lea     rdx, ds:0B8h[rdx*8]
0x14001040a  call    cs:__imp_ExAllocatePool2
0x140010411  nop     dword ptr [rax+rax+00h]
0x140010416  mov     r11, rax
0x140010419  test    rax, rax
0x14001041c  jz      loc_140010557
0x140010422  mov     qword ptr [rax+98h], 100h
0x14001042d  mov     r9d, 2
0x140010433  xor     r8d, r8d
0x140010436  mov     edx, [rbx+r8*4]
0x14001043a  mov     rax, rbp
0x14001043d  mov     [r11+r8*8+48h], r9
0x140010442  mov     ecx, edx
0x140010444  shl     rax, cl
0x140010447  add     r9, rdx
0x14001044a  sub     rax, rbp
0x14001044d  mov     [r11+r8*8+18h], rax
0x140010452  add     r8, rbp
0x140010455  cmp     r8, 3
0x140010459  jnz     short loc_140010436
0x14001045b  mov     ecx, edi
0x14001045d  mov     [r11+68h], r9
0x140010461  lea     rdx, [r9+rdi]
0x140010465  mov     rax, rbp
0x140010468  shl     rax, cl
0x14001046b  xor     ebx, ebx
0x14001046d  sub     rax, rbp
0x140010470  mov     [r11+70h], rdx
0x140010474  mov     [r11+38h], rax
0x140010478  lea     ecx, [r8+3Dh]
0x14001047c  sub     cl, dl
0x14001047e  mov     rax, rbp
0x140010481  shl     rax, cl
0x140010484  mov     rcx, rdx
0x140010487  dec     rax
0x14001048a  mov     [r11+40h], rax
0x14001048e  shl     rax, cl
0x140010491  not     rax
0x140010494  mov     [r11+0A9h], sil
0x14001049b  mov     [r11+78h], rax
0x14001049f  mov     rax, [rsp+48h+arg_20]
0x1400104a4  mov     [r11+0A0h], rax
0x1400104ab  lea     rax, [r11+0B8h]
0x1400104b2  mov     [r11+10h], rax
0x1400104b6  mov     [r11+80h], r8d
0x1400104bd  mov     byte ptr [r11+0A8h], 0
0x1400104c5  mov     qword ptr [r11], 0
0x1400104cc  mov     edi, [r11+18h]
0x1400104d0  lea     esi, [rdi+1]
0x1400104d3  test    esi, esi
0x1400104d5  jz      short loc_14001051B
0x1400104d7  mov     rcx, [r11+48h]
0x1400104db  mov     r8, [r11+18h]
0x1400104df  mov     r9, [r11+10h]
0x1400104e3  mov     rdx, r8
0x1400104e6  mov     r10d, ebx
0x1400104e9  inc     ebx
0x1400104eb  shl     rdx, cl
0x1400104ee  not     rdx
0x1400104f1  mov     eax, ebx
0x1400104f3  and     rax, r8
0x1400104f6  and     rdx, [r9+r10*8]
0x1400104fa  shl     rax, cl
0x1400104fd  or      rdx, rax
0x140010500  mov     [r9+r10*8], rdx
0x140010504  mov     rcx, [r11+10h]
0x140010508  mov     rax, [rcx+r10*8]
0x14001050c  and     rax, 0FFFFFFFFFFFFFFFDh
0x140010510  or      rax, rbp
0x140010513  mov     [rcx+r10*8], rax
0x140010517  cmp     ebx, esi
0x140010519  jb      short loc_1400104D7
0x14001051b  mov     rcx, [r11+10h]
0x14001051f  mov     rax, r11
0x140010522  mov     qword ptr [rcx+rdi*8], 0FFFFFFFFFFFFFFFFh
0x14001052a  mov     rcx, [r11+10h]
0x14001052e  mov     [r11+88h], rbp
0x140010535  lea     rdx, [rcx+rdi*8]
0x140010539  mov     rcx, [r11+70h]
0x14001053d  mov     [r11+90h], rdx
0x140010544  mov     rdx, [r11+40h]
0x140010548  shl     rdx, cl
0x14001054b  not     rdx
0x14001054e  mov     [r11+0B0h], rdx
0x140010555  jmp     short loc_140010559
0x140010557  xor     eax, eax
0x140010559  add     rsp, 28h
0x14001055d  pop     rdi
0x14001055e  pop     rsi
0x14001055f  pop     rbp
0x140010560  pop     rbx
0x140010561  retn
```
