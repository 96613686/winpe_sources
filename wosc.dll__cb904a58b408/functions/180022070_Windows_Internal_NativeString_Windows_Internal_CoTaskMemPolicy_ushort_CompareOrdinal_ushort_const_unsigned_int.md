# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinal(ushort const *,unsigned __int64)

- ea: `0x180022070`
- end: `0x1800220de`
- name: `?CompareOrdinal@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022a8c`
- `0x180026d90`

## callees

- `0x180022070`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800220d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800220d3`

## pseudocode

```c
int __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinal(
        __int64 a1,
        const WCHAR *a2,
        int a3)
{
  const WCHAR *v3; // r10
  __int64 v4; // rax
  int v5; // r9d
  __int64 v6; // rdx
  const WCHAR *v7; // rcx

  v3 = a2;
  v4 = *(_QWORD *)(a1 + 8);
  v5 = a2 != 0 ? a3 : 0;
  if ( !a2 )
    v3 = &String1;
  v6 = -1;
  if ( v4 != -1 )
  {
    v7 = *(const WCHAR **)a1;
    LODWORD(v6) = v4;
    if ( v7 )
      return CompareStringOrdinal(v7, v6, v3, v5, 0);
LABEL_9:
    v7 = &String1;
    return CompareStringOrdinal(v7, v6, v3, v5, 0);
  }
  if ( !*(_QWORD *)a1 )
  {
    LODWORD(v6) = 0;
    goto LABEL_9;
  }
  do
    ++v6;
  while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v6) );
  v7 = *(const WCHAR **)a1;
  return CompareStringOrdinal(v7, v6, v3, v5, 0);
}

```

## disassembly

```asm
0x180022070  sub     rsp, 38h
0x180022074  mov     rax, rdx
0x180022077  lea     r11, String1
0x18002207e  neg     rax
0x180022081  mov     r10, rdx
0x180022084  mov     rax, [rcx+8]
0x180022088  sbb     r9d, r9d
0x18002208b  and     r9d, r8d; cchCount2
0x18002208e  xor     r8d, r8d
0x180022091  test    rdx, rdx
0x180022094  cmovz   r10, r11
0x180022098  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002209c  cmp     rax, rdx
0x18002209f  jnz     short loc_1800220BD
0x1800220a1  mov     rax, [rcx]
0x1800220a4  test    rax, rax
0x1800220a7  jz      short loc_1800220B8
0x1800220a9  inc     rdx
0x1800220ac  cmp     [rax+rdx*2], r8w
0x1800220b1  jnz     short loc_1800220A9
0x1800220b3  mov     rcx, rax
0x1800220b6  jmp     short loc_1800220CB
0x1800220b8  mov     rdx, r8
0x1800220bb  jmp     short loc_1800220C8
0x1800220bd  mov     rcx, [rcx]
0x1800220c0  mov     rdx, rax; cchCount1
0x1800220c3  test    rcx, rcx
0x1800220c6  jnz     short loc_1800220CB
0x1800220c8  mov     rcx, r11; lpString1
0x1800220cb  mov     [rsp+38h+bIgnoreCase], r8d; bIgnoreCase
0x1800220d0  mov     r8, r10; lpString2
0x1800220d3  call    cs:__imp_CompareStringOrdinal
0x1800220d9  add     rsp, 38h
0x1800220dd  retn
```
