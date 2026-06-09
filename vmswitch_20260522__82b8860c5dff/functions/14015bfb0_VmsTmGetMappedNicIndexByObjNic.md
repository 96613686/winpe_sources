# VmsTmGetMappedNicIndexByObjNic

- ea: `0x14015bfb0`
- end: `0x14015c646`
- name: `VmsTmGetMappedNicIndexByObjNic`
- size: `1686`
- prototype: ``
- caller_count: `21`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002e564`
- `0x14008cd0c`
- `0x140094d5c`
- `0x14009c5dc`
- `0x14012c284`
- `0x14012de04`
- `0x14012e224`
- `0x14012ed40`
- `0x14012ff88`
- `0x1401309bc`
- `0x140130cf8`
- `0x14013114c`
- `0x14013176c`
- `0x140131e98`
- `0x140133240`
- `0x140134694`
- `0x140135b48`
- `0x140137770`
- `0x140141a14`
- `0x140142364`
- `0x140143890`

## callees

- `0x1400247dc`
- `0x140027a64`
- `0x1400313cc`
- `0x14003a450`
- `0x14004a1b4`
- `0x140052460`
- `0x14006b084`
- `0x14008497c`
- `0x14015bfb0`
- `0x14015e0d8`

## import_xrefs

- `NDIS!NdisAcquireRWLockRead` at `0x14015c203`
- `NDIS!NdisAcquireRWLockRead` at `0x14015c203`
- `NDIS!NdisReleaseRWLock` at `0x14015c1e9`
- `NDIS!NdisReleaseRWLock` at `0x14015c254`
- `NDIS!NdisReleaseRWLock` at `0x14015c48d`
- `NDIS!NdisReleaseRWLock` at `0x14015c4e9`
- `NDIS!NdisReleaseRWLock` at `0x14015c55b`
- `NDIS!NdisReleaseRWLock` at `0x14015c5e9`
- `NDIS!NdisReleaseRWLock` at `0x14015c1e9`
- `NDIS!NdisReleaseRWLock` at `0x14015c254`
- `NDIS!NdisReleaseRWLock` at `0x14015c48d`
- `NDIS!NdisReleaseRWLock` at `0x14015c4e9`
- `NDIS!NdisReleaseRWLock` at `0x14015c55b`
- `NDIS!NdisReleaseRWLock` at `0x14015c5e9`

## pseudocode

```c
__int64 __fastcall VmsTmGetMappedNicIndexByObjNic(__int64 a1, int a2, _WORD *a3)
{
  int v3; // r14d
  char v5; // r13
  char v7; // r12
  __int128 v8; // xmm6
  __int128 v9; // xmm7
  unsigned int v10; // edi
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rsi
  int v14; // edx
  __int64 v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 v19; // rsi
  int v20; // edx
  char v21; // di
  __int16 v22; // r13
  bool v23; // r15
  int v24; // edx
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // edx
  _WORD *v28; // r15
  int v29; // edx
  int v30; // r9d
  char v31; // si
  int v32; // edx
  char v33; // al
  __int64 v34; // xmm0_8
  struct _NDIS_RW_LOCK_EX *v35; // rcx
  int v37; // [rsp+28h] [rbp-89h]
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp-39h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-11h]
  struct _LOCK_STATE_EX v40; // [rsp+118h] [rbp+67h] BYREF
  int v41; // [rsp+120h] [rbp+6Fh]
  _WORD *v42; // [rsp+128h] [rbp+77h]
  struct _LOCK_STATE_EX v43; // [rsp+130h] [rbp+7Fh] BYREF

  v42 = a3;
  v41 = a2;
  v3 = 0;
  *(_WORD *)&v43.OldIrql = 0;
  v5 = a2;
  v43.Flags = 0;
  *(_WORD *)&v40.OldIrql = 0;
  v7 = 0;
  v40.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  v8 = 0;
  LockState.Flags = 0;
  v9 = 0;
  v39 = 0;
  if ( !a1 )
  {
    WPP_RECORDER_SF_s(VmsIfrLog, a2, 19, 96, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, "ObjNic != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( !a3 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      97,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      "MappedNicIndex != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( !a1 )
  {
    v10 = -1073741823;
    v3 = -1073741823;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, a2, 20, 98, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, 1);
    v13 = 56;
LABEL_49:
    v28 = v42;
    goto LABEL_50;
  }
  VmsOmObjectLockShared(a1, &LockState, 0);
  if ( !*(_QWORD *)(a1 + 1984) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v14,
      19,
      99,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      "ObjNic->Port != NULL");
    if ( !*(_QWORD *)(a1 + 1984) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v15 = a1 + 1888;
  if ( *(_QWORD *)(a1 + 1888)
    || (WPP_RECORDER_SF_s(
          VmsIfrLog,
          v14,
          19,
          100,
          (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
          "ObjNic->ParentSwitch != NULL"),
        *(_QWORD *)v15) )
  {
    v16 = a1 + 1888;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v16 = a1 + 1888;
  }
  v17 = *(_QWORD *)(a1 + 1984);
  if ( !v17 || !*(_QWORD *)v15 )
  {
    v16 = a1 + 1888;
    goto LABEL_47;
  }
  v18 = *(_QWORD *)(*(_QWORD *)v15 + 9000LL);
  if ( !v18 )
  {
LABEL_47:
    v10 = -1073741823;
    v3 = -1073741823;
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_qqqd(
      VmsIfrNicLog,
      v17,
      20,
      101,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      *(_QWORD *)(a1 + 1984),
      *(_QWORD *)v16,
      *(_QWORD *)(*(_QWORD *)v16 + 9000LL),
      1);
    goto LABEL_48;
  }
  v19 = *(_QWORD *)(v18 + 16);
  if ( !v19 )
  {
    WPP_RECORDER_SF_s(VmsIfrLog, v17, 19, 102, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, "Team != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v10 = -1073741823;
    v3 = -1073741823;
    LOBYTE(v20) = 2;
    WPP_RECORDER_SF_d(VmsIfrNicLog, v20, 20, 103, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, 1);
LABEL_48:
    v13 = a1 + 56;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
    goto LABEL_49;
  }
  v21 = *(_BYTE *)(a1 + 4910);
  v22 = 0;
  if ( v21 )
    v22 = *(_WORD *)(a1 + 4908);
  v23 = v21 != 0;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v19 + 1584), &v43, 0);
  v25 = *(_QWORD *)(*(_QWORD *)(a1 + 1984) + 10832LL);
  if ( !v25 )
    goto LABEL_45;
  v7 = 1;
  if ( !v21 )
  {
    v26 = *(_QWORD *)(v25 + 72);
    if ( v26 )
    {
      v22 = *(unsigned __int8 *)(v26 + 680);
      v23 = 1;
      goto LABEL_25;
    }
LABEL_45:
    v33 = v21;
    v10 = -1073741823;
    LOBYTE(v24) = 2;
    WPP_RECORDER_SF_qdd(
      VmsIfrNicLog,
      v24,
      20,
      104,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      v25,
      v33,
      1);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v19 + 1584), &v43);
    v28 = v42;
    v13 = a1 + 56;
    v5 = v41;
    v7 = 0;
    v3 = -1073741823;
    goto LABEL_50;
  }
LABEL_25:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v19 + 1584), &v43);
  if ( !v23 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v27,
      19,
      106,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      "mappedNicIndexSet");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v28 = v42;
  *v42 = v22;
  VmsOmObjectLockExclusive(a1, &v40, 0);
  v10 = -1073741823;
  v31 = v41;
  v39 = *(_QWORD *)(a1 + 4916);
  v8 = *(_OWORD *)(a1 + 4884);
  v9 = *(_OWORD *)(a1 + 4900);
  switch ( v41 )
  {
    case 1:
      ++*(_DWORD *)(a1 + 4912);
      if ( !*(_BYTE *)(a1 + 4910) )
      {
        *(_BYTE *)(a1 + 4910) = 1;
        *(_WORD *)(a1 + 4908) = v22;
      }
      break;
    case 3:
      ++*(_DWORD *)(a1 + 4916);
      if ( !*(_BYTE *)(a1 + 4910) )
      {
        WPP_RECORDER_SF_s(VmsIfrLog, v29, 19, 107, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, "FALSE");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      break;
    case 2:
      if ( !*(_DWORD *)(a1 + 4884) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v29,
          v41 + 17,
          v41 + 106,
          (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
          "ObjNic->VportStub.ResourcesAllocatedCount != 0");
        if ( !*(_DWORD *)(a1 + 4884) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
          if ( !*(_DWORD *)(a1 + 4884) )
          {
            v3 = -1073741823;
            LOBYTE(v32) = 2;
            WPP_RECORDER_SF_d(VmsIfrNicLog, v32, 20, 109, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, 1);
          }
        }
      }
      break;
    default:
      WPP_RECORDER_SF_s(VmsIfrLog, v29, 19, 110, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, "FALSE");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      break;
  }
  if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_qddlllddd(
      WPP_GLOBAL_Control->DeviceExtension,
      *(unsigned __int16 *)(a1 + 4908),
      *(unsigned __int8 *)(a1 + 4910),
      v30,
      v37,
      a1,
      v31,
      *(_BYTE *)(a1 + 4910),
      *(_DWORD *)(a1 + 4884),
      *(_DWORD *)(a1 + 4912),
      *(_DWORD *)(a1 + 4916),
      *(_WORD *)(a1 + 4908),
      v22,
      v3);
  if ( *(_BYTE *)(a1 + 4910) )
    *v28 = *(_WORD *)(a1 + 4908);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &v40);
  v5 = v41;
  v13 = a1 + 56;
LABEL_50:
  if ( *v28 )
  {
    v10 = v3;
    if ( !v3 )
      return v10;
  }
  else if ( !v3 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v11,
      19,
      114,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      "status != NDIS_STATUS_SUCCESS");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( v7 )
  {
    VmsOmObjectLockExclusive(a1, &v40, 0);
    v34 = v39;
    v35 = *(struct _NDIS_RW_LOCK_EX **)v13;
    *(_OWORD *)(a1 + 4884) = v8;
    *(_OWORD *)(a1 + 4900) = v9;
    *(_QWORD *)(a1 + 4916) = v34;
    NdisReleaseRWLock(v35, &v40);
  }
  WPP_RECORDER_SF_qLd(
    VmsIfrNicLog,
    v11,
    v12,
    115,
    (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
    a1,
    v5,
    v10);
  return v10;
}

```

## disassembly

```asm
0x14015bfb0  mov     rax, rsp
0x14015bfb3  mov     [rax+18h], r8
0x14015bfb7  mov     [rax+10h], edx
0x14015bfba  push    rbp
0x14015bfbb  push    rbx
0x14015bfbc  push    rsi
0x14015bfbd  push    rdi
0x14015bfbe  push    r12
0x14015bfc0  push    r13
0x14015bfc2  push    r14
0x14015bfc4  push    r15
0x14015bfc6  lea     rbp, [rax-5Fh]
0x14015bfca  sub     rsp, 0C8h
0x14015bfd1  movaps  xmmword ptr [rax-58h], xmm6
0x14015bfd5  lea     r15, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015bfdc  movaps  xmmword ptr [rax-68h], xmm7
0x14015bfe0  xor     r14d, r14d
0x14015bfe3  xor     eax, eax
0x14015bfe5  mov     rdi, r8
0x14015bfe8  mov     word ptr [rbp+57h+arg_18.OldIrql], ax
0x14015bfec  mov     r13d, edx
0x14015bfef  mov     [rbp+57h+arg_18.Flags], al
0x14015bff5  mov     rbx, rcx
0x14015bff8  mov     word ptr [rbp+57h+arg_0.OldIrql], ax
0x14015bffc  mov     r12b, r14b
0x14015bfff  mov     [rbp+57h+arg_0.Flags], al
0x14015c002  lea     esi, [rax+13h]
0x14015c005  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14015c009  xorps   xmm6, xmm6
0x14015c00c  mov     [rbp+57h+LockState.Flags], al
0x14015c00f  xorps   xmm7, xmm7
0x14015c012  mov     [rbp+57h+var_68], rax
0x14015c016  test    rcx, rcx
0x14015c019  jnz     short loc_14015C044
0x14015c01b  lea     rax, aObjnicNull_0; "ObjNic != NULL"
0x14015c022  mov     r8d, esi
0x14015c025  lea     r9d, [rcx+60h]
0x14015c029  mov     [rsp+100h+var_D8], rax
0x14015c02e  mov     rcx, cs:VmsIfrLog
0x14015c035  mov     [rsp+100h+var_E0], r15
0x14015c03a  call    WPP_RECORDER_SF_s
0x14015c03f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic != ((void *)0)")
0x14015c044  test    rdi, rdi
0x14015c047  jnz     short loc_14015C072
0x14015c049  mov     rcx, cs:VmsIfrLog
0x14015c050  lea     rax, aMappednicindex_0; "MappedNicIndex != NULL"
0x14015c057  mov     [rsp+100h+var_D8], rax
0x14015c05c  lea     r9d, [rdi+61h]
0x14015c060  mov     r8d, esi
0x14015c063  mov     [rsp+100h+var_E0], r15
0x14015c068  call    WPP_RECORDER_SF_s
0x14015c06d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "MappedNicIndex != ((void *)0)")
0x14015c072  test    rbx, rbx
0x14015c075  jnz     short loc_14015C0A7
0x14015c077  mov     edi, 0C0000001h
0x14015c07c  mov     r14d, edi
0x14015c07f  mov     rcx, cs:VmsIfrLog
0x14015c086  lea     r9d, [rbx+62h]
0x14015c08a  mov     dword ptr [rsp+100h+var_D8], edi
0x14015c08e  lea     r8d, [rbx+14h]
0x14015c092  mov     dl, 2
0x14015c094  mov     [rsp+100h+var_E0], r15
0x14015c099  call    WPP_RECORDER_SF_d
0x14015c09e  lea     rsi, [rbx+38h]
0x14015c0a2  jmp     loc_14015C567
0x14015c0a7  xor     r8d, r8d
0x14015c0aa  lea     rdx, [rbp+57h+LockState]
0x14015c0ae  mov     rcx, rbx
0x14015c0b1  call    VmsOmObjectLockShared
0x14015c0b6  cmp     [rbx+7C0h], r14
0x14015c0bd  jnz     short loc_14015C0F3
0x14015c0bf  mov     rcx, cs:VmsIfrLog
0x14015c0c6  lea     rax, aObjnicPortNull; "ObjNic->Port != NULL"
0x14015c0cd  mov     [rsp+100h+var_D8], rax
0x14015c0d2  mov     r9d, 63h ; 'c'
0x14015c0d8  mov     r8d, esi
0x14015c0db  mov     [rsp+100h+var_E0], r15
0x14015c0e0  call    WPP_RECORDER_SF_s
0x14015c0e5  cmp     [rbx+7C0h], r14
0x14015c0ec  jnz     short loc_14015C0F3
0x14015c0ee  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic->Port != ((void *)0)")
0x14015c0f3  lea     rdi, [rbx+760h]
0x14015c0fa  cmp     [rdi], r14
0x14015c0fd  jnz     short loc_14015C138
0x14015c0ff  mov     rcx, cs:VmsIfrLog
0x14015c106  lea     rax, aObjnicParentsw; "ObjNic->ParentSwitch != NULL"
0x14015c10d  mov     [rsp+100h+var_D8], rax
0x14015c112  mov     r9d, 64h ; 'd'
0x14015c118  mov     r8d, esi
0x14015c11b  mov     [rsp+100h+var_E0], r15
0x14015c120  call    WPP_RECORDER_SF_s
0x14015c125  cmp     [rdi], r14
0x14015c128  jnz     short loc_14015C138
0x14015c12a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic->ParentSwitch != ((void *)0)")
0x14015c12f  lea     rcx, [rbx+760h]
0x14015c136  jmp     short loc_14015C13B
0x14015c138  mov     rcx, rdi
0x14015c13b  mov     rdx, [rbx+7C0h]
0x14015c142  test    rdx, rdx
0x14015c145  jz      loc_14015C50B
0x14015c14b  mov     rsi, [rdi]
0x14015c14e  test    rsi, rsi
0x14015c151  jz      loc_14015C50B
0x14015c157  mov     rsi, [rsi+2328h]
0x14015c15e  test    rsi, rsi
0x14015c161  jz      loc_14015C50E
0x14015c167  mov     rsi, [rsi+10h]
0x14015c16b  test    rsi, rsi
0x14015c16e  jnz     short loc_14015C1C6
0x14015c170  mov     rcx, cs:VmsIfrLog
0x14015c177  lea     rax, aTeamNull_0; "Team != NULL"
0x14015c17e  mov     [rsp+100h+var_D8], rax
0x14015c183  lea     r9d, [rsi+66h]
0x14015c187  lea     r8d, [rsi+13h]
0x14015c18b  mov     [rsp+100h+var_E0], r15
0x14015c190  call    WPP_RECORDER_SF_s
0x14015c195  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Team != ((void *)0)")
0x14015c19a  mov     edi, 0C0000001h
0x14015c19f  mov     r14d, edi
0x14015c1a2  mov     rcx, cs:VmsIfrNicLog
0x14015c1a9  lea     r9d, [rsi+67h]
0x14015c1ad  mov     dword ptr [rsp+100h+var_D8], edi
0x14015c1b1  lea     r8d, [rsi+14h]
0x14015c1b5  mov     dl, 2
0x14015c1b7  mov     [rsp+100h+var_E0], r15
0x14015c1bc  call    WPP_RECORDER_SF_d
0x14015c1c1  jmp     loc_14015C550
0x14015c1c6  movzx   edi, byte ptr [rbx+132Eh]
0x14015c1cd  mov     r13d, r14d
0x14015c1d0  test    dil, dil
0x14015c1d3  jz      short loc_14015C1DD
0x14015c1d5  movzx   r13d, word ptr [rbx+132Ch]
0x14015c1dd  mov     rcx, [rbx+38h]; Lock
0x14015c1e1  lea     rdx, [rbp+57h+LockState]; LockState
0x14015c1e5  setnz   r15b
0x14015c1e9  call    cs:__imp_NdisReleaseRWLock
0x14015c1f0  nop     dword ptr [rax+rax+00h]
0x14015c1f5  mov     rcx, [rsi+630h]; Lock
0x14015c1fc  lea     rdx, [rbp+57h+arg_18]; LockState
0x14015c200  xor     r8d, r8d; Flags
0x14015c203  call    cs:__imp_NdisAcquireRWLockRead
0x14015c20a  nop     dword ptr [rax+rax+00h]
0x14015c20f  mov     rax, [rbx+7C0h]
0x14015c216  mov     rcx, [rax+2A50h]
0x14015c21d  test    rcx, rcx
0x14015c220  jz      loc_14015C4A6
0x14015c226  mov     r12d, 1
0x14015c22c  test    dil, dil
0x14015c22f  jnz     short loc_14015C249
0x14015c231  mov     rax, [rcx+48h]
0x14015c235  test    rax, rax
0x14015c238  jz      loc_14015C4A6
0x14015c23e  movzx   r13d, byte ptr [rax+2A8h]
0x14015c246  mov     r15b, r12b
0x14015c249  mov     rcx, [rsi+630h]; Lock
0x14015c250  lea     rdx, [rbp+57h+arg_18]; LockState
0x14015c254  call    cs:__imp_NdisReleaseRWLock
0x14015c25b  nop     dword ptr [rax+rax+00h]
0x14015c260  test    r15b, r15b
0x14015c263  jnz     short loc_14015C298
0x14015c265  mov     rcx, cs:VmsIfrLog
0x14015c26c  lea     rax, aMappednicindex; "mappedNicIndexSet"
0x14015c273  mov     [rsp+100h+var_D8], rax
0x14015c278  mov     r9d, 6Ah ; 'j'
0x14015c27e  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c285  mov     [rsp+100h+var_E0], rax
0x14015c28a  lea     r8d, [r9-57h]
0x14015c28e  call    WPP_RECORDER_SF_s
0x14015c293  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "mappedNicIndexSet")
0x14015c298  mov     r15, [rbp+57h+arg_10]
0x14015c29c  lea     rdx, [rbp+57h+arg_0]
0x14015c2a0  xor     r8d, r8d
0x14015c2a3  mov     rcx, rbx
0x14015c2a6  mov     [r15], r13w
0x14015c2aa  call    VmsOmObjectLockExclusive
0x14015c2af  movsd   xmm0, qword ptr [rbx+1334h]
0x14015c2b7  mov     edi, 0C0000001h
0x14015c2bc  mov     esi, [rbp+57h+arg_8]
0x14015c2bf  movsd   [rbp+57h+var_68], xmm0
0x14015c2c4  movups  xmm6, xmmword ptr [rbx+1314h]
0x14015c2cb  movups  xmm7, xmmword ptr [rbx+1324h]
0x14015c2d2  cmp     esi, r12d
0x14015c2d5  jnz     short loc_14015C2FF
0x14015c2d7  add     [rbx+1330h], r12d
0x14015c2de  cmp     [rbx+132Eh], r14b
0x14015c2e5  jnz     loc_14015C402
0x14015c2eb  mov     [rbx+132Eh], r12b
0x14015c2f2  mov     [rbx+132Ch], r13w
0x14015c2fa  jmp     loc_14015C402
0x14015c2ff  cmp     esi, 3
0x14015c302  jnz     short loc_14015C34E
0x14015c304  add     [rbx+1334h], r12d
0x14015c30b  cmp     [rbx+132Eh], r14b
0x14015c312  jnz     loc_14015C402
0x14015c318  mov     rcx, cs:VmsIfrLog
0x14015c31f  lea     rax, aFalse; "FALSE"
0x14015c326  mov     [rsp+100h+var_D8], rax
0x14015c32b  lea     r9d, [rsi+68h]
0x14015c32f  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c336  lea     r8d, [rsi+10h]
0x14015c33a  mov     [rsp+100h+var_E0], rax
0x14015c33f  call    WPP_RECORDER_SF_s
0x14015c344  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "0")
0x14015c349  jmp     loc_14015C402
0x14015c34e  cmp     esi, 2
0x14015c351  jnz     short loc_14015C3CF
0x14015c353  cmp     [rbx+1314h], r14d
0x14015c35a  jnz     loc_14015C402
0x14015c360  mov     rcx, cs:VmsIfrLog
0x14015c367  lea     rax, aObjnicVportstu; "ObjNic->VportStub.ResourcesAllocatedCou"...
0x14015c36e  mov     [rsp+100h+var_D8], rax
0x14015c373  lea     r9d, [rsi+6Ah]
0x14015c377  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c37e  lea     r8d, [rsi+11h]
0x14015c382  mov     [rsp+100h+var_E0], rax
0x14015c387  call    WPP_RECORDER_SF_s
0x14015c38c  cmp     [rbx+1314h], r14d
0x14015c393  jnz     short loc_14015C402
0x14015c395  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic->VportStub.ResourcesAllocatedCount != 0")
0x14015c39a  cmp     [rbx+1314h], r14d
0x14015c3a1  jnz     short loc_14015C402
0x14015c3a3  mov     r14d, edi
0x14015c3a6  mov     rcx, cs:VmsIfrNicLog
0x14015c3ad  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c3b4  lea     r9d, [rsi+6Bh]
0x14015c3b8  mov     dword ptr [rsp+100h+var_D8], edi
0x14015c3bc  lea     r8d, [rsi+12h]
0x14015c3c0  mov     [rsp+100h+var_E0], rax
0x14015c3c5  mov     dl, sil
0x14015c3c8  call    WPP_RECORDER_SF_d
0x14015c3cd  jmp     short loc_14015C402
0x14015c3cf  mov     rcx, cs:VmsIfrLog
0x14015c3d6  lea     rax, aFalse; "FALSE"
0x14015c3dd  mov     [rsp+100h+var_D8], rax
0x14015c3e2  mov     r9d, 6Eh ; 'n'
0x14015c3e8  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c3ef  mov     [rsp+100h+var_E0], rax
0x14015c3f4  lea     r8d, [r9-5Bh]
0x14015c3f8  call    WPP_RECORDER_SF_s
0x14015c3fd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "0")
0x14015c402  mov     rcx, cs:WPP_GLOBAL_Control
0x14015c409  mov     al, [rcx+29h]
0x14015c40c  sub     al, r12b
0x14015c40f  cmp     al, 2
0x14015c411  ja      short loc_14015C41B
0x14015c413  xor     eax, eax
0x14015c415  cmp     [rcx+48h], ax
0x14015c419  jz      short loc_14015C472
0x14015c41b  movzx   edx, word ptr [rbx+132Ch]
0x14015c422  movzx   r8d, byte ptr [rbx+132Eh]
0x14015c42a  mov     rcx, [rcx+40h]
0x14015c42e  mov     [rsp+100h+var_98], r14d
0x14015c433  movzx   eax, r13w
0x14015c437  mov     [rsp+100h+var_A0], eax
0x14015c43b  mov     eax, [rbx+1334h]
0x14015c441  mov     [rsp+100h+var_A8], edx
0x14015c445  mov     [rsp+100h+var_B0], eax
0x14015c449  mov     eax, [rbx+1330h]
0x14015c44f  mov     [rsp+100h+var_B8], eax
0x14015c453  mov     eax, [rbx+1314h]
0x14015c459  mov     [rsp+100h+var_C0], eax
0x14015c45d  mov     [rsp+100h+var_C8], r8d
0x14015c462  mov     dword ptr [rsp+100h+var_D0], esi
0x14015c466  mov     [rsp+100h+var_D8], rbx
0x14015c46b  call    WPP_RECORDER_SF_qddlllddd
0x14015c470  xor     eax, eax
0x14015c472  cmp     [rbx+132Eh], al
0x14015c478  jz      short loc_14015C485
0x14015c47a  movzx   eax, word ptr [rbx+132Ch]
0x14015c481  mov     [r15], ax
0x14015c485  mov     rcx, [rbx+38h]; Lock
0x14015c489  lea     rdx, [rbp+57h+arg_0]; LockState
0x14015c48d  call    cs:__imp_NdisReleaseRWLock
0x14015c494  nop     dword ptr [rax+rax+00h]
0x14015c499  mov     r13d, [rbp+57h+arg_8]
0x14015c49d  lea     rsi, [rbx+38h]
0x14015c4a1  jmp     loc_14015C56B
0x14015c4a6  mov     eax, edi
0x14015c4a8  mov     r9d, 68h ; 'h'
0x14015c4ae  mov     edi, 0C0000001h
0x14015c4b3  mov     dl, 2
0x14015c4b5  mov     [rsp+100h+var_C8], edi
0x14015c4b9  mov     dword ptr [rsp+100h+var_D0], eax
0x14015c4bd  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c4c4  mov     [rsp+100h+var_D8], rcx
0x14015c4c9  lea     r8d, [r9-54h]
0x14015c4cd  mov     rcx, cs:VmsIfrNicLog
0x14015c4d4  mov     [rsp+100h+var_E0], rax
0x14015c4d9  call    WPP_RECORDER_SF_qdd
0x14015c4de  mov     rcx, [rsi+630h]; Lock
0x14015c4e5  lea     rdx, [rbp+57h+arg_18]; LockState
0x14015c4e9  call    cs:__imp_NdisReleaseRWLock
0x14015c4f0  nop     dword ptr [rax+rax+00h]
0x14015c4f5  mov     r15, [rbp+57h+arg_10]
0x14015c4f9  lea     rsi, [rbx+38h]
0x14015c4fd  mov     r13d, [rbp+57h+arg_8]
0x14015c501  xor     eax, eax
0x14015c503  mov     r12b, al
0x14015c506  mov     r14d, edi
0x14015c509  jmp     short loc_14015C56D
  ... truncated ...
```
