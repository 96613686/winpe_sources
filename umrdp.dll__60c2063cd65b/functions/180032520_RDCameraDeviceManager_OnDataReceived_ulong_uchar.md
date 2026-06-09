# RDCameraDeviceManager::OnDataReceived(ulong,uchar *)

- ea: `0x180032520`
- end: `0x180032aa4`
- name: `?OnDataReceived@RDCameraDeviceManager@@UEAAJKPEAE@Z`
- size: `1412`
- prototype: `__int64 __fastcall(RDCameraDeviceManager *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x18000bd44`
- `0x18000f79c`
- `0x180017dc8`
- `0x18001ba64`
- `0x180028640`
- `0x180031f2c`
- `0x180032520`
- `0x180032aac`
- `0x180032d10`
- `0x18004749c`
- `0x1800476c0`
- `0x180047c88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003255d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003255d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a84`

## string_xrefs

- `0x1800325ac`: `ProtocolHelper::ValidateMessage failed`
- `0x180032881`: `RDMediaProtocolHelper::PayloadToRDMediaDeviceInfo failed`
- `0x180032723`: `RDMediaProtocolHelper::PayloadToANSIString failed`
- `0x1800327c9`: `RemoveRDCameraDevice failed`

## pseudocode

```c
__int64 __fastcall RDCameraDeviceManager::OnDataReceived(
        RDCameraDeviceManager *this,
        unsigned int a2,
        unsigned __int8 *a3)
{
  unsigned __int16 *v4; // rsi
  int v7; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // r14d
  int v10; // r15d
  unsigned int v11; // eax
  int v12; // r15d
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // esi
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  int v25; // r14d
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  char *v31; // [rsp+30h] [rbp-20h] BYREF
  void *Block; // [rsp+38h] [rbp-18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-10h]
  unsigned __int8 v34; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int8 v35; // [rsp+A8h] [rbp+58h] BYREF

  v35 = 0;
  v4 = 0;
  v34 = 0;
  Block = 0;
  v31 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = RDMediaProtocolHelper::ValidateMessage(a3, a2, (enum RDMMessageType *)&v35, &v34);
  if ( v7 < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        18,
        (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"ProtocolHelper::ValidateMessage failed",
        v7);
    }
    goto LABEL_72;
  }
  v9 = v34;
  if ( v35 != 3 )
  {
    v10 = *((unsigned __int8 *)this + 632);
    if ( v34 != (_BYTE)v10 )
    {
      v7 = -2147024809;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ddd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          19,
          WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
          v11,
          v9,
          v10);
      }
      goto LABEL_72;
    }
  }
  v12 = v35;
  if ( v35 != 3 )
  {
    if ( v35 != 5 )
    {
      if ( v35 != 6 )
      {
        v7 = -2147024809;
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            28,
            WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
            v13,
            v12);
        }
        goto LABEL_72;
      }
      v7 = RDMediaProtocolHelper::PayloadToANSIString(a3, a2, &v31);
      if ( v7 < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            25,
            (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
            v14,
            (__int64)"RDMediaProtocolHelper::PayloadToANSIString failed",
            v7);
        }
        goto LABEL_70;
      }
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          26,
          (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
          v15,
          (__int64)v31);
      }
      v16 = RDCameraDeviceManager::RemoveRDCameraDevice(this, v31);
      v17 = *(_QWORD *)&WPP_GLOBAL_Control;
      v18 = v16;
      if ( v16 >= 0
        || *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        v7 = v16;
        if ( v16 >= 0 )
        {
LABEL_70:
          if ( v31 )
            operator delete(v31);
          goto LABEL_72;
        }
      }
      else
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          33,
          (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
          v19,
          (__int64)"RemoveRDCameraDevice failed",
          v18);
        v17 = *(_QWORD *)&WPP_GLOBAL_Control;
        v7 = v18;
      }
      if ( (unsigned int *)v17 != &WPP_GLOBAL_Control && (*(_BYTE *)(v17 + 28) & 8) != 0 && *(_BYTE *)(v17 + 25) >= 2u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          27,
          (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
          v20,
          (__int64)"OnDeviceAddedNotification failed",
          v18);
      }
      goto LABEL_70;
    }
    v7 = RDMediaProtocolHelper::PayloadToRDMediaDeviceInfo(a3, a2, (unsigned __int16 **)&Block, &v31);
    if ( v7 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          22,
          (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
          v21,
          (__int64)"RDMediaProtocolHelper::PayloadToRDMediaDeviceInfo failed",
          v7);
      }
      v4 = (unsigned __int16 *)Block;
      goto LABEL_68;
    }
    v4 = (unsigned __int16 *)Block;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        23,
        (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
        v22,
        (__int64)v4);
    }
    v23 = RDCameraDeviceManager::AddRDCameraDevice(this, v9, v4, v31);
    v24 = *(_QWORD *)&WPP_GLOBAL_Control;
    v25 = v23;
    if ( v23 < 0
      && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        32,
        (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
        v26,
        (__int64)"AddRDCameraDevice failed",
        v25);
      v24 = *(_QWORD *)&WPP_GLOBAL_Control;
      v7 = v25;
LABEL_55:
      if ( (unsigned int *)v24 != &WPP_GLOBAL_Control && (*(_BYTE *)(v24 + 28) & 8) != 0 && *(_BYTE *)(v24 + 25) >= 2u )
      {
        v27 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          24,
          (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
          v27,
          (__int64)"OnDeviceAddedNotification failed",
          v25);
      }
      goto LABEL_68;
    }
    v7 = v23;
    if ( v23 < 0 )
      goto LABEL_55;
LABEL_68:
    if ( v4 )
      operator delete(v4);
    goto LABEL_70;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v28 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      20,
      WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
      v28,
      v9);
  }
  v7 = RDCameraDeviceManager::OnSelectVersionRequest(this, v9);
  if ( v7 < 0
    && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      21,
      (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
      v29,
      (__int64)"OnSelectVersionRequest failed",
      v7);
    goto LABEL_68;
  }
LABEL_72:
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180032520  mov     [rsp-38h+arg_8], rbx
0x180032525  push    rbp
0x180032526  push    rsi
0x180032527  push    rdi
0x180032528  push    r12
0x18003252a  push    r13
0x18003252c  push    r14
0x18003252e  push    r15
0x180032530  mov     rbp, rsp
0x180032533  sub     rsp, 50h
0x180032537  xor     eax, eax
0x180032539  mov     r13, rcx
0x18003253c  mov     [rbp+arg_18], al
0x18003253f  mov     esi, eax
0x180032541  mov     [rbp+arg_0], al
0x180032544  mov     rbx, r8
0x180032547  mov     [rbp+Block], rax
0x18003254b  mov     r12d, edx
0x18003254e  mov     [rbp+var_20], rax
0x180032552  lea     rax, [rcx+10h]
0x180032556  mov     rcx, rax; lpCriticalSection
0x180032559  mov     [rbp+lpCriticalSection], rax
0x18003255d  call    cs:__imp_EnterCriticalSection
0x180032563  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x180032567  mov     edx, r12d; unsigned int
0x18003256a  lea     r8, [rbp+arg_18]; enum RDMMessageType *
0x18003256e  mov     rcx, rbx; unsigned __int8 *
0x180032571  call    ?ValidateMessage@RDMediaProtocolHelper@@SAJPEAEKPEAW4RDMMessageType@@0@Z; RDMediaProtocolHelper::ValidateMessage(uchar *,ulong,RDMMessageType *,uchar *)
0x180032576  mov     edi, eax
0x180032578  test    eax, eax
0x18003257a  jns     short loc_1800325DE
0x18003257c  mov     rax, cs:WPP_GLOBAL_Control
0x180032583  lea     rbx, WPP_GLOBAL_Control
0x18003258a  cmp     rax, rbx
0x18003258d  jz      loc_180032A7B
0x180032593  test    byte ptr [rax+1Ch], 8
0x180032597  jz      loc_180032A7B
0x18003259d  cmp     byte ptr [rax+19h], 2
0x1800325a1  jb      loc_180032A7B
0x1800325a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800325ac  lea     rcx, aProtocolhelper; "ProtocolHelper::ValidateMessage failed"
0x1800325b3  mov     [rsp+50h+var_28], edi
0x1800325b7  mov     [rsp+50h+var_30], rcx
0x1800325bc  lea     edx, [rsi+12h]
0x1800325bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325c6  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x1800325cd  mov     r9d, eax
0x1800325d0  mov     rcx, [rcx+10h]
0x1800325d4  call    WPP_SF_DsD
0x1800325d9  jmp     loc_180032A7B
0x1800325de  movzx   eax, [rbp+arg_18]
0x1800325e2  movzx   r14d, [rbp+arg_0]
0x1800325e7  cmp     al, 3
0x1800325e9  jz      short loc_18003265B
0x1800325eb  movzx   r15d, byte ptr [r13+278h]
0x1800325f3  cmp     r14b, r15b
0x1800325f6  jz      short loc_18003265B
0x1800325f8  mov     edi, 80070057h
0x1800325fd  mov     rax, cs:WPP_GLOBAL_Control
0x180032604  lea     rbx, WPP_GLOBAL_Control
0x18003260b  cmp     rax, rbx
0x18003260e  jz      loc_180032A7B
0x180032614  test    byte ptr [rax+1Ch], 1
0x180032618  jz      loc_180032A7B
0x18003261e  cmp     byte ptr [rax+19h], 2
0x180032622  jb      loc_180032A7B
0x180032628  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003262d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032634  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x18003263b  mov     edx, 13h
0x180032640  mov     [rsp+50h+var_28], r15d
0x180032645  mov     r9d, eax
0x180032648  mov     dword ptr [rsp+50h+var_30], r14d
0x18003264d  mov     rcx, [rcx+10h]
0x180032651  call    WPP_SF_Ddd
0x180032656  jmp     loc_180032A7B
0x18003265b  mov     ecx, eax
0x18003265d  mov     r15d, eax
0x180032660  sub     ecx, 3
0x180032663  jz      loc_1800329BB
0x180032669  sub     ecx, 2
0x18003266c  jz      loc_180032844
0x180032672  cmp     ecx, 1
0x180032675  jz      short loc_1800326D5
0x180032677  mov     edi, 80070057h
0x18003267c  mov     rax, cs:WPP_GLOBAL_Control
0x180032683  lea     rbx, WPP_GLOBAL_Control
0x18003268a  cmp     rax, rbx
0x18003268d  jz      loc_180032A7B
0x180032693  test    byte ptr [rax+1Ch], 1
0x180032697  jz      loc_180032A7B
0x18003269d  cmp     byte ptr [rax+19h], 2
0x1800326a1  jb      loc_180032A7B
0x1800326a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800326ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326b3  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x1800326ba  mov     edx, 1Ch
0x1800326bf  mov     dword ptr [rsp+50h+var_30], r15d
0x1800326c4  mov     r9d, eax
0x1800326c7  mov     rcx, [rcx+10h]
0x1800326cb  call    WPP_SF_Dd
0x1800326d0  jmp     loc_180032A7B
0x1800326d5  lea     r8, [rbp+var_20]; char **
0x1800326d9  mov     edx, r12d; unsigned int
0x1800326dc  mov     rcx, rbx; unsigned __int8 *
0x1800326df  call    ?PayloadToANSIString@RDMediaProtocolHelper@@SAJPEAEKPEAPEAD@Z; RDMediaProtocolHelper::PayloadToANSIString(uchar *,ulong,char * *)
0x1800326e4  mov     edi, eax
0x1800326e6  test    eax, eax
0x1800326e8  jns     short loc_18003274E
0x1800326ea  mov     rax, cs:WPP_GLOBAL_Control
0x1800326f1  lea     rbx, WPP_GLOBAL_Control
0x1800326f8  cmp     rax, rbx
0x1800326fb  jz      loc_180032A6D
0x180032701  test    byte ptr [rax+1Ch], 8
0x180032705  jz      loc_180032A6D
0x18003270b  cmp     byte ptr [rax+19h], 2
0x18003270f  jb      loc_180032A6D
0x180032715  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003271a  mov     edx, 19h
0x18003271f  mov     [rsp+50h+var_28], edi
0x180032723  lea     rcx, aRdmediaprotoco; "RDMediaProtocolHelper::PayloadToANSIStr"...
0x18003272a  mov     [rsp+50h+var_30], rcx
0x18003272f  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x180032736  mov     rcx, cs:WPP_GLOBAL_Control
0x18003273d  mov     r9d, eax
0x180032740  mov     rcx, [rcx+10h]
0x180032744  call    WPP_SF_DsD
0x180032749  jmp     loc_180032A6D
0x18003274e  mov     rax, cs:WPP_GLOBAL_Control
0x180032755  lea     rbx, WPP_GLOBAL_Control
0x18003275c  cmp     rax, rbx
0x18003275f  jz      short loc_18003279A
0x180032761  test    byte ptr [rax+1Ch], 1
0x180032765  jz      short loc_18003279A
0x180032767  cmp     byte ptr [rax+19h], 4
0x18003276b  jb      short loc_18003279A
0x18003276d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032772  mov     rcx, [rbp+var_20]
0x180032776  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x18003277d  mov     [rsp+50h+var_30], rcx
0x180032782  mov     edx, 1Ah
0x180032787  mov     rcx, cs:WPP_GLOBAL_Control
0x18003278e  mov     r9d, eax
0x180032791  mov     rcx, [rcx+10h]
0x180032795  call    WPP_SF_Ds
0x18003279a  mov     rdx, [rbp+var_20]; char *
0x18003279e  mov     rcx, r13; this
0x1800327a1  call    ?RemoveRDCameraDevice@RDCameraDeviceManager@@AEAAJPEBD@Z; RDCameraDeviceManager::RemoveRDCameraDevice(char const *)
0x1800327a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327ad  mov     esi, eax
0x1800327af  test    eax, eax
0x1800327b1  jns     short loc_180032803
0x1800327b3  cmp     rcx, rbx
0x1800327b6  jz      short loc_180032803
0x1800327b8  test    byte ptr [rcx+1Ch], 8
0x1800327bc  jz      short loc_180032803
0x1800327be  cmp     byte ptr [rcx+19h], 2
0x1800327c2  jb      short loc_180032803
0x1800327c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800327c9  lea     rcx, aRemoverdcamera; "RemoveRDCameraDevice failed"
0x1800327d0  mov     [rsp+50h+var_28], esi
0x1800327d4  mov     [rsp+50h+var_30], rcx
0x1800327d9  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x1800327e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327e7  mov     edx, 21h ; '!'
0x1800327ec  mov     r9d, eax
0x1800327ef  mov     rcx, [rcx+10h]
0x1800327f3  call    WPP_SF_DsD
0x1800327f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327ff  mov     edi, esi
0x180032801  jmp     short loc_18003280D
0x180032803  mov     edi, esi
0x180032805  test    esi, esi
0x180032807  jns     loc_180032A6D
0x18003280d  cmp     rcx, rbx
0x180032810  jz      loc_180032A6D
0x180032816  test    byte ptr [rcx+1Ch], 8
0x18003281a  jz      loc_180032A6D
0x180032820  cmp     byte ptr [rcx+19h], 2
0x180032824  jb      loc_180032A6D
0x18003282a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003282f  mov     edx, 1Bh
0x180032834  mov     [rsp+50h+var_28], esi
0x180032838  lea     rcx, aOndeviceaddedn; "OnDeviceAddedNotification failed"
0x18003283f  jmp     loc_18003272A
0x180032844  lea     r9, [rbp+var_20]; char **
0x180032848  mov     edx, r12d; unsigned int
0x18003284b  lea     r8, [rbp+Block]; unsigned __int16 **
0x18003284f  mov     rcx, rbx; unsigned __int8 *
0x180032852  call    ?PayloadToRDMediaDeviceInfo@RDMediaProtocolHelper@@SAJPEAEKPEAPEAGPEAPEAD@Z; RDMediaProtocolHelper::PayloadToRDMediaDeviceInfo(uchar *,ulong,ushort * *,char * *)
0x180032857  mov     edi, eax
0x180032859  test    eax, eax
0x18003285b  jns     short loc_1800328B9
0x18003285d  mov     rax, cs:WPP_GLOBAL_Control
0x180032864  lea     rbx, WPP_GLOBAL_Control
0x18003286b  cmp     rax, rbx
0x18003286e  jz      short loc_1800328B0
0x180032870  test    byte ptr [rax+1Ch], 8
0x180032874  jz      short loc_1800328B0
0x180032876  cmp     byte ptr [rax+19h], 2
0x18003287a  jb      short loc_1800328B0
0x18003287c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032881  lea     rcx, aRdmediaprotoco_0; "RDMediaProtocolHelper::PayloadToRDMedia"...
0x180032888  mov     [rsp+50h+var_28], edi
0x18003288c  mov     [rsp+50h+var_30], rcx
0x180032891  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x180032898  mov     rcx, cs:WPP_GLOBAL_Control
0x18003289f  mov     edx, 16h
0x1800328a4  mov     r9d, eax
0x1800328a7  mov     rcx, [rcx+10h]
0x1800328ab  call    WPP_SF_DsD
0x1800328b0  mov     rsi, [rbp+Block]
0x1800328b4  jmp     loc_180032A60
0x1800328b9  mov     rax, cs:WPP_GLOBAL_Control
0x1800328c0  lea     rbx, WPP_GLOBAL_Control
0x1800328c7  mov     rsi, [rbp+Block]
0x1800328cb  cmp     rax, rbx
0x1800328ce  jz      short loc_180032905
0x1800328d0  test    byte ptr [rax+1Ch], 1
0x1800328d4  jz      short loc_180032905
0x1800328d6  cmp     byte ptr [rax+19h], 4
0x1800328da  jb      short loc_180032905
0x1800328dc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800328e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328e8  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x1800328ef  mov     edx, 17h
0x1800328f4  mov     [rsp+50h+var_30], rsi
0x1800328f9  mov     r9d, eax
0x1800328fc  mov     rcx, [rcx+10h]
0x180032900  call    WPP_SF_DS
0x180032905  mov     r9, [rbp+var_20]; char *
0x180032909  mov     edx, r14d; unsigned int
0x18003290c  mov     r8, rsi; unsigned __int16 *
0x18003290f  mov     rcx, r13; this
0x180032912  call    ?AddRDCameraDevice@RDCameraDeviceManager@@AEAAJKPEBGPEBD@Z; RDCameraDeviceManager::AddRDCameraDevice(ulong,ushort const *,char const *)
0x180032917  mov     rcx, cs:WPP_GLOBAL_Control
0x18003291e  mov     r14d, eax
0x180032921  test    eax, eax
0x180032923  jns     short loc_180032977
0x180032925  cmp     rcx, rbx
0x180032928  jz      short loc_180032977
0x18003292a  test    byte ptr [rcx+1Ch], 8
0x18003292e  jz      short loc_180032977
0x180032930  cmp     byte ptr [rcx+19h], 2
0x180032934  jb      short loc_180032977
0x180032936  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003293b  lea     rcx, aAddrdcameradev; "AddRDCameraDevice failed"
0x180032942  mov     [rsp+50h+var_28], r14d
0x180032947  mov     [rsp+50h+var_30], rcx
0x18003294c  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x180032953  mov     rcx, cs:WPP_GLOBAL_Control
0x18003295a  mov     edx, 20h ; ' '
0x18003295f  mov     r9d, eax
0x180032962  mov     rcx, [rcx+10h]
0x180032966  call    WPP_SF_DsD
0x18003296b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032972  mov     edi, r14d
0x180032975  jmp     short loc_180032983
0x180032977  mov     edi, r14d
0x18003297a  test    r14d, r14d
0x18003297d  jns     loc_180032A60
0x180032983  cmp     rcx, rbx
0x180032986  jz      loc_180032A60
0x18003298c  test    byte ptr [rcx+1Ch], 8
0x180032990  jz      loc_180032A60
0x180032996  cmp     byte ptr [rcx+19h], 2
0x18003299a  jb      loc_180032A60
0x1800329a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800329a5  mov     edx, 18h
0x1800329aa  mov     [rsp+50h+var_28], r14d
0x1800329af  lea     rcx, aOndeviceaddedn; "OnDeviceAddedNotification failed"
0x1800329b6  jmp     loc_180032A41
0x1800329bb  mov     rax, cs:WPP_GLOBAL_Control
0x1800329c2  lea     rbx, WPP_GLOBAL_Control
0x1800329c9  cmp     rax, rbx
0x1800329cc  jz      short loc_180032A03
0x1800329ce  test    byte ptr [rax+1Ch], 1
0x1800329d2  jz      short loc_180032A03
0x1800329d4  cmp     byte ptr [rax+19h], 4
0x1800329d8  jb      short loc_180032A03
0x1800329da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800329df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329e6  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x1800329ed  mov     edx, 14h
0x1800329f2  mov     dword ptr [rsp+50h+var_30], r14d
0x1800329f7  mov     r9d, eax
0x1800329fa  mov     rcx, [rcx+10h]
0x1800329fe  call    WPP_SF_Dd
0x180032a03  mov     dl, r14b; unsigned __int8
0x180032a06  mov     rcx, r13; this
0x180032a09  call    ?OnSelectVersionRequest@RDCameraDeviceManager@@AEAAJE@Z; RDCameraDeviceManager::OnSelectVersionRequest(uchar)
0x180032a0e  mov     edi, eax
0x180032a10  test    eax, eax
0x180032a12  jns     short loc_180032A7B
0x180032a14  mov     rax, cs:WPP_GLOBAL_Control
0x180032a1b  cmp     rax, rbx
0x180032a1e  jz      short loc_180032A7B
0x180032a20  test    byte ptr [rax+1Ch], 8
0x180032a24  jz      short loc_180032A7B
0x180032a26  cmp     byte ptr [rax+19h], 2
  ... truncated ...
```
