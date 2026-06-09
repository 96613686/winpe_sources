# UbpmpExecutionTimeLimitCheckSet

- ea: `0x18000cce0`
- end: `0x18000d0bd`
- name: `UbpmpExecutionTimeLimitCheckSet`
- size: `989`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bd60`
- `0x18000d0d0`
- `0x18002e500`

## callees

- `0x18000cce0`
- `0x180018fbc`
- `0x18001af64`
- `0x18001c2e8`
- `0x180027c88`
- `0x18002d1fc`
- `0x180037aa0`
- `0x180040260`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ce99`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ce99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d040`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d040`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000cebe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000cebe`
- `RPCRT4!UuidEqual` at `0x18000cf01`
- `RPCRT4!UuidEqual` at `0x18000cf01`

## pseudocode

```c
void __fastcall UbpmpExecutionTimeLimitCheckSet(__int64 a1, UUID *a2, int a3, unsigned int a4)
{
  _QWORD *v5; // rdx
  int v6; // r8d
  unsigned __int64 v7; // rdi
  __int64 v8; // rcx
  int v9; // eax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rbx
  __int64 v13; // rcx
  unsigned int UbpmNameHash; // eax
  __int64 v15; // r8
  _QWORD *v16; // rsi
  ULONGLONG v17; // r13
  unsigned __int64 v18; // r15
  UUID *v19; // r13
  _QWORD *v20; // rdi
  PVOID *v21; // rcx
  unsigned __int64 v22; // rax
  int v23; // eax
  __int64 v24; // r10
  __int64 v25; // rdx
  struct _TP_TIMER *v26; // rcx
  char v27[8]; // [rsp+48h] [rbp-69h] BYREF
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp-61h] BYREF
  unsigned int v29; // [rsp+58h] [rbp-59h] BYREF
  RPC_STATUS Status; // [rsp+5Ch] [rbp-55h] BYREF
  ULONGLONG TickCount64; // [rsp+60h] [rbp-51h] BYREF
  UUID *Uuid2; // [rsp+68h] [rbp-49h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-29h] BYREF
  void *v35; // [rsp+98h] [rbp-19h]
  int v36; // [rsp+A0h] [rbp-11h]
  int v37; // [rsp+A4h] [rbp-Dh]
  unsigned int *v38; // [rsp+A8h] [rbp-9h]
  __int64 v39; // [rsp+B0h] [rbp-1h]
  ULONGLONG *v40; // [rsp+B8h] [rbp+7h]
  __int64 v41; // [rsp+C0h] [rbp+Fh]

  Uuid2 = a2;
  Status = 0;
  v27[0] = 0;
  if ( (a3 & 0x10001) == 0x10001 )
    return;
  v5 = *(_QWORD **)(a1 + 24);
  if ( a4 == 0xFFFF || (v6 = *(_DWORD *)(v5[3] + 48LL * a4 + 20), v6 == -1) )
    v7 = 0;
  else
    v7 = (unsigned int)(1000 * v6);
  v8 = *(_QWORD *)(v5[5] + 32LL);
  if ( v8 && (v9 = *(_DWORD *)(v8 + 12)) != 0 )
    v10 = (unsigned int)(1000 * v9);
  else
    v10 = 0;
  if ( !v5[6] || (unsigned int)UbpmpMaintenanceTaskCompletedWithinDeadline(a1, v27) || (v11 = 3600000, !v27[0]) )
    v11 = 0;
  v12 = -1;
  if ( !v7 )
  {
    v7 = -1;
    if ( v10 )
      v7 = v10;
  }
  if ( v11 && v11 < v7 )
    v7 = v11;
  v13 = *(_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(v13 + 48) )
  {
    UbpmNameHash = UbpmUtilsGetUbpmNameHash(*(PCWSTR *)(v13 + 8));
    if ( (unsigned int)dword_18004F0F0 > 4 )
    {
      v29 = UbpmNameHash;
      TickCount64 = v7;
      v40 = &TickCount64;
      v41 = 8;
      v38 = &v29;
      *(_DWORD *)&EventDescriptor.Level = 4;
      UserData.Ptr = (ULONGLONG)off_18004F0F8;
      v39 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_18004F0F8;
      v35 = &unk_180046100;
      UserData.Reserved = 2;
      v36 = 57;
      v37 = 1;
      pftDueTime.dwLowDateTime = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
  }
  if ( v7 == -1 )
    return;
  TickCount64 = GetTickCount64();
  v16 = *(_QWORD **)(a1 + 224);
  v17 = TickCount64;
  v18 = v7 + TickCount64;
  if ( v16 == (_QWORD *)(a1 + 224) )
    goto LABEL_48;
  v19 = Uuid2;
  do
  {
    v20 = v16;
    v16 = (_QWORD *)*v16;
    if ( !UuidEqual((UUID *)((char *)v20 + 52), v19, &Status) )
      goto LABEL_30;
    v20[9] = v18;
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_Sqid(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 40LL) + 32LL),
        v15,
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
        (char)v20,
        v18,
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 40LL) + 32LL) + 12LL));
LABEL_30:
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
    v22 = v20[9];
    if ( v22 && v12 >= v22 )
      v12 = v20[9];
  }
  while ( v16 != (_QWORD *)(a1 + 224) );
  v17 = TickCount64;
  if ( v12 != -1 && v12 >= TickCount64 )
  {
    if ( !*(_QWORD *)(a1 + 288) && !*(_BYTE *)(a1 + 296) )
    {
      v23 = UbpmpExecutionTimeLimitInitialize(a1);
      if ( v23 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            128,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
            v23);
        return;
      }
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
    v24 = *(_QWORD *)(a1 + 288);
    v25 = 5000;
    if ( v12 - v17 > 0x1388 )
      v25 = v12 - v17;
    if ( v24 )
    {
      v26 = *(struct _TP_TIMER **)(v24 + 40);
      pftDueTime = (struct _FILETIME)(-10000 * v25);
      SetThreadpoolTimer(v26, &pftDueTime, 0, 0);
LABEL_48:
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 0x10) != 0 )
    WPP_SF_ii(v21[2], 129, v15, v12, v17);
}

```

## disassembly

```asm
0x18000cce0  mov     r11, rsp
0x18000cce3  push    rbp
0x18000cce4  push    r14
0x18000cce6  push    r15
0x18000cce8  lea     rbp, [r11-5Fh]
0x18000ccec  sub     rsp, 0F0h
0x18000ccf3  mov     rax, cs:__security_cookie
0x18000ccfa  xor     rax, rsp
0x18000ccfd  mov     [rbp+57h+var_40], rax
0x18000cd01  xor     r15d, r15d
0x18000cd04  mov     [rbp+57h+Uuid2], rdx
0x18000cd08  and     r8d, 10001h
0x18000cd0f  mov     [rbp+57h+Status], r15d
0x18000cd13  mov     [rbp+57h+var_C0], r15b
0x18000cd17  mov     r14, rcx
0x18000cd1a  cmp     r8d, 10001h
0x18000cd21  jz      loc_18000D0A3
0x18000cd27  mov     rdx, [rcx+18h]
0x18000cd2b  mov     [r11+18h], rbx
0x18000cd2f  mov     [r11-28h], rdi
0x18000cd33  cmp     r9d, 0FFFFh
0x18000cd3a  jz      short loc_18000CD5E
0x18000cd3c  mov     eax, r9d
0x18000cd3f  lea     rcx, [rax+rax*2]
0x18000cd43  mov     rax, [rdx+18h]
0x18000cd47  add     rcx, rcx
0x18000cd4a  mov     r8d, [rax+rcx*8+14h]
0x18000cd4f  cmp     r8d, 0FFFFFFFFh
0x18000cd53  jz      short loc_18000CD5E
0x18000cd55  imul    edi, r8d, 3E8h
0x18000cd5c  jmp     short loc_18000CD61
0x18000cd5e  mov     rdi, r15
0x18000cd61  mov     rax, [rdx+28h]
0x18000cd65  mov     [rsp+0E8h], rsi
0x18000cd6d  mov     rcx, [rax+20h]
0x18000cd71  test    rcx, rcx
0x18000cd74  jz      short loc_18000CD85
0x18000cd76  mov     eax, [rcx+0Ch]
0x18000cd79  test    eax, eax
0x18000cd7b  jz      short loc_18000CD85
0x18000cd7d  imul    esi, eax, 3E8h
0x18000cd83  jmp     short loc_18000CD88
0x18000cd85  mov     rsi, r15
0x18000cd88  cmp     [rdx+30h], r15
0x18000cd8c  jz      short loc_18000CDA9
0x18000cd8e  lea     rdx, [rbp+57h+var_C0]
0x18000cd92  mov     rcx, r14
0x18000cd95  call    UbpmpMaintenanceTaskCompletedWithinDeadline
0x18000cd9a  test    eax, eax
0x18000cd9c  jnz     short loc_18000CDA9
0x18000cd9e  mov     eax, 36EE80h
0x18000cda3  cmp     [rbp+57h+var_C0], r15b
0x18000cda7  jnz     short loc_18000CDAC
0x18000cda9  mov     rax, r15
0x18000cdac  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000cdb3  test    rdi, rdi
0x18000cdb6  jnz     short loc_18000CDC2
0x18000cdb8  test    rsi, rsi
0x18000cdbb  mov     rdi, rbx
0x18000cdbe  cmovnz  rdi, rsi
0x18000cdc2  test    rax, rax
0x18000cdc5  jz      short loc_18000CDCE
0x18000cdc7  cmp     rax, rdi
0x18000cdca  cmovb   rdi, rax
0x18000cdce  mov     rcx, [r14+18h]
0x18000cdd2  cmp     [rcx+30h], r15
0x18000cdd6  jz      loc_18000CEA5
0x18000cddc  mov     rcx, [rcx+8]; SourceString
0x18000cde0  call    ?UbpmUtilsGetUbpmNameHash@@YAKPEBG@Z; UbpmUtilsGetUbpmNameHash(ushort const *)
0x18000cde5  mov     ecx, cs:dword_18004F0F0
0x18000cdeb  cmp     ecx, 4
0x18000cdee  jbe     loc_18000CEA5
0x18000cdf4  mov     [rbp+57h+var_B0], eax
0x18000cdf7  lea     rcx, _TraceLoggingMetadata
0x18000cdfe  mov     [rbp+57h+var_A8], rdi
0x18000ce02  lea     rax, [rbp+57h+var_A8]
0x18000ce06  mov     [rbp+57h+var_50], rax
0x18000ce0a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000ce0e  lea     rax, [rbp+57h+var_B0]
0x18000ce12  mov     [rbp+57h+var_48], 8
0x18000ce1a  mov     [rbp+57h+var_60], rax
0x18000ce1e  xor     r9d, r9d; RelatedActivityId
0x18000ce21  movzx   eax, cs:word_1800460F6
0x18000ce28  xor     r8d, r8d; ActivityId
0x18000ce2b  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000ce2e  mov     rax, cs:off_18004F0F8
0x18000ce35  mov     [rbp+57h+var_80.Ptr], rax
0x18000ce39  mov     [rbp+57h+var_58], 4
0x18000ce41  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000ce48  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18000ce4c  movzx   eax, word ptr [rax]
0x18000ce4f  mov     [rbp+57h+var_80.Size], eax
0x18000ce52  lea     rax, unk_180046100
0x18000ce59  mov     [rbp+57h+var_70], rax
0x18000ce5d  lea     rax, _TraceLoggingMetadataEnd
0x18000ce64  sub     eax, ecx
0x18000ce66  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18000ce6d  mov     [rbp+57h+var_68], 39h ; '9'
0x18000ce74  mov     [rbp+57h+var_64], 1
0x18000ce7b  mov     [rbp+57h+pftDueTime.dwLowDateTime], eax
0x18000ce7e  mov     eax, [rbp+57h+pftDueTime.dwLowDateTime]
0x18000ce81  mov     rcx, cs:RegHandle; RegHandle
0x18000ce88  lea     rax, [rbp+57h+var_80]
0x18000ce8c  mov     [rsp+100h+UserData], rax; UserData
0x18000ce91  mov     [rsp+100h+UserDataCount], 4; UserDataCount
0x18000ce99  call    cs:__imp_EventWriteTransfer
0x18000cea0  nop     dword ptr [rax+rax+00h]
0x18000cea5  cmp     rdi, rbx
0x18000cea8  jz      loc_18000D08B
0x18000ceae  mov     [rsp+100h+var_28], r12
0x18000ceb6  mov     [rsp+100h+var_30], r13
0x18000cebe  call    cs:__imp_GetTickCount64
0x18000cec5  nop     dword ptr [rax+rax+00h]
0x18000ceca  lea     r12, [r14+0E0h]
0x18000ced1  mov     [rbp+57h+var_A8], rax
0x18000ced5  mov     rsi, [r12]
0x18000ced9  mov     r13, rax
0x18000cedc  lea     r15, [rdi+rax]
0x18000cee0  cmp     rsi, r12
0x18000cee3  jz      loc_18000D04C
0x18000cee9  mov     r13, [rbp+57h+Uuid2]
0x18000ceed  nop     dword ptr [rax]
0x18000cef0  mov     rdi, rsi
0x18000cef3  lea     r8, [rbp+57h+Status]; Status
0x18000cef7  mov     rsi, [rsi]
0x18000cefa  mov     rdx, r13; Uuid2
0x18000cefd  lea     rcx, [rdi+34h]; Uuid1
0x18000cf01  call    cs:__imp_UuidEqual
0x18000cf08  nop     dword ptr [rax+rax+00h]
0x18000cf0d  test    eax, eax
0x18000cf0f  jz      short loc_18000CF5B
0x18000cf11  mov     [rdi+48h], r15
0x18000cf15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf1c  lea     rax, WPP_GLOBAL_Control
0x18000cf23  cmp     rcx, rax
0x18000cf26  jz      short loc_18000CF62
0x18000cf28  test    dword ptr [rcx+1Ch], 200h
0x18000cf2f  jz      short loc_18000CF62
0x18000cf31  mov     r9, [r14+18h]
0x18000cf35  mov     rcx, [rcx+10h]
0x18000cf39  mov     rax, [r9+28h]
0x18000cf3d  mov     r9, [r9+8]
0x18000cf41  mov     rdx, [rax+20h]
0x18000cf45  mov     eax, [rdx+0Ch]
0x18000cf48  mov     [rsp+30h], eax
0x18000cf4c  mov     [rsp+100h+UserData], r15
0x18000cf51  mov     qword ptr [rsp+100h+UserDataCount], rdi
0x18000cf56  call    WPP_SF_Sqid
0x18000cf5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf62  mov     rax, [rdi+48h]
0x18000cf66  test    rax, rax
0x18000cf69  jz      short loc_18000CF72
0x18000cf6b  cmp     rbx, rax
0x18000cf6e  cmovnb  rbx, rax
0x18000cf72  cmp     rsi, r12
0x18000cf75  jnz     loc_18000CEF0
0x18000cf7b  mov     r13, [rbp+57h+var_A8]
0x18000cf7f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000cf83  jz      loc_18000D053
0x18000cf89  cmp     rbx, r13
0x18000cf8c  jb      loc_18000D053
0x18000cf92  cmp     qword ptr [r14+120h], 0
0x18000cf9a  jnz     short loc_18000D000
0x18000cf9c  cmp     byte ptr [r14+128h], 0
0x18000cfa4  jnz     short loc_18000D000
0x18000cfa6  mov     rcx, r14
0x18000cfa9  call    UbpmpExecutionTimeLimitInitialize
0x18000cfae  test    eax, eax
0x18000cfb0  jz      short loc_18000CFF9
0x18000cfb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfb9  lea     rdx, WPP_GLOBAL_Control
0x18000cfc0  cmp     rcx, rdx
0x18000cfc3  jz      loc_18000D07B
0x18000cfc9  test    byte ptr [rcx+1Ch], 1
0x18000cfcd  jz      loc_18000D07B
0x18000cfd3  mov     r9, [r14+18h]
0x18000cfd7  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000cfde  mov     rcx, [rcx+10h]
0x18000cfe2  mov     edx, 80h
0x18000cfe7  mov     [rsp+100h+UserDataCount], eax
0x18000cfeb  mov     r9, [r9+8]
0x18000cfef  call    WPP_SF_Sd
0x18000cff4  jmp     loc_18000D07B
0x18000cff9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d000  mov     r10, [r14+120h]
0x18000d007  mov     edx, 1388h
0x18000d00c  mov     rax, rbx
0x18000d00f  sub     rax, r13
0x18000d012  cmp     rax, rdx
0x18000d015  cmova   rdx, rax
0x18000d019  test    r10, r10
0x18000d01c  jz      short loc_18000D053
0x18000d01e  mov     rcx, [r10+28h]; pti
0x18000d022  xor     r9d, r9d; msWindowLength
0x18000d025  imul    rax, rdx, 0FFFFFFFFFFFFD8F0h
0x18000d02c  xor     r8d, r8d; msPeriod
0x18000d02f  mov     rdx, rax
0x18000d032  mov     [rbp+57h+pftDueTime.dwLowDateTime], eax
0x18000d035  shr     rdx, 20h
0x18000d039  mov     [rbp+57h+pftDueTime.dwHighDateTime], edx
0x18000d03c  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x18000d040  call    cs:__imp_SetThreadpoolTimer
0x18000d047  nop     dword ptr [rax+rax+00h]
0x18000d04c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d053  lea     rax, WPP_GLOBAL_Control
0x18000d05a  cmp     rcx, rax
0x18000d05d  jz      short loc_18000D07B
0x18000d05f  test    byte ptr [rcx+1Ch], 10h
0x18000d063  jz      short loc_18000D07B
0x18000d065  mov     rcx, [rcx+10h]
0x18000d069  mov     edx, 81h
0x18000d06e  mov     r9, rbx
0x18000d071  mov     qword ptr [rsp+100h+UserDataCount], r13
0x18000d076  call    WPP_SF_ii
0x18000d07b  mov     r12, [rsp+100h+var_28]
0x18000d083  mov     r13, [rsp+100h+var_30]
0x18000d08b  mov     rsi, [rsp+0E8h]
0x18000d093  mov     rbx, [rsp+100h+arg_10]
0x18000d09b  mov     rdi, [rsp+100h+var_20]
0x18000d0a3  mov     rcx, [rbp+57h+var_40]
0x18000d0a7  xor     rcx, rsp; StackCookie
0x18000d0aa  call    __security_check_cookie
0x18000d0af  add     rsp, 0F0h
0x18000d0b6  pop     r15
0x18000d0b8  pop     r14
0x18000d0ba  pop     rbp
0x18000d0bb  retn
```
