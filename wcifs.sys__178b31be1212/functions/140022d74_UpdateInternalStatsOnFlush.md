# UpdateInternalStatsOnFlush

- ea: `0x140022d74`
- end: `0x140022db6`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140022c84`
- `0x14002eaac`

## callees

- `0x140022d74`

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
0x140022d74  test    edx, edx
0x140022d76  jz      short locret_140022DB5
0x140022d78  lea     r8, [rcx+128h]
0x140022d7f  cmp     [rcx+138h], edx
0x140022d85  ja      short loc_140022D8F
0x140022d87  mov     rax, [r8]
0x140022d8a  test    rax, rax
0x140022d8d  jnz     short loc_140022D98
0x140022d8f  mov     rax, [r8]
0x140022d92  mov     [rcx+138h], edx
0x140022d98  cmp     [rcx+134h], edx
0x140022d9e  jnb     short loc_140022DA6
0x140022da0  mov     [rcx+134h], edx
0x140022da6  inc     rax
0x140022da9  mov     [r8], rax
0x140022dac  mov     eax, edx
0x140022dae  add     [rcx+120h], rax
0x140022db5  retn
```
