# StringCchLengthW(x,x,x)

- ea: `0x10003754`
- end: `0x10003778`
- name: `_StringCchLengthW@12`
- size: `36`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100032d0`
- `0x10004de8`

## callees

- `0x10003754`
- `0x10004d9d`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  int v3; // ecx
  HRESULT result; // eax
  size_t v5; // [esp+0h] [ebp-4h]
  size_t *savedregs; // [esp+4h] [ebp+0h]

  if ( v3 )
  {
    result = StringLengthWorkerW_0(psz, v5, savedregs);
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
0x10003754  mov     edi, edi
0x10003756  push    ebp; pcchLength
0x10003757  mov     ebp, esp
0x10003759  push    esi; cchMax
0x1000375a  mov     esi, [ebp+psz]
0x1000375d  test    ecx, ecx
0x1000375f  jz      loc_10005C81
0x10003765  push    esi; psz
0x10003766  call    StringLengthWorkerW_0
0x1000376b  test    eax, eax
0x1000376d  js      loc_10005C86
0x10003773  pop     esi
0x10003774  pop     ebp
0x10003775  retn    4
0x10005c81  mov     eax, 80070057h
0x10005c86  test    esi, esi
0x10005c88  jz      loc_10003773
0x10005c8e  mov     dword ptr [esi], 0
0x10005c94  jmp     loc_10003773
```
