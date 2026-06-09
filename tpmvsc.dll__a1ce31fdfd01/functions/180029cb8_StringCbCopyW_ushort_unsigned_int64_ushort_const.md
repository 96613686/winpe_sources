# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180029cb8`
- end: `0x180029d24`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `108`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180028250`
- `0x18002ee4c`

## callees

- `0x180029cb8`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int64 v3; // rdx
  __int64 result; // rax
  __int64 v5; // rax
  unsigned __int16 *v6; // rax

  v3 = a2 >> 1;
  if ( !v3 )
    return 2147942487LL;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = a1 - 1;
    if ( v3 )
      v6 = a1;
    *v6 = 0;
    return v3 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180029cb8  xor     r9d, r9d
0x180029cbb  shr     rdx, 1
0x180029cbe  jz      short loc_180029D15
0x180029cc0  cmp     rdx, 7FFFFFFFh
0x180029cc7  jbe     short loc_180029CD0
0x180029cc9  mov     eax, 80070057h
0x180029cce  jmp     short loc_180029D1F
0x180029cd0  mov     eax, 7FFFFFFEh
0x180029cd5  test    rax, rax
0x180029cd8  jz      short loc_180029CF9
0x180029cda  movzx   r10d, word ptr [r8]
0x180029cde  test    r10w, r10w
0x180029ce2  jz      short loc_180029CF9
0x180029ce4  mov     [rcx], r10w
0x180029ce8  add     r8, 2
0x180029cec  add     rcx, 2
0x180029cf0  dec     rax
0x180029cf3  sub     rdx, 1
0x180029cf7  jnz     short loc_180029CD5
0x180029cf9  test    rdx, rdx
0x180029cfc  lea     rax, [rcx-2]
0x180029d00  cmovnz  rax, rcx
0x180029d04  neg     rdx
0x180029d07  mov     [rax], r9w
0x180029d0b  sbb     eax, eax
0x180029d0d  not     eax
0x180029d0f  and     eax, 8007007Ah
0x180029d14  retn
0x180029d15  mov     eax, 80070057h
0x180029d1a  test    rdx, rdx
0x180029d1d  jz      short locret_180029D23
0x180029d1f  mov     [rcx], r9w
0x180029d23  retn
```
