# VmsCdpCopySwitchInfo

- ea: `0x140064aa0`
- end: `0x140064deb`
- name: `VmsCdpCopySwitchInfo`
- size: `843`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140035d14`
- `0x1400b3e68`

## callees

- `0x14001484c`
- `0x140027a64`
- `0x140064aa0`
- `0x140064df4`
- `0x14008497c`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140064ae4`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064cc0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064ae4`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064cc0`
- `NDIS!NdisAcquireRWLockRead` at `0x140064ad8`
- `NDIS!NdisAcquireRWLockRead` at `0x140064b04`
- `NDIS!NdisAcquireRWLockRead` at `0x140064ad8`
- `NDIS!NdisAcquireRWLockRead` at `0x140064b04`
- `NDIS!NdisReleaseRWLock` at `0x140064c57`
- `NDIS!NdisReleaseRWLock` at `0x140064c6f`
- `NDIS!NdisReleaseRWLock` at `0x140064c57`
- `NDIS!NdisReleaseRWLock` at `0x140064c6f`

## pseudocode

```c
void __fastcall VmsCdpCopySwitchInfo(__int64 a1, __int64 a2)
{
  char v4; // bp
  int v5; // edx
  __int64 ProtocolNicObject; // rax
  __int64 v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // ecx
  struct _LOCK_STATE_EX v12; // [rsp+50h] [rbp+8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  *(_WORD *)&v12.OldIrql = 0;
  v12.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  v4 = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead(VmsOmObjectListLock, &LockState, 0);
  if ( KeGetCurrentIrql() != 2 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v5,
      19,
      24,
      (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
      (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
    if ( KeGetCurrentIrql() != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &v12, 1u);
  memmove((void *)a2, *(const void **)(a1 + 352), *(unsigned __int16 *)(a1 + 344));
  memmove((void *)(a2 + 256), *(const void **)(a1 + 624), *(unsigned __int16 *)(a1 + 616));
  *(_DWORD *)(a2 + 768) = *(_DWORD *)(a1 + 68);
  memmove((void *)(a2 + 772), *(const void **)(a1 + 1664), *(unsigned __int16 *)(a1 + 1656));
  memmove((void *)(a2 + 2820), *(const void **)(a1 + 3728), *(unsigned __int16 *)(a1 + 3720));
  memmove((void *)(a2 + 3076), *(const void **)(a1 + 4000), *(unsigned __int16 *)(a1 + 3992));
  memmove((void *)(a2 + 3348), *(const void **)(a1 + 4336), *(unsigned __int16 *)(a1 + 4328));
  *(_DWORD *)(a2 + 3332) = *(_DWORD *)(a1 + 1456);
  *(_DWORD *)(a2 + 3336) = *(_DWORD *)(a1 + 1412);
  *(_BYTE *)(a2 + 3620) = *(_BYTE *)(a1 + 8568);
  *(_BYTE *)(a2 + 3621) = *(_BYTE *)(a1 + 8572);
  if ( *(_DWORD *)(a1 + 8568) )
    *(_DWORD *)(a2 + 3628) |= 0x80u;
  *(_BYTE *)(a2 + 3622) = 1;
  *(_DWORD *)(a2 + 3624) = *(_DWORD *)(a1 + 8720);
  ProtocolNicObject = VmsOmFindProtocolNicObject(a1);
  v7 = ProtocolNicObject;
  if ( ProtocolNicObject )
  {
    v9 = *(_QWORD *)(ProtocolNicObject + 3312);
    v4 = 1;
    if ( *(_BYTE *)(v9 + 304) )
      *(_DWORD *)(a2 + 3340) = *(_DWORD *)(v9 + 428);
    if ( *(_BYTE *)(v9 + 305) || *(_BYTE *)(v9 + 1513) )
    {
      *(_DWORD *)(a2 + 3604) = *(_DWORD *)(v9 + 1348);
      *(_DWORD *)(a2 + 3608) = *(_DWORD *)(v9 + 1356);
      *(_DWORD *)(a2 + 3612) = *(_DWORD *)(v9 + 1452);
      *(_DWORD *)(a2 + 3616) = *(_DWORD *)(v9 + 1436) + *(_DWORD *)(v9 + 1456);
    }
  }
  if ( *(_BYTE *)(a1 + 8904) )
    *(_DWORD *)(a2 + 3628) |= 1u;
  if ( *(_BYTE *)(a1 + 8912) )
  {
    *(_DWORD *)(a2 + 3628) |= 2u;
    v10 = *(_DWORD *)(a2 + 3628);
    if ( *(_DWORD *)(a1 + 8972) == 4 )
    {
      v11 = v10 | 8;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 8972) != 5 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          *(_DWORD *)(a1 + 8972) - 4,
          19,
          57,
          (__int64)WPP_cc27987529003045581b1d2fbac88226_Traceguids,
          (__int64)"!\"Invalid LoadBalancingAlgorithm\"");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
        goto LABEL_8;
      }
      v11 = v10 | 0x10;
    }
    *(_DWORD *)(a2 + 3628) = v11;
  }
LABEL_8:
  *(_DWORD *)(a2 + 3632) = *(_DWORD *)(a1 + 9144);
  if ( *(_BYTE *)(a1 + 8913) )
    *(_DWORD *)(a2 + 3628) |= 0x100u;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &v12);
  NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
  if ( v4 )
  {
    LOBYTE(v8) = 50;
    VmsOmpObjectDereference(v7, v8);
  }
}

```

## disassembly

```asm
0x140064aa0  mov     [rsp+arg_10], rbx
0x140064aa5  push    rbp
0x140064aa6  push    rsi
0x140064aa7  push    rdi
0x140064aa8  sub     rsp, 30h
0x140064aac  xor     eax, eax
0x140064aae  mov     rbx, rdx
0x140064ab1  mov     rdi, rcx
0x140064ab4  mov     word ptr [rsp+48h+arg_0.OldIrql], ax
0x140064ab9  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140064ac0  lea     rdx, [rsp+48h+LockState]; LockState
0x140064ac5  xor     r8d, r8d; Flags
0x140064ac8  mov     [rsp+48h+arg_0.Flags], al
0x140064acc  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140064ad1  xor     bpl, bpl
0x140064ad4  mov     [rsp+48h+LockState.Flags], al
0x140064ad8  call    cs:__imp_NdisAcquireRWLockRead
0x140064adf  nop     dword ptr [rax+rax+00h]
0x140064ae4  call    cs:__imp_KeGetCurrentIrql
0x140064aeb  nop     dword ptr [rax+rax+00h]
0x140064af0  cmp     al, 2
0x140064af2  jnz     loc_140064C92
0x140064af8  mov     rcx, [rdi+38h]; Lock
0x140064afc  lea     rdx, [rsp+48h+arg_0]; LockState
0x140064b01  mov     r8b, 1; Flags
0x140064b04  call    cs:__imp_NdisAcquireRWLockRead
0x140064b0b  nop     dword ptr [rax+rax+00h]
0x140064b10  movzx   r8d, word ptr [rdi+158h]; Size
0x140064b18  mov     rcx, rbx; void *
0x140064b1b  mov     rdx, [rdi+160h]; Src
0x140064b22  call    memmove
0x140064b27  movzx   r8d, word ptr [rdi+268h]; Size
0x140064b2f  lea     rcx, [rbx+100h]; void *
0x140064b36  mov     rdx, [rdi+270h]; Src
0x140064b3d  call    memmove
0x140064b42  mov     eax, [rdi+44h]
0x140064b45  lea     rcx, [rbx+304h]; void *
0x140064b4c  mov     [rbx+300h], eax
0x140064b52  movzx   r8d, word ptr [rdi+678h]; Size
0x140064b5a  mov     rdx, [rdi+680h]; Src
0x140064b61  call    memmove
0x140064b66  movzx   r8d, word ptr [rdi+0E88h]; Size
0x140064b6e  lea     rcx, [rbx+0B04h]; void *
0x140064b75  mov     rdx, [rdi+0E90h]; Src
0x140064b7c  call    memmove
0x140064b81  movzx   r8d, word ptr [rdi+0F98h]; Size
0x140064b89  lea     rcx, [rbx+0C04h]; void *
0x140064b90  mov     rdx, [rdi+0FA0h]; Src
0x140064b97  call    memmove
0x140064b9c  movzx   r8d, word ptr [rdi+10E8h]; Size
0x140064ba4  lea     rcx, [rbx+0D14h]; void *
0x140064bab  mov     rdx, [rdi+10F0h]; Src
0x140064bb2  call    memmove
0x140064bb7  mov     eax, [rdi+5B0h]
0x140064bbd  mov     [rbx+0D04h], eax
0x140064bc3  mov     eax, [rdi+584h]
0x140064bc9  mov     [rbx+0D08h], eax
0x140064bcf  mov     al, [rdi+2178h]
0x140064bd5  mov     [rbx+0E24h], al
0x140064bdb  mov     al, [rdi+217Ch]
0x140064be1  mov     [rbx+0E25h], al
0x140064be7  cmp     dword ptr [rdi+2178h], 0
0x140064bee  jnz     loc_140064CDE
0x140064bf4  mov     byte ptr [rbx+0E26h], 1
0x140064bfb  mov     rcx, rdi
0x140064bfe  mov     eax, [rdi+2210h]
0x140064c04  mov     [rbx+0E28h], eax
0x140064c0a  call    VmsOmFindProtocolNicObject
0x140064c0f  mov     rsi, rax
0x140064c12  test    rax, rax
0x140064c15  jnz     loc_140064CEB
0x140064c1b  cmp     byte ptr [rdi+22C8h], 0
0x140064c22  jnz     loc_140064D5B
0x140064c28  cmp     byte ptr [rdi+22D0h], 0
0x140064c2f  jnz     loc_140064D67
0x140064c35  mov     eax, [rdi+23B8h]
0x140064c3b  mov     [rbx+0E30h], eax
0x140064c41  cmp     byte ptr [rdi+22D1h], 0
0x140064c48  jnz     loc_140064DCF
0x140064c4e  mov     rcx, [rdi+38h]; Lock
0x140064c52  lea     rdx, [rsp+48h+arg_0]; LockState
0x140064c57  call    cs:__imp_NdisReleaseRWLock
0x140064c5e  nop     dword ptr [rax+rax+00h]
0x140064c63  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140064c6a  lea     rdx, [rsp+48h+LockState]; LockState
0x140064c6f  call    cs:__imp_NdisReleaseRWLock
0x140064c76  nop     dword ptr [rax+rax+00h]
0x140064c7b  test    bpl, bpl
0x140064c7e  jnz     loc_140064DDC
0x140064c84  mov     rbx, [rsp+48h+arg_10]
0x140064c89  add     rsp, 30h
0x140064c8d  pop     rdi
0x140064c8e  pop     rsi
0x140064c8f  pop     rbp
0x140064c90  retn
0x140064c92  mov     rcx, cs:VmsIfrLog
0x140064c99  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x140064ca0  mov     [rsp+48h+var_20], rax
0x140064ca5  mov     r9d, 18h
0x140064cab  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140064cb2  mov     [rsp+48h+var_28], rax
0x140064cb7  lea     r8d, [r9-5]
0x140064cbb  call    WPP_RECORDER_SF_s
0x140064cc0  call    cs:__imp_KeGetCurrentIrql
0x140064cc7  nop     dword ptr [rax+rax+00h]
0x140064ccc  cmp     al, 2
0x140064cce  jz      loc_140064AF8
0x140064cd4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x140064cd9  jmp     loc_140064AF8
0x140064cde  bts     dword ptr [rbx+0E2Ch], 7
0x140064ce6  jmp     loc_140064BF4
0x140064ceb  mov     rdx, [rax+0CF0h]
0x140064cf2  mov     bpl, 1
0x140064cf5  cmp     byte ptr [rdx+130h], 0
0x140064cfc  jz      short loc_140064D0A
0x140064cfe  mov     ecx, [rdx+1ACh]
0x140064d04  mov     [rbx+0D0Ch], ecx
0x140064d0a  cmp     byte ptr [rdx+131h], 0
0x140064d11  jnz     short loc_140064D20
0x140064d13  cmp     byte ptr [rdx+5E9h], 0
0x140064d1a  jz      loc_140064C1B
0x140064d20  mov     eax, [rdx+544h]
0x140064d26  mov     [rbx+0E14h], eax
0x140064d2c  mov     eax, [rdx+54Ch]
0x140064d32  mov     [rbx+0E18h], eax
0x140064d38  mov     eax, [rdx+5ACh]
0x140064d3e  mov     [rbx+0E1Ch], eax
0x140064d44  mov     eax, [rdx+5B0h]
0x140064d4a  add     eax, [rdx+59Ch]
0x140064d50  mov     [rbx+0E20h], eax
0x140064d56  jmp     loc_140064C1B
0x140064d5b  or      dword ptr [rbx+0E2Ch], 1
0x140064d62  jmp     loc_140064C28
0x140064d67  or      dword ptr [rbx+0E2Ch], 2
0x140064d6e  mov     edx, [rdi+230Ch]
0x140064d74  mov     ecx, [rbx+0E2Ch]
0x140064d7a  sub     edx, 4
0x140064d7d  jz      short loc_140064DC1
0x140064d7f  cmp     edx, 1
0x140064d82  jz      short loc_140064DBC
0x140064d84  mov     rcx, cs:VmsIfrLog
0x140064d8b  lea     rax, aInvalidLoadbal; "!\"Invalid LoadBalancingAlgorithm\""
0x140064d92  mov     [rsp+48h+var_20], rax
0x140064d97  mov     r9d, 39h ; '9'
0x140064d9d  lea     rax, WPP_cc27987529003045581b1d2fbac88226_Traceguids
0x140064da4  mov     [rsp+48h+var_28], rax
0x140064da9  lea     r8d, [r9-26h]
0x140064dad  call    WPP_RECORDER_SF_s
0x140064db2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"Invalid LoadBalancingAlgorithm"")
0x140064db7  jmp     loc_140064C35
0x140064dbc  or      ecx, 10h
0x140064dbf  jmp     short loc_140064DC4
0x140064dc1  or      ecx, 8
0x140064dc4  mov     [rbx+0E2Ch], ecx
0x140064dca  jmp     loc_140064C35
0x140064dcf  bts     dword ptr [rbx+0E2Ch], 8
0x140064dd7  jmp     loc_140064C4E
0x140064ddc  mov     dl, 32h ; '2'
0x140064dde  mov     rcx, rsi
0x140064de1  call    VmsOmpObjectDereference
0x140064de6  jmp     loc_140064C84
```
