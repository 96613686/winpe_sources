# CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::GetEntry(int,unsigned __int64 &,CWMFileSinkV1::WRITER_SINK_COMMAND * &)

- ea: `0x18000950c`
- end: `0x18000952a`
- name: `?GetEntry@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@QEBAHHAEA_KAEAPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@Z`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000afa0`

## callees

- `0x18000950c`

## pseudocode

```c
__int64 __fastcall CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::GetEntry(
        _QWORD **a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  _QWORD *v4; // rdx

  v4 = *a1;
  if ( !*a1 )
    return 0;
  *a3 = *v4;
  *a4 = v4[1];
  return 1;
}

```

## disassembly

```asm
0x18000950c  mov     rdx, [rcx]
0x18000950f  test    rdx, rdx
0x180009512  jnz     short loc_180009517
0x180009514  xor     eax, eax
0x180009516  retn
0x180009517  mov     rax, [rdx]
0x18000951a  mov     [r8], rax
0x18000951d  mov     rax, [rdx+8]
0x180009521  mov     [r9], rax
0x180009524  mov     eax, 1
0x180009529  retn
```
