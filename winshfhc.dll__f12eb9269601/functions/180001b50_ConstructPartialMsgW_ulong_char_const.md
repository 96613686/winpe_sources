# ConstructPartialMsgW(ulong,char const *,...)

- ea: `0x180001b50`
- end: `0x180001b81`
- name: `?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ`
- size: `49`
- prototype: `struct tagLOG_PARTIAL_MSG *(unsigned int, const char *, ...)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b88`
- `0x1800020b4`
- `0x180002368`
- `0x180002688`

## import_xrefs

- `WDSCORE!ConstructPartialMsgVW` at `0x180001b6f`
- `WDSCORE!ConstructPartialMsgVW` at `0x180001b6f`

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
0x180001b50  mov     rax, rsp
0x180001b53  mov     [rax+10h], rdx
0x180001b57  mov     [rax+18h], r8
0x180001b5b  mov     [rax+20h], r9
0x180001b5f  sub     rsp, 38h
0x180001b63  lea     r8, [rax+18h]
0x180001b67  mov     qword ptr [rax-18h], 0
0x180001b6f  call    cs:__imp_ConstructPartialMsgVW
0x180001b76  nop     dword ptr [rax+rax+00h]
0x180001b7b  add     rsp, 38h
0x180001b7f  retn
```
