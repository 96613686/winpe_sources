# GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>::~GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>(void)

- ea: `0x18001334c`
- end: `0x180013368`
- name: `??1?$GenericLexer@V?$XmlTokenizer@VGenericLexerSource@@@@VGenericLexerSource@@@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180013390`

## callees

- `0x1800034f0`
- `0x18001334c`

## pseudocode

```c
void __fastcall GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>::~GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 24) != a1 + 40 )
    operator delete(*(void **)(a1 + 24));
}

```

## disassembly

```asm
0x18001334c  sub     rsp, 28h
0x180013350  lea     rax, [rcx+28h]
0x180013354  cmp     [rcx+18h], rax
0x180013358  jz      short loc_180013363
0x18001335a  mov     rcx, [rcx+18h]; void *
0x18001335e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013363  add     rsp, 28h
0x180013367  retn
```
