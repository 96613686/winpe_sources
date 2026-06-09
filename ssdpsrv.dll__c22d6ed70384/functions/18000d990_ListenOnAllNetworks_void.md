# ListenOnAllNetworks(void)

- ea: `0x18000d990`
- end: `0x18000dc4d`
- name: `?ListenOnAllNetworks@@YAHXZ`
- size: `701`
- prototype: `DWORD(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000a768`
- `0x18000eb10`

## callees

- `0x18000936c`
- `0x18000d990`
- `0x1800255a8`
- `0x180028000`
- `0x180030200`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000da02`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000da02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dbe4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dbe4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d9d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d9d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000da3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000da3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db5e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000dac9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000dac9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000db4d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000db4d`
- `WS2_32!WSAEventSelect` at `0x18000db33`
- `WS2_32!WSAEventSelect` at `0x18000db33`

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
  EnterCriticalSection(&stru_180042200);
  for ( i = Block; i != (struct _SSDPNetwork *)&Block; i = *(struct _SSDPNetwork **)i )
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
          v7 = RegisterWaitForSingleObject((PHANDLE)(v3 + 24), v4, SsdpNetProc, (PVOID)v3, 0xFFFFFFFF, 0);
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
  LeaveCriticalSection(&stru_180042200);
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
0x18000d990  push    rbx
0x18000d992  push    rbp
0x18000d993  push    rdi
0x18000d994  push    r13
0x18000d996  push    r15
0x18000d998  sub     rsp, 30h
0x18000d99c  xor     edi, edi
0x18000d99e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9a5  lea     rbp, WPP_GLOBAL_Control
0x18000d9ac  lea     r15, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000d9b3  cmp     rcx, rbp
0x18000d9b6  jz      short loc_18000D9D0
0x18000d9b8  test    dword ptr [rcx+1Ch], 200h
0x18000d9bf  jz      short loc_18000D9D0
0x18000d9c1  mov     rcx, [rcx+10h]
0x18000d9c5  lea     edx, [rdi+2Dh]
0x18000d9c8  mov     r8, r15
0x18000d9cb  call    WPP_SF_
0x18000d9d0  lea     rcx, stru_180042200; lpCriticalSection
0x18000d9d7  call    cs:__imp_EnterCriticalSection
0x18000d9dd  mov     rbx, cs:Block
0x18000d9e4  lea     r13, Block
0x18000d9eb  jmp     loc_18000DBD4
0x18000d9f0  cmp     dword ptr [rbx+98h], 1
0x18000d9f7  jz      loc_18000DBD1
0x18000d9fd  mov     ecx, 20h ; ' '; Size
0x18000da02  call    cs:__imp_malloc
0x18000da08  mov     [rbx+0B0h], rax
0x18000da0f  test    rax, rax
0x18000da12  jz      loc_18000DBD1
0x18000da18  mov     dword ptr [rax], 1
0x18000da1e  xor     r9d, r9d; lpName
0x18000da21  mov     rcx, [rbx+0B0h]
0x18000da28  xor     r8d, r8d; bInitialState
0x18000da2b  mov     rax, [rbx+0A0h]
0x18000da32  xor     edx, edx; bManualReset
0x18000da34  mov     [rcx+8], rax
0x18000da38  xor     ecx, ecx; lpEventAttributes
0x18000da3a  call    cs:__imp_CreateEventA
0x18000da40  mov     rcx, [rbx+0B0h]
0x18000da47  mov     [rcx+10h], rax
0x18000da4b  mov     r9, [rbx+0B0h]; Context
0x18000da52  mov     rdx, [r9+10h]; hObject
0x18000da56  test    rdx, rdx
0x18000da59  jnz     short loc_18000DAAE
0x18000da5b  mov     rcx, r9; void *
0x18000da5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000da63  mov     qword ptr [rbx+0B0h], 0
0x18000da6e  mov     rax, cs:WPP_GLOBAL_Control
0x18000da75  cmp     rax, rbp
0x18000da78  jz      loc_18000DBD1
0x18000da7e  test    byte ptr [rax+1Ch], 1
0x18000da82  jz      loc_18000DBD1
0x18000da88  call    cs:__imp_GetLastError
0x18000da8e  mov     edx, 2Eh ; '.'
0x18000da93  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da9a  mov     r9d, eax
0x18000da9d  mov     r8, r15
0x18000daa0  mov     rcx, [rcx+10h]
0x18000daa4  call    WPP_SF_d
0x18000daa9  jmp     loc_18000DBD1
0x18000daae  lea     rcx, [r9+18h]; phNewWaitObject
0x18000dab2  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000daba  lea     r8, ?SsdpNetProc@@YAXPEAXE@Z; Callback
0x18000dac1  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000dac9  call    cs:__imp_RegisterWaitForSingleObject
0x18000dacf  mov     rcx, [rbx+0B0h]
0x18000dad6  test    eax, eax
0x18000dad8  jnz     short loc_18000DB25
0x18000dada  mov     rcx, [rcx+10h]; hObject
0x18000dade  call    cs:__imp_CloseHandle
0x18000dae4  mov     rcx, [rbx+0B0h]; void *
0x18000daeb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000daf0  mov     qword ptr [rbx+0B0h], 0
0x18000dafb  mov     rax, cs:WPP_GLOBAL_Control
0x18000db02  cmp     rax, rbp
0x18000db05  jz      loc_18000DBD1
0x18000db0b  test    byte ptr [rax+1Ch], 1
0x18000db0f  jz      loc_18000DBD1
0x18000db15  call    cs:__imp_GetLastError
0x18000db1b  mov     edx, 2Fh ; '/'
0x18000db20  jmp     loc_18000DA93
0x18000db25  mov     rdx, [rcx+10h]; hEventObject
0x18000db29  mov     r8d, 1; lNetworkEvents
0x18000db2f  mov     rcx, [rcx+8]; s
0x18000db33  call    cs:__imp_WSAEventSelect
0x18000db39  cmp     eax, 0FFFFFFFFh
0x18000db3c  jnz     short loc_18000DB9D
0x18000db3e  mov     rcx, [rbx+0B0h]
0x18000db45  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000db49  mov     rcx, [rcx+18h]; WaitHandle
0x18000db4d  call    cs:__imp_UnregisterWaitEx
0x18000db53  mov     rcx, [rbx+0B0h]
0x18000db5a  mov     rcx, [rcx+10h]; hObject
0x18000db5e  call    cs:__imp_CloseHandle
0x18000db64  mov     rcx, [rbx+0B0h]; void *
0x18000db6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000db70  mov     qword ptr [rbx+0B0h], 0
0x18000db7b  mov     rax, cs:WPP_GLOBAL_Control
0x18000db82  cmp     rax, rbp
0x18000db85  jz      short loc_18000DBD1
0x18000db87  test    byte ptr [rax+1Ch], 1
0x18000db8b  jz      short loc_18000DBD1
0x18000db8d  call    cs:__imp_GetLastError
0x18000db93  mov     edx, 30h ; '0'
0x18000db98  jmp     loc_18000DA93
0x18000db9d  mov     edi, 1
0x18000dba2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dba9  cmp     rcx, rbp
0x18000dbac  jz      short loc_18000DBD1
0x18000dbae  test    dword ptr [rcx+1Ch], 200h
0x18000dbb5  jz      short loc_18000DBD1
0x18000dbb7  mov     eax, [rbx+0A0h]
0x18000dbbd  mov     r9, [rbx+0B0h]
0x18000dbc4  mov     rcx, [rcx+10h]
0x18000dbc8  mov     [rsp+58h+dwMilliseconds], eax
0x18000dbcc  call    WPP_SF_qD
0x18000dbd1  mov     rbx, [rbx]
0x18000dbd4  cmp     rbx, r13
0x18000dbd7  jnz     loc_18000D9F0
0x18000dbdd  lea     rcx, stru_180042200; lpCriticalSection
0x18000dbe4  call    cs:__imp_LeaveCriticalSection
0x18000dbea  test    edi, edi
0x18000dbec  jz      short loc_18000DC18
0x18000dbee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbf5  cmp     rcx, rbp
0x18000dbf8  jz      short loc_18000DC14
0x18000dbfa  test    dword ptr [rcx+1Ch], 200h
0x18000dc01  jz      short loc_18000DC14
0x18000dc03  mov     rcx, [rcx+10h]
0x18000dc07  mov     edx, 32h ; '2'
0x18000dc0c  mov     r8, r15
0x18000dc0f  call    WPP_SF_
0x18000dc14  xor     eax, eax
0x18000dc16  jmp     short loc_18000DC41
0x18000dc18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc1f  cmp     rcx, rbp
0x18000dc22  jz      short loc_18000DC3B
0x18000dc24  test    byte ptr [rcx+1Ch], 1
0x18000dc28  jz      short loc_18000DC3B
0x18000dc2a  mov     rcx, [rcx+10h]
0x18000dc2e  mov     edx, 33h ; '3'
0x18000dc33  mov     r8, r15
0x18000dc36  call    WPP_SF_
0x18000dc3b  call    cs:__imp_GetLastError
0x18000dc41  add     rsp, 30h
0x18000dc45  pop     r15
0x18000dc47  pop     r13
0x18000dc49  pop     rdi
0x18000dc4a  pop     rbp
0x18000dc4b  pop     rbx
0x18000dc4c  retn
```
