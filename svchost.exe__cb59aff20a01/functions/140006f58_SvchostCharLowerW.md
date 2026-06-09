# SvchostCharLowerW

- ea: `0x140006f58`
- end: `0x140006f96`
- name: `SvchostCharLowerW`
- size: `62`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003180`
- `0x140004680`

## callees

- `0x140006f58`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x140006f8b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x140006f8b`

## pseudocode

```c
int __fastcall SvchostCharLowerW(WCHAR *lpSrcStr)
{
  int result; // eax
  __int64 v2; // r9

  result = 0;
  if ( lpSrcStr )
  {
    v2 = -1;
    do
      ++v2;
    while ( lpSrcStr[v2] );
    return LCMapStringW(0x400u, 0x100u, lpSrcStr, v2 + 1, lpSrcStr, v2 + 1);
  }
  return result;
}

```

## disassembly

```asm
0x140006f58  sub     rsp, 38h
0x140006f5c  xor     eax, eax
0x140006f5e  test    rcx, rcx
0x140006f61  jz      short loc_140006F91
0x140006f63  or      r9, 0FFFFFFFFFFFFFFFFh
0x140006f67  inc     r9
0x140006f6a  cmp     [rcx+r9*2], ax
0x140006f6f  jnz     short loc_140006F67
0x140006f71  inc     r9d; cchSrc
0x140006f74  mov     r8, rcx; lpSrcStr
0x140006f77  mov     [rsp+38h+cchDest], r9d; cchDest
0x140006f7c  mov     edx, 100h; dwMapFlags
0x140006f81  mov     [rsp+38h+lpDestStr], rcx; lpDestStr
0x140006f86  mov     ecx, 400h; Locale
0x140006f8b  call    cs:__imp_LCMapStringW
0x140006f91  add     rsp, 38h
0x140006f95  retn
```
