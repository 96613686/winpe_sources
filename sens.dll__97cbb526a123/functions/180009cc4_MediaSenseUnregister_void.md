# MediaSenseUnregister(void)

- ea: `0x180009cc4`
- end: `0x180009e75`
- name: `?MediaSenseUnregister@@YAHXZ`
- size: `433`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800093d8`

## callees

- `0x180008300`
- `0x180009cc4`
- `0x180009f64`
- `0x18000a7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009cf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009cf5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180009d27`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180009d27`
- `WMICLNT!WmiNotificationRegistrationW` at `0x180009da7`
- `WMICLNT!WmiNotificationRegistrationW` at `0x180009e09`
- `WMICLNT!WmiNotificationRegistrationW` at `0x180009da7`
- `WMICLNT!WmiNotificationRegistrationW` at `0x180009e09`

## pseudocode

```c
__int64 MediaSenseUnregister(void)
{
  unsigned int v0; // ebx
  BOOL v1; // edi
  const char *v2; // r9
  unsigned int v3; // eax
  unsigned int v4; // eax
  GUID v6; // [rsp+30h] [rbp-48h] BYREF

  v6 = 0;
  v0 = 1;
  EnterCriticalSection(&gSensLock);
  v1 = gdwMediaSenseState == 2;
  gdwMediaSenseState = 3;
  if ( ghMediaTimer )
  {
    v0 = DeleteTimerQueueTimer(0, ghMediaTimer, 0);
    ghMediaTimer = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v2 = "succeeded";
      if ( !v0 )
        v2 = "failed!";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids, v2);
    }
  }
  if ( v1 )
  {
    v6 = GUID_NDIS_STATUS_MEDIA_DISCONNECT;
    v3 = WmiNotificationRegistrationW(&v6, 0, EventCallbackRoutine, 0, 4);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids, v3);
      }
      v0 = 0;
    }
    v6 = GUID_NDIS_STATUS_MEDIA_CONNECT;
    v4 = WmiNotificationRegistrationW(&v6, 0, EventCallbackRoutine, 0, 4);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids, v4);
      }
      v0 = 0;
    }
  }
  gdwMediaSenseState = 4;
  LeaveCriticalSection(&gSensLock);
  return v0;
}

```

## disassembly

```asm
0x180009cc4  push    rbx
0x180009cc6  push    rsi
0x180009cc7  push    rdi
0x180009cc8  push    r14
0x180009cca  sub     rsp, 58h
0x180009cce  mov     rax, cs:__security_cookie
0x180009cd5  xor     rax, rsp
0x180009cd8  mov     [rsp+78h+var_38], rax
0x180009cdd  xorps   xmm0, xmm0
0x180009ce0  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009ce7  mov     esi, 1
0x180009cec  xor     edi, edi
0x180009cee  movups  [rsp+78h+var_48], xmm0
0x180009cf3  mov     ebx, esi
0x180009cf5  call    cs:__imp_EnterCriticalSection
0x180009cfb  cmp     cs:?gdwMediaSenseState@@3KA, 2; ulong gdwMediaSenseState
0x180009d02  lea     r14, WPP_GLOBAL_Control
0x180009d09  mov     rdx, cs:?ghMediaTimer@@3PEAXEA; Timer
0x180009d10  cmovz   edi, esi
0x180009d13  mov     cs:?gdwMediaSenseState@@3KA, 3; ulong gdwMediaSenseState
0x180009d1d  test    rdx, rdx
0x180009d20  jz      short loc_180009D79
0x180009d22  xor     r8d, r8d; CompletionEvent
0x180009d25  xor     ecx, ecx; TimerQueue
0x180009d27  call    cs:__imp_DeleteTimerQueueTimer
0x180009d2d  mov     ebx, eax
0x180009d2f  mov     cs:?ghMediaTimer@@3PEAXEA, 0; void * ghMediaTimer
0x180009d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d41  cmp     rcx, r14
0x180009d44  jz      short loc_180009D79
0x180009d46  test    [rcx+1Ch], sil
0x180009d4a  jz      short loc_180009D79
0x180009d4c  cmp     byte ptr [rcx+19h], 5
0x180009d50  jb      short loc_180009D79
0x180009d52  mov     rcx, [rcx+10h]
0x180009d56  lea     rax, aFailed; "failed!"
0x180009d5d  test    ebx, ebx
0x180009d5f  lea     r9, aSucceeded; "succeeded"
0x180009d66  lea     edx, [rsi+1Ch]
0x180009d69  cmovz   r9, rax
0x180009d6d  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180009d74  call    WPP_SF_s
0x180009d79  test    edi, edi
0x180009d7b  jz      loc_180009E45
0x180009d81  movups  xmm0, xmmword ptr cs:GUID_NDIS_STATUS_MEDIA_DISCONNECT.Data1
0x180009d88  xor     r9d, r9d
0x180009d8b  mov     [rsp+78h+var_58], 4
0x180009d93  lea     r8, ?EventCallbackRoutine@@YAXPEAU_WNODE_HEADER@@K@Z; EventCallbackRoutine(_WNODE_HEADER *,ulong)
0x180009d9a  xor     edx, edx
0x180009d9c  lea     rcx, [rsp+78h+var_48]
0x180009da1  movdqu  [rsp+78h+var_48], xmm0
0x180009da7  call    cs:__imp_WmiNotificationRegistrationW
0x180009dad  test    eax, eax
0x180009daf  jz      short loc_180009DE3
0x180009db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009db8  cmp     rcx, r14
0x180009dbb  jz      short loc_180009DE1
0x180009dbd  test    [rcx+1Ch], sil
0x180009dc1  jz      short loc_180009DE1
0x180009dc3  cmp     byte ptr [rcx+19h], 2
0x180009dc7  jb      short loc_180009DE1
0x180009dc9  mov     rcx, [rcx+10h]
0x180009dcd  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180009dd4  mov     edx, 1Eh
0x180009dd9  mov     r9d, eax
0x180009ddc  call    WPP_SF_d
0x180009de1  xor     ebx, ebx
0x180009de3  movups  xmm0, xmmword ptr cs:GUID_NDIS_STATUS_MEDIA_CONNECT.Data1
0x180009dea  xor     r9d, r9d
0x180009ded  mov     [rsp+78h+var_58], 4
0x180009df5  lea     r8, ?EventCallbackRoutine@@YAXPEAU_WNODE_HEADER@@K@Z; EventCallbackRoutine(_WNODE_HEADER *,ulong)
0x180009dfc  xor     edx, edx
0x180009dfe  lea     rcx, [rsp+78h+var_48]
0x180009e03  movdqu  [rsp+78h+var_48], xmm0
0x180009e09  call    cs:__imp_WmiNotificationRegistrationW
0x180009e0f  test    eax, eax
0x180009e11  jz      short loc_180009E45
0x180009e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e1a  cmp     rcx, r14
0x180009e1d  jz      short loc_180009E43
0x180009e1f  test    [rcx+1Ch], sil
0x180009e23  jz      short loc_180009E43
0x180009e25  cmp     byte ptr [rcx+19h], 2
0x180009e29  jb      short loc_180009E43
0x180009e2b  mov     rcx, [rcx+10h]
0x180009e2f  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180009e36  mov     edx, 1Fh
0x180009e3b  mov     r9d, eax
0x180009e3e  call    WPP_SF_d
0x180009e43  xor     ebx, ebx
0x180009e45  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009e4c  mov     cs:?gdwMediaSenseState@@3KA, 4; ulong gdwMediaSenseState
0x180009e56  call    cs:__imp_LeaveCriticalSection
0x180009e5c  mov     eax, ebx
0x180009e5e  mov     rcx, [rsp+78h+var_38]
0x180009e63  xor     rcx, rsp; StackCookie
0x180009e66  call    __security_check_cookie
0x180009e6b  add     rsp, 58h
0x180009e6f  pop     r14
0x180009e71  pop     rdi
0x180009e72  pop     rsi
0x180009e73  pop     rbx
0x180009e74  retn
```
