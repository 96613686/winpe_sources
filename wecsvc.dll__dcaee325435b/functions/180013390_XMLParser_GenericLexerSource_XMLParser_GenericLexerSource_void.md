# XMLParser<GenericLexerSource>::~XMLParser<GenericLexerSource>(void)

- ea: `0x180013390`
- end: `0x1800133ba`
- name: `??1?$XMLParser@VGenericLexerSource@@@@UEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800133c0`
- `0x18001351c`
- `0x1800221c4`
- `0x1800221d6`

## callees

- `0x18001334c`
- `0x180013370`

## pseudocode

```c
__int64 __fastcall XMLParser<GenericLexerSource>::~XMLParser<GenericLexerSource>(_QWORD *a1)
{
  *a1 = &XMLParser<GenericLexerSource>::`vftable';
  GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>::~GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>((__int64)(a1 + 8));
  return wmi::Stack<unsigned long,6,16>::~Stack<unsigned long,6,16>(a1 + 1);
}

```

## disassembly

```asm
0x180013390  push    rbx
0x180013392  sub     rsp, 20h
0x180013396  lea     rax, ??_7?$XMLParser@VGenericLexerSource@@@@6B@; const XMLParser<GenericLexerSource>::`vftable'
0x18001339d  mov     rbx, rcx
0x1800133a0  mov     [rcx], rax
0x1800133a3  add     rcx, 40h ; '@'
0x1800133a7  call    ??1?$GenericLexer@V?$XmlTokenizer@VGenericLexerSource@@@@VGenericLexerSource@@@@QEAA@XZ; GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>::~GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>(void)
0x1800133ac  lea     rcx, [rbx+8]
0x1800133b0  add     rsp, 20h
0x1800133b4  pop     rbx
0x1800133b5  jmp     ??1?$Stack@K$05$0BA@@wmi@@QEAA@XZ; wmi::Stack<ulong,6,16>::~Stack<ulong,6,16>(void)
```
