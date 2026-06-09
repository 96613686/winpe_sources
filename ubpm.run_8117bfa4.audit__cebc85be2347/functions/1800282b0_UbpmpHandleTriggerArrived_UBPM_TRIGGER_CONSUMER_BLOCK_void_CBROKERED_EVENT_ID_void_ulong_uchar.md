# UbpmpHandleTriggerArrived(_UBPM_TRIGGER_CONSUMER_BLOCK *,void *,_CBROKERED_EVENT_ID,void *,ulong,uchar)

- ea: `0x1800282b0`
- end: `0x180028a69`
- name: `?UbpmpHandleTriggerArrived@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAXU_CBROKERED_EVENT_ID@@1KE@Z`
- size: `1977`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028250`
- `0x180028280`

## callees

- `0x1800044f8`
- `0x180008720`
- `0x180008920`
- `0x18001af64`
- `0x180024d08`
- `0x1800282b0`
- `0x18002e500`
- `0x18002f75c`
- `0x180035184`
- `0x180037cac`
- `0x180040216`
- `0x180040260`
- `0x180041010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002854c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028609`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028849`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002854c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028609`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028849`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180028650`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002874e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800287ac`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800288b5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180028650`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002874e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800287ac`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800288b5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800283d4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028a35`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800283d4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028a35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028855`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028855`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800284ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800284ac`

## pseudocode

```c
ULONG __fastcall UbpmpHandleTriggerArrived(__int64 a1, __int64 a2, __int64 a3, void *a4, unsigned int a5, char a6)
{
  __int64 *v6; // r15
  __int64 v9; // r12
  unsigned __int16 v10; // di
  __int64 v11; // r14
  __int64 *v12; // rcx
  __int64 v13; // rax
  bool v14; // zf
  int v15; // eax
  unsigned int v16; // esi
  __int64 v17; // r12
  unsigned int v18; // ebx
  int v19; // r15d
  HRESULT v20; // esi
  bool v21; // sf
  struct _UBPM_REPETITION_CONTEXT *v22; // r9
  __int64 *v23; // r13
  unsigned int v24; // edx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  struct _UBPM_REPETITION_CONTEXT *v28; // rcx
  int v29; // eax
  unsigned int v30; // eax
  __int64 *v31; // r10
  unsigned int v32; // edx
  ULONG result; // eax
  __int64 v34; // rax
  __int64 *v35; // rcx
  int v36; // r14d
  __int64 v37; // rbx
  signed __int64 v38; // rsi
  DWORD CurrentThreadId; // eax
  void *v40; // r13
  __int64 v41; // rcx
  int v42; // eax
  int v43; // r8d
  unsigned int v44; // eax
  unsigned int v45; // [rsp+40h] [rbp-89h] BYREF
  __int64 *v46; // [rsp+48h] [rbp-81h]
  unsigned int v47; // [rsp+50h] [rbp-79h]
  struct _UBPM_REPETITION_CONTEXT *v48; // [rsp+58h] [rbp-71h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-59h] BYREF
  void *v51; // [rsp+78h] [rbp-51h]
  EVENT_DESCRIPTOR v52; // [rsp+80h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-39h] BYREF
  int *v54; // [rsp+A0h] [rbp-29h]
  int v55; // [rsp+A8h] [rbp-21h]
  int v56; // [rsp+ACh] [rbp-1Dh]
  __int64 *v57; // [rsp+B0h] [rbp-19h]
  int v58; // [rsp+B8h] [rbp-11h]
  int v59; // [rsp+BCh] [rbp-Dh]
  unsigned int *v60; // [rsp+C0h] [rbp-9h]
  __int64 v61; // [rsp+C8h] [rbp-1h]

  v6 = (__int64 *)(a1 + 24);
  *(_QWORD *)&v52.Id = a1;
  v46 = (__int64 *)(a1 + 24);
  v48 = 0;
  v51 = a4;
  v9 = a1;
  v10 = -1;
  v11 = -1;
  if ( (unsigned int)dword_18004F0F0 <= 4 )
  {
    v46 = (__int64 *)(a1 + 24);
  }
  else
  {
    v12 = *(__int64 **)(*v6 + 8);
    if ( v12 )
    {
      v13 = -1;
      do
        v14 = *((_WORD *)v12 + ++v13) == 0;
      while ( !v14 );
      v15 = 2 * v13 + 2;
    }
    else
    {
      v12 = &qword_1800439C0;
      v15 = 2;
    }
    v58 = v15;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_18004F0F8;
    v57 = v12;
    v59 = 0;
    EventDescriptor.Keyword = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_18004F0F8;
    v54 = (int *)byte_18004617B;
    UserData.Reserved = 2;
    v55 = 29;
    v56 = 1;
    v45 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v47 = UbpmConsumerIncPendingActions(v9);
  v16 = v47;
  if ( !v47 )
  {
    if ( a4 && a5 < 0x14 )
    {
      v16 = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v9 + 24) + 8LL),
          87);
      goto LABEL_63;
    }
    v17 = *v6;
    v18 = 0;
    EventDescriptor = 0;
    if ( memcmp_0(&EventDescriptor, (const void *)(v17 + 84), 0x10u) )
    {
      v19 = 0;
      v45 = 0;
      ppv = 0;
      *(_QWORD *)&EventDescriptor.Id = 0;
      v20 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &IID_INetworkListManagerPrivate, &ppv);
      if ( v20 >= 0 )
      {
        v20 = (*(__int64 (__fastcall **)(LPVOID, __int64, EVENT_DESCRIPTOR *))(*(_QWORD *)ppv + 48LL))(
                ppv,
                v17 + 84,
                &EventDescriptor);
        if ( v20 >= 0 )
        {
          v20 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)&EventDescriptor.Id + 96LL))(
                  *(_QWORD *)&EventDescriptor.Id,
                  &v45);
          if ( v20 >= 0 )
          {
            v20 = 0;
            v19 = v45 & 1;
          }
        }
      }
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( *(_QWORD *)&EventDescriptor.Id )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&EventDescriptor.Id + 16LL))(*(_QWORD *)&EventDescriptor.Id);
      v21 = v20 < 0;
      v16 = v47;
      if ( !v21 )
        LOBYTE(v18) = v19 != 0;
      v6 = v46;
    }
    v45 = v18;
    v9 = *(_QWORD *)&v52.Id;
    RtlAcquireSRWLockExclusive(*(_QWORD *)&v52.Id + 48LL);
    *(_DWORD *)(v9 + 56) = GetCurrentThreadId();
    if ( (*(_BYTE *)(v9 + 41) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v9 + 24) + 8LL),
          0);
      v16 = 1223;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(v9 + 24) + 8LL));
    if ( a6 )
    {
      RtlAcquireSRWLockExclusive(v9 + 208);
      *(_DWORD *)(v9 + 216) = GetCurrentThreadId();
      v22 = *(struct _UBPM_REPETITION_CONTEXT **)(v9 + 240);
      if ( v22 != (struct _UBPM_REPETITION_CONTEXT *)(v9 + 240) )
      {
        while ( 1 )
        {
          v48 = v22;
          if ( *((_QWORD *)v22 + 5) == a2 )
            break;
          v22 = *(struct _UBPM_REPETITION_CONTEXT **)v22;
          if ( v22 == (struct _UBPM_REPETITION_CONTEXT *)(v9 + 240) )
            goto LABEL_39;
        }
        if ( *((_DWORD *)v22 + 20) )
        {
          v23 = v46;
          v10 = 0;
          v24 = *(_DWORD *)(*v46 + 20);
          if ( v24 )
          {
            while ( *(_QWORD *)(*(_QWORD *)(v9 + 32) + 40LL * v10) != *((_QWORD *)v22 + 4) )
            {
              if ( ++v10 >= v24 )
                goto LABEL_57;
            }
            v25 = *((_QWORD *)v22 + 11);
            if ( v25 )
            {
              v26 = *((_DWORD *)v22 + 24) - 20;
              v27 = v25 + 16;
            }
            else
            {
              v26 = 0;
              v27 = 0;
            }
            UbpmpPerformTriggerActions((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v9, v27, v26);
            v28 = v48;
            v29 = *((_DWORD *)v48 + 20);
            if ( v29 != -1 )
            {
              *((_DWORD *)v48 + 20) = v29 - 1;
              v28 = v48;
            }
            if ( !*((_QWORD *)v28 + 8) && !*((_DWORD *)v28 + 20) )
            {
              v30 = UbpmpSubmitDeleteRepetitionContextWork(v28);
              v16 = v30;
              if ( v30 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    54,
                    (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                    *(_QWORD *)(*v23 + 8),
                    v30);
              }
            }
          }
LABEL_57:
          *(_DWORD *)(v9 + 216) = 0;
          RtlReleaseSRWLockExclusive(v9 + 208);
          v6 = v23;
          goto LABEL_62;
        }
      }
LABEL_39:
      *(_DWORD *)(v9 + 216) = 0;
      RtlReleaseSRWLockExclusive(v9 + 208);
    }
    else
    {
      v31 = v46;
      v10 = 0;
      v32 = *(_DWORD *)(*v46 + 20);
      if ( !v32 )
      {
LABEL_61:
        v6 = v46;
        goto LABEL_62;
      }
      while ( *(_QWORD *)(*(_QWORD *)(v9 + 32) + 40LL * v10) != a2 )
      {
        if ( ++v10 >= v32 )
          goto LABEL_61;
      }
      v37 = *(_QWORD *)(*v46 + 24) + 48LL * v10;
      v38 = _InterlockedExchangeAdd64((volatile signed __int64 *)&g_ullCollectionId, 1u);
      if ( *(_DWORD *)(v37 + 16) )
      {
        v40 = v51;
      }
      else
      {
        RtlAcquireSRWLockExclusive(v9 + 208);
        CurrentThreadId = GetCurrentThreadId();
        v40 = v51;
        *(_DWORD *)(v9 + 216) = CurrentThreadId;
        if ( v40 )
        {
          v41 = (__int64)v40 + 16;
          v42 = a5 - 20;
        }
        else
        {
          v42 = 0;
          v41 = 0;
        }
        UbpmpPerformTriggerActions((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v9, v41, v42);
        *(_DWORD *)(v9 + 216) = 0;
        RtlReleaseSRWLockExclusive(v9 + 208);
        v31 = v46;
      }
      v43 = *(_DWORD *)(v37 + 16);
      if ( !v43 && !*(_DWORD *)(v37 + 24) )
      {
        v16 = v47;
        v6 = v46;
        goto LABEL_62;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_ddS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)WPP_GLOBAL_Control,
          v43,
          *(_DWORD *)(v37 + 24),
          v43,
          *(_QWORD *)(*v31 + 8));
      v44 = UbpmpScheduleRepetitionSeries((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v9, v10, v38 + 1, v40, a5, 0, &v48);
      v16 = v44;
      if ( v44 )
      {
        v6 = v46;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *(_QWORD *)(*v46 + 8),
            v44);
        goto LABEL_62;
      }
    }
    v6 = v46;
LABEL_62:
    *(_DWORD *)(v9 + 56) = 0;
    RtlReleaseSRWLockExclusive(v9 + 48);
LABEL_63:
    UbpmConsumerDecPendingActions(v9);
  }
  UbpmTelemTriggerArrived(v9, v10, v16);
  result = dword_18004F0F0;
  if ( (unsigned int)dword_18004F0F0 > 4 )
  {
    v34 = *v6;
    v45 = v16;
    v61 = 4;
    v35 = *(__int64 **)(v34 + 8);
    v60 = &v45;
    if ( v35 )
    {
      do
        v14 = *((_WORD *)v35 + ++v11) == 0;
      while ( !v14 );
      v36 = 2 * v11 + 2;
    }
    else
    {
      v35 = &qword_1800439C0;
      v36 = 2;
    }
    *(_DWORD *)&v52.Level = 516;
    UserData.Ptr = (ULONGLONG)off_18004F0F8;
    v57 = v35;
    v59 = 0;
    v52.Keyword = 0;
    v58 = v36;
    *(_DWORD *)&v52.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_18004F0F8;
    v54 = &dword_1800460CC;
    UserData.Reserved = 2;
    v55 = 40;
    v56 = 1;
    v47 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EventWriteTransfer(RegHandle, &v52, 0, 0, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1800282b0  mov     [rsp-8+arg_8], rbx
0x1800282b5  push    rbp
0x1800282b6  push    rsi
0x1800282b7  push    rdi
0x1800282b8  push    r12
0x1800282ba  push    r13
0x1800282bc  push    r14
0x1800282be  push    r15
0x1800282c0  lea     rbp, [rsp-17h]
0x1800282c5  sub     rsp, 0E0h
0x1800282cc  mov     rax, cs:__security_cookie
0x1800282d3  xor     rax, rsp
0x1800282d6  mov     [rbp+47h+var_40], rax
0x1800282da  mov     eax, cs:dword_18004F0F0
0x1800282e0  lea     r15, [rcx+18h]
0x1800282e4  mov     r13, rdx
0x1800282e7  mov     qword ptr [rbp+47h+var_90.Id], rcx
0x1800282eb  xor     edx, edx
0x1800282ed  mov     [rsp+110h+var_C8], r15
0x1800282f2  mov     [rbp+47h+var_B8], rdx
0x1800282f6  mov     rbx, r9
0x1800282f9  mov     [rbp+47h+var_98], rbx
0x1800282fd  mov     r12, rcx
0x180028300  lea     r8, _TraceLoggingMetadata
0x180028307  mov     edi, 0FFFFh
0x18002830c  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180028313  cmp     eax, 4
0x180028316  jbe     loc_1800283E2
0x18002831c  mov     rax, [r15]
0x18002831f  mov     rcx, [rax+8]
0x180028323  test    rcx, rcx
0x180028326  jz      short loc_180028344
0x180028328  mov     rax, r14
0x18002832b  nop     dword ptr [rax+rax+00h]
0x180028330  cmp     [rcx+rax*2+2], dx
0x180028335  lea     rax, [rax+1]
0x180028339  jnz     short loc_180028330
0x18002833b  lea     eax, ds:2[rax*2]
0x180028342  jmp     short loc_180028350
0x180028344  lea     rcx, qword_1800439C0
0x18002834b  mov     eax, 2
0x180028350  mov     [rbp+47h+var_58], eax
0x180028353  xor     r9d, r9d; RelatedActivityId
0x180028356  movzx   eax, cs:word_180046171
0x18002835d  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180028360  mov     rax, cs:off_18004F0F8
0x180028367  mov     [rbp+47h+var_80.Ptr], rax
0x18002836b  mov     [rbp+47h+var_60], rcx
0x18002836f  mov     [rbp+47h+var_54], edx
0x180028372  mov     [rbp+47h+EventDescriptor.Keyword], rdx
0x180028376  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18002837a  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x180028381  movzx   eax, word ptr [rax]
0x180028384  mov     [rbp+47h+var_80.Size], eax
0x180028387  lea     rax, byte_18004617B
0x18002838e  mov     [rbp+47h+var_70], rax
0x180028392  lea     rax, _TraceLoggingMetadataEnd
0x180028399  sub     eax, r8d
0x18002839c  mov     dword ptr [rbp+47h+var_80.0Ch], 2
0x1800283a3  mov     [rbp+47h+var_68], 1Dh
0x1800283aa  xor     r8d, r8d; ActivityId
0x1800283ad  mov     [rbp+47h+var_64], 1
0x1800283b4  mov     [rsp+110h+var_D0], eax
0x1800283b8  mov     eax, [rsp+110h+var_D0]
0x1800283bc  mov     rcx, cs:RegHandle; RegHandle
0x1800283c3  lea     rax, [rbp+47h+var_80]
0x1800283c7  mov     [rsp+110h+UserData], rax; UserData
0x1800283cc  mov     [rsp+110h+UserDataCount], 3; UserDataCount
0x1800283d4  call    cs:__imp_EventWriteTransfer
0x1800283db  nop     dword ptr [rax+rax+00h]
0x1800283e0  jmp     short loc_1800283E7
0x1800283e2  mov     [rsp+110h+var_C8], r15
0x1800283e7  mov     rcx, r12
0x1800283ea  call    UbpmConsumerIncPendingActions
0x1800283ef  mov     [rbp+47h+var_C0], eax
0x1800283f2  mov     esi, eax
0x1800283f4  test    eax, eax
0x1800283f6  jnz     loc_1800287C0
0x1800283fc  test    rbx, rbx
0x1800283ff  jz      short loc_180028454
0x180028401  cmp     [rbp+47h+arg_20], 14h
0x180028405  jnb     short loc_180028454
0x180028407  mov     esi, 57h ; 'W'
0x18002840c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028413  lea     rax, WPP_GLOBAL_Control
0x18002841a  cmp     rcx, rax
0x18002841d  jz      loc_1800287B8
0x180028423  test    byte ptr [rcx+1Ch], 1
0x180028427  jz      loc_1800287B8
0x18002842d  mov     r9, [r12+18h]
0x180028432  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180028439  mov     rcx, [rcx+10h]
0x18002843d  mov     edx, 33h ; '3'
0x180028442  mov     [rsp+110h+UserDataCount], esi
0x180028446  mov     r9, [r9+8]
0x18002844a  call    WPP_SF_Sd
0x18002844f  jmp     loc_1800287B8
0x180028454  mov     r12, [r15]
0x180028457  lea     rcx, [rbp+47h+EventDescriptor]; Buf1
0x18002845b  xorps   xmm0, xmm0
0x18002845e  mov     r8d, 10h; Size
0x180028464  xor     ebx, ebx
0x180028466  movups  xmmword ptr [rbp+47h+EventDescriptor.Id], xmm0
0x18002846a  lea     rdx, [r12+54h]; Buf2
0x18002846f  call    memcmp_0
0x180028474  test    eax, eax
0x180028476  jz      loc_18002853F
0x18002847c  xor     eax, eax
0x18002847e  lea     r9, IID_INetworkListManagerPrivate; riid
0x180028485  mov     r15d, eax
0x180028488  mov     [rsp+110h+var_D0], eax
0x18002848c  mov     [rbp+47h+ppv], rax
0x180028490  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180028497  mov     qword ptr [rbp+47h+EventDescriptor.Id], rax
0x18002849b  xor     edx, edx; pUnkOuter
0x18002849d  lea     rax, [rbp+47h+ppv]
0x1800284a1  mov     r8d, 4; dwClsContext
0x1800284a7  mov     qword ptr [rsp+110h+UserDataCount], rax; ppv
0x1800284ac  call    cs:__imp_CoCreateInstance
0x1800284b3  nop     dword ptr [rax+rax+00h]
0x1800284b8  mov     esi, eax
0x1800284ba  test    eax, eax
0x1800284bc  js      short loc_180028503
0x1800284be  mov     rcx, [rbp+47h+ppv]
0x1800284c2  lea     r8, [rbp+47h+EventDescriptor]
0x1800284c6  lea     rdx, [r12+54h]
0x1800284cb  mov     rax, [rcx]
0x1800284ce  mov     rax, [rax+30h]
0x1800284d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284d7  mov     esi, eax
0x1800284d9  test    eax, eax
0x1800284db  js      short loc_180028503
0x1800284dd  mov     rcx, qword ptr [rbp+47h+EventDescriptor.Id]
0x1800284e1  lea     rdx, [rsp+110h+var_D0]
0x1800284e6  mov     rax, [rcx]
0x1800284e9  mov     rax, [rax+60h]
0x1800284ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284f2  mov     esi, eax
0x1800284f4  test    eax, eax
0x1800284f6  js      short loc_180028503
0x1800284f8  mov     r15d, [rsp+110h+var_D0]
0x1800284fd  xor     esi, esi
0x1800284ff  and     r15d, 1
0x180028503  mov     rcx, [rbp+47h+ppv]
0x180028507  test    rcx, rcx
0x18002850a  jz      short loc_180028518
0x18002850c  mov     rax, [rcx]
0x18002850f  mov     rax, [rax+10h]
0x180028513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028518  mov     rcx, qword ptr [rbp+47h+EventDescriptor.Id]
0x18002851c  test    rcx, rcx
0x18002851f  jz      short loc_18002852D
0x180028521  mov     rax, [rcx]
0x180028524  mov     rax, [rax+10h]
0x180028528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002852d  test    esi, esi
0x18002852f  mov     esi, [rbp+47h+var_C0]
0x180028532  js      short loc_18002853A
0x180028534  test    r15d, r15d
0x180028537  setnz   bl
0x18002853a  mov     r15, [rsp+110h+var_C8]
0x18002853f  mov     [rsp+110h+var_D0], ebx
0x180028543  mov     r12, qword ptr [rbp+47h+var_90.Id]
0x180028547  lea     rcx, [r12+30h]
0x18002854c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180028553  nop     dword ptr [rax+rax+00h]
0x180028558  call    cs:__imp_GetCurrentThreadId
0x18002855f  nop     dword ptr [rax+rax+00h]
0x180028564  mov     [r12+38h], eax
0x180028569  test    byte ptr [r12+29h], 1
0x18002856f  jnz     short loc_1800285BA
0x180028571  mov     rcx, cs:WPP_GLOBAL_Control
0x180028578  lea     rax, WPP_GLOBAL_Control
0x18002857f  cmp     rcx, rax
0x180028582  jz      short loc_1800285B0
0x180028584  test    byte ptr [rcx+1Ch], 1
0x180028588  jz      short loc_1800285B0
0x18002858a  mov     r9, [r12+18h]
0x18002858f  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180028596  mov     rcx, [rcx+10h]
0x18002859a  mov     edx, 34h ; '4'
0x18002859f  mov     [rsp+110h+UserDataCount], 0
0x1800285a7  mov     r9, [r9+8]
0x1800285ab  call    WPP_SF_Sd
0x1800285b0  mov     esi, 4C7h
0x1800285b5  jmp     loc_18002879E
0x1800285ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285c1  lea     r15, WPP_GLOBAL_Control
0x1800285c8  cmp     rcx, r15
0x1800285cb  jz      short loc_1800285F4
0x1800285cd  test    dword ptr [rcx+1Ch], 200h
0x1800285d4  jz      short loc_1800285F4
0x1800285d6  mov     r9, [r12+18h]
0x1800285db  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x1800285e2  mov     rcx, [rcx+10h]
0x1800285e6  mov     edx, 35h ; '5'
0x1800285eb  mov     r9, [r9+8]
0x1800285ef  call    WPP_SF_S
0x1800285f4  cmp     [rbp+47h+arg_28], 0
0x1800285f8  jz      loc_18002875F
0x1800285fe  lea     rbx, [r12+0D0h]
0x180028606  mov     rcx, rbx
0x180028609  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180028610  nop     dword ptr [rax+rax+00h]
0x180028615  call    cs:__imp_GetCurrentThreadId
0x18002861c  nop     dword ptr [rax+rax+00h]
0x180028621  mov     [rbx+8], eax
0x180028624  lea     rax, [r12+0F0h]
0x18002862c  mov     r9, [rax]
0x18002862f  cmp     r9, rax
0x180028632  jz      short loc_180028646
0x180028634  mov     [rbp+47h+var_B8], r9
0x180028638  cmp     [r9+28h], r13
0x18002863c  jz      short loc_180028666
0x18002863e  mov     r9, [r9]
0x180028641  cmp     r9, rax
0x180028644  jnz     short loc_180028634
0x180028646  mov     rcx, rbx
0x180028649  mov     dword ptr [rbx+8], 0
0x180028650  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180028657  nop     dword ptr [rax+rax+00h]
0x18002865c  mov     r15, [rsp+110h+var_C8]
0x180028661  jmp     loc_18002879E
0x180028666  cmp     dword ptr [r9+50h], 0
0x18002866b  jbe     short loc_180028646
0x18002866d  mov     r13, [rsp+110h+var_C8]
0x180028672  xor     eax, eax
0x180028674  movzx   edi, ax
0x180028677  mov     rax, [r13+0]
0x18002867b  mov     edx, [rax+14h]
0x18002867e  test    edx, edx
0x180028680  jz      loc_180028744
0x180028686  mov     r8, [r9+20h]
0x18002868a  mov     r10, [r12+20h]
0x18002868f  nop
0x180028690  movzx   eax, di
0x180028693  lea     rcx, [rax+rax*4]
0x180028697  cmp     [r10+rcx*8], r8
0x18002869b  jz      short loc_1800286AC
0x18002869d  inc     di
0x1800286a0  movzx   eax, di
0x1800286a3  cmp     eax, edx
0x1800286a5  jb      short loc_180028690
0x1800286a7  jmp     loc_180028744
0x1800286ac  mov     rcx, [r9+58h]
0x1800286b0  test    rcx, rcx
0x1800286b3  jz      short loc_1800286C2
0x1800286b5  mov     eax, [r9+60h]
0x1800286b9  sub     eax, 14h
0x1800286bc  add     rcx, 10h
0x1800286c0  jmp     short loc_1800286C6
0x1800286c2  xor     eax, eax
0x1800286c4  xor     ecx, ecx
0x1800286c6  mov     r9, [r9+10h]
0x1800286ca  lea     rdx, [rsp+110h+var_D0]
0x1800286cf  mov     dword ptr [rsp+110h+UserData], eax; int
0x1800286d3  movzx   r8d, di
0x1800286d7  mov     qword ptr [rsp+110h+UserDataCount], rcx; __int64
0x1800286dc  mov     rcx, r12; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x1800286df  call    UbpmpPerformTriggerActions
0x1800286e4  mov     rcx, [rbp+47h+var_B8]
0x1800286e8  mov     eax, [rcx+50h]
0x1800286eb  cmp     eax, 0FFFFFFFFh
0x1800286ee  jz      short loc_1800286F9
0x1800286f0  dec     eax
0x1800286f2  mov     [rcx+50h], eax
0x1800286f5  mov     rcx, [rbp+47h+var_B8]; struct _UBPM_REPETITION_CONTEXT *
0x1800286f9  cmp     qword ptr [rcx+40h], 0
0x1800286fe  jnz     short loc_180028744
0x180028700  cmp     dword ptr [rcx+50h], 0
0x180028704  jnz     short loc_180028744
0x180028706  call    ?UbpmpSubmitDeleteRepetitionContextWork@@YAKPEAU_UBPM_REPETITION_CONTEXT@@@Z; UbpmpSubmitDeleteRepetitionContextWork(_UBPM_REPETITION_CONTEXT *)
0x18002870b  mov     esi, eax
0x18002870d  test    eax, eax
0x18002870f  jz      short loc_180028744
0x180028711  mov     rcx, cs:WPP_GLOBAL_Control
0x180028718  cmp     rcx, r15
0x18002871b  jz      short loc_180028744
0x18002871d  test    byte ptr [rcx+1Ch], 1
0x180028721  jz      short loc_180028744
0x180028723  mov     r9, [r13+0]
0x180028727  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18002872e  mov     rcx, [rcx+10h]
0x180028732  mov     edx, 36h ; '6'
0x180028737  mov     [rsp+110h+UserDataCount], eax
0x18002873b  mov     r9, [r9+8]
0x18002873f  call    WPP_SF_Sd
0x180028744  mov     rcx, rbx
0x180028747  mov     dword ptr [rbx+8], 0
0x18002874e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180028755  nop     dword ptr [rax+rax+00h]
0x18002875a  mov     r15, r13
0x18002875d  jmp     short loc_18002879E
0x18002875f  mov     r10, [rsp+110h+var_C8]
0x180028764  xor     eax, eax
0x180028766  movzx   edi, ax
0x180028769  mov     r9, [r10]
0x18002876c  mov     edx, [r9+14h]
0x180028770  test    edx, edx
0x180028772  jz      short loc_18002879B
  ... truncated ...
```
