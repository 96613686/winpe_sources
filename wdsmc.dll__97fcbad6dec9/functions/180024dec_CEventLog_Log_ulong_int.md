# CEventLog::Log(ulong,int,...)

- ea: `0x180024dec`
- end: `0x180024e09`
- name: `?Log@CEventLog@@QEAAKKHZZ`
- size: `29`
- prototype: `unsigned int(CEventLog *__hidden this, unsigned int, int, ...)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e28`
- `0x180005f18`
- `0x18000967c`
- `0x180009ab8`
- `0x180009cec`
- `0x180009dc8`
- `0x180009e84`
- `0x180016904`

## callees

- `0x180024e10`

## pseudocode

```c
unsigned int CEventLog::Log(CEventLog *this, unsigned int a2, int a3, ...)
{
  va_list va; // [rsp+48h] [rbp+20h] BYREF

  va_start(va, a3);
  return CEventLog::LogV(this, a2, a3, va);
}

```

## disassembly

```asm
0x180024dec  mov     [rsp+arg_10], r8d
0x180024df1  mov     qword ptr [rsp+arg_18], r9
0x180024df6  sub     rsp, 28h
0x180024dfa  lea     r9, [rsp+28h+arg_18]; char *
0x180024dff  call    ?LogV@CEventLog@@QEAAKKHPEAD@Z; CEventLog::LogV(ulong,int,char *)
0x180024e04  add     rsp, 28h
0x180024e08  retn
```
