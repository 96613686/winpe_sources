# MpObSendOpenProcessBMNotification

- ea: `0x140033db0`
- end: `0x1400346e9`
- name: `MpObSendOpenProcessBMNotification`
- size: `2361`
- prototype: `__int64 __usercall@<rax>(HANDLE ProcessId@<rcx>, int, int, char, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002f510`

## callees

- `0x1400018a4`
- `0x1400026c0`
- `0x140003950`
- `0x140003d20`
- `0x1400049dc`
- `0x1400051bc`
- `0x14000a624`
- `0x1400118d0`
- `0x140011900`
- `0x140033db0`
- `0x140034b50`
- `0x140035100`
- `0x140066180`
- `0x140070414`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x140033f8f`
- `ntoskrnl!KeQueryPriorityThread` at `0x140033f8f`
- `ntoskrnl!SeQueryInformationToken` at `0x140033ec7`
- `ntoskrnl!SeQueryInformationToken` at `0x140033ec7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140033ee8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140034363`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140034492`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140033ee8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140034363`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140034492`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140033e97`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140033e97`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140033fe2`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140034042`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140033fe2`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140034042`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140033ff6`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140034056`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140033ff6`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140034056`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003414c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034176`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003414c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034176`
- `ntoskrnl!ObfDereferenceObject` at `0x14003400a`
- `ntoskrnl!ObfDereferenceObject` at `0x14003406a`
- `ntoskrnl!ObfDereferenceObject` at `0x14003400a`
- `ntoskrnl!ObfDereferenceObject` at `0x14003406a`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x140033f72`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x140033f72`

## pseudocode

```c
void __fastcall MpObSendOpenProcessBMNotification(
        HANDLE ProcessId,
        void *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        char a7,
        unsigned __int8 a8)
{
  unsigned int v9; // esi
  int v11; // ecx
  const void **v13; // r13
  const void **v14; // rdi
  PDEVICE_OBJECT v15; // rcx
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS v17; // eax
  unsigned int v18; // esi
  __int64 PoolWithTag; // rax
  __int64 v20; // r12
  NTSTATUS v21; // eax
  KPRIORITY PriorityThread; // eax
  IO_PRIORITY_HINT IoPriority; // ecx
  __int64 v24; // rsi
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rax
  __int16 v29; // r9
  int v30; // edx
  int v31; // eax
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  unsigned int ProcessName; // eax
  unsigned int v36; // eax
  int v37; // ecx
  int v38; // eax
  int v39; // eax
  int v40; // edx
  char v41; // [rsp+30h] [rbp-69h]
  unsigned __int8 v42; // [rsp+31h] [rbp-68h]
  int v43; // [rsp+34h] [rbp-65h]
  NTSTATUS v44; // [rsp+38h] [rbp-61h]
  int v45; // [rsp+38h] [rbp-61h]
  unsigned int v46; // [rsp+3Ch] [rbp-5Dh]
  unsigned int v47; // [rsp+40h] [rbp-59h]
  const void **v49; // [rsp+50h] [rbp-49h] BYREF
  __int64 v50; // [rsp+58h] [rbp-41h]
  PVOID TokenInformation; // [rsp+60h] [rbp-39h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp-31h] BYREF
  _IO_PRIORITY_INFO PriorityInfo; // [rsp+88h] [rbp-11h] BYREF

  v50 = a4;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v9 = 112;
  v11 = *(_DWORD *)(MpData + 868);
  v43 = 112;
  v13 = 0;
  v49 = 0;
  v14 = 0;
  *(_QWORD *)&PriorityInfo.Size = 0;
  v46 = 0;
  v47 = 0;
  if ( (v11 & 2) == 0 || (a5 & 0x2EA) == 0 && !a7 && !a8 )
    return;
  if ( ProcessId )
  {
    if ( *(_DWORD *)(a3 + 104) == 1 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        return;
      v34 = 30;
      goto LABEL_52;
    }
    if ( !a7 && !a8 )
    {
      if ( !(unsigned __int8)MpShouldSendBmMessage(a3, a8, a3, a4) )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          return;
        v34 = 31;
LABEL_52:
        WPP_SF_(v15->AttachedDevice, v34, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids);
        return;
      }
      v33 = *(unsigned int *)(v32 + 56);
      if ( (v33 & 8) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids, v33);
        return;
      }
    }
    SeCaptureSubjectContext(&SubjectContext);
    PrimaryToken = SubjectContext.PrimaryToken;
    if ( SubjectContext.ClientToken )
      PrimaryToken = SubjectContext.ClientToken;
    if ( PrimaryToken )
    {
      LODWORD(TokenInformation) = 0;
      v17 = SeQueryInformationToken(PrimaryToken, TokenSessionId, &TokenInformation);
      v44 = v17;
      if ( v17 >= 0 )
      {
        v45 = (int)TokenInformation;
        SeReleaseSubjectContext(&SubjectContext);
        if ( a5 == a6 )
        {
          v42 = 0;
          v41 = 0;
        }
        else
        {
          v42 = 1;
          ProcessName = MpGetProcessName(ProcessId, &v49);
          v13 = v49;
          if ( ProcessName )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                35,
                WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids,
                ProcessName);
            }
          }
          else
          {
            v46 = 112;
            v9 = *(unsigned __int16 *)v49 + 114;
            v43 = v9;
          }
          v36 = MpGetProcessName(a2, &PriorityInfo);
          v14 = *(const void ***)&PriorityInfo.Size;
          if ( v36 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids, v36);
            }
          }
          else
          {
            v47 = v9;
            v9 += **(unsigned __int16 **)&PriorityInfo.Size + 2;
            v43 = v9;
          }
          v41 = 1;
          if ( v9 < 0x18 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                26,
                WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
                KeGetCurrentThread());
            }
            v37 = -1073741811;
            goto LABEL_91;
          }
        }
        _mm_lfence();
        v18 = v9 + 24;
        PoolWithTag = MpAllocatePoolWithTag(1, v18, 1835094093);
        v20 = PoolWithTag;
        if ( PoolWithTag )
        {
          *(_WORD *)PoolWithTag = 421;
          *(_DWORD *)(PoolWithTag + 4) = v18;
          PriorityInfo.Size = 16;
          *(_WORD *)(PoolWithTag + 2) = 2;
          *(_OWORD *)(PoolWithTag + 8) = 0;
          *(_QWORD *)&PriorityInfo.ThreadPriority = 0xFFFF;
          PriorityInfo.IoPriority = IoPriorityNormal;
          v21 = FltRetrieveIoPriorityInfo(0, 0, KeGetCurrentThread(), &PriorityInfo);
          if ( v21 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              33,
              WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
              (unsigned int)v21);
          }
          PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
          IoPriority = PriorityInfo.IoPriority;
          v24 = v20 + 24;
          *(_DWORD *)(v20 + 12) = PriorityThread;
          *(_DWORD *)(v20 + 8) = IoPriority;
          *(_DWORD *)(v20 + 16) = PriorityInfo.PagePriority;
          *(_DWORD *)(v20 + 36) = 1;
          *(_QWORD *)(v20 + 24) = 0;
          *(_QWORD *)&PriorityInfo.Size = 0;
          TokenInformation = 0;
          *(_DWORD *)(v20 + 32) = v43;
          *(_DWORD *)(v20 + 40) = 4;
          if ( PsLookupProcessByProcessId(ProcessId, (PEPROCESS *)&TokenInformation) >= 0 )
          {
            *(_QWORD *)&PriorityInfo.Size = PsGetProcessCreateTimeQuadPart((PEPROCESS)TokenInformation);
            ObfDereferenceObject(TokenInformation);
          }
          v25 = *(_QWORD *)&PriorityInfo.Size;
          *(_DWORD *)(v20 + 48) = (_DWORD)ProcessId;
          *(_QWORD *)(v20 + 52) = MpFileTimeToUlong64(v25);
          v26 = (int)a2;
          *(_QWORD *)&PriorityInfo.Size = 0;
          if ( a2 )
          {
            TokenInformation = 0;
            if ( PsLookupProcessByProcessId(a2, (PEPROCESS *)&TokenInformation) >= 0 )
            {
              *(_QWORD *)&PriorityInfo.Size = PsGetProcessCreateTimeQuadPart((PEPROCESS)TokenInformation);
              ObfDereferenceObject(TokenInformation);
            }
            v26 = (int)a2;
          }
          v27 = *(_QWORD *)&PriorityInfo.Size;
          *(_DWORD *)(v20 + 60) = v26;
          v28 = MpFileTimeToUlong64(v27);
          v30 = v42;
          *(_QWORD *)(v20 + 64) = v28;
          *(_DWORD *)(v20 + 76) = a5;
          *(_DWORD *)(v20 + 72) = v45;
          *(_QWORD *)(v20 + 80) = 0;
          *(_QWORD *)(v20 + 88) = 0;
          *(_DWORD *)(v20 + 132) = v42;
          if ( a7 )
          {
            v30 = v42 | 2;
            *(_DWORD *)(v20 + 132) = v30;
            if ( !v41 )
            {
              v30 = v42 | 0xA;
              *(_DWORD *)(v20 + 132) = v30;
            }
          }
          if ( a8 )
          {
            v40 = v30 | 4;
            *(_DWORD *)(v20 + 132) = v40;
            if ( !v41 )
              *(_DWORD *)(v20 + 132) = v40 | 0x10;
          }
          *(_OWORD *)(v20 + 96) = 0;
          if ( a7 )
            *(_OWORD *)(v20 + 96) = *(_OWORD *)(a3 + 136);
          *(_OWORD *)(v20 + 112) = 0;
          if ( a8 )
            *(_OWORD *)(v20 + 112) = *(_OWORD *)(v50 + 152);
          if ( v13 )
          {
            v38 = *(unsigned __int16 *)v13;
            if ( v29 != (_WORD)v38 )
            {
              *(_DWORD *)(v20 + 80) = v38 + 2;
              *(_DWORD *)(v20 + 84) = v46;
              memmove((void *)(v24 + v46), v13[1], *(unsigned __int16 *)v13);
              v29 = 0;
              *(_WORD *)(v24 + 2 * ((unsigned __int64)(*(unsigned __int16 *)v13 + v46) >> 1)) = 0;
            }
          }
          if ( v14 )
          {
            v39 = *(unsigned __int16 *)v14;
            if ( v29 != (_WORD)v39 )
            {
              *(_DWORD *)(v20 + 88) = v39 + 2;
              *(_DWORD *)(v20 + 92) = v47;
              memmove((void *)(v24 + v47), v14[1], *(unsigned __int16 *)v14);
              *(_WORD *)(v24 + 2 * ((unsigned __int64)(*(unsigned __int16 *)v14 + v47) >> 1)) = 0;
            }
          }
          v31 = MpAsyncSendNotification((int)v20 + 24, v43, 0, 1, a3);
          if ( v31 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              _mm_lfence();
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                38,
                WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids,
                KeGetCurrentThread(),
                v31);
            }
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_DDD(
              WPP_GLOBAL_Control->AttachedDevice,
              39,
              WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids,
              (unsigned int)ProcessId,
              (_DWORD)a2,
              a5);
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20 + 36), 0xFFFFFFFF) == 1 )
            ExFreePoolWithTag((PVOID)v20, 0x6D61504Du);
LABEL_36:
          if ( v13 )
            MpFreeString(v13);
          if ( v14 )
            ExFreePoolWithTag(v14, 0x7375704Du);
          return;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            27,
            WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
            KeGetCurrentThread());
        v37 = -1073741670;
LABEL_91:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            37,
            WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids,
            KeGetCurrentThread(),
            v37);
        }
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
          KeGetCurrentThread(),
          v17);
      }
      SeReleaseSubjectContext(&SubjectContext);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids,
          KeGetCurrentThread(),
          v44);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          33,
          WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids,
          KeGetCurrentThread(),
          -1073741823);
      SeReleaseSubjectContext(&SubjectContext);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      29,
      WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids,
      KeGetCurrentThread());
  }
}

```

## disassembly

```asm
0x140033db0  mov     [rsp-8+arg_18], rbx
0x140033db5  push    rbp
0x140033db6  push    rsi
0x140033db7  push    rdi
0x140033db8  push    r12
0x140033dba  push    r13
0x140033dbc  push    r14
0x140033dbe  push    r15
0x140033dc0  lea     rbp, [rsp-7]
0x140033dc5  sub     rsp, 0A0h
0x140033dcc  mov     rax, cs:__security_cookie
0x140033dd3  xor     rax, rsp
0x140033dd6  mov     [rbp+37h+var_38], rax
0x140033dda  mov     rax, cs:MpData
0x140033de1  xor     ebx, ebx
0x140033de3  xorps   xmm0, xmm0
0x140033de6  mov     [rbp+37h+var_78], r9
0x140033dea  mov     r15, rcx
0x140033ded  mov     [rbp+37h+ProcessId], rdx
0x140033df1  movups  xmmword ptr [rbp+37h+SubjectContext.ClientToken], xmm0
0x140033df5  mov     esi, 70h ; 'p'
0x140033dfa  mov     r14, r8
0x140033dfd  movups  xmmword ptr [rbp+37h+SubjectContext.PrimaryToken], xmm0
0x140033e01  mov     ecx, [rax+364h]
0x140033e07  mov     r12, rdx
0x140033e0a  mov     [rbp+37h+var_9C], esi
0x140033e0d  mov     r13d, ebx
0x140033e10  mov     [rbp+37h+var_80], rbx
0x140033e14  mov     edi, ebx
0x140033e16  mov     qword ptr [rbp+37h+PriorityInfo.Size], rbx
0x140033e1a  mov     [rbp+37h+var_94], ebx
0x140033e1d  mov     [rbp+37h+var_90], ebx
0x140033e20  test    cl, 2
0x140033e23  jz      short loc_140033E63
0x140033e25  test    [rbp+37h+arg_20], 2EAh
0x140033e2c  movzx   edx, [rbp+37h+arg_38]
0x140033e30  movzx   ecx, [rbp+37h+arg_30]
0x140033e34  jz      loc_140034187
0x140033e3a  test    r15, r15
0x140033e3d  jz      loc_140034374
0x140033e43  mov     eax, [r8+68h]
0x140033e47  cmp     eax, 1
0x140033e4a  jnz     short loc_140033E8B
0x140033e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140033e53  lea     rbx, WPP_GLOBAL_Control
0x140033e5a  cmp     rcx, rbx
0x140033e5d  jnz     loc_1400343F5
0x140033e63  mov     rcx, [rbp+37h+var_38]
0x140033e67  xor     rcx, rsp; StackCookie
0x140033e6a  call    __security_check_cookie
0x140033e6f  mov     rbx, [rsp+0D0h+arg_18]
0x140033e77  add     rsp, 0A0h
0x140033e7e  pop     r15
0x140033e80  pop     r14
0x140033e82  pop     r13
0x140033e84  pop     r12
0x140033e86  pop     rdi
0x140033e87  pop     rsi
0x140033e88  pop     rbp
0x140033e89  retn
0x140033e8b  test    cl, cl
0x140033e8d  jz      loc_14003419C
0x140033e93  lea     rcx, [rbp+37h+SubjectContext]; SubjectContext
0x140033e97  call    cs:__imp_SeCaptureSubjectContext
0x140033e9e  nop     dword ptr [rax+rax+00h]
0x140033ea3  mov     rax, [rbp+37h+SubjectContext.ClientToken]
0x140033ea7  mov     rcx, [rbp+37h+SubjectContext.PrimaryToken]
0x140033eab  test    rax, rax
0x140033eae  cmovnz  rcx, rax; Token
0x140033eb2  test    rcx, rcx
0x140033eb5  jz      loc_140034348
0x140033ebb  lea     r8, [rbp+37h+TokenInformation]; TokenInformation
0x140033ebf  mov     dword ptr [rbp+37h+TokenInformation], ebx
0x140033ec2  mov     edx, 0Ch; TokenInformationClass
0x140033ec7  call    cs:__imp_SeQueryInformationToken
0x140033ece  nop     dword ptr [rax+rax+00h]
0x140033ed3  mov     [rbp+37h+var_98], eax
0x140033ed6  test    eax, eax
0x140033ed8  js      loc_140034447
0x140033ede  mov     eax, dword ptr [rbp+37h+TokenInformation]
0x140033ee1  lea     rcx, [rbp+37h+SubjectContext]; SubjectContext
0x140033ee5  mov     [rbp+37h+var_98], eax
0x140033ee8  call    cs:__imp_SeReleaseSubjectContext
0x140033eef  nop     dword ptr [rax+rax+00h]
0x140033ef4  mov     eax, [rbp+37h+arg_20]
0x140033ef7  lea     rbx, WPP_GLOBAL_Control
0x140033efe  cmp     eax, [rbp+37h+arg_28]
0x140033f01  jnz     loc_140034236
0x140033f07  mov     [rbp+37h+var_9F], dil
0x140033f0b  mov     [rbp+37h+var_A0], dil
0x140033f0f  lfence
0x140033f12  add     esi, 18h
0x140033f15  mov     ecx, 1
0x140033f1a  mov     edx, esi
0x140033f1c  mov     r8d, 6D61504Dh
0x140033f22  call    MpAllocatePoolWithTag
0x140033f27  mov     r12, rax
0x140033f2a  test    rax, rax
0x140033f2d  jz      loc_14003455F
0x140033f33  mov     word ptr [rax], 1A5h
0x140033f38  lea     r9, [rbp+37h+PriorityInfo]; PriorityInfo
0x140033f3c  mov     [rax+4], esi
0x140033f3f  xorps   xmm0, xmm0
0x140033f42  mov     eax, 2
0x140033f47  mov     [rbp+37h+PriorityInfo.Size], 10h
0x140033f4e  mov     [r12+2], ax
0x140033f54  xor     edx, edx; FileObject
0x140033f56  movups  xmmword ptr [r12+8], xmm0
0x140033f5c  mov     qword ptr [rbp+37h+PriorityInfo.ThreadPriority], 0FFFFh
0x140033f64  xor     ecx, ecx; Data
0x140033f66  mov     [rbp+37h+PriorityInfo.IoPriority], eax
0x140033f69  mov     r8, gs:188h; Thread
0x140033f72  call    cs:__imp_FltRetrieveIoPriorityInfo
0x140033f79  nop     dword ptr [rax+rax+00h]
0x140033f7e  test    eax, eax
0x140033f80  js      loc_1400345E8
0x140033f86  mov     rcx, gs:188h; Thread
0x140033f8f  call    cs:__imp_KeQueryPriorityThread
0x140033f96  nop     dword ptr [rax+rax+00h]
0x140033f9b  mov     ecx, [rbp+37h+PriorityInfo.IoPriority]
0x140033f9e  lea     rsi, [r12+18h]
0x140033fa3  mov     [r12+0Ch], eax
0x140033fa8  lea     rdx, [rbp+37h+TokenInformation]; Process
0x140033fac  mov     [r12+8], ecx
0x140033fb1  xor     ecx, ecx
0x140033fb3  mov     [rbp+37h+PriorityInfo.ThreadPriority], eax
0x140033fb6  mov     eax, [rbp+37h+PriorityInfo.PagePriority]
0x140033fb9  mov     [r12+10h], eax
0x140033fbe  mov     eax, [rbp+37h+var_9C]
0x140033fc1  mov     dword ptr [r12+24h], 1
0x140033fca  mov     [rsi], rcx
0x140033fcd  mov     qword ptr [rbp+37h+PriorityInfo.Size], rcx
0x140033fd1  mov     [rbp+37h+TokenInformation], rcx
0x140033fd5  mov     rcx, r15; ProcessId
0x140033fd8  mov     [rsi+8], eax
0x140033fdb  mov     dword ptr [rsi+10h], 4
0x140033fe2  call    cs:__imp_PsLookupProcessByProcessId
0x140033fe9  nop     dword ptr [rax+rax+00h]
0x140033fee  test    eax, eax
0x140033ff0  js      short loc_140034016
0x140033ff2  mov     rcx, [rbp+37h+TokenInformation]; Process
0x140033ff6  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140033ffd  nop     dword ptr [rax+rax+00h]
0x140034002  mov     rcx, [rbp+37h+TokenInformation]; Object
0x140034006  mov     qword ptr [rbp+37h+PriorityInfo.Size], rax
0x14003400a  call    cs:__imp_ObfDereferenceObject
0x140034011  nop     dword ptr [rax+rax+00h]
0x140034016  mov     rcx, qword ptr [rbp+37h+PriorityInfo.Size]
0x14003401a  mov     [rsi+18h], r15d
0x14003401e  call    MpFileTimeToUlong64
0x140034023  xor     r9d, r9d
0x140034026  mov     [rsi+1Ch], rax
0x14003402a  mov     rax, [rbp+37h+ProcessId]
0x14003402e  mov     qword ptr [rbp+37h+PriorityInfo.Size], r9
0x140034032  test    rax, rax
0x140034035  jz      short loc_14003407D
0x140034037  lea     rdx, [rbp+37h+TokenInformation]; Process
0x14003403b  mov     [rbp+37h+TokenInformation], r9
0x14003403f  mov     rcx, rax; ProcessId
0x140034042  call    cs:__imp_PsLookupProcessByProcessId
0x140034049  nop     dword ptr [rax+rax+00h]
0x14003404e  test    eax, eax
0x140034050  js      short loc_140034076
0x140034052  mov     rcx, [rbp+37h+TokenInformation]; Process
0x140034056  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14003405d  nop     dword ptr [rax+rax+00h]
0x140034062  mov     rcx, [rbp+37h+TokenInformation]; Object
0x140034066  mov     qword ptr [rbp+37h+PriorityInfo.Size], rax
0x14003406a  call    cs:__imp_ObfDereferenceObject
0x140034071  nop     dword ptr [rax+rax+00h]
0x140034076  mov     rax, [rbp+37h+ProcessId]
0x14003407a  xor     r9d, r9d
0x14003407d  mov     rcx, qword ptr [rbp+37h+PriorityInfo.Size]
0x140034081  mov     [rsi+24h], eax
0x140034084  call    MpFileTimeToUlong64
0x140034089  movzx   edx, [rbp+37h+var_9F]
0x14003408d  movzx   r8d, [rbp+37h+var_A0]
0x140034092  mov     [rsi+28h], rax
0x140034096  mov     eax, [rbp+37h+arg_20]
0x140034099  mov     [rsi+34h], eax
0x14003409c  mov     eax, [rbp+37h+var_98]
0x14003409f  mov     [rsi+30h], eax
0x1400340a2  movzx   eax, [rbp+37h+arg_30]
0x1400340a6  mov     qword ptr [rsi+38h], 0
0x1400340ae  mov     qword ptr [rsi+40h], 0
0x1400340b6  mov     [rsi+6Ch], edx
0x1400340b9  test    al, al
0x1400340bb  jnz     loc_14003462B
0x1400340c1  movzx   ecx, [rbp+37h+arg_38]
0x1400340c5  test    cl, cl
0x1400340c7  jnz     loc_140034645
0x1400340cd  xorps   xmm0, xmm0
0x1400340d0  movups  xmmword ptr [rsi+48h], xmm0
0x1400340d4  test    al, al
0x1400340d6  jnz     loc_14003465F
0x1400340dc  xorps   xmm0, xmm0
0x1400340df  movups  xmmword ptr [rsi+58h], xmm0
0x1400340e3  test    cl, cl
0x1400340e5  jnz     loc_1400342AD
0x1400340eb  test    r13, r13
0x1400340ee  jnz     loc_1400342C1
0x1400340f4  test    rdi, rdi
0x1400340f7  jnz     loc_140034308
0x1400340fd  mov     edx, [rbp+37h+var_9C]
0x140034100  mov     r9d, 1
0x140034106  xor     r8d, r8d
0x140034109  mov     [rsp+0D0h+var_B0], r14
0x14003410e  mov     rcx, rsi
0x140034111  call    MpAsyncSendNotification
0x140034116  test    eax, eax
0x140034118  js      loc_140034670
0x14003411e  mov     rcx, cs:WPP_GLOBAL_Control
0x140034125  cmp     rcx, rbx
0x140034128  jz      short loc_140034135
0x14003412a  mov     eax, [rcx+2Ch]
0x14003412d  test    al, 4
0x14003412f  jnz     loc_1400346BD
0x140034135  mov     eax, 0FFFFFFFFh
0x14003413a  lock xadd [rsi+0Ch], eax
0x14003413f  cmp     eax, 1
0x140034142  jnz     short loc_140034158
0x140034144  mov     edx, 6D61504Dh; Tag
0x140034149  mov     rcx, r12; P
0x14003414c  call    cs:__imp_ExFreePoolWithTag
0x140034153  nop     dword ptr [rax+rax+00h]
0x140034158  test    r13, r13
0x14003415b  jz      short loc_140034165
0x14003415d  mov     rcx, r13
0x140034160  call    MpFreeString
0x140034165  test    rdi, rdi
0x140034168  jz      loc_140033E63
0x14003416e  mov     edx, 7375704Dh; Tag
0x140034173  mov     rcx, rdi; P
0x140034176  call    cs:__imp_ExFreePoolWithTag
0x14003417d  nop     dword ptr [rax+rax+00h]
0x140034182  jmp     loc_140033E63
0x140034187  test    cl, cl
0x140034189  jnz     loc_140033E3A
0x14003418f  test    dl, dl
0x140034191  jnz     loc_140033E3A
0x140034197  jmp     loc_140033E63
0x14003419c  test    dl, dl
0x14003419e  jnz     loc_140033E93
0x1400341a4  mov     rcx, r14
0x1400341a7  call    MpShouldSendBmMessage
0x1400341ac  test    al, al
0x1400341ae  jz      short loc_1400341FA
0x1400341b0  mov     r9d, [r8+38h]
0x1400341b4  test    r9b, 8
0x1400341b8  jz      loc_140033E93
0x1400341be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400341c5  lea     rbx, WPP_GLOBAL_Control
0x1400341cc  cmp     rcx, rbx
0x1400341cf  jz      loc_140033E63
0x1400341d5  mov     eax, [rcx+2Ch]
0x1400341d8  test    al, 4
0x1400341da  jz      loc_140033E63
0x1400341e0  mov     rcx, [rcx+18h]
0x1400341e4  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x1400341eb  mov     edx, 20h ; ' '
0x1400341f0  call    WPP_SF_d
0x1400341f5  jmp     loc_140033E63
0x1400341fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140034201  lea     rbx, WPP_GLOBAL_Control
0x140034208  cmp     rcx, rbx
0x14003420b  jz      loc_140033E63
0x140034211  mov     eax, [rcx+2Ch]
0x140034214  test    al, 4
0x140034216  jz      loc_140033E63
0x14003421c  mov     edx, 1Fh
0x140034221  mov     rcx, [rcx+18h]
0x140034225  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x14003422c  call    WPP_SF_
0x140034231  jmp     loc_140033E63
0x140034236  lea     rdx, [rbp+37h+var_80]
0x14003423a  mov     [rbp+37h+var_9F], 1
0x14003423e  mov     rcx, r15
0x140034241  call    MpGetProcessName
0x140034246  mov     r13, [rbp+37h+var_80]
0x14003424a  test    eax, eax
0x14003424c  jnz     loc_1400344ED
0x140034252  mov     [rbp+37h+var_94], esi
0x140034255  movzx   esi, word ptr [r13+0]
0x14003425a  add     esi, 72h ; 'r'
0x14003425d  mov     [rbp+37h+var_9C], esi
0x140034260  lea     rdx, [rbp+37h+PriorityInfo]
0x140034264  mov     rcx, r12
0x140034267  call    MpGetProcessName
0x14003426c  mov     rdi, qword ptr [rbp+37h+PriorityInfo.Size]
0x140034270  test    eax, eax
0x140034272  jnz     loc_140034526
0x140034278  movzx   eax, word ptr [rdi]
0x14003427b  add     eax, 2
0x14003427e  mov     [rbp+37h+var_90], esi
0x140034281  add     esi, eax
0x140034283  mov     [rbp+37h+var_9C], esi
0x140034286  mov     [rbp+37h+var_A0], 1
0x14003428a  cmp     esi, 18h
0x14003428d  jnb     loc_140033F0F
0x140034293  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
