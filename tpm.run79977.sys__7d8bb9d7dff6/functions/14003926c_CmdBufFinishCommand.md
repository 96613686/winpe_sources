# CmdBufFinishCommand

- ea: `0x14003926c`
- end: `0x1400392c1`
- name: `CmdBufFinishCommand`
- size: `85`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140033400`
- `0x140033bd8`
- `0x140034398`
- `0x1400344a4`

## callees

- `0x1400390c4`
- `0x14003926c`

## pseudocode

```c
__int64 __fastcall CmdBufFinishCommand(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rdx
  __int64 v3; // rax
  __int64 v4; // r10
  int v5; // r11d

  if ( !a1 )
    return 2150170884LL;
  if ( *(_DWORD *)(a1 + 16) != 1 )
    return 2150170880LL;
  v2 = *(unsigned int *)(a1 + 20);
  v3 = *(_QWORD *)(a1 + 8) + 2LL;
  *(_DWORD *)(a1 + 20) = 2;
  *(_QWORD *)(a1 + 24) = v3;
  result = CmdBufAddUint32(a1, v2);
  if ( (int)result >= 0 )
  {
    *(_DWORD *)(v4 + 20) = v5;
    *(_DWORD *)(v4 + 16) = 2;
  }
  return result;
}

```

## disassembly

```asm
0x14003926c  sub     rsp, 28h
0x140039270  mov     r10, rcx
0x140039273  test    rcx, rcx
0x140039276  jnz     short loc_14003927F
0x140039278  mov     eax, 80290104h
0x14003927d  jmp     short loc_1400392BB
0x14003927f  cmp     dword ptr [rcx+10h], 1
0x140039283  jz      short loc_14003928C
0x140039285  mov     eax, 80290100h
0x14003928a  jmp     short loc_1400392BB
0x14003928c  mov     r11d, [rcx+14h]
0x140039290  mov     edx, r11d
0x140039293  mov     rax, [rcx+8]
0x140039297  add     rax, 2
0x14003929b  mov     dword ptr [rcx+14h], 2
0x1400392a2  mov     [rcx+18h], rax
0x1400392a6  call    CmdBufAddUint32
0x1400392ab  test    eax, eax
0x1400392ad  js      short loc_1400392BB
0x1400392af  mov     [r10+14h], r11d
0x1400392b3  mov     dword ptr [r10+10h], 2
0x1400392bb  add     rsp, 28h
0x1400392bf  retn
```
