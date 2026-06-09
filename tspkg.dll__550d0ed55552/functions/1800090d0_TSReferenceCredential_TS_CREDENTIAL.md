# TSReferenceCredential(_TS_CREDENTIAL *)

- ea: `0x1800090d0`
- end: `0x1800090d9`
- name: `?TSReferenceCredential@@YAXPEAU_TS_CREDENTIAL@@@Z`
- size: `9`
- prototype: `void __fastcall(struct _TS_CREDENTIAL *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a410`
- `0x18000a548`
- `0x180013200`
- `0x180013c64`
- `0x180013e00`
- `0x18001a3e0`
- `0x18001a820`
- `0x18001aa90`
- `0x18001b000`

## callees

- `0x1800090d0`

## pseudocode

```c
void __fastcall TSReferenceCredential(struct _TS_CREDENTIAL *a1)
{
  if ( a1 )
    _InterlockedIncrement((volatile signed __int32 *)a1);
}

```

## disassembly

```asm
0x1800090d0  test    rcx, rcx
0x1800090d3  jz      short locret_1800090D8
0x1800090d5  lock inc dword ptr [rcx]
0x1800090d8  retn
```
