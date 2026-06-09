# operator delete(void *,unsigned __int64)

- ea: `0x140021b24`
- end: `0x140021b29`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140008020`
- `0x140009940`
- `0x14000a574`
- `0x140018d68`
- `0x140022c70`
- `0x1400233d8`
- `0x1400236e0`
- `0x140023720`
- `0x140023760`
- `0x1400237b0`
- `0x1400237f0`
- `0x140023830`
- `0x140023870`
- `0x140027480`
- `0x1400274b0`
- `0x1400283e0`
- `0x14002a9b0`
- `0x14002a9e0`
- `0x14002dac0`
- `0x14002faf0`
- `0x140031b60`
- `0x140031e20`
- `0x140031ef0`
- `0x1400324d2`
- `0x140032e8f`
- `0x1400336bb`
- `0x140033767`

## callees

- `0x1400039a0`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x140021b24  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
