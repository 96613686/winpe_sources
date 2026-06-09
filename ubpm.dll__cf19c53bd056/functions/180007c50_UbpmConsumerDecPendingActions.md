# UbpmConsumerDecPendingActions

- ea: `0x180007c50`
- end: `0x180007e27`
- name: `UbpmConsumerDecPendingActions`
- size: `471`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002dc0`
- `0x180003684`
- `0x180007480`
- `0x18000a710`
- `0x180019a30`
- `0x180026650`
- `0x1800275a0`
- `0x18002b2b0`
- `0x18002b880`

## callees

- `0x180007c50`
- `0x18003488c`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007c76`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007c76`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007e09`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007e09`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180007ca1`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180007ca1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007dfc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007dfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c7c`

## pseudocode

```c
__int64 __fastcall UbpmConsumerDecPendingActions(__int64 a1)
{
  __int64 v2; // rcx
  bool v3; // zf
  int v4; // edx
  int v5; // eax
  __int64 v6; // rax
  int *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  int v11; // [rsp+34h] [rbp-75h] BYREF
  int v12; // [rsp+38h] [rbp-71h] BYREF
  int v13; // [rsp+3Ch] [rbp-6Dh] BYREF
  __int64 v14; // [rsp+40h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-49h] BYREF
  char *v17; // [rsp+70h] [rbp-39h]
  int v18; // [rsp+78h] [rbp-31h]
  int v19; // [rsp+7Ch] [rbp-2Dh]
  int *v20; // [rsp+80h] [rbp-29h]
  int v21; // [rsp+88h] [rbp-21h]
  int v22; // [rsp+8Ch] [rbp-1Dh]
  int *v23; // [rsp+90h] [rbp-19h]
  __int64 v24; // [rsp+98h] [rbp-11h]
  int *v25; // [rsp+A0h] [rbp-9h]
  __int64 v26; // [rsp+A8h] [rbp-1h]
  __int64 *v27; // [rsp+B0h] [rbp+7h]
  __int64 v28; // [rsp+B8h] [rbp+Fh]
  int *v29; // [rsp+C0h] [rbp+17h]
  __int64 v30; // [rsp+C8h] [rbp+1Fh]

  RtlAcquireSRWLockExclusive(a1 + 72);
  *(_DWORD *)(a1 + 80) = GetCurrentThreadId();
  if ( *(int *)(a1 + 88) <= 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  v3 = (*(_DWORD *)(a1 + 88))-- == 1;
  v4 = 0;
  if ( v3 )
  {
    WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 96));
    v4 = 1;
  }
  if ( (unsigned int)dword_18004C0F0 > 5 && (qword_18004C100 & 1) != 0 && (qword_18004C108 & 1) == qword_18004C108 )
  {
    v5 = *(_DWORD *)(a1 + 92) & 1;
    v11 = v4;
    v12 = v5;
    v13 = *(_DWORD *)(a1 + 88);
    v6 = *(_QWORD *)(a1 + 24);
    v14 = a1;
    v30 = 4;
    v28 = 8;
    v7 = *(int **)(v6 + 8);
    v29 = &v11;
    v27 = &v14;
    v25 = &v12;
    v23 = &v13;
    v26 = 4;
    v24 = 4;
    if ( v7 )
    {
      v8 = -1;
      do
        v3 = *((_WORD *)v7 + ++v8) == 0;
      while ( !v3 );
      v9 = 2 * v8 + 2;
    }
    else
    {
      v7 = &dword_1800405F4;
      v9 = 2;
    }
    v21 = v9;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18004C0F8;
    v20 = v7;
    v22 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)off_18004C0F8;
    v17 = byte_180042ED9;
    UserData.Reserved = 2;
    v18 = 114;
    v19 = 1;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
  }
  *(_DWORD *)(a1 + 80) = 0;
  return RtlReleaseSRWLockExclusive(a1 + 72);
}

```

## disassembly

```asm
0x180007c50  push    rbp
0x180007c52  push    rbx
0x180007c53  push    rsi
0x180007c54  push    rdi
0x180007c55  lea     rbp, [rsp-3Fh]
0x180007c5a  sub     rsp, 0E8h
0x180007c61  mov     rax, cs:__security_cookie
0x180007c68  xor     rax, rsp
0x180007c6b  mov     [rbp+57h+var_30], rax
0x180007c6f  mov     rbx, rcx
0x180007c72  add     rcx, 48h ; 'H'
0x180007c76  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007c7c  call    cs:__imp_GetCurrentThreadId
0x180007c82  mov     [rbx+50h], eax
0x180007c85  cmp     dword ptr [rbx+58h], 0
0x180007c89  jg      short loc_180007C90
0x180007c8b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007c90  sub     dword ptr [rbx+58h], 1
0x180007c94  mov     esi, 0
0x180007c99  mov     edx, esi
0x180007c9b  jnz     short loc_180007CAC
0x180007c9d  lea     rcx, [rbx+60h]; ConditionVariable
0x180007ca1  call    cs:__imp_WakeConditionVariable
0x180007ca7  mov     edx, 1
0x180007cac  mov     eax, cs:dword_18004C0F0
0x180007cb2  cmp     eax, 5
0x180007cb5  jbe     loc_180007E02
0x180007cbb  mov     rcx, cs:qword_18004C108
0x180007cc2  mov     rax, cs:qword_18004C100
0x180007cc9  test    al, 1
0x180007ccb  jz      loc_180007E02
0x180007cd1  mov     rax, rcx
0x180007cd4  and     eax, 1
0x180007cd7  cmp     rax, rcx
0x180007cda  jnz     loc_180007E02
0x180007ce0  mov     eax, [rbx+5Ch]
0x180007ce3  and     eax, 1
0x180007ce6  mov     [rbp+57h+var_CC], edx
0x180007ce9  mov     [rbp+57h+var_C8], eax
0x180007cec  mov     eax, [rbx+58h]
0x180007cef  mov     [rbp+57h+var_C4], eax
0x180007cf2  mov     rax, [rbx+18h]
0x180007cf6  mov     [rbp+57h+var_C0], rbx
0x180007cfa  mov     [rbp+57h+var_38], 4
0x180007d02  mov     [rbp+57h+var_48], 8
0x180007d0a  mov     rcx, [rax+8]
0x180007d0e  lea     rax, [rbp+57h+var_CC]
0x180007d12  mov     [rbp+57h+var_40], rax
0x180007d16  lea     rax, [rbp+57h+var_C0]
0x180007d1a  mov     [rbp+57h+var_50], rax
0x180007d1e  lea     rax, [rbp+57h+var_C8]
0x180007d22  mov     [rbp+57h+var_60], rax
0x180007d26  lea     rax, [rbp+57h+var_C4]
0x180007d2a  mov     [rbp+57h+var_70], rax
0x180007d2e  mov     [rbp+57h+var_58], 4
0x180007d36  mov     [rbp+57h+var_68], 4
0x180007d3e  test    rcx, rcx
0x180007d41  jz      short loc_180007D64
0x180007d43  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007d4a  nop     word ptr [rax+rax+00h]
0x180007d50  cmp     [rcx+rax*2+2], si
0x180007d55  lea     rax, [rax+1]
0x180007d59  jnz     short loc_180007D50
0x180007d5b  lea     eax, ds:2[rax*2]
0x180007d62  jmp     short loc_180007D70
0x180007d64  lea     rcx, dword_1800405F4
0x180007d6b  mov     eax, 2
0x180007d70  mov     [rbp+57h+var_78], eax
0x180007d73  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180007d77  movzx   eax, cs:word_180042ECF
0x180007d7e  xor     r9d, r9d; RelatedActivityId
0x180007d81  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180007d84  xor     r8d, r8d; ActivityId
0x180007d87  mov     rax, cs:off_18004C0F8
0x180007d8e  mov     [rbp+57h+var_A0.Ptr], rax
0x180007d92  mov     [rbp+57h+var_80], rcx
0x180007d96  lea     rcx, _TraceLoggingMetadata
0x180007d9d  mov     [rbp+57h+var_74], esi
0x180007da0  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180007da7  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x180007daf  movzx   eax, word ptr [rax]
0x180007db2  mov     [rbp+57h+var_A0.Size], eax
0x180007db5  lea     rax, byte_180042ED9
0x180007dbc  mov     [rbp+57h+var_90], rax
0x180007dc0  lea     rax, _TraceLoggingMetadataEnd
0x180007dc7  sub     eax, ecx
0x180007dc9  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x180007dd0  mov     [rbp+57h+var_88], 72h ; 'r'
0x180007dd7  mov     [rbp+57h+var_84], 1
0x180007dde  mov     [rbp+57h+var_D0], eax
0x180007de1  mov     eax, [rbp+57h+var_D0]
0x180007de4  mov     rcx, cs:RegHandle; RegHandle
0x180007deb  lea     rax, [rbp+57h+var_A0]
0x180007def  mov     [rsp+100h+UserData], rax; UserData
0x180007df4  mov     [rsp+100h+UserDataCount], 7; UserDataCount
0x180007dfc  call    cs:__imp_EventWriteTransfer
0x180007e02  lea     rcx, [rbx+48h]
0x180007e06  mov     [rbx+50h], esi
0x180007e09  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007e0f  mov     rcx, [rbp+57h+var_30]
0x180007e13  xor     rcx, rsp; StackCookie
0x180007e16  call    __security_check_cookie
0x180007e1b  add     rsp, 0E8h
0x180007e22  pop     rdi
0x180007e23  pop     rsi
0x180007e24  pop     rbx
0x180007e25  pop     rbp
0x180007e26  retn
```
