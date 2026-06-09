# UbpmpToggleMaintenancePdcActivator

- ea: `0x18002ef50`
- end: `0x18002f53d`
- name: `UbpmpToggleMaintenancePdcActivator`
- size: `1517`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002b760`

## callees

- `0x18002db10`
- `0x18002ecd8`
- `0x18002ef50`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18002f3bc`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002f411`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002f3bc`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002f411`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002f13e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002f177`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002f13e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002f177`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ef83`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002f196`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002f1c7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ef83`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002f196`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002f1c7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002f0ec`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002f38c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002f3b3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002f0ec`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002f38c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002f3b3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002f0d0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002f36d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002f514`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002f0d0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002f36d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002f514`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f113`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f11e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f3eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f113`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f11e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f3eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ef89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f19c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f1cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ef89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f19c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f1cd`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x18002f266`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x18002f266`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002f26f`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002f26f`

## pseudocode

```c
int __fastcall UbpmpToggleMaintenancePdcActivator(int a1)
{
  unsigned int v2; // esi
  unsigned __int8 v3; // cl
  int v4; // r12d
  DWORD v5; // edi
  _QWORD *Value; // rbx
  _QWORD *v7; // r14
  char *v8; // r13
  char *v9; // rbx
  _QWORD *v10; // rdi
  _QWORD *v11; // rdx
  __int64 v12; // rsi
  int *v13; // rbx
  __int64 v14; // rax
  bool v15; // zf
  unsigned int v16; // eax
  __int64 *v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  unsigned int v21; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-65h]
  int v23; // [rsp+38h] [rbp-61h] BYREF
  int v24; // [rsp+3Ch] [rbp-5Dh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-59h] BYREF
  __int64 v26; // [rsp+50h] [rbp-49h] BYREF
  __int128 v27; // [rsp+60h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-29h] BYREF
  __int16 *v29; // [rsp+80h] [rbp-19h]
  int v30; // [rsp+88h] [rbp-11h]
  int v31; // [rsp+8Ch] [rbp-Dh]
  int *v32; // [rsp+90h] [rbp-9h]
  __int64 v33; // [rsp+98h] [rbp-1h]
  int *v34; // [rsp+A0h] [rbp+7h]
  __int64 v35; // [rsp+A8h] [rbp+Fh]
  unsigned int *v36; // [rsp+B0h] [rbp+17h]
  __int64 v37; // [rsp+B8h] [rbp+1Fh]

  RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
  dword_18004CEE8 = GetCurrentThreadId();
  v22 = 0;
  v2 = 0;
  v26 = 0;
  if ( a1 )
  {
    v3 = 0;
LABEL_5:
    UbpmTakeMaintenancePdcReference(v3);
    goto LABEL_6;
  }
  if ( dword_18004CB7C + dword_18004CBBC + dword_18004CBFC + dword_18004CC3C + dword_18004CC7C )
  {
    v3 = 1;
    goto LABEL_5;
  }
LABEL_6:
  if ( (unsigned int)dword_18004C0F0 > 5 && (qword_18004C100 & 4) != 0 && (qword_18004C108 & 4) == qword_18004C108 )
  {
    v34 = &v23;
    v32 = &v24;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18004C0F8;
    v23 = dword_18004CB7C + dword_18004CBBC + dword_18004CBFC + dword_18004CC3C + dword_18004CC7C;
    v24 = a1;
    v35 = 4;
    v33 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 4;
    UserData.Size = *(unsigned __int16 *)off_18004C0F8;
    v29 = &word_180043F7E;
    UserData.Reserved = 2;
    v30 = 76;
    v31 = 1;
    v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  dword_18004CEE8 = 0;
  RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
  if ( !qword_18004CB48 )
  {
    v4 = 10;
    goto LABEL_48;
  }
  v5 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    Value = TlsGetValue(UbpmpLockTrackerId);
    if ( (*(_QWORD *)TlsGetValue(v5) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      __int2c();
    *Value |= 2uLL;
    ++Value[2];
  }
  RtlAcquireSRWLockShared(&g_ConsumerListLock);
  v7 = g_leConsumerListHead;
  if ( g_leConsumerListHead != (_UNKNOWN *)&g_leConsumerListHead )
  {
LABEL_17:
    v8 = (char *)(v7 + 5);
    RtlAcquireSRWLockShared(v7 + 5);
    if ( !*(_QWORD *)(v7[2] + 48LL) )
      goto LABEL_40;
    v9 = (char *)(v7 + 25);
    RtlAcquireSRWLockExclusive(v7 + 25);
    *((_DWORD *)v7 + 52) = GetCurrentThreadId();
    v10 = (_QWORD *)v7[27];
    if ( v10 == v7 + 27 )
      goto LABEL_39;
    while ( 1 )
    {
      RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
      dword_18004CEE8 = GetCurrentThreadId();
      if ( qword_18004CB38 )
      {
        if ( byte_18004CB40 != 1 )
          goto LABEL_25;
        if ( !v10[2] )
          break;
      }
LABEL_37:
      dword_18004CEE8 = 0;
      RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
      v10 = (_QWORD *)*v10;
      if ( v10 == v7 + 27 )
      {
        v8 = (char *)(v7 + 5);
        v9 = (char *)(v7 + 25);
LABEL_39:
        *((_DWORD *)v9 + 2) = 0;
        RtlReleaseSRWLockExclusive(v9);
LABEL_40:
        RtlReleaseSRWLockShared(v8);
        v7 = (_QWORD *)*v7;
        if ( v7 == &g_leConsumerListHead )
        {
          v2 = v22;
          goto LABEL_42;
        }
        goto LABEL_17;
      }
    }
    v11 = (_QWORD *)v7[2];
    v27 = *(_OWORD *)((char *)v10 + 52);
    if ( (int)UbpmpSleepStudyStartReportingBlocker(qword_18004CB48, *v11, v11[1], &v27, &v26) >= 0 )
    {
      v10[2] = v26;
      v26 = 0;
    }
    else
    {
      v22 = 10;
    }
LABEL_25:
    if ( !byte_18004CB40 )
    {
      v12 = v10[2];
      if ( v12 )
      {
        v13 = *(int **)(v7[2] + 8LL);
        SleepstudyHelperBlockerActiveDereference(v10[2]);
        SleepstudyHelperDestroyBlocker(v12);
        if ( (unsigned int)dword_18004C0F0 > 5 && (qword_18004C100 & 4) != 0 && (qword_18004C108 & 4) == qword_18004C108 )
        {
          if ( v13 )
          {
            v14 = -1;
            do
              v15 = *((_WORD *)v13 + ++v14) == 0;
            while ( !v15 );
            v16 = 2 * v14 + 2;
          }
          else
          {
            v13 = &dword_1800405F4;
            v16 = 2;
          }
          v33 = v16;
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (ULONGLONG)off_18004C0F8;
          v32 = v13;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 4;
          UserData.Size = *(unsigned __int16 *)off_18004C0F8;
          v29 = (__int16 *)byte_180043F45;
          UserData.Reserved = 2;
          v30 = 45;
          v31 = 1;
          v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        v10[2] = 0;
      }
    }
    goto LABEL_37;
  }
LABEL_42:
  if ( UbpmpLockTrackerId != -1 )
  {
    v17 = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
    v18 = *v17;
    if ( (*v17 & 2) == 0 )
      __int2c();
    v15 = v17[2]-- == 1;
    if ( v15 )
      *v17 = v18 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  RtlReleaseSRWLockShared(&g_ConsumerListLock);
  v4 = 0;
LABEL_48:
  LODWORD(v19) = dword_18004C0F0;
  if ( (unsigned int)dword_18004C0F0 > 5 )
  {
    LODWORD(v19) = qword_18004C100;
    if ( (qword_18004C100 & 4) != 0 )
    {
      v19 = qword_18004C108 & 4;
      if ( v19 == qword_18004C108 )
      {
        v21 = v2;
        v36 = &v21;
        v24 = 0;
        v34 = &v24;
        v23 = v4;
        v32 = &v23;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_18004C0F8;
        v37 = 4;
        v35 = 4;
        v33 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 4;
        UserData.Size = *(unsigned __int16 *)off_18004C0F8;
        v29 = word_180044222;
        UserData.Reserved = 2;
        v30 = 88;
        v31 = 1;
        v22 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        LODWORD(v19) = EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
      }
    }
  }
  return v19;
}

```

## disassembly

```asm
0x18002ef50  push    rbp
0x18002ef52  push    rsi
0x18002ef53  push    rdi
0x18002ef54  push    r14
0x18002ef56  push    r15
0x18002ef58  lea     rbp, [rsp-37h]
0x18002ef5d  sub     rsp, 0D0h
0x18002ef64  mov     rax, cs:__security_cookie
0x18002ef6b  xor     rax, rsp
0x18002ef6e  mov     [rbp+57h+var_30], rax
0x18002ef72  mov     [rsp+0F0h+arg_0], rbx
0x18002ef7a  mov     ebx, ecx
0x18002ef7c  lea     rcx, g_MaintenanceLaunchLock
0x18002ef83  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002ef89  call    cs:__imp_GetCurrentThreadId
0x18002ef8f  xor     r15d, r15d
0x18002ef92  mov     cs:dword_18004CEE8, eax
0x18002ef98  mov     [rbp+57h+var_BC], r15d
0x18002ef9c  mov     esi, r15d
0x18002ef9f  mov     [rbp+57h+var_A0], r15
0x18002efa3  test    ebx, ebx
0x18002efa5  jz      short loc_18002EFAB
0x18002efa7  xor     ecx, ecx
0x18002efa9  jmp     short loc_18002EFCD
0x18002efab  mov     edx, cs:dword_18004CC7C
0x18002efb1  add     edx, cs:dword_18004CC3C
0x18002efb7  add     edx, cs:dword_18004CBFC
0x18002efbd  add     edx, cs:dword_18004CBBC
0x18002efc3  add     edx, cs:dword_18004CB7C
0x18002efc9  jz      short loc_18002EFD2
0x18002efcb  mov     cl, 1; unsigned __int8
0x18002efcd  call    ?UbpmTakeMaintenancePdcReference@@YAXE@Z; UbpmTakeMaintenancePdcReference(uchar)
0x18002efd2  mov     eax, cs:dword_18004C0F0
0x18002efd8  lea     rdi, _TraceLoggingMetadataEnd
0x18002efdf  lea     r14, _TraceLoggingMetadata
0x18002efe6  cmp     eax, 5
0x18002efe9  jbe     loc_18002F0D6
0x18002efef  mov     rcx, cs:qword_18004C108
0x18002eff6  mov     rax, cs:qword_18004C100
0x18002effd  test    al, 4
0x18002efff  jz      loc_18002F0D6
0x18002f005  mov     rax, rcx
0x18002f008  and     eax, 4
0x18002f00b  cmp     rax, rcx
0x18002f00e  jnz     loc_18002F0D6
0x18002f014  mov     edx, cs:dword_18004CC7C
0x18002f01a  lea     rax, [rbp+57h+var_B8]
0x18002f01e  add     edx, cs:dword_18004CC3C
0x18002f024  xor     r9d, r9d; RelatedActivityId
0x18002f027  add     edx, cs:dword_18004CBFC
0x18002f02d  xor     r8d, r8d; ActivityId
0x18002f030  add     edx, cs:dword_18004CBBC
0x18002f036  add     edx, cs:dword_18004CB7C
0x18002f03c  mov     [rbp+57h+var_50], rax
0x18002f040  lea     rax, [rbp+57h+var_B4]
0x18002f044  mov     [rbp+57h+var_60], rax
0x18002f048  movzx   eax, cs:word_180043F74
0x18002f04f  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18002f052  mov     rax, cs:off_18004C0F8
0x18002f059  mov     [rbp+57h+var_80.Ptr], rax
0x18002f05d  mov     [rbp+57h+var_B8], edx
0x18002f060  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18002f064  mov     [rbp+57h+var_B4], ebx
0x18002f067  mov     [rbp+57h+var_48], 4
0x18002f06f  mov     [rbp+57h+var_58], 4
0x18002f077  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18002f07e  mov     [rbp+57h+EventDescriptor.Keyword], 4
0x18002f086  movzx   eax, word ptr [rax]
0x18002f089  mov     [rbp+57h+var_80.Size], eax
0x18002f08c  lea     rax, word_180043F7E
0x18002f093  mov     [rbp+57h+var_70], rax
0x18002f097  mov     rax, rdi
0x18002f09a  sub     eax, r14d
0x18002f09d  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18002f0a4  mov     [rbp+57h+var_68], 4Ch ; 'L'
0x18002f0ab  mov     [rbp+57h+var_64], 1
0x18002f0b2  mov     [rbp+57h+var_C0], eax
0x18002f0b5  mov     eax, [rbp+57h+var_C0]
0x18002f0b8  mov     rcx, cs:RegHandle; RegHandle
0x18002f0bf  lea     rax, [rbp+57h+var_80]
0x18002f0c3  mov     [rsp+0F0h+UserData], rax; UserData
0x18002f0c8  mov     [rsp+0F0h+UserDataCount], 4; UserDataCount
0x18002f0d0  call    cs:__imp_EventWriteTransfer
0x18002f0d6  lea     rcx, g_MaintenanceLaunchLock
0x18002f0dd  mov     [rsp+0F0h+arg_8], r12
0x18002f0e5  mov     cs:dword_18004CEE8, r15d
0x18002f0ec  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002f0f2  cmp     cs:qword_18004CB48, rsi
0x18002f0f9  jnz     short loc_18002F106
0x18002f0fb  mov     r12d, 0Ah
0x18002f101  jmp     loc_18002F428
0x18002f106  mov     edi, cs:UbpmpLockTrackerId
0x18002f10c  cmp     edi, 0FFFFFFFFh
0x18002f10f  jz      short loc_18002F137
0x18002f111  mov     ecx, edi; dwTlsIndex
0x18002f113  call    cs:__imp_TlsGetValue
0x18002f119  mov     ecx, edi; dwTlsIndex
0x18002f11b  mov     rbx, rax
0x18002f11e  call    cs:__imp_TlsGetValue
0x18002f124  test    qword ptr [rax], 0FFFFFFFFFFFFFFFEh
0x18002f12b  jz      short loc_18002F12F
0x18002f12d  int     2Ch; Windows NT - assertion failure
0x18002f12f  or      qword ptr [rbx], 2
0x18002f133  inc     qword ptr [rbx+10h]
0x18002f137  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x18002f13e  call    cs:__imp_RtlAcquireSRWLockShared
0x18002f144  mov     r14, cs:g_leConsumerListHead
0x18002f14b  lea     rax, g_leConsumerListHead
0x18002f152  cmp     r14, rax
0x18002f155  jz      loc_18002F3E0
0x18002f15b  mov     [rsp+0F0h+arg_10], r13
0x18002f163  mov     r12d, 0Ah
0x18002f169  nop     dword ptr [rax+00000000h]
0x18002f170  lea     r13, [r14+28h]
0x18002f174  mov     rcx, r13
0x18002f177  call    cs:__imp_RtlAcquireSRWLockShared
0x18002f17d  mov     rax, [r14+10h]
0x18002f181  cmp     qword ptr [rax+30h], 0
0x18002f186  jz      loc_18002F3B9
0x18002f18c  lea     rbx, [r14+0C8h]
0x18002f193  mov     rcx, rbx
0x18002f196  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002f19c  call    cs:__imp_GetCurrentThreadId
0x18002f1a2  lea     r15, [r14+0D8h]
0x18002f1a9  mov     [rbx+8], eax
0x18002f1ac  mov     rdi, [r15]
0x18002f1af  cmp     rdi, r15
0x18002f1b2  jz      loc_18002F3A9
0x18002f1b8  lea     r13, _TraceLoggingMetadataEnd
0x18002f1bf  nop
0x18002f1c0  lea     rcx, g_MaintenanceLaunchLock
0x18002f1c7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002f1cd  call    cs:__imp_GetCurrentThreadId
0x18002f1d3  cmp     cs:qword_18004CB38, 0
0x18002f1db  mov     cs:dword_18004CEE8, eax
0x18002f1e1  jz      loc_18002F37B
0x18002f1e7  cmp     cs:byte_18004CB40, 1
0x18002f1ee  jnz     short loc_18002F241
0x18002f1f0  cmp     qword ptr [rdi+10h], 0
0x18002f1f5  jnz     loc_18002F37B
0x18002f1fb  mov     rdx, [r14+10h]
0x18002f1ff  lea     rax, [rbp+57h+var_A0]
0x18002f203  movups  xmm0, xmmword ptr [rdi+34h]
0x18002f207  mov     rcx, cs:qword_18004CB48
0x18002f20e  lea     r9, [rbp+57h+var_90]
0x18002f212  mov     qword ptr [rsp+0F0h+UserDataCount], rax
0x18002f217  movaps  [rbp+57h+var_90], xmm0
0x18002f21b  mov     r8, [rdx+8]
0x18002f21f  mov     rdx, [rdx]
0x18002f222  call    UbpmpSleepStudyStartReportingBlocker
0x18002f227  test    eax, eax
0x18002f229  jns     short loc_18002F231
0x18002f22b  mov     [rbp+57h+var_BC], r12d
0x18002f22f  jmp     short loc_18002F241
0x18002f231  mov     rax, [rbp+57h+var_A0]
0x18002f235  mov     [rdi+10h], rax
0x18002f239  mov     [rbp+57h+var_A0], 0
0x18002f241  cmp     cs:byte_18004CB40, 0
0x18002f248  jnz     loc_18002F37B
0x18002f24e  mov     rsi, [rdi+10h]
0x18002f252  test    rsi, rsi
0x18002f255  jz      loc_18002F37B
0x18002f25b  mov     rax, [r14+10h]
0x18002f25f  mov     rcx, rsi
0x18002f262  mov     rbx, [rax+8]
0x18002f266  call    cs:__imp_SleepstudyHelperBlockerActiveDereference
0x18002f26c  mov     rcx, rsi
0x18002f26f  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x18002f275  mov     eax, cs:dword_18004C0F0
0x18002f27b  cmp     eax, 5
0x18002f27e  jbe     loc_18002F373
0x18002f284  mov     rcx, cs:qword_18004C108
0x18002f28b  mov     rax, cs:qword_18004C100
0x18002f292  test    al, 4
0x18002f294  jz      loc_18002F373
0x18002f29a  mov     rax, rcx
0x18002f29d  and     eax, 4
0x18002f2a0  cmp     rax, rcx
0x18002f2a3  jnz     loc_18002F373
0x18002f2a9  test    rbx, rbx
0x18002f2ac  jz      short loc_18002F2D5
0x18002f2ae  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002f2b5  nop     word ptr [rax+rax+00000000h]
0x18002f2c0  cmp     word ptr [rbx+rax*2+2], 0
0x18002f2c6  lea     rax, [rax+1]
0x18002f2ca  jnz     short loc_18002F2C0
0x18002f2cc  lea     eax, ds:2[rax*2]
0x18002f2d3  jmp     short loc_18002F2E1
0x18002f2d5  lea     rbx, dword_1800405F4
0x18002f2dc  mov     eax, 2
0x18002f2e1  mov     dword ptr [rbp+57h+var_58], eax
0x18002f2e4  lea     rcx, _TraceLoggingMetadata
0x18002f2eb  movzx   eax, cs:word_180043F3B
0x18002f2f2  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18002f2f6  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18002f2f9  xor     r9d, r9d; RelatedActivityId
0x18002f2fc  mov     rax, cs:off_18004C0F8
0x18002f303  xor     r8d, r8d; ActivityId
0x18002f306  mov     [rbp+57h+var_80.Ptr], rax
0x18002f30a  mov     [rbp+57h+var_60], rbx
0x18002f30e  mov     dword ptr [rbp+57h+var_58+4], 0
0x18002f315  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18002f31c  mov     [rbp+57h+EventDescriptor.Keyword], 4
0x18002f324  movzx   eax, word ptr [rax]
0x18002f327  mov     [rbp+57h+var_80.Size], eax
0x18002f32a  lea     rax, byte_180043F45
0x18002f331  mov     [rbp+57h+var_70], rax
0x18002f335  mov     rax, r13
0x18002f338  sub     eax, ecx
0x18002f33a  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18002f341  mov     [rbp+57h+var_68], 2Dh ; '-'
0x18002f348  mov     [rbp+57h+var_64], 1
0x18002f34f  mov     [rbp+57h+var_C0], eax
0x18002f352  mov     eax, [rbp+57h+var_C0]
0x18002f355  mov     rcx, cs:RegHandle; RegHandle
0x18002f35c  lea     rax, [rbp+57h+var_80]
0x18002f360  mov     [rsp+0F0h+UserData], rax; UserData
0x18002f365  mov     [rsp+0F0h+UserDataCount], 3; UserDataCount
0x18002f36d  call    cs:__imp_EventWriteTransfer
0x18002f373  mov     qword ptr [rdi+10h], 0
0x18002f37b  lea     rcx, g_MaintenanceLaunchLock
0x18002f382  mov     cs:dword_18004CEE8, 0
0x18002f38c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002f392  mov     rdi, [rdi]
0x18002f395  cmp     rdi, r15
0x18002f398  jnz     loc_18002F1C0
0x18002f39e  lea     r13, [r14+28h]
0x18002f3a2  lea     rbx, [r14+0C8h]
0x18002f3a9  xor     r15d, r15d
0x18002f3ac  mov     rcx, rbx
0x18002f3af  mov     [rbx+8], r15d
0x18002f3b3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002f3b9  mov     rcx, r13
0x18002f3bc  call    cs:__imp_RtlReleaseSRWLockShared
0x18002f3c2  mov     r14, [r14]
0x18002f3c5  lea     rax, g_leConsumerListHead
0x18002f3cc  cmp     r14, rax
0x18002f3cf  jnz     loc_18002F170
0x18002f3d5  mov     r13, [rsp+0F0h+arg_10]
0x18002f3dd  mov     esi, [rbp+57h+var_BC]
0x18002f3e0  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x18002f3e6  cmp     ecx, 0FFFFFFFFh
0x18002f3e9  jz      short loc_18002F40A
0x18002f3eb  call    cs:__imp_TlsGetValue
0x18002f3f1  mov     r8, [rax]
0x18002f3f4  test    r8b, 2
0x18002f3f8  jnz     short loc_18002F3FC
0x18002f3fa  int     2Ch; Windows NT - assertion failure
0x18002f3fc  sub     qword ptr [rax+10h], 1
0x18002f401  jnz     short loc_18002F40A
0x18002f403  and     r8, 0FFFFFFFFFFFFFFFDh
0x18002f407  mov     [rax], r8
0x18002f40a  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x18002f411  call    cs:__imp_RtlReleaseSRWLockShared
0x18002f417  mov     r12d, r15d
0x18002f41a  lea     rdi, _TraceLoggingMetadataEnd
0x18002f421  lea     r14, _TraceLoggingMetadata
0x18002f428  mov     eax, cs:dword_18004C0F0
0x18002f42e  mov     rbx, [rsp+0F0h+arg_0]
0x18002f436  cmp     eax, 5
0x18002f439  jbe     loc_18002F51A
0x18002f43f  mov     rcx, cs:qword_18004C108
0x18002f446  mov     rax, cs:qword_18004C100
0x18002f44d  test    al, 4
0x18002f44f  jz      loc_18002F51A
0x18002f455  mov     rax, rcx
0x18002f458  and     eax, 4
0x18002f45b  cmp     rax, rcx
0x18002f45e  jnz     loc_18002F51A
0x18002f464  mov     [rbp+57h+var_C0], esi
0x18002f467  lea     rax, [rbp+57h+var_C0]
0x18002f46b  mov     [rbp+57h+var_40], rax
0x18002f46f  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18002f473  mov     [rbp+57h+var_B4], r15d
0x18002f477  lea     rax, [rbp+57h+var_B4]
0x18002f47b  mov     [rbp+57h+var_50], rax
0x18002f47f  sub     edi, r14d
0x18002f482  lea     rax, [rbp+57h+var_B8]
0x18002f486  mov     [rbp+57h+var_B8], r12d
0x18002f48a  mov     [rbp+57h+var_60], rax
0x18002f48e  xor     r9d, r9d; RelatedActivityId
0x18002f491  movzx   eax, cs:word_180044218
0x18002f498  xor     r8d, r8d; ActivityId
0x18002f49b  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18002f49e  mov     rax, cs:off_18004C0F8
0x18002f4a5  mov     [rbp+57h+var_80.Ptr], rax
0x18002f4a9  mov     [rbp+57h+var_38], 4
0x18002f4b1  mov     [rbp+57h+var_48], 4
0x18002f4b9  mov     [rbp+57h+var_58], 4
0x18002f4c1  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18002f4c8  mov     [rbp+57h+EventDescriptor.Keyword], 4
0x18002f4d0  movzx   eax, word ptr [rax]
0x18002f4d3  mov     [rbp+57h+var_80.Size], eax
0x18002f4d6  lea     rax, word_180044222
0x18002f4dd  mov     [rbp+57h+var_70], rax
0x18002f4e1  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18002f4e8  mov     [rbp+57h+var_68], 58h ; 'X'
0x18002f4ef  mov     [rbp+57h+var_64], 1
0x18002f4f6  mov     [rbp+57h+var_BC], edi
0x18002f4f9  mov     eax, [rbp+57h+var_BC]
  ... truncated ...
```
