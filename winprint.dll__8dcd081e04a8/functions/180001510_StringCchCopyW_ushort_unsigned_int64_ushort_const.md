# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180001510`
- end: `0x18000157d`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d80`

## callees

- `0x180001510`

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
0x180001510  mov     r9, rcx
0x180001513  test    rdx, rdx
0x180001516  jz      short loc_18000156C
0x180001518  cmp     rdx, 7FFFFFFFh
0x18000151f  ja      short loc_180001565
0x180001521  mov     eax, 7FFFFFFEh
0x180001526  test    rax, rax
0x180001529  jz      short loc_180001549
0x18000152b  movzx   ecx, word ptr [r8]
0x18000152f  test    cx, cx
0x180001532  jz      short loc_180001549
0x180001534  mov     [r9], cx
0x180001538  add     r8, 2
0x18000153c  add     r9, 2
0x180001540  dec     rax
0x180001543  sub     rdx, 1
0x180001547  jnz     short loc_180001526
0x180001549  test    rdx, rdx
0x18000154c  lea     rax, [r9-2]
0x180001550  cmovnz  rax, r9
0x180001554  xor     ecx, ecx
0x180001556  test    rdx, rdx
0x180001559  mov     [rax], cx
0x18000155c  mov     eax, 8007007Ah
0x180001561  cmovnz  eax, ecx
0x180001564  retn
0x180001565  mov     eax, 80070057h
0x18000156a  jmp     short loc_180001576
0x18000156c  mov     eax, 80070057h
0x180001571  test    rdx, rdx
0x180001574  jz      short locret_180001564
0x180001576  xor     ecx, ecx
0x180001578  mov     [r9], cx
0x18000157c  retn
```
