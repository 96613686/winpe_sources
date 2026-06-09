# RtlUShortAdd(ushort,ushort,ushort *)

- ea: `0x180008da0`
- end: `0x180008dbe`
- name: `?RtlUShortAdd@@YAJGGPEAG@Z`
- size: `30`
- prototype: `__int64 __fastcall(unsigned __int16, unsigned __int16, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004dd0`
- `0x18000b3b4`
- `0x180013060`
- `0x180013490`

## callees

- `0x180008da0`

## pseudocode

```c
__int64 __fastcall RtlUShortAdd(unsigned __int16 a1, __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 v3; // dx

  if ( (unsigned __int16)(a1 + 2) < a1 )
    v3 = -1;
  else
    v3 = a1 + 2;
  *a3 = v3;
  return (unsigned __int16)(a1 + 2) < a1 ? 0xC0000095 : 0;
}

```

## disassembly

```asm
0x180008da0  lea     eax, [rcx+2]
0x180008da3  cmp     ax, cx
0x180008da6  jb      short loc_180008DAD
0x180008da8  movzx   edx, ax
0x180008dab  jmp     short loc_180008DB2
0x180008dad  mov     edx, 0FFFFh
0x180008db2  sbb     eax, eax
0x180008db4  mov     [r8], dx
0x180008db8  and     eax, 0C0000095h
0x180008dbd  retn
```
