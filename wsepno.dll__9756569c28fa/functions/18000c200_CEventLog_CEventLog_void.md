# CEventLog::~CEventLog(void)

- ea: `0x18000c200`
- end: `0x18000c22c`
- name: `??1CEventLog@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CEventLog *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180005234`
- `0x180007d30`
- `0x180007de0`
- `0x180007e90`
- `0x180008510`
- `0x180008648`
- `0x1800087a8`

## callees

- `0x18000c200`
- `0x18000c324`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18000c211`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18000c211`

## pseudocode

```c
void __fastcall CEventLog::~CEventLog(void **this)
{
  void *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    DeregisterEventSource(v2);
    *this = 0;
  }
  CEventLog::CStrArray::Destroy((CEventLog::CStrArray *)(this + 1));
}

```

## disassembly

```asm
0x18000c200  push    rbx
0x18000c202  sub     rsp, 20h
0x18000c206  mov     rbx, rcx
0x18000c209  mov     rcx, [rcx]; hEventLog
0x18000c20c  test    rcx, rcx
0x18000c20f  jz      short loc_18000C21E
0x18000c211  call    cs:__imp_DeregisterEventSource
0x18000c217  mov     qword ptr [rbx], 0
0x18000c21e  lea     rcx, [rbx+8]; this
0x18000c222  add     rsp, 20h
0x18000c226  pop     rbx
0x18000c227  jmp     ?Destroy@CStrArray@CEventLog@@AEAAXXZ; CEventLog::CStrArray::Destroy(void)
```
