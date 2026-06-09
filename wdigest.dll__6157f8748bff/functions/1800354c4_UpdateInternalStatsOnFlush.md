# UpdateInternalStatsOnFlush

- ea: `0x1800354c4`
- end: `0x180035506`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180035460`

## callees

- `0x1800354c4`

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
0x1800354c4  test    edx, edx
0x1800354c6  jz      short locret_180035505
0x1800354c8  lea     r8, [rcx+118h]
0x1800354cf  cmp     [rcx+128h], edx
0x1800354d5  ja      short loc_1800354DF
0x1800354d7  mov     rax, [r8]
0x1800354da  test    rax, rax
0x1800354dd  jnz     short loc_1800354E8
0x1800354df  mov     rax, [r8]
0x1800354e2  mov     [rcx+128h], edx
0x1800354e8  cmp     [rcx+124h], edx
0x1800354ee  jnb     short loc_1800354F6
0x1800354f0  mov     [rcx+124h], edx
0x1800354f6  inc     rax
0x1800354f9  mov     [r8], rax
0x1800354fc  mov     eax, edx
0x1800354fe  add     [rcx+110h], rax
0x180035505  retn
```
