# wil::details::ResultStringSize(char const *)

- ea: `0x180005d38`
- end: `0x180005d52`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b6c`
- `0x180005ea0`
- `0x180005fdc`

## callees

- `0x180005d38`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const char *a2)
{
  __int64 v3; // rax

  if ( !this )
    return 1;
  v3 = -1;
  do
    ++v3;
  while ( *((_BYTE *)this + v3) );
  return v3 + 1;
}

```

## disassembly

```asm
0x180005d38  test    rcx, rcx
0x180005d3b  jnz     short loc_180005D41
0x180005d3d  lea     eax, [rcx+1]
0x180005d40  retn
0x180005d41  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005d45  inc     rax
0x180005d48  cmp     byte ptr [rcx+rax], 0
0x180005d4c  jnz     short loc_180005D45
0x180005d4e  inc     rax
0x180005d51  retn
```
