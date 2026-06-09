# DavWorkerThread

- ea: `0x18000ce10`
- end: `0x18000d741`
- name: `DavWorkerThread`
- size: `2353`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000b7dc`
- `0x18000b89c`
- `0x18000bd30`
- `0x18000ca04`
- `0x18000ce10`
- `0x18000d804`
- `0x18000d858`
- `0x18000d8b8`
- `0x180011360`
- `0x1800113c8`
- `0x180028f90`
- `0x180029000`
- `0x180029654`
- `0x1800296e8`
- `0x18002cf62`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d64e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d113`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d165`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d113`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cfb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cfb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d076`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cf07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cf07`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d01f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d01f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d354`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d386`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d3b8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d3ea`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d41c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d4ec`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d51e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d550`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d57b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d5a6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d354`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d386`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d3b8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d3ea`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d41c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d4ec`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d51e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d550`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d57b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d5a6`
- `KERNEL32!LocalAlloc` at `0x18000cf9f`
- `KERNEL32!LocalAlloc` at `0x18000cf9f`

## pseudocode

```c
__int64 __fastcall DavWorkerThread(_DWORD *Parameter, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  char *v4; // rdx
  _DWORD *v5; // r14
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  DWORD v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rbx
  DWORD LastError; // esi
  char *lpOutBuffer; // rdi
  unsigned int v14; // r12d
  DWORD v15; // r13d
  DWORD *v16; // r15
  __int64 v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  int v19; // r8d
  _QWORD *v20; // rdi
  unsigned int v21; // r13d
  _QWORD *v22; // rcx
  bool v23; // cf
  _QWORD **v24; // rdx
  HLOCAL *v25; // rax
  DWORD v26; // ecx
  __int64 *v27; // rbx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  BOOL v30; // eax
  __int64 v31; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v33; // rbx
  DWORD v34; // eax
  __int64 v35; // r9
  __int64 (__fastcall *v36)(); // rcx
  int v37; // eax
  unsigned int v38; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-68h] BYREF
  __int64 v41; // [rsp+48h] [rbp-60h] BYREF
  __int64 v42; // [rsp+50h] [rbp-58h]
  int v44; // [rsp+B8h] [rbp+10h]
  int v45; // [rsp+C0h] [rbp+18h]
  unsigned int v46; // [rsp+C8h] [rbp+20h]

  v3 = *(_QWORD *)Parameter;
  v4 = (char *)Parameter - *(_QWORD *)Parameter;
  v42 = *(_QWORD *)Parameter;
  v41 = 0;
  v5 = Parameter;
  v6 = (__int64)((unsigned __int128)((__int64)(v4 - 24) * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 3;
  v7 = (v6 >> 63) + v6;
  Parameter[8] = v7;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, a3, *((_QWORD *)Parameter + 1), Parameter[4]);
  v8 = UMReflectorOpenWorker(DavReflectorHandle, &v41);
  v11 = v41;
  LastError = v8;
  if ( v8 )
    goto LABEL_141;
  if ( !v41 )
  {
    LastError = 1359;
LABEL_141:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_LD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v10, (unsigned int)v5[4], LastError);
    goto LABEL_133;
  }
  lpOutBuffer = 0;
  v44 = 0;
  v14 = 0;
  v45 = 0;
  v15 = 0;
  v46 = 0;
  v16 = 0;
  BytesReturned = 0;
  if ( *(_BYTE *)(v3 + 16) )
    goto LABEL_133;
  while ( 1 )
  {
    if ( lpOutBuffer )
      goto LABEL_33;
    if ( !v11 )
      goto LABEL_25;
    v17 = *(_QWORD *)(v11 + 16);
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
    if ( *(_DWORD *)(v17 + 64) )
      break;
    v19 = *(_DWORD *)(v17 + 120);
    v20 = 0;
    v21 = 9220;
    if ( v19 )
    {
      v22 = *(_QWORD **)(v17 + 104);
      if ( v22 != (_QWORD *)(v17 + 104) )
      {
        do
        {
          if ( v20 )
            goto LABEL_18;
          v20 = v22 - 2;
          v23 = *((_DWORD *)v22 - 4) < 0x2404u;
          v22 = (_QWORD *)*v22;
          if ( v23 )
            v20 = 0;
        }
        while ( v22 != (_QWORD *)(v17 + 104) );
        if ( v20 )
        {
LABEL_18:
          *(_DWORD *)(v17 + 120) = v19 - 1;
          v24 = (_QWORD **)v20[2];
          if ( v24[1] != v20 + 2 || (v25 = (HLOCAL *)v20[3], *v25 != v20 + 2) )
LABEL_139:
            __fastfail(3u);
          *v25 = v24;
          v24[1] = v25;
          v21 = *(_DWORD *)v20;
        }
      }
    }
    if ( !v20 )
    {
      v20 = LocalAlloc(0, v21);
      if ( !v20 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
        v5 = Parameter;
        v15 = BytesReturned;
        goto LABEL_24;
      }
    }
    memset_0(v20, 0, v21);
    v20[1] = v17;
    v27 = (__int64 *)(v17 + 88);
    *(_DWORD *)v20 = v21;
    *((_DWORD *)v20 + 8) = 3;
    v28 = *v27;
    if ( *(__int64 **)(*v27 + 8) != v27 )
      goto LABEL_139;
    v29 = v20 + 2;
    lpOutBuffer = (char *)(v20 + 5);
    *v29 = v28;
    v29[1] = v27;
    *(_QWORD *)(v28 + 8) = v29;
    *v27 = (__int64)v29;
    *((_DWORD *)lpOutBuffer + 4) = 9180;
    LeaveCriticalSection(v18);
    v11 = v41;
    v14 = 0;
    v8 = v44;
    v5 = Parameter;
    v15 = BytesReturned;
    v46 = 0;
LABEL_33:
    BytesReturned = 0;
    if ( v11 && lpOutBuffer )
    {
      *((_DWORD *)lpOutBuffer - 2) = 2;
      if ( v16 )
      {
        *(v16 - 2) = 5;
        if ( *(_DWORD *)(v11 + 24) )
        {
          *(_DWORD *)(v11 + 24) = 0;
          if ( v8 )
            v16[5] &= ~1u;
        }
        v30 = DeviceIoControl(
                *(HANDLE *)(v11 + 32),
                0x140382u,
                v16,
                v16[4],
                lpOutBuffer,
                *((_DWORD *)lpOutBuffer + 4),
                &BytesReturned,
                0);
        *(v16 - 2) = 6;
      }
      else
      {
        if ( *(_DWORD *)(v11 + 24) )
        {
          if ( !v8 )
            *((_DWORD *)lpOutBuffer + 5) |= 1u;
          *(_DWORD *)(v11 + 24) = 0;
        }
        v30 = DeviceIoControl(
                *(HANDLE *)(v11 + 32),
                0x14037Eu,
                0,
                0,
                lpOutBuffer,
                *((_DWORD *)lpOutBuffer + 4),
                &BytesReturned,
                0);
      }
      if ( v30 )
      {
        LastError = 0;
        *((_DWORD *)lpOutBuffer - 2) = 4;
        if ( (lpOutBuffer[20] & 1) != 0 )
          *(_DWORD *)(v11 + 24) = 1;
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          v31 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          CurrentThreadId = GetCurrentThreadId();
          WPP_SF_Dd(v31, 11, WPP_5c5973c51195330a8a6f57b2bd7dab85_Traceguids, CurrentThreadId, LastError);
        }
        v11 = v41;
        *((_DWORD *)lpOutBuffer - 2) = 3;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        v33 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v34 = GetCurrentThreadId();
        WPP_SF_d(v33, 10, WPP_5c5973c51195330a8a6f57b2bd7dab85_Traceguids, v34);
        v11 = v41;
      }
      LastError = 87;
    }
    if ( v16 )
    {
      UMReflectorCompleteWorkItem(v11, v16);
      v16 = 0;
    }
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_LLd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, (unsigned int)v5[4], LastError, 10 - v15);
      BytesReturned = ++v15;
      if ( v15 >= 0xA || *(_BYTE *)(v42 + 16) == 1 )
        goto LABEL_125;
      memset_0(lpOutBuffer, 0, 0x23DCu);
      *((_DWORD *)lpOutBuffer + 4) = 9180;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids,
          (unsigned int)v5[4]);
      v26 = 100;
      goto LABEL_30;
    }
    v35 = *((unsigned int *)lpOutBuffer + 12);
    v15 = 0;
    BytesReturned = 0;
    if ( (int)v35 > 7 )
    {
      switch ( (_DWORD)v35 )
      {
        case 8:
          v36 = DavFsFinalizeVNetRoot;
          break;
        case 9:
          LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
          RevertToSelf();
          v44 = 1;
          if ( LastError )
            goto LABEL_114;
          v45 = 1;
          v36 = (__int64 (__fastcall *)())DavFsReName;
          break;
        case 0xA:
          LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
          RevertToSelf();
          v44 = 1;
          if ( LastError )
            goto LABEL_114;
          v45 = 1;
          v36 = (__int64 (__fastcall *)())DavFsSetFileInformation;
          break;
        case 0xB:
          LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
          RevertToSelf();
          v44 = 1;
          if ( LastError )
            goto LABEL_114;
          v45 = 1;
          v36 = (__int64 (__fastcall *)())DavFsQueryVolumeInformation;
          break;
        case 0xC:
          LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
          RevertToSelf();
          v44 = 1;
          if ( LastError )
            goto LABEL_114;
          v45 = 1;
          v36 = (__int64 (__fastcall *)())DavFsLockRefresh;
          break;
        case 0xD:
          LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
          RevertToSelf();
          v44 = 1;
          if ( LastError )
            goto LABEL_114;
          v45 = 1;
          v36 = (__int64 (__fastcall *)())DavFsFsCtl;
          break;
        case 0xE:
          *((_QWORD *)lpOutBuffer + 9) = -1;
          v36 = DavDevFsCtl;
          v44 = 1;
          v45 = 0;
          break;
        default:
LABEL_97:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, v35);
          goto LABEL_113;
      }
    }
    else if ( (_DWORD)v35 == 7 )
    {
      v36 = DavFsFinalizeFcb;
    }
    else if ( (_DWORD)v35 )
    {
      switch ( (_DWORD)v35 )
      {
        case 1:
          LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
          RevertToSelf();
          v44 = 1;
          if ( LastError )
            goto LABEL_114;
          v45 = 1;
          v36 = (__int64 (__fastcall *)())DavFsCreateVNetRoot;
          break;
        case 2:
          LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
          RevertToSelf();
          v44 = 1;
          if ( LastError )
            goto LABEL_114;
          v45 = 1;
          v36 = (__int64 (__fastcall *)())DavFsQueryDirectory;
          break;
        case 3:
          LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
          RevertToSelf();
          v44 = 1;
          if ( LastError )
            goto LABEL_114;
          v45 = 1;
          v36 = (__int64 (__fastcall *)())DavFsClose;
          break;
        case 4:
          LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
          RevertToSelf();
          v44 = 1;
          if ( LastError )
            goto LABEL_114;
          v45 = 1;
          v36 = (__int64 (__fastcall *)())DavFsCreateSrvCall;
          break;
        case 5:
          v36 = DavFsFinalizeSrvCall;
          break;
        case 6:
          v36 = DavFsFinalizeFobx;
          break;
        default:
          goto LABEL_97;
      }
    }
    else
    {
      LastError = DavFsSetTheDavCallBackContext(lpOutBuffer);
      RevertToSelf();
      v44 = 1;
      if ( LastError )
        goto LABEL_114;
      v45 = 1;
      v36 = (__int64 (__fastcall *)())DavFsCreate;
    }
    LastError = DavPostWorkItem(v36, lpOutBuffer);
    if ( LastError )
    {
LABEL_114:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, LastError);
      if ( v45 )
        DavFsFinalizeTheDavCallBackContext(lpOutBuffer);
      v37 = DavDosErrorToNtStatus(LastError);
      *((_DWORD *)lpOutBuffer + 8) = v37;
      if ( !v37 )
        __debugbreak();
      goto LABEL_121;
    }
LABEL_113:
    lpOutBuffer = 0;
LABEL_121:
    v16 = (DWORD *)lpOutBuffer;
    lpOutBuffer = 0;
LABEL_122:
    if ( *(_BYTE *)(v42 + 16) )
      goto LABEL_125;
    v8 = v44;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
LABEL_24:
  v14 = v46;
  v11 = v41;
LABEL_25:
  lpOutBuffer = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_LD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v10, (unsigned int)v5[4], 10 - v14);
  v46 = ++v14;
  if ( v14 < 0xA )
  {
    v26 = 250;
LABEL_30:
    Sleep(v26);
    goto LABEL_122;
  }
  LastError = GetLastError();
LABEL_125:
  if ( v16 )
  {
    v38 = UMReflectorSendResponse(v11, v16);
    if ( v38 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, v38);
    UMReflectorCompleteWorkItem(v11, v16);
  }
  if ( lpOutBuffer )
    UMReflectorCompleteWorkItem(v11, lpOutBuffer);
LABEL_133:
  if ( v11 )
    UMReflectorCloseWorker(v11);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_LD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v10, (unsigned int)v5[4], LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000ce10  mov     [rsp+arg_0], rcx
0x18000ce15  push    rbx
0x18000ce16  push    rbp
0x18000ce17  push    rsi
0x18000ce18  push    rdi
0x18000ce19  push    r12
0x18000ce1b  push    r13
0x18000ce1d  push    r14
0x18000ce1f  push    r15
0x18000ce21  sub     rsp, 68h
0x18000ce25  mov     rbp, [rcx]
0x18000ce28  mov     rdx, rcx
0x18000ce2b  sub     rdx, rbp
0x18000ce2e  mov     [rsp+0A8h+var_58], rbp
0x18000ce33  sub     rdx, 18h
0x18000ce37  mov     [rsp+0A8h+var_60], 0
0x18000ce40  mov     rax, 2AAAAAAAAAAAAAABh
0x18000ce4a  mov     r14, rcx
0x18000ce4d  imul    rdx
0x18000ce50  sar     rdx, 3
0x18000ce54  mov     rax, rdx
0x18000ce57  shr     rax, 3Fh
0x18000ce5b  add     rdx, rax
0x18000ce5e  mov     [rcx+20h], edx
0x18000ce61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce68  lea     rdi, WPP_GLOBAL_Control
0x18000ce6f  cmp     rcx, rdi
0x18000ce72  jz      short loc_18000CE8F
0x18000ce74  test    byte ptr [rcx+1Ch], 2
0x18000ce78  jz      short loc_18000CE8F
0x18000ce7a  mov     eax, [r14+10h]
0x18000ce7e  mov     r9, [r14+8]
0x18000ce82  mov     rcx, [rcx+10h]
0x18000ce86  mov     dword ptr [rsp+0A8h+lpOutBuffer], eax
0x18000ce8a  call    WPP_SF_qL
0x18000ce8f  mov     rcx, cs:DavReflectorHandle
0x18000ce96  lea     rdx, [rsp+0A8h+var_60]
0x18000ce9b  call    UMReflectorOpenWorker
0x18000cea0  mov     rbx, [rsp+0A8h+var_60]
0x18000cea5  mov     esi, eax
0x18000cea7  test    eax, eax
0x18000cea9  jnz     loc_18000D711
0x18000ceaf  test    rbx, rbx
0x18000ceb2  jz      loc_18000D70C
0x18000ceb8  xor     edi, edi
0x18000ceba  mov     [rsp+0A8h+arg_8], eax
0x18000cec1  xor     r12d, r12d
0x18000cec4  mov     [rsp+0A8h+arg_10], edi
0x18000cecb  xor     r13d, r13d
0x18000cece  mov     [rsp+0A8h+arg_18], r12d
0x18000ced6  xor     r15d, r15d
0x18000ced9  mov     [rsp+0A8h+BytesReturned], r13d
0x18000cede  cmp     [rbp+10h], al
0x18000cee1  jnz     loc_18000D6B6
0x18000cee7  lea     ebp, [rax+1]
0x18000ceea  test    rdi, rdi
0x18000ceed  jnz     loc_18000D0A0
0x18000cef3  test    rbx, rbx
0x18000cef6  jz      loc_18000CFD0
0x18000cefc  mov     rbx, [rbx+10h]
0x18000cf00  lea     r12, [rbx+10h]
0x18000cf04  mov     rcx, r12; lpCriticalSection
0x18000cf07  call    cs:__imp_EnterCriticalSection
0x18000cf0d  cmp     [rbx+40h], edi
0x18000cf10  jz      short loc_18000CF20
0x18000cf12  mov     rcx, r12; lpCriticalSection
0x18000cf15  call    cs:__imp_LeaveCriticalSection
0x18000cf1b  jmp     loc_18000CFC3
0x18000cf20  mov     r8d, [rbx+78h]
0x18000cf24  xor     edi, edi
0x18000cf26  mov     r9d, 2404h
0x18000cf2c  mov     r13d, r9d
0x18000cf2f  test    r8d, r8d
0x18000cf32  jz      short loc_18000CF8E
0x18000cf34  lea     rdx, [rbx+68h]
0x18000cf38  mov     rcx, [rdx]
0x18000cf3b  cmp     rcx, rdx
0x18000cf3e  jz      short loc_18000CF8E
0x18000cf40  test    rdi, rdi
0x18000cf43  jnz     short loc_18000CF5F
0x18000cf45  lea     rdi, [rcx-10h]
0x18000cf49  xor     eax, eax
0x18000cf4b  cmp     [rdi], r9d
0x18000cf4e  mov     rcx, [rcx]
0x18000cf51  cmovb   rdi, rax
0x18000cf55  cmp     rcx, rdx
0x18000cf58  jnz     short loc_18000CF40
0x18000cf5a  test    rdi, rdi
0x18000cf5d  jz      short loc_18000CF8E
0x18000cf5f  lea     rcx, [rdi+10h]
0x18000cf63  lea     eax, [r8-1]
0x18000cf67  mov     [rbx+78h], eax
0x18000cf6a  mov     rdx, [rcx]
0x18000cf6d  cmp     [rdx+8], rcx
0x18000cf71  jnz     loc_18000D705
0x18000cf77  mov     rax, [rdi+18h]
0x18000cf7b  cmp     [rax], rcx
0x18000cf7e  jnz     loc_18000D705
0x18000cf84  mov     [rax], rdx
0x18000cf87  mov     [rdx+8], rax
0x18000cf8b  mov     r13d, [rdi]
0x18000cf8e  mov     r14d, r13d
0x18000cf91  test    rdi, rdi
0x18000cf94  jnz     loc_18000D02A
0x18000cf9a  mov     edx, r14d; uBytes
0x18000cf9d  xor     ecx, ecx; uFlags
0x18000cf9f  call    cs:__imp_LocalAlloc
0x18000cfa5  mov     rdi, rax
0x18000cfa8  test    rax, rax
0x18000cfab  jnz     short loc_18000D02A
0x18000cfad  mov     rcx, r12; lpCriticalSection
0x18000cfb0  call    cs:__imp_LeaveCriticalSection
0x18000cfb6  mov     r14, [rsp+0A8h+arg_0]
0x18000cfbe  mov     r13d, [rsp+0A8h+BytesReturned]
0x18000cfc3  mov     r12d, [rsp+0A8h+arg_18]
0x18000cfcb  mov     rbx, [rsp+0A8h+var_60]
0x18000cfd0  xor     edi, edi
0x18000cfd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfd9  lea     rax, WPP_GLOBAL_Control
0x18000cfe0  cmp     rcx, rax
0x18000cfe3  jz      short loc_18000D005
0x18000cfe5  test    [rcx+1Ch], bpl
0x18000cfe9  jz      short loc_18000D005
0x18000cfeb  mov     r9d, [r14+10h]
0x18000cfef  lea     eax, [rdi+0Ah]
0x18000cff2  mov     rcx, [rcx+10h]
0x18000cff6  lea     edx, [rdi+19h]
0x18000cff9  sub     eax, r12d
0x18000cffc  mov     dword ptr [rsp+0A8h+lpOutBuffer], eax
0x18000d000  call    WPP_SF_LD
0x18000d005  inc     r12d
0x18000d008  mov     [rsp+0A8h+arg_18], r12d
0x18000d010  cmp     r12d, 0Ah
0x18000d014  jnb     loc_18000D64E
0x18000d01a  mov     ecx, 0FAh; dwMilliseconds
0x18000d01f  call    cs:__imp_Sleep
0x18000d025  jmp     loc_18000D637
0x18000d02a  mov     r8, r14; Size
0x18000d02d  xor     edx, edx; Val
0x18000d02f  mov     rcx, rdi; void *
0x18000d032  call    memset_0
0x18000d037  mov     [rdi+8], rbx
0x18000d03b  add     rbx, 58h ; 'X'
0x18000d03f  mov     [rdi], r13d
0x18000d042  mov     dword ptr [rdi+20h], 3
0x18000d049  mov     rcx, [rbx]
0x18000d04c  cmp     [rcx+8], rbx
0x18000d050  jnz     loc_18000D705
0x18000d056  lea     rax, [rdi+10h]
0x18000d05a  add     rdi, 28h ; '('
0x18000d05e  mov     [rax], rcx
0x18000d061  mov     [rax+8], rbx
0x18000d065  mov     [rcx+8], rax
0x18000d069  mov     rcx, r12; lpCriticalSection
0x18000d06c  mov     [rbx], rax
0x18000d06f  mov     dword ptr [rdi+10h], 23DCh
0x18000d076  call    cs:__imp_LeaveCriticalSection
0x18000d07c  mov     rbx, [rsp+0A8h+var_60]
0x18000d081  xor     r12d, r12d
0x18000d084  mov     eax, [rsp+0A8h+arg_8]
0x18000d08b  mov     r14, [rsp+0A8h+arg_0]
0x18000d093  mov     r13d, [rsp+0A8h+BytesReturned]
0x18000d098  mov     [rsp+0A8h+arg_18], r12d
0x18000d0a0  mov     [rsp+0A8h+BytesReturned], 0
0x18000d0a8  test    rbx, rbx
0x18000d0ab  jz      loc_18000D1DA
0x18000d0b1  test    rdi, rdi
0x18000d0b4  jz      loc_18000D1DA
0x18000d0ba  mov     dword ptr [rdi-8], 2
0x18000d0c1  test    r15, r15
0x18000d0c4  jz      short loc_18000D123
0x18000d0c6  mov     dword ptr [r15-8], 5
0x18000d0ce  cmp     dword ptr [rbx+18h], 0
0x18000d0d2  jz      short loc_18000D0E4
0x18000d0d4  mov     dword ptr [rbx+18h], 0
0x18000d0db  test    eax, eax
0x18000d0dd  jz      short loc_18000D0E4
0x18000d0df  and     dword ptr [r15+14h], 0FFFFFFFEh
0x18000d0e4  mov     r9d, [r15+10h]; nInBufferSize
0x18000d0e8  lea     rax, [rsp+0A8h+BytesReturned]
0x18000d0ed  mov     rcx, [rbx+20h]; hDevice
0x18000d0f1  mov     r8, r15; lpInBuffer
0x18000d0f4  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x18000d0fd  mov     edx, 140382h; dwIoControlCode
0x18000d102  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x18000d107  mov     eax, [rdi+10h]
0x18000d10a  mov     [rsp+0A8h+nOutBufferSize], eax; nOutBufferSize
0x18000d10e  mov     [rsp+0A8h+lpOutBuffer], rdi; lpOutBuffer
0x18000d113  call    cs:__imp_DeviceIoControl
0x18000d119  mov     dword ptr [r15-8], 6
0x18000d121  jmp     short loc_18000D16B
0x18000d123  cmp     dword ptr [rbx+18h], 0
0x18000d127  jz      short loc_18000D137
0x18000d129  test    eax, eax
0x18000d12b  jnz     short loc_18000D130
0x18000d12d  or      [rdi+14h], ebp
0x18000d130  mov     dword ptr [rbx+18h], 0
0x18000d137  mov     rcx, [rbx+20h]; hDevice
0x18000d13b  lea     rax, [rsp+0A8h+BytesReturned]
0x18000d140  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x18000d149  xor     r9d, r9d; nInBufferSize
0x18000d14c  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x18000d151  xor     r8d, r8d; lpInBuffer
0x18000d154  mov     eax, [rdi+10h]
0x18000d157  mov     edx, 14037Eh; dwIoControlCode
0x18000d15c  mov     [rsp+0A8h+nOutBufferSize], eax; nOutBufferSize
0x18000d160  mov     [rsp+0A8h+lpOutBuffer], rdi; lpOutBuffer
0x18000d165  call    cs:__imp_DeviceIoControl
0x18000d16b  test    eax, eax
0x18000d16d  jnz     short loc_18000D1C6
0x18000d16f  call    cs:__imp_GetLastError
0x18000d175  mov     esi, eax
0x18000d177  mov     rbx, cs:WPP_GLOBAL_Control
0x18000d17e  lea     rax, WPP_GLOBAL_Control
0x18000d185  cmp     rbx, rax
0x18000d188  jz      short loc_18000D1B8
0x18000d18a  test    dword ptr [rbx+1Ch], 1000h
0x18000d191  jz      short loc_18000D1B8
0x18000d193  mov     rbx, [rbx+10h]
0x18000d197  call    cs:__imp_GetCurrentThreadId
0x18000d19d  mov     edx, 0Bh
0x18000d1a2  mov     dword ptr [rsp+0A8h+lpOutBuffer], esi
0x18000d1a6  mov     r9d, eax
0x18000d1a9  lea     r8, WPP_5c5973c51195330a8a6f57b2bd7dab85_Traceguids
0x18000d1b0  mov     rcx, rbx
0x18000d1b3  call    WPP_SF_Dd
0x18000d1b8  mov     rbx, [rsp+0A8h+var_60]
0x18000d1bd  mov     dword ptr [rdi-8], 3
0x18000d1c4  jmp     short loc_18000D221
0x18000d1c6  xor     esi, esi
0x18000d1c8  mov     dword ptr [rdi-8], 4
0x18000d1cf  test    [rdi+14h], bpl
0x18000d1d3  jz      short loc_18000D221
0x18000d1d5  mov     [rbx+18h], ebp
0x18000d1d8  jmp     short loc_18000D221
0x18000d1da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1e1  lea     rax, WPP_GLOBAL_Control
0x18000d1e8  cmp     rcx, rax
0x18000d1eb  jz      short loc_18000D21C
0x18000d1ed  test    dword ptr [rcx+1Ch], 1000h
0x18000d1f4  jz      short loc_18000D21C
0x18000d1f6  mov     rbx, [rcx+10h]
0x18000d1fa  call    cs:__imp_GetCurrentThreadId
0x18000d200  mov     edx, 0Ah
0x18000d205  lea     r8, WPP_5c5973c51195330a8a6f57b2bd7dab85_Traceguids
0x18000d20c  mov     r9d, eax
0x18000d20f  mov     rcx, rbx
0x18000d212  call    WPP_SF_d
0x18000d217  mov     rbx, [rsp+0A8h+var_60]
0x18000d21c  mov     esi, 57h ; 'W'
0x18000d221  test    r15, r15
0x18000d224  jz      short loc_18000D234
0x18000d226  mov     rdx, r15
0x18000d229  mov     rcx, rbx
0x18000d22c  call    UMReflectorCompleteWorkItem
0x18000d231  xor     r15d, r15d
0x18000d234  test    esi, esi
0x18000d236  jz      loc_18000D2E6
0x18000d23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d243  lea     rax, WPP_GLOBAL_Control
0x18000d24a  cmp     rcx, rax
0x18000d24d  jz      short loc_18000D272
0x18000d24f  test    [rcx+1Ch], bpl
0x18000d253  jz      short loc_18000D272
0x18000d255  mov     r9d, [r14+10h]
0x18000d259  mov     eax, 0Ah
0x18000d25e  mov     rcx, [rcx+10h]
0x18000d262  sub     eax, r13d
0x18000d265  mov     [rsp+0A8h+nOutBufferSize], eax
0x18000d269  mov     dword ptr [rsp+0A8h+lpOutBuffer], esi
0x18000d26d  call    WPP_SF_LLd
0x18000d272  inc     r13d
0x18000d275  mov     [rsp+0A8h+BytesReturned], r13d
0x18000d27a  cmp     r13d, 0Ah
0x18000d27e  jnb     loc_18000D656
0x18000d284  mov     rax, [rsp+0A8h+var_58]
0x18000d289  cmp     [rax+10h], bpl
0x18000d28d  jz      loc_18000D656
0x18000d293  xor     edx, edx; Val
0x18000d295  mov     r8d, 23DCh; Size
0x18000d29b  mov     rcx, rdi; void *
0x18000d29e  call    memset_0
0x18000d2a3  mov     dword ptr [rdi+10h], 23DCh
0x18000d2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2b1  lea     rax, WPP_GLOBAL_Control
0x18000d2b8  cmp     rcx, rax
0x18000d2bb  jz      short loc_18000D2DC
0x18000d2bd  test    byte ptr [rcx+1Ch], 2
0x18000d2c1  jz      short loc_18000D2DC
0x18000d2c3  mov     r9d, [r14+10h]
0x18000d2c7  lea     r8, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids
0x18000d2ce  mov     rcx, [rcx+10h]
0x18000d2d2  mov     edx, 1Bh
0x18000d2d7  call    WPP_SF_d
0x18000d2dc  mov     ecx, 64h ; 'd'
0x18000d2e1  jmp     loc_18000D01F
0x18000d2e6  mov     r9d, [rdi+30h]
0x18000d2ea  xor     r13d, r13d
0x18000d2ed  mov     [rsp+0A8h+BytesReturned], r13d
0x18000d2f2  cmp     r9d, 7
  ... truncated ...
```
