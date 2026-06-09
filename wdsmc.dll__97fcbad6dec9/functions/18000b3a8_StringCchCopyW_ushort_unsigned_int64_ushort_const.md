# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000b3a8`
- end: `0x18000b42a`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `130`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b178`
- `0x18000b560`
- `0x18000f688`
- `0x18000fa3c`
- `0x18001ed10`
- `0x1800244bc`

## callees

- `0x18000b3a8`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(char *a1, __int64 a2, char *a3)
{
  signed int v3; // r9d
  __int64 v4; // r10
  signed __int64 v5; // r8
  unsigned __int16 v6; // ax
  unsigned __int16 *v7; // rax

  v3 = 0;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    v3 = -2147024809;
  if ( v3 < 0 )
  {
    if ( a2 )
      *(_WORD *)a1 = 0;
  }
  else
  {
    if ( a2 )
    {
      v4 = 2147483646 - a2;
      v5 = a3 - a1;
      do
      {
        if ( !(v4 + a2) )
          break;
        v6 = *(_WORD *)&a1[v5];
        if ( !v6 )
          break;
        *(_WORD *)a1 = v6;
        a1 += 2;
        --a2;
      }
      while ( a2 );
    }
    v7 = (unsigned __int16 *)(a1 - 2);
    if ( a2 )
      v7 = (unsigned __int16 *)a1;
    v3 = a2 == 0 ? 0x8007007A : 0;
    *v7 = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b3a8  mov     [rsp+arg_0], rbx
0x18000b3ad  xor     ebx, ebx
0x18000b3af  lea     rax, [rdx-1]
0x18000b3b3  mov     r10d, 7FFFFFFEh
0x18000b3b9  mov     r9d, ebx
0x18000b3bc  cmp     rax, r10
0x18000b3bf  mov     r11d, 80070057h
0x18000b3c5  cmova   r9d, r11d
0x18000b3c9  test    r9d, r9d
0x18000b3cc  js      short loc_18000B419
0x18000b3ce  test    rdx, rdx
0x18000b3d1  jz      short loc_18000B3F9
0x18000b3d3  sub     r10, rdx
0x18000b3d6  sub     r8, rcx
0x18000b3d9  lea     rax, [r10+rdx]
0x18000b3dd  test    rax, rax
0x18000b3e0  jz      short loc_18000B3F9
0x18000b3e2  movzx   eax, word ptr [r8+rcx]
0x18000b3e7  test    ax, ax
0x18000b3ea  jz      short loc_18000B3F9
0x18000b3ec  mov     [rcx], ax
0x18000b3ef  add     rcx, 2
0x18000b3f3  sub     rdx, 1
0x18000b3f7  jnz     short loc_18000B3D9
0x18000b3f9  test    rdx, rdx
0x18000b3fc  lea     rax, [rcx-2]
0x18000b400  cmovnz  rax, rcx
0x18000b404  neg     rdx
0x18000b407  sbb     r9d, r9d
0x18000b40a  not     r9d
0x18000b40d  and     r9d, 8007007Ah
0x18000b414  mov     [rax], bx
0x18000b417  jmp     short loc_18000B421
0x18000b419  test    rdx, rdx
0x18000b41c  jz      short loc_18000B421
0x18000b41e  mov     [rcx], bx
0x18000b421  mov     rbx, [rsp+arg_0]
0x18000b426  mov     eax, r9d
0x18000b429  retn
```
