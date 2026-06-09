# SdbReadGUIDTag

- ea: `0x140013d54`
- end: `0x140013db8`
- name: `SdbReadGUIDTag`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140019410`
- `0x14001b4b0`
- `0x14001c290`
- `0x14002b138`

## callees

- `0x14001008c`
- `0x140013c14`
- `0x140013d54`

## string_xrefs

- `0x140013d87`: `Failed to read GUID`
- `0x140013d94`: `SdbReadGUIDTag`

## pseudocode

```c
_OWORD *__fastcall SdbReadGUIDTag(_OWORD *a1, __int64 a2, unsigned int a3, _OWORD *a4)
{
  *a1 = 0;
  if ( !(unsigned int)SdbReadBinaryTag(a2, a3, a1, 0x10u) )
  {
    AslLogCallPrintf(1, "SdbReadGUIDTag", 196, "Failed to read GUID");
    *a1 = *a4;
  }
  return a1;
}

```

## disassembly

```asm
0x140013d54  mov     [rsp+arg_0], rbx
0x140013d59  push    rdi
0x140013d5a  sub     rsp, 20h
0x140013d5e  mov     eax, r8d
0x140013d61  mov     r10, rdx
0x140013d64  xorps   xmm0, xmm0
0x140013d67  mov     rdi, r9
0x140013d6a  movups  xmmword ptr [rcx], xmm0
0x140013d6d  mov     rbx, rcx
0x140013d70  mov     r8, rcx
0x140013d73  mov     rcx, r10
0x140013d76  mov     r9d, 10h
0x140013d7c  mov     edx, eax
0x140013d7e  call    SdbReadBinaryTag
0x140013d83  test    eax, eax
0x140013d85  jnz     short loc_140013DAA
0x140013d87  lea     r9, aFailedToReadGu; "Failed to read GUID"
0x140013d8e  mov     r8d, 0C4h
0x140013d94  lea     rdx, aSdbreadguidtag; "SdbReadGUIDTag"
0x140013d9b  lea     ecx, [rax+1]
0x140013d9e  call    AslLogCallPrintf
0x140013da3  movaps  xmm0, xmmword ptr [rdi]
0x140013da6  movdqu  xmmword ptr [rbx], xmm0
0x140013daa  mov     rax, rbx
0x140013dad  mov     rbx, [rsp+28h+arg_0]
0x140013db2  add     rsp, 20h
0x140013db6  pop     rdi
0x140013db7  retn
```
