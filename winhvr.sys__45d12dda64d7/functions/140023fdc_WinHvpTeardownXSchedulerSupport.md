# WinHvpTeardownXSchedulerSupport

- ea: `0x140023fdc`
- end: `0x140024017`
- name: `WinHvpTeardownXSchedulerSupport`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e5ec`
- `0x140023d88`
- `0x14002a804`

## callees

- `0x14000b040`
- `0x140023fdc`

## pseudocode

```c
void WinHvpTeardownXSchedulerSupport()
{
  if ( WinHvpRootSchedulerActive )
  {
    if ( qword_140016198 )
    {
      WinHvpFreePoolWithTag((void *)qword_140016198, 0x58764857u);
      qword_140016198 = 0;
    }
    WinHvpRootSchedulerActive = 0;
  }
}

```

## disassembly

```asm
0x140023fdc  sub     rsp, 28h
0x140023fe0  cmp     cs:WinHvpRootSchedulerActive, 0
0x140023fe7  jz      short loc_140024011
0x140023fe9  mov     rcx, cs:qword_140016198
0x140023ff0  test    rcx, rcx
0x140023ff3  jz      short loc_14002400A
0x140023ff5  mov     edx, 58764857h
0x140023ffa  call    WinHvpFreePoolWithTag
0x140023fff  mov     cs:qword_140016198, 0
0x14002400a  mov     cs:WinHvpRootSchedulerActive, 0
0x140024011  add     rsp, 28h
0x140024015  retn
```
