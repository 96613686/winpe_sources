# StringIsPrefixed(ushort const *,ushort const *)

- ea: `0x180008810`
- end: `0x18000885e`
- name: `?StringIsPrefixed@@YAHPEBG0@Z`
- size: `78`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008798`
- `0x18000b2d0`
- `0x1800198ac`

## callees

- `0x180008810`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008851`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008851`

## pseudocode

```c
__int64 __fastcall StringIsPrefixed(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rdx
  unsigned int v4; // ebx

  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( v3 > 0x7FFFFFFF )
    return 0;
  v4 = 1;
  if ( CompareStringOrdinal(a1, v3, a2, v3, 1) != 2 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x180008810  mov     [rsp+arg_0], rbx
0x180008815  push    rdi
0x180008816  sub     rsp, 30h
0x18000881a  mov     r8, rdx; lpString2
0x18000881d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180008821  xor     edi, edi
0x180008823  inc     rdx; cchCount1
0x180008826  cmp     [r8+rdx*2], di
0x18000882b  jnz     short loc_180008823
0x18000882d  cmp     rdx, 7FFFFFFFh
0x180008834  jbe     short loc_180008845
0x180008836  mov     ebx, edi
0x180008838  mov     eax, ebx
0x18000883a  mov     rbx, [rsp+38h+arg_0]
0x18000883f  add     rsp, 30h
0x180008843  pop     rdi
0x180008844  retn
0x180008845  mov     ebx, 1
0x18000884a  mov     r9d, edx; cchCount2
0x18000884d  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x180008851  call    cs:__imp_CompareStringOrdinal
0x180008857  cmp     eax, 2
0x18000885a  jz      short loc_180008838
0x18000885c  jmp     short loc_180008836
```
