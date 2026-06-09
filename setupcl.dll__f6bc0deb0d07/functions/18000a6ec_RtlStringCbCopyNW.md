# RtlStringCbCopyNW

- ea: `0x18000a6ec`
- end: `0x18000a754`
- name: `RtlStringCbCopyNW`
- size: `104`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, _WORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a75c`
- `0x180011cb4`

## callees

- `0x18000a6ec`

## pseudocode

```c
__int64 __fastcall RtlStringCbCopyNW(_WORD *a1, unsigned __int64 a2, _WORD *a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdx
  _WORD *v5; // r10
  unsigned __int64 v6; // r9
  _WORD *v8; // rax

  v4 = a2 >> 1;
  v5 = a1;
  if ( v4 - 1 > 0x7FFFFFFE )
    return 3221225485LL;
  v6 = a4 >> 1;
  if ( v6 > 0x7FFFFFFE )
  {
    *a1 = 0;
    return 3221225485LL;
  }
  do
  {
    if ( !v6 )
      break;
    if ( !*a3 )
      break;
    *v5++ = *a3++;
    --v6;
    --v4;
  }
  while ( v4 );
  v8 = v5 - 1;
  if ( v4 )
    v8 = v5;
  *v8 = 0;
  return v4 == 0 ? 0x80000005 : 0;
}

```

## disassembly

```asm
0x18000a6ec  shr     rdx, 1
0x18000a6ef  mov     r10, rcx
0x18000a6f2  mov     ecx, 7FFFFFFEh
0x18000a6f7  lea     rax, [rdx-1]
0x18000a6fb  cmp     rax, rcx
0x18000a6fe  ja      short loc_18000A70E
0x18000a700  shr     r9, 1
0x18000a703  cmp     r9, rcx
0x18000a706  jbe     short loc_18000A714
0x18000a708  xor     ecx, ecx
0x18000a70a  mov     [r10], cx
0x18000a70e  mov     eax, 0C000000Dh
0x18000a713  retn
0x18000a714  xor     ecx, ecx
0x18000a716  test    r9, r9
0x18000a719  jz      short loc_18000A739
0x18000a71b  movzx   eax, word ptr [r8]
0x18000a71f  test    ax, ax
0x18000a722  jz      short loc_18000A739
0x18000a724  mov     [r10], ax
0x18000a728  add     r8, 2
0x18000a72c  add     r10, 2
0x18000a730  dec     r9
0x18000a733  sub     rdx, 1
0x18000a737  jnz     short loc_18000A716
0x18000a739  test    rdx, rdx
0x18000a73c  lea     rax, [r10-2]
0x18000a740  cmovnz  rax, r10
0x18000a744  neg     rdx
0x18000a747  mov     [rax], cx
0x18000a74a  sbb     eax, eax
0x18000a74c  not     eax
0x18000a74e  and     eax, 80000005h
0x18000a753  retn
```
