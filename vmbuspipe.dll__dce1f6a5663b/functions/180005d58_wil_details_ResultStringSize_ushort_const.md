# wil::details::ResultStringSize(ushort const *)

- ea: `0x180005d58`
- end: `0x180005d79`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003be4`
- `0x180005ea0`
- `0x180005fdc`

## callees

- `0x180005d58`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax

  if ( !this )
    return 2;
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)this + v3) );
  return 2 * v3 + 2;
}

```

## disassembly

```asm
0x180005d58  xor     edx, edx
0x180005d5a  test    rcx, rcx
0x180005d5d  jnz     short loc_180005D63
0x180005d5f  lea     eax, [rdx+2]
0x180005d62  retn
0x180005d63  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005d67  inc     rax
0x180005d6a  cmp     [rcx+rax*2], dx
0x180005d6e  jnz     short loc_180005D67
0x180005d70  lea     rax, ds:2[rax*2]
0x180005d78  retn
```
