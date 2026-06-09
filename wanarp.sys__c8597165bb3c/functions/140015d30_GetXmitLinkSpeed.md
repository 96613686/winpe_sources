# GetXmitLinkSpeed

- ea: `0x140015d30`
- end: `0x140015d5e`
- name: `GetXmitLinkSpeed`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400019c0`

## callees

- `0x140002030`
- `0x140015d30`

## pseudocode

```c
__int64 GetXmitLinkSpeed()
{
  __int64 v0; // rcx

  if ( (unsigned int)IsDialInAdapter() || *(_BYTE *)(v0 + 148) != 6 )
    return 28800;
  else
    return *(_QWORD *)(v0 + 328);
}

```

## disassembly

```asm
0x140015d30  sub     rsp, 28h
0x140015d34  call    IsDialInAdapter
0x140015d39  test    eax, eax
0x140015d3b  jnz     short loc_140015D53
0x140015d3d  cmp     byte ptr [rcx+94h], 6
0x140015d44  jnz     short loc_140015D53
0x140015d46  mov     rax, [rcx+148h]
0x140015d4d  add     rsp, 28h
0x140015d51  retn
0x140015d53  mov     eax, 7080h
0x140015d58  add     rsp, 28h
0x140015d5c  retn
```
