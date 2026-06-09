# CWmpCodecBase::HrTestStateMinimum(int)

- ea: `0x180028870`
- end: `0x180028883`
- name: `?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z`
- size: `19`
- prototype: `__int64 __fastcall(CWmpCodecBase *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180028430`
- `0x180028530`
- `0x1800287c0`
- `0x18002af00`
- `0x180032c10`
- `0x180033930`
- `0x180038340`
- `0x180038a00`
- `0x180038a90`
- `0x180038fb0`
- `0x180039370`
- `0x180039630`

## callees

- `0x180028870`

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
0x180028870  xor     eax, eax
0x180028872  cmp     [rcx+10h], eax
0x180028875  jz      short loc_18002887D
0x180028877  cmp     edx, [rcx+10h]
0x18002887a  jg      short loc_18002887D
0x18002887c  retn
0x18002887d  mov     eax, 88982F04h
0x180028882  retn
```
