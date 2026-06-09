# UpdateInternalStatsOnFlush

- ea: `0x140022d24`
- end: `0x140022d66`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140022c34`
- `0x14002ea5c`

## callees

- `0x140022d24`

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
0x140022d24  test    edx, edx
0x140022d26  jz      short locret_140022D65
0x140022d28  lea     r8, [rcx+128h]
0x140022d2f  cmp     [rcx+138h], edx
0x140022d35  ja      short loc_140022D3F
0x140022d37  mov     rax, [r8]
0x140022d3a  test    rax, rax
0x140022d3d  jnz     short loc_140022D48
0x140022d3f  mov     rax, [r8]
0x140022d42  mov     [rcx+138h], edx
0x140022d48  cmp     [rcx+134h], edx
0x140022d4e  jnb     short loc_140022D56
0x140022d50  mov     [rcx+134h], edx
0x140022d56  inc     rax
0x140022d59  mov     [r8], rax
0x140022d5c  mov     eax, edx
0x140022d5e  add     [rcx+120h], rax
0x140022d65  retn
```
