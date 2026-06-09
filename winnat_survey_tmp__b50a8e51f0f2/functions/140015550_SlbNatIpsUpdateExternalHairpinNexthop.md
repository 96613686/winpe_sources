# SlbNatIpsUpdateExternalHairpinNexthop

- ea: `0x140015550`
- end: `0x1400156e9`
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
- `0x140015550`
- `0x14001ef70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015666`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015666`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400156b8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400156b8`

## pseudocode

```c
char __fastcall SlbNatIpsUpdateExternalHairpinNexthop(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // ecx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v10; // rdx
  char v11; // r8
  __int64 v12; // rdi
  char v13; // al
  _OWORD v14[2]; // [rsp+60h] [rbp-20h] BYREF
  int v15; // [rsp+B0h] [rbp+30h] BYREF
  int v16; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v17; // [rsp+C0h] [rbp+40h] BYREF

  v17 = 0;
  memset(v14, 0, 28);
  v15 = 0;
  v16 = 0;
  if ( *(_QWORD *)(a1 + 64) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  if ( (*(_BYTE *)(a2 + 64) & 0x20) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  if ( !*(_QWORD *)(a2 + 24) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  if ( (*(_BYTE *)(a2 + 64) & 1) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  (*(void (__fastcall **)(_QWORD, _QWORD, _OWORD *))(*(_QWORD *)(a1 + 16) + 112LL))(
    *(_QWORD *)(a1 + 8),
    *(_QWORD *)(a2 + 24),
    v14);
  if ( !*((_QWORD *)&v14[0] + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4);
  v6 = v14[0];
  if ( !LODWORD(v14[0]) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(0, v4);
    v6 = v14[0];
  }
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int, _QWORD, int, int, int *, int *, __int64 *))(*(_QWORD *)(a1 + 16) + 88LL))(
         *(_QWORD *)(a1 + 8),
         *(_QWORD *)(a1 + 48),
         1,
         *(_QWORD *)(a2 + 104) + 4LL,
         v6,
         0,
         ScopeIdUnspecified,
         1,
         &v15,
         &v16,
         &v17) < 0 )
    return 0;
  if ( (v15 & 1) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v7);
  if ( !v17 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v7);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 232));
  v10 = v17;
  v11 = *(_BYTE *)(a2 + 64) & 0xFE;
  v12 = *(_QWORD *)(a2 + 24);
  *(_DWORD *)(a2 + 12) = v16;
  v13 = v15 & 1;
  *(_QWORD *)(a2 + 24) = v10;
  *(_BYTE *)(a2 + 64) = v13 | v11;
  (*(void (__fastcall **)(_QWORD, __int64, _OWORD *))(*(_QWORD *)(a1 + 16) + 112LL))(*(_QWORD *)(a1 + 8), v10, v14);
  *(_DWORD *)(a1 + 120) = DWORD1(v14[1]);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 232));
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(a1 + 16) + 104LL))(*(_QWORD *)(a1 + 8), v12);
  return 1;
}

```

## disassembly

```asm
0x140015550  push    rbp
0x140015552  push    rbx
0x140015553  push    rsi
0x140015554  push    rdi
0x140015555  push    r14
0x140015557  mov     rbp, rsp
0x14001555a  sub     rsp, 80h
0x140015561  xor     ebx, ebx
0x140015563  xorps   xmm0, xmm0
0x140015566  xor     eax, eax
0x140015568  mov     [rbp+arg_10], rbx
0x14001556c  mov     rsi, rdx
0x14001556f  mov     r14, rcx
0x140015572  movups  [rbp+var_20], xmm0
0x140015576  mov     [rbp+arg_0], ebx
0x140015579  movups  [rbp+var_20+0Ch], xmm0
0x14001557d  mov     [rbp+arg_8], ebx
0x140015580  cmp     [rcx+40h], rbx
0x140015584  jz      short loc_14001558B
0x140015586  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001558b  test    byte ptr [rsi+40h], 20h
0x14001558f  jnz     short loc_140015596
0x140015591  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015596  cmp     [rsi+18h], rbx
0x14001559a  jnz     short loc_1400155A1
0x14001559c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400155a1  test    byte ptr [rsi+40h], 1
0x1400155a5  jnz     short loc_1400155AC
0x1400155a7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400155ac  mov     rax, [r14+10h]
0x1400155b0  lea     r8, [rbp+var_20]
0x1400155b4  mov     rdx, [rsi+18h]
0x1400155b8  mov     rcx, [r14+8]
0x1400155bc  mov     rax, [rax+70h]
0x1400155c0  call    _guard_dispatch_icall
0x1400155c5  cmp     qword ptr [rbp+var_20+8], rbx
0x1400155c9  jnz     short loc_1400155D0
0x1400155cb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400155d0  mov     ecx, dword ptr [rbp+var_20]
0x1400155d3  test    ecx, ecx
0x1400155d5  jnz     short loc_1400155DF
0x1400155d7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400155dc  mov     ecx, dword ptr [rbp+var_20]
0x1400155df  mov     rax, [r14+10h]
0x1400155e3  mov     r8d, 1
0x1400155e9  mov     r9, [rsi+68h]
0x1400155ed  mov     rdx, [r14+30h]
0x1400155f1  add     r9, 4
0x1400155f5  mov     r10, [rax+58h]
0x1400155f9  lea     rax, [rbp+arg_10]
0x1400155fd  mov     [rsp+80h+var_30], rax
0x140015602  lea     rax, [rbp+arg_8]
0x140015606  mov     [rsp+80h+var_38], rax
0x14001560b  lea     rax, [rbp+arg_0]
0x14001560f  mov     [rsp+80h+var_40], rax
0x140015614  mov     eax, cs:ScopeIdUnspecified
0x14001561a  mov     [rsp+80h+var_48], 1
0x140015622  mov     [rsp+80h+var_50], eax
0x140015626  mov     rax, r10
0x140015629  mov     [rsp+80h+var_58], rbx
0x14001562e  mov     [rsp+80h+var_60], ecx
0x140015632  mov     rcx, [r14+8]
0x140015636  call    _guard_dispatch_icall
0x14001563b  test    eax, eax
0x14001563d  jns     short loc_140015646
0x14001563f  xor     al, al
0x140015641  jmp     loc_1400156DA
0x140015646  test    byte ptr [rbp+arg_0], 1
0x14001564a  jz      short loc_140015651
0x14001564c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140015651  cmp     [rbp+arg_10], rbx
0x140015655  jnz     short loc_14001565C
0x140015657  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001565c  lea     rbx, [rsi+0E8h]
0x140015663  mov     rcx, rbx; SpinLock
0x140015666  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001566d  nop     dword ptr [rax+rax+00h]
0x140015672  mov     eax, [rbp+arg_8]
0x140015675  mov     r8b, [rsi+40h]
0x140015679  mov     rdx, [rbp+arg_10]
0x14001567d  and     r8b, 0FEh
0x140015681  mov     rdi, [rsi+18h]
0x140015685  mov     [rsi+0Ch], eax
0x140015688  mov     al, byte ptr [rbp+arg_0]
0x14001568b  and     al, 1
0x14001568d  mov     [rsi+18h], rdx
0x140015691  or      r8b, al
0x140015694  mov     [rsi+40h], r8b
0x140015698  lea     r8, [rbp+var_20]
0x14001569c  mov     rax, [r14+10h]
0x1400156a0  mov     rcx, [r14+8]
0x1400156a4  mov     rax, [rax+70h]
0x1400156a8  call    _guard_dispatch_icall
0x1400156ad  mov     r8d, [rbp+var_C]
0x1400156b1  mov     rcx, rbx; SpinLock
0x1400156b4  mov     [r14+78h], r8d
0x1400156b8  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400156bf  nop     dword ptr [rax+rax+00h]
0x1400156c4  mov     rcx, [r14+10h]
0x1400156c8  mov     rdx, rdi
0x1400156cb  mov     rax, [rcx+68h]
0x1400156cf  mov     rcx, [r14+8]
0x1400156d3  call    _guard_dispatch_icall
0x1400156d8  mov     al, 1
0x1400156da  add     rsp, 80h
0x1400156e1  pop     r14
0x1400156e3  pop     rdi
0x1400156e4  pop     rsi
0x1400156e5  pop     rbx
0x1400156e6  pop     rbp
0x1400156e7  retn
```
