# UbpmpExecutionTimeLimitCheckSet

- ea: `0x18001c000`
- end: `0x18001c3ef`
- name: `UbpmpExecutionTimeLimitCheckSet`
- size: `1007`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001acb0`
- `0x18001c400`
- `0x18002c480`

## callees

- `0x1800169d4`
- `0x18001c000`
- `0x18001e9f4`
- `0x18001fbf8`
- `0x18002b258`
- `0x18003556c`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001c10f`
- `ntdll!RtlInitUnicodeString` at `0x18001c10f`
- `ntdll!RtlHashUnicodeString` at `0x18001c127`
- `ntdll!RtlHashUnicodeString` at `0x18001c127`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001c1ea`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001c1ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c379`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c379`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c209`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c209`
- `RPCRT4!UuidEqual` at `0x18001c243`
- `RPCRT4!UuidEqual` at `0x18001c243`

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
  __int64 v13; // rdx
  const WCHAR *v14; // rdx
  bool v15; // sf
  ULONG v16; // ecx
  __int64 v17; // r8
  _QWORD *v18; // rsi
  ULONGLONG v19; // r13
  unsigned __int64 v20; // r15
  UUID *v21; // r13
  _QWORD *v22; // rdi
  PVOID *v23; // rcx
  unsigned __int64 v24; // rax
  int v25; // eax
  __int64 v26; // r10
  __int64 v27; // rdx
  struct _TP_TIMER *v28; // rcx
  _BYTE v29[4]; // [rsp+48h] [rbp-69h] BYREF
  ULONG HashValue; // [rsp+4Ch] [rbp-65h] BYREF
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp-61h] BYREF
  RPC_STATUS Status; // [rsp+58h] [rbp-59h] BYREF
  ULONGLONG TickCount64; // [rsp+60h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-49h] BYREF
  UUID *Uuid2; // [rsp+78h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-29h] BYREF
  void *v37; // [rsp+98h] [rbp-19h]
  int v38; // [rsp+A0h] [rbp-11h]
  int v39; // [rsp+A4h] [rbp-Dh]
  ULONG *p_HashValue; // [rsp+A8h] [rbp-9h]
  __int64 v41; // [rsp+B0h] [rbp-1h]
  ULONGLONG *v42; // [rsp+B8h] [rbp+7h]
  __int64 v43; // [rsp+C0h] [rbp+Fh]

  Uuid2 = a2;
  Status = 0;
  v29[0] = 0;
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
  if ( !v5[6] || (unsigned int)UbpmpMaintenanceTaskCompletedWithinDeadline(a1, v29) || (v11 = 3600000, !v29[0]) )
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
    v14 = *(const WCHAR **)(v13 + 8);
    HashValue = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v14);
    v15 = RtlHashUnicodeString(&DestinationString, 1u, 1u, &HashValue) < 0;
    v16 = 0;
    if ( !v15 )
      v16 = HashValue;
    if ( (unsigned int)dword_18004C0F0 > 4 )
    {
      HashValue = v16;
      v42 = &TickCount64;
      TickCount64 = v7;
      p_HashValue = &HashValue;
      *(_DWORD *)(&DestinationString.MaximumLength + 1) = 4;
      UserData.Ptr = (ULONGLONG)off_18004C0F8;
      v43 = 8;
      v41 = 4;
      *(_DWORD *)&DestinationString.Length = 184549376;
      DestinationString.Buffer = 0;
      UserData.Size = *(unsigned __int16 *)off_18004C0F8;
      v37 = &unk_180043098;
      UserData.Reserved = 2;
      v38 = 57;
      v39 = 1;
      pftDueTime.dwLowDateTime = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&DestinationString, 0, 0, 4u, &UserData);
    }
  }
  if ( v7 == -1 )
    return;
  TickCount64 = GetTickCount64();
  v18 = *(_QWORD **)(a1 + 224);
  v19 = TickCount64;
  v20 = v7 + TickCount64;
  if ( v18 == (_QWORD *)(a1 + 224) )
    goto LABEL_50;
  v21 = Uuid2;
  do
  {
    v22 = v18;
    v18 = (_QWORD *)*v18;
    if ( !UuidEqual((UUID *)((char *)v22 + 52), v21, &Status) )
      goto LABEL_32;
    v22[9] = v20;
    v23 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_Sqid(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 40LL) + 32LL),
        v17,
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
        (char)v22,
        v20,
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 40LL) + 32LL) + 12LL));
LABEL_32:
      v23 = (PVOID *)WPP_GLOBAL_Control;
    }
    v24 = v22[9];
    if ( v24 && v12 >= v24 )
      v12 = v22[9];
  }
  while ( v18 != (_QWORD *)(a1 + 224) );
  v19 = TickCount64;
  if ( v12 != -1 && v12 >= TickCount64 )
  {
    if ( !*(_QWORD *)(a1 + 288) && !*(_BYTE *)(a1 + 296) )
    {
      v25 = UbpmpExecutionTimeLimitInitialize(a1);
      if ( v25 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            128,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
            v25);
        return;
      }
      v23 = (PVOID *)WPP_GLOBAL_Control;
    }
    v26 = *(_QWORD *)(a1 + 288);
    v27 = 5000;
    if ( v12 - v19 > 0x1388 )
      v27 = v12 - v19;
    if ( v26 )
    {
      v28 = *(struct _TP_TIMER **)(v26 + 40);
      pftDueTime = (struct _FILETIME)(-10000 * v27);
      SetThreadpoolTimer(v28, &pftDueTime, 0, 0);
LABEL_50:
      v23 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 0x10) != 0 )
    WPP_SF_ii(v23[2], 129, v17, v12, v19);
}

```

## disassembly

```asm
0x18001c000  mov     r11, rsp
0x18001c003  push    rbp
0x18001c004  push    r14
0x18001c006  push    r15
0x18001c008  lea     rbp, [r11-5Fh]
0x18001c00c  sub     rsp, 0F0h
0x18001c013  mov     rax, cs:__security_cookie
0x18001c01a  xor     rax, rsp
0x18001c01d  mov     [rbp+57h+var_40], rax
0x18001c021  xor     r15d, r15d
0x18001c024  mov     [rbp+57h+Uuid2], rdx
0x18001c028  and     r8d, 10001h
0x18001c02f  mov     [rbp+57h+Status], r15d
0x18001c033  mov     [rbp+57h+var_C0], r15b
0x18001c037  mov     r14, rcx
0x18001c03a  cmp     r8d, 10001h
0x18001c041  jz      loc_18001C3D6
0x18001c047  mov     rdx, [rcx+18h]
0x18001c04b  mov     [r11+18h], rbx
0x18001c04f  mov     [r11-28h], rdi
0x18001c053  cmp     r9d, 0FFFFh
0x18001c05a  jz      short loc_18001C07E
0x18001c05c  mov     eax, r9d
0x18001c05f  lea     rcx, [rax+rax*2]
0x18001c063  mov     rax, [rdx+18h]
0x18001c067  add     rcx, rcx
0x18001c06a  mov     r8d, [rax+rcx*8+14h]
0x18001c06f  cmp     r8d, 0FFFFFFFFh
0x18001c073  jz      short loc_18001C07E
0x18001c075  imul    edi, r8d, 3E8h
0x18001c07c  jmp     short loc_18001C081
0x18001c07e  mov     rdi, r15
0x18001c081  mov     rax, [rdx+28h]
0x18001c085  mov     [rsp+0E8h], rsi
0x18001c08d  mov     rcx, [rax+20h]
0x18001c091  test    rcx, rcx
0x18001c094  jz      short loc_18001C0A5
0x18001c096  mov     eax, [rcx+0Ch]
0x18001c099  test    eax, eax
0x18001c09b  jz      short loc_18001C0A5
0x18001c09d  imul    esi, eax, 3E8h
0x18001c0a3  jmp     short loc_18001C0A8
0x18001c0a5  mov     rsi, r15
0x18001c0a8  cmp     [rdx+30h], r15
0x18001c0ac  jz      short loc_18001C0C9
0x18001c0ae  lea     rdx, [rbp+57h+var_C0]
0x18001c0b2  mov     rcx, r14
0x18001c0b5  call    UbpmpMaintenanceTaskCompletedWithinDeadline
0x18001c0ba  test    eax, eax
0x18001c0bc  jnz     short loc_18001C0C9
0x18001c0be  mov     eax, 36EE80h
0x18001c0c3  cmp     [rbp+57h+var_C0], r15b
0x18001c0c7  jnz     short loc_18001C0CC
0x18001c0c9  mov     rax, r15
0x18001c0cc  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001c0d3  test    rdi, rdi
0x18001c0d6  jnz     short loc_18001C0E2
0x18001c0d8  test    rsi, rsi
0x18001c0db  mov     rdi, rbx
0x18001c0de  cmovnz  rdi, rsi
0x18001c0e2  test    rax, rax
0x18001c0e5  jz      short loc_18001C0EE
0x18001c0e7  cmp     rax, rdi
0x18001c0ea  cmovb   rdi, rax
0x18001c0ee  mov     rdx, [r14+18h]
0x18001c0f2  cmp     [rdx+30h], r15
0x18001c0f6  jz      loc_18001C1F0
0x18001c0fc  mov     rdx, [rdx+8]; SourceString
0x18001c100  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001c104  xorps   xmm0, xmm0
0x18001c107  mov     [rbp+57h+HashValue], r15d
0x18001c10b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001c10f  call    cs:__imp_RtlInitUnicodeString
0x18001c115  mov     r8d, 1; HashAlgorithm
0x18001c11b  lea     r9, [rbp+57h+HashValue]; HashValue
0x18001c11f  movzx   edx, r8b; CaseInSensitive
0x18001c123  lea     rcx, [rbp+57h+DestinationString]; String
0x18001c127  call    cs:__imp_RtlHashUnicodeString
0x18001c12d  test    eax, eax
0x18001c12f  mov     ecx, r15d
0x18001c132  mov     eax, cs:dword_18004C0F0
0x18001c138  cmovns  ecx, [rbp+57h+HashValue]
0x18001c13c  cmp     eax, 4
0x18001c13f  jbe     loc_18001C1F0
0x18001c145  mov     [rbp+57h+HashValue], ecx
0x18001c148  lea     rax, [rbp+57h+var_A8]
0x18001c14c  mov     [rbp+57h+var_50], rax
0x18001c150  lea     rcx, _TraceLoggingMetadata
0x18001c157  lea     rax, [rbp+57h+HashValue]
0x18001c15b  mov     [rbp+57h+var_A8], rdi
0x18001c15f  mov     [rbp+57h+var_60], rax
0x18001c163  lea     rdx, [rbp+57h+DestinationString]; EventDescriptor
0x18001c167  movzx   eax, cs:word_18004308E
0x18001c16e  xor     r9d, r9d; RelatedActivityId
0x18001c171  mov     dword ptr [rbp+57h+DestinationString+4], eax
0x18001c174  xor     r8d, r8d; ActivityId
0x18001c177  mov     rax, cs:off_18004C0F8
0x18001c17e  mov     [rbp+57h+var_80.Ptr], rax
0x18001c182  mov     [rbp+57h+var_48], 8
0x18001c18a  mov     [rbp+57h+var_58], 4
0x18001c192  mov     dword ptr [rbp+57h+DestinationString.Length], 0B000000h
0x18001c199  mov     [rbp+57h+DestinationString.Buffer], r15
0x18001c19d  movzx   eax, word ptr [rax]
0x18001c1a0  mov     [rbp+57h+var_80.Size], eax
0x18001c1a3  lea     rax, unk_180043098
0x18001c1aa  mov     [rbp+57h+var_70], rax
0x18001c1ae  lea     rax, _TraceLoggingMetadataEnd
0x18001c1b5  sub     eax, ecx
0x18001c1b7  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18001c1be  mov     [rbp+57h+var_68], 39h ; '9'
0x18001c1c5  mov     [rbp+57h+var_64], 1
0x18001c1cc  mov     [rbp+57h+pftDueTime.dwLowDateTime], eax
0x18001c1cf  mov     eax, [rbp+57h+pftDueTime.dwLowDateTime]
0x18001c1d2  mov     rcx, cs:RegHandle; RegHandle
0x18001c1d9  lea     rax, [rbp+57h+var_80]
0x18001c1dd  mov     [rsp+100h+UserData], rax; UserData
0x18001c1e2  mov     [rsp+100h+UserDataCount], 4; UserDataCount
0x18001c1ea  call    cs:__imp_EventWriteTransfer
0x18001c1f0  cmp     rdi, rbx
0x18001c1f3  jz      loc_18001C3BE
0x18001c1f9  mov     [rsp+100h+var_28], r12
0x18001c201  mov     [rsp+100h+var_30], r13
0x18001c209  call    cs:__imp_GetTickCount64
0x18001c20f  lea     r12, [r14+0E0h]
0x18001c216  mov     [rbp+57h+var_A8], rax
0x18001c21a  mov     rsi, [r12]
0x18001c21e  mov     r13, rax
0x18001c221  lea     r15, [rdi+rax]
0x18001c225  cmp     rsi, r12
0x18001c228  jz      loc_18001C37F
0x18001c22e  mov     r13, [rbp+57h+Uuid2]
0x18001c232  mov     rdi, rsi
0x18001c235  lea     r8, [rbp+57h+Status]; Status
0x18001c239  mov     rsi, [rsi]
0x18001c23c  mov     rdx, r13; Uuid2
0x18001c23f  lea     rcx, [rdi+34h]; Uuid1
0x18001c243  call    cs:__imp_UuidEqual
0x18001c249  test    eax, eax
0x18001c24b  jz      short loc_18001C297
0x18001c24d  mov     [rdi+48h], r15
0x18001c251  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c258  lea     rax, WPP_GLOBAL_Control
0x18001c25f  cmp     rcx, rax
0x18001c262  jz      short loc_18001C29E
0x18001c264  test    dword ptr [rcx+1Ch], 200h
0x18001c26b  jz      short loc_18001C29E
0x18001c26d  mov     r9, [r14+18h]
0x18001c271  mov     rcx, [rcx+10h]
0x18001c275  mov     rax, [r9+28h]
0x18001c279  mov     r9, [r9+8]
0x18001c27d  mov     rdx, [rax+20h]
0x18001c281  mov     eax, [rdx+0Ch]
0x18001c284  mov     [rsp+30h], eax
0x18001c288  mov     [rsp+100h+UserData], r15
0x18001c28d  mov     qword ptr [rsp+100h+UserDataCount], rdi
0x18001c292  call    WPP_SF_Sqid
0x18001c297  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c29e  mov     rax, [rdi+48h]
0x18001c2a2  test    rax, rax
0x18001c2a5  jz      short loc_18001C2AE
0x18001c2a7  cmp     rbx, rax
0x18001c2aa  cmovnb  rbx, rax
0x18001c2ae  cmp     rsi, r12
0x18001c2b1  jnz     loc_18001C232
0x18001c2b7  mov     r13, [rbp+57h+var_A8]
0x18001c2bb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001c2bf  jz      loc_18001C386
0x18001c2c5  cmp     rbx, r13
0x18001c2c8  jb      loc_18001C386
0x18001c2ce  cmp     qword ptr [r14+120h], 0
0x18001c2d6  jnz     short loc_18001C339
0x18001c2d8  cmp     byte ptr [r14+128h], 0
0x18001c2e0  jnz     short loc_18001C339
0x18001c2e2  mov     rcx, r14
0x18001c2e5  call    UbpmpExecutionTimeLimitInitialize
0x18001c2ea  test    eax, eax
0x18001c2ec  jz      short loc_18001C332
0x18001c2ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2f5  lea     rdx, WPP_GLOBAL_Control
0x18001c2fc  cmp     rcx, rdx
0x18001c2ff  jz      loc_18001C3AE
0x18001c305  test    byte ptr [rcx+1Ch], 1
0x18001c309  jz      loc_18001C3AE
0x18001c30f  mov     r9, [r14+18h]
0x18001c313  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001c31a  mov     rcx, [rcx+10h]
0x18001c31e  mov     edx, 80h
0x18001c323  mov     [rsp+100h+UserDataCount], eax
0x18001c327  mov     r9, [r9+8]
0x18001c32b  call    WPP_SF_Sd
0x18001c330  jmp     short loc_18001C3AE
0x18001c332  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c339  mov     r10, [r14+120h]
0x18001c340  mov     edx, 1388h
0x18001c345  mov     rax, rbx
0x18001c348  sub     rax, r13
0x18001c34b  cmp     rax, rdx
0x18001c34e  cmova   rdx, rax
0x18001c352  test    r10, r10
0x18001c355  jz      short loc_18001C386
0x18001c357  mov     rcx, [r10+28h]; pti
0x18001c35b  xor     r9d, r9d; msWindowLength
0x18001c35e  imul    rax, rdx, 0FFFFFFFFFFFFD8F0h
0x18001c365  xor     r8d, r8d; msPeriod
0x18001c368  mov     rdx, rax
0x18001c36b  mov     [rbp+57h+pftDueTime.dwLowDateTime], eax
0x18001c36e  shr     rdx, 20h
0x18001c372  mov     [rbp+57h+pftDueTime.dwHighDateTime], edx
0x18001c375  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x18001c379  call    cs:__imp_SetThreadpoolTimer
0x18001c37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c386  lea     rax, WPP_GLOBAL_Control
0x18001c38d  cmp     rcx, rax
0x18001c390  jz      short loc_18001C3AE
0x18001c392  test    byte ptr [rcx+1Ch], 10h
0x18001c396  jz      short loc_18001C3AE
0x18001c398  mov     rcx, [rcx+10h]
0x18001c39c  mov     edx, 81h
0x18001c3a1  mov     r9, rbx
0x18001c3a4  mov     qword ptr [rsp+100h+UserDataCount], r13
0x18001c3a9  call    WPP_SF_ii
0x18001c3ae  mov     r12, [rsp+100h+var_28]
0x18001c3b6  mov     r13, [rsp+100h+var_30]
0x18001c3be  mov     rsi, [rsp+0E8h]
0x18001c3c6  mov     rbx, [rsp+100h+arg_10]
0x18001c3ce  mov     rdi, [rsp+100h+var_20]
0x18001c3d6  mov     rcx, [rbp+57h+var_40]
0x18001c3da  xor     rcx, rsp; StackCookie
0x18001c3dd  call    __security_check_cookie
0x18001c3e2  add     rsp, 0F0h
0x18001c3e9  pop     r15
0x18001c3eb  pop     r14
0x18001c3ed  pop     rbp
0x18001c3ee  retn
```
