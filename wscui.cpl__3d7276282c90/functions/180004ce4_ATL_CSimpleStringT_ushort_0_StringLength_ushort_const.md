# ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)

- ea: `0x180004ce4`
- end: `0x180004cfc`
- name: `?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z`
- size: `24`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000485c`
- `0x180005220`
- `0x180009300`
- `0x180009590`

## callees

- `0x180004ce4`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::StringLength(__int64 a1)
{
  __int64 result; // rax

  if ( !a1 )
    return 0;
  result = -1;
  do
    ++result;
  while ( *(_WORD *)(a1 + 2 * result) );
  return result;
}

```

## disassembly

```asm
0x180004ce4  xor     edx, edx
0x180004ce6  test    rcx, rcx
0x180004ce9  jnz     short loc_180004CEE
0x180004ceb  xor     eax, eax
0x180004ced  retn
0x180004cee  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004cf2  inc     rax
0x180004cf5  cmp     [rcx+rax*2], dx
0x180004cf9  jnz     short loc_180004CF2
0x180004cfb  retn
```
