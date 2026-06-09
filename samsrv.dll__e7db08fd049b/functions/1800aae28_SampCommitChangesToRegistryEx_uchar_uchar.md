# SampCommitChangesToRegistryEx(uchar,uchar *)

- ea: `0x1800aae28`
- end: `0x1800ab3df`
- name: `?SampCommitChangesToRegistryEx@@YAJEPEAE@Z`
- size: `1463`
- prototype: `__int64 __fastcall(unsigned __int8, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800656f8`

## callees

- `0x180021bec`
- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x1800372ec`
- `0x1800aae28`
- `0x1800ab8c0`
- `0x1800ad17c`
- `0x1800b03d0`
- `0x1800b0c24`
- `0x1800b0ca0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aaf51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aaf51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab134`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ab0eb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ab0eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab12c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab12c`
- `ntdll!RtlApplyRXactNoFlush` at `0x1800aaeea`
- `ntdll!RtlApplyRXactNoFlush` at `0x1800aaeea`
- `ntdll!NtQuerySystemTime` at `0x1800ab1bd`
- `ntdll!NtQuerySystemTime` at `0x1800ab1bd`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ab38a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ab38a`
- `ntdll!RtlEnterCriticalSection` at `0x1800aaeaf`
- `ntdll!RtlEnterCriticalSection` at `0x1800aaeaf`

## pseudocode

```c
__int64 __fastcall SampCommitChangesToRegistryEx(unsigned __int8 a1, unsigned __int8 *a2)
{
  int v3; // r15d
  unsigned int v5; // eax
  PUNICODE_STRING v6; // rcx
  __int64 v7; // r14
  int v8; // ebx
  int v9; // edi
  DWORD LastError; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  int refreshed; // eax
  PUNICODE_STRING v14; // rcx
  union _LARGE_INTEGER v15; // rbx
  unsigned __int8 v16; // dl
  HANDLE v17; // rbx
  DWORD v18; // eax
  unsigned __int8 v19; // al
  __int64 v20; // r8
  _OWORD *v21; // rcx
  struct _PSAMP_DEFINED_DOMAINS *v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  _OWORD *v25; // rax
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  _OWORD *v39; // rax
  _OWORD *v40; // rdx
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  DWORD ThreadId; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v55[376]; // [rsp+48h] [rbp-B8h] BYREF
  int v56; // [rsp+200h] [rbp+100h] BYREF
  int v57; // [rsp+208h] [rbp+108h] BYREF

  v3 = a1;
  v56 = 0;
  v57 = 0;
  if ( SampRXactContextInvalidated )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        32,
        WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
        3221225495LL,
        -1073741801);
    return 3221225495LL;
  }
  RtlEnterCriticalSection(&SampRegistryHiveLock);
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 33, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
  v5 = RtlApplyRXactNoFlush(SampRXactContext);
  v56 = v5;
  v6 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 34, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v5);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 2;
  if ( v56 >= 0 )
    goto LABEL_28;
  if ( (*(_BYTE *)(&v6[4].MaximumLength + 1) & 4) != 0 )
  {
    if ( HIBYTE(v6[4].Length) >= 2u )
    {
      v8 = FlushThreadCreated;
      v9 = FlushImmediately;
      LastError = GetLastError();
      WPP_SF_LLddd(WPP_GLOBAL_Control[3].Buffer, v11, v12, (unsigned int)v56, LastError, v9, v8, v3);
      v6 = WPP_GLOBAL_Control;
    }
    if ( (*(_BYTE *)(&v6[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v6[4].Length) >= 2u )
    {
      WPP_SF_d(v6[3].Buffer, 36, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v56);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( v56 >= 0 )
  {
LABEL_28:
    v15 = LastUnflushedChange;
    if ( (_BYTE)v3 && LastUnflushedChange.QuadPart == SampHasNeverTime.QuadPart )
      FlushAsync = 1;
    v16 = FlushImmediately;
    if ( FlushImmediately )
      goto LABEL_52;
    if ( FlushThreadCreated )
      goto LABEL_45;
    ThreadId = 0;
    v17 = CreateThread(0, 0, SampFlushThread, 0, 0, &ThreadId);
    if ( v17 )
    {
      FlushThreadCreated = 1;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 37, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, ThreadId);
      CloseHandle(v17);
    }
    else
    {
      v18 = GetLastError();
      v6 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
LABEL_42:
        v16 = FlushImmediately;
        if ( !FlushImmediately )
        {
          v19 = FlushThreadCreated;
          if ( FlushThreadCreated )
          {
            v15 = LastUnflushedChange;
LABEL_45:
            if ( (_BYTE)v3 )
            {
              if ( (*(_BYTE *)(&v6[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v6[4].Length) >= 4u )
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_q)(
                  v6[3].Buffer,
                  40,
                  WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
                  (union _LARGE_INTEGER)v15.QuadPart);
            }
            else
            {
              NtQuerySystemTime(&LastUnflushedChange);
              if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0
                && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
              {
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_ii)(
                  WPP_GLOBAL_Control[3].Buffer,
                  41,
                  v20,
                  (union _LARGE_INTEGER)v15.QuadPart,
                  (union _LARGE_INTEGER)LastUnflushedChange.QuadPart);
              }
            }
LABEL_57:
            if ( v56 >= 0 && SampTransactionWithinDomainFn() == 1 )
            {
              v21 = v55;
              v22 = SampDefinedDomains;
              v23 = 2;
              v24 = 1360LL * SampTransactionDomainIndexGlobal;
              v25 = (_OWORD *)((char *)SampDefinedDomains + v24 + 128);
              do
              {
                v26 = v25[1];
                *v21 = *v25;
                v27 = v25[2];
                v21[1] = v26;
                v28 = v25[3];
                v21[2] = v27;
                v29 = v25[4];
                v21[3] = v28;
                v30 = v25[5];
                v21[4] = v29;
                v31 = v25[6];
                v21[5] = v30;
                v32 = v25[7];
                v25 += 8;
                v21[6] = v31;
                v21[7] = v32;
                v21 += 8;
                --v23;
              }
              while ( v23 );
              v33 = v25[1];
              *v21 = *v25;
              v34 = v25[2];
              v21[1] = v33;
              v35 = v25[3];
              v21[2] = v34;
              v36 = v25[4];
              v21[3] = v35;
              v37 = v25[5];
              v21[4] = v36;
              v38 = v25[6];
              v39 = (_OWORD *)((char *)v22 + v24 + 496);
              v40 = v55;
              v21[5] = v37;
              v21[6] = v38;
              do
              {
                v41 = v40[1];
                *v39 = *v40;
                v42 = v40[2];
                v39[1] = v41;
                v43 = v40[3];
                v39[2] = v42;
                v44 = v40[4];
                v39[3] = v43;
                v45 = v40[5];
                v39[4] = v44;
                v46 = v40[6];
                v39[5] = v45;
                v47 = v40[7];
                v40 += 8;
                v39[6] = v46;
                v39[7] = v47;
                v39 += 8;
                --v7;
              }
              while ( v7 );
              v48 = v40[1];
              *v39 = *v40;
              v49 = v40[2];
              v39[1] = v48;
              v50 = v40[3];
              v39[2] = v49;
              v51 = v40[4];
              v39[3] = v50;
              v52 = v40[5];
              v39[4] = v51;
              v53 = v40[6];
              v39[5] = v52;
              v39[6] = v53;
            }
            goto LABEL_64;
          }
LABEL_53:
          if ( (*(_BYTE *)(&v6[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v6[4].Length) >= 4u )
            WPP_SF_Dd(v6[3].Buffer, 39, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v16, v19);
          v56 = SampFlushRegistryHive();
          goto LABEL_57;
        }
LABEL_52:
        v19 = FlushThreadCreated;
        goto LABEL_53;
      }
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 38, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v18, v18);
    }
    v6 = WPP_GLOBAL_Control;
    goto LABEL_42;
  }
  SampWriteEventLog(SAMMSG_COMMIT_FAILED, L"b", 4, &v56);
  refreshed = SampRefreshRegistry();
  v57 = refreshed;
  if ( refreshed < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[3].Buffer,
        42,
        WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
        (unsigned int)refreshed);
      v14 = WPP_GLOBAL_Control;
    }
    SampServiceState = 6;
    SampRXactContextInvalidated = 1;
    if ( (*(_BYTE *)(&v14[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v14[4].Length) >= 2u )
      WPP_SF_(v14[3].Buffer, 43, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
    SampWriteEventLog(SAMMSG_REFRESH_FAILED, L"b", 4, &v57);
  }
  LastUnflushedChange = SampHasNeverTime;
  FlushImmediately = 0;
  FlushAsync = 0;
  *a2 = 1;
LABEL_64:
  RtlLeaveCriticalSection(&SampRegistryHiveLock);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 44, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v56, v56);
  return (unsigned int)v56;
}

```

## disassembly

```asm
0x1800aae28  mov     [rsp-8+arg_0], rbx
0x1800aae2d  mov     [rsp-8+arg_8], rsi
0x1800aae32  push    rbp
0x1800aae33  push    rdi
0x1800aae34  push    r12
0x1800aae36  push    r14
0x1800aae38  push    r15
0x1800aae3a  lea     rbp, [rsp-0C0h]
0x1800aae42  sub     rsp, 1C0h
0x1800aae49  cmp     cs:?SampRXactContextInvalidated@@3EA, 0; uchar SampRXactContextInvalidated
0x1800aae50  mov     r12, rdx
0x1800aae53  movzx   r15d, cl
0x1800aae57  mov     [rbp+0E0h+arg_10], 0
0x1800aae61  mov     [rbp+0E0h+arg_18], 0
0x1800aae6b  jz      short loc_1800AAEA8
0x1800aae6d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aae74  mov     ebx, 0C0000017h
0x1800aae79  test    dword ptr [rcx+44h], 20000h
0x1800aae80  jz      short loc_1800AAEA1
0x1800aae82  mov     rcx, [rcx+38h]
0x1800aae86  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800aae8d  mov     edx, 20h ; ' '
0x1800aae92  mov     [rsp+1E0h+dwCreationFlags], ebx
0x1800aae96  mov     r9d, 0C0000017h
0x1800aae9c  call    WPP_SF_Dd
0x1800aaea1  mov     eax, ebx
0x1800aaea3  jmp     loc_1800AB3C3
0x1800aaea8  lea     rcx, ?SampRegistryHiveLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800aaeaf  call    cs:__imp_RtlEnterCriticalSection
0x1800aaeb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaebc  lea     rsi, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800aaec3  mov     edi, 4
0x1800aaec8  test    [rcx+44h], dil
0x1800aaecc  jz      short loc_1800AAEE3
0x1800aaece  cmp     [rcx+41h], dil
0x1800aaed2  jb      short loc_1800AAEE3
0x1800aaed4  mov     rcx, [rcx+38h]
0x1800aaed8  lea     edx, [rdi+1Dh]
0x1800aaedb  mov     r8, rsi
0x1800aaede  call    WPP_SF_
0x1800aaee3  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x1800aaeea  call    cs:__imp_RtlApplyRXactNoFlush
0x1800aaef0  mov     [rbp+0E0h+arg_10], eax
0x1800aaef6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaefd  test    [rcx+44h], dil
0x1800aaf01  jz      short loc_1800AAF24
0x1800aaf03  cmp     [rcx+41h], dil
0x1800aaf07  jb      short loc_1800AAF24
0x1800aaf09  mov     rcx, [rcx+38h]
0x1800aaf0d  mov     edx, 22h ; '"'
0x1800aaf12  mov     r9d, eax
0x1800aaf15  mov     r8, rsi
0x1800aaf18  call    WPP_SF_d
0x1800aaf1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaf24  cmp     [rbp+0E0h+arg_10], 0
0x1800aaf2b  mov     r14d, 2
0x1800aaf31  jge     loc_1800AB08D
0x1800aaf37  test    [rcx+44h], dil
0x1800aaf3b  jz      short loc_1800AAFB5
0x1800aaf3d  cmp     [rcx+41h], r14b
0x1800aaf41  jb      short loc_1800AAF8A
0x1800aaf43  movzx   ebx, cs:?FlushThreadCreated@@3EA; uchar FlushThreadCreated
0x1800aaf4a  movzx   edi, cs:?FlushImmediately@@3EA; uchar FlushImmediately
0x1800aaf51  call    cs:__imp_GetLastError
0x1800aaf57  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaf5e  mov     r9d, [rbp+0E0h+arg_10]
0x1800aaf65  mov     [rsp+1E0h+var_1A8], r15d
0x1800aaf6a  mov     [rsp+1E0h+var_1B0], ebx
0x1800aaf6e  mov     rcx, [rcx+38h]
0x1800aaf72  mov     dword ptr [rsp+1E0h+lpThreadId], edi
0x1800aaf76  mov     [rsp+1E0h+dwCreationFlags], eax
0x1800aaf7a  call    WPP_SF_LLddd
0x1800aaf7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaf86  lea     edi, [r14+2]
0x1800aaf8a  test    [rcx+44h], dil
0x1800aaf8e  jz      short loc_1800AAFB5
0x1800aaf90  cmp     [rcx+41h], r14b
0x1800aaf94  jb      short loc_1800AAFB5
0x1800aaf96  mov     r9d, [rbp+0E0h+arg_10]
0x1800aaf9d  mov     edx, 24h ; '$'
0x1800aafa2  mov     rcx, [rcx+38h]
0x1800aafa6  mov     r8, rsi
0x1800aafa9  call    WPP_SF_d
0x1800aafae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aafb5  cmp     [rbp+0E0h+arg_10], 0
0x1800aafbc  jge     loc_1800AB08D
0x1800aafc2  lea     r9, [rbp+0E0h+arg_10]
0x1800aafc9  mov     r8, rdi
0x1800aafcc  lea     rdx, aB; "b"
0x1800aafd3  lea     rcx, SAMMSG_COMMIT_FAILED
0x1800aafda  call    SampWriteEventLog
0x1800aafdf  call    ?SampRefreshRegistry@@YAJXZ; SampRefreshRegistry(void)
0x1800aafe4  mov     [rbp+0E0h+arg_18], eax
0x1800aafea  test    eax, eax
0x1800aafec  jns     short loc_1800AB067
0x1800aafee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaff5  test    [rcx+44h], dil
0x1800aaff9  jz      short loc_1800AB01C
0x1800aaffb  cmp     [rcx+41h], r14b
0x1800aafff  jb      short loc_1800AB01C
0x1800ab001  mov     rcx, [rcx+38h]
0x1800ab005  mov     edx, 2Ah ; '*'
0x1800ab00a  mov     r9d, eax
0x1800ab00d  mov     r8, rsi
0x1800ab010  call    WPP_SF_d
0x1800ab015  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab01c  mov     cs:?SampServiceState@@3W4_SAMP_SERVICE_STATE@@A, 6; _SAMP_SERVICE_STATE SampServiceState
0x1800ab026  mov     cs:?SampRXactContextInvalidated@@3EA, 1; uchar SampRXactContextInvalidated
0x1800ab02d  test    [rcx+44h], dil
0x1800ab031  jz      short loc_1800AB04A
0x1800ab033  cmp     [rcx+41h], r14b
0x1800ab037  jb      short loc_1800AB04A
0x1800ab039  mov     rcx, [rcx+38h]
0x1800ab03d  mov     edx, 2Bh ; '+'
0x1800ab042  mov     r8, rsi
0x1800ab045  call    WPP_SF_
0x1800ab04a  lea     r9, [rbp+0E0h+arg_18]
0x1800ab051  mov     r8, rdi
0x1800ab054  lea     rdx, aB; "b"
0x1800ab05b  lea     rcx, SAMMSG_REFRESH_FAILED
0x1800ab062  call    SampWriteEventLog
0x1800ab067  mov     rax, cs:?SampHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SampHasNeverTime
0x1800ab06e  mov     qword ptr cs:?LastUnflushedChange@@3T_LARGE_INTEGER@@A, rax; _LARGE_INTEGER LastUnflushedChange ...
0x1800ab075  mov     cs:?FlushImmediately@@3EA, 0; uchar FlushImmediately
0x1800ab07c  mov     cs:?FlushAsync@@3EA, 0; uchar FlushAsync
0x1800ab083  mov     byte ptr [r12], 1
0x1800ab088  jmp     loc_1800AB383
0x1800ab08d  mov     rbx, qword ptr cs:?LastUnflushedChange@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LastUnflushedChange ...
0x1800ab094  test    r15b, r15b
0x1800ab097  jz      short loc_1800AB0A9
0x1800ab099  cmp     rbx, cs:?SampHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SampHasNeverTime
0x1800ab0a0  jnz     short loc_1800AB0A9
0x1800ab0a2  mov     cs:?FlushAsync@@3EA, 1; uchar FlushAsync
0x1800ab0a9  mov     dl, cs:?FlushImmediately@@3EA; uchar FlushImmediately
0x1800ab0af  test    dl, dl
0x1800ab0b1  jnz     loc_1800AB1F5
0x1800ab0b7  cmp     cs:?FlushThreadCreated@@3EA, dl; uchar FlushThreadCreated
0x1800ab0bd  jnz     loc_1800AB187
0x1800ab0c3  lea     rax, [rsp+1E0h+ThreadId]
0x1800ab0c8  mov     [rsp+1E0h+ThreadId], 0
0x1800ab0d0  mov     [rsp+1E0h+lpThreadId], rax; lpThreadId
0x1800ab0d5  lea     r8, ?SampFlushThread@@YAJPEAX@Z; lpStartAddress
0x1800ab0dc  xor     r9d, r9d; lpParameter
0x1800ab0df  mov     [rsp+1E0h+dwCreationFlags], 0; dwCreationFlags
0x1800ab0e7  xor     edx, edx; dwStackSize
0x1800ab0e9  xor     ecx, ecx; lpThreadAttributes
0x1800ab0eb  call    cs:__imp_CreateThread
0x1800ab0f1  mov     rbx, rax
0x1800ab0f4  test    rax, rax
0x1800ab0f7  jz      short loc_1800AB134
0x1800ab0f9  mov     cs:?FlushThreadCreated@@3EA, 1; uchar FlushThreadCreated
0x1800ab100  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab107  test    [rcx+44h], dil
0x1800ab10b  jz      short loc_1800AB129
0x1800ab10d  cmp     byte ptr [rcx+41h], 5
0x1800ab111  jb      short loc_1800AB129
0x1800ab113  mov     r9d, [rsp+1E0h+ThreadId]
0x1800ab118  mov     edx, 25h ; '%'
0x1800ab11d  mov     rcx, [rcx+38h]
0x1800ab121  mov     r8, rsi
0x1800ab124  call    WPP_SF_d
0x1800ab129  mov     rcx, rbx; hObject
0x1800ab12c  call    cs:__imp_CloseHandle
0x1800ab132  jmp     short loc_1800AB165
0x1800ab134  call    cs:__imp_GetLastError
0x1800ab13a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab141  test    [rcx+44h], dil
0x1800ab145  jz      short loc_1800AB16C
0x1800ab147  cmp     [rcx+41h], r14b
0x1800ab14b  jb      short loc_1800AB16C
0x1800ab14d  mov     rcx, [rcx+38h]
0x1800ab151  mov     edx, 26h ; '&'
0x1800ab156  mov     r9d, eax
0x1800ab159  mov     [rsp+1E0h+dwCreationFlags], eax
0x1800ab15d  mov     r8, rsi
0x1800ab160  call    WPP_SF_Dd
0x1800ab165  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab16c  mov     dl, cs:?FlushImmediately@@3EA; uchar FlushImmediately
0x1800ab172  test    dl, dl
0x1800ab174  jnz     short loc_1800AB1F5
0x1800ab176  mov     al, cs:?FlushThreadCreated@@3EA; uchar FlushThreadCreated
0x1800ab17c  test    al, al
0x1800ab17e  jz      short loc_1800AB1FB
0x1800ab180  mov     rbx, qword ptr cs:?LastUnflushedChange@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LastUnflushedChange ...
0x1800ab187  test    r15b, r15b
0x1800ab18a  jz      short loc_1800AB1B6
0x1800ab18c  test    [rcx+44h], dil
0x1800ab190  jz      loc_1800AB22E
0x1800ab196  cmp     [rcx+41h], dil
0x1800ab19a  jb      loc_1800AB22E
0x1800ab1a0  mov     rcx, [rcx+38h]
0x1800ab1a4  mov     edx, 28h ; '('
0x1800ab1a9  mov     r9, rbx
0x1800ab1ac  mov     r8, rsi
0x1800ab1af  call    WPP_SF_q
0x1800ab1b4  jmp     short loc_1800AB22E
0x1800ab1b6  lea     rcx, ?LastUnflushedChange@@3T_LARGE_INTEGER@@A; SystemTime
0x1800ab1bd  call    cs:__imp_NtQuerySystemTime
0x1800ab1c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab1ca  test    [rcx+44h], dil
0x1800ab1ce  jz      short loc_1800AB22E
0x1800ab1d0  cmp     [rcx+41h], dil
0x1800ab1d4  jb      short loc_1800AB22E
0x1800ab1d6  mov     rax, qword ptr cs:?LastUnflushedChange@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LastUnflushedChange ...
0x1800ab1dd  mov     edx, 29h ; ')'
0x1800ab1e2  mov     rcx, [rcx+38h]
0x1800ab1e6  mov     r9, rbx
0x1800ab1e9  mov     qword ptr [rsp+1E0h+dwCreationFlags], rax
0x1800ab1ee  call    WPP_SF_ii
0x1800ab1f3  jmp     short loc_1800AB22E
0x1800ab1f5  mov     al, cs:?FlushThreadCreated@@3EA; uchar FlushThreadCreated
0x1800ab1fb  test    [rcx+44h], dil
0x1800ab1ff  jz      short loc_1800AB223
0x1800ab201  cmp     [rcx+41h], dil
0x1800ab205  jb      short loc_1800AB223
0x1800ab207  mov     rcx, [rcx+38h]
0x1800ab20b  mov     r8, rsi
0x1800ab20e  movzx   eax, al
0x1800ab211  movzx   r9d, dl
0x1800ab215  mov     edx, 27h ; '''
0x1800ab21a  mov     [rsp+1E0h+dwCreationFlags], eax
0x1800ab21e  call    WPP_SF_Dd
0x1800ab223  call    ?SampFlushRegistryHive@@YAJXZ; SampFlushRegistryHive(void)
0x1800ab228  mov     [rbp+0E0h+arg_10], eax
0x1800ab22e  cmp     [rbp+0E0h+arg_10], 0
0x1800ab235  jl      loc_1800AB383
0x1800ab23b  call    ?SampTransactionWithinDomainFn@@YAEXZ; SampTransactionWithinDomainFn(void)
0x1800ab240  cmp     al, 1
0x1800ab242  jnz     loc_1800AB383
0x1800ab248  mov     eax, cs:?SampTransactionDomainIndexGlobal@@3KA; ulong SampTransactionDomainIndexGlobal
0x1800ab24e  lea     rcx, [rsp+1E0h+var_198]
0x1800ab253  mov     r8, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800ab25a  mov     r9, r14
0x1800ab25d  imul    rdx, rax, 550h
0x1800ab264  lea     rax, [r8+80h]
0x1800ab26b  mov     r10d, 80h
0x1800ab271  add     rax, rdx
0x1800ab274  movups  xmm0, xmmword ptr [rax]
0x1800ab277  movups  xmm1, xmmword ptr [rax+10h]
0x1800ab27b  movups  xmmword ptr [rcx], xmm0
0x1800ab27e  movups  xmm0, xmmword ptr [rax+20h]
0x1800ab282  movups  xmmword ptr [rcx+10h], xmm1
0x1800ab286  movups  xmm1, xmmword ptr [rax+30h]
0x1800ab28a  movups  xmmword ptr [rcx+20h], xmm0
0x1800ab28e  movups  xmm0, xmmword ptr [rax+40h]
0x1800ab292  movups  xmmword ptr [rcx+30h], xmm1
0x1800ab296  movups  xmm1, xmmword ptr [rax+50h]
0x1800ab29a  movups  xmmword ptr [rcx+40h], xmm0
0x1800ab29e  movups  xmm0, xmmword ptr [rax+60h]
0x1800ab2a2  movups  xmmword ptr [rcx+50h], xmm1
0x1800ab2a6  movups  xmm1, xmmword ptr [rax+70h]
0x1800ab2aa  add     rax, r10
0x1800ab2ad  movups  xmmword ptr [rcx+60h], xmm0
0x1800ab2b1  movups  xmmword ptr [rcx+70h], xmm1
0x1800ab2b5  add     rcx, r10
0x1800ab2b8  sub     r9, 1
0x1800ab2bc  jnz     short loc_1800AB274
0x1800ab2be  movups  xmm0, xmmword ptr [rax]
0x1800ab2c1  movups  xmm1, xmmword ptr [rax+10h]
0x1800ab2c5  movups  xmmword ptr [rcx], xmm0
0x1800ab2c8  movups  xmm0, xmmword ptr [rax+20h]
0x1800ab2cc  movups  xmmword ptr [rcx+10h], xmm1
0x1800ab2d0  movups  xmm1, xmmword ptr [rax+30h]
0x1800ab2d4  movups  xmmword ptr [rcx+20h], xmm0
0x1800ab2d8  movups  xmm0, xmmword ptr [rax+40h]
0x1800ab2dc  movups  xmmword ptr [rcx+30h], xmm1
0x1800ab2e0  movups  xmm1, xmmword ptr [rax+50h]
0x1800ab2e4  movups  xmmword ptr [rcx+40h], xmm0
0x1800ab2e8  movups  xmm0, xmmword ptr [rax+60h]
0x1800ab2ec  lea     rax, [r8+1F0h]
0x1800ab2f3  add     rax, rdx
0x1800ab2f6  lea     rdx, [rsp+1E0h+var_198]
0x1800ab2fb  movups  xmmword ptr [rcx+50h], xmm1
0x1800ab2ff  movups  xmmword ptr [rcx+60h], xmm0
0x1800ab303  movups  xmm0, xmmword ptr [rdx]
0x1800ab306  movups  xmm1, xmmword ptr [rdx+10h]
0x1800ab30a  movups  xmmword ptr [rax], xmm0
0x1800ab30d  movups  xmm0, xmmword ptr [rdx+20h]
0x1800ab311  movups  xmmword ptr [rax+10h], xmm1
0x1800ab315  movups  xmm1, xmmword ptr [rdx+30h]
0x1800ab319  movups  xmmword ptr [rax+20h], xmm0
0x1800ab31d  movups  xmm0, xmmword ptr [rdx+40h]
0x1800ab321  movups  xmmword ptr [rax+30h], xmm1
0x1800ab325  movups  xmm1, xmmword ptr [rdx+50h]
0x1800ab329  movups  xmmword ptr [rax+40h], xmm0
0x1800ab32d  movups  xmm0, xmmword ptr [rdx+60h]
0x1800ab331  movups  xmmword ptr [rax+50h], xmm1
0x1800ab335  movups  xmm1, xmmword ptr [rdx+70h]
0x1800ab339  add     rdx, r10
0x1800ab33c  movups  xmmword ptr [rax+60h], xmm0
0x1800ab340  movups  xmmword ptr [rax+70h], xmm1
0x1800ab344  add     rax, r10
0x1800ab347  sub     r14, 1
0x1800ab34b  jnz     short loc_1800AB303
0x1800ab34d  movups  xmm0, xmmword ptr [rdx]
0x1800ab350  movups  xmm1, xmmword ptr [rdx+10h]
0x1800ab354  movups  xmmword ptr [rax], xmm0
0x1800ab357  movups  xmm0, xmmword ptr [rdx+20h]
0x1800ab35b  movups  xmmword ptr [rax+10h], xmm1
0x1800ab35f  movups  xmm1, xmmword ptr [rdx+30h]
  ... truncated ...
```
