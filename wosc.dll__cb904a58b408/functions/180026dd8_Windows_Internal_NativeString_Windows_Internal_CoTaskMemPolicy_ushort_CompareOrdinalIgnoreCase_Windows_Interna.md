# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)

- ea: `0x180026dd8`
- end: `0x180026e63`
- name: `?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028830`
- `0x1800288a4`

## callees

- `0x180026dd8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026e58`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026e58`

## pseudocode

```c
int __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9
  __int64 v4; // rdx
  const WCHAR *v5; // r10
  __int64 v6; // r8
  const WCHAR *v7; // rcx

  v2 = *(_QWORD *)(a2 + 8);
  v4 = -1;
  v5 = *(const WCHAR **)a2;
  if ( v2 != -1 )
  {
    if ( v5 )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( !v5 )
  {
    LODWORD(v2) = 0;
LABEL_8:
    v5 = &String1;
    goto LABEL_9;
  }
  v2 = -1;
  do
    ++v2;
  while ( v5[v2] );
LABEL_9:
  v6 = *(_QWORD *)(a1 + 8);
  if ( v6 != -1 )
  {
    v7 = *(const WCHAR **)a1;
    LODWORD(v4) = v6;
    if ( v7 )
      return CompareStringOrdinal(v7, v4, v5, v2, 1);
LABEL_15:
    v7 = &String1;
    return CompareStringOrdinal(v7, v4, v5, v2, 1);
  }
  if ( !*(_QWORD *)a1 )
  {
    LODWORD(v4) = 0;
    goto LABEL_15;
  }
  do
    ++v4;
  while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v4) );
  v7 = *(const WCHAR **)a1;
  return CompareStringOrdinal(v7, v4, v5, v2, 1);
}

```

## disassembly

```asm
0x180026dd8  sub     rsp, 38h
0x180026ddc  mov     r9, [rdx+8]; cchCount2
0x180026de0  mov     r8, rdx
0x180026de3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180026de7  xor     eax, eax
0x180026de9  mov     r10, [r8]
0x180026dec  cmp     r9, rdx
0x180026def  jnz     short loc_180026E0A
0x180026df1  test    r10, r10
0x180026df4  jz      short loc_180026E05
0x180026df6  mov     r9, rdx
0x180026df9  inc     r9
0x180026dfc  cmp     [r10+r9*2], ax
0x180026e01  jnz     short loc_180026DF9
0x180026e03  jmp     short loc_180026E16
0x180026e05  mov     r9, rax
0x180026e08  jmp     short loc_180026E0F
0x180026e0a  test    r10, r10
0x180026e0d  jnz     short loc_180026E16
0x180026e0f  lea     r10, String1
0x180026e16  mov     r8, [rcx+8]
0x180026e1a  cmp     r8, rdx
0x180026e1d  jnz     short loc_180026E3B
0x180026e1f  mov     r8, [rcx]
0x180026e22  test    r8, r8
0x180026e25  jz      short loc_180026E36
0x180026e27  inc     rdx
0x180026e2a  cmp     [r8+rdx*2], ax
0x180026e2f  jnz     short loc_180026E27
0x180026e31  mov     rcx, r8
0x180026e34  jmp     short loc_180026E4D
0x180026e36  mov     rdx, rax
0x180026e39  jmp     short loc_180026E46
0x180026e3b  mov     rcx, [rcx]
0x180026e3e  mov     rdx, r8; cchCount1
0x180026e41  test    rcx, rcx
0x180026e44  jnz     short loc_180026E4D
0x180026e46  lea     rcx, String1; lpString1
0x180026e4d  mov     r8, r10; lpString2
0x180026e50  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180026e58  call    cs:__imp_CompareStringOrdinal
0x180026e5e  add     rsp, 38h
0x180026e62  retn
```
