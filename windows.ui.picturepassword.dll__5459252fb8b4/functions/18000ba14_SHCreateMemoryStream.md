# SHCreateMemoryStream

- ea: `0x18000ba14`
- end: `0x18000ba3c`
- name: `SHCreateMemoryStream`
- size: `40`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000772c`
- `0x18000ed0c`

## import_xrefs

- `SHCORE!SHCreateMemStream` at `0x18000ba21`
- `SHCORE!SHCreateMemStream` at `0x18000ba21`

## pseudocode

```c
__int64 __fastcall SHCreateMemoryStream(__int64 a1, __int64 a2, IStream **a3)
{
  IStream *v4; // rax

  v4 = SHCreateMemStream(0, 0);
  *a3 = v4;
  return v4 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18000ba14  push    rbx
0x18000ba16  sub     rsp, 20h
0x18000ba1a  xor     edx, edx; cbInit
0x18000ba1c  xor     ecx, ecx; pInit
0x18000ba1e  mov     rbx, r8
0x18000ba21  call    cs:__imp_SHCreateMemStream
0x18000ba27  mov     [rbx], rax
0x18000ba2a  neg     rax
0x18000ba2d  sbb     eax, eax
0x18000ba2f  not     eax
0x18000ba31  and     eax, 8007000Eh
0x18000ba36  add     rsp, 20h
0x18000ba3a  pop     rbx
0x18000ba3b  retn
```
