# wmi::AutoVectorPtr<ushort *>::~AutoVectorPtr<ushort *>(void)

- ea: `0x180006224`
- end: `0x18000622c`
- name: `??1?$AutoVectorPtr@PEAG@wmi@@QEAA@XZ`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c528`
- `0x18000c53a`
- `0x18000c54c`
- `0x18000c55e`

## callees

- `0x1800026c0`

## pseudocode

```c
void __fastcall wmi::AutoVectorPtr<unsigned short *>::~AutoVectorPtr<unsigned short *>(void **a1)
{
  operator delete(*a1);
}

```

## disassembly

```asm
0x180006224  mov     rcx, [rcx]; void *
0x180006227  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
