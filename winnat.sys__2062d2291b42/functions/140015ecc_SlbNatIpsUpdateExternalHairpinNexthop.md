# SlbNatIpsUpdateExternalHairpinNexthop

- ea: `0x140015ecc`
- end: `0x140016065`
- name: `SlbNatIpsUpdateExternalHairpinNexthop`
- size: `409`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400020e0`

## callees

- `0x14000caa0`
- `0x140015ecc`
- `0x14001f4b0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015fe2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015fe2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016034`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016034`

## pseudocode

```c
char __fastcall SlbNatIpsUpdateExternalHairpinNexthop(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // ecx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v13; // rdx
  char v14; // r8
  __int64 v15; // rdi
  char v16; // al
  _OWORD v17[2]; // [rsp+60h] [rbp-20h] BYREF
  int v18; // [rsp+B0h] [rbp+30h] BYREF
  int v19; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v20; // [rsp+C0h] [rbp+40h] BYREF

  v20 = 0;
  memset(v17, 0, 28);
  v18 = 0;
  v19 = 0;
  if ( *(_QWORD *)(a1 + 64) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( (*(_BYTE *)(a2 + 64) & 0x20) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( !*(_QWORD *)(a2 + 24) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( (*(_BYTE *)(a2 + 64) & 1) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  (*(void (__fastcall **)(_QWORD, _QWORD, _OWORD *))(*(_QWORD *)(a1 + 16) + 112LL))(
    *(_QWORD *)(a1 + 8),
    *(_QWORD *)(a2 + 24),
    v17);
  if ( !*((_QWORD *)&v17[0] + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v7);
  v8 = v17[0];
  if ( !LODWORD(v17[0]) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(0, v5, v7);
    v8 = v17[0];
  }
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int, _QWORD, int, int, int *, int *, __int64 *))(*(_QWORD *)(a1 + 16) + 88LL))(
         *(_QWORD *)(a1 + 8),
         *(_QWORD *)(a1 + 48),
         1,
         *(_QWORD *)(a2 + 104) + 4LL,
         v8,
         0,
         ScopeIdUnspecified,
         1,
         &v18,
         &v19,
         &v20) < 0 )
    return 0;
  if ( (v18 & 1) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9, v11);
  if ( !v20 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9, v11);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 232));
  v13 = v20;
  v14 = *(_BYTE *)(a2 + 64) & 0xFE;
  v15 = *(_QWORD *)(a2 + 24);
  *(_DWORD *)(a2 + 12) = v19;
  v16 = v18 & 1;
  *(_QWORD *)(a2 + 24) = v13;
  *(_BYTE *)(a2 + 64) = v16 | v14;
  (*(void (__fastcall **)(_QWORD, __int64, _OWORD *))(*(_QWORD *)(a1 + 16) + 112LL))(*(_QWORD *)(a1 + 8), v13, v17);
  *(_DWORD *)(a1 + 120) = DWORD1(v17[1]);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 232));
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(a1 + 16) + 104LL))(*(_QWORD *)(a1 + 8), v15);
  return 1;
}

```

## disassembly

```asm
0x140015ecc  push    rbp
0x140015ece  push    rbx
0x140015ecf  push    rsi
0x140015ed0  push    rdi
0x140015ed1  push    r14
0x140015ed3  mov     rbp, rsp
0x140015ed6  sub     rsp, 80h
0x140015edd  xor     ebx, ebx
0x140015edf  xorps   xmm0, xmm0
0x140015ee2  xor     eax, eax
0x140015ee4  mov     [rbp+arg_10], rbx
0x140015ee8  mov     rsi, rdx
0x140015eeb  mov     r14, rcx
0x140015eee  movups  [rbp+var_20], xmm0
0x140015ef2  mov     [rbp+arg_0], ebx
0x140015ef5  movups  [rbp+var_20+0Ch], xmm0
0x140015ef9  mov     [rbp+arg_8], ebx
0x140015efc  cmp     [rcx+40h], rbx
0x140015f00  jz      short loc_140015F07
0x140015f02  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015f07  test    byte ptr [rsi+40h], 20h
0x140015f0b  jnz     short loc_140015F12
0x140015f0d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015f12  cmp     [rsi+18h], rbx
0x140015f16  jnz     short loc_140015F1D
0x140015f18  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015f1d  test    byte ptr [rsi+40h], 1
0x140015f21  jnz     short loc_140015F28
0x140015f23  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015f28  mov     rax, [r14+10h]
0x140015f2c  lea     r8, [rbp+var_20]
0x140015f30  mov     rdx, [rsi+18h]
0x140015f34  mov     rcx, [r14+8]
0x140015f38  mov     rax, [rax+70h]
0x140015f3c  call    _guard_dispatch_icall
0x140015f41  cmp     qword ptr [rbp+var_20+8], rbx
0x140015f45  jnz     short loc_140015F4C
0x140015f47  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015f4c  mov     ecx, dword ptr [rbp+var_20]
0x140015f4f  test    ecx, ecx
0x140015f51  jnz     short loc_140015F5B
0x140015f53  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015f58  mov     ecx, dword ptr [rbp+var_20]
0x140015f5b  mov     rax, [r14+10h]
0x140015f5f  mov     r8d, 1
0x140015f65  mov     r9, [rsi+68h]
0x140015f69  mov     rdx, [r14+30h]
0x140015f6d  add     r9, 4
0x140015f71  mov     r10, [rax+58h]
0x140015f75  lea     rax, [rbp+arg_10]
0x140015f79  mov     [rsp+80h+var_30], rax
0x140015f7e  lea     rax, [rbp+arg_8]
0x140015f82  mov     [rsp+80h+var_38], rax
0x140015f87  lea     rax, [rbp+arg_0]
0x140015f8b  mov     [rsp+80h+var_40], rax
0x140015f90  mov     eax, cs:ScopeIdUnspecified
0x140015f96  mov     [rsp+80h+var_48], 1
0x140015f9e  mov     [rsp+80h+var_50], eax
0x140015fa2  mov     rax, r10
0x140015fa5  mov     [rsp+80h+var_58], rbx
0x140015faa  mov     [rsp+80h+var_60], ecx
0x140015fae  mov     rcx, [r14+8]
0x140015fb2  call    _guard_dispatch_icall
0x140015fb7  test    eax, eax
0x140015fb9  jns     short loc_140015FC2
0x140015fbb  xor     al, al
0x140015fbd  jmp     loc_140016056
0x140015fc2  test    byte ptr [rbp+arg_0], 1
0x140015fc6  jz      short loc_140015FCD
0x140015fc8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015fcd  cmp     [rbp+arg_10], rbx
0x140015fd1  jnz     short loc_140015FD8
0x140015fd3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015fd8  lea     rbx, [rsi+0E8h]
0x140015fdf  mov     rcx, rbx; SpinLock
0x140015fe2  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140015fe9  nop     dword ptr [rax+rax+00h]
0x140015fee  mov     eax, [rbp+arg_8]
0x140015ff1  mov     r8b, [rsi+40h]
0x140015ff5  mov     rdx, [rbp+arg_10]
0x140015ff9  and     r8b, 0FEh
0x140015ffd  mov     rdi, [rsi+18h]
0x140016001  mov     [rsi+0Ch], eax
0x140016004  mov     al, byte ptr [rbp+arg_0]
0x140016007  and     al, 1
0x140016009  mov     [rsi+18h], rdx
0x14001600d  or      r8b, al
0x140016010  mov     [rsi+40h], r8b
0x140016014  lea     r8, [rbp+var_20]
0x140016018  mov     rax, [r14+10h]
0x14001601c  mov     rcx, [r14+8]
0x140016020  mov     rax, [rax+70h]
0x140016024  call    _guard_dispatch_icall
0x140016029  mov     r8d, [rbp+var_C]
0x14001602d  mov     rcx, rbx; SpinLock
0x140016030  mov     [r14+78h], r8d
0x140016034  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001603b  nop     dword ptr [rax+rax+00h]
0x140016040  mov     rcx, [r14+10h]
0x140016044  mov     rdx, rdi
0x140016047  mov     rax, [rcx+68h]
0x14001604b  mov     rcx, [r14+8]
0x14001604f  call    _guard_dispatch_icall
0x140016054  mov     al, 1
0x140016056  add     rsp, 80h
0x14001605d  pop     r14
0x14001605f  pop     rdi
0x140016060  pop     rsi
0x140016061  pop     rbx
0x140016062  pop     rbp
0x140016063  retn
```
