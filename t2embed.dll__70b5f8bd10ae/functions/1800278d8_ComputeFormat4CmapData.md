# ComputeFormat4CmapData

- ea: `0x1800278d8`
- end: `0x180027b54`
- name: `ComputeFormat4CmapData`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d5f8`

## callees

- `0x180013230`
- `0x18001d0e8`
- `0x1800278d8`

## pseudocode

```c
__int64 __fastcall ComputeFormat4CmapData(
        _WORD *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        _WORD *a5,
        __int64 a6,
        unsigned __int16 a7)
{
  _WORD *v7; // r13
  unsigned __int16 v8; // r12
  unsigned __int16 v10; // r10
  __int64 v11; // r14
  __int64 v12; // rbp
  int v13; // r8d
  unsigned __int16 i; // si
  __int64 v15; // rax
  int v16; // ecx
  __int16 v17; // cx
  __int16 v18; // ax
  __int16 v19; // cx
  unsigned __int16 v20; // si
  unsigned __int16 v21; // r14
  unsigned __int16 v22; // r10
  unsigned __int16 v23; // bp
  unsigned __int16 v24; // r8
  unsigned __int16 v25; // dx
  unsigned __int16 v26; // cx
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int16 v29; // si
  __int16 v30; // bx
  __int16 v31; // bx
  __int16 v32; // ax
  unsigned __int16 v33; // di
  __int64 result; // rax
  __int16 v35; // r9

  v7 = a5;
  v8 = 0;
  v10 = 0;
  *a5 = 0;
  if ( a7 )
  {
    do
    {
      v11 = v10;
      while ( v10 < a7 - 1 && *(unsigned __int16 *)(a6 + 4LL * v10) + 1 == *(unsigned __int16 *)(a6 + 4LL * v10 + 4) )
        ++v10;
      v12 = v10;
      v13 = 1;
      ++v10;
      for ( i = v11; i < (unsigned __int16)v12; v13 = v16 )
      {
        if ( !v13 )
          break;
        v15 = i;
        v16 = 0;
        ++i;
        if ( *(unsigned __int16 *)(a6 + 4 * v15 + 2) + 1 == *(unsigned __int16 *)(a6 + 4 * v15 + 6) )
          v16 = v13;
      }
      *(_WORD *)(a2 + 8LL * v8 + 2) = *(_WORD *)(a6 + 4 * v11);
      *(_WORD *)(a2 + 8LL * v8) = *(_WORD *)(a6 + 4 * v12);
      if ( v13 )
      {
        v17 = 0;
        v18 = *(_WORD *)(a6 + 4 * v11 + 2) - *(_WORD *)(a6 + 4 * v11);
      }
      else
      {
        v17 = 1;
        v18 = 0;
      }
      *(_WORD *)(a2 + 8LL * v8 + 4) = v18;
      *(_WORD *)(a2 + 8LL * v8 + 6) = v17;
      v19 = ++v8;
    }
    while ( v10 < a7 );
    v20 = v19;
    v7 = a5;
    if ( v19 )
    {
      v21 = 0;
      v22 = 0;
      do
      {
        v23 = *(_WORD *)(a2 + 8LL * v22 + 2);
        v24 = *(_WORD *)(a2 + 8LL * v22);
        if ( *(_WORD *)(a2 + 8LL * v22 + 6) )
        {
          v25 = *a5;
          *(_WORD *)(a2 + 8LL * v22 + 6) = 2 * (v19 + *a5 - v22 + 1);
          if ( v23 <= v24 )
          {
            v26 = v25;
            do
            {
              v27 = v21;
              ++v25;
              ++v21;
              ++v23;
              *(_WORD *)(a4 + 2LL * v26) = *(_WORD *)(a6 + 4 * v27 + 2);
              v26 = v25;
            }
            while ( v23 <= *(_WORD *)(a2 + 8LL * v22) );
            *a5 = v25;
          }
        }
        else
        {
          *(_WORD *)(a2 + 8LL * v22 + 6) = 0;
          v21 += v24 - v23 + 1;
        }
        ++v22;
        v19 = v20;
      }
      while ( v22 < v20 );
    }
  }
  else
  {
    v20 = 0;
  }
  v28 = v20;
  v29 = v20 + 1;
  *a3 = v29;
  *(_DWORD *)(a2 + 8 * v28 + 4) = 1;
  *(_DWORD *)(a2 + 8 * v28) = -1;
  *a1 = 4;
  a1[2] = 0;
  v30 = v29 * GetGenericSize(&FORMAT4_SEGMENTS_CONTROL);
  v31 = GetGenericSize(&CMAP_FORMAT4_CONTROL) + v30;
  v32 = *v7 + 1;
  a1[3] = 2 * v29;
  a1[1] = 2 * v32 + v31;
  v33 = 1 << (log2ui16(v29) + 1);
  a1[4] = v33;
  result = log2ui16(v33 >> 1);
  a1[6] = v35 - v33;
  a1[5] = result;
  return result;
}

```

## disassembly

```asm
0x1800278d8  mov     rax, rsp
0x1800278db  mov     [rax+10h], rbx
0x1800278df  mov     [rax+20h], r9
0x1800278e3  mov     [rax+18h], r8
0x1800278e7  mov     [rax+8], rcx
0x1800278eb  push    rbp
0x1800278ec  push    rsi
0x1800278ed  push    rdi
0x1800278ee  push    r12
0x1800278f0  push    r13
0x1800278f2  push    r14
0x1800278f4  push    r15
0x1800278f6  sub     rsp, 20h
0x1800278fa  mov     r13, [rsp+58h+arg_20]
0x180027902  xor     r12d, r12d
0x180027905  movzx   r15d, [rsp+58h+arg_30]
0x18002790e  mov     r11, rdx
0x180027911  mov     rbx, [rsp+58h+arg_28]
0x180027919  mov     r10d, r12d
0x18002791c  mov     [r13+0], r12w
0x180027921  lea     edi, [r12+1]
0x180027926  cmp     r12w, r15w
0x18002792a  jnb     loc_180027AA1
0x180027930  mov     r9d, r15d
0x180027933  sub     r9d, edi
0x180027936  xor     r13d, r13d
0x180027939  movzx   r14d, r10w
0x18002793d  jmp     short loc_180027956
0x18002793f  movzx   eax, r10w
0x180027943  movzx   ecx, word ptr [rbx+rax*4]
0x180027947  movzx   eax, word ptr [rbx+rax*4+4]
0x18002794c  add     ecx, edi
0x18002794e  cmp     ecx, eax
0x180027950  jnz     short loc_18002795F
0x180027952  add     r10w, di
0x180027956  movzx   eax, r10w
0x18002795a  cmp     eax, r9d
0x18002795d  jl      short loc_18002793F
0x18002795f  movzx   ebp, r10w
0x180027963  mov     r8d, edi
0x180027966  add     r10w, di
0x18002796a  movzx   esi, r14w
0x18002796e  cmp     r14w, bp
0x180027972  jnb     short loc_18002799C
0x180027974  test    r8d, r8d
0x180027977  jz      short loc_18002799C
0x180027979  movzx   eax, si
0x18002797c  mov     ecx, r13d
0x18002797f  add     si, di
0x180027982  movzx   edx, word ptr [rbx+rax*4+2]
0x180027987  movzx   eax, word ptr [rbx+rax*4+6]
0x18002798c  add     edx, edi
0x18002798e  cmp     edx, eax
0x180027990  cmovz   ecx, r8d
0x180027994  mov     r8d, ecx
0x180027997  cmp     si, bp
0x18002799a  jb      short loc_180027974
0x18002799c  movzx   eax, word ptr [rbx+r14*4]
0x1800279a1  movzx   edx, r12w
0x1800279a5  mov     [r11+rdx*8+2], ax
0x1800279ab  movzx   ecx, word ptr [rbx+rbp*4]
0x1800279af  mov     [r11+rdx*8], cx
0x1800279b4  test    r8d, r8d
0x1800279b7  jz      short loc_1800279C9
0x1800279b9  movzx   eax, word ptr [rbx+r14*4+2]
0x1800279bf  mov     ecx, r13d
0x1800279c2  sub     ax, [rbx+r14*4]
0x1800279c7  jmp     short loc_1800279CF
0x1800279c9  movzx   ecx, di
0x1800279cc  mov     eax, r13d
0x1800279cf  mov     [r11+rdx*8+4], ax
0x1800279d5  mov     [r11+rdx*8+6], cx
0x1800279db  lea     ecx, [rdi+r12]
0x1800279df  movzx   r12d, cx
0x1800279e3  cmp     r10w, r15w
0x1800279e7  jb      loc_180027939
0x1800279ed  cmp     r13w, cx
0x1800279f1  movzx   esi, cx
0x1800279f4  mov     r13, [rsp+58h+arg_20]
0x1800279fc  jnb     loc_180027A9C
0x180027a02  mov     r15, [rsp+58h+arg_18]
0x180027a07  xor     r12d, r12d
0x180027a0a  mov     r14d, r12d
0x180027a0d  mov     r10d, r12d
0x180027a10  movzx   r9d, r10w
0x180027a14  movzx   ebp, word ptr [r11+r9*8+2]
0x180027a1a  movzx   r8d, word ptr [r11+r9*8]
0x180027a1f  cmp     [r11+r9*8+6], r12w
0x180027a25  jnz     short loc_180027A3B
0x180027a27  sub     r8w, bp
0x180027a2b  mov     [r11+r9*8+6], r12w
0x180027a31  add     r8w, di
0x180027a35  add     r14w, r8w
0x180027a39  jmp     short loc_180027A89
0x180027a3b  movzx   edx, word ptr [r13+0]
0x180027a40  movzx   eax, dx
0x180027a43  sub     ax, r10w
0x180027a47  add     ax, cx
0x180027a4a  add     ax, di
0x180027a4d  add     ax, ax
0x180027a50  mov     [r11+r9*8+6], ax
0x180027a56  cmp     bp, r8w
0x180027a5a  ja      short loc_180027A89
0x180027a5c  movzx   ecx, dx
0x180027a5f  movzx   eax, r14w
0x180027a63  add     dx, di
0x180027a66  movzx   ecx, cx
0x180027a69  add     r14w, di
0x180027a6d  add     bp, di
0x180027a70  movzx   eax, word ptr [rbx+rax*4+2]
0x180027a75  mov     [r15+rcx*2], ax
0x180027a7a  movzx   ecx, dx
0x180027a7d  cmp     bp, [r11+r9*8]
0x180027a82  jbe     short loc_180027A5F
0x180027a84  mov     [r13+0], dx
0x180027a89  add     r10w, di
0x180027a8d  movzx   ecx, si
0x180027a90  cmp     r10w, si
0x180027a94  jb      loc_180027A10
0x180027a9a  jmp     short loc_180027AA4
0x180027a9c  xor     r12d, r12d
0x180027a9f  jmp     short loc_180027AA4
0x180027aa1  mov     esi, r12d
0x180027aa4  mov     rax, [rsp+58h+arg_10]
0x180027aa9  mov     r14, [rsp+58h+arg_0]
0x180027aae  movzx   ecx, si
0x180027ab1  add     si, di
0x180027ab4  mov     [rax], si
0x180027ab7  mov     [r11+rcx*8+4], edi
0x180027abc  mov     dword ptr [r11+rcx*8], 0FFFFFFFFh
0x180027ac4  lea     rcx, FORMAT4_SEGMENTS_CONTROL
0x180027acb  mov     word ptr [r14], 4
0x180027ad1  mov     [r14+4], r12w
0x180027ad6  call    GetGenericSize
0x180027adb  movzx   ecx, si
0x180027ade  movzx   ebx, ax
0x180027ae1  imul    ebx, ecx
0x180027ae4  lea     rcx, CMAP_FORMAT4_CONTROL
0x180027aeb  call    GetGenericSize
0x180027af0  add     bx, ax
0x180027af3  movzx   r9d, si
0x180027af7  movzx   eax, word ptr [r13+0]
0x180027afc  add     r9w, r9w
0x180027b00  add     ax, di
0x180027b03  mov     [r14+6], r9w
0x180027b08  add     ax, ax
0x180027b0b  movzx   ecx, si
0x180027b0e  add     bx, ax
0x180027b11  mov     [r14+2], bx
0x180027b16  call    log2ui16
0x180027b1b  lea     ecx, [rdi+rax]
0x180027b1e  shl     di, cl
0x180027b21  movzx   ecx, di
0x180027b24  mov     [r14+8], di
0x180027b29  shr     cx, 1
0x180027b2c  call    log2ui16
0x180027b31  mov     rbx, [rsp+58h+arg_8]
0x180027b36  sub     r9w, di
0x180027b3a  mov     [r14+0Ch], r9w
0x180027b3f  mov     [r14+0Ah], ax
0x180027b44  add     rsp, 20h
0x180027b48  pop     r15
0x180027b4a  pop     r14
0x180027b4c  pop     r13
0x180027b4e  pop     r12
0x180027b50  pop     rdi
0x180027b51  pop     rsi
0x180027b52  pop     rbp
0x180027b53  retn
```
