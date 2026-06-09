# CmdBufStartCommand

- ea: `0x14003950c`
- end: `0x14003956a`
- name: `CmdBufStartCommand`
- size: `94`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140033400`
- `0x140033bd8`
- `0x140034398`
- `0x1400344a4`

## callees

- `0x140039058`
- `0x1400390c4`
- `0x14003950c`

## pseudocode

```c
__int64 __fastcall CmdBufStartCommand(_QWORD *a1)
{
  __int64 result; // rax
  __int64 v2; // r10
  __int64 v3; // r10
  unsigned int v4; // r11d

  if ( !a1 )
    return 2150170884LL;
  a1[3] = a1[1];
  a1[2] = 1;
  a1[4] = 0;
  a1[5] = 0;
  result = CmdBufAddUint16();
  if ( (int)result >= 0 )
  {
    result = CmdBufAddUint32(v2, 0);
    if ( (int)result >= 0 )
      return CmdBufAddUint32(v3, v4);
  }
  return result;
}

```

## disassembly

```asm
0x14003950c  sub     rsp, 28h
0x140039510  mov     r11d, r8d
0x140039513  mov     r10, rcx
0x140039516  test    rcx, rcx
0x140039519  jnz     short loc_140039522
0x14003951b  mov     eax, 80290104h
0x140039520  jmp     short loc_140039564
0x140039522  mov     rax, [rcx+8]
0x140039526  mov     [rcx+18h], rax
0x14003952a  mov     qword ptr [rcx+10h], 1
0x140039532  mov     qword ptr [rcx+20h], 0
0x14003953a  mov     qword ptr [rcx+28h], 0
0x140039542  call    CmdBufAddUint16
0x140039547  test    eax, eax
0x140039549  js      short loc_140039564
0x14003954b  xor     edx, edx
0x14003954d  mov     rcx, r10
0x140039550  call    CmdBufAddUint32
0x140039555  test    eax, eax
0x140039557  js      short loc_140039564
0x140039559  mov     edx, r11d
0x14003955c  mov     rcx, r10
0x14003955f  call    CmdBufAddUint32
0x140039564  add     rsp, 28h
0x140039568  retn
```
