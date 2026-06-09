# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180007f14`
- end: `0x180007f7f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a54`
- `0x18000e1a8`
- `0x1800117e0`

## callees

- `0x180007f14`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180007f14  xor     r10d, r10d
0x180007f17  mov     r9, rcx
0x180007f1a  test    rdx, rdx
0x180007f1d  jz      short loc_180007F70
0x180007f1f  cmp     rdx, 7FFFFFFFh
0x180007f26  jbe     short loc_180007F2F
0x180007f28  mov     eax, 80070057h
0x180007f2d  jmp     short loc_180007F7A
0x180007f2f  mov     eax, 7FFFFFFEh
0x180007f34  test    rax, rax
0x180007f37  jz      short loc_180007F57
0x180007f39  movzx   ecx, word ptr [r8]
0x180007f3d  test    cx, cx
0x180007f40  jz      short loc_180007F57
0x180007f42  mov     [r9], cx
0x180007f46  add     r8, 2
0x180007f4a  add     r9, 2
0x180007f4e  dec     rax
0x180007f51  sub     rdx, 1
0x180007f55  jnz     short loc_180007F34
0x180007f57  test    rdx, rdx
0x180007f5a  lea     rcx, [r9-2]
0x180007f5e  cmovnz  rcx, r9
0x180007f62  neg     rdx
0x180007f65  sbb     eax, eax
0x180007f67  not     eax
0x180007f69  and     eax, 8007007Ah
0x180007f6e  jmp     short loc_180007F7A
0x180007f70  mov     eax, 80070057h
0x180007f75  test    rdx, rdx
0x180007f78  jz      short locret_180007F7E
0x180007f7a  mov     [rcx], r10w
0x180007f7e  retn
```
