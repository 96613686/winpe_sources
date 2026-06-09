# VmsOmSwitchGetStats

- ea: `0x14004c070`
- end: `0x14004c4a4`
- name: `VmsOmSwitchGetStats`
- size: `1076`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400b4364`

## callees

- `0x140027a64`
- `0x14004c070`
- `0x14008497c`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004c27c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004c3b6`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004c27c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004c3b6`
- `NDIS!NdisAcquireRWLockRead` at `0x14004c0b6`
- `NDIS!NdisAcquireRWLockRead` at `0x14004c29f`
- `NDIS!NdisAcquireRWLockRead` at `0x14004c0b6`
- `NDIS!NdisAcquireRWLockRead` at `0x14004c29f`
- `NDIS!NdisReleaseRWLock` at `0x14004c24c`
- `NDIS!NdisReleaseRWLock` at `0x14004c363`
- `NDIS!NdisReleaseRWLock` at `0x14004c24c`
- `NDIS!NdisReleaseRWLock` at `0x14004c363`

## pseudocode

```c
void __fastcall VmsOmSwitchGetStats(__int64 a1, _QWORD *a2)
{
  __int64 i; // r10
  __int64 j; // rdx
  __int64 k; // rdx
  __int64 m; // rdx
  __int64 *v8; // r12
  __int64 *v9; // r14
  int v10; // edx
  int v11; // edx
  unsigned int v12; // r13d
  __int64 v13; // r12
  _QWORD *v14; // rbx
  __int64 v15; // rdi
  _QWORD *v16; // rax
  unsigned __int64 v17; // r15
  __int64 v18; // rax
  unsigned int v19; // ecx
  const char *v20; // [rsp+30h] [rbp-58h]
  struct _LOCK_STATE_EX v21; // [rsp+90h] [rbp+8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+98h] [rbp+10h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+18h]

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(a2, 0, 0x140u);
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState, 0);
  for ( i = 0; (unsigned int)i < VmsMaximumProcCount; i = (unsigned int)(i + 1) )
  {
    *a2 += *(_QWORD *)(320 * i + a1 + 9664);
    a2[1] += *(_QWORD *)(320 * i + a1 + 9672);
    a2[2] += *(_QWORD *)(320 * i + a1 + 9680);
    a2[3] += *(_QWORD *)(320 * i + a1 + 9688);
    a2[4] += *(_QWORD *)(320 * i + a1 + 9696);
    a2[5] += *(_QWORD *)(320 * i + a1 + 9704);
    a2[6] += *(_QWORD *)(320 * i + a1 + 9712);
    a2[7] += *(_QWORD *)(320 * i + a1 + 9720);
    a2[8] += *(_QWORD *)(320 * i + a1 + 9728);
    a2[10] += *(_QWORD *)(320 * i + a1 + 9744);
    a2[11] += *(_QWORD *)(320 * i + a1 + 9752);
    a2[12] += *(_QWORD *)(320 * i + a1 + 9760);
    a2[13] += *(_QWORD *)(320 * i + a1 + 9768);
    a2[14] += *(_QWORD *)(320 * i + a1 + 9776);
    for ( j = 0; j != 4; ++j )
      a2[j + 17] += *(_QWORD *)(*(_QWORD *)(a1 + 9184) + 8 * (j + 16LL * (unsigned int)i));
    for ( k = 0; k != 6; ++k )
      a2[k + 21] += *(_QWORD *)(((unsigned __int64)(unsigned int)i << 7) + 32 + 8 * k + *(_QWORD *)(a1 + 9184));
    for ( m = 0; m != 6; ++m )
      a2[m + 27] += *(_QWORD *)(((unsigned __int64)(unsigned int)i << 7) + 80 + 8 * m + *(_QWORD *)(a1 + 9184));
  }
  v8 = (__int64 *)(a1 + 1416);
  a2[15] = *(_QWORD *)(a1 + 9784);
  a2[16] = *(_QWORD *)(a1 + 9792);
  v9 = *(__int64 **)(a1 + 1416);
  while ( v9 != v8 )
  {
    *(_WORD *)&v21.OldIrql = 0;
    v21.Flags = 0;
    if ( KeGetCurrentIrql() != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v10,
        19,
        24,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        "KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v9[7], &v21, 1u);
    v12 = 0;
    v13 = *(_QWORD *)(a1 + 1504);
    v14 = 0;
    v23 = v9[162];
LABEL_14:
    v15 = *(_QWORD *)(v13 + 56);
    v16 = v14;
    v14 += 2;
    if ( !v16 )
      v14 = *(_QWORD **)v15;
    v17 = *(_QWORD *)v15 + 16LL * *(unsigned int *)(v15 + 8);
    while ( (unsigned __int64)v14 <= v17 )
    {
      if ( (unsigned __int64)v14 < *(_QWORD *)v15 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v11,
          19,
          10,
          (__int64)WPP_69588da4af783cda376b20afdf4d2080_Traceguids,
          "Entry >= &AddressTable->Entries[0]");
        if ( (unsigned __int64)v14 < *(_QWORD *)v15 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( (unsigned __int64)v14 > *(_QWORD *)v15 + 16 * (unsigned __int64)*(unsigned int *)(v15 + 8) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v11,
          19,
          11,
          (__int64)WPP_69588da4af783cda376b20afdf4d2080_Traceguids,
          "Entry <= &AddressTable->Entries[AddressTable->MaxBucketIndex]");
        if ( (unsigned __int64)v14 > *(_QWORD *)v15 + 16 * (unsigned __int64)*(unsigned int *)(v15 + 8) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( (((_BYTE)v14 - *(_BYTE *)v15) & 0xF) != 0 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v11,
          19,
          12,
          (__int64)WPP_69588da4af783cda376b20afdf4d2080_Traceguids,
          "((PUCHAR)Entry -(PUCHAR)AddressTable->Entries) % sizeof(*Entry) == 0",
          v20);
        if ( (((_BYTE)v14 - *(_BYTE *)v15) & 0xF) != 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( *v14 )
      {
        v18 = v14[1];
        if ( (v18 & 0xFFFFFFFFFFFFFEF8uLL) != 0 )
        {
          if ( !v14 )
            break;
          v19 = v12 + 1;
          if ( (v18 & 0xFFFFFFFFFFFFFFF8uLL) != v23 )
            v19 = v12;
          v12 = v19;
          goto LABEL_14;
        }
      }
      v14 += 2;
    }
    a2[9] += v12;
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v9[7], &v21);
    v9 = (__int64 *)*v9;
    v8 = (__int64 *)(a1 + 1416);
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
}

```

## disassembly

```asm
0x14004c070  mov     r11, rsp
0x14004c073  mov     [r11+20h], rbx
0x14004c077  push    rbp
0x14004c078  push    rsi
0x14004c079  push    rdi
0x14004c07a  push    r12
0x14004c07c  push    r13
0x14004c07e  push    r14
0x14004c080  push    r15
0x14004c082  sub     rsp, 50h
0x14004c086  mov     rsi, rdx
0x14004c089  xor     eax, eax
0x14004c08b  mov     rbp, rcx
0x14004c08e  mov     [r11+10h], ax
0x14004c093  mov     rcx, rsi; void *
0x14004c096  mov     [r11+12h], al
0x14004c09a  xor     edx, edx; Val
0x14004c09c  mov     r8d, 140h; Size
0x14004c0a2  call    memset
0x14004c0a7  mov     rcx, [rbp+38h]; Lock
0x14004c0ab  lea     rdx, [rsp+88h+LockState]; LockState
0x14004c0b3  xor     r8d, r8d; Flags
0x14004c0b6  call    cs:__imp_NdisAcquireRWLockRead
0x14004c0bd  nop     dword ptr [rax+rax+00h]
0x14004c0c2  xor     r10d, r10d
0x14004c0c5  cmp     cs:VmsMaximumProcCount, r10d
0x14004c0cc  jz      loc_14004C213
0x14004c0d2  lea     rcx, [r10+r10*4]
0x14004c0d6  mov     r8d, r10d
0x14004c0d9  shl     rcx, 6
0x14004c0dd  add     r8, r8
0x14004c0e0  mov     r9d, r10d
0x14004c0e3  mov     rax, [rcx+rbp+25C0h]
0x14004c0eb  add     [rsi], rax
0x14004c0ee  mov     rax, [rcx+rbp+25C8h]
0x14004c0f6  add     [rsi+8], rax
0x14004c0fa  mov     rax, [rcx+rbp+25D0h]
0x14004c102  add     [rsi+10h], rax
0x14004c106  mov     rax, [rcx+rbp+25D8h]
0x14004c10e  add     [rsi+18h], rax
0x14004c112  mov     rax, [rcx+rbp+25E0h]
0x14004c11a  add     [rsi+20h], rax
0x14004c11e  mov     rax, [rcx+rbp+25E8h]
0x14004c126  add     [rsi+28h], rax
0x14004c12a  mov     rax, [rcx+rbp+25F0h]
0x14004c132  add     [rsi+30h], rax
0x14004c136  mov     rax, [rcx+rbp+25F8h]
0x14004c13e  add     [rsi+38h], rax
0x14004c142  mov     rax, [rcx+rbp+2600h]
0x14004c14a  add     [rsi+40h], rax
0x14004c14e  mov     rax, [rcx+rbp+2610h]
0x14004c156  add     [rsi+50h], rax
0x14004c15a  mov     rax, [rcx+rbp+2618h]
0x14004c162  add     [rsi+58h], rax
0x14004c166  mov     rax, [rcx+rbp+2620h]
0x14004c16e  add     [rsi+60h], rax
0x14004c172  mov     rax, [rcx+rbp+2628h]
0x14004c17a  add     [rsi+68h], rax
0x14004c17e  mov     rax, [rcx+rbp+2630h]
0x14004c186  add     [rsi+70h], rax
0x14004c18a  xor     edx, edx
0x14004c18c  mov     rax, [rbp+23E0h]
0x14004c193  lea     rcx, [rdx+r8*8]
0x14004c197  mov     rcx, [rax+rcx*8]
0x14004c19b  add     [rsi+rdx*8+88h], rcx
0x14004c1a3  inc     rdx
0x14004c1a6  cmp     rdx, 4
0x14004c1aa  jnz     short loc_14004C18C
0x14004c1ac  mov     r8, r9
0x14004c1af  xor     edx, edx
0x14004c1b1  shl     r8, 7
0x14004c1b5  add     r8, 20h ; ' '
0x14004c1b9  mov     rax, [rbp+23E0h]
0x14004c1c0  lea     rcx, [r8+rdx*8]
0x14004c1c4  mov     rcx, [rcx+rax]
0x14004c1c8  add     [rsi+rdx*8+0A8h], rcx
0x14004c1d0  inc     rdx
0x14004c1d3  cmp     rdx, 6
0x14004c1d7  jnz     short loc_14004C1B9
0x14004c1d9  xor     edx, edx
0x14004c1db  shl     r9, 7
0x14004c1df  add     r9, 50h ; 'P'
0x14004c1e3  mov     rax, [rbp+23E0h]
0x14004c1ea  lea     rcx, [r9+rdx*8]
0x14004c1ee  mov     rcx, [rcx+rax]
0x14004c1f2  add     [rsi+rdx*8+0D8h], rcx
0x14004c1fa  inc     rdx
0x14004c1fd  cmp     rdx, 6
0x14004c201  jnz     short loc_14004C1E3
0x14004c203  inc     r10d
0x14004c206  cmp     r10d, cs:VmsMaximumProcCount
0x14004c20d  jb      loc_14004C0D2
0x14004c213  mov     rax, [rbp+2638h]
0x14004c21a  lea     r12, [rbp+588h]
0x14004c221  mov     [rsi+78h], rax
0x14004c225  mov     rax, [rbp+2640h]
0x14004c22c  mov     [rsi+80h], rax
0x14004c233  mov     r14, [r12]
0x14004c237  jmp     short loc_14004C262
0x14004c239  mov     eax, r13d
0x14004c23c  lea     rdx, [rsp+88h+arg_0]; LockState
0x14004c244  add     [rsi+48h], rax
0x14004c248  mov     rcx, [r14+38h]; Lock
0x14004c24c  call    cs:__imp_NdisReleaseRWLock
0x14004c253  nop     dword ptr [rax+rax+00h]
0x14004c258  mov     r14, [r14]
0x14004c25b  lea     r12, [rbp+588h]
0x14004c262  cmp     r14, r12
0x14004c265  jz      loc_14004C357
0x14004c26b  xor     eax, eax
0x14004c26d  mov     word ptr [rsp+88h+arg_0.OldIrql], ax
0x14004c275  mov     [rsp+88h+arg_0.Flags], al
0x14004c27c  call    cs:__imp_KeGetCurrentIrql
0x14004c283  nop     dword ptr [rax+rax+00h]
0x14004c288  cmp     al, 2
0x14004c28a  jnz     loc_14004C388
0x14004c290  mov     rcx, [r14+38h]; Lock
0x14004c294  lea     rdx, [rsp+88h+arg_0]; LockState
0x14004c29c  mov     r8b, 1; Flags
0x14004c29f  call    cs:__imp_NdisAcquireRWLockRead
0x14004c2a6  nop     dword ptr [rax+rax+00h]
0x14004c2ab  mov     rax, [r14+510h]
0x14004c2b2  xor     r13d, r13d
0x14004c2b5  mov     r12, [rbp+5E0h]
0x14004c2bc  xor     ebx, ebx
0x14004c2be  mov     [rsp+88h+arg_10], rax
0x14004c2c6  mov     rdi, [r12+38h]
0x14004c2cb  mov     rax, rbx
0x14004c2ce  add     rbx, 10h
0x14004c2d2  test    rax, rax
0x14004c2d5  mov     rcx, [rdi]
0x14004c2d8  mov     r15d, [rdi+8]
0x14004c2dc  cmovz   rbx, rcx
0x14004c2e0  shl     r15, 4
0x14004c2e4  add     r15, rcx
0x14004c2e7  cmp     rbx, r15
0x14004c2ea  ja      loc_14004C239
0x14004c2f0  cmp     rbx, [rdi]
0x14004c2f3  jb      loc_14004C3D4
0x14004c2f9  mov     eax, [rdi+8]
0x14004c2fc  shl     rax, 4
0x14004c300  add     rax, [rdi]
0x14004c303  cmp     rbx, rax
0x14004c306  ja      loc_14004C415
0x14004c30c  mov     al, bl
0x14004c30e  sub     al, [rdi]
0x14004c310  test    al, 0Fh
0x14004c312  jnz     loc_14004C460
0x14004c318  mov     rax, [rbx]
0x14004c31b  test    rax, rax
0x14004c31e  jnz     short loc_14004C326
0x14004c320  add     rbx, 10h
0x14004c324  jmp     short loc_14004C2E7
0x14004c326  mov     rax, [rbx+8]
0x14004c32a  test    rax, 0FFFFFFFFFFFFFEF8h
0x14004c330  jz      short loc_14004C320
0x14004c332  test    rbx, rbx
0x14004c335  jz      loc_14004C239
0x14004c33b  lea     ecx, [r13+1]
0x14004c33f  and     rax, 0FFFFFFFFFFFFFFF8h
0x14004c343  cmp     rax, [rsp+88h+arg_10]
0x14004c34b  cmovnz  ecx, r13d
0x14004c34f  mov     r13d, ecx
0x14004c352  jmp     loc_14004C2C6
0x14004c357  mov     rcx, [rbp+38h]; Lock
0x14004c35b  lea     rdx, [rsp+88h+LockState]; LockState
0x14004c363  call    cs:__imp_NdisReleaseRWLock
0x14004c36a  nop     dword ptr [rax+rax+00h]
0x14004c36f  mov     rbx, [rsp+88h+arg_18]
0x14004c377  add     rsp, 50h
0x14004c37b  pop     r15
0x14004c37d  pop     r14
0x14004c37f  pop     r13
0x14004c381  pop     r12
0x14004c383  pop     rdi
0x14004c384  pop     rsi
0x14004c385  pop     rbp
0x14004c386  retn
0x14004c388  mov     rcx, cs:VmsIfrLog
0x14004c38f  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x14004c396  mov     [rsp+88h+var_60], rax
0x14004c39b  mov     r9d, 18h
0x14004c3a1  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x14004c3a8  mov     [rsp+88h+var_68], rax
0x14004c3ad  lea     r8d, [r9-5]
0x14004c3b1  call    WPP_RECORDER_SF_s
0x14004c3b6  call    cs:__imp_KeGetCurrentIrql
0x14004c3bd  nop     dword ptr [rax+rax+00h]
0x14004c3c2  cmp     al, 2
0x14004c3c4  jz      loc_14004C290
0x14004c3ca  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x14004c3cf  jmp     loc_14004C290
0x14004c3d4  mov     rcx, cs:VmsIfrLog
0x14004c3db  lea     rax, aEntryAddressta; "Entry >= &AddressTable->Entries[0]"
0x14004c3e2  mov     [rsp+88h+var_60], rax
0x14004c3e7  mov     r9d, 0Ah
0x14004c3ed  lea     rax, WPP_69588da4af783cda376b20afdf4d2080_Traceguids
0x14004c3f4  mov     [rsp+88h+var_68], rax
0x14004c3f9  lea     r8d, [r9+9]
0x14004c3fd  call    WPP_RECORDER_SF_s
0x14004c402  cmp     rbx, [rdi]
0x14004c405  jnb     loc_14004C2F9
0x14004c40b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Entry >= &AddressTable->Entries[0]")
0x14004c410  jmp     loc_14004C2F9
0x14004c415  mov     rcx, cs:VmsIfrLog
0x14004c41c  lea     rax, aEntryAddressta_0; "Entry <= &AddressTable->Entries[Address"...
0x14004c423  mov     [rsp+88h+var_60], rax
0x14004c428  mov     r9d, 0Bh
0x14004c42e  lea     rax, WPP_69588da4af783cda376b20afdf4d2080_Traceguids
0x14004c435  mov     [rsp+88h+var_68], rax
0x14004c43a  lea     r8d, [r9+8]
0x14004c43e  call    WPP_RECORDER_SF_s
0x14004c443  mov     eax, [rdi+8]
0x14004c446  shl     rax, 4
0x14004c44a  add     rax, [rdi]
0x14004c44d  cmp     rbx, rax
0x14004c450  jbe     loc_14004C30C
0x14004c456  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Entry <= &AddressTable->Entries[AddressTable->MaxBucketIndex]")
0x14004c45b  jmp     loc_14004C30C
0x14004c460  mov     rcx, cs:VmsIfrLog
0x14004c467  lea     rax, aPucharEntryPuc; "((PUCHAR)Entry -(PUCHAR)AddressTable->E"...
0x14004c46e  mov     [rsp+88h+var_60], rax
0x14004c473  mov     r9d, 0Ch
0x14004c479  lea     rax, WPP_69588da4af783cda376b20afdf4d2080_Traceguids
0x14004c480  mov     [rsp+88h+var_68], rax
0x14004c485  lea     r8d, [r9+7]
0x14004c489  call    WPP_RECORDER_SF_s
0x14004c48e  mov     al, bl
0x14004c490  sub     al, [rdi]
0x14004c492  test    al, 0Fh
0x14004c494  jz      loc_14004C318
0x14004c49a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((PUCHAR)Entry -(PUCHAR)AddressTable->Entries) % sizeof(*Entry) == 0")
0x14004c49f  jmp     loc_14004C318
```
