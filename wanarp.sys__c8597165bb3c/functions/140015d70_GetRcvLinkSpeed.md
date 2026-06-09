# GetRcvLinkSpeed

- ea: `0x140015d70`
- end: `0x140015d9e`
- name: `GetRcvLinkSpeed`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400019c0`

## callees

- `0x140002030`
- `0x140015d70`

## pseudocode

```c
__int64 GetRcvLinkSpeed()
{
  __int64 v0; // rcx

  if ( (unsigned int)IsDialInAdapter() || *(_BYTE *)(v0 + 148) != 6 )
    return 28800;
  else
    return *(_QWORD *)(v0 + 336);
}

```

## disassembly

```asm
0x140015d70  sub     rsp, 28h
0x140015d74  call    IsDialInAdapter
0x140015d79  test    eax, eax
0x140015d7b  jz      short loc_140015D88
0x140015d7d  mov     eax, 7080h
0x140015d82  add     rsp, 28h
0x140015d86  retn
0x140015d88  cmp     byte ptr [rcx+94h], 6
0x140015d8f  jnz     short loc_140015D7D
0x140015d91  mov     rax, [rcx+150h]
0x140015d98  add     rsp, 28h
0x140015d9c  retn
```
