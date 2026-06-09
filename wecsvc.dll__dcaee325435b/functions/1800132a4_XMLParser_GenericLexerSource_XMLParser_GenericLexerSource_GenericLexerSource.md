# XMLParser<GenericLexerSource>::XMLParser<GenericLexerSource>(GenericLexerSource &)

- ea: `0x1800132a4`
- end: `0x180013307`
- name: `??0?$XMLParser@VGenericLexerSource@@@@QEAA@AEAVGenericLexerSource@@@Z`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001351c`

## pseudocode

```c
__int64 __fastcall XMLParser<GenericLexerSource>::XMLParser<GenericLexerSource>(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  *(_QWORD *)a1 = &XMLParser<GenericLexerSource>::`vftable';
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = a1 + 8;
  *(_DWORD *)(a1 + 40) = 6;
  *(_DWORD *)(a1 + 44) = -1;
  *(_QWORD *)(a1 + 72) = &XmlTokenizerDriverTable;
  *(_QWORD *)(a1 + 88) = a1 + 104;
  result = a1;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  *(_QWORD *)(a1 + 64) = a2;
  *(_DWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 96) = 128;
  *(_DWORD *)(a1 + 360) = 0;
  return result;
}

```

## disassembly

```asm
0x1800132a4  xor     r8d, r8d
0x1800132a7  lea     rax, ??_7?$XMLParser@VGenericLexerSource@@@@6B@; const XMLParser<GenericLexerSource>::`vftable'
0x1800132ae  mov     [rcx], rax
0x1800132b1  xorps   xmm0, xmm0
0x1800132b4  lea     rax, [rcx+8]
0x1800132b8  movups  xmmword ptr [rax], xmm0
0x1800132bb  mov     [rax+10h], r8
0x1800132bf  mov     [rax+18h], rax
0x1800132c3  mov     dword ptr [rax+20h], 6
0x1800132ca  mov     dword ptr [rax+24h], 0FFFFFFFFh
0x1800132d1  lea     rax, ?XmlTokenizerDriverTable@@3PAULexEl@@A; LexEl near * XmlTokenizerDriverTable
0x1800132d8  mov     [rcx+48h], rax
0x1800132dc  lea     rax, [rcx+68h]
0x1800132e0  mov     [rcx+58h], rax
0x1800132e4  mov     rax, rcx
0x1800132e7  mov     [rcx+30h], r8
0x1800132eb  mov     [rcx+38h], rdx
0x1800132ef  mov     [rcx+40h], rdx
0x1800132f3  mov     [rcx+50h], r8d
0x1800132f7  mov     qword ptr [rcx+60h], 80h
0x1800132ff  mov     [rcx+168h], r8d
0x180013306  retn
```
