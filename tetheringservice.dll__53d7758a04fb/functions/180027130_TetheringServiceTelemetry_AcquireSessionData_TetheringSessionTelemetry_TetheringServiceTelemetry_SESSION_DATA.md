# TetheringServiceTelemetry::AcquireSessionData(TetheringSessionTelemetry &,TetheringServiceTelemetry::SESSION_DATA &)

- ea: `0x180027130`
- end: `0x180027198`
- name: `?AcquireSessionData@TetheringServiceTelemetry@@QEAAXAEAVTetheringSessionTelemetry@@AEAUSESSION_DATA@1@@Z`
- size: `104`
- prototype: `void __fastcall(TetheringServiceTelemetry *this, RTL_SRWLOCK *, struct TetheringServiceTelemetry::SESSION_DATA *)`
- caller_count: `13`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000d9dc`
- `0x18000dfd8`
- `0x18000ee3c`
- `0x180010c6c`
- `0x180010e84`
- `0x1800110d4`
- `0x18001379c`
- `0x180014c8c`
- `0x180015430`
- `0x180019b4c`
- `0x18001dc08`
- `0x18001e4a4`
- `0x18001f740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027144`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027144`

## pseudocode

```c
void __fastcall TetheringServiceTelemetry::AcquireSessionData(
        TetheringServiceTelemetry *this,
        RTL_SRWLOCK *a2,
        struct TetheringServiceTelemetry::SESSION_DATA *a3)
{
  AcquireSRWLockExclusive(a2 + 2);
  *((_QWORD *)a3 + 7) = a2 + 10;
  *((_QWORD *)a3 + 8) = (char *)a2 + 92;
  *((_QWORD *)a3 + 9) = a2 + 17;
  *((_QWORD *)a3 + 2) = (char *)a2 + 68;
  *((_QWORD *)a3 + 3) = a2 + 7;
  *((_QWORD *)a3 + 4) = (char *)a2 + 60;
  *((_QWORD *)a3 + 5) = a2 + 8;
  *((_QWORD *)a3 + 6) = a2 + 9;
}

```

## disassembly

```asm
0x180027130  mov     [rsp+arg_0], rbx
0x180027135  push    rdi
0x180027136  sub     rsp, 20h
0x18002713a  lea     rcx, [rdx+10h]; SRWLock
0x18002713e  mov     rdi, r8
0x180027141  mov     rbx, rdx
0x180027144  call    cs:__imp_AcquireSRWLockExclusive
0x18002714a  lea     rax, [rbx+50h]
0x18002714e  mov     [rdi+38h], rax
0x180027152  lea     rax, [rbx+5Ch]
0x180027156  mov     [rdi+40h], rax
0x18002715a  lea     rax, [rbx+88h]
0x180027161  mov     [rdi+48h], rax
0x180027165  lea     rax, [rbx+44h]
0x180027169  mov     [rdi+10h], rax
0x18002716d  lea     rax, [rbx+38h]
0x180027171  mov     [rdi+18h], rax
0x180027175  lea     rax, [rbx+3Ch]
0x180027179  mov     [rdi+20h], rax
0x18002717d  lea     rax, [rbx+40h]
0x180027181  mov     [rdi+28h], rax
0x180027185  lea     rax, [rbx+48h]
0x180027189  mov     rbx, [rsp+28h+arg_0]
0x18002718e  mov     [rdi+30h], rax
0x180027192  add     rsp, 20h
0x180027196  pop     rdi
0x180027197  retn
```
