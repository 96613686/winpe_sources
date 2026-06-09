# VmsOmNicDelete

- ea: `0x1400ff21c`
- end: `0x1400ff5a1`
- name: `VmsOmNicDelete`
- size: `901`
- prototype: ``
- caller_count: `8`
- callee_count: `20`
- tags: `registry_config, installer_update`

## callers

- `0x1400a9560`
- `0x1400f54cc`
- `0x1400f610c`
- `0x1400f672c`
- `0x1400fb810`
- `0x1400fc724`
- `0x140117f40`
- `0x140122500`

## callees

- `0x14001484c`
- `0x14002d318`
- `0x14002d86c`
- `0x14006b084`
- `0x14006ec68`
- `0x14006f844`
- `0x1400764b4`
- `0x1400a832c`
- `0x1400ff21c`
- `0x14010177c`
- `0x140104158`
- `0x140104f40`
- `0x1401064dc`
- `0x140106848`
- `0x140106f38`
- `0x1401aff3c`
- `0x1401bbb64`
- `0x1401bbc40`
- `0x1401bbe10`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ff30f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ff327`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ff30f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ff327`
- `NDIS!NdisMSleep` at `0x1400ff3d1`
- `NDIS!NdisMSleep` at `0x1400ff3d1`
- `NDIS!NdisReleaseRWLock` at `0x1400ff387`
- `NDIS!NdisReleaseRWLock` at `0x1400ff3a0`
- `NDIS!NdisReleaseRWLock` at `0x1400ff44c`
- `NDIS!NdisReleaseRWLock` at `0x1401bcc46`
- `NDIS!NdisReleaseRWLock` at `0x1401bcc6e`
- `NDIS!NdisReleaseRWLock` at `0x1400ff387`
- `NDIS!NdisReleaseRWLock` at `0x1400ff3a0`
- `NDIS!NdisReleaseRWLock` at `0x1400ff44c`
- `NDIS!NdisReleaseRWLock` at `0x1401bcc46`
- `NDIS!NdisReleaseRWLock` at `0x1401bcc6e`

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
    local_unwind_0(v37, &loc_1400FF4C6);
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
0x1400ff21c  push    rbx
0x1400ff21e  push    rsi
0x1400ff21f  push    rdi
0x1400ff220  push    r12
0x1400ff222  push    r14
0x1400ff224  push    r15
0x1400ff226  sub     rsp, 3A8h
0x1400ff22d  mov     rax, cs:__security_cookie
0x1400ff234  xor     rax, rsp
0x1400ff237  mov     [rsp+3D8h+var_48], rax
0x1400ff23f  mov     [rsp+3D8h+var_350], rsp
0x1400ff247  mov     r15, r8
0x1400ff24a  mov     r12, rdx
0x1400ff24d  mov     rbx, rcx
0x1400ff250  mov     [rsp+3D8h+var_358], rcx
0x1400ff258  xor     edi, edi
0x1400ff25a  mov     [rsp+3D8h+var_380], edi
0x1400ff25e  xor     eax, eax
0x1400ff260  mov     word ptr [rsp+3D8h+var_384.OldIrql], ax
0x1400ff265  mov     [rsp+3D8h+var_384.Flags], al
0x1400ff269  mov     word ptr [rsp+3D8h+LockState.OldIrql], ax
0x1400ff26e  mov     [rsp+3D8h+LockState.Flags], al
0x1400ff272  mov     r14b, dil
0x1400ff275  mov     [rsp+3D8h+var_37C], edi
0x1400ff279  xor     edx, edx; Val
0x1400ff27b  mov     r8d, 0FEh; Size
0x1400ff281  lea     rcx, [rsp+3D8h+var_348]; void *
0x1400ff289  call    memset
0x1400ff28e  mov     qword ptr [rsp+3D8h+DestinationString.Length], 0FE0000h
0x1400ff297  lea     rax, [rsp+3D8h+var_348]
0x1400ff29f  mov     [rsp+3D8h+DestinationString.Buffer], rax
0x1400ff2a4  xor     edx, edx; Val
0x1400ff2a6  mov     r8d, 1FEh; Size
0x1400ff2ac  lea     rcx, [rsp+3D8h+var_248]; void *
0x1400ff2b4  call    memset
0x1400ff2b9  mov     qword ptr [rsp+3D8h+var_378.Length], 1FE0000h
0x1400ff2c2  lea     rax, [rsp+3D8h+var_248]
0x1400ff2ca  mov     [rsp+3D8h+var_378.Buffer], rax
0x1400ff2cf  lea     r9d, [rdi+1Bh]
0x1400ff2d3  mov     [rsp+3D8h+var_3A8], rbx
0x1400ff2d8  mov     eax, [rbx+750h]
0x1400ff2de  mov     dword ptr [rsp+3D8h+var_3B0], eax
0x1400ff2e2  call    WPP_RECORDER_SF_Lq
0x1400ff2e7  nop
0x1400ff2e8  lea     rdx, [rsp+3D8h+var_384]
0x1400ff2ed  call    VmsUtilLockExclusive
0x1400ff2f2  nop
0x1400ff2f3  mov     r8b, 1
0x1400ff2f6  lea     rdx, [rsp+3D8h+LockState]
0x1400ff2fb  mov     rcx, rbx
0x1400ff2fe  call    VmsOmObjectLockExclusive
0x1400ff303  lea     rsi, [rbx+48h]
0x1400ff307  mov     rdx, rsi; SourceString
0x1400ff30a  lea     rcx, [rsp+3D8h+DestinationString]; DestinationString
0x1400ff30f  call    cs:__imp_RtlCopyUnicodeString
0x1400ff316  nop     dword ptr [rax+rax+00h]
0x1400ff31b  lea     rdx, [rbx+268h]; SourceString
0x1400ff322  lea     rcx, [rsp+3D8h+var_378]; DestinationString
0x1400ff327  call    cs:__imp_RtlCopyUnicodeString
0x1400ff32e  nop     dword ptr [rax+rax+00h]
0x1400ff333  mov     ecx, [rbx+44h]
0x1400ff336  cmp     ecx, 2
0x1400ff339  jz      loc_1400FF48C
0x1400ff33f  cmp     [rbx+0FB9h], dil
0x1400ff346  jnz     loc_1400FF48C
0x1400ff34c  cmp     byte ptr [rbx+754h], 1
0x1400ff353  jnz     short loc_1400FF370
0x1400ff355  mov     al, cs:VmsIsUnloadForServicing
0x1400ff35b  test    al, al
0x1400ff35d  jnz     short loc_1400FF370
0x1400ff35f  lea     r8d, [rdi+2]
0x1400ff363  mov     dl, 8
0x1400ff365  mov     rcx, rbx
0x1400ff368  call    VmsOmObjectPrepareForConfigStore
0x1400ff36d  mov     r14b, al
0x1400ff370  mov     dword ptr [rbx+44h], 2
0x1400ff377  mov     byte ptr [rbx+0FB9h], 1
0x1400ff37e  lea     rdx, [rsp+3D8h+LockState]; LockState
0x1400ff383  mov     rcx, [rbx+38h]; Lock
0x1400ff387  call    cs:__imp_NdisReleaseRWLock
0x1400ff38e  nop     dword ptr [rax+rax+00h]
0x1400ff393  nop
0x1400ff394  lea     rdx, [rsp+3D8h+var_384]; LockState
0x1400ff399  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1400ff3a0  call    cs:__imp_NdisReleaseRWLock
0x1400ff3a7  nop     dword ptr [rax+rax+00h]
0x1400ff3ac  cmp     dword ptr [rbx+750h], 1
0x1400ff3b3  jnz     short loc_1400FF3DD
0x1400ff3b5  cmp     cs:VmsIsUnloadForServicing, 0
0x1400ff3bc  jnz     short loc_1400FF3DD
0x1400ff3be  mov     r8, rsi
0x1400ff3c1  xor     edx, edx
0x1400ff3c3  xor     ecx, ecx
0x1400ff3c5  call    VmsOmMarkObjectConfigDeletion
0x1400ff3ca  jmp     short loc_1400FF3DD
0x1400ff3cc  mov     ecx, 2710h; MicrosecondsToSleep
0x1400ff3d1  call    cs:__imp_NdisMSleep
0x1400ff3d8  nop     dword ptr [rax+rax+00h]
0x1400ff3dd  cmp     [rbx+0FB8h], dil
0x1400ff3e4  jnz     short loc_1400FF3CC
0x1400ff3e6  mov     rcx, rbx
0x1400ff3e9  call    VmsOmpWaitForVFsToBeRevoked
0x1400ff3ee  cmp     dword ptr [rbx+758h], 1
0x1400ff3f5  jnz     short loc_1400FF3FF
0x1400ff3f7  mov     rcx, rbx; int
0x1400ff3fa  call    VmsOmNicPvtDisconnect
0x1400ff3ff  lea     rcx, [rbx+1640h]; void *
0x1400ff406  call    VmsQueueGroupUninitialize
0x1400ff40b  lea     rdx, [rbx+133Ch]; void *
0x1400ff412  lea     rcx, [rbx+1578h]; void *
0x1400ff419  call    VmsVrssUninitializeRssConfig
0x1400ff41e  xor     r8d, r8d
0x1400ff421  lea     rdx, [rsp+3D8h+LockState]
0x1400ff426  mov     rcx, rbx
0x1400ff429  call    VmsOmObjectLockExclusive
0x1400ff42e  mov     [rbx+0CD8h], r15
0x1400ff435  mov     [rbx+0CE0h], r12
0x1400ff43c  mov     [rbx+0FB9h], dil
0x1400ff443  lea     rdx, [rsp+3D8h+LockState]; LockState
0x1400ff448  mov     rcx, [rbx+38h]; Lock
0x1400ff44c  call    cs:__imp_NdisReleaseRWLock
0x1400ff453  nop     dword ptr [rax+rax+00h]
0x1400ff458  cmp     r14b, 1
0x1400ff45c  jnz     short loc_1400FF46F
0x1400ff45e  mov     r8d, 8
0x1400ff464  mov     rdx, rsi
0x1400ff467  mov     rcx, rbx
0x1400ff46a  call    VmsOmNicStoreConfig
0x1400ff46f  mov     rax, [rbx+0D00h]
0x1400ff476  test    rax, rax
0x1400ff479  jz      short loc_1400FF4C6
0x1400ff47b  mov     rdx, [rbx+0CF0h]
0x1400ff482  mov     rcx, rbx
0x1400ff485  call    _guard_dispatch_icall
0x1400ff48a  jmp     short loc_1400FF4C6
0x1400ff48c  mov     [rsp+3D8h+var_380], 0C0000056h
0x1400ff494  movzx   eax, byte ptr [rbx+0FB9h]
0x1400ff49b  mov     dword ptr [rsp+3D8h+var_3A8], eax
0x1400ff49f  mov     dword ptr [rsp+3D8h+var_3B0], ecx
0x1400ff4a3  call    WPP_RECORDER_SF_Ll
0x1400ff4a8  mov     [rsp+3D8h+var_37C], 1
0x1400ff4b0  lea     rdx, loc_1400FF4C6
0x1400ff4b7  mov     rcx, [rsp+3D8h+var_350]
0x1400ff4bf  call    _local_unwind_0
0x1400ff4c4  nop
0x1400ff4c5  nop
0x1400ff4c6  mov     rbx, [rsp+3D8h+var_358]
0x1400ff4ce  lea     rax, [rbx+718h]
0x1400ff4d5  xor     edi, edi
0x1400ff4d7  cmp     [rsp+3D8h+var_380], edi
0x1400ff4db  jnz     short loc_1400FF50B
0x1400ff4dd  mov     [rsp+3D8h+var_3A8], rax
0x1400ff4e2  lea     rax, [rsp+3D8h+var_378]
0x1400ff4e7  mov     [rsp+3D8h+var_3B0], rax
0x1400ff4ec  lea     rax, [rsp+3D8h+DestinationString]
0x1400ff4f1  mov     [rsp+3D8h+var_3B8], rax
0x1400ff4f6  lea     r9d, [rdi+8]
0x1400ff4fa  call    VmsEtwTraceNicOperationSuccess
0x1400ff4ff  mov     dl, 0FFh
0x1400ff501  mov     rcx, rbx
0x1400ff504  call    VmsOmpObjectDereference
0x1400ff509  jmp     short loc_1400FF57B
0x1400ff50b  mov     [rsp+3D8h+var_398], rax
0x1400ff510  lea     rax, [rsp+3D8h+var_378]
0x1400ff515  mov     [rsp+3D8h+var_3A0], rax
0x1400ff51a  lea     rax, [rsp+3D8h+DestinationString]
0x1400ff51f  mov     [rsp+3D8h+var_3A8], rax
0x1400ff524  mov     dword ptr [rsp+3D8h+var_3B0], 8
0x1400ff52c  mov     eax, [rsp+3D8h+var_37C]
0x1400ff530  mov     dword ptr [rsp+3D8h+var_3B8], eax
0x1400ff534  lea     r9, [rsp+3D8h+var_380]
0x1400ff539  call    VmsEtwTraceNicOperationFailure
0x1400ff53e  lea     rcx, [rbx+268h]
0x1400ff545  mov     r9d, 1Dh
0x1400ff54b  mov     eax, [rsp+3D8h+var_380]
0x1400ff54f  mov     dword ptr [rsp+3D8h+var_3A0], eax
0x1400ff553  mov     [rsp+3D8h+var_3A8], rcx
0x1400ff558  mov     [rsp+3D8h+var_3B0], rbx
0x1400ff55d  lea     rax, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x1400ff564  mov     [rsp+3D8h+var_3B8], rax
0x1400ff569  lea     r8d, [r9-9]
0x1400ff56d  mov     dl, 2
0x1400ff56f  mov     rcx, cs:VmsIfrNicLog
0x1400ff576  call    WPP_RECORDER_SF_qZd
0x1400ff57b  mov     eax, [rsp+3D8h+var_380]
0x1400ff57f  mov     rcx, [rsp+3D8h+var_48]
0x1400ff587  xor     rcx, rsp; StackCookie
0x1400ff58a  call    __security_check_cookie
0x1400ff58f  add     rsp, 3A8h
0x1400ff596  pop     r15
0x1400ff598  pop     r14
0x1400ff59a  pop     r12
0x1400ff59c  pop     rdi
0x1400ff59d  pop     rsi
0x1400ff59e  pop     rbx
0x1400ff59f  retn
0x1401bcc2e  push    rbp
0x1401bcc30  sub     rsp, 50h
0x1401bcc34  mov     rbp, rdx
0x1401bcc37  lea     rdx, [rbp+50h]; LockState
0x1401bcc3b  mov     rcx, [rbp+80h]
0x1401bcc42  mov     rcx, [rcx+38h]; Lock
0x1401bcc46  call    cs:__imp_NdisReleaseRWLock
0x1401bcc4d  nop     dword ptr [rax+rax+00h]
0x1401bcc52  nop
0x1401bcc53  add     rsp, 50h
0x1401bcc57  pop     rbp
0x1401bcc58  retn
0x1401bcc5a  push    rbp
0x1401bcc5c  sub     rsp, 50h
0x1401bcc60  mov     rbp, rdx
0x1401bcc63  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1401bcc6a  lea     rdx, [rbp+54h]; LockState
0x1401bcc6e  call    cs:__imp_NdisReleaseRWLock
0x1401bcc75  nop     dword ptr [rax+rax+00h]
0x1401bcc7a  nop
0x1401bcc7b  add     rsp, 50h
0x1401bcc7f  pop     rbp
0x1401bcc80  retn
```
