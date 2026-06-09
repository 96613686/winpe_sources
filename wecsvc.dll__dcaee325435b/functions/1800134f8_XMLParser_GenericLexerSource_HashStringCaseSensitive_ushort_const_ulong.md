# XMLParser<GenericLexerSource>::HashStringCaseSensitive(ushort const *,ulong)

- ea: `0x1800134f8`
- end: `0x180013513`
- name: `?HashStringCaseSensitive@?$XMLParser@VGenericLexerSource@@@@AEAAKPEBGK@Z`
- size: `27`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800133f8`
- `0x180013d60`

## callees

- `0x1800134f8`

## pseudocode

```c
__int64 __fastcall XMLParser<GenericLexerSource>::HashStringCaseSensitive(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  __int64 i; // r10
  int v5; // r9d

  result = 0;
  for ( i = 0; (unsigned int)i < a3; result = (unsigned int)(v5 + result) )
  {
    v5 = *(unsigned __int16 *)(a2 + 2 * i);
    i = (unsigned int)(i + 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800134f8  xor     eax, eax
0x1800134fa  xor     r10d, r10d
0x1800134fd  test    r8d, r8d
0x180013500  jz      short locret_180013512
0x180013502  movzx   r9d, word ptr [rdx+r10*2]
0x180013507  inc     r10d
0x18001350a  add     eax, r9d
0x18001350d  cmp     r10d, r8d
0x180013510  jb      short loc_180013502
0x180013512  retn
```
