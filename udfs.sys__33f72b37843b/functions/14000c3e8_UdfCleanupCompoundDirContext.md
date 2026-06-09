# UdfCleanupCompoundDirContext

- ea: `0x14000c3e8`
- end: `0x14000c418`
- name: `UdfCleanupCompoundDirContext`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014cb8`
- `0x1400177ac`
- `0x14003269c`
- `0x140033548`
- `0x140034450`
- `0x14003f4c8`

## callees

- `0x14003f360`
- `0x1400567cc`

## pseudocode

```c
__int64 __fastcall UdfCleanupCompoundDirContext(__int64 a1, __int64 a2)
{
  UdfCleanupDirContext(a1, a2);
  return UdfCleanupIcbContext(a1, a2 + 152);
}

```

## disassembly

```asm
0x14000c3e8  mov     [rsp+arg_0], rbx
0x14000c3ed  push    rdi
0x14000c3ee  sub     rsp, 20h
0x14000c3f2  mov     rbx, rdx
0x14000c3f5  mov     rdi, rcx
0x14000c3f8  call    UdfCleanupDirContext
0x14000c3fd  lea     rdx, [rbx+98h]
0x14000c404  mov     rcx, rdi
0x14000c407  call    UdfCleanupIcbContext
0x14000c40c  mov     rbx, [rsp+28h+arg_0]
0x14000c411  add     rsp, 20h
0x14000c415  pop     rdi
0x14000c416  retn
```
