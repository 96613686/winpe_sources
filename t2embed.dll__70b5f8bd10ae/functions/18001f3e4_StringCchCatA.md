# StringCchCatA

- ea: `0x18001f3e4`
- end: `0x18001f43a`
- name: `StringCchCatA`
- size: `86`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18001edf0`
- `0x180021ffc`
- `0x18002218c`
- `0x18002231c`
- `0x18002252c`
- `0x1800229a8`
- `0x180023224`

## callees

- `0x18001ba48`
- `0x18001df94`
- `0x18001f3e4`

## pseudocode

```c
HRESULT __stdcall StringCchCatA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  size_t *v5; // r8
  __int64 v6; // r10
  __int64 v7; // r11
  size_t v8; // [rsp+20h] [rbp-18h]
  size_t pcchLength; // [rsp+48h] [rbp+10h] BYREF

  pcchLength = 0;
  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  result = StringLengthWorkerA(pszDest, cchDest, &pcchLength);
  if ( result >= 0 )
    return StringCopyWorkerA((STRSAFE_LPSTR)(pcchLength + v7), v6 - pcchLength, v5, pszSrc, v8);
  return result;
}

```

## disassembly

```asm
0x18001f3e4  push    rbx
0x18001f3e6  sub     rsp, 30h
0x18001f3ea  lea     rax, [rdx-1]
0x18001f3ee  mov     [rsp+38h+pcchLength], 0
0x18001f3f7  mov     rbx, r8
0x18001f3fa  mov     r10, rdx
0x18001f3fd  mov     r11, rcx
0x18001f400  cmp     rax, 7FFFFFFEh
0x18001f406  ja      short loc_18001F42F
0x18001f408  lea     r8, [rsp+38h+pcchLength]; pcchLength
0x18001f40d  call    StringLengthWorkerA
0x18001f412  test    eax, eax
0x18001f414  js      short loc_18001F434
0x18001f416  mov     rax, [rsp+38h+pcchLength]
0x18001f41b  mov     r9, rbx; pszSrc
0x18001f41e  sub     r10, rax
0x18001f421  mov     rdx, r10; cchDest
0x18001f424  lea     rcx, [rax+r11]; pszDest
0x18001f428  call    StringCopyWorkerA
0x18001f42d  jmp     short loc_18001F434
0x18001f42f  mov     eax, 80070057h
0x18001f434  add     rsp, 30h
0x18001f438  pop     rbx
0x18001f439  retn
```
