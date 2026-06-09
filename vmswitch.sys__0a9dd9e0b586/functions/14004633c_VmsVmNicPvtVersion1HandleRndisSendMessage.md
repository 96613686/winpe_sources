# VmsVmNicPvtVersion1HandleRndisSendMessage

- ea: `0x14004633c`
- end: `0x140046897`
- name: `VmsVmNicPvtVersion1HandleRndisSendMessage`
- size: `1371`
- prototype: `_QWORD *__fastcall(__int64, _DWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400452e0`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x14003a450`
- `0x14004633c`
- `0x1400468a0`
- `0x140046e5c`
- `0x140049500`
- `0x14006c010`
- `0x14006d980`
- `0x14008497c`
- `0x1401a3550`
- `0x1401bbcb0`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004666d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140046696`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004666d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140046696`
- `NDIS!NdisAcquireRWLockRead` at `0x1400463c1`
- `NDIS!NdisAcquireRWLockRead` at `0x1400463c1`
- `NDIS!NdisReleaseRWLock` at `0x140046474`
- `NDIS!NdisReleaseRWLock` at `0x140046541`
- `NDIS!NdisReleaseRWLock` at `0x140046474`
- `NDIS!NdisReleaseRWLock` at `0x140046541`
- `vmbkmclr!VmbChannelPacketGetClientContext` at `0x140046376`
- `vmbkmclr!VmbChannelPacketGetClientContext` at `0x140046376`
- `vmbkmclr!VmbChannelPacketComplete` at `0x1400465a0`
- `vmbkmclr!VmbChannelPacketComplete` at `0x1400465a0`

## pseudocode

```c
_QWORD *__fastcall VmsVmNicPvtVersion1HandleRndisSendMessage(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r14
  __int64 ClientContext; // rax
  int v9; // edx
  __int64 v10; // r9
  __int64 v11; // rdi
  __int64 v12; // rsi
  int v13; // edx
  __int64 v14; // r9
  unsigned int v15; // edx
  __int64 v16; // rbx
  bool v17; // zf
  bool v18; // al
  _QWORD *result; // rax
  bool v20; // cf
  int v21; // edx
  int v22; // ecx
  int v23; // r8d
  __int64 v24; // r8
  __int64 v25; // r12
  int v26; // eax
  PVOID v27; // rbx
  PVOID v28; // r13
  unsigned int v29; // ebx
  int v30; // edx
  int v31; // edx
  int v32; // edx
  int v33; // r9d
  int v34; // eax
  int BugCheckOnFailure; // [rsp+20h] [rbp-C8h]
  int v36; // [rsp+30h] [rbp-B8h]
  char v37; // [rsp+50h] [rbp-98h]
  struct _LOCK_STATE_EX LockState; // [rsp+54h] [rbp-94h] BYREF
  void *Src; // [rsp+58h] [rbp-90h]
  __int64 v40; // [rsp+60h] [rbp-88h]
  _DWORD v41[2]; // [rsp+68h] [rbp-80h] BYREF
  __int128 v42; // [rsp+70h] [rbp-78h]
  __int128 v43; // [rsp+80h] [rbp-68h]

  v40 = a4;
  v5 = a4;
  ClientContext = VmbChannelPacketGetClientContext(a4);
  v11 = *(_QWORD *)(a1 + 8);
  v12 = ClientContext;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v37 = *(_BYTE *)(*(_QWORD *)(v11 + 680) + 1877LL);
  if ( a2[2] != -1 )
  {
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(v11 + 680) + 56LL), &LockState, 0);
    if ( *(_DWORD *)(v11 + 548) )
    {
      if ( *(_QWORD *)(v11 + 296) )
      {
        v15 = a2[2];
        if ( v15 >= *(_DWORD *)(v11 + 304) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrNicLog,
            v15,
            19,
            167,
            (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
            (__int64)"srpMessage->SendBufferSectionIndex < vmNicExt->SendBufferSectionMdlArrayLength");
          if ( a2[2] >= *(_DWORD *)(v11 + 304) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
          v33 = 168;
          v36 = *(_DWORD *)(v11 + 304);
          v34 = a2[2];
        }
        else
        {
          if ( a2[3] <= *(_DWORD *)(v11 + 576) )
          {
            if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(8LL * v15 + *(_QWORD *)(v11 + 1448)), 1, 0) )
            {
              LOBYTE(v14) = v37 == 0;
              v16 = *(_QWORD *)(*(_QWORD *)(v11 + 296) + 8LL * (unsigned int)a2[2]);
              *(_DWORD *)(v16 + 40) = a2[3];
              *(_QWORD *)v16 = a3;
              *(_DWORD *)(v12 + 64) = a2[2];
              *(_BYTE *)(v12 + 8) = 1;
              VmsVmNicShadowMessageIfNecessary(v11, v12, v16, v14);
              if ( !v37 && !*(_BYTE *)(v12 + 9) )
              {
                v25 = *(_QWORD *)(*(_QWORD *)(v11 + 328) + 8LL * (unsigned int)a2[2]);
                v26 = a2[3];
                *(_QWORD *)v25 = a3;
                *(_DWORD *)(v25 + 40) = v26;
                v27 = (*(_BYTE *)(v16 + 10) & 5) != 0
                    ? *(PVOID *)(v16 + 24)
                    : MmMapLockedPagesSpecifyCache((PMDL)v16, 0, MmCached, 0, 0, 0x40000000u);
                v17 = (*(_BYTE *)(v25 + 10) & 5) == 0;
                Src = v27;
                v28 = v17
                    ? MmMapLockedPagesSpecifyCache((PMDL)v25, 0, MmCached, 0, 0, 0x40000000u)
                    : *(PVOID *)(v25 + 24);
                if ( v27 && v28 )
                {
                  v29 = a2[3];
                  HviEnterKernelAperture();
                  memmove(v28, Src, v29);
                  HviLeaveKernelAperture();
                  *(_QWORD *)(v12 + 16) = v25;
                }
              }
              NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(v11 + 680) + 56LL), &LockState);
              goto LABEL_9;
            }
            LOBYTE(v15) = 2;
            WPP_RECORDER_SF_d(
              VmsIfrNicLog,
              v15,
              20,
              171,
              (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
              a2[2]);
            v5 = v40;
            goto LABEL_14;
          }
          WPP_RECORDER_SF_s(
            VmsIfrNicLog,
            v15,
            19,
            169,
            (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
            (__int64)"srpMessage->SendBufferSectionSize <= vmNicExt->Persistent.SendBufferSubAllocationSize");
          if ( a2[3] > *(_DWORD *)(v11 + 576) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
          v33 = 170;
          v36 = *(_DWORD *)(v11 + 576);
          v34 = a2[3];
        }
        LOBYTE(v32) = 2;
        WPP_RECORDER_SF_ld(
          VmsIfrNicLog,
          v32,
          20,
          v33,
          (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
          v34,
          v36);
      }
      else
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v13,
          19,
          165,
          (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
          (__int64)"vmNicExt->SendBufferSectionMdlArray != NULL");
        if ( !*(_QWORD *)(v11 + 296) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        LOBYTE(v31) = 2;
        WPP_RECORDER_SF_(VmsIfrNicLog, v31, 20, 166, (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids);
      }
    }
    else
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_(VmsIfrNicLog, v13, 20, 164, (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids);
    }
LABEL_14:
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(v11 + 680) + 56LL), &LockState);
LABEL_15:
    WPP_RECORDER_SF_qqqq(v22, v21, v23, 172, BugCheckOnFailure, a1, (char)a2, a3, v5);
    v24 = *(unsigned int *)(v11 + 704);
    v41[0] = 108;
    v41[1] = 5;
    v42 = 0;
    v43 = 0;
    return (_QWORD *)VmbChannelPacketComplete(v5, v41, v24);
  }
  if ( !a3 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrNicLog,
      v9,
      19,
      161,
      (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
      (__int64)"ExternalDataMdl != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    LOBYTE(v30) = 2;
    WPP_RECORDER_SF_(VmsIfrNicLog, v30, 20, 162, (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids);
    goto LABEL_15;
  }
  LOBYTE(v10) = v37 == 0;
  *(_BYTE *)(ClientContext + 8) = 0;
  VmsVmNicShadowMessageIfNecessary(v11, ClientContext, a3, v10);
  ++*(_QWORD *)(v11 + 272);
LABEL_9:
  _InterlockedAdd((volatile signed __int32 *)(v11 + 244), 1u);
  v17 = *(_BYTE *)(v12 + 9) == 0;
  *(_QWORD *)v12 = v40;
  *(_QWORD *)(v12 + 24) = *(_QWORD *)(v12 + 16);
  *(_DWORD *)(v12 + 36) = a2[1];
  *(_QWORD *)(v12 + 48) = v12 + 72;
  *(_DWORD *)(v12 + 40) = *(_DWORD *)(v11 + 252);
  v18 = !v17 && !*(_BYTE *)(v12 + 10);
  *(_BYTE *)(v12 + 32) = v18;
  *(_QWORD *)(v12 + 56) = 0;
  result = *(_QWORD **)(a1 + 48);
  *result = v12 + 24;
  v20 = ++*(_DWORD *)(a1 + 32) < 0x10u;
  *(_QWORD *)(a1 + 48) = v12 + 56;
  if ( !v20 )
    return (_QWORD *)VmsVmNicPvtKmclProcessingCompleteInternal(*(_QWORD *)a1);
  return result;
}

```

## disassembly

```asm
0x14004633c  push    rbx
0x14004633e  push    rbp
0x14004633f  push    rsi
0x140046340  push    rdi
0x140046341  push    r12
0x140046343  push    r13
0x140046345  push    r14
0x140046347  push    r15
0x140046349  sub     rsp, 0A8h
0x140046350  mov     rax, cs:__security_cookie
0x140046357  xor     rax, rsp
0x14004635a  mov     [rsp+0E8h+var_58], rax
0x140046362  mov     r15, rcx
0x140046365  mov     [rsp+0E8h+var_88], r9
0x14004636a  mov     rcx, r9
0x14004636d  mov     r14, r9
0x140046370  mov     r13, r8
0x140046373  mov     rbp, rdx
0x140046376  call    cs:__imp_VmbChannelPacketGetClientContext
0x14004637d  nop     dword ptr [rax+rax+00h]
0x140046382  mov     rdi, [r15+8]
0x140046386  mov     rsi, rax
0x140046389  xor     eax, eax
0x14004638b  mov     word ptr [rsp+0E8h+LockState.OldIrql], ax
0x140046390  mov     [rsp+0E8h+LockState.Flags], al
0x140046394  mov     rcx, [rdi+2A8h]
0x14004639b  mov     al, [rcx+755h]
0x1400463a1  test    al, al
0x1400463a3  mov     [rsp+0E8h+var_98], al
0x1400463a7  setz    r12b
0x1400463ab  cmp     dword ptr [rbp+8], 0FFFFFFFFh
0x1400463af  jz      loc_1400465B1
0x1400463b5  mov     rcx, [rcx+38h]; Lock
0x1400463b9  lea     rdx, [rsp+0E8h+LockState]; LockState
0x1400463be  xor     r8d, r8d; Flags
0x1400463c1  call    cs:__imp_NdisAcquireRWLockRead
0x1400463c8  nop     dword ptr [rax+rax+00h]
0x1400463cd  cmp     dword ptr [rdi+224h], 0
0x1400463d4  jz      loc_14004650B
0x1400463da  cmp     qword ptr [rdi+128h], 0
0x1400463e2  jz      loc_140046703
0x1400463e8  mov     edx, [rbp+8]
0x1400463eb  cmp     edx, [rdi+130h]
0x1400463f1  jnb     loc_140046766
0x1400463f7  mov     eax, [rdi+240h]
0x1400463fd  cmp     [rbp+0Ch], eax
0x140046400  ja      loc_1400467F5
0x140046406  mov     rcx, [rdi+5A8h]
0x14004640d  mov     eax, edx
0x14004640f  shl     rax, 3
0x140046413  add     rcx, rax
0x140046416  xor     eax, eax
0x140046418  lea     r14d, [rax+1]
0x14004641c  lock cmpxchg [rcx], r14
0x140046421  jnz     loc_140046832
0x140046427  mov     ecx, [rbp+8]
0x14004642a  mov     r9b, r12b
0x14004642d  mov     rax, [rdi+128h]
0x140046434  mov     rdx, rsi
0x140046437  mov     rbx, [rax+rcx*8]
0x14004643b  mov     rcx, rdi
0x14004643e  mov     eax, [rbp+0Ch]
0x140046441  mov     r8, rbx
0x140046444  mov     [rbx+28h], eax
0x140046447  mov     [rbx], r13
0x14004644a  mov     eax, [rbp+8]
0x14004644d  mov     [rsi+40h], eax
0x140046450  mov     [rsi+8], r14b
0x140046454  call    VmsVmNicShadowMessageIfNecessary
0x140046459  cmp     [rsp+0E8h+var_98], 0
0x14004645e  jz      loc_140046869
0x140046464  mov     rcx, [rdi+2A8h]
0x14004646b  lea     rdx, [rsp+0E8h+LockState]; LockState
0x140046470  mov     rcx, [rcx+38h]; Lock
0x140046474  call    cs:__imp_NdisReleaseRWLock
0x14004647b  nop     dword ptr [rax+rax+00h]
0x140046480  lock add [rdi+0F4h], r14d
0x140046488  cmp     byte ptr [rsi+9], 0
0x14004648c  lea     rdx, [rsi+18h]
0x140046490  mov     rax, [rsp+0E8h+var_88]
0x140046495  mov     [rsi], rax
0x140046498  mov     rax, [rsi+10h]
0x14004649c  mov     [rdx], rax
0x14004649f  mov     eax, [rbp+4]
0x1400464a2  mov     [rdx+0Ch], eax
0x1400464a5  lea     rax, [rsi+48h]
0x1400464a9  mov     [rdx+18h], rax
0x1400464ad  mov     eax, [rdi+0FCh]
0x1400464b3  mov     [rdx+10h], eax
0x1400464b6  jnz     loc_140046878
0x1400464bc  xor     al, al
0x1400464be  mov     [rdx+8], al
0x1400464c1  lea     rcx, [rdx+20h]
0x1400464c5  mov     qword ptr [rcx], 0
0x1400464cc  mov     rax, [r15+30h]
0x1400464d0  mov     [rax], rdx
0x1400464d3  add     [r15+20h], r14d
0x1400464d7  cmp     dword ptr [r15+20h], 10h
0x1400464dc  mov     [r15+30h], rcx
0x1400464e0  jnb     loc_14004688A
0x1400464e6  mov     rcx, [rsp+0E8h+var_58]
0x1400464ee  xor     rcx, rsp; StackCookie
0x1400464f1  call    __security_check_cookie
0x1400464f6  add     rsp, 0A8h
0x1400464fd  pop     r15
0x1400464ff  pop     r14
0x140046501  pop     r13
0x140046503  pop     r12
0x140046505  pop     rdi
0x140046506  pop     rsi
0x140046507  pop     rbp
0x140046508  pop     rbx
0x140046509  retn
0x14004650b  mov     rcx, cs:VmsIfrNicLog
0x140046512  lea     rbx, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x140046519  mov     r9d, 0A4h
0x14004651f  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rbx
0x140046524  mov     r8d, 14h
0x14004652a  mov     dl, 2
0x14004652c  call    WPP_RECORDER_SF_
0x140046531  mov     rcx, [rdi+2A8h]
0x140046538  lea     rdx, [rsp+0E8h+LockState]; LockState
0x14004653d  mov     rcx, [rcx+38h]; Lock
0x140046541  call    cs:__imp_NdisReleaseRWLock
0x140046548  nop     dword ptr [rax+rax+00h]
0x14004654d  mov     [rsp+0E8h+var_A8], r14
0x140046552  mov     r9d, 0ACh
0x140046558  mov     [rsp+0E8h+var_B0], r13
0x14004655d  mov     [rsp+0E8h+var_B8], rbp
0x140046562  mov     qword ptr [rsp+0E8h+Priority], r15
0x140046567  call    WPP_RECORDER_SF_qqqq
0x14004656c  mov     r8d, [rdi+2C0h]
0x140046573  lea     rdx, [rsp+0E8h+var_80]
0x140046578  xorps   xmm0, xmm0
0x14004657b  mov     [rsp+0E8h+var_80], 6Ch ; 'l'
0x140046583  xorps   xmm1, xmm1
0x140046586  mov     [rsp+0E8h+var_7C], 5
0x14004658e  mov     rcx, r14
0x140046591  movdqu  [rsp+0E8h+var_78], xmm0
0x140046597  movdqu  [rsp+0E8h+var_68], xmm1
0x1400465a0  call    cs:__imp_VmbChannelPacketComplete
0x1400465a7  nop     dword ptr [rax+rax+00h]
0x1400465ac  jmp     loc_1400464E6
0x1400465b1  test    r13, r13
0x1400465b4  jz      loc_1400466AA
0x1400465ba  mov     r9b, r12b
0x1400465bd  mov     byte ptr [rsi+8], 0
0x1400465c1  mov     r8, r13
0x1400465c4  mov     rdx, rsi
0x1400465c7  mov     rcx, rdi
0x1400465ca  call    VmsVmNicShadowMessageIfNecessary
0x1400465cf  mov     r14d, 1
0x1400465d5  add     [rdi+110h], r14
0x1400465dc  jmp     loc_140046480
0x1400465e1  mov     rax, [rdi+148h]
0x1400465e8  mov     ecx, [rbp+8]
0x1400465eb  mov     r12, [rax+rcx*8]
0x1400465ef  mov     eax, [rbp+0Ch]
0x1400465f2  mov     [r12], r13
0x1400465f6  mov     r13d, 40000000h
0x1400465fc  mov     [r12+28h], eax
0x140046601  test    byte ptr [rbx+0Ah], 5
0x140046605  jz      short loc_140046655
0x140046607  mov     rbx, [rbx+18h]
0x14004660b  test    byte ptr [r12+0Ah], 5
0x140046611  mov     [rsp+0E8h+Src], rbx
0x140046616  jz      short loc_14004667E
0x140046618  mov     r13, [r12+18h]
0x14004661d  test    rbx, rbx
0x140046620  jz      loc_140046464
0x140046626  test    r13, r13
0x140046629  jz      loc_140046464
0x14004662f  mov     ebx, [rbp+0Ch]
0x140046632  call    HviEnterKernelAperture
0x140046637  mov     rdx, [rsp+0E8h+Src]; Src
0x14004663c  mov     r8d, ebx; Size
0x14004663f  mov     rcx, r13; void *
0x140046642  call    memmove
0x140046647  call    HviLeaveKernelAperture
0x14004664c  mov     [rsi+10h], r12
0x140046650  jmp     loc_140046464
0x140046655  mov     [rsp+0E8h+Priority], r13d; Priority
0x14004665a  xor     r9d, r9d; RequestedAddress
0x14004665d  mov     r8d, r14d; CacheType
0x140046660  mov     [rsp+0E8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140046668  xor     edx, edx; AccessMode
0x14004666a  mov     rcx, rbx; MemoryDescriptorList
0x14004666d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140046674  nop     dword ptr [rax+rax+00h]
0x140046679  mov     rbx, rax
0x14004667c  jmp     short loc_14004660B
0x14004667e  mov     [rsp+0E8h+Priority], r13d; Priority
0x140046683  xor     r9d, r9d; RequestedAddress
0x140046686  mov     r8d, r14d; CacheType
0x140046689  mov     [rsp+0E8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140046691  xor     edx, edx; AccessMode
0x140046693  mov     rcx, r12; MemoryDescriptorList
0x140046696  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004669d  nop     dword ptr [rax+rax+00h]
0x1400466a2  mov     r13, rax
0x1400466a5  jmp     loc_14004661D
0x1400466aa  mov     rcx, cs:VmsIfrNicLog
0x1400466b1  lea     rax, aExternaldatamd; "ExternalDataMdl != NULL"
0x1400466b8  mov     qword ptr [rsp+0E8h+Priority], rax
0x1400466bd  lea     rbx, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x1400466c4  mov     r9d, 0A1h
0x1400466ca  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rbx
0x1400466cf  mov     r8d, 13h
0x1400466d5  call    WPP_RECORDER_SF_s
0x1400466da  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ExternalDataMdl != ((void *)0)")
0x1400466df  mov     rcx, cs:VmsIfrNicLog
0x1400466e6  mov     r9d, 0A2h
0x1400466ec  mov     r8d, 14h
0x1400466f2  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rbx
0x1400466f7  mov     dl, 2
0x1400466f9  call    WPP_RECORDER_SF_
0x1400466fe  jmp     loc_14004654D
0x140046703  mov     rcx, cs:VmsIfrNicLog
0x14004670a  lea     rax, aVmnicextSendbu; "vmNicExt->SendBufferSectionMdlArray != "...
0x140046711  mov     qword ptr [rsp+0E8h+Priority], rax
0x140046716  lea     rbx, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x14004671d  mov     r9d, 0A5h
0x140046723  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rbx
0x140046728  mov     r8d, 13h
0x14004672e  call    WPP_RECORDER_SF_s
0x140046733  cmp     qword ptr [rdi+128h], 0
0x14004673b  jnz     short loc_140046742
0x14004673d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "vmNicExt->SendBufferSectionMdlArray != ((void *)0)")
0x140046742  mov     rcx, cs:VmsIfrNicLog
0x140046749  mov     r9d, 0A6h
0x14004674f  mov     r8d, 14h
0x140046755  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rbx
0x14004675a  mov     dl, 2
0x14004675c  call    WPP_RECORDER_SF_
0x140046761  jmp     loc_140046531
0x140046766  mov     rcx, cs:VmsIfrNicLog
0x14004676d  lea     rax, aSrpmessageSend_0; "srpMessage->SendBufferSectionIndex < vm"...
0x140046774  mov     qword ptr [rsp+0E8h+Priority], rax
0x140046779  lea     rbx, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x140046780  mov     r9d, 0A7h
0x140046786  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rbx
0x14004678b  mov     r8d, 13h
0x140046791  call    WPP_RECORDER_SF_s
0x140046796  mov     eax, [rdi+130h]
0x14004679c  cmp     [rbp+8], eax
0x14004679f  jb      short loc_1400467A6
0x1400467a1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "srpMessage->SendBufferSectionIndex < vmNicExt->SendBufferSectionMdlArrayLength")
0x1400467a6  mov     eax, [rdi+130h]
0x1400467ac  mov     r9d, 0A8h
0x1400467b2  mov     dword ptr [rsp+0E8h+var_B8], eax
0x1400467b6  mov     eax, [rbp+8]
0x1400467b9  jmp     short loc_1400467D3
0x1400467bb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "srpMessage->SendBufferSectionSize <= vmNicExt->Persistent.SendBufferSubAllocationSize")
0x1400467c0  mov     eax, [rdi+240h]
0x1400467c6  mov     r9d, 0AAh
0x1400467cc  mov     dword ptr [rsp+0E8h+var_B8], eax
0x1400467d0  mov     eax, [rbp+0Ch]
0x1400467d3  mov     rcx, cs:VmsIfrNicLog
0x1400467da  mov     r8d, 14h
0x1400467e0  mov     [rsp+0E8h+Priority], eax
0x1400467e4  mov     dl, 2
0x1400467e6  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rbx
0x1400467eb  call    WPP_RECORDER_SF_ld
0x1400467f0  jmp     loc_140046531
0x1400467f5  mov     rcx, cs:VmsIfrNicLog
0x1400467fc  lea     rax, aSrpmessageSend; "srpMessage->SendBufferSectionSize <= vm"...
0x140046803  mov     qword ptr [rsp+0E8h+Priority], rax
0x140046808  lea     rbx, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x14004680f  mov     r9d, 0A9h
0x140046815  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rbx
0x14004681a  mov     r8d, 13h
0x140046820  call    WPP_RECORDER_SF_s
0x140046825  mov     eax, [rdi+240h]
0x14004682b  cmp     [rbp+0Ch], eax
0x14004682e  jbe     short loc_1400467C0
0x140046830  jmp     short loc_1400467BB
0x140046832  mov     eax, [rbp+8]
0x140046835  lea     rbx, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x14004683c  mov     rcx, cs:VmsIfrNicLog
0x140046843  mov     r9d, 0ABh
0x140046849  mov     [rsp+0E8h+Priority], eax
0x14004684d  mov     r8d, 14h
0x140046853  mov     dl, 2
0x140046855  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rbx
0x14004685a  call    WPP_RECORDER_SF_d
0x14004685f  mov     r14, [rsp+0E8h+var_88]
0x140046864  jmp     loc_140046531
0x140046869  cmp     byte ptr [rsi+9], 0
0x14004686d  jnz     loc_140046464
0x140046873  jmp     loc_1400465E1
0x140046878  cmp     byte ptr [rsi+0Ah], 0
0x14004687c  jnz     loc_1400464BC
0x140046882  mov     al, r14b
0x140046885  jmp     loc_1400464BE
0x14004688a  mov     rcx, [r15]
0x14004688d  call    VmsVmNicPvtKmclProcessingCompleteInternal
0x140046892  jmp     loc_1400464E6
```
