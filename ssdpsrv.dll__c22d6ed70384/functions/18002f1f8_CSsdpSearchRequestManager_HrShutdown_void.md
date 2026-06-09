# CSsdpSearchRequestManager::HrShutdown(void)

- ea: `0x18002f1f8`
- end: `0x18002f465`
- name: `?HrShutdown@CSsdpSearchRequestManager@@QEAAJXZ`
- size: `621`
- prototype: `__int64 __fastcall(char *lpCriticalSection)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002d870`

## callees

- `0x18000c158`
- `0x18000c698`
- `0x1800186a0`
- `0x18001959c`
- `0x180019bac`
- `0x180022a80`
- `0x180023934`
- `0x1800255a8`
- `0x180028000`
- `0x18002f1f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f2ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f3ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f2ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f3ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f2f4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f3bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f2f4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f3bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f23f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f392`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f23f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f392`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f303`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f3d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f303`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f3d0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18002f2cb`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18002f2cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f356`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f356`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3eb`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequestManager::HrShutdown(char *lpCriticalSection)
{
  unsigned int v2; // ebp
  void *v3; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v4; // rcx
  LPCSTR v5; // rcx
  __int64 v6; // rdx
  PRTL_CRITICAL_SECTION_DEBUG v7; // rcx
  HANDLE v8; // rsi
  HANDLE v9; // rcx
  HANDLE v10; // rcx
  LPCSTR v11; // rcx
  void *ExitCode; // [rsp+50h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  *((_DWORD *)lpCriticalSection + 168) = 1;
  v14 = (struct _RTL_CRITICAL_SECTION *)(lpCriticalSection + 40);
  if ( *((_QWORD *)lpCriticalSection + 5) )
  {
    ExitCode = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&v14, &ExitCode) )
        break;
      CSsdpRundownSupport::RemoveRundownItem(&CSsdpRundownSupport::s_instance, ExitCode);
      v2 = CSsdpSearchRequest::HrShutdown((CSsdpSearchRequest *)ExitCode);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v14) );
  }
  CUList<CSsdpSearchRequest>::Clear(lpCriticalSection + 40);
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  v3 = (void *)*((_QWORD *)lpCriticalSection + 6);
  if ( v3 )
  {
    LODWORD(ExitCode) = 0;
    if ( GetExitCodeThread(v3, (LPDWORD)&ExitCode) )
    {
      if ( (_DWORD)ExitCode != 259 )
        goto LABEL_21;
      CSsdpSearchSocketManager::WakeupSelect((CSsdpSearchSocketManager *)(lpCriticalSection + 64));
      v4 = (PRTL_CRITICAL_SECTION_DEBUG)*((_QWORD *)lpCriticalSection + 85);
      if ( v4 )
        SetEvent(v4);
      if ( WaitForSingleObject(*((HANDLE *)lpCriticalSection + 6), 0xEE48u) != 258 )
        goto LABEL_21;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_21;
      v6 = 35;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_21;
      v6 = 37;
    }
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, 2147549183LL);
LABEL_21:
    CloseHandle(*((HANDLE *)lpCriticalSection + 6));
    *((_QWORD *)lpCriticalSection + 6) = 0;
    *((_DWORD *)lpCriticalSection + 14) = 0;
  }
  v7 = (PRTL_CRITICAL_SECTION_DEBUG)*((_QWORD *)lpCriticalSection + 85);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)lpCriticalSection + 85) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 688));
  v8 = (HANDLE)*((_QWORD *)lpCriticalSection + 92);
  *((_QWORD *)lpCriticalSection + 92) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 688));
  v9 = (HANDLE)*((_QWORD *)lpCriticalSection + 93);
  if ( v9 )
    SetEvent(v9);
  if ( v8 )
  {
    WaitForSingleObject(v8, 0xFFFFFFFF);
    CloseHandle(v8);
  }
  v10 = (HANDLE)*((_QWORD *)lpCriticalSection + 93);
  if ( v10 )
  {
    CloseHandle(v10);
    *((_QWORD *)lpCriticalSection + 93) = 0;
  }
  CSsdpSearchSocketManager::Shutdown((CSsdpSearchSocketManager *)(lpCriticalSection + 64));
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v2 && v11 != (LPCSTR)&WPP_GLOBAL_Control && (v11[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v11 + 2), 39, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18002f1f8  mov     [rsp+arg_10], rbx
0x18002f1fd  push    rbp
0x18002f1fe  push    rsi
0x18002f1ff  push    rdi
0x18002f200  push    r12
0x18002f202  push    r15
0x18002f204  sub     rsp, 20h
0x18002f208  mov     rdi, rcx
0x18002f20b  xor     ebp, ebp
0x18002f20d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f214  lea     r15, WPP_GLOBAL_Control
0x18002f21b  lea     r12, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18002f222  cmp     rcx, r15
0x18002f225  jz      short loc_18002F23C
0x18002f227  test    byte ptr [rcx+1Ch], 8
0x18002f22b  jz      short loc_18002F23C
0x18002f22d  mov     rcx, [rcx+10h]
0x18002f231  lea     edx, [rbp+22h]
0x18002f234  mov     r8, r12
0x18002f237  call    WPP_SF_
0x18002f23c  mov     rcx, rdi; lpCriticalSection
0x18002f23f  call    cs:__imp_EnterCriticalSection
0x18002f245  lea     rbx, [rdi+28h]
0x18002f249  mov     dword ptr [rdi+2A0h], 1
0x18002f253  mov     [rsp+48h+arg_8], rbx
0x18002f258  cmp     [rbx], rbp
0x18002f25b  jz      short loc_18002F2A0
0x18002f25d  mov     [rsp+48h+ExitCode], rbp
0x18002f262  lea     rdx, [rsp+48h+ExitCode]
0x18002f267  lea     rcx, [rsp+48h+arg_8]
0x18002f26c  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18002f271  test    eax, eax
0x18002f273  jnz     short loc_18002F2A0
0x18002f275  mov     rdx, [rsp+48h+ExitCode]; void *
0x18002f27a  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x18002f281  call    ?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z; CSsdpRundownSupport::RemoveRundownItem(void *)
0x18002f286  mov     rcx, [rsp+48h+ExitCode]; this
0x18002f28b  call    ?HrShutdown@CSsdpSearchRequest@@QEAAJXZ; CSsdpSearchRequest::HrShutdown(void)
0x18002f290  lea     rcx, [rsp+48h+arg_8]
0x18002f295  mov     ebp, eax
0x18002f297  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18002f29c  test    eax, eax
0x18002f29e  jz      short loc_18002F262
0x18002f2a0  mov     rcx, rbx
0x18002f2a3  call    ?Clear@?$CUList@VCSsdpSearchRequest@@@@QEAAXXZ; CUList<CSsdpSearchRequest>::Clear(void)
0x18002f2a8  mov     rcx, rdi; lpCriticalSection
0x18002f2ab  call    cs:__imp_LeaveCriticalSection
0x18002f2b1  mov     rcx, [rdi+30h]; hThread
0x18002f2b5  test    rcx, rcx
0x18002f2b8  jz      loc_18002F36B
0x18002f2be  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x18002f2c3  mov     dword ptr [rsp+48h+ExitCode], 0
0x18002f2cb  call    cs:__imp_GetExitCodeThread
0x18002f2d1  test    eax, eax
0x18002f2d3  jz      short loc_18002F329
0x18002f2d5  cmp     dword ptr [rsp+48h+ExitCode], 103h
0x18002f2dd  jnz     short loc_18002F352
0x18002f2df  lea     rcx, [rdi+40h]; this
0x18002f2e3  call    ?WakeupSelect@CSsdpSearchSocketManager@@QEAAXXZ; CSsdpSearchSocketManager::WakeupSelect(void)
0x18002f2e8  mov     rcx, [rdi+2A8h]; hEvent
0x18002f2ef  test    rcx, rcx
0x18002f2f2  jz      short loc_18002F2FA
0x18002f2f4  call    cs:__imp_SetEvent
0x18002f2fa  mov     rcx, [rdi+30h]; hHandle
0x18002f2fe  mov     edx, 0EE48h; dwMilliseconds
0x18002f303  call    cs:__imp_WaitForSingleObject
0x18002f309  cmp     eax, 102h
0x18002f30e  jnz     short loc_18002F352
0x18002f310  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f317  cmp     rcx, r15
0x18002f31a  jz      short loc_18002F352
0x18002f31c  test    byte ptr [rcx+1Ch], 1
0x18002f320  jz      short loc_18002F352
0x18002f322  mov     edx, 23h ; '#'
0x18002f327  jmp     short loc_18002F340
0x18002f329  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f330  cmp     rcx, r15
0x18002f333  jz      short loc_18002F352
0x18002f335  test    byte ptr [rcx+1Ch], 1
0x18002f339  jz      short loc_18002F352
0x18002f33b  mov     edx, 25h ; '%'
0x18002f340  mov     rcx, [rcx+10h]
0x18002f344  mov     r9d, 8000FFFFh
0x18002f34a  mov     r8, r12
0x18002f34d  call    WPP_SF_d
0x18002f352  mov     rcx, [rdi+30h]; hObject
0x18002f356  call    cs:__imp_CloseHandle
0x18002f35c  mov     qword ptr [rdi+30h], 0
0x18002f364  mov     dword ptr [rdi+38h], 0
0x18002f36b  mov     rcx, [rdi+2A8h]; hObject
0x18002f372  test    rcx, rcx
0x18002f375  jz      short loc_18002F388
0x18002f377  call    cs:__imp_CloseHandle
0x18002f37d  mov     qword ptr [rdi+2A8h], 0
0x18002f388  lea     rbx, [rdi+2B0h]
0x18002f38f  mov     rcx, rbx; lpCriticalSection
0x18002f392  call    cs:__imp_EnterCriticalSection
0x18002f398  mov     rsi, [rdi+2E0h]
0x18002f39f  mov     rcx, rbx; lpCriticalSection
0x18002f3a2  mov     qword ptr [rdi+2E0h], 0
0x18002f3ad  call    cs:__imp_LeaveCriticalSection
0x18002f3b3  mov     rcx, [rdi+2E8h]; hEvent
0x18002f3ba  test    rcx, rcx
0x18002f3bd  jz      short loc_18002F3C5
0x18002f3bf  call    cs:__imp_SetEvent
0x18002f3c5  test    rsi, rsi
0x18002f3c8  jz      short loc_18002F3DF
0x18002f3ca  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002f3cd  mov     rcx, rsi; hHandle
0x18002f3d0  call    cs:__imp_WaitForSingleObject
0x18002f3d6  mov     rcx, rsi; hObject
0x18002f3d9  call    cs:__imp_CloseHandle
0x18002f3df  mov     rcx, [rdi+2E8h]; hObject
0x18002f3e6  test    rcx, rcx
0x18002f3e9  jz      short loc_18002F3FC
0x18002f3eb  call    cs:__imp_CloseHandle
0x18002f3f1  mov     qword ptr [rdi+2E8h], 0
0x18002f3fc  lea     rcx, [rdi+40h]; this
0x18002f400  call    ?Shutdown@CSsdpSearchSocketManager@@QEAAXXZ; CSsdpSearchSocketManager::Shutdown(void)
0x18002f405  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f40c  cmp     rcx, r15
0x18002f40f  jz      short loc_18002F42F
0x18002f411  test    byte ptr [rcx+1Ch], 8
0x18002f415  jz      short loc_18002F42F
0x18002f417  mov     rcx, [rcx+10h]
0x18002f41b  mov     edx, 26h ; '&'
0x18002f420  mov     r8, r12
0x18002f423  call    WPP_SF_
0x18002f428  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f42f  test    ebp, ebp
0x18002f431  jz      short loc_18002F452
0x18002f433  cmp     rcx, r15
0x18002f436  jz      short loc_18002F452
0x18002f438  test    byte ptr [rcx+1Ch], 1
0x18002f43c  jz      short loc_18002F452
0x18002f43e  mov     rcx, [rcx+10h]
0x18002f442  mov     edx, 27h ; '''
0x18002f447  mov     r9d, ebp
0x18002f44a  mov     r8, r12
0x18002f44d  call    WPP_SF_d
0x18002f452  mov     rbx, [rsp+48h+arg_10]
0x18002f457  mov     eax, ebp
0x18002f459  add     rsp, 20h
0x18002f45d  pop     r15
0x18002f45f  pop     r12
0x18002f461  pop     rdi
0x18002f462  pop     rsi
0x18002f463  pop     rbp
0x18002f464  retn
```
