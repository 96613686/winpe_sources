# formatQuantizer

- ea: `0x180011738`
- end: `0x18001181a`
- name: `formatQuantizer`
- size: `226`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000129c`
- `0x1800110d0`
- `0x180031110`
- `0x1800312c4`
- `0x180032738`
- `0x180032914`
- `0x180042088`
- `0x180042294`

## callees

- `0x180011738`
- `0x180011820`

## pseudocode

```c
__int64 __fastcall formatQuantizer(__int64 *a1, char a2, unsigned __int64 a3, __int64 a4, int a5, unsigned int a6)
{
  unsigned __int64 v6; // rbx
  __int64 v7; // r11
  _BOOL8 v12; // r9
  __int64 result; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx

  if ( a3 )
  {
    v6 = 0;
    v7 = 20 * a4;
    if ( a2 == 1 )
    {
      do
      {
        v12 = 1;
        if ( v6 )
        {
          v15 = a1[1];
          v16 = a1[v6];
          *(_OWORD *)(v16 + v7) = *(_OWORD *)(v15 + v7);
          *(_DWORD *)(v16 + v7 + 16) = *(_DWORD *)(v15 + v7 + 16);
          if ( a5 == 1 )
            v12 = 0;
        }
        result = remapQP(v7 + a1[v6++], v12, a6, v12);
      }
      while ( v6 < a3 );
    }
    else
    {
      do
      {
        if ( !v6 )
          goto LABEL_8;
        if ( !a2 )
        {
          v17 = *a1;
          v18 = a1[v6];
          v19 = 5 * a4;
          *(_OWORD *)(v18 + 4 * v19) = *(_OWORD *)(*a1 + 20 * a4);
          *(_DWORD *)(v18 + 4 * v19 + 16) = *(_DWORD *)(v17 + 20 * a4 + 16);
        }
        if ( a5 == 1 )
          v14 = 0;
        else
LABEL_8:
          v14 = 1;
        result = remapQP(v7 + a1[v6++], v14, a6, a4);
      }
      while ( v6 < a3 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011738  test    r8, r8
0x18001173b  jz      short locret_18001179B
0x18001173d  push    rbx
0x18001173e  push    rbp
0x18001173f  push    rsi
0x180011740  push    rdi
0x180011741  push    r14
0x180011743  sub     rsp, 20h
0x180011747  lea     r11, [r9+r9*4]
0x18001174b  xor     ebx, ebx
0x18001174d  shl     r11, 2
0x180011751  mov     rdi, r9
0x180011754  mov     r14, r8
0x180011757  mov     bpl, dl
0x18001175a  mov     rsi, rcx
0x18001175d  cmp     dl, 1
0x180011760  jnz     short loc_18001179C
0x180011762  lea     rdx, ds:0[rbx*8]
0x18001176a  test    rbx, rbx
0x18001176d  jnz     short loc_1800117C1
0x18001176f  mov     r9d, 1
0x180011775  mov     rcx, [rsi+rdx]
0x180011779  mov     edx, r9d
0x18001177c  mov     r8d, [rsp+48h+arg_28]
0x180011781  add     rcx, r11
0x180011784  call    remapQP
0x180011789  inc     rbx
0x18001178c  cmp     rbx, r14
0x18001178f  jb      short loc_180011762
0x180011791  add     rsp, 20h
0x180011795  pop     r14
0x180011797  pop     rdi
0x180011798  pop     rsi
0x180011799  pop     rbp
0x18001179a  pop     rbx
0x18001179b  retn
0x18001179c  test    rbx, rbx
0x18001179f  jnz     short loc_1800117E9
0x1800117a1  mov     edx, 1
0x1800117a6  mov     rcx, [rsi+rbx*8]
0x1800117aa  mov     r8d, [rsp+48h+arg_28]
0x1800117af  add     rcx, r11
0x1800117b2  call    remapQP
0x1800117b7  inc     rbx
0x1800117ba  cmp     rbx, r14
0x1800117bd  jb      short loc_18001179C
0x1800117bf  jmp     short loc_180011791
0x1800117c1  cmp     [rsp+48h+arg_20], 1
0x1800117c6  mov     rax, [rsi+8]
0x1800117ca  mov     rcx, [rdx+rsi]
0x1800117ce  movups  xmm0, xmmword ptr [rax+r11]
0x1800117d3  movups  xmmword ptr [rcx+r11], xmm0
0x1800117d8  mov     eax, [rax+r11+10h]
0x1800117dd  mov     [rcx+r11+10h], eax
0x1800117e2  jnz     short loc_18001176F
0x1800117e4  xor     r9d, r9d
0x1800117e7  jmp     short loc_180011775
0x1800117e9  test    bpl, bpl
0x1800117ec  jnz     short loc_18001180F
0x1800117ee  mov     rax, [rsi]
0x1800117f1  lea     r8, [rdi+rdi*4]
0x1800117f5  mov     rcx, [rsi+rbx*8]
0x1800117f9  lea     rdx, [rdi+rdi*4]
0x1800117fd  movups  xmm0, xmmword ptr [rax+r8*4]
0x180011802  movups  xmmword ptr [rcx+rdx*4], xmm0
0x180011806  mov     eax, [rax+r8*4+10h]
0x18001180b  mov     [rcx+rdx*4+10h], eax
0x18001180f  cmp     [rsp+48h+arg_20], 1
0x180011814  jnz     short loc_1800117A1
0x180011816  xor     edx, edx
0x180011818  jmp     short loc_1800117A6
```
