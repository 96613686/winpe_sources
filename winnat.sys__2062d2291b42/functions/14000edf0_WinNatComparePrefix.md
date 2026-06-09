# WinNatComparePrefix

- ea: `0x14000edf0`
- end: `0x14000ee33`
- name: `WinNatComparePrefix`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400107b0`

## callees

- `0x14000edf0`

## pseudocode

```c
bool __fastcall WinNatComparePrefix(_BYTE *a1, _BYTE *a2, unsigned int a3)
{
  while ( a3 > 8 )
  {
    if ( *a1 != *a2 )
      return 0;
    ++a2;
    ++a1;
    a3 -= 8;
  }
  return !a3 || *a1 >> (8 - a3) == *a2 >> (8 - a3);
}

```

## disassembly

```asm
0x14000edf0  mov     r9, rdx
0x14000edf3  mov     r10d, 8
0x14000edf9  cmp     r8d, r10d
0x14000edfc  jbe     short loc_14000EE15
0x14000edfe  mov     al, [r9]
0x14000ee01  cmp     [rcx], al
0x14000ee03  jnz     short loc_14000EE11
0x14000ee05  inc     r9
0x14000ee08  inc     rcx
0x14000ee0b  add     r8d, 0FFFFFFF8h
0x14000ee0f  jmp     short loc_14000EDF9
0x14000ee11  xor     al, al
0x14000ee13  retn
0x14000ee15  test    r8d, r8d
0x14000ee18  jz      short loc_14000EE30
0x14000ee1a  mov     dl, [rcx]
0x14000ee1c  sub     r10b, r8b
0x14000ee1f  mov     al, [r9]
0x14000ee22  mov     cl, r10b
0x14000ee25  shr     al, cl
0x14000ee27  shr     dl, cl
0x14000ee29  cmp     dl, al
0x14000ee2b  setz    al
0x14000ee2e  retn
0x14000ee30  mov     al, 1
0x14000ee32  retn
```
