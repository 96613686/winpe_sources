# CSsdpSearchRequestManager::HrInitialize(void)

- ea: `0x18000d550`
- end: `0x18000d6ee`
- name: `?HrInitialize@CSsdpSearchRequestManager@@QEAAJXZ`
- size: `414`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000c078`

## callees

- `0x18000683c`
- `0x18000d550`
- `0x18000dc84`
- `0x18000e3bc`
- `0x180013efc`
- `0x1800261e4`
- `0x1800271fc`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d5fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d6d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d5fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d6d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d58f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d58f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000d614`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000d690`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000d614`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000d690`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d660`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d660`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequestManager::HrInitialize(char *lpCriticalSection)
{
  int Win32Error; // edi
  struct _RTL_CRITICAL_SECTION_DEBUG *EventA; // rax
  HANDLE Thread; // rax

  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  *((_QWORD *)lpCriticalSection + 85) = 0;
  *((_QWORD *)lpCriticalSection + 6) = 0;
  *((_DWORD *)lpCriticalSection + 168) = 1;
  CUList<CSsdpSearchRequest>::Clear(lpCriticalSection + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 72));
  CSsdpSearchSocketManager::Clear((CSsdpSearchSocketManager *)(lpCriticalSection + 64));
  CSsdpSearchSocketManager::ClearOld((CSsdpSearchSocketManager *)(lpCriticalSection + 64));
  Win32Error = CSsdpSearchSocketManager::HrBuildSocketList((CSsdpSearchSocketManager *)(lpCriticalSection + 64));
  if ( Win32Error >= 0 )
    _InterlockedIncrement((volatile signed __int32 *)lpCriticalSection + 16);
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 72));
  if ( Win32Error >= 0 )
  {
    EventA = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventA(0, 0, 0, 0);
    *((_QWORD *)lpCriticalSection + 85) = EventA;
    if ( EventA || (Win32Error = HrFromLastWin32Error(), Win32Error >= 0) )
    {
      *((_DWORD *)lpCriticalSection + 168) = 0;
      Thread = CreateThread(0, 0, CSsdpSearchRequestManager::DwSearchThreadProc, 0, 0, (LPDWORD)lpCriticalSection + 14);
      *((_QWORD *)lpCriticalSection + 6) = Thread;
      if ( !Thread )
      {
        *((_DWORD *)lpCriticalSection + 168) = 1;
        Win32Error = HrFromLastWin32Error();
      }
    }
  }
  *((_QWORD *)lpCriticalSection + 93) = CreateEventA(0, 0, 0, 0);
  if ( Win32Error && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
      (unsigned int)Win32Error);
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x18000d550  push    rbx
0x18000d552  push    rbp
0x18000d553  push    rsi
0x18000d554  push    rdi
0x18000d555  push    r12
0x18000d557  sub     rsp, 30h
0x18000d55b  mov     rbx, rcx
0x18000d55e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d565  lea     r12, WPP_GLOBAL_Control
0x18000d56c  cmp     rcx, r12
0x18000d56f  jz      short loc_18000D58C
0x18000d571  test    byte ptr [rcx+1Ch], 8
0x18000d575  jz      short loc_18000D58C
0x18000d577  mov     rcx, [rcx+10h]
0x18000d57b  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18000d582  mov     edx, 20h ; ' '
0x18000d587  call    WPP_SF_
0x18000d58c  mov     rcx, rbx; lpCriticalSection
0x18000d58f  call    cs:__imp_EnterCriticalSection
0x18000d596  nop     dword ptr [rax+rax+00h]
0x18000d59b  mov     qword ptr [rbx+2A8h], 0
0x18000d5a6  lea     rcx, [rbx+28h]
0x18000d5aa  mov     qword ptr [rbx+30h], 0
0x18000d5b2  mov     dword ptr [rbx+2A0h], 1
0x18000d5bc  call    ?Clear@?$CUList@VCSsdpSearchRequest@@@@QEAAXXZ; CUList<CSsdpSearchRequest>::Clear(void)
0x18000d5c1  lea     rsi, [rbx+40h]
0x18000d5c5  lea     rcx, [rsi+8]; lpCriticalSection
0x18000d5c9  call    cs:__imp_EnterCriticalSection
0x18000d5d0  nop     dword ptr [rax+rax+00h]
0x18000d5d5  mov     rcx, rsi; this
0x18000d5d8  call    ?Clear@CSsdpSearchSocketManager@@AEAAXXZ; CSsdpSearchSocketManager::Clear(void)
0x18000d5dd  mov     rcx, rsi; this
0x18000d5e0  call    ?ClearOld@CSsdpSearchSocketManager@@AEAAXXZ; CSsdpSearchSocketManager::ClearOld(void)
0x18000d5e5  mov     rcx, rsi; this
0x18000d5e8  call    ?HrBuildSocketList@CSsdpSearchSocketManager@@AEAAJXZ; CSsdpSearchSocketManager::HrBuildSocketList(void)
0x18000d5ed  mov     edi, eax
0x18000d5ef  test    eax, eax
0x18000d5f1  js      short loc_18000D5F6
0x18000d5f3  lock inc dword ptr [rsi]
0x18000d5f6  lea     rcx, [rsi+8]; lpCriticalSection
0x18000d5fa  call    cs:__imp_LeaveCriticalSection
0x18000d601  nop     dword ptr [rax+rax+00h]
0x18000d606  test    edi, edi
0x18000d608  js      short loc_18000D686
0x18000d60a  xor     r9d, r9d; lpName
0x18000d60d  xor     r8d, r8d; bInitialState
0x18000d610  xor     edx, edx; bManualReset
0x18000d612  xor     ecx, ecx; lpEventAttributes
0x18000d614  call    cs:__imp_CreateEventA
0x18000d61b  nop     dword ptr [rax+rax+00h]
0x18000d620  mov     [rbx+2A8h], rax
0x18000d627  test    rax, rax
0x18000d62a  jnz     short loc_18000D637
0x18000d62c  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000d631  mov     edi, eax
0x18000d633  test    eax, eax
0x18000d635  js      short loc_18000D686
0x18000d637  lea     rax, [rbx+38h]
0x18000d63b  mov     dword ptr [rbx+2A0h], 0
0x18000d645  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18000d64a  lea     r8, ?DwSearchThreadProc@CSsdpSearchRequestManager@@CAKPEAX@Z; lpStartAddress
0x18000d651  xor     r9d, r9d; lpParameter
0x18000d654  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18000d65c  xor     edx, edx; dwStackSize
0x18000d65e  xor     ecx, ecx; lpThreadAttributes
0x18000d660  call    cs:__imp_CreateThread
0x18000d667  nop     dword ptr [rax+rax+00h]
0x18000d66c  mov     [rbx+30h], rax
0x18000d670  test    rax, rax
0x18000d673  jnz     short loc_18000D686
0x18000d675  mov     dword ptr [rbx+2A0h], 1
0x18000d67f  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000d684  mov     edi, eax
0x18000d686  xor     r9d, r9d; lpName
0x18000d689  xor     r8d, r8d; bInitialState
0x18000d68c  xor     edx, edx; bManualReset
0x18000d68e  xor     ecx, ecx; lpEventAttributes
0x18000d690  call    cs:__imp_CreateEventA
0x18000d697  nop     dword ptr [rax+rax+00h]
0x18000d69c  mov     [rbx+2E8h], rax
0x18000d6a3  test    edi, edi
0x18000d6a5  jz      short loc_18000D6D1
0x18000d6a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6ae  cmp     rcx, r12
0x18000d6b1  jz      short loc_18000D6D1
0x18000d6b3  test    byte ptr [rcx+1Ch], 1
0x18000d6b7  jz      short loc_18000D6D1
0x18000d6b9  mov     rcx, [rcx+10h]
0x18000d6bd  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18000d6c4  mov     edx, 21h ; '!'
0x18000d6c9  mov     r9d, edi
0x18000d6cc  call    WPP_SF_d
0x18000d6d1  mov     rcx, rbx; lpCriticalSection
0x18000d6d4  call    cs:__imp_LeaveCriticalSection
0x18000d6db  nop     dword ptr [rax+rax+00h]
0x18000d6e0  mov     eax, edi
0x18000d6e2  add     rsp, 30h
0x18000d6e6  pop     r12
0x18000d6e8  pop     rdi
0x18000d6e9  pop     rsi
0x18000d6ea  pop     rbp
0x18000d6eb  pop     rbx
0x18000d6ec  retn
```
