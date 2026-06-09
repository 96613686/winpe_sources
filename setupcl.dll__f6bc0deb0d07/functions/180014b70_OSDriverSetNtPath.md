# OSDriverSetNtPath

- ea: `0x180014b70`
- end: `0x180014bbb`
- name: `OSDriverSetNtPath`
- size: `75`
- prototype: `char __fastcall(__int64, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180014784`
- `0x18001490c`

## callees

- `0x18000f670`
- `0x180014b70`

## pseudocode

```c
char __fastcall OSDriverSetNtPath(__int64 a1, const wchar_t *a2)
{
  char result; // al
  __int64 v3; // r11
  __int64 v4; // rax

  result = 0;
  if ( a1 && a2 )
  {
    if ( *a2 )
    {
      StringCchCopyW((STRSAFE_LPWSTR)(a1 + 524), 0x104u, a2);
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
0x180014b70  sub     rsp, 28h
0x180014b74  mov     r11, rcx
0x180014b77  xor     ecx, ecx
0x180014b79  mov     al, cl
0x180014b7b  test    r11, r11
0x180014b7e  jz      short loc_180014BB6
0x180014b80  test    rdx, rdx
0x180014b83  jz      short loc_180014BB6
0x180014b85  cmp     [rdx], cx
0x180014b88  jz      short loc_180014BB6
0x180014b8a  mov     r8, rdx; pszSrc
0x180014b8d  lea     rcx, [r11+20Ch]; pszDest
0x180014b94  mov     edx, 104h; cchDest
0x180014b99  call    StringCchCopyW
0x180014b9e  mov     rax, [r11+828h]
0x180014ba5  mov     ecx, 10000000h
0x180014baa  or      [r11+824h], ecx
0x180014bb1  or      [rax+4], ecx
0x180014bb4  mov     al, 1
0x180014bb6  add     rsp, 28h
0x180014bba  retn
```
