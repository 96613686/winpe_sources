# LOG_WRITER::ETWLogData::~ETWLogData(void)

- ea: `0x1800021c4`
- end: `0x18000229d`
- name: `??1ETWLogData@LOG_WRITER@@QEAA@XZ`
- size: `217`
- prototype: `void __fastcall(LOG_WRITER::ETWLogData *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003718`
- `0x18000ee05`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180002222`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000222f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000223c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002249`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002256`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002263`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002270`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000227d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002287`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002222`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000222f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000223c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002249`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002256`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002263`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002270`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000227d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002287`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002296`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800021d4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800021e1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800021ee`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800021fb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002208`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002215`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800021d4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800021e1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800021ee`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800021fb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002208`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002215`

## pseudocode

```c
void __fastcall LOG_WRITER::ETWLogData::~ETWLogData(LOG_WRITER::ETWLogData *this)
{
  STRA::~STRA((LOG_WRITER::ETWLogData *)((char *)this + 1784));
  STRA::~STRA((LOG_WRITER::ETWLogData *)((char *)this + 1712));
  STRA::~STRA((LOG_WRITER::ETWLogData *)((char *)this + 1624));
  STRA::~STRA((LOG_WRITER::ETWLogData *)((char *)this + 1536));
  STRA::~STRA((LOG_WRITER::ETWLogData *)((char *)this + 1448));
  STRA::~STRA((LOG_WRITER::ETWLogData *)((char *)this + 1360));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 1048));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 928));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 808));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 728));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 608));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 520));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 344));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 168));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 88));
  STRU::~STRU((LOG_WRITER::ETWLogData *)((char *)this + 8));
}

```

## disassembly

```asm
0x1800021c4  push    rbx
0x1800021c6  sub     rsp, 20h
0x1800021ca  mov     rbx, rcx
0x1800021cd  add     rcx, 6F8h
0x1800021d4  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800021da  lea     rcx, [rbx+6B0h]
0x1800021e1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800021e7  lea     rcx, [rbx+658h]
0x1800021ee  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800021f4  lea     rcx, [rbx+600h]
0x1800021fb  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002201  lea     rcx, [rbx+5A8h]
0x180002208  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000220e  lea     rcx, [rbx+550h]
0x180002215  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000221b  lea     rcx, [rbx+418h]
0x180002222  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002228  lea     rcx, [rbx+3A0h]
0x18000222f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002235  lea     rcx, [rbx+328h]
0x18000223c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002242  lea     rcx, [rbx+2D8h]
0x180002249  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000224f  lea     rcx, [rbx+260h]
0x180002256  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000225c  lea     rcx, [rbx+208h]
0x180002263  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002269  lea     rcx, [rbx+158h]
0x180002270  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002276  lea     rcx, [rbx+0A8h]
0x18000227d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002283  lea     rcx, [rbx+58h]
0x180002287  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000228d  lea     rcx, [rbx+8]
0x180002291  add     rsp, 20h
0x180002295  pop     rbx
0x180002296  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
