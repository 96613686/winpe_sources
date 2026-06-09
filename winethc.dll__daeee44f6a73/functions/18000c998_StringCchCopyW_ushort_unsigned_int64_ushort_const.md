# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000c998`
- end: `0x18000ca03`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d60`
- `0x180005b30`
- `0x180007800`
- `0x1800087b4`
- `0x18000ca0c`
- `0x18000e2a4`
- `0x18000f5f8`

## callees

- `0x18000c998`

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
0x18000c998  xor     r10d, r10d
0x18000c99b  mov     r9, rcx
0x18000c99e  test    rdx, rdx
0x18000c9a1  jz      short loc_18000C9F4
0x18000c9a3  cmp     rdx, 7FFFFFFFh
0x18000c9aa  jbe     short loc_18000C9B3
0x18000c9ac  mov     eax, 80070057h
0x18000c9b1  jmp     short loc_18000C9FE
0x18000c9b3  mov     eax, 7FFFFFFEh
0x18000c9b8  test    rax, rax
0x18000c9bb  jz      short loc_18000C9DB
0x18000c9bd  movzx   ecx, word ptr [r8]
0x18000c9c1  test    cx, cx
0x18000c9c4  jz      short loc_18000C9DB
0x18000c9c6  mov     [r9], cx
0x18000c9ca  add     r8, 2
0x18000c9ce  add     r9, 2
0x18000c9d2  dec     rax
0x18000c9d5  sub     rdx, 1
0x18000c9d9  jnz     short loc_18000C9B8
0x18000c9db  test    rdx, rdx
0x18000c9de  lea     rcx, [r9-2]
0x18000c9e2  cmovnz  rcx, r9
0x18000c9e6  neg     rdx
0x18000c9e9  sbb     eax, eax
0x18000c9eb  not     eax
0x18000c9ed  and     eax, 8007007Ah
0x18000c9f2  jmp     short loc_18000C9FE
0x18000c9f4  mov     eax, 80070057h
0x18000c9f9  test    rdx, rdx
0x18000c9fc  jz      short locret_18000CA02
0x18000c9fe  mov     [rcx], r10w
0x18000ca02  retn
```
