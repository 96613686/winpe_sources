# StringCchLengthA(x,x,x)

- ea: `0x10002e2f`
- end: `0x10002e53`
- name: `_StringCchLengthA@12`
- size: `36`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10002870`
- `0x100049a9`

## callees

- `0x10002e2f`
- `0x10004960`

## pseudocode

```c
HRESULT __stdcall StringCchLengthA(STRSAFE_PCNZCH psz, size_t cchMax, size_t *pcchLength)
{
  int v3; // ecx
  HRESULT result; // eax
  size_t v5; // [esp+0h] [ebp-4h]
  size_t *savedregs; // [esp+4h] [ebp+0h]

  if ( v3 )
  {
    result = StringLengthWorkerA_0(psz, v5, savedregs);
    if ( result >= 0 )
      return result;
  }
  else
  {
    result = -2147024809;
  }
  if ( psz )
    *(_DWORD *)psz = 0;
  return result;
}

```

## disassembly

```asm
0x10002e2f  mov     edi, edi
0x10002e31  push    ebp; pcchLength
0x10002e32  mov     ebp, esp
0x10002e34  push    esi; cchMax
0x10002e35  mov     esi, [ebp+psz]
0x10002e38  test    ecx, ecx
0x10002e3a  jz      loc_10005748
0x10002e40  push    esi; psz
0x10002e41  call    StringLengthWorkerA_0
0x10002e46  test    eax, eax
0x10002e48  js      loc_1000574D
0x10002e4e  pop     esi
0x10002e4f  pop     ebp
0x10002e50  retn    4
0x10005748  mov     eax, 80070057h
0x1000574d  test    esi, esi
0x1000574f  jz      loc_10002E4E
0x10005755  mov     dword ptr [esi], 0
0x1000575b  jmp     loc_10002E4E
```
