# CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::~CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>(void)

- ea: `0x180007bb4`
- end: `0x180007bd2`
- name: `??1?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180007bd8`
- `0x180009150`
- `0x18000d67c`
- `0x1800117c0`
- `0x180015874`
- `0x180015928`
- `0x180015e04`
- `0x1800160e4`
- `0x18001616c`

## callees

- `0x180007bb4`
- `0x180009188`

## pseudocode

```c
void **__fastcall CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::~CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>(
        __int64 a1)
{
  bool v1; // zf
  void **result; // rax

  v1 = *(_DWORD *)(a1 + 8) == 0;
  result = &CTPtrArray<CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD,20>::`vftable';
  *(_QWORD *)a1 = &CTPtrArray<CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD,20>::`vftable';
  if ( v1 )
    return (void **)CTSparseBlock<unsigned long,unsigned short *,20,1>::FreeList();
  return result;
}

```

## disassembly

```asm
0x180007bb4  sub     rsp, 28h
0x180007bb8  cmp     dword ptr [rcx+8], 0
0x180007bbc  lea     rax, ??_7?$CTPtrArray@U_STREAM_NAME_RECORD@CASFStreamPropertiesObjectEx@@$0BE@@@6B@; const CTPtrArray<CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD,20>::`vftable'
0x180007bc3  mov     [rcx], rax
0x180007bc6  jnz     short loc_180007BCD
0x180007bc8  call    ?FreeList@?$CTSparseBlock@KPEAG$0BE@$00@@QEAAJH@Z; CTSparseBlock<ulong,ushort *,20,1>::FreeList(int)
0x180007bcd  add     rsp, 28h
0x180007bd1  retn
```
