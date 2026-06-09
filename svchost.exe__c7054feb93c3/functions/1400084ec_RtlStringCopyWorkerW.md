# RtlStringCopyWorkerW

- ea: `0x1400084ec`
- end: `0x14000853d`
- name: `RtlStringCopyWorkerW`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008280`

## callees

- `0x1400084ec`

## pseudocode

```c
__int64 __fastcall RtlStringCopyWorkerW(_WORD *a1, __int64 a2, __int64 a3, _WORD *a4)
{
  __int64 v4; // r8
  __int64 i; // rax
  _WORD *v6; // rdx
  __int64 result; // rax

  v4 = a2;
  for ( i = 2147483646; v4; --v4 )
  {
    if ( !i )
      break;
    if ( !*a4 )
      break;
    *a1++ = *a4++;
    --i;
  }
  v6 = a1 - 1;
  result = v4 == 0 ? 0x80000005 : 0;
  if ( v4 )
    v6 = a1;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x1400084ec  xor     r10d, r10d
0x1400084ef  mov     r8, rdx
0x1400084f2  mov     eax, 7FFFFFFEh
0x1400084f7  test    rdx, rdx
0x1400084fa  jz      short loc_14000851E
0x1400084fc  test    rax, rax
0x1400084ff  jz      short loc_14000851E
0x140008501  movzx   edx, word ptr [r9]
0x140008505  test    dx, dx
0x140008508  jz      short loc_14000851E
0x14000850a  mov     [rcx], dx
0x14000850d  add     r9, 2
0x140008511  add     rcx, 2
0x140008515  dec     rax
0x140008518  sub     r8, 1
0x14000851c  jnz     short loc_1400084FC
0x14000851e  mov     rax, r8
0x140008521  lea     rdx, [rcx-2]
0x140008525  neg     rax
0x140008528  sbb     eax, eax
0x14000852a  not     eax
0x14000852c  and     eax, 80000005h
0x140008531  test    r8, r8
0x140008534  cmovnz  rdx, rcx
0x140008538  mov     [rdx], r10w
0x14000853c  retn
```
