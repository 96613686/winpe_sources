# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180036efc`
- end: `0x180036f4b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180036fe0`

## callees

- `0x180036efc`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v5; // rdx
  __int64 result; // rax

  v3 = 2147483646;
  v4 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = a1 - 1;
  result = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v5 = a1;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x180036efc  mov     eax, 7FFFFFFEh
0x180036f01  mov     r9d, 104h
0x180036f07  xor     r10d, r10d
0x180036f0a  test    rax, rax
0x180036f0d  jz      short loc_180036F2C
0x180036f0f  movzx   edx, word ptr [r8]
0x180036f13  test    dx, dx
0x180036f16  jz      short loc_180036F2C
0x180036f18  mov     [rcx], dx
0x180036f1b  add     r8, 2
0x180036f1f  add     rcx, 2
0x180036f23  dec     rax
0x180036f26  sub     r9, 1
0x180036f2a  jnz     short loc_180036F0A
0x180036f2c  mov     rax, r9
0x180036f2f  lea     rdx, [rcx-2]
0x180036f33  neg     rax
0x180036f36  sbb     eax, eax
0x180036f38  not     eax
0x180036f3a  and     eax, 8007007Ah
0x180036f3f  test    r9, r9
0x180036f42  cmovnz  rdx, rcx
0x180036f46  mov     [rdx], r10w
0x180036f4a  retn
```
