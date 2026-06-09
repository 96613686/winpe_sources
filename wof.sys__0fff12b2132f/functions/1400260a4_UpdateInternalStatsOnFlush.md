# UpdateInternalStatsOnFlush

- ea: `0x1400260a4`
- end: `0x1400260e6`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140025fb4`
- `0x14003d5cc`

## callees

- `0x1400260a4`

## pseudocode

```c
void __fastcall UpdateInternalStatsOnFlush(__int64 a1, unsigned int a2)
{
  __int64 *v2; // r8
  __int64 v3; // rax

  if ( a2 )
  {
    v2 = (__int64 *)(a1 + 296);
    if ( *(_DWORD *)(a1 + 312) > a2 || (v3 = *v2) == 0 )
    {
      v3 = *v2;
      *(_DWORD *)(a1 + 312) = a2;
    }
    if ( *(_DWORD *)(a1 + 308) < a2 )
      *(_DWORD *)(a1 + 308) = a2;
    *v2 = v3 + 1;
    *(_QWORD *)(a1 + 288) += a2;
  }
}

```

## disassembly

```asm
0x1400260a4  test    edx, edx
0x1400260a6  jz      short locret_1400260E5
0x1400260a8  lea     r8, [rcx+128h]
0x1400260af  cmp     [rcx+138h], edx
0x1400260b5  ja      short loc_1400260BF
0x1400260b7  mov     rax, [r8]
0x1400260ba  test    rax, rax
0x1400260bd  jnz     short loc_1400260C8
0x1400260bf  mov     rax, [r8]
0x1400260c2  mov     [rcx+138h], edx
0x1400260c8  cmp     [rcx+134h], edx
0x1400260ce  jnb     short loc_1400260D6
0x1400260d0  mov     [rcx+134h], edx
0x1400260d6  inc     rax
0x1400260d9  mov     [r8], rax
0x1400260dc  mov     eax, edx
0x1400260de  add     [rcx+120h], rax
0x1400260e5  retn
```
