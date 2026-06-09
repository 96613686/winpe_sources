# UbpmpTriggerCancelled

- ea: `0x18002b880`
- end: `0x18002bc03`
- name: `UbpmpTriggerCancelled`
- size: `899`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007c50`
- `0x180007e30`
- `0x180008f30`
- `0x18001e9f4`
- `0x18002b880`
- `0x180035c50`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18002baf2`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002baf2`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b9aa`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b9aa`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002baad`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002baad`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002bae1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002bae1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002b98d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002bbd6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002b98d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002bbd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bab3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bab3`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002ba57`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002ba57`

## pseudocode

```c
ULONG __fastcall UbpmpTriggerCancelled(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  unsigned __int16 v5; // si
  __int64 v8; // r14
  int *v9; // rcx
  __int64 v10; // rax
  bool v11; // zf
  int v12; // eax
  int v13; // r15d
  unsigned int v14; // edx
  __int64 v15; // r8
  unsigned int i; // ebx
  __int64 v17; // rdi
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // ebx
  ULONG result; // eax
  __int64 v22; // rax
  int *v23; // rcx
  int v24; // r14d
  unsigned int v25; // [rsp+30h] [rbp-61h] BYREF
  __int64 v26; // [rsp+38h] [rbp-59h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-51h] BYREF
  __int64 Source1; // [rsp+50h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-31h] BYREF
  int *v30; // [rsp+70h] [rbp-21h]
  int v31; // [rsp+78h] [rbp-19h]
  int v32; // [rsp+7Ch] [rbp-15h]
  int *v33; // [rsp+80h] [rbp-11h]
  int v34; // [rsp+88h] [rbp-9h]
  int v35; // [rsp+8Ch] [rbp-5h]
  unsigned int *v36; // [rsp+90h] [rbp-1h]
  __int64 v37; // [rsp+98h] [rbp+7h]

  v5 = 0;
  Source1 = a2;
  v26 = a4;
  v8 = -1;
  if ( (unsigned int)dword_18004C0F0 > 4 )
  {
    v9 = *(int **)(*(_QWORD *)(a3 + 24) + 8LL);
    if ( v9 )
    {
      v10 = -1;
      do
        v11 = *((_WORD *)v9 + ++v10) == 0;
      while ( !v11 );
      v12 = 2 * v10 + 2;
    }
    else
    {
      v9 = &dword_1800405F4;
      v12 = 2;
    }
    v34 = v12;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_18004C0F8;
    v33 = v9;
    v35 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_18004C0F8;
    v30 = &dword_18004313C;
    UserData.Reserved = 2;
    v31 = 31;
    v32 = 1;
    v25 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v13 = UbpmConsumerIncPendingActions(a3);
  if ( !v13 )
  {
    RtlAcquireSRWLockShared(a3 + 48);
    if ( (*(_BYTE *)(a3 + 41) & 1) != 0 )
    {
      v14 = *(_DWORD *)(*(_QWORD *)(a3 + 24) + 20LL);
      if ( v14 )
      {
        v15 = *(_QWORD *)(a3 + 32);
        while ( *(_QWORD *)(v15 + 40LL * v5 + 8) != a1 && *(_QWORD *)(v15 + 40LL * v5) != a1 )
        {
          if ( ++v5 >= v14 )
            goto LABEL_27;
        }
        for ( i = 0; i < 5; ++i )
        {
          v17 = 28LL * i;
          if ( RtlCompareMemory(&Source1, (char *)&g_CSebConditions + v17 + 20, 8u) == 8 )
          {
            v20 = *(_DWORD *)((char *)&g_CSebConditions + v17 + 16);
            v13 = 0;
            RtlAcquireSRWLockExclusive(a3 + 208);
            *(_DWORD *)(a3 + 216) = GetCurrentThreadId();
            UbpmpActionTerminatesOnConstraintLocked((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)a3, v5, v20, 0);
            *(_DWORD *)(a3 + 216) = 0;
            RtlReleaseSRWLockExclusive(a3 + 208);
            goto LABEL_27;
          }
        }
        v13 = 1168;
        v18 = v26 + 16;
        v19 = a5 - 20;
        if ( !v26 )
        {
          v19 = a5;
          v18 = 0;
        }
        UbpmpCancelTriggerActions(a3, v5, v18, v19);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL),
          0);
      v13 = 1223;
    }
LABEL_27:
    RtlReleaseSRWLockShared(a3 + 48);
    UbpmConsumerDecPendingActions(a3);
  }
  result = dword_18004C0F0;
  if ( (unsigned int)dword_18004C0F0 > 4 )
  {
    v22 = *(_QWORD *)(a3 + 24);
    v25 = v13;
    v37 = 4;
    v23 = *(int **)(v22 + 8);
    v36 = &v25;
    if ( v23 )
    {
      do
        v11 = *((_WORD *)v23 + ++v8) == 0;
      while ( !v11 );
      v24 = 2 * v8 + 2;
    }
    else
    {
      v23 = &dword_1800405F4;
      v24 = 2;
    }
    *(_DWORD *)&EventDescriptor.Level = 516;
    UserData.Ptr = (ULONGLONG)off_18004C0F8;
    v33 = v23;
    v34 = v24;
    v35 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_18004C0F8;
    v30 = (int *)byte_1800430DD;
    UserData.Reserved = 2;
    v31 = 42;
    v32 = 1;
    LODWORD(v26) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18002b880  mov     [rsp-8+arg_0], rbx
0x18002b885  push    rbp
0x18002b886  push    rsi
0x18002b887  push    rdi
0x18002b888  push    r12
0x18002b88a  push    r13
0x18002b88c  push    r14
0x18002b88e  push    r15
0x18002b890  lea     rbp, [rsp-1Fh]
0x18002b895  sub     rsp, 0B0h
0x18002b89c  mov     rax, cs:__security_cookie
0x18002b8a3  xor     rax, rsp
0x18002b8a6  mov     [rbp+4Fh+var_40], rax
0x18002b8aa  mov     eax, cs:dword_18004C0F0
0x18002b8b0  lea     rdi, _TraceLoggingMetadataEnd
0x18002b8b7  xor     esi, esi
0x18002b8b9  mov     [rbp+4Fh+Source1], rdx
0x18002b8bd  mov     [rbp+4Fh+var_A8], r9
0x18002b8c1  mov     r13, r8
0x18002b8c4  lea     rdx, _TraceLoggingMetadata
0x18002b8cb  mov     rbx, rcx
0x18002b8ce  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18002b8d5  cmp     eax, 4
0x18002b8d8  jbe     loc_18002B993
0x18002b8de  mov     rax, [r8+18h]
0x18002b8e2  mov     rcx, [rax+8]
0x18002b8e6  test    rcx, rcx
0x18002b8e9  jz      short loc_18002B904
0x18002b8eb  mov     rax, r14
0x18002b8ee  xchg    ax, ax
0x18002b8f0  cmp     [rcx+rax*2+2], si
0x18002b8f5  lea     rax, [rax+1]
0x18002b8f9  jnz     short loc_18002B8F0
0x18002b8fb  lea     eax, ds:2[rax*2]
0x18002b902  jmp     short loc_18002B910
0x18002b904  lea     rcx, dword_1800405F4
0x18002b90b  mov     eax, 2
0x18002b910  mov     [rbp+4Fh+var_58], eax
0x18002b913  xor     r9d, r9d; RelatedActivityId
0x18002b916  movzx   eax, cs:word_180043132
0x18002b91d  xor     r8d, r8d; ActivityId
0x18002b920  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x18002b923  mov     rax, cs:off_18004C0F8
0x18002b92a  mov     [rbp+4Fh+var_80.Ptr], rax
0x18002b92e  mov     [rbp+4Fh+var_60], rcx
0x18002b932  mov     [rbp+4Fh+var_54], esi
0x18002b935  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x18002b93c  mov     [rbp+4Fh+EventDescriptor.Keyword], rsi
0x18002b940  movzx   eax, word ptr [rax]
0x18002b943  mov     [rbp+4Fh+var_80.Size], eax
0x18002b946  lea     rax, dword_18004313C
0x18002b94d  mov     [rbp+4Fh+var_70], rax
0x18002b951  mov     rax, rdi
0x18002b954  sub     eax, edx
0x18002b956  mov     dword ptr [rbp+4Fh+var_80.0Ch], 2
0x18002b95d  mov     [rbp+4Fh+var_68], 1Fh
0x18002b964  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x18002b968  mov     [rbp+4Fh+var_64], 1
0x18002b96f  mov     [rbp+4Fh+var_B0], eax
0x18002b972  mov     eax, [rbp+4Fh+var_B0]
0x18002b975  mov     rcx, cs:RegHandle; RegHandle
0x18002b97c  lea     rax, [rbp+4Fh+var_80]
0x18002b980  mov     [rsp+0E0h+UserData], rax; UserData
0x18002b985  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x18002b98d  call    cs:__imp_EventWriteTransfer
0x18002b993  mov     rcx, r13
0x18002b996  call    UbpmConsumerIncPendingActions
0x18002b99b  mov     r15d, eax
0x18002b99e  test    eax, eax
0x18002b9a0  jnz     loc_18002BB00
0x18002b9a6  lea     rcx, [r13+30h]
0x18002b9aa  call    cs:__imp_RtlAcquireSRWLockShared
0x18002b9b0  test    byte ptr [r13+29h], 1
0x18002b9b5  jnz     short loc_18002B9FC
0x18002b9b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9be  lea     rax, WPP_GLOBAL_Control
0x18002b9c5  cmp     rcx, rax
0x18002b9c8  jz      short loc_18002B9F1
0x18002b9ca  test    byte ptr [rcx+1Ch], 1
0x18002b9ce  jz      short loc_18002B9F1
0x18002b9d0  mov     r9, [r13+18h]
0x18002b9d4  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18002b9db  mov     rcx, [rcx+10h]
0x18002b9df  mov     edx, 3Eh ; '>'
0x18002b9e4  mov     [rsp+0E0h+UserDataCount], esi
0x18002b9e8  mov     r9, [r9+8]
0x18002b9ec  call    WPP_SF_Sd
0x18002b9f1  mov     r15d, 4C7h
0x18002b9f7  jmp     loc_18002BAEE
0x18002b9fc  mov     rax, [r13+18h]
0x18002ba00  mov     edx, [rax+14h]
0x18002ba03  test    edx, edx
0x18002ba05  jz      loc_18002BAEE
0x18002ba0b  mov     r8, [r13+20h]
0x18002ba0f  nop
0x18002ba10  movzx   eax, si
0x18002ba13  lea     rcx, [rax+rax*4]
0x18002ba17  cmp     [r8+rcx*8+8], rbx
0x18002ba1c  jz      short loc_18002BA35
0x18002ba1e  cmp     [r8+rcx*8], rbx
0x18002ba22  jz      short loc_18002BA35
0x18002ba24  inc     si
0x18002ba27  movzx   eax, si
0x18002ba2a  cmp     eax, edx
0x18002ba2c  jb      short loc_18002BA10
0x18002ba2e  xor     esi, esi
0x18002ba30  jmp     loc_18002BAEE
0x18002ba35  xor     ebx, ebx
0x18002ba37  lea     r15, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18002ba3e  xchg    ax, ax
0x18002ba40  mov     eax, ebx
0x18002ba42  lea     rdx, [r15+14h]
0x18002ba46  imul    rdi, rax, 1Ch
0x18002ba4a  mov     r8d, 8; Length
0x18002ba50  lea     rcx, [rbp+4Fh+Source1]; Source1
0x18002ba54  add     rdx, rdi; Source2
0x18002ba57  call    cs:__imp_RtlCompareMemory
0x18002ba5d  cmp     rax, 8
0x18002ba61  jz      short loc_18002BA9E
0x18002ba63  inc     ebx
0x18002ba65  cmp     ebx, 5
0x18002ba68  jb      short loc_18002BA40
0x18002ba6a  mov     rcx, [rbp+4Fh+var_A8]
0x18002ba6e  movzx   edx, si
0x18002ba71  mov     eax, [rbp+4Fh+arg_20]
0x18002ba74  test    rcx, rcx
0x18002ba77  mov     r15d, 490h
0x18002ba7d  lea     r8, [rcx+10h]
0x18002ba81  lea     r9d, [rax-14h]
0x18002ba85  cmovz   r9d, eax
0x18002ba89  xor     eax, eax
0x18002ba8b  test    rcx, rcx
0x18002ba8e  mov     rcx, r13
0x18002ba91  cmovz   r8, rax
0x18002ba95  call    UbpmpCancelTriggerActions
0x18002ba9a  xor     esi, esi
0x18002ba9c  jmp     short loc_18002BAE7
0x18002ba9e  mov     ebx, [rdi+r15+10h]
0x18002baa3  lea     rcx, [r13+0D0h]
0x18002baaa  xor     r15d, r15d
0x18002baad  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002bab3  call    cs:__imp_GetCurrentThreadId
0x18002bab9  movzx   edx, si; unsigned int
0x18002babc  xor     r9d, r9d; struct _GUID *
0x18002babf  mov     r8d, ebx; unsigned int
0x18002bac2  mov     [r13+0D8h], eax
0x18002bac9  mov     rcx, r13; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18002bacc  call    ?UbpmpActionTerminatesOnConstraintLocked@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@KKPEAU_GUID@@@Z; UbpmpActionTerminatesOnConstraintLocked(_UBPM_TRIGGER_CONSUMER_BLOCK *,ulong,ulong,_GUID *)
0x18002bad1  xor     esi, esi
0x18002bad3  lea     rcx, [r13+0D0h]
0x18002bada  mov     [r13+0D8h], esi
0x18002bae1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002bae7  lea     rdi, _TraceLoggingMetadataEnd
0x18002baee  lea     rcx, [r13+30h]
0x18002baf2  call    cs:__imp_RtlReleaseSRWLockShared
0x18002baf8  mov     rcx, r13
0x18002bafb  call    UbpmConsumerDecPendingActions
0x18002bb00  mov     eax, cs:dword_18004C0F0
0x18002bb06  cmp     eax, 4
0x18002bb09  jbe     loc_18002BBDC
0x18002bb0f  mov     rax, [r13+18h]
0x18002bb13  mov     [rbp+4Fh+var_B0], r15d
0x18002bb17  mov     [rbp+4Fh+var_48], 4
0x18002bb1f  mov     rcx, [rax+8]
0x18002bb23  lea     rax, [rbp+4Fh+var_B0]
0x18002bb27  mov     [rbp+4Fh+var_50], rax
0x18002bb2b  test    rcx, rcx
0x18002bb2e  jz      short loc_18002BB47
0x18002bb30  cmp     word ptr [rcx+r14*2+2], 0
0x18002bb37  lea     r14, [r14+1]
0x18002bb3b  jnz     short loc_18002BB30
0x18002bb3d  lea     r14d, ds:2[r14*2]
0x18002bb45  jmp     short loc_18002BB54
0x18002bb47  lea     rcx, dword_1800405F4
0x18002bb4e  mov     r14d, 2
0x18002bb54  movzx   eax, cs:word_1800430D3
0x18002bb5b  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x18002bb5f  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x18002bb62  xor     r9d, r9d; RelatedActivityId
0x18002bb65  mov     rax, cs:off_18004C0F8
0x18002bb6c  xor     r8d, r8d; ActivityId
0x18002bb6f  mov     [rbp+4Fh+var_80.Ptr], rax
0x18002bb73  mov     [rbp+4Fh+var_60], rcx
0x18002bb77  mov     [rbp+4Fh+var_58], r14d
0x18002bb7b  mov     [rbp+4Fh+var_54], esi
0x18002bb7e  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x18002bb85  mov     [rbp+4Fh+EventDescriptor.Keyword], rsi
0x18002bb89  movzx   eax, word ptr [rax]
0x18002bb8c  mov     [rbp+4Fh+var_80.Size], eax
0x18002bb8f  lea     rax, byte_1800430DD
0x18002bb96  mov     [rbp+4Fh+var_70], rax
0x18002bb9a  lea     rax, _TraceLoggingMetadata
0x18002bba1  sub     edi, eax
0x18002bba3  mov     dword ptr [rbp+4Fh+var_80.0Ch], 2
0x18002bbaa  mov     [rbp+4Fh+var_68], 2Ah ; '*'
0x18002bbb1  mov     [rbp+4Fh+var_64], 1
0x18002bbb8  mov     dword ptr [rbp+4Fh+var_A8], edi
0x18002bbbb  mov     eax, dword ptr [rbp+4Fh+var_A8]
0x18002bbbe  mov     rcx, cs:RegHandle; RegHandle
0x18002bbc5  lea     rax, [rbp+4Fh+var_80]
0x18002bbc9  mov     [rsp+0E0h+UserData], rax; UserData
0x18002bbce  mov     [rsp+0E0h+UserDataCount], 4; UserDataCount
0x18002bbd6  call    cs:__imp_EventWriteTransfer
0x18002bbdc  mov     rcx, [rbp+4Fh+var_40]
0x18002bbe0  xor     rcx, rsp; StackCookie
0x18002bbe3  call    __security_check_cookie
0x18002bbe8  mov     rbx, [rsp+0E0h+arg_0]
0x18002bbf0  add     rsp, 0B0h
0x18002bbf7  pop     r15
0x18002bbf9  pop     r14
0x18002bbfb  pop     r13
0x18002bbfd  pop     r12
0x18002bbff  pop     rdi
0x18002bc00  pop     rsi
0x18002bc01  pop     rbp
0x18002bc02  retn
```
