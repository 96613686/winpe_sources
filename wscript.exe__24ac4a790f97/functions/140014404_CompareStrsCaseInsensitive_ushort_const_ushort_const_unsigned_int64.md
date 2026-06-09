# CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)

- ea: `0x140014404`
- end: `0x1400144d5`
- name: `?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z`
- size: `209`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006c88`
- `0x14000757c`
- `0x14000c070`
- `0x14000d810`
- `0x1400111d0`
- `0x140011404`
- `0x1400137b4`
- `0x14001550c`

## callees

- `0x140014404`

## pseudocode

```c
__int64 __fastcall CompareStrsCaseInsensitive(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int64 a3)
{
  const unsigned __int16 *v3; // r10
  const unsigned __int16 *v4; // r9
  unsigned __int64 v5; // rax
  unsigned __int16 v6; // dx
  unsigned __int16 v7; // r11
  unsigned __int16 v8; // cx

  v3 = a2;
  v4 = a1;
  if ( a3 == -1 )
  {
    if ( a1 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a1[v5] );
    }
    else
    {
      v5 = 0;
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
    if ( v5 > a3 )
      a3 = v5;
  }
  while ( 1 )
  {
    if ( !a3 )
      return 0;
    v6 = *v3;
    if ( *v4 == *v3 )
    {
      if ( !*v4 )
        return 0;
      goto LABEL_25;
    }
    if ( !*v4 )
      return 0xFFFFFFFFLL;
    if ( !v6 )
      return 1;
    v7 = *v4;
    if ( (unsigned __int16)(*v4 - 65) <= 0x19u )
      v7 += 32;
    v8 = v6 + 32;
    if ( (unsigned __int16)(v6 - 65) > 0x19u )
      v8 = *v3;
    if ( v7 != v8 )
      return v6 < *v4 ? 1 : -1;
LABEL_25:
    --a3;
    ++v4;
    ++v3;
  }
}

```

## disassembly

```asm
0x140014404  mov     [rsp+arg_0], rbx
0x140014409  mov     [rsp+arg_8], rdi
0x14001440e  xor     ebx, ebx
0x140014410  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140014414  mov     r10, rdx
0x140014417  mov     r9, rcx
0x14001441a  cmp     r8, rdi
0x14001441d  jnz     loc_1400144B7
0x140014423  test    rcx, rcx
0x140014426  jz      short loc_140014436
0x140014428  mov     rax, rdi
0x14001442b  inc     rax
0x14001442e  cmp     [rcx+rax*2], bx
0x140014432  jnz     short loc_14001442B
0x140014434  jmp     short loc_140014439
0x140014436  mov     rax, rbx
0x140014439  test    rdx, rdx
0x14001443c  jz      short loc_14001444D
0x14001443e  mov     r8, rdi
0x140014441  inc     r8
0x140014444  cmp     [rdx+r8*2], bx
0x140014449  jnz     short loc_140014441
0x14001444b  jmp     short loc_140014450
0x14001444d  mov     r8, rbx
0x140014450  cmp     rax, r8
0x140014453  cmova   r8, rax
0x140014457  jmp     short loc_1400144B7
0x140014459  movzx   edx, word ptr [r10]
0x14001445d  cmp     [r9], dx
0x140014461  jz      short loc_1400144A6
0x140014463  cmp     bx, [r9]
0x140014467  jz      short loc_1400144D1
0x140014469  cmp     bx, dx
0x14001446c  jz      short loc_1400144CA
0x14001446e  movzx   eax, word ptr [r9]
0x140014472  movzx   r11d, word ptr [r9]
0x140014476  sub     ax, 41h ; 'A'
0x14001447a  cmp     ax, 19h
0x14001447e  ja      short loc_140014485
0x140014480  add     r11w, 20h ; ' '
0x140014485  lea     eax, [rdx-41h]
0x140014488  cmp     ax, 19h
0x14001448c  lea     ecx, [rdx+20h]
0x14001448f  cmova   cx, dx
0x140014493  cmp     r11w, cx
0x140014497  jz      short loc_1400144AC
0x140014499  cmp     dx, [r9]
0x14001449d  sbb     eax, eax
0x14001449f  and     eax, 2
0x1400144a2  add     eax, edi
0x1400144a4  jmp     short loc_1400144BF
0x1400144a6  cmp     bx, [r9]
0x1400144aa  jz      short loc_1400144BD
0x1400144ac  dec     r8
0x1400144af  add     r9, 2
0x1400144b3  add     r10, 2
0x1400144b7  cmp     r8, 1
0x1400144bb  jnb     short loc_140014459
0x1400144bd  xor     eax, eax
0x1400144bf  mov     rbx, [rsp+arg_0]
0x1400144c4  mov     rdi, [rsp+arg_8]
0x1400144c9  retn
0x1400144ca  mov     eax, 1
0x1400144cf  jmp     short loc_1400144BF
0x1400144d1  mov     eax, edi
0x1400144d3  jmp     short loc_1400144BF
```
