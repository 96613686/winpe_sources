# OSBESetOsLoaderPath

- ea: `0x180013f98`
- end: `0x180013fe3`
- name: `OSBESetOsLoaderPath`
- size: `75`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012dfc`
- `0x1800135b0`

## callees

- `0x18000f670`
- `0x180013f98`

## pseudocode

```c
__int64 __fastcall OSBESetOsLoaderPath(__int64 a1, const wchar_t *a2)
{
  __int64 v2; // rbx
  __int64 v3; // r11
  __int64 v4; // rcx

  v2 = 0;
  if ( a1 && a2 )
  {
    v2 = a1 + 1048;
    StringCchCopyW((STRSAFE_LPWSTR)(a1 + 1048), 0x104u, a2);
    v4 = *(_QWORD *)(v3 + 3136);
    *(_DWORD *)(v3 + 3128) |= 0x10000000u;
    *(_DWORD *)(v4 + 4) |= 0x10000000u;
  }
  return v2;
}

```

## disassembly

```asm
0x180013f98  push    rbx
0x180013f9a  sub     rsp, 20h
0x180013f9e  xor     ebx, ebx
0x180013fa0  mov     r11, rcx
0x180013fa3  test    rcx, rcx
0x180013fa6  jz      short loc_180013FDA
0x180013fa8  test    rdx, rdx
0x180013fab  jz      short loc_180013FDA
0x180013fad  lea     rbx, [rcx+418h]
0x180013fb4  mov     r8, rdx; pszSrc
0x180013fb7  mov     rcx, rbx; pszDest
0x180013fba  mov     edx, 104h; cchDest
0x180013fbf  call    StringCchCopyW
0x180013fc4  mov     rcx, [r11+0C40h]
0x180013fcb  mov     eax, 10000000h
0x180013fd0  or      [r11+0C38h], eax
0x180013fd7  or      [rcx+4], eax
0x180013fda  mov     rax, rbx
0x180013fdd  add     rsp, 20h
0x180013fe1  pop     rbx
0x180013fe2  retn
```
