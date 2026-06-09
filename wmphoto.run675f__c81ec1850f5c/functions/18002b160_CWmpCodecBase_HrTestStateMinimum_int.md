# CWmpCodecBase::HrTestStateMinimum(int)

- ea: `0x18002b160`
- end: `0x18002b174`
- name: `?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z`
- size: `20`
- prototype: `__int64 __fastcall(CWmpCodecBase *__hidden this, int)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180028690`
- `0x180028cb0`
- `0x1800296e0`
- `0x180029770`
- `0x18002a750`
- `0x18002b0b0`
- `0x18002b180`
- `0x180032690`
- `0x180032bb0`
- `0x1800331a0`
- `0x180033ee0`
- `0x180038980`
- `0x180039080`
- `0x180039120`
- `0x180039680`
- `0x180039a60`
- `0x180039d50`

## callees

- `0x18002b160`

## pseudocode

```c
__int64 __fastcall CWmpCodecBase::HrTestStateMinimum(CWmpCodecBase *this, int a2)
{
  __int64 result; // rax

  result = 0;
  if ( !*((_DWORD *)this + 4) || a2 > *((_DWORD *)this + 4) )
    return 2291674884LL;
  return result;
}

```

## disassembly

```asm
0x18002b160  xor     eax, eax
0x18002b162  cmp     [rcx+10h], eax
0x18002b165  jz      short loc_18002B16E
0x18002b167  cmp     edx, [rcx+10h]
0x18002b16a  jg      short loc_18002B16E
0x18002b16c  retn
0x18002b16e  mov     eax, 88982F04h
0x18002b173  retn
```
