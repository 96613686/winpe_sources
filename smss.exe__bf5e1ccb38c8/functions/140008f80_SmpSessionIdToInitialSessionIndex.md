# SmpSessionIdToInitialSessionIndex

- ea: `0x140008f80`
- end: `0x140008fae`
- name: `SmpSessionIdToInitialSessionIndex`
- size: `46`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400031b0`
- `0x140005ac4`
- `0x140017954`

## callees

- `0x140008f80`

## pseudocode

```c
__int64 __fastcall SmpSessionIdToInitialSessionIndex(int a1)
{
  __int64 result; // rax

  if ( a1 != -1 )
  {
    for ( result = 0; (unsigned int)result < SmpNumberInitialSessions; result = (unsigned int)(result + 1) )
    {
      if ( a1 == *(_DWORD *)(SmpCoreProcessIds + 40 * result) )
        return result;
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140008f80  cmp     ecx, 0FFFFFFFFh
0x140008f83  jz      short loc_140008FA8
0x140008f85  mov     r9d, cs:SmpNumberInitialSessions
0x140008f8c  xor     eax, eax
0x140008f8e  mov     r10, cs:SmpCoreProcessIds
0x140008f95  cmp     eax, r9d
0x140008f98  jnb     short loc_140008FA8
0x140008f9a  lea     rdx, [rax+rax*4]
0x140008f9e  cmp     ecx, [r10+rdx*8]
0x140008fa2  jz      short locret_140008FAD
0x140008fa4  inc     eax
0x140008fa6  jmp     short loc_140008F95
0x140008fa8  mov     eax, 0FFFFFFFFh
0x140008fad  retn
```
