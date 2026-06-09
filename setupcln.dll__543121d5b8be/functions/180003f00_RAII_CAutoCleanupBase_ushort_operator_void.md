# RAII::CAutoCleanupBase<ushort *>::operator&(void)

- ea: `0x180003f00`
- end: `0x180003f05`
- name: `??I?$CAutoCleanupBase@PEAG@RAII@@UEBAPEBQEAGXZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800071a8`
- `0x18000ed8c`
- `0x18001200c`
- `0x1800123a0`

## pseudocode

```c
__int64 __fastcall RAII::CAutoCleanupBase<unsigned short *>::operator&(__int64 a1)
{
  return a1 + 8;
}

```

## disassembly

```asm
0x180003f00  lea     rax, [rcx+8]
0x180003f04  retn
```
