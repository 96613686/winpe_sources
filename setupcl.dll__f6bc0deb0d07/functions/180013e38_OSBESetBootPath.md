# OSBESetBootPath

- ea: `0x180013e38`
- end: `0x180013e83`
- name: `OSBESetBootPath`
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
- `0x180013e38`

## pseudocode

```c
__int64 __fastcall OSBESetBootPath(__int64 a1, const wchar_t *a2)
{
  __int64 v2; // rbx
  __int64 v3; // r11
  __int64 v4; // rcx

  v2 = 0;
  if ( a1 && a2 )
  {
    v2 = a1 + 2088;
    StringCchCopyW((STRSAFE_LPWSTR)(a1 + 2088), 0x104u, a2);
    v4 = *(_QWORD *)(v3 + 3136);
    *(_DWORD *)(v3 + 3128) |= 0x10000000u;
    *(_DWORD *)(v4 + 4) |= 0x10000000u;
  }
  return v2;
}

```

## disassembly

```asm
0x180013e38  push    rbx
0x180013e3a  sub     rsp, 20h
0x180013e3e  xor     ebx, ebx
0x180013e40  mov     r11, rcx
0x180013e43  test    rcx, rcx
0x180013e46  jz      short loc_180013E7A
0x180013e48  test    rdx, rdx
0x180013e4b  jz      short loc_180013E7A
0x180013e4d  lea     rbx, [rcx+828h]
0x180013e54  mov     r8, rdx; pszSrc
0x180013e57  mov     rcx, rbx; pszDest
0x180013e5a  mov     edx, 104h; cchDest
0x180013e5f  call    StringCchCopyW
0x180013e64  mov     rcx, [r11+0C40h]
0x180013e6b  mov     eax, 10000000h
0x180013e70  or      [r11+0C38h], eax
0x180013e77  or      [rcx+4], eax
0x180013e7a  mov     rax, rbx
0x180013e7d  add     rsp, 20h
0x180013e81  pop     rbx
0x180013e82  retn
```
