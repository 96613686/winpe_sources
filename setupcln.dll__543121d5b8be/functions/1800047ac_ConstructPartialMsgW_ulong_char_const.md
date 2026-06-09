# ConstructPartialMsgW(ulong,char const *,...)

- ea: `0x1800047ac`
- end: `0x1800047d6`
- name: `?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ`
- size: `42`
- prototype: `struct tagLOG_PARTIAL_MSG *(__int64, const char *, ...)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x1800040c0`
- `0x1800049a0`
- `0x180004c70`
- `0x180005080`
- `0x1800055e0`
- `0x1800056c0`
- `0x18000580c`
- `0x180005924`
- `0x180005c30`
- `0x180006518`
- `0x180006868`
- `0x180006b48`
- `0x180006f80`
- `0x1800070b0`
- `0x1800071a8`
- `0x1800074e4`
- `0x180007b68`
- `0x180007c44`
- `0x18000ed8c`
- `0x18001200c`

## import_xrefs

- `WDSCORE!ConstructPartialMsgVW` at `0x1800047cb`
- `WDSCORE!ConstructPartialMsgVW` at `0x1800047cb`

## pseudocode

```c
struct tagLOG_PARTIAL_MSG *ConstructPartialMsgW(__int64 a1, const char *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  return (struct tagLOG_PARTIAL_MSG *)ConstructPartialMsgVW(a1, a2, (__int64 *)va);
}

```

## disassembly

```asm
0x1800047ac  mov     rax, rsp
0x1800047af  mov     [rax+10h], rdx
0x1800047b3  mov     [rax+18h], r8
0x1800047b7  mov     [rax+20h], r9
0x1800047bb  sub     rsp, 38h
0x1800047bf  lea     r8, [rax+18h]
0x1800047c3  mov     qword ptr [rax-18h], 0
0x1800047cb  call    cs:__imp_ConstructPartialMsgVW
0x1800047d1  add     rsp, 38h
0x1800047d5  retn
```
