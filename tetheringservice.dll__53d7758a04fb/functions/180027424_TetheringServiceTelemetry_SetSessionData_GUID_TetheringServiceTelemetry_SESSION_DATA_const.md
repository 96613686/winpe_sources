# TetheringServiceTelemetry::SetSessionData(_GUID *,TetheringServiceTelemetry::SESSION_DATA const &)

- ea: `0x180027424`
- end: `0x1800274ba`
- name: `?SetSessionData@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@AEBUSESSION_DATA@1@@Z`
- size: `150`
- prototype: `__int64 __fastcall(TetheringServiceTelemetry *__hidden this, struct _GUID *, const struct TetheringServiceTelemetry::SESSION_DATA *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000ce60`
- `0x180014c8c`
- `0x180019b4c`

## callees

- `0x1800272c0`
- `0x180027424`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027497`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027497`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027470`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027470`

## pseudocode

```c
__int64 __fastcall TetheringServiceTelemetry::SetSessionData(
        TetheringServiceTelemetry *this,
        struct _GUID *a2,
        const struct TetheringServiceTelemetry::SESSION_DATA *a3)
{
  int Session; // esi
  struct TetheringSessionTelemetry *v5; // rbx
  struct TetheringSessionTelemetry *v7; // [rsp+50h] [rbp+8h] BYREF

  v7 = 0;
  Session = TetheringServiceTelemetry::GetSession(this, a2, &v7);
  if ( Session >= 0 )
  {
    v5 = v7;
    AcquireSRWLockExclusive((PSRWLOCK)v7 + 2);
    *(_OWORD *)((char *)v5 + 196) = *(_OWORD *)*(_QWORD *)a3;
    *(_OWORD *)((char *)v5 + 212) = *(_OWORD *)*((_QWORD *)a3 + 1);
    ReleaseSRWLockExclusive((PSRWLOCK)v5 + 2);
    (*(void (__fastcall **)(struct TetheringSessionTelemetry *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else if ( v7 )
  {
    (*(void (__fastcall **)(struct TetheringSessionTelemetry *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return (unsigned int)Session;
}

```

## disassembly

```asm
0x180027424  mov     [rsp+arg_0], rcx
0x180027429  push    rbx
0x18002742a  push    rsi
0x18002742b  push    rdi
0x18002742c  push    r14
0x18002742e  sub     rsp, 28h
0x180027432  mov     r14, r8
0x180027435  mov     [rsp+48h+arg_0], 0
0x18002743e  lea     r8, [rsp+48h+arg_0]; struct TetheringSessionTelemetry **
0x180027443  call    ?GetSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@PEAPEAVTetheringSessionTelemetry@@@Z; TetheringServiceTelemetry::GetSession(_GUID *,TetheringSessionTelemetry * *)
0x180027448  mov     esi, eax
0x18002744a  test    eax, eax
0x18002744c  jns     short loc_180027467
0x18002744e  mov     rcx, [rsp+48h+arg_0]
0x180027453  test    rcx, rcx
0x180027456  jz      short loc_180027465
0x180027458  mov     rdx, [rcx]
0x18002745b  mov     rax, [rdx+10h]
0x18002745f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027464  nop
0x180027465  jmp     short loc_1800274AE
0x180027467  mov     rbx, [rsp+48h+arg_0]
0x18002746c  lea     rcx, [rbx+10h]; SRWLock
0x180027470  call    cs:__imp_AcquireSRWLockExclusive
0x180027476  mov     rax, [r14]
0x180027479  movups  xmm0, xmmword ptr [rax]
0x18002747c  movdqu  xmmword ptr [rbx+0C4h], xmm0
0x180027484  mov     rax, [r14+8]
0x180027488  movups  xmm1, xmmword ptr [rax]
0x18002748b  movdqu  xmmword ptr [rbx+0D4h], xmm1
0x180027493  lea     rcx, [rbx+10h]; SRWLock
0x180027497  call    cs:__imp_ReleaseSRWLockExclusive
0x18002749d  nop
0x18002749e  mov     rax, [rbx]
0x1800274a1  mov     rcx, rbx
0x1800274a4  mov     rax, [rax+10h]
0x1800274a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274ad  nop
0x1800274ae  mov     eax, esi
0x1800274b0  add     rsp, 28h
0x1800274b4  pop     r14
0x1800274b6  pop     rdi
0x1800274b7  pop     rsi
0x1800274b8  pop     rbx
0x1800274b9  retn
```
