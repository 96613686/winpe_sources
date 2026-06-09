# sub_18000DFFC

- ea: `0x18000dffc`
- end: `0x18000e026`
- name: `sub_18000DFFC`
- size: `42`
- prototype: `RTL_SRWLOCK **__fastcall(RTL_SRWLOCK **, RTL_SRWLOCK *)`
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e138`
- `0x18000e1e4`
- `0x18000e320`
- `0x18000ebc4`
- `0x18000ecf4`
- `0x18000edb4`
- `0x18000ee58`
- `0x18000eea4`
- `0x18000ef08`
- `0x18000efb8`
- `0x18000f03c`
- `0x18000f410`
- `0x18000f574`
- `0x18000f630`
- `0x18000f6ac`
- `0x18000f878`
- `0x1800106f8`
- `0x180010750`
- `0x1800107fc`
- `0x180010864`
- `0x1800109d8`
- `0x180014ce4`
- `0x18001633c`
- `0x1800182cc`
- `0x180018604`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e00f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e00f`

## pseudocode

```c
RTL_SRWLOCK **__fastcall sub_18000DFFC(RTL_SRWLOCK **a1, RTL_SRWLOCK *a2)
{
  AcquireSRWLockExclusive(a2);
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x18000dffc  mov     [rsp+arg_0], rbx
0x18000e001  push    rdi
0x18000e002  sub     rsp, 20h
0x18000e006  mov     rdi, rcx
0x18000e009  mov     rbx, rdx
0x18000e00c  mov     rcx, rdx; SRWLock
0x18000e00f  call    cs:AcquireSRWLockExclusive
0x18000e015  mov     [rdi], rbx
0x18000e018  mov     rax, rdi
0x18000e01b  mov     rbx, [rsp+28h+arg_0]
0x18000e020  add     rsp, 20h
0x18000e024  pop     rdi
0x18000e025  retn
```
