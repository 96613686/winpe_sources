# CreateCbsLogMonitorProvider

- ea: `0x180011c80`
- end: `0x180011ca2`
- name: `CreateCbsLogMonitorProvider`
- size: `34`
- prototype: `_QWORD *()`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001300`
- `0x180011c80`

## pseudocode

```c
_QWORD *CreateCbsLogMonitorProvider()
{
  _QWORD *result; // rax

  result = operator new(8u);
  if ( result )
    *result = &CCbsLogMonitorProvider::`vftable';
  return result;
}

```

## disassembly

```asm
0x180011c80  sub     rsp, 28h
0x180011c84  mov     ecx, 8; Size
0x180011c89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011c8e  test    rax, rax
0x180011c91  jz      short loc_180011C9D
0x180011c93  lea     rcx, ??_7CCbsLogMonitorProvider@@6B@; const CCbsLogMonitorProvider::`vftable'
0x180011c9a  mov     [rax], rcx
0x180011c9d  add     rsp, 28h
0x180011ca1  retn
```
