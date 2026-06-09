# StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x140002c30`
- end: `0x140002c99`
- name: `?StringCchCopyW@@YAJPEA_W_KPEB_W@Z`
- size: `105`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c980`

## callees

- `0x140002c30`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(wchar_t *a1, __int64 a2, const wchar_t *a3)
{
  __int64 v3; // r9
  signed __int64 v4; // r10
  wchar_t v5; // ax
  wchar_t *v6; // rax
  __int64 result; // rax

  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    result = 2147942487LL;
    if ( a2 )
      *a1 = 0;
  }
  else
  {
    v3 = 2147483646 - a2;
    v4 = (char *)a3 - (char *)a1;
    do
    {
      if ( !(v3 + a2) )
        break;
      v5 = *(wchar_t *)((char *)a1 + v4);
      if ( !v5 )
        break;
      *a1++ = v5;
      --a2;
    }
    while ( a2 );
    v6 = a1 - 1;
    if ( a2 )
      v6 = a1;
    *v6 = 0;
    return a2 == 0 ? 0x8007007A : 0;
  }
  return result;
}

```

## disassembly

```asm
0x140002c30  lea     rax, [rdx-1]
0x140002c34  mov     r9d, 7FFFFFFEh
0x140002c3a  mov     r10, r8
0x140002c3d  cmp     rax, r9
0x140002c40  ja      short loc_140002C87
0x140002c42  sub     r9, rdx
0x140002c45  sub     r10, rcx
0x140002c48  xor     r8d, r8d
0x140002c4b  lea     rax, [r9+rdx]
0x140002c4f  test    rax, rax
0x140002c52  jz      short loc_140002C6B
0x140002c54  movzx   eax, word ptr [r10+rcx]
0x140002c59  test    ax, ax
0x140002c5c  jz      short loc_140002C6B
0x140002c5e  mov     [rcx], ax
0x140002c61  add     rcx, 2
0x140002c65  sub     rdx, 1
0x140002c69  jnz     short loc_140002C4B
0x140002c6b  test    rdx, rdx
0x140002c6e  lea     rax, [rcx-2]
0x140002c72  cmovnz  rax, rcx
0x140002c76  neg     rdx
0x140002c79  mov     [rax], r8w
0x140002c7d  sbb     eax, eax
0x140002c7f  not     eax
0x140002c81  and     eax, 8007007Ah
0x140002c86  retn
0x140002c87  xor     r8d, r8d
0x140002c8a  mov     eax, 80070057h
0x140002c8f  test    rdx, rdx
0x140002c92  jz      short locret_140002C98
0x140002c94  mov     [rcx], r8w
0x140002c98  retn
```
