# XMLParser<GenericLexerSource>::`scalar deleting destructor'(uint)

- ea: `0x1800133c0`
- end: `0x1800133ef`
- name: `??_G?$XMLParser@VGenericLexerSource@@@@UEAAPEAXI@Z`
- size: `47`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800034f0`
- `0x180013390`
- `0x1800133c0`

## pseudocode

```c
_QWORD *__fastcall XMLParser<GenericLexerSource>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  XMLParser<GenericLexerSource>::~XMLParser<GenericLexerSource>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800133c0  mov     [rsp+arg_0], rbx
0x1800133c5  push    rdi
0x1800133c6  sub     rsp, 20h
0x1800133ca  mov     ebx, edx
0x1800133cc  mov     rdi, rcx
0x1800133cf  call    ??1?$XMLParser@VGenericLexerSource@@@@UEAA@XZ; XMLParser<GenericLexerSource>::~XMLParser<GenericLexerSource>(void)
0x1800133d4  test    bl, 1
0x1800133d7  jz      short loc_1800133E1
0x1800133d9  mov     rcx, rdi; void *
0x1800133dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800133e1  mov     rbx, [rsp+28h+arg_0]
0x1800133e6  mov     rax, rdi
0x1800133e9  add     rsp, 20h
0x1800133ed  pop     rdi
0x1800133ee  retn
```
