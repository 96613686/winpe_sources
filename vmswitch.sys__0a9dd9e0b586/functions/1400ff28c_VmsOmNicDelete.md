# VmsOmNicDelete

- ea: `0x1400ff28c`
- end: `0x1400ff611`
- name: `VmsOmNicDelete`
- size: `901`
- prototype: ``
- caller_count: `8`
- callee_count: `20`
- tags: `registry_config, installer_update`

## callers

- `0x1400a95d0`
- `0x1400f553c`
- `0x1400f617c`
- `0x1400f679c`
- `0x1400fb880`
- `0x1400fc794`
- `0x140117fb0`
- `0x140122570`

## callees

- `0x14001484c`
- `0x14002d318`
- `0x14002d86c`
- `0x14006b084`
- `0x14006ec68`
- `0x14006f844`
- `0x1400764b4`
- `0x1400a839c`
- `0x1400ff28c`
- `0x1401017ec`
- `0x1401041c8`
- `0x140104fb0`
- `0x14010654c`
- `0x1401068b8`
- `0x140106fa8`
- `0x1401affac`
- `0x1401bbbd4`
- `0x1401bbcb0`
- `0x1401bbe80`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ff37f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ff397`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ff37f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ff397`
- `NDIS!NdisMSleep` at `0x1400ff441`
- `NDIS!NdisMSleep` at `0x1400ff441`
- `NDIS!NdisReleaseRWLock` at `0x1400ff3f7`
- `NDIS!NdisReleaseRWLock` at `0x1400ff410`
- `NDIS!NdisReleaseRWLock` at `0x1400ff4bc`
- `NDIS!NdisReleaseRWLock` at `0x1401bccc6`
- `NDIS!NdisReleaseRWLock` at `0x1401bccee`
- `NDIS!NdisReleaseRWLock` at `0x1400ff3f7`
- `NDIS!NdisReleaseRWLock` at `0x1400ff410`
- `NDIS!NdisReleaseRWLock` at `0x1400ff4bc`
- `NDIS!NdisReleaseRWLock` at `0x1401bccc6`
- `NDIS!NdisReleaseRWLock` at `0x1401bccee`

## pseudocode

```c
__int64 __fastcall VmsOmNicDelete(__int64 a1, __int64 a2, __int64 a3)
{
  char v6; // r14
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rdx
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  void (__fastcall *v19)(__int64, _QWORD); // rax
  __int64 v20; // rbx
  __int64 v21; // rdx
  int v22; // edx
  __int64 v24; // [rsp+0h] [rbp-3D8h] BYREF
  __int64 v25; // [rsp+20h] [rbp-3B8h]
  __int64 v26; // [rsp+28h] [rbp-3B0h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+30h] [rbp-3A8h]
  struct _UNICODE_STRING *v28; // [rsp+38h] [rbp-3A0h]
  __int64 v29; // [rsp+40h] [rbp-398h]
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp-388h] BYREF
  struct _LOCK_STATE_EX v31; // [rsp+54h] [rbp-384h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-380h] BYREF
  int v33; // [rsp+5Ch] [rbp-37Ch]
  struct _UNICODE_STRING v34; // [rsp+60h] [rbp-378h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-368h] BYREF
  __int64 v36; // [rsp+80h] [rbp-358h]
  __int64 *v37; // [rsp+88h] [rbp-350h]
  _BYTE v38[256]; // [rsp+90h] [rbp-348h] BYREF
  _BYTE v39[512]; // [rsp+190h] [rbp-248h] BYREF

  v37 = &v24;
  v36 = a1;
  v32 = 0;
  *(_WORD *)&v31.OldIrql = 0;
  v31.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = 0;
  v33 = 0;
  memset(v38, 0, 0xFEu);
  *(_QWORD *)&DestinationString.Length = 16646144;
  DestinationString.Buffer = (wchar_t *)v38;
  memset(v39, 0, 0x1FEu);
  *(_QWORD *)&v34.Length = 33423360;
  v34.Buffer = (wchar_t *)v39;
  WPP_RECORDER_SF_Lq(v8, v7, v9, 27, v25, *(_DWORD *)(a1 + 1872), a1);
  VmsUtilLockExclusive(v10, &v31);
  LOBYTE(v11) = 1;
  VmsOmObjectLockExclusive(a1, &LockState, v11);
  RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a1 + 72));
  RtlCopyUnicodeString(&v34, (PCUNICODE_STRING)(a1 + 616));
  v15 = *(_DWORD *)(a1 + 68);
  if ( v15 == 2 || *(_BYTE *)(a1 + 4025) )
  {
    v32 = -1073741738;
    WPP_RECORDER_SF_Ll(v15, v12, v13, v14, v25, v15, *(_BYTE *)(a1 + 4025));
    v33 = 1;
    local_unwind_0(v37, &loc_1400FF536);
  }
  else
  {
    if ( *(_BYTE *)(a1 + 1876) == 1 && !VmsIsUnloadForServicing )
    {
      LOBYTE(v12) = 8;
      v6 = VmsOmObjectPrepareForConfigStore(a1, v12, 2);
    }
    *(_DWORD *)(a1 + 68) = 2;
    *(_BYTE *)(a1 + 4025) = 1;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
    NdisReleaseRWLock(VmsOmObjectListLock, &v31);
    if ( *(_DWORD *)(a1 + 1872) == 1 && !VmsIsUnloadForServicing )
      VmsOmMarkObjectConfigDeletion(0, 0, a1 + 72);
    while ( *(_BYTE *)(a1 + 4024) )
      NdisMSleep(0x2710u);
    VmsOmpWaitForVFsToBeRevoked(a1);
    if ( *(_DWORD *)(a1 + 1880) == 1 )
      VmsOmNicPvtDisconnect(a1);
    VmsQueueGroupUninitialize((void *)(a1 + 5696));
    VmsVrssUninitializeRssConfig((void *)(a1 + 5496), (void *)(a1 + 4924));
    VmsOmObjectLockExclusive(a1, &LockState, 0);
    *(_QWORD *)(a1 + 3288) = a3;
    *(_QWORD *)(a1 + 3296) = a2;
    *(_BYTE *)(a1 + 4025) = 0;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
    if ( v6 == 1 )
      VmsOmNicStoreConfig(a1, (const UNICODE_STRING *)(a1 + 72), 8);
    v19 = *(void (__fastcall **)(__int64, _QWORD))(a1 + 3328);
    if ( v19 )
      v19(a1, *(_QWORD *)(a1 + 3312));
  }
  v20 = v36;
  if ( v32 )
  {
    v29 = v36 + 1816;
    v28 = &v34;
    p_DestinationString = &DestinationString;
    LODWORD(v26) = 8;
    LODWORD(v25) = v33;
    VmsEtwTraceNicOperationFailure(v17, v16, v18, &v32);
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_qZd(
      VmsIfrNicLog,
      v22,
      20,
      29,
      (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
      v20,
      v20 + 616,
      v32);
  }
  else
  {
    VmsEtwTraceNicOperationSuccess(v17, v16, v18, 8, (__int64)&DestinationString, (__int64)&v34, v36 + 1816);
    LOBYTE(v21) = -1;
    VmsOmpObjectDereference(v20, v21);
  }
  return v32;
}

```

## disassembly

```asm
0x1400ff28c  push    rbx
0x1400ff28e  push    rsi
0x1400ff28f  push    rdi
0x1400ff290  push    r12
0x1400ff292  push    r14
0x1400ff294  push    r15
0x1400ff296  sub     rsp, 3A8h
0x1400ff29d  mov     rax, cs:__security_cookie
0x1400ff2a4  xor     rax, rsp
0x1400ff2a7  mov     [rsp+3D8h+var_48], rax
0x1400ff2af  mov     [rsp+3D8h+var_350], rsp
0x1400ff2b7  mov     r15, r8
0x1400ff2ba  mov     r12, rdx
0x1400ff2bd  mov     rbx, rcx
0x1400ff2c0  mov     [rsp+3D8h+var_358], rcx
0x1400ff2c8  xor     edi, edi
0x1400ff2ca  mov     [rsp+3D8h+var_380], edi
0x1400ff2ce  xor     eax, eax
0x1400ff2d0  mov     word ptr [rsp+3D8h+var_384.OldIrql], ax
0x1400ff2d5  mov     [rsp+3D8h+var_384.Flags], al
0x1400ff2d9  mov     word ptr [rsp+3D8h+LockState.OldIrql], ax
0x1400ff2de  mov     [rsp+3D8h+LockState.Flags], al
0x1400ff2e2  mov     r14b, dil
0x1400ff2e5  mov     [rsp+3D8h+var_37C], edi
0x1400ff2e9  xor     edx, edx; Val
0x1400ff2eb  mov     r8d, 0FEh; Size
0x1400ff2f1  lea     rcx, [rsp+3D8h+var_348]; void *
0x1400ff2f9  call    memset
0x1400ff2fe  mov     qword ptr [rsp+3D8h+DestinationString.Length], 0FE0000h
0x1400ff307  lea     rax, [rsp+3D8h+var_348]
0x1400ff30f  mov     [rsp+3D8h+DestinationString.Buffer], rax
0x1400ff314  xor     edx, edx; Val
0x1400ff316  mov     r8d, 1FEh; Size
0x1400ff31c  lea     rcx, [rsp+3D8h+var_248]; void *
0x1400ff324  call    memset
0x1400ff329  mov     qword ptr [rsp+3D8h+var_378.Length], 1FE0000h
0x1400ff332  lea     rax, [rsp+3D8h+var_248]
0x1400ff33a  mov     [rsp+3D8h+var_378.Buffer], rax
0x1400ff33f  lea     r9d, [rdi+1Bh]
0x1400ff343  mov     [rsp+3D8h+var_3A8], rbx
0x1400ff348  mov     eax, [rbx+750h]
0x1400ff34e  mov     dword ptr [rsp+3D8h+var_3B0], eax
0x1400ff352  call    WPP_RECORDER_SF_Lq
0x1400ff357  nop
0x1400ff358  lea     rdx, [rsp+3D8h+var_384]
0x1400ff35d  call    VmsUtilLockExclusive
0x1400ff362  nop
0x1400ff363  mov     r8b, 1
0x1400ff366  lea     rdx, [rsp+3D8h+LockState]
0x1400ff36b  mov     rcx, rbx
0x1400ff36e  call    VmsOmObjectLockExclusive
0x1400ff373  lea     rsi, [rbx+48h]
0x1400ff377  mov     rdx, rsi; SourceString
0x1400ff37a  lea     rcx, [rsp+3D8h+DestinationString]; DestinationString
0x1400ff37f  call    cs:__imp_RtlCopyUnicodeString
0x1400ff386  nop     dword ptr [rax+rax+00h]
0x1400ff38b  lea     rdx, [rbx+268h]; SourceString
0x1400ff392  lea     rcx, [rsp+3D8h+var_378]; DestinationString
0x1400ff397  call    cs:__imp_RtlCopyUnicodeString
0x1400ff39e  nop     dword ptr [rax+rax+00h]
0x1400ff3a3  mov     ecx, [rbx+44h]
0x1400ff3a6  cmp     ecx, 2
0x1400ff3a9  jz      loc_1400FF4FC
0x1400ff3af  cmp     [rbx+0FB9h], dil
0x1400ff3b6  jnz     loc_1400FF4FC
0x1400ff3bc  cmp     byte ptr [rbx+754h], 1
0x1400ff3c3  jnz     short loc_1400FF3E0
0x1400ff3c5  mov     al, cs:VmsIsUnloadForServicing
0x1400ff3cb  test    al, al
0x1400ff3cd  jnz     short loc_1400FF3E0
0x1400ff3cf  lea     r8d, [rdi+2]
0x1400ff3d3  mov     dl, 8
0x1400ff3d5  mov     rcx, rbx
0x1400ff3d8  call    VmsOmObjectPrepareForConfigStore
0x1400ff3dd  mov     r14b, al
0x1400ff3e0  mov     dword ptr [rbx+44h], 2
0x1400ff3e7  mov     byte ptr [rbx+0FB9h], 1
0x1400ff3ee  lea     rdx, [rsp+3D8h+LockState]; LockState
0x1400ff3f3  mov     rcx, [rbx+38h]; Lock
0x1400ff3f7  call    cs:__imp_NdisReleaseRWLock
0x1400ff3fe  nop     dword ptr [rax+rax+00h]
0x1400ff403  nop
0x1400ff404  lea     rdx, [rsp+3D8h+var_384]; LockState
0x1400ff409  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1400ff410  call    cs:__imp_NdisReleaseRWLock
0x1400ff417  nop     dword ptr [rax+rax+00h]
0x1400ff41c  cmp     dword ptr [rbx+750h], 1
0x1400ff423  jnz     short loc_1400FF44D
0x1400ff425  cmp     cs:VmsIsUnloadForServicing, 0
0x1400ff42c  jnz     short loc_1400FF44D
0x1400ff42e  mov     r8, rsi
0x1400ff431  xor     edx, edx
0x1400ff433  xor     ecx, ecx
0x1400ff435  call    VmsOmMarkObjectConfigDeletion
0x1400ff43a  jmp     short loc_1400FF44D
0x1400ff43c  mov     ecx, 2710h; MicrosecondsToSleep
0x1400ff441  call    cs:__imp_NdisMSleep
0x1400ff448  nop     dword ptr [rax+rax+00h]
0x1400ff44d  cmp     [rbx+0FB8h], dil
0x1400ff454  jnz     short loc_1400FF43C
0x1400ff456  mov     rcx, rbx
0x1400ff459  call    VmsOmpWaitForVFsToBeRevoked
0x1400ff45e  cmp     dword ptr [rbx+758h], 1
0x1400ff465  jnz     short loc_1400FF46F
0x1400ff467  mov     rcx, rbx; int
0x1400ff46a  call    VmsOmNicPvtDisconnect
0x1400ff46f  lea     rcx, [rbx+1640h]; void *
0x1400ff476  call    VmsQueueGroupUninitialize
0x1400ff47b  lea     rdx, [rbx+133Ch]; void *
0x1400ff482  lea     rcx, [rbx+1578h]; void *
0x1400ff489  call    VmsVrssUninitializeRssConfig
0x1400ff48e  xor     r8d, r8d
0x1400ff491  lea     rdx, [rsp+3D8h+LockState]
0x1400ff496  mov     rcx, rbx
0x1400ff499  call    VmsOmObjectLockExclusive
0x1400ff49e  mov     [rbx+0CD8h], r15
0x1400ff4a5  mov     [rbx+0CE0h], r12
0x1400ff4ac  mov     [rbx+0FB9h], dil
0x1400ff4b3  lea     rdx, [rsp+3D8h+LockState]; LockState
0x1400ff4b8  mov     rcx, [rbx+38h]; Lock
0x1400ff4bc  call    cs:__imp_NdisReleaseRWLock
0x1400ff4c3  nop     dword ptr [rax+rax+00h]
0x1400ff4c8  cmp     r14b, 1
0x1400ff4cc  jnz     short loc_1400FF4DF
0x1400ff4ce  mov     r8d, 8
0x1400ff4d4  mov     rdx, rsi
0x1400ff4d7  mov     rcx, rbx
0x1400ff4da  call    VmsOmNicStoreConfig
0x1400ff4df  mov     rax, [rbx+0D00h]
0x1400ff4e6  test    rax, rax
0x1400ff4e9  jz      short loc_1400FF536
0x1400ff4eb  mov     rdx, [rbx+0CF0h]
0x1400ff4f2  mov     rcx, rbx
0x1400ff4f5  call    _guard_dispatch_icall
0x1400ff4fa  jmp     short loc_1400FF536
0x1400ff4fc  mov     [rsp+3D8h+var_380], 0C0000056h
0x1400ff504  movzx   eax, byte ptr [rbx+0FB9h]
0x1400ff50b  mov     dword ptr [rsp+3D8h+var_3A8], eax
0x1400ff50f  mov     dword ptr [rsp+3D8h+var_3B0], ecx
0x1400ff513  call    WPP_RECORDER_SF_Ll
0x1400ff518  mov     [rsp+3D8h+var_37C], 1
0x1400ff520  lea     rdx, loc_1400FF536
0x1400ff527  mov     rcx, [rsp+3D8h+var_350]
0x1400ff52f  call    _local_unwind_0
0x1400ff534  nop
0x1400ff535  nop
0x1400ff536  mov     rbx, [rsp+3D8h+var_358]
0x1400ff53e  lea     rax, [rbx+718h]
0x1400ff545  xor     edi, edi
0x1400ff547  cmp     [rsp+3D8h+var_380], edi
0x1400ff54b  jnz     short loc_1400FF57B
0x1400ff54d  mov     [rsp+3D8h+var_3A8], rax
0x1400ff552  lea     rax, [rsp+3D8h+var_378]
0x1400ff557  mov     [rsp+3D8h+var_3B0], rax
0x1400ff55c  lea     rax, [rsp+3D8h+DestinationString]
0x1400ff561  mov     [rsp+3D8h+var_3B8], rax
0x1400ff566  lea     r9d, [rdi+8]
0x1400ff56a  call    VmsEtwTraceNicOperationSuccess
0x1400ff56f  mov     dl, 0FFh
0x1400ff571  mov     rcx, rbx
0x1400ff574  call    VmsOmpObjectDereference
0x1400ff579  jmp     short loc_1400FF5EB
0x1400ff57b  mov     [rsp+3D8h+var_398], rax
0x1400ff580  lea     rax, [rsp+3D8h+var_378]
0x1400ff585  mov     [rsp+3D8h+var_3A0], rax
0x1400ff58a  lea     rax, [rsp+3D8h+DestinationString]
0x1400ff58f  mov     [rsp+3D8h+var_3A8], rax
0x1400ff594  mov     dword ptr [rsp+3D8h+var_3B0], 8
0x1400ff59c  mov     eax, [rsp+3D8h+var_37C]
0x1400ff5a0  mov     dword ptr [rsp+3D8h+var_3B8], eax
0x1400ff5a4  lea     r9, [rsp+3D8h+var_380]
0x1400ff5a9  call    VmsEtwTraceNicOperationFailure
0x1400ff5ae  lea     rcx, [rbx+268h]
0x1400ff5b5  mov     r9d, 1Dh
0x1400ff5bb  mov     eax, [rsp+3D8h+var_380]
0x1400ff5bf  mov     dword ptr [rsp+3D8h+var_3A0], eax
0x1400ff5c3  mov     [rsp+3D8h+var_3A8], rcx
0x1400ff5c8  mov     [rsp+3D8h+var_3B0], rbx
0x1400ff5cd  lea     rax, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x1400ff5d4  mov     [rsp+3D8h+var_3B8], rax
0x1400ff5d9  lea     r8d, [r9-9]
0x1400ff5dd  mov     dl, 2
0x1400ff5df  mov     rcx, cs:VmsIfrNicLog
0x1400ff5e6  call    WPP_RECORDER_SF_qZd
0x1400ff5eb  mov     eax, [rsp+3D8h+var_380]
0x1400ff5ef  mov     rcx, [rsp+3D8h+var_48]
0x1400ff5f7  xor     rcx, rsp; StackCookie
0x1400ff5fa  call    __security_check_cookie
0x1400ff5ff  add     rsp, 3A8h
0x1400ff606  pop     r15
0x1400ff608  pop     r14
0x1400ff60a  pop     r12
0x1400ff60c  pop     rdi
0x1400ff60d  pop     rsi
0x1400ff60e  pop     rbx
0x1400ff60f  retn
0x1401bccae  push    rbp
0x1401bccb0  sub     rsp, 50h
0x1401bccb4  mov     rbp, rdx
0x1401bccb7  lea     rdx, [rbp+50h]; LockState
0x1401bccbb  mov     rcx, [rbp+80h]
0x1401bccc2  mov     rcx, [rcx+38h]; Lock
0x1401bccc6  call    cs:__imp_NdisReleaseRWLock
0x1401bcccd  nop     dword ptr [rax+rax+00h]
0x1401bccd2  nop
0x1401bccd3  add     rsp, 50h
0x1401bccd7  pop     rbp
0x1401bccd8  retn
0x1401bccda  push    rbp
0x1401bccdc  sub     rsp, 50h
0x1401bcce0  mov     rbp, rdx
0x1401bcce3  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1401bccea  lea     rdx, [rbp+54h]; LockState
0x1401bccee  call    cs:__imp_NdisReleaseRWLock
0x1401bccf5  nop     dword ptr [rax+rax+00h]
0x1401bccfa  nop
0x1401bccfb  add     rsp, 50h
0x1401bccff  pop     rbp
0x1401bcd00  retn
```
