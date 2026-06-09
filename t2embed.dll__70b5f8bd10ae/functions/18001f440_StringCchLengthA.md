# StringCchLengthA

- ea: `0x18001f440`
- end: `0x18001f46a`
- name: `StringCchLengthA`
- size: `42`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001edf0`
- `0x180021ffc`
- `0x18002218c`
- `0x18002231c`
- `0x18002252c`
- `0x1800229a8`

## callees

- `0x18001df94`
- `0x18001f440`

## pseudocode

```c
HRESULT __stdcall StringCchLengthA(STRSAFE_PCNZCH psz, size_t cchMax, size_t *pcchLength)
{
  HRESULT result; // eax

  if ( psz )
  {
    result = StringLengthWorkerA(psz, cchMax, pcchLength);
    if ( result >= 0 )
      return result;
  }
  else
  {
    result = -2147024809;
  }
  if ( pcchLength )
    *pcchLength = 0;
  return result;
}

```

## disassembly

```asm
0x18001f440  sub     rsp, 28h
0x18001f444  test    rcx, rcx
0x18001f447  jz      short loc_18001F454
0x18001f449  call    StringLengthWorkerA
0x18001f44e  test    eax, eax
0x18001f450  jns     short loc_18001F465
0x18001f452  jmp     short loc_18001F459
0x18001f454  mov     eax, 80070057h
0x18001f459  test    r8, r8
0x18001f45c  jz      short loc_18001F465
0x18001f45e  mov     qword ptr [r8], 0
0x18001f465  add     rsp, 28h
0x18001f469  retn
```
