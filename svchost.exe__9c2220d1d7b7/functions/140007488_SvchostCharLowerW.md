# SvchostCharLowerW

- ea: `0x140007488`
- end: `0x1400074cd`
- name: `SvchostCharLowerW`
- size: `69`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003470`
- `0x140004a30`

## callees

- `0x140007488`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1400074bb`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1400074bb`

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
0x140007488  sub     rsp, 38h
0x14000748c  xor     eax, eax
0x14000748e  test    rcx, rcx
0x140007491  jz      short loc_1400074C7
0x140007493  or      r9, 0FFFFFFFFFFFFFFFFh
0x140007497  inc     r9
0x14000749a  cmp     [rcx+r9*2], ax
0x14000749f  jnz     short loc_140007497
0x1400074a1  inc     r9d; cchSrc
0x1400074a4  mov     r8, rcx; lpSrcStr
0x1400074a7  mov     [rsp+38h+cchDest], r9d; cchDest
0x1400074ac  mov     edx, 100h; dwMapFlags
0x1400074b1  mov     [rsp+38h+lpDestStr], rcx; lpDestStr
0x1400074b6  mov     ecx, 400h; Locale
0x1400074bb  call    cs:__imp_LCMapStringW
0x1400074c2  nop     dword ptr [rax+rax+00h]
0x1400074c7  add     rsp, 38h
0x1400074cb  retn
```
