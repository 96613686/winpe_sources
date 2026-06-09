# CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)

- ea: `0x180005850`
- end: `0x180005918`
- name: `?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z`
- size: `200`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005bbc`
- `0x180008930`
- `0x180009cf0`

## callees

- `0x180005850`

## pseudocode

```c
__int64 __fastcall CompareStrsCaseInsensitive(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int64 a3)
{
  const unsigned __int16 *v3; // r9
  unsigned __int64 v4; // rax
  unsigned __int16 v5; // cx
  unsigned __int16 v6; // r10
  unsigned __int16 v7; // r11

  v3 = a1;
  if ( a3 == -1 )
  {
    if ( a1 )
    {
      v4 = -1;
      do
        ++v4;
      while ( a1[v4] );
    }
    else
    {
      v4 = 0;
    }
    if ( a2 )
    {
      a3 = -1;
      do
        ++a3;
      while ( a2[a3] );
    }
    else
    {
      a3 = 0;
    }
    if ( v4 > a3 )
      a3 = v4;
  }
  while ( a3 )
  {
    v5 = *a2;
    if ( *v3 == *a2 )
    {
      if ( !*v3 )
        return 0;
    }
    else
    {
      if ( !*v3 )
        return 0xFFFFFFFFLL;
      if ( !v5 )
        return 1;
      v6 = *v3;
      if ( (unsigned __int16)(*v3 - 65) <= 0x19u )
        v6 += 32;
      v7 = *a2;
      if ( (unsigned __int16)(v5 - 65) <= 0x19u )
        v7 = v5 + 32;
      if ( v6 != v7 )
        return v5 < *v3 ? 1 : -1;
    }
    --a3;
    ++v3;
    ++a2;
  }
  return 0;
}

```

## disassembly

```asm
0x180005850  mov     [rsp+arg_0], rbx
0x180005855  mov     [rsp+arg_8], rdi
0x18000585a  xor     ebx, ebx
0x18000585c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180005860  mov     r9, rcx
0x180005863  cmp     r8, rdi
0x180005866  jnz     short loc_18000589C
0x180005868  test    rcx, rcx
0x18000586b  jz      short loc_18000587B
0x18000586d  mov     rax, rdi
0x180005870  inc     rax
0x180005873  cmp     [rcx+rax*2], bx
0x180005877  jnz     short loc_180005870
0x180005879  jmp     short loc_18000587E
0x18000587b  mov     rax, rbx
0x18000587e  test    rdx, rdx
0x180005881  jz      short loc_180005892
0x180005883  mov     r8, rdi
0x180005886  inc     r8
0x180005889  cmp     [rdx+r8*2], bx
0x18000588e  jnz     short loc_180005886
0x180005890  jmp     short loc_180005895
0x180005892  mov     r8, rbx
0x180005895  cmp     rax, r8
0x180005898  cmova   r8, rax
0x18000589c  cmp     r8, 1
0x1800058a0  jb      short loc_18000590B
0x1800058a2  movzx   ecx, word ptr [rdx]
0x1800058a5  cmp     [r9], cx
0x1800058a9  jz      short loc_1800058ED
0x1800058ab  cmp     bx, [r9]
0x1800058af  jz      short loc_180005907
0x1800058b1  cmp     bx, cx
0x1800058b4  jz      short loc_180005900
0x1800058b6  movzx   r10d, word ptr [r9]
0x1800058ba  lea     eax, [r10-41h]
0x1800058be  cmp     ax, 19h
0x1800058c2  ja      short loc_1800058C9
0x1800058c4  add     r10w, 20h ; ' '
0x1800058c9  lea     eax, [rcx-41h]
0x1800058cc  movzx   r11d, cx
0x1800058d0  cmp     ax, 19h
0x1800058d4  ja      short loc_1800058DA
0x1800058d6  lea     r11d, [rcx+20h]
0x1800058da  cmp     r10w, r11w
0x1800058de  jz      short loc_1800058F3
0x1800058e0  cmp     cx, [r9]
0x1800058e4  sbb     eax, eax
0x1800058e6  and     eax, 2
0x1800058e9  add     eax, edi
0x1800058eb  jmp     short loc_18000590D
0x1800058ed  cmp     bx, [r9]
0x1800058f1  jz      short loc_18000590B
0x1800058f3  dec     r8
0x1800058f6  add     r9, 2
0x1800058fa  add     rdx, 2
0x1800058fe  jmp     short loc_18000589C
0x180005900  mov     eax, 1
0x180005905  jmp     short loc_18000590D
0x180005907  mov     eax, edi
0x180005909  jmp     short loc_18000590D
0x18000590b  xor     eax, eax
0x18000590d  mov     rbx, [rsp+arg_0]
0x180005912  mov     rdi, [rsp+arg_8]
0x180005917  retn
```
