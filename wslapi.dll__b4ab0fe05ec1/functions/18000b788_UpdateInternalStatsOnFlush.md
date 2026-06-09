# UpdateInternalStatsOnFlush

- ea: `0x18000b788`
- end: `0x18000b7ca`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000b280`
- `0x18000b608`

## callees

- `0x18000b788`

## pseudocode

```c
void __fastcall UpdateInternalStatsOnFlush(__int64 a1, unsigned int a2)
{
  __int64 *v2; // r8
  __int64 v3; // rax

  if ( a2 )
  {
    v2 = (__int64 *)(a1 + 280);
    if ( *(_DWORD *)(a1 + 296) > a2 || (v3 = *v2) == 0 )
    {
      v3 = *v2;
      *(_DWORD *)(a1 + 296) = a2;
    }
    if ( *(_DWORD *)(a1 + 292) < a2 )
      *(_DWORD *)(a1 + 292) = a2;
    *v2 = v3 + 1;
    *(_QWORD *)(a1 + 272) += a2;
  }
}

```

## disassembly

```asm
0x18000b788  test    edx, edx
0x18000b78a  jz      short locret_18000B7C9
0x18000b78c  lea     r8, [rcx+118h]
0x18000b793  cmp     [rcx+128h], edx
0x18000b799  ja      short loc_18000B7A3
0x18000b79b  mov     rax, [r8]
0x18000b79e  test    rax, rax
0x18000b7a1  jnz     short loc_18000B7AC
0x18000b7a3  mov     rax, [r8]
0x18000b7a6  mov     [rcx+128h], edx
0x18000b7ac  cmp     [rcx+124h], edx
0x18000b7b2  jnb     short loc_18000B7BA
0x18000b7b4  mov     [rcx+124h], edx
0x18000b7ba  inc     rax
0x18000b7bd  mov     [r8], rax
0x18000b7c0  mov     eax, edx
0x18000b7c2  add     [rcx+110h], rax
0x18000b7c9  retn
```
