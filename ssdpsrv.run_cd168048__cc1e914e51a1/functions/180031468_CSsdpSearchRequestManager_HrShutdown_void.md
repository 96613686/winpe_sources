# CSsdpSearchRequestManager::HrShutdown(void)

- ea: `0x180031468`
- end: `0x180031724`
- name: `?HrShutdown@CSsdpSearchRequestManager@@QEAAJXZ`
- size: `700`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002f900`

## callees

- `0x18000dc84`
- `0x180014274`
- `0x180019920`
- `0x18001a7c8`
- `0x18001aeb4`
- `0x180024490`
- `0x18002534c`
- `0x1800271fc`
- `0x180029df0`
- `0x180031468`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031521`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003164d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031521`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003164d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031576`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031665`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031576`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031665`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800314af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003162c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800314af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003162c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003158b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003167c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003158b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003167c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180031547`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180031547`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800315e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003160b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003168b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800316a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800315e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003160b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003168b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800316a3`

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
  LPCRITICAL_SECTION v14; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  *((_DWORD *)lpCriticalSection + 168) = 1;
  v14 = (LPCRITICAL_SECTION)(lpCriticalSection + 40);
  if ( *((_QWORD *)lpCriticalSection + 5) )
  {
    ExitCode = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v14, &ExitCode) )
        break;
      CSsdpRundownSupport::RemoveRundownItem(&CSsdpRundownSupport::s_instance, ExitCode);
      v2 = CSsdpSearchRequest::HrShutdown((CSsdpSearchRequest *)ExitCode);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(&v14) );
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
0x180031468  mov     [rsp+arg_10], rbx
0x18003146d  push    rbp
0x18003146e  push    rsi
0x18003146f  push    rdi
0x180031470  push    r12
0x180031472  push    r15
0x180031474  sub     rsp, 20h
0x180031478  mov     rdi, rcx
0x18003147b  xor     ebp, ebp
0x18003147d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031484  lea     r15, WPP_GLOBAL_Control
0x18003148b  lea     r12, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x180031492  cmp     rcx, r15
0x180031495  jz      short loc_1800314AC
0x180031497  test    byte ptr [rcx+1Ch], 8
0x18003149b  jz      short loc_1800314AC
0x18003149d  mov     rcx, [rcx+10h]
0x1800314a1  lea     edx, [rbp+22h]
0x1800314a4  mov     r8, r12
0x1800314a7  call    WPP_SF_
0x1800314ac  mov     rcx, rdi; lpCriticalSection
0x1800314af  call    cs:__imp_EnterCriticalSection
0x1800314b6  nop     dword ptr [rax+rax+00h]
0x1800314bb  lea     rbx, [rdi+28h]
0x1800314bf  mov     dword ptr [rdi+2A0h], 1
0x1800314c9  mov     [rsp+48h+arg_8], rbx
0x1800314ce  cmp     [rbx], rbp
0x1800314d1  jz      short loc_180031516
0x1800314d3  mov     [rsp+48h+ExitCode], rbp
0x1800314d8  lea     rdx, [rsp+48h+ExitCode]
0x1800314dd  lea     rcx, [rsp+48h+arg_8]
0x1800314e2  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x1800314e7  test    eax, eax
0x1800314e9  jnz     short loc_180031516
0x1800314eb  mov     rdx, [rsp+48h+ExitCode]; void *
0x1800314f0  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x1800314f7  call    ?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z; CSsdpRundownSupport::RemoveRundownItem(void *)
0x1800314fc  mov     rcx, [rsp+48h+ExitCode]; this
0x180031501  call    ?HrShutdown@CSsdpSearchRequest@@QEAAJXZ; CSsdpSearchRequest::HrShutdown(void)
0x180031506  lea     rcx, [rsp+48h+arg_8]
0x18003150b  mov     ebp, eax
0x18003150d  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180031512  test    eax, eax
0x180031514  jz      short loc_1800314D8
0x180031516  mov     rcx, rbx
0x180031519  call    ?Clear@?$CUList@VCSsdpSearchRequest@@@@QEAAXXZ; CUList<CSsdpSearchRequest>::Clear(void)
0x18003151e  mov     rcx, rdi; lpCriticalSection
0x180031521  call    cs:__imp_LeaveCriticalSection
0x180031528  nop     dword ptr [rax+rax+00h]
0x18003152d  mov     rcx, [rdi+30h]; hThread
0x180031531  test    rcx, rcx
0x180031534  jz      loc_1800315FF
0x18003153a  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x18003153f  mov     dword ptr [rsp+48h+ExitCode], 0
0x180031547  call    cs:__imp_GetExitCodeThread
0x18003154e  nop     dword ptr [rax+rax+00h]
0x180031553  test    eax, eax
0x180031555  jz      short loc_1800315B7
0x180031557  cmp     dword ptr [rsp+48h+ExitCode], 103h
0x18003155f  jnz     short loc_1800315E0
0x180031561  lea     rcx, [rdi+40h]; this
0x180031565  call    ?WakeupSelect@CSsdpSearchSocketManager@@QEAAXXZ; CSsdpSearchSocketManager::WakeupSelect(void)
0x18003156a  mov     rcx, [rdi+2A8h]; hEvent
0x180031571  test    rcx, rcx
0x180031574  jz      short loc_180031582
0x180031576  call    cs:__imp_SetEvent
0x18003157d  nop     dword ptr [rax+rax+00h]
0x180031582  mov     rcx, [rdi+30h]; hHandle
0x180031586  mov     edx, 0EE48h; dwMilliseconds
0x18003158b  call    cs:__imp_WaitForSingleObject
0x180031592  nop     dword ptr [rax+rax+00h]
0x180031597  cmp     eax, 102h
0x18003159c  jnz     short loc_1800315E0
0x18003159e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800315a5  cmp     rcx, r15
0x1800315a8  jz      short loc_1800315E0
0x1800315aa  test    byte ptr [rcx+1Ch], 1
0x1800315ae  jz      short loc_1800315E0
0x1800315b0  mov     edx, 23h ; '#'
0x1800315b5  jmp     short loc_1800315CE
0x1800315b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800315be  cmp     rcx, r15
0x1800315c1  jz      short loc_1800315E0
0x1800315c3  test    byte ptr [rcx+1Ch], 1
0x1800315c7  jz      short loc_1800315E0
0x1800315c9  mov     edx, 25h ; '%'
0x1800315ce  mov     rcx, [rcx+10h]
0x1800315d2  mov     r9d, 8000FFFFh
0x1800315d8  mov     r8, r12
0x1800315db  call    WPP_SF_d
0x1800315e0  mov     rcx, [rdi+30h]; hObject
0x1800315e4  call    cs:__imp_CloseHandle
0x1800315eb  nop     dword ptr [rax+rax+00h]
0x1800315f0  mov     qword ptr [rdi+30h], 0
0x1800315f8  mov     dword ptr [rdi+38h], 0
0x1800315ff  mov     rcx, [rdi+2A8h]; hObject
0x180031606  test    rcx, rcx
0x180031609  jz      short loc_180031622
0x18003160b  call    cs:__imp_CloseHandle
0x180031612  nop     dword ptr [rax+rax+00h]
0x180031617  mov     qword ptr [rdi+2A8h], 0
0x180031622  lea     rbx, [rdi+2B0h]
0x180031629  mov     rcx, rbx; lpCriticalSection
0x18003162c  call    cs:__imp_EnterCriticalSection
0x180031633  nop     dword ptr [rax+rax+00h]
0x180031638  mov     rsi, [rdi+2E0h]
0x18003163f  mov     rcx, rbx; lpCriticalSection
0x180031642  mov     qword ptr [rdi+2E0h], 0
0x18003164d  call    cs:__imp_LeaveCriticalSection
0x180031654  nop     dword ptr [rax+rax+00h]
0x180031659  mov     rcx, [rdi+2E8h]; hEvent
0x180031660  test    rcx, rcx
0x180031663  jz      short loc_180031671
0x180031665  call    cs:__imp_SetEvent
0x18003166c  nop     dword ptr [rax+rax+00h]
0x180031671  test    rsi, rsi
0x180031674  jz      short loc_180031697
0x180031676  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180031679  mov     rcx, rsi; hHandle
0x18003167c  call    cs:__imp_WaitForSingleObject
0x180031683  nop     dword ptr [rax+rax+00h]
0x180031688  mov     rcx, rsi; hObject
0x18003168b  call    cs:__imp_CloseHandle
0x180031692  nop     dword ptr [rax+rax+00h]
0x180031697  mov     rcx, [rdi+2E8h]; hObject
0x18003169e  test    rcx, rcx
0x1800316a1  jz      short loc_1800316BA
0x1800316a3  call    cs:__imp_CloseHandle
0x1800316aa  nop     dword ptr [rax+rax+00h]
0x1800316af  mov     qword ptr [rdi+2E8h], 0
0x1800316ba  lea     rcx, [rdi+40h]; this
0x1800316be  call    ?Shutdown@CSsdpSearchSocketManager@@QEAAXXZ; CSsdpSearchSocketManager::Shutdown(void)
0x1800316c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316ca  cmp     rcx, r15
0x1800316cd  jz      short loc_1800316ED
0x1800316cf  test    byte ptr [rcx+1Ch], 8
0x1800316d3  jz      short loc_1800316ED
0x1800316d5  mov     rcx, [rcx+10h]
0x1800316d9  mov     edx, 26h ; '&'
0x1800316de  mov     r8, r12
0x1800316e1  call    WPP_SF_
0x1800316e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316ed  test    ebp, ebp
0x1800316ef  jz      short loc_180031710
0x1800316f1  cmp     rcx, r15
0x1800316f4  jz      short loc_180031710
0x1800316f6  test    byte ptr [rcx+1Ch], 1
0x1800316fa  jz      short loc_180031710
0x1800316fc  mov     rcx, [rcx+10h]
0x180031700  mov     edx, 27h ; '''
0x180031705  mov     r9d, ebp
0x180031708  mov     r8, r12
0x18003170b  call    WPP_SF_d
0x180031710  mov     rbx, [rsp+48h+arg_10]
0x180031715  mov     eax, ebp
0x180031717  add     rsp, 20h
0x18003171b  pop     r15
0x18003171d  pop     r12
0x18003171f  pop     rdi
0x180031720  pop     rsi
0x180031721  pop     rbp
0x180031722  retn
```
