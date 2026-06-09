# CSsdpSearchRequestManager::HrInitialize(void)

- ea: `0x18000babc`
- end: `0x18000bc2f`
- name: `?HrInitialize@CSsdpSearchRequestManager@@QEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(char *lpCriticalSection)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000a768`

## callees

- `0x18000554c`
- `0x18000babc`
- `0x18000c158`
- `0x18000c340`
- `0x18000d09c`
- `0x1800246e4`
- `0x1800255a8`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bc1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bc1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bafb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bafb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb2f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000bb6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000bbde`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000bb6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000bbde`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000bbb4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000bbb4`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequestManager::HrInitialize(char *lpCriticalSection)
{
  signed int Win32Error; // edi
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
      Thread = CreateThread(
                 0,
                 0,
                 (LPTHREAD_START_ROUTINE)CSsdpSearchRequestManager::DwSearchThreadProc,
                 0,
                 0,
                 (LPDWORD)lpCriticalSection + 14);
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
0x18000babc  push    rbx
0x18000babe  push    rbp
0x18000babf  push    rsi
0x18000bac0  push    rdi
0x18000bac1  push    r12
0x18000bac3  sub     rsp, 30h
0x18000bac7  mov     rbx, rcx
0x18000baca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bad1  lea     r12, WPP_GLOBAL_Control
0x18000bad8  cmp     rcx, r12
0x18000badb  jz      short loc_18000BAF8
0x18000badd  test    byte ptr [rcx+1Ch], 8
0x18000bae1  jz      short loc_18000BAF8
0x18000bae3  mov     rcx, [rcx+10h]
0x18000bae7  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18000baee  mov     edx, 20h ; ' '
0x18000baf3  call    WPP_SF_
0x18000baf8  mov     rcx, rbx; lpCriticalSection
0x18000bafb  call    cs:__imp_EnterCriticalSection
0x18000bb01  mov     qword ptr [rbx+2A8h], 0
0x18000bb0c  lea     rcx, [rbx+28h]
0x18000bb10  mov     qword ptr [rbx+30h], 0
0x18000bb18  mov     dword ptr [rbx+2A0h], 1
0x18000bb22  call    ?Clear@?$CUList@VCSsdpSearchRequest@@@@QEAAXXZ; CUList<CSsdpSearchRequest>::Clear(void)
0x18000bb27  lea     rsi, [rbx+40h]
0x18000bb2b  lea     rcx, [rsi+8]; lpCriticalSection
0x18000bb2f  call    cs:__imp_EnterCriticalSection
0x18000bb35  mov     rcx, rsi; this
0x18000bb38  call    ?Clear@CSsdpSearchSocketManager@@AEAAXXZ; CSsdpSearchSocketManager::Clear(void)
0x18000bb3d  mov     rcx, rsi; this
0x18000bb40  call    ?ClearOld@CSsdpSearchSocketManager@@AEAAXXZ; CSsdpSearchSocketManager::ClearOld(void)
0x18000bb45  mov     rcx, rsi; this
0x18000bb48  call    ?HrBuildSocketList@CSsdpSearchSocketManager@@AEAAJXZ; CSsdpSearchSocketManager::HrBuildSocketList(void)
0x18000bb4d  mov     edi, eax
0x18000bb4f  test    eax, eax
0x18000bb51  js      short loc_18000BB56
0x18000bb53  lock inc dword ptr [rsi]
0x18000bb56  lea     rcx, [rsi+8]; lpCriticalSection
0x18000bb5a  call    cs:__imp_LeaveCriticalSection
0x18000bb60  test    edi, edi
0x18000bb62  js      short loc_18000BBD4
0x18000bb64  xor     r9d, r9d; lpName
0x18000bb67  xor     r8d, r8d; bInitialState
0x18000bb6a  xor     edx, edx; bManualReset
0x18000bb6c  xor     ecx, ecx; lpEventAttributes
0x18000bb6e  call    cs:__imp_CreateEventA
0x18000bb74  mov     [rbx+2A8h], rax
0x18000bb7b  test    rax, rax
0x18000bb7e  jnz     short loc_18000BB8B
0x18000bb80  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000bb85  mov     edi, eax
0x18000bb87  test    eax, eax
0x18000bb89  js      short loc_18000BBD4
0x18000bb8b  lea     rax, [rbx+38h]
0x18000bb8f  mov     dword ptr [rbx+2A0h], 0
0x18000bb99  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18000bb9e  lea     r8, ?DwSearchThreadProc@CSsdpSearchRequestManager@@CAKPEAX@Z; lpStartAddress
0x18000bba5  xor     r9d, r9d; lpParameter
0x18000bba8  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18000bbb0  xor     edx, edx; dwStackSize
0x18000bbb2  xor     ecx, ecx; lpThreadAttributes
0x18000bbb4  call    cs:__imp_CreateThread
0x18000bbba  mov     [rbx+30h], rax
0x18000bbbe  test    rax, rax
0x18000bbc1  jnz     short loc_18000BBD4
0x18000bbc3  mov     dword ptr [rbx+2A0h], 1
0x18000bbcd  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000bbd2  mov     edi, eax
0x18000bbd4  xor     r9d, r9d; lpName
0x18000bbd7  xor     r8d, r8d; bInitialState
0x18000bbda  xor     edx, edx; bManualReset
0x18000bbdc  xor     ecx, ecx; lpEventAttributes
0x18000bbde  call    cs:__imp_CreateEventA
0x18000bbe4  mov     [rbx+2E8h], rax
0x18000bbeb  test    edi, edi
0x18000bbed  jz      short loc_18000BC19
0x18000bbef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbf6  cmp     rcx, r12
0x18000bbf9  jz      short loc_18000BC19
0x18000bbfb  test    byte ptr [rcx+1Ch], 1
0x18000bbff  jz      short loc_18000BC19
0x18000bc01  mov     rcx, [rcx+10h]
0x18000bc05  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18000bc0c  mov     edx, 21h ; '!'
0x18000bc11  mov     r9d, edi
0x18000bc14  call    WPP_SF_d
0x18000bc19  mov     rcx, rbx; lpCriticalSection
0x18000bc1c  call    cs:__imp_LeaveCriticalSection
0x18000bc22  mov     eax, edi
0x18000bc24  add     rsp, 30h
0x18000bc28  pop     r12
0x18000bc2a  pop     rdi
0x18000bc2b  pop     rsi
0x18000bc2c  pop     rbp
0x18000bc2d  pop     rbx
0x18000bc2e  retn
```
