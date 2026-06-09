# formatQuantizer

- ea: `0x18001190c`
- end: `0x1800119ef`
- name: `formatQuantizer`
- size: `227`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012bc`
- `0x18001128c`
- `0x18003146c`
- `0x180031620`
- `0x180032cb4`
- `0x180032eb4`
- `0x180042878`
- `0x180042a84`

## callees

- `0x18001190c`
- `0x1800119f8`

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
0x18001190c  test    r8, r8
0x18001190f  jz      short locret_18001196F
0x180011911  push    rbx
0x180011912  push    rbp
0x180011913  push    rsi
0x180011914  push    rdi
0x180011915  push    r14
0x180011917  sub     rsp, 20h
0x18001191b  lea     r11, [r9+r9*4]
0x18001191f  xor     ebx, ebx
0x180011921  shl     r11, 2
0x180011925  mov     rdi, r9
0x180011928  mov     r14, r8
0x18001192b  mov     bpl, dl
0x18001192e  mov     rsi, rcx
0x180011931  cmp     dl, 1
0x180011934  jnz     short loc_180011971
0x180011936  lea     rdx, ds:0[rbx*8]
0x18001193e  test    rbx, rbx
0x180011941  jnz     short loc_180011996
0x180011943  mov     r9d, 1
0x180011949  mov     rcx, [rsi+rdx]
0x18001194d  mov     edx, r9d
0x180011950  mov     r8d, [rsp+48h+arg_28]
0x180011955  add     rcx, r11
0x180011958  call    remapQP
0x18001195d  inc     rbx
0x180011960  cmp     rbx, r14
0x180011963  jb      short loc_180011936
0x180011965  add     rsp, 20h
0x180011969  pop     r14
0x18001196b  pop     rdi
0x18001196c  pop     rsi
0x18001196d  pop     rbp
0x18001196e  pop     rbx
0x18001196f  retn
0x180011971  test    rbx, rbx
0x180011974  jnz     short loc_1800119BE
0x180011976  mov     edx, 1
0x18001197b  mov     rcx, [rsi+rbx*8]
0x18001197f  mov     r8d, [rsp+48h+arg_28]
0x180011984  add     rcx, r11
0x180011987  call    remapQP
0x18001198c  inc     rbx
0x18001198f  cmp     rbx, r14
0x180011992  jb      short loc_180011971
0x180011994  jmp     short loc_180011965
0x180011996  cmp     [rsp+48h+arg_20], 1
0x18001199b  mov     rax, [rsi+8]
0x18001199f  mov     rcx, [rdx+rsi]
0x1800119a3  movups  xmm0, xmmword ptr [rax+r11]
0x1800119a8  movups  xmmword ptr [rcx+r11], xmm0
0x1800119ad  mov     eax, [rax+r11+10h]
0x1800119b2  mov     [rcx+r11+10h], eax
0x1800119b7  jnz     short loc_180011943
0x1800119b9  xor     r9d, r9d
0x1800119bc  jmp     short loc_180011949
0x1800119be  test    bpl, bpl
0x1800119c1  jnz     short loc_1800119E4
0x1800119c3  mov     rax, [rsi]
0x1800119c6  lea     r8, [rdi+rdi*4]
0x1800119ca  mov     rcx, [rsi+rbx*8]
0x1800119ce  lea     rdx, [rdi+rdi*4]
0x1800119d2  movups  xmm0, xmmword ptr [rax+r8*4]
0x1800119d7  movups  xmmword ptr [rcx+rdx*4], xmm0
0x1800119db  mov     eax, [rax+r8*4+10h]
0x1800119e0  mov     [rcx+rdx*4+10h], eax
0x1800119e4  cmp     [rsp+48h+arg_20], 1
0x1800119e9  jnz     short loc_180011976
0x1800119eb  xor     edx, edx
0x1800119ed  jmp     short loc_18001197B
```
