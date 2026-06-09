# CLogFileSector::WriteMoveNotification(ulong,LogMoveNotification const &)

- ea: `0x180008384`
- end: `0x18000841d`
- name: `?WriteMoveNotification@CLogFileSector@@QEAAXKAEBULogMoveNotification@@@Z`
- size: `153`
- prototype: `void __fastcall(CLogFileSector *__hidden this, unsigned int, const struct LogMoveNotification *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007f90`

## callees

- `0x18000833c`
- `0x180008430`

## pseudocode

```c
void __fastcall CLogFileSector::WriteMoveNotification(
        CLogFileSector *this,
        unsigned int a2,
        const struct LogMoveNotification *a3)
{
  struct tagLogEntry *LogEntry; // rax

  CLogFileSector::RaiseIfNotOpen(this);
  LogEntry = CLogFileSector::GetLogEntry(this, a2);
  *((_DWORD *)LogEntry + 2) = *(_DWORD *)a3;
  *((_DWORD *)LogEntry + 3) = *((_DWORD *)a3 + 1);
  *((_DWORD *)LogEntry + 4) = *((_DWORD *)a3 + 2);
  *(_OWORD *)((char *)LogEntry + 20) = *(_OWORD *)((char *)a3 + 12);
  *(_OWORD *)((char *)LogEntry + 36) = *(_OWORD *)((char *)a3 + 28);
  *(_OWORD *)((char *)LogEntry + 52) = *(_OWORD *)((char *)a3 + 44);
  *(_OWORD *)((char *)LogEntry + 68) = *(_OWORD *)((char *)a3 + 60);
  *(_OWORD *)((char *)LogEntry + 84) = *(_OWORD *)((char *)a3 + 76);
  *(_OWORD *)((char *)LogEntry + 100) = *(_OWORD *)((char *)a3 + 92);
  *((_DWORD *)LogEntry + 29) = *((_DWORD *)a3 + 27);
  *((_DWORD *)LogEntry + 30) = *((_DWORD *)a3 + 28);
  CLogFileSector::RaiseIfNotOpen(this);
  *(_DWORD *)this |= 2u;
}

```

## disassembly

```asm
0x180008384  mov     [rsp+arg_0], rbx
0x180008389  mov     [rsp+arg_8], rsi
0x18000838e  push    rdi
0x18000838f  sub     rsp, 20h
0x180008393  mov     rdi, r8
0x180008396  mov     ebx, edx
0x180008398  mov     rsi, rcx
0x18000839b  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x1800083a0  mov     edx, ebx; unsigned int
0x1800083a2  mov     rcx, rsi; this
0x1800083a5  call    ?GetLogEntry@CLogFileSector@@QEAAPEAUtagLogEntry@@K@Z; CLogFileSector::GetLogEntry(ulong)
0x1800083aa  mov     edx, [rdi]
0x1800083ac  mov     r9, rax
0x1800083af  mov     rcx, rsi; this
0x1800083b2  mov     [rax+8], edx
0x1800083b5  mov     edx, [rdi+4]
0x1800083b8  mov     [rax+0Ch], edx
0x1800083bb  mov     edx, [rdi+8]
0x1800083be  mov     [rax+10h], edx
0x1800083c1  movups  xmm0, xmmword ptr [rdi+0Ch]
0x1800083c5  movdqu  xmmword ptr [rax+14h], xmm0
0x1800083ca  movups  xmm0, xmmword ptr [rdi+1Ch]
0x1800083ce  movdqu  xmmword ptr [rax+24h], xmm0
0x1800083d3  movups  xmm1, xmmword ptr [rdi+2Ch]
0x1800083d7  movdqu  xmmword ptr [rax+34h], xmm1
0x1800083dc  movups  xmm0, xmmword ptr [rdi+3Ch]
0x1800083e0  movdqu  xmmword ptr [rax+44h], xmm0
0x1800083e5  movups  xmm0, xmmword ptr [rdi+4Ch]
0x1800083e9  movdqu  xmmword ptr [rax+54h], xmm0
0x1800083ee  movups  xmm1, xmmword ptr [rdi+5Ch]
0x1800083f2  movdqu  xmmword ptr [rax+64h], xmm1
0x1800083f7  mov     eax, [rdi+6Ch]
0x1800083fa  mov     [r9+74h], eax
0x1800083fe  mov     eax, [rdi+70h]
0x180008401  mov     [r9+78h], eax
0x180008405  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x18000840a  or      dword ptr [rsi], 2
0x18000840d  mov     rsi, [rsp+28h+arg_8]
0x180008412  mov     rbx, [rsp+28h+arg_0]
0x180008417  add     rsp, 20h
0x18000841b  pop     rdi
0x18000841c  retn
```
