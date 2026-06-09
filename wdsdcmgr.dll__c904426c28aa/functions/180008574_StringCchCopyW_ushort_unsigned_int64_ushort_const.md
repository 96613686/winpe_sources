# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008574`
- end: `0x1800085f6`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `130`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ba4`
- `0x180013dcc`

## callees

- `0x180008574`

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
0x180008574  mov     [rsp+arg_0], rbx
0x180008579  xor     ebx, ebx
0x18000857b  lea     rax, [rdx-1]
0x18000857f  mov     r10d, 7FFFFFFEh
0x180008585  mov     r9d, ebx
0x180008588  cmp     rax, r10
0x18000858b  mov     r11d, 80070057h
0x180008591  cmova   r9d, r11d
0x180008595  test    r9d, r9d
0x180008598  js      short loc_1800085E5
0x18000859a  test    rdx, rdx
0x18000859d  jz      short loc_1800085C5
0x18000859f  sub     r10, rdx
0x1800085a2  sub     r8, rcx
0x1800085a5  lea     rax, [r10+rdx]
0x1800085a9  test    rax, rax
0x1800085ac  jz      short loc_1800085C5
0x1800085ae  movzx   eax, word ptr [r8+rcx]
0x1800085b3  test    ax, ax
0x1800085b6  jz      short loc_1800085C5
0x1800085b8  mov     [rcx], ax
0x1800085bb  add     rcx, 2
0x1800085bf  sub     rdx, 1
0x1800085c3  jnz     short loc_1800085A5
0x1800085c5  test    rdx, rdx
0x1800085c8  lea     rax, [rcx-2]
0x1800085cc  cmovnz  rax, rcx
0x1800085d0  neg     rdx
0x1800085d3  sbb     r9d, r9d
0x1800085d6  not     r9d
0x1800085d9  and     r9d, 8007007Ah
0x1800085e0  mov     [rax], bx
0x1800085e3  jmp     short loc_1800085ED
0x1800085e5  test    rdx, rdx
0x1800085e8  jz      short loc_1800085ED
0x1800085ea  mov     [rcx], bx
0x1800085ed  mov     rbx, [rsp+arg_0]
0x1800085f2  mov     eax, r9d
0x1800085f5  retn
```
