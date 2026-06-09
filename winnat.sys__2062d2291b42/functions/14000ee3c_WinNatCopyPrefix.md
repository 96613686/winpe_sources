# WinNatCopyPrefix

- ea: `0x14000ee3c`
- end: `0x14000ee8f`
- name: `WinNatCopyPrefix`
- size: `83`
- prototype: `char __fastcall(__int64, __int64, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400019f0`
- `0x14000f2e0`
- `0x1400103e0`
- `0x14001988c`
- `0x140019a08`
- `0x14001b150`

## callees

- `0x14000ee3c`

## pseudocode

```c
char __fastcall WinNatCopyPrefix(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // rax
  __int64 v5; // r10
  int i; // r8d
  char v8; // cl

  v4 = 0;
  v5 = a3 >> 3;
  for ( i = a3 & 7; (unsigned int)v4 < a4; v4 = (unsigned int)(v4 + 1) )
  {
    if ( (unsigned int)v4 >= (unsigned int)v5 )
      v8 = 0;
    else
      v8 = *(_BYTE *)(v4 + a2);
    *(_BYTE *)(v4 + a1) = v8;
  }
  if ( i )
  {
    LOBYTE(v4) = *(_BYTE *)(v5 + a2) & (-1 << (8 - i));
    *(_BYTE *)(v5 + a1) = v4;
  }
  return v4;
}

```

## disassembly

```asm
0x14000ee3c  mov     [rsp+arg_0], rbx
0x14000ee41  mov     r10d, r8d
0x14000ee44  xor     eax, eax
0x14000ee46  shr     r10d, 3
0x14000ee4a  and     r8d, 7
0x14000ee4e  mov     rbx, rcx
0x14000ee51  test    r9d, r9d
0x14000ee54  jz      short loc_14000EE6C
0x14000ee56  cmp     eax, r10d
0x14000ee59  jnb     short loc_14000EE60
0x14000ee5b  mov     cl, [rax+rdx]
0x14000ee5e  jmp     short loc_14000EE62
0x14000ee60  xor     cl, cl
0x14000ee62  mov     [rax+rbx], cl
0x14000ee65  inc     eax
0x14000ee67  cmp     eax, r9d
0x14000ee6a  jb      short loc_14000EE56
0x14000ee6c  test    r8d, r8d
0x14000ee6f  jz      short loc_14000EE88
0x14000ee71  mov     ecx, 8
0x14000ee76  mov     eax, 0FFh
0x14000ee7b  sub     ecx, r8d
0x14000ee7e  shl     al, cl
0x14000ee80  and     al, [r10+rdx]
0x14000ee84  mov     [r10+rbx], al
0x14000ee88  mov     rbx, [rsp+arg_0]
0x14000ee8d  retn
```
