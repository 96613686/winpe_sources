# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180001eb0`
- end: `0x180001f1b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001df8`
- `0x180002b00`

## callees

- `0x180001eb0`

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
0x180001eb0  xor     r10d, r10d
0x180001eb3  mov     r9, rcx
0x180001eb6  test    rdx, rdx
0x180001eb9  jz      short loc_180001F0C
0x180001ebb  cmp     rdx, 7FFFFFFFh
0x180001ec2  jbe     short loc_180001ECB
0x180001ec4  mov     eax, 80070057h
0x180001ec9  jmp     short loc_180001F16
0x180001ecb  mov     eax, 7FFFFFFEh
0x180001ed0  test    rax, rax
0x180001ed3  jz      short loc_180001EF3
0x180001ed5  movzx   ecx, word ptr [r8]
0x180001ed9  test    cx, cx
0x180001edc  jz      short loc_180001EF3
0x180001ede  mov     [r9], cx
0x180001ee2  add     r8, 2
0x180001ee6  add     r9, 2
0x180001eea  dec     rax
0x180001eed  sub     rdx, 1
0x180001ef1  jnz     short loc_180001ED0
0x180001ef3  test    rdx, rdx
0x180001ef6  lea     rcx, [r9-2]
0x180001efa  cmovnz  rcx, r9
0x180001efe  neg     rdx
0x180001f01  sbb     eax, eax
0x180001f03  not     eax
0x180001f05  and     eax, 8007007Ah
0x180001f0a  jmp     short loc_180001F16
0x180001f0c  mov     eax, 80070057h
0x180001f11  test    rdx, rdx
0x180001f14  jz      short locret_180001F1A
0x180001f16  mov     [rcx], r10w
0x180001f1a  retn
```
