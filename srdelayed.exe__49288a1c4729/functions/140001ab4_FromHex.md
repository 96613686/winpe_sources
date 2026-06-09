# FromHex

- ea: `0x140001ab4`
- end: `0x140001af4`
- name: `FromHex`
- size: `64`
- prototype: `__int64 __fastcall(__int16, _WORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001fa4`
- `0x1400028a4`

## callees

- `0x140001ab4`

## pseudocode

```c
__int64 __fastcall FromHex(__int16 a1, _WORD *a2)
{
  __int16 v2; // cx
  __int16 v3; // ax

  *a2 = 0;
  if ( (unsigned __int16)(a1 - 48) <= 9u )
  {
    v2 = a1 - 48;
LABEL_8:
    *a2 = v2;
    return 0;
  }
  if ( (unsigned __int16)(a1 - 65) <= 5u )
  {
    v3 = -55;
LABEL_7:
    v2 = v3 + a1;
    goto LABEL_8;
  }
  if ( (unsigned __int16)(a1 - 97) <= 5u )
  {
    v3 = -87;
    goto LABEL_7;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140001ab4  xor     eax, eax
0x140001ab6  mov     [rdx], ax
0x140001ab9  lea     eax, [rcx-30h]
0x140001abc  cmp     ax, 9
0x140001ac0  ja      short loc_140001AC7
0x140001ac2  movzx   ecx, ax
0x140001ac5  jmp     short loc_140001AE8
0x140001ac7  lea     eax, [rcx-41h]
0x140001aca  cmp     ax, 5
0x140001ace  ja      short loc_140001AD7
0x140001ad0  mov     eax, 0FFC9h
0x140001ad5  jmp     short loc_140001AE5
0x140001ad7  lea     eax, [rcx-61h]
0x140001ada  cmp     ax, 5
0x140001ade  ja      short loc_140001AEE
0x140001ae0  mov     eax, 0FFA9h
0x140001ae5  add     cx, ax
0x140001ae8  mov     [rdx], cx
0x140001aeb  xor     eax, eax
0x140001aed  retn
0x140001aee  mov     eax, 0C000000Dh
0x140001af3  retn
```
