# CreateObject<CDiagnosticMetadata>(void)

- ea: `0x180001010`
- end: `0x180001015`
- name: `??$CreateObject@VCDiagnosticMetadata@@@@YAPEAUIUnknown@@XZ`
- size: `5`
- prototype: `CDiagnosticMetadata *()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000101c`

## pseudocode

```c
// attributes: thunk
CDiagnosticMetadata *CreateObject<CDiagnosticMetadata>()
{
  return CreateClassObject<CDiagnosticMetadata>();
}

```

## disassembly

```asm
0x180001010  jmp     ??$CreateClassObject@VCDiagnosticMetadata@@@@YAPEAVCDiagnosticMetadata@@XZ; CreateClassObject<CDiagnosticMetadata>(void)
```
