# CTPtrArray<WRITER_SINK_CALLBACK,20>::Add(WRITER_SINK_CALLBACK *,ulong *)

- ea: `0x18000807c`
- end: `0x1800080a8`
- name: `?Add@?$CTPtrArray@UWRITER_SINK_CALLBACK@@$0BE@@@QEAAHPEAUWRITER_SINK_CALLBACK@@PEAK@Z`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800086d0`
- `0x18000d930`
- `0x18000ef60`

## callees

- `0x18000807c`
- `0x18000b69c`

## pseudocode

```c
_BOOL8 __fastcall CTPtrArray<WRITER_SINK_CALLBACK,20>::Add(_DWORD *a1, __int64 (__fastcall **a2)(_QWORD, _QWORD *))
{
  int v3; // eax

  v3 = CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::SetValue(a1, a1[54], a2);
  if ( v3 >= 0 )
    ++a1[54];
  return v3 >= 0;
}

```

## disassembly

```asm
0x18000807c  push    rbx
0x18000807e  sub     rsp, 20h
0x180008082  mov     r8, rdx
0x180008085  mov     rbx, rcx
0x180008088  mov     edx, [rcx+0D8h]
0x18000808e  call    ?SetValue@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@QEAAJKPEAUWRITER_SINK_CALLBACK@@@Z; CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::SetValue(ulong,WRITER_SINK_CALLBACK *)
0x180008093  test    eax, eax
0x180008095  js      short loc_18000809D
0x180008097  inc     dword ptr [rbx+0D8h]
0x18000809d  not     eax
0x18000809f  shr     eax, 1Fh
0x1800080a2  add     rsp, 20h
0x1800080a6  pop     rbx
0x1800080a7  retn
```
