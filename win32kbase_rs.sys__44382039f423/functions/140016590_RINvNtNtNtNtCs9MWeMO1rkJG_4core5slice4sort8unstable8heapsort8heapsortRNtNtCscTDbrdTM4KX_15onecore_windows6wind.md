# _RINvNtNtNtNtCs9MWeMO1rkJG_4core5slice4sort8unstable8heapsort8heapsortRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB8_SB15_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2C_10RegionCore16subtract_complex0E0EB2C_

- ea: `0x140016590`
- end: `0x140016649`
- name: `_RINvNtNtNtNtCs9MWeMO1rkJG_4core5slice4sort8unstable8heapsort8heapsortRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB8_SB15_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2C_10RegionCore16subtract_complex0E0EB2C_`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140016650`

## callees

- `0x140016590`

## pseudocode

```c
unsigned __int64 __fastcall RINvNtNtNtNtCs9MWeMO1rkJG_4core5slice4sort8unstable8heapsort8heapsortRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB8_SB15_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2C_10RegionCore16subtract_complex0E0EB2C_(
        __int64 *a1,
        unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  unsigned __int64 v3; // r8
  __int64 v4; // r8
  unsigned __int64 v5; // r9
  unsigned __int64 v6; // r10
  __int64 v7; // rsi
  unsigned __int64 v8; // r11
  __int64 v9; // r10
  __int64 v10; // rsi

  result = a2 + (a2 >> 1);
  while ( result )
  {
    v3 = --result - a2;
    if ( result < a2 )
    {
      v4 = *a1;
      *a1 = a1[result];
      a1[result] = v4;
      v3 = 0;
    }
    v5 = result;
    if ( a2 < result )
      v5 = a2;
    v6 = 2 * v3 + 1;
    if ( v6 < v5 )
    {
      v7 = 2 * v3;
      do
      {
        if ( v7 + 2 >= v5 )
          v8 = v6;
        else
          v8 = v6 + (*(_DWORD *)(a1[v6] + 4) < *(_DWORD *)(a1[v7 + 2] + 4));
        v9 = a1[v3];
        v10 = a1[v8];
        if ( *(_DWORD *)(v9 + 4) >= *(_DWORD *)(v10 + 4) )
          break;
        a1[v3] = v10;
        a1[v8] = v9;
        v7 = 2 * v8;
        v6 = 2 * v8 + 1;
        v3 = v8;
      }
      while ( v6 < v5 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x140016590  push    rsi
0x140016591  push    rdi
0x140016592  mov     rax, rdx
0x140016595  shr     rax, 1
0x140016598  add     rax, rdx
0x14001659b  jnz     short loc_1400165A5
0x14001659d  pop     rdi
0x14001659e  pop     rsi
0x14001659f  retn
0x1400165a0  test    rax, rax
0x1400165a3  jz      short loc_14001659D
0x1400165a5  dec     rax
0x1400165a8  mov     r8, rax
0x1400165ab  sub     r8, rdx
0x1400165ae  jnb     short loc_1400165C1
0x1400165b0  mov     r8, [rcx]
0x1400165b3  mov     r9, [rcx+rax*8]
0x1400165b7  mov     [rcx], r9
0x1400165ba  mov     [rcx+rax*8], r8
0x1400165be  xor     r8d, r8d
0x1400165c1  cmp     rdx, rax
0x1400165c4  mov     r9, rax
0x1400165c7  cmovb   r9, rdx
0x1400165cb  lea     r10, ds:1[r8*2]
0x1400165d3  cmp     r10, r9
0x1400165d6  jnb     short loc_1400165A0
0x1400165d8  lea     rsi, [r8+r8]
0x1400165dc  nop     dword ptr [rax+00h]
0x1400165e0  lea     r11, [rsi+2]
0x1400165e4  cmp     r11, r9
0x1400165e7  jnb     short loc_140016610
0x1400165e9  mov     r11, [rcx+r10*8]
0x1400165ed  mov     rsi, [rcx+rsi*8+10h]
0x1400165f2  mov     edi, [r11+4]
0x1400165f6  xor     r11d, r11d
0x1400165f9  cmp     edi, [rsi+4]
0x1400165fc  setl    r11b
0x140016600  add     r11, r10
0x140016603  jmp     short loc_140016613
0x140016610  mov     r11, r10
0x140016613  mov     r10, [rcx+r8*8]
0x140016617  mov     rsi, [rcx+r11*8]
0x14001661b  mov     edi, [r10+4]
0x14001661f  cmp     edi, [rsi+4]
0x140016622  jge     loc_1400165A0
0x140016628  mov     [rcx+r8*8], rsi
0x14001662c  mov     [rcx+r11*8], r10
0x140016630  lea     rsi, [r11+r11]
0x140016634  lea     r10, ds:1[r11*2]
0x14001663c  mov     r8, r11
0x14001663f  cmp     r10, r9
0x140016642  jb      short loc_1400165E0
0x140016644  jmp     loc_1400165A0
```
