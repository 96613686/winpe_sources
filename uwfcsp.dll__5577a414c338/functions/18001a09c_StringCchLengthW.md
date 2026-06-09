# StringCchLengthW

- ea: `0x18001a09c`
- end: `0x18001a0e1`
- name: `StringCchLengthW`
- size: `69`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ff08`

## callees

- `0x18001a09c`

## string_xrefs

- `0x18001a0a1`: `EmbeddedFeature-UnifiedWriteFilter-Enabled`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  const wchar_t *v3; // rax
  __int64 v4; // rcx
  HRESULT result; // eax

  v3 = L"EmbeddedFeature-UnifiedWriteFilter-Enabled";
  v4 = 0x7FFFFFFF;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  result = v4 == 0 ? 0x80070057 : 0;
  if ( pcchLength )
  {
    if ( v4 )
      *pcchLength = 0x7FFFFFFF - v4;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a09c  mov     edx, 7FFFFFFFh
0x18001a0a1  lea     rax, aEmbeddedfeatur; "EmbeddedFeature-UnifiedWriteFilter-Enab"...
0x18001a0a8  mov     ecx, edx
0x18001a0aa  xor     r9d, r9d
0x18001a0ad  cmp     [rax], r9w
0x18001a0b1  jz      short loc_18001A0BD
0x18001a0b3  add     rax, 2
0x18001a0b7  sub     rcx, 1
0x18001a0bb  jnz     short loc_18001A0AD
0x18001a0bd  mov     rax, rcx
0x18001a0c0  neg     rax
0x18001a0c3  sbb     eax, eax
0x18001a0c5  not     eax
0x18001a0c7  and     eax, 80070057h
0x18001a0cc  test    r8, r8
0x18001a0cf  jz      short locret_18001A0E0
0x18001a0d1  test    rcx, rcx
0x18001a0d4  jz      short loc_18001A0DD
0x18001a0d6  sub     rdx, rcx
0x18001a0d9  mov     [r8], rdx
0x18001a0dc  retn
0x18001a0dd  mov     [r8], r9
0x18001a0e0  retn
```
