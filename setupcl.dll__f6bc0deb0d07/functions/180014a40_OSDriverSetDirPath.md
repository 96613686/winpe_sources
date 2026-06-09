# OSDriverSetDirPath

- ea: `0x180014a40`
- end: `0x180014a8b`
- name: `OSDriverSetDirPath`
- size: `75`
- prototype: `char __fastcall(__int64, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014784`
- `0x18001490c`

## callees

- `0x18000f670`
- `0x180014a40`

## pseudocode

```c
char __fastcall OSDriverSetDirPath(__int64 a1, const wchar_t *a2)
{
  char result; // al
  __int64 v3; // r11
  __int64 v4; // rax

  result = 0;
  if ( a1 && a2 )
  {
    if ( *a2 )
    {
      StringCchCopyW((STRSAFE_LPWSTR)(a1 + 1044), 0x104u, a2);
      v4 = *(_QWORD *)(v3 + 2088);
      *(_DWORD *)(v3 + 2084) |= 0x10000000u;
      *(_DWORD *)(v4 + 4) |= 0x10000000u;
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014a40  sub     rsp, 28h
0x180014a44  mov     r11, rcx
0x180014a47  xor     ecx, ecx
0x180014a49  mov     al, cl
0x180014a4b  test    r11, r11
0x180014a4e  jz      short loc_180014A86
0x180014a50  test    rdx, rdx
0x180014a53  jz      short loc_180014A86
0x180014a55  cmp     [rdx], cx
0x180014a58  jz      short loc_180014A86
0x180014a5a  mov     r8, rdx; pszSrc
0x180014a5d  lea     rcx, [r11+414h]; pszDest
0x180014a64  mov     edx, 104h; cchDest
0x180014a69  call    StringCchCopyW
0x180014a6e  mov     rax, [r11+828h]
0x180014a75  mov     ecx, 10000000h
0x180014a7a  or      [r11+824h], ecx
0x180014a81  or      [rax+4], ecx
0x180014a84  mov     al, 1
0x180014a86  add     rsp, 28h
0x180014a8a  retn
```
