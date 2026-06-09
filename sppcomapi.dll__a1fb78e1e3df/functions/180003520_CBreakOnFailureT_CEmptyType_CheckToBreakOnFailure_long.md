# CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)

- ea: `0x180003520`
- end: `0x180003539`
- name: `?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `201`
- callee_count: `1`
- tags: ``

## callers

- `0x180003020`
- `0x1800031fc`
- `0x1800032a0`
- `0x180003318`
- `0x180003540`
- `0x180003650`
- `0x1800036ec`
- `0x180003950`
- `0x180003c18`
- `0x180003d80`
- `0x180003e14`
- `0x180003ed8`
- `0x18000405c`
- `0x1800044d8`
- `0x180004520`
- `0x180004790`
- `0x1800047d0`
- `0x180004840`
- `0x180004880`
- `0x180004ca8`
- `0x180004d60`
- `0x180004d98`
- `0x180004e18`
- `0x180004eb0`
- `0x180005050`
- `0x1800050f0`
- `0x180005260`
- `0x1800052a0`
- `0x180005490`
- `0x180005560`
- `0x180005640`
- `0x1800056d0`
- `0x1800057d0`
- `0x180005810`
- `0x180005920`
- `0x180005960`
- `0x1800059f0`
- `0x180005ab0`
- `0x180005b30`
- `0x18000f3d0`
- `0x18000f530`
- `0x18000f5a0`
- `0x180018e30`
- `0x180018f80`
- `0x180019110`
- `0x180019170`
- `0x180019210`
- `0x1800192e0`
- `0x180019400`
- `0x180019530`

## callees

- `0x180003520`

## pseudocode

```c
__int64 __fastcall CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(int a1)
{
  __int64 result; // rax

  result = (unsigned int)CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn;
  if ( CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn
    && a1 < 0
    && (CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn == a1 || CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn == -1) )
  {
    __debugbreak();
  }
  return result;
}

```

## disassembly

```asm
0x180003520  mov     eax, cs:?g_hResultToBreakOn@?$CBreakOnFailureT@VCEmptyType@@@@0JA; long CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn
0x180003526  test    eax, eax
0x180003528  jz      short locret_180003538
0x18000352a  test    ecx, ecx
0x18000352c  jns     short locret_180003538
0x18000352e  cmp     eax, ecx
0x180003530  jz      short loc_180003537
0x180003532  cmp     eax, 0FFFFFFFFh
0x180003535  jnz     short locret_180003538
0x180003537  int     3; Trap to Debugger
0x180003538  retn
```
