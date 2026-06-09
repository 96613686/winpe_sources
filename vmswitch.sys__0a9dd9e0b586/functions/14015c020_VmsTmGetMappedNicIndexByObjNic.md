# VmsTmGetMappedNicIndexByObjNic

- ea: `0x14015c020`
- end: `0x14015c6b6`
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
- `0x14012c2f4`
- `0x14012de74`
- `0x14012e294`
- `0x14012edb0`
- `0x14012fff8`
- `0x140130a2c`
- `0x140130d68`
- `0x1401311bc`
- `0x1401317dc`
- `0x140131f08`
- `0x1401332b0`
- `0x140134704`
- `0x140135bb8`
- `0x1401377e0`
- `0x140141a84`
- `0x1401423d4`
- `0x140143900`

## callees

- `0x1400247dc`
- `0x140027a64`
- `0x1400313cc`
- `0x14003a450`
- `0x14004a1b4`
- `0x140052460`
- `0x14006b084`
- `0x14008497c`
- `0x14015c020`
- `0x14015e148`

## import_xrefs

- `NDIS!NdisAcquireRWLockRead` at `0x14015c273`
- `NDIS!NdisAcquireRWLockRead` at `0x14015c273`
- `NDIS!NdisReleaseRWLock` at `0x14015c259`
- `NDIS!NdisReleaseRWLock` at `0x14015c2c4`
- `NDIS!NdisReleaseRWLock` at `0x14015c4fd`
- `NDIS!NdisReleaseRWLock` at `0x14015c559`
- `NDIS!NdisReleaseRWLock` at `0x14015c5cb`
- `NDIS!NdisReleaseRWLock` at `0x14015c659`
- `NDIS!NdisReleaseRWLock` at `0x14015c259`
- `NDIS!NdisReleaseRWLock` at `0x14015c2c4`
- `NDIS!NdisReleaseRWLock` at `0x14015c4fd`
- `NDIS!NdisReleaseRWLock` at `0x14015c559`
- `NDIS!NdisReleaseRWLock` at `0x14015c5cb`
- `NDIS!NdisReleaseRWLock` at `0x14015c659`

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
0x14015c020  mov     rax, rsp
0x14015c023  mov     [rax+18h], r8
0x14015c027  mov     [rax+10h], edx
0x14015c02a  push    rbp
0x14015c02b  push    rbx
0x14015c02c  push    rsi
0x14015c02d  push    rdi
0x14015c02e  push    r12
0x14015c030  push    r13
0x14015c032  push    r14
0x14015c034  push    r15
0x14015c036  lea     rbp, [rax-5Fh]
0x14015c03a  sub     rsp, 0C8h
0x14015c041  movaps  xmmword ptr [rax-58h], xmm6
0x14015c045  lea     r15, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c04c  movaps  xmmword ptr [rax-68h], xmm7
0x14015c050  xor     r14d, r14d
0x14015c053  xor     eax, eax
0x14015c055  mov     rdi, r8
0x14015c058  mov     word ptr [rbp+57h+arg_18.OldIrql], ax
0x14015c05c  mov     r13d, edx
0x14015c05f  mov     [rbp+57h+arg_18.Flags], al
0x14015c065  mov     rbx, rcx
0x14015c068  mov     word ptr [rbp+57h+arg_0.OldIrql], ax
0x14015c06c  mov     r12b, r14b
0x14015c06f  mov     [rbp+57h+arg_0.Flags], al
0x14015c072  lea     esi, [rax+13h]
0x14015c075  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14015c079  xorps   xmm6, xmm6
0x14015c07c  mov     [rbp+57h+LockState.Flags], al
0x14015c07f  xorps   xmm7, xmm7
0x14015c082  mov     [rbp+57h+var_68], rax
0x14015c086  test    rcx, rcx
0x14015c089  jnz     short loc_14015C0B4
0x14015c08b  lea     rax, aObjnicNull_0; "ObjNic != NULL"
0x14015c092  mov     r8d, esi
0x14015c095  lea     r9d, [rcx+60h]
0x14015c099  mov     [rsp+100h+var_D8], rax
0x14015c09e  mov     rcx, cs:VmsIfrLog
0x14015c0a5  mov     [rsp+100h+var_E0], r15
0x14015c0aa  call    WPP_RECORDER_SF_s
0x14015c0af  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic != ((void *)0)")
0x14015c0b4  test    rdi, rdi
0x14015c0b7  jnz     short loc_14015C0E2
0x14015c0b9  mov     rcx, cs:VmsIfrLog
0x14015c0c0  lea     rax, aMappednicindex_0; "MappedNicIndex != NULL"
0x14015c0c7  mov     [rsp+100h+var_D8], rax
0x14015c0cc  lea     r9d, [rdi+61h]
0x14015c0d0  mov     r8d, esi
0x14015c0d3  mov     [rsp+100h+var_E0], r15
0x14015c0d8  call    WPP_RECORDER_SF_s
0x14015c0dd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "MappedNicIndex != ((void *)0)")
0x14015c0e2  test    rbx, rbx
0x14015c0e5  jnz     short loc_14015C117
0x14015c0e7  mov     edi, 0C0000001h
0x14015c0ec  mov     r14d, edi
0x14015c0ef  mov     rcx, cs:VmsIfrLog
0x14015c0f6  lea     r9d, [rbx+62h]
0x14015c0fa  mov     dword ptr [rsp+100h+var_D8], edi
0x14015c0fe  lea     r8d, [rbx+14h]
0x14015c102  mov     dl, 2
0x14015c104  mov     [rsp+100h+var_E0], r15
0x14015c109  call    WPP_RECORDER_SF_d
0x14015c10e  lea     rsi, [rbx+38h]
0x14015c112  jmp     loc_14015C5D7
0x14015c117  xor     r8d, r8d
0x14015c11a  lea     rdx, [rbp+57h+LockState]
0x14015c11e  mov     rcx, rbx
0x14015c121  call    VmsOmObjectLockShared
0x14015c126  cmp     [rbx+7C0h], r14
0x14015c12d  jnz     short loc_14015C163
0x14015c12f  mov     rcx, cs:VmsIfrLog
0x14015c136  lea     rax, aObjnicPortNull; "ObjNic->Port != NULL"
0x14015c13d  mov     [rsp+100h+var_D8], rax
0x14015c142  mov     r9d, 63h ; 'c'
0x14015c148  mov     r8d, esi
0x14015c14b  mov     [rsp+100h+var_E0], r15
0x14015c150  call    WPP_RECORDER_SF_s
0x14015c155  cmp     [rbx+7C0h], r14
0x14015c15c  jnz     short loc_14015C163
0x14015c15e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic->Port != ((void *)0)")
0x14015c163  lea     rdi, [rbx+760h]
0x14015c16a  cmp     [rdi], r14
0x14015c16d  jnz     short loc_14015C1A8
0x14015c16f  mov     rcx, cs:VmsIfrLog
0x14015c176  lea     rax, aObjnicParentsw; "ObjNic->ParentSwitch != NULL"
0x14015c17d  mov     [rsp+100h+var_D8], rax
0x14015c182  mov     r9d, 64h ; 'd'
0x14015c188  mov     r8d, esi
0x14015c18b  mov     [rsp+100h+var_E0], r15
0x14015c190  call    WPP_RECORDER_SF_s
0x14015c195  cmp     [rdi], r14
0x14015c198  jnz     short loc_14015C1A8
0x14015c19a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic->ParentSwitch != ((void *)0)")
0x14015c19f  lea     rcx, [rbx+760h]
0x14015c1a6  jmp     short loc_14015C1AB
0x14015c1a8  mov     rcx, rdi
0x14015c1ab  mov     rdx, [rbx+7C0h]
0x14015c1b2  test    rdx, rdx
0x14015c1b5  jz      loc_14015C57B
0x14015c1bb  mov     rsi, [rdi]
0x14015c1be  test    rsi, rsi
0x14015c1c1  jz      loc_14015C57B
0x14015c1c7  mov     rsi, [rsi+2328h]
0x14015c1ce  test    rsi, rsi
0x14015c1d1  jz      loc_14015C57E
0x14015c1d7  mov     rsi, [rsi+10h]
0x14015c1db  test    rsi, rsi
0x14015c1de  jnz     short loc_14015C236
0x14015c1e0  mov     rcx, cs:VmsIfrLog
0x14015c1e7  lea     rax, aTeamNull_0; "Team != NULL"
0x14015c1ee  mov     [rsp+100h+var_D8], rax
0x14015c1f3  lea     r9d, [rsi+66h]
0x14015c1f7  lea     r8d, [rsi+13h]
0x14015c1fb  mov     [rsp+100h+var_E0], r15
0x14015c200  call    WPP_RECORDER_SF_s
0x14015c205  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Team != ((void *)0)")
0x14015c20a  mov     edi, 0C0000001h
0x14015c20f  mov     r14d, edi
0x14015c212  mov     rcx, cs:VmsIfrNicLog
0x14015c219  lea     r9d, [rsi+67h]
0x14015c21d  mov     dword ptr [rsp+100h+var_D8], edi
0x14015c221  lea     r8d, [rsi+14h]
0x14015c225  mov     dl, 2
0x14015c227  mov     [rsp+100h+var_E0], r15
0x14015c22c  call    WPP_RECORDER_SF_d
0x14015c231  jmp     loc_14015C5C0
0x14015c236  movzx   edi, byte ptr [rbx+132Eh]
0x14015c23d  mov     r13d, r14d
0x14015c240  test    dil, dil
0x14015c243  jz      short loc_14015C24D
0x14015c245  movzx   r13d, word ptr [rbx+132Ch]
0x14015c24d  mov     rcx, [rbx+38h]; Lock
0x14015c251  lea     rdx, [rbp+57h+LockState]; LockState
0x14015c255  setnz   r15b
0x14015c259  call    cs:__imp_NdisReleaseRWLock
0x14015c260  nop     dword ptr [rax+rax+00h]
0x14015c265  mov     rcx, [rsi+630h]; Lock
0x14015c26c  lea     rdx, [rbp+57h+arg_18]; LockState
0x14015c270  xor     r8d, r8d; Flags
0x14015c273  call    cs:__imp_NdisAcquireRWLockRead
0x14015c27a  nop     dword ptr [rax+rax+00h]
0x14015c27f  mov     rax, [rbx+7C0h]
0x14015c286  mov     rcx, [rax+2A50h]
0x14015c28d  test    rcx, rcx
0x14015c290  jz      loc_14015C516
0x14015c296  mov     r12d, 1
0x14015c29c  test    dil, dil
0x14015c29f  jnz     short loc_14015C2B9
0x14015c2a1  mov     rax, [rcx+48h]
0x14015c2a5  test    rax, rax
0x14015c2a8  jz      loc_14015C516
0x14015c2ae  movzx   r13d, byte ptr [rax+2A8h]
0x14015c2b6  mov     r15b, r12b
0x14015c2b9  mov     rcx, [rsi+630h]; Lock
0x14015c2c0  lea     rdx, [rbp+57h+arg_18]; LockState
0x14015c2c4  call    cs:__imp_NdisReleaseRWLock
0x14015c2cb  nop     dword ptr [rax+rax+00h]
0x14015c2d0  test    r15b, r15b
0x14015c2d3  jnz     short loc_14015C308
0x14015c2d5  mov     rcx, cs:VmsIfrLog
0x14015c2dc  lea     rax, aMappednicindex; "mappedNicIndexSet"
0x14015c2e3  mov     [rsp+100h+var_D8], rax
0x14015c2e8  mov     r9d, 6Ah ; 'j'
0x14015c2ee  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c2f5  mov     [rsp+100h+var_E0], rax
0x14015c2fa  lea     r8d, [r9-57h]
0x14015c2fe  call    WPP_RECORDER_SF_s
0x14015c303  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "mappedNicIndexSet")
0x14015c308  mov     r15, [rbp+57h+arg_10]
0x14015c30c  lea     rdx, [rbp+57h+arg_0]
0x14015c310  xor     r8d, r8d
0x14015c313  mov     rcx, rbx
0x14015c316  mov     [r15], r13w
0x14015c31a  call    VmsOmObjectLockExclusive
0x14015c31f  movsd   xmm0, qword ptr [rbx+1334h]
0x14015c327  mov     edi, 0C0000001h
0x14015c32c  mov     esi, [rbp+57h+arg_8]
0x14015c32f  movsd   [rbp+57h+var_68], xmm0
0x14015c334  movups  xmm6, xmmword ptr [rbx+1314h]
0x14015c33b  movups  xmm7, xmmword ptr [rbx+1324h]
0x14015c342  cmp     esi, r12d
0x14015c345  jnz     short loc_14015C36F
0x14015c347  add     [rbx+1330h], r12d
0x14015c34e  cmp     [rbx+132Eh], r14b
0x14015c355  jnz     loc_14015C472
0x14015c35b  mov     [rbx+132Eh], r12b
0x14015c362  mov     [rbx+132Ch], r13w
0x14015c36a  jmp     loc_14015C472
0x14015c36f  cmp     esi, 3
0x14015c372  jnz     short loc_14015C3BE
0x14015c374  add     [rbx+1334h], r12d
0x14015c37b  cmp     [rbx+132Eh], r14b
0x14015c382  jnz     loc_14015C472
0x14015c388  mov     rcx, cs:VmsIfrLog
0x14015c38f  lea     rax, aFalse; "FALSE"
0x14015c396  mov     [rsp+100h+var_D8], rax
0x14015c39b  lea     r9d, [rsi+68h]
0x14015c39f  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c3a6  lea     r8d, [rsi+10h]
0x14015c3aa  mov     [rsp+100h+var_E0], rax
0x14015c3af  call    WPP_RECORDER_SF_s
0x14015c3b4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "0")
0x14015c3b9  jmp     loc_14015C472
0x14015c3be  cmp     esi, 2
0x14015c3c1  jnz     short loc_14015C43F
0x14015c3c3  cmp     [rbx+1314h], r14d
0x14015c3ca  jnz     loc_14015C472
0x14015c3d0  mov     rcx, cs:VmsIfrLog
0x14015c3d7  lea     rax, aObjnicVportstu; "ObjNic->VportStub.ResourcesAllocatedCou"...
0x14015c3de  mov     [rsp+100h+var_D8], rax
0x14015c3e3  lea     r9d, [rsi+6Ah]
0x14015c3e7  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c3ee  lea     r8d, [rsi+11h]
0x14015c3f2  mov     [rsp+100h+var_E0], rax
0x14015c3f7  call    WPP_RECORDER_SF_s
0x14015c3fc  cmp     [rbx+1314h], r14d
0x14015c403  jnz     short loc_14015C472
0x14015c405  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic->VportStub.ResourcesAllocatedCount != 0")
0x14015c40a  cmp     [rbx+1314h], r14d
0x14015c411  jnz     short loc_14015C472
0x14015c413  mov     r14d, edi
0x14015c416  mov     rcx, cs:VmsIfrNicLog
0x14015c41d  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c424  lea     r9d, [rsi+6Bh]
0x14015c428  mov     dword ptr [rsp+100h+var_D8], edi
0x14015c42c  lea     r8d, [rsi+12h]
0x14015c430  mov     [rsp+100h+var_E0], rax
0x14015c435  mov     dl, sil
0x14015c438  call    WPP_RECORDER_SF_d
0x14015c43d  jmp     short loc_14015C472
0x14015c43f  mov     rcx, cs:VmsIfrLog
0x14015c446  lea     rax, aFalse; "FALSE"
0x14015c44d  mov     [rsp+100h+var_D8], rax
0x14015c452  mov     r9d, 6Eh ; 'n'
0x14015c458  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c45f  mov     [rsp+100h+var_E0], rax
0x14015c464  lea     r8d, [r9-5Bh]
0x14015c468  call    WPP_RECORDER_SF_s
0x14015c46d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "0")
0x14015c472  mov     rcx, cs:WPP_GLOBAL_Control
0x14015c479  mov     al, [rcx+29h]
0x14015c47c  sub     al, r12b
0x14015c47f  cmp     al, 2
0x14015c481  ja      short loc_14015C48B
0x14015c483  xor     eax, eax
0x14015c485  cmp     [rcx+48h], ax
0x14015c489  jz      short loc_14015C4E2
0x14015c48b  movzx   edx, word ptr [rbx+132Ch]
0x14015c492  movzx   r8d, byte ptr [rbx+132Eh]
0x14015c49a  mov     rcx, [rcx+40h]
0x14015c49e  mov     [rsp+100h+var_98], r14d
0x14015c4a3  movzx   eax, r13w
0x14015c4a7  mov     [rsp+100h+var_A0], eax
0x14015c4ab  mov     eax, [rbx+1334h]
0x14015c4b1  mov     [rsp+100h+var_A8], edx
0x14015c4b5  mov     [rsp+100h+var_B0], eax
0x14015c4b9  mov     eax, [rbx+1330h]
0x14015c4bf  mov     [rsp+100h+var_B8], eax
0x14015c4c3  mov     eax, [rbx+1314h]
0x14015c4c9  mov     [rsp+100h+var_C0], eax
0x14015c4cd  mov     [rsp+100h+var_C8], r8d
0x14015c4d2  mov     dword ptr [rsp+100h+var_D0], esi
0x14015c4d6  mov     [rsp+100h+var_D8], rbx
0x14015c4db  call    WPP_RECORDER_SF_qddlllddd
0x14015c4e0  xor     eax, eax
0x14015c4e2  cmp     [rbx+132Eh], al
0x14015c4e8  jz      short loc_14015C4F5
0x14015c4ea  movzx   eax, word ptr [rbx+132Ch]
0x14015c4f1  mov     [r15], ax
0x14015c4f5  mov     rcx, [rbx+38h]; Lock
0x14015c4f9  lea     rdx, [rbp+57h+arg_0]; LockState
0x14015c4fd  call    cs:__imp_NdisReleaseRWLock
0x14015c504  nop     dword ptr [rax+rax+00h]
0x14015c509  mov     r13d, [rbp+57h+arg_8]
0x14015c50d  lea     rsi, [rbx+38h]
0x14015c511  jmp     loc_14015C5DB
0x14015c516  mov     eax, edi
0x14015c518  mov     r9d, 68h ; 'h'
0x14015c51e  mov     edi, 0C0000001h
0x14015c523  mov     dl, 2
0x14015c525  mov     [rsp+100h+var_C8], edi
0x14015c529  mov     dword ptr [rsp+100h+var_D0], eax
0x14015c52d  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015c534  mov     [rsp+100h+var_D8], rcx
0x14015c539  lea     r8d, [r9-54h]
0x14015c53d  mov     rcx, cs:VmsIfrNicLog
0x14015c544  mov     [rsp+100h+var_E0], rax
0x14015c549  call    WPP_RECORDER_SF_qdd
0x14015c54e  mov     rcx, [rsi+630h]; Lock
0x14015c555  lea     rdx, [rbp+57h+arg_18]; LockState
0x14015c559  call    cs:__imp_NdisReleaseRWLock
0x14015c560  nop     dword ptr [rax+rax+00h]
0x14015c565  mov     r15, [rbp+57h+arg_10]
0x14015c569  lea     rsi, [rbx+38h]
0x14015c56d  mov     r13d, [rbp+57h+arg_8]
0x14015c571  xor     eax, eax
0x14015c573  mov     r12b, al
0x14015c576  mov     r14d, edi
0x14015c579  jmp     short loc_14015C5DD
  ... truncated ...
```
