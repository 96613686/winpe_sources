# RtlStringLengthWorkerW

- ea: `0x180002750`
- end: `0x18000278c`
- name: `RtlStringLengthWorkerW`
- size: `60`
- prototype: `__int64 __fastcall(_WORD *, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ec0`
- `0x1800027a0`
- `0x180004180`
- `0x1800056d0`
- `0x180008d20`

## callees

- `0x180002750`

## pseudocode

```c
__int64 __fastcall RtlStringLengthWorkerW(_WORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax
  __int64 v4; // r9

  result = 0;
  v4 = a2;
  if ( a2 )
  {
    while ( *a1 )
    {
      ++a1;
      if ( !--a2 )
        goto LABEL_4;
    }
  }
  else
  {
LABEL_4:
    result = 3221225485LL;
  }
  if ( a3 )
  {
    if ( (int)result < 0 )
      *a3 = 0;
    else
      *a3 = v4 - a2;
  }
  return result;
}

```

## disassembly

```asm
0x180002750  xor     eax, eax
0x180002752  mov     r9, rdx
0x180002755  test    rdx, rdx
0x180002758  jz      short loc_18000276F
0x18000275a  nop     word ptr [rax+rax+00h]
0x180002760  cmp     [rcx], ax
0x180002763  jz      short loc_180002774
0x180002765  add     rcx, 2
0x180002769  sub     rdx, 1
0x18000276d  jnz     short loc_180002760
0x18000276f  mov     eax, 0C000000Dh
0x180002774  test    r8, r8
0x180002777  jz      short locret_180002783
0x180002779  test    eax, eax
0x18000277b  js      short loc_180002784
0x18000277d  sub     r9, rdx
0x180002780  mov     [r8], r9
0x180002783  retn
0x180002784  mov     qword ptr [r8], 0
0x18000278b  retn
```
