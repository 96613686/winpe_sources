# ListenOnAllNetworks(void)

- ea: `0x18000ece0`
- end: `0x18000efec`
- name: `?ListenOnAllNetworks@@YAHXZ`
- size: `780`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c078`
- `0x18000ffa0`

## callees

- `0x18000a9ac`
- `0x18000ece0`
- `0x1800271fc`
- `0x180029df0`
- `0x180032570`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ed58`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ed58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ed27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ed27`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ed96`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ed96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eee4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eee4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000ee31`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000ee31`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000eecd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000eecd`
- `WS2_32!WSAEventSelect` at `0x18000eead`
- `WS2_32!WSAEventSelect` at `0x18000eead`

## pseudocode

```c
DWORD ListenOnAllNetworks(void)
{
  int v0; // edi
  struct _SSDPNetwork *i; // rbx
  _DWORD *v2; // rax
  __int64 v3; // r9
  void *v4; // rdx
  DWORD LastError; // eax
  __int64 v6; // rdx
  BOOL v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8

  v0 = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids);
  EnterCriticalSection(&stru_1800452F8);
  for ( i = qword_1800452E8; i != (struct _SSDPNetwork *)&qword_1800452E8; i = *(struct _SSDPNetwork **)i )
  {
    if ( *((_DWORD *)i + 38) != 1 )
    {
      v2 = malloc(0x20u);
      *((_QWORD *)i + 22) = v2;
      if ( v2 )
      {
        *v2 = 1;
        *(_QWORD *)(*((_QWORD *)i + 22) + 8LL) = *((_QWORD *)i + 20);
        *(_QWORD *)(*((_QWORD *)i + 22) + 16LL) = CreateEventA(0, 0, 0, 0);
        v3 = *((_QWORD *)i + 22);
        v4 = *(void **)(v3 + 16);
        if ( v4 )
        {
          v7 = RegisterWaitForSingleObject(
                 (PHANDLE)(v3 + 24),
                 v4,
                 (WAITORTIMERCALLBACK)SsdpNetProc,
                 (PVOID)v3,
                 0xFFFFFFFF,
                 0);
          v8 = *((_QWORD *)i + 22);
          if ( v7 )
          {
            if ( WSAEventSelect(*(_QWORD *)(v8 + 8), *(HANDLE *)(v8 + 16), 1) == -1 )
            {
              UnregisterWaitEx(*(HANDLE *)(*((_QWORD *)i + 22) + 24LL), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
              CloseHandle(*(HANDLE *)(*((_QWORD *)i + 22) + 16LL));
              operator delete(*((void **)i + 22));
              *((_QWORD *)i + 22) = 0;
              if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
              {
                LastError = GetLastError();
                v6 = 48;
                goto LABEL_11;
              }
            }
            else
            {
              v0 = 1;
              if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              {
                WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, *((_QWORD *)i + 22), *((_DWORD *)i + 40));
              }
            }
          }
          else
          {
            CloseHandle(*(HANDLE *)(v8 + 16));
            operator delete(*((void **)i + 22));
            *((_QWORD *)i + 22) = 0;
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
            {
              LastError = GetLastError();
              v6 = 47;
              goto LABEL_11;
            }
          }
        }
        else
        {
          operator delete(*((void **)i + 22));
          *((_QWORD *)i + 22) = 0;
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          {
            LastError = GetLastError();
            v6 = 46;
LABEL_11:
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v6,
              WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids,
              LastError);
            continue;
          }
        }
      }
    }
  }
  LeaveCriticalSection(&stru_1800452F8);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids);
    return GetLastError();
  }
}

```

## disassembly

```asm
0x18000ece0  push    rbx
0x18000ece2  push    rbp
0x18000ece3  push    rdi
0x18000ece4  push    r13
0x18000ece6  push    r15
0x18000ece8  sub     rsp, 30h
0x18000ecec  xor     edi, edi
0x18000ecee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecf5  lea     rbp, WPP_GLOBAL_Control
0x18000ecfc  lea     r15, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000ed03  cmp     rcx, rbp
0x18000ed06  jz      short loc_18000ED20
0x18000ed08  test    dword ptr [rcx+1Ch], 200h
0x18000ed0f  jz      short loc_18000ED20
0x18000ed11  mov     rcx, [rcx+10h]
0x18000ed15  lea     edx, [rdi+2Dh]
0x18000ed18  mov     r8, r15
0x18000ed1b  call    WPP_SF_
0x18000ed20  lea     rcx, stru_1800452F8; lpCriticalSection
0x18000ed27  call    cs:__imp_EnterCriticalSection
0x18000ed2e  nop     dword ptr [rax+rax+00h]
0x18000ed33  mov     rbx, cs:qword_1800452E8
0x18000ed3a  lea     r13, qword_1800452E8
0x18000ed41  jmp     loc_18000EF66
0x18000ed46  cmp     dword ptr [rbx+98h], 1
0x18000ed4d  jz      loc_18000EF63
0x18000ed53  mov     ecx, 20h ; ' '; Size
0x18000ed58  call    cs:__imp_malloc
0x18000ed5f  nop     dword ptr [rax+rax+00h]
0x18000ed64  mov     [rbx+0B0h], rax
0x18000ed6b  test    rax, rax
0x18000ed6e  jz      loc_18000EF63
0x18000ed74  mov     dword ptr [rax], 1
0x18000ed7a  xor     r9d, r9d; lpName
0x18000ed7d  mov     rcx, [rbx+0B0h]
0x18000ed84  xor     r8d, r8d; bInitialState
0x18000ed87  mov     rax, [rbx+0A0h]
0x18000ed8e  xor     edx, edx; bManualReset
0x18000ed90  mov     [rcx+8], rax
0x18000ed94  xor     ecx, ecx; lpEventAttributes
0x18000ed96  call    cs:__imp_CreateEventA
0x18000ed9d  nop     dword ptr [rax+rax+00h]
0x18000eda2  mov     rcx, [rbx+0B0h]
0x18000eda9  mov     [rcx+10h], rax
0x18000edad  mov     r9, [rbx+0B0h]; Context
0x18000edb4  mov     rdx, [r9+10h]; hObject
0x18000edb8  test    rdx, rdx
0x18000edbb  jnz     short loc_18000EE16
0x18000edbd  mov     rcx, r9; void *
0x18000edc0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000edc5  mov     qword ptr [rbx+0B0h], 0
0x18000edd0  mov     rax, cs:WPP_GLOBAL_Control
0x18000edd7  cmp     rax, rbp
0x18000edda  jz      loc_18000EF63
0x18000ede0  test    byte ptr [rax+1Ch], 1
0x18000ede4  jz      loc_18000EF63
0x18000edea  call    cs:__imp_GetLastError
0x18000edf1  nop     dword ptr [rax+rax+00h]
0x18000edf6  mov     edx, 2Eh ; '.'
0x18000edfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee02  mov     r9d, eax
0x18000ee05  mov     r8, r15
0x18000ee08  mov     rcx, [rcx+10h]
0x18000ee0c  call    WPP_SF_d
0x18000ee11  jmp     loc_18000EF63
0x18000ee16  lea     rcx, [r9+18h]; phNewWaitObject
0x18000ee1a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000ee22  lea     r8, ?SsdpNetProc@@YAXPEAXE@Z; Callback
0x18000ee29  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000ee31  call    cs:__imp_RegisterWaitForSingleObject
0x18000ee38  nop     dword ptr [rax+rax+00h]
0x18000ee3d  mov     rcx, [rbx+0B0h]
0x18000ee44  test    eax, eax
0x18000ee46  jnz     short loc_18000EE9F
0x18000ee48  mov     rcx, [rcx+10h]; hObject
0x18000ee4c  call    cs:__imp_CloseHandle
0x18000ee53  nop     dword ptr [rax+rax+00h]
0x18000ee58  mov     rcx, [rbx+0B0h]; void *
0x18000ee5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ee64  mov     qword ptr [rbx+0B0h], 0
0x18000ee6f  mov     rax, cs:WPP_GLOBAL_Control
0x18000ee76  cmp     rax, rbp
0x18000ee79  jz      loc_18000EF63
0x18000ee7f  test    byte ptr [rax+1Ch], 1
0x18000ee83  jz      loc_18000EF63
0x18000ee89  call    cs:__imp_GetLastError
0x18000ee90  nop     dword ptr [rax+rax+00h]
0x18000ee95  mov     edx, 2Fh ; '/'
0x18000ee9a  jmp     loc_18000EDFB
0x18000ee9f  mov     rdx, [rcx+10h]; hEventObject
0x18000eea3  mov     r8d, 1; lNetworkEvents
0x18000eea9  mov     rcx, [rcx+8]; s
0x18000eead  call    cs:__imp_WSAEventSelect
0x18000eeb4  nop     dword ptr [rax+rax+00h]
0x18000eeb9  cmp     eax, 0FFFFFFFFh
0x18000eebc  jnz     short loc_18000EF2F
0x18000eebe  mov     rcx, [rbx+0B0h]
0x18000eec5  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000eec9  mov     rcx, [rcx+18h]; WaitHandle
0x18000eecd  call    cs:__imp_UnregisterWaitEx
0x18000eed4  nop     dword ptr [rax+rax+00h]
0x18000eed9  mov     rcx, [rbx+0B0h]
0x18000eee0  mov     rcx, [rcx+10h]; hObject
0x18000eee4  call    cs:__imp_CloseHandle
0x18000eeeb  nop     dword ptr [rax+rax+00h]
0x18000eef0  mov     rcx, [rbx+0B0h]; void *
0x18000eef7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000eefc  mov     qword ptr [rbx+0B0h], 0
0x18000ef07  mov     rax, cs:WPP_GLOBAL_Control
0x18000ef0e  cmp     rax, rbp
0x18000ef11  jz      short loc_18000EF63
0x18000ef13  test    byte ptr [rax+1Ch], 1
0x18000ef17  jz      short loc_18000EF63
0x18000ef19  call    cs:__imp_GetLastError
0x18000ef20  nop     dword ptr [rax+rax+00h]
0x18000ef25  mov     edx, 30h ; '0'
0x18000ef2a  jmp     loc_18000EDFB
0x18000ef2f  mov     edi, 1
0x18000ef34  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef3b  cmp     rcx, rbp
0x18000ef3e  jz      short loc_18000EF63
0x18000ef40  test    dword ptr [rcx+1Ch], 200h
0x18000ef47  jz      short loc_18000EF63
0x18000ef49  mov     eax, [rbx+0A0h]
0x18000ef4f  mov     r9, [rbx+0B0h]
0x18000ef56  mov     rcx, [rcx+10h]
0x18000ef5a  mov     [rsp+58h+dwMilliseconds], eax
0x18000ef5e  call    WPP_SF_qD
0x18000ef63  mov     rbx, [rbx]
0x18000ef66  cmp     rbx, r13
0x18000ef69  jnz     loc_18000ED46
0x18000ef6f  lea     rcx, stru_1800452F8; lpCriticalSection
0x18000ef76  call    cs:__imp_LeaveCriticalSection
0x18000ef7d  nop     dword ptr [rax+rax+00h]
0x18000ef82  test    edi, edi
0x18000ef84  jz      short loc_18000EFB0
0x18000ef86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef8d  cmp     rcx, rbp
0x18000ef90  jz      short loc_18000EFAC
0x18000ef92  test    dword ptr [rcx+1Ch], 200h
0x18000ef99  jz      short loc_18000EFAC
0x18000ef9b  mov     rcx, [rcx+10h]
0x18000ef9f  mov     edx, 32h ; '2'
0x18000efa4  mov     r8, r15
0x18000efa7  call    WPP_SF_
0x18000efac  xor     eax, eax
0x18000efae  jmp     short loc_18000EFDF
0x18000efb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efb7  cmp     rcx, rbp
0x18000efba  jz      short loc_18000EFD3
0x18000efbc  test    byte ptr [rcx+1Ch], 1
0x18000efc0  jz      short loc_18000EFD3
0x18000efc2  mov     rcx, [rcx+10h]
0x18000efc6  mov     edx, 33h ; '3'
0x18000efcb  mov     r8, r15
0x18000efce  call    WPP_SF_
0x18000efd3  call    cs:__imp_GetLastError
0x18000efda  nop     dword ptr [rax+rax+00h]
0x18000efdf  add     rsp, 30h
0x18000efe3  pop     r15
0x18000efe5  pop     r13
0x18000efe7  pop     rdi
0x18000efe8  pop     rbp
0x18000efe9  pop     rbx
0x18000efea  retn
```
