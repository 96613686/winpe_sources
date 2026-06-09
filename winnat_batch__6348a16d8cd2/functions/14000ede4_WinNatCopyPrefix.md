# WinNatCopyPrefix

- ea: `0x14000ede4`
- end: `0x14000ee37`
- name: `WinNatCopyPrefix`
- size: `83`
- prototype: `char __fastcall(__int64, __int64, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400019f0`
- `0x14000f288`
- `0x140010380`
- `0x1400193ac`
- `0x140019528`
- `0x14001ac70`

## callees

- `0x14000ede4`

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
0x14000ede4  mov     [rsp+arg_0], rbx
0x14000ede9  mov     r10d, r8d
0x14000edec  xor     eax, eax
0x14000edee  shr     r10d, 3
0x14000edf2  and     r8d, 7
0x14000edf6  mov     rbx, rcx
0x14000edf9  test    r9d, r9d
0x14000edfc  jz      short loc_14000EE14
0x14000edfe  cmp     eax, r10d
0x14000ee01  jnb     short loc_14000EE08
0x14000ee03  mov     cl, [rax+rdx]
0x14000ee06  jmp     short loc_14000EE0A
0x14000ee08  xor     cl, cl
0x14000ee0a  mov     [rax+rbx], cl
0x14000ee0d  inc     eax
0x14000ee0f  cmp     eax, r9d
0x14000ee12  jb      short loc_14000EDFE
0x14000ee14  test    r8d, r8d
0x14000ee17  jz      short loc_14000EE30
0x14000ee19  mov     ecx, 8
0x14000ee1e  mov     eax, 0FFh
0x14000ee23  sub     ecx, r8d
0x14000ee26  shl     al, cl
0x14000ee28  and     al, [r10+rdx]
0x14000ee2c  mov     [r10+rbx], al
0x14000ee30  mov     rbx, [rsp+arg_0]
0x14000ee35  retn
```
