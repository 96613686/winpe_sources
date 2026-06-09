# CSsdpNotifyRequestManager::HrCreateWinHttpSession(void)

- ea: `0x1800231f4`
- end: `0x180023360`
- name: `?HrCreateWinHttpSession@CSsdpNotifyRequestManager@@AEAAJXZ`
- size: `364`
- prototype: `__int64 __fastcall(CSsdpNotifyRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001af78`

## callees

- `0x18000683c`
- `0x1800231f4`
- `0x1800271fc`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023341`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023341`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002320c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002320c`
- `WINHTTP!WinHttpOpen` at `0x18002323d`
- `WINHTTP!WinHttpOpen` at `0x18002323d`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800232f7`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800232f7`
- `WINHTTP!WinHttpSetTimeouts` at `0x18002329e`
- `WINHTTP!WinHttpSetTimeouts` at `0x18002329e`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequestManager::HrCreateWinHttpSession(CSsdpNotifyRequestManager *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  int Win32Error; // ebx
  void *v3; // rax

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  Win32Error = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( !g_hInetSess )
  {
    v3 = WinHttpOpen(pszAgentW, 1u, 0, 0, 0x10000000u);
    g_hInetSess = v3;
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
        v3 = g_hInetSess;
      }
      if ( WinHttpSetTimeouts(v3, 30000, 30000, 30000, 30000) || (Win32Error = HrFromLastWin32Error(), Win32Error >= 0) )
      {
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
        if ( WinHttpSetStatusCallback(g_hInetSess, CSsdpNotifyRequest::AsynchronousWinHTTPCallback, 0x97E0C00u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
          Win32Error = HrFromLastWin32Error();
      }
      if ( Win32Error && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          113,
          WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
          (unsigned int)Win32Error);
    }
  }
  LeaveCriticalSection(v1);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800231f4  mov     [rsp+arg_0], rbx
0x1800231f9  mov     [rsp+arg_8], rsi
0x1800231fe  push    rdi
0x1800231ff  sub     rsp, 30h
0x180023203  lea     rdi, [rcx+60h]
0x180023207  xor     ebx, ebx
0x180023209  mov     rcx, rdi; lpCriticalSection
0x18002320c  call    cs:__imp_EnterCriticalSection
0x180023213  nop     dword ptr [rax+rax+00h]
0x180023218  cmp     cs:?g_hInetSess@@3PEAXEA, rbx; void * g_hInetSess
0x18002321f  jnz     loc_18002333E
0x180023225  xor     r9d, r9d; pszProxyBypassW
0x180023228  mov     [rsp+38h+dwFlags], 10000000h; dwFlags
0x180023230  xor     r8d, r8d; pszProxyW
0x180023233  lea     edx, [rbx+1]; dwAccessType
0x180023236  lea     rcx, pszAgentW; "Microsoft-Windows/10.0 UPnP/1.0"
0x18002323d  call    cs:__imp_WinHttpOpen
0x180023244  nop     dword ptr [rax+rax+00h]
0x180023249  mov     cs:?g_hInetSess@@3PEAXEA, rax; void * g_hInetSess
0x180023250  test    rax, rax
0x180023253  jz      loc_18002333E
0x180023259  mov     rcx, cs:WPP_GLOBAL_Control
0x180023260  lea     rsi, WPP_GLOBAL_Control
0x180023267  cmp     rcx, rsi
0x18002326a  jz      short loc_18002328C
0x18002326c  test    byte ptr [rcx+1Ch], 8
0x180023270  jz      short loc_18002328C
0x180023272  mov     rcx, [rcx+10h]
0x180023276  lea     edx, [rbx+6Fh]
0x180023279  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180023280  call    WPP_SF_
0x180023285  mov     rax, cs:?g_hInetSess@@3PEAXEA; void * g_hInetSess
0x18002328c  mov     edx, 7530h; nResolveTimeout
0x180023291  mov     rcx, rax; hInternet
0x180023294  mov     r9d, edx; nSendTimeout
0x180023297  mov     [rsp+38h+dwFlags], edx; nReceiveTimeout
0x18002329b  mov     r8d, edx; nConnectTimeout
0x18002329e  call    cs:__imp_WinHttpSetTimeouts
0x1800232a5  nop     dword ptr [rax+rax+00h]
0x1800232aa  test    eax, eax
0x1800232ac  jnz     short loc_1800232B9
0x1800232ae  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800232b3  mov     ebx, eax
0x1800232b5  test    eax, eax
0x1800232b7  js      short loc_180023310
0x1800232b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232c0  cmp     rcx, rsi
0x1800232c3  jz      short loc_1800232E0
0x1800232c5  test    byte ptr [rcx+1Ch], 8
0x1800232c9  jz      short loc_1800232E0
0x1800232cb  mov     rcx, [rcx+10h]
0x1800232cf  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x1800232d6  mov     edx, 70h ; 'p'
0x1800232db  call    WPP_SF_
0x1800232e0  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hInternet
0x1800232e7  lea     rdx, ?AsynchronousWinHTTPCallback@CSsdpNotifyRequest@@SAXPEAX_KK0K@Z; lpfnInternetCallback
0x1800232ee  xor     r9d, r9d; dwReserved
0x1800232f1  mov     r8d, 97E0C00h; dwNotificationFlags
0x1800232f7  call    cs:__imp_WinHttpSetStatusCallback
0x1800232fe  nop     dword ptr [rax+rax+00h]
0x180023303  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023307  jnz     short loc_180023310
0x180023309  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18002330e  mov     ebx, eax
0x180023310  test    ebx, ebx
0x180023312  jz      short loc_18002333E
0x180023314  mov     rcx, cs:WPP_GLOBAL_Control
0x18002331b  cmp     rcx, rsi
0x18002331e  jz      short loc_18002333E
0x180023320  test    byte ptr [rcx+1Ch], 1
0x180023324  jz      short loc_18002333E
0x180023326  mov     rcx, [rcx+10h]
0x18002332a  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180023331  mov     edx, 71h ; 'q'
0x180023336  mov     r9d, ebx
0x180023339  call    WPP_SF_d
0x18002333e  mov     rcx, rdi; lpCriticalSection
0x180023341  call    cs:__imp_LeaveCriticalSection
0x180023348  nop     dword ptr [rax+rax+00h]
0x18002334d  mov     rsi, [rsp+38h+arg_8]
0x180023352  mov     eax, ebx
0x180023354  mov     rbx, [rsp+38h+arg_0]
0x180023359  add     rsp, 30h
0x18002335d  pop     rdi
0x18002335e  retn
```
