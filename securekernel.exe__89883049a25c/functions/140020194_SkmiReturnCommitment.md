# SkmiReturnCommitment

- ea: `0x140020194`
- end: `0x1400201f2`
- name: `SkmiReturnCommitment`
- size: `94`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001d0ac`
- `0x14001ed6c`
- `0x1400280b0`
- `0x14002eabc`
- `0x14005b00c`
- `0x14005b9e4`
- `0x1400603cc`
- `0x1400651cc`
- `0x140065d00`
- `0x1400661e4`
- `0x140066464`
- `0x14006779c`
- `0x14006a3d8`
- `0x14006a4b8`
- `0x14006a9a0`

## callees

- `0x1400017f4`
- `0x140002e40`
- `0x1400202b0`
- `0x1400f2fc0`

## pseudocode

```c
__int64 __fastcall SkmiReturnCommitment(__int64 a1, __int64 a2)
{
  char v4; // al
  char v5; // bl
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx

  _InterlockedAdd64(&SkmiTotalCommitment, -a2);
  v4 = SkAcquireSpinLockExclusive(a1 + 124);
  *(_QWORD *)(a1 + 128) -= a2;
  v5 = v4;
  *(_DWORD *)(a1 + 124) = 0;
  SkTrackSpinLockRelease(v7, v6);
  LOBYTE(v8) = v5;
  SkeLowerIrql(v8);
  return SkmiTrimIntegrityTable();
}

```

## disassembly

```asm
0x140020194  mov     [rsp+arg_0], rbx
0x140020199  mov     [rsp+arg_8], rsi
0x14002019e  push    rdi
0x14002019f  sub     rsp, 20h
0x1400201a3  mov     rax, rdx
0x1400201a6  mov     rdi, rdx
0x1400201a9  neg     rax
0x1400201ac  mov     rsi, rcx
0x1400201af  lock add cs:SkmiTotalCommitment, rax
0x1400201b7  add     rcx, 7Ch ; '|'
0x1400201bb  call    SkAcquireSpinLockExclusive
0x1400201c0  sub     [rsi+80h], rdi
0x1400201c7  mov     bl, al
0x1400201c9  mov     dword ptr [rsi+7Ch], 0
0x1400201d0  call    SkTrackSpinLockRelease
0x1400201d5  mov     cl, bl
0x1400201d7  call    SkeLowerIrql
0x1400201dc  call    SkmiTrimIntegrityTable
0x1400201e1  mov     rbx, [rsp+28h+arg_0]
0x1400201e6  mov     rsi, [rsp+28h+arg_8]
0x1400201eb  add     rsp, 20h
0x1400201ef  pop     rdi
0x1400201f0  retn
```
