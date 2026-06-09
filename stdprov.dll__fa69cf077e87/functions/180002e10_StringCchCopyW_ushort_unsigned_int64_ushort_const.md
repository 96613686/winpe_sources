# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180002e10`
- end: `0x180002e7d`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `32`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001100`
- `0x180001310`
- `0x1800013d0`
- `0x180001640`
- `0x1800020c0`
- `0x180002770`
- `0x180002fa0`
- `0x180003190`
- `0x1800038e0`
- `0x180003f64`
- `0x1800040c8`
- `0x1800043c0`
- `0x18000a320`
- `0x18000abf0`
- `0x18000b458`
- `0x18000c9e0`
- `0x18000e110`
- `0x18000f5f8`
- `0x18000f770`
- `0x18000f914`
- `0x18000fd08`
- `0x18000fe68`
- `0x1800101d4`
- `0x1800109a0`
- `0x1800111d0`
- `0x18001175c`
- `0x180011cf0`
- `0x180012a94`
- `0x18001345c`
- `0x1800136f0`
- `0x1800147e4`

## callees

- `0x180002e10`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  unsigned __int16 *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = v3 - 1;
    if ( a2 )
      v5 = v3;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002e10  mov     r9, rcx
0x180002e13  test    rdx, rdx
0x180002e16  jz      short loc_180002E6C
0x180002e18  cmp     rdx, 7FFFFFFFh
0x180002e1f  ja      short loc_180002E65
0x180002e21  mov     eax, 7FFFFFFEh
0x180002e26  test    rax, rax
0x180002e29  jz      short loc_180002E49
0x180002e2b  movzx   ecx, word ptr [r8]
0x180002e2f  test    cx, cx
0x180002e32  jz      short loc_180002E49
0x180002e34  mov     [r9], cx
0x180002e38  add     r8, 2
0x180002e3c  add     r9, 2
0x180002e40  dec     rax
0x180002e43  sub     rdx, 1
0x180002e47  jnz     short loc_180002E26
0x180002e49  test    rdx, rdx
0x180002e4c  lea     rax, [r9-2]
0x180002e50  cmovnz  rax, r9
0x180002e54  xor     ecx, ecx
0x180002e56  test    rdx, rdx
0x180002e59  mov     [rax], cx
0x180002e5c  mov     eax, 8007007Ah
0x180002e61  cmovnz  eax, ecx
0x180002e64  retn
0x180002e65  mov     eax, 80070057h
0x180002e6a  jmp     short loc_180002E76
0x180002e6c  mov     eax, 80070057h
0x180002e71  test    rdx, rdx
0x180002e74  jz      short locret_180002E64
0x180002e76  xor     ecx, ecx
0x180002e78  mov     [r9], cx
0x180002e7c  retn
```
