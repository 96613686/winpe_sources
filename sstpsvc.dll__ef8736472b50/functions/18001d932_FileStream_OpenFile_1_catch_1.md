# _FileStream::OpenFile_::_1_::catch$1

- ea: `0x18001d932`
- end: `0x18001d957`
- name: `_FileStream::OpenFile_::_1_::catch$1`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall FileStream::OpenFile_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = 8;
  return 0;
}

```

## disassembly

```asm
0x18001d932  mov     [rsp+arg_8], rdx
0x18001d937  push    rbp
0x18001d938  sub     rsp, 60h
0x18001d93c  mov     rbp, rdx
0x18001d93f  mov     dword ptr [rbp+60h], 8
0x18001d946  mov     rax, 0
0x18001d950  add     rsp, 60h
0x18001d954  pop     rbp
0x18001d955  retn
```
