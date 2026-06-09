# CSsdpNotifyRequestManager::HrCreateWinHttpSession(void)

- ea: `0x180021ab0`
- end: `0x180021bfd`
- name: `?HrCreateWinHttpSession@CSsdpNotifyRequestManager@@AEAAJXZ`
- size: `333`
- prototype: `__int64 __fastcall(CSsdpNotifyRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180019ce4`

## callees

- `0x18000554c`
- `0x180021ab0`
- `0x1800255a8`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021be5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021be5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021ac8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021ac8`
- `WINHTTP!WinHttpOpen` at `0x180021af3`
- `WINHTTP!WinHttpOpen` at `0x180021af3`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180021ba1`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180021ba1`
- `WINHTTP!WinHttpSetTimeouts` at `0x180021b4e`
- `WINHTTP!WinHttpSetTimeouts` at `0x180021b4e`

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
        if ( WinHttpSetStatusCallback(
               g_hInetSess,
               (WINHTTP_STATUS_CALLBACK)CSsdpNotifyRequest::AsynchronousWinHTTPCallback,
               0x97E0C00u,
               0) == (WINHTTP_STATUS_CALLBACK)-1LL )
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
0x180021ab0  mov     [rsp+arg_0], rbx
0x180021ab5  mov     [rsp+arg_8], rsi
0x180021aba  push    rdi
0x180021abb  sub     rsp, 30h
0x180021abf  lea     rdi, [rcx+60h]
0x180021ac3  xor     ebx, ebx
0x180021ac5  mov     rcx, rdi; lpCriticalSection
0x180021ac8  call    cs:__imp_EnterCriticalSection
0x180021ace  cmp     cs:?g_hInetSess@@3PEAXEA, rbx; void * g_hInetSess
0x180021ad5  jnz     loc_180021BE2
0x180021adb  xor     r9d, r9d; pszProxyBypassW
0x180021ade  mov     [rsp+38h+dwFlags], 10000000h; dwFlags
0x180021ae6  xor     r8d, r8d; pszProxyW
0x180021ae9  lea     edx, [rbx+1]; dwAccessType
0x180021aec  lea     rcx, pszAgentW; "Microsoft-Windows/10.0 UPnP/1.0"
0x180021af3  call    cs:__imp_WinHttpOpen
0x180021af9  mov     cs:?g_hInetSess@@3PEAXEA, rax; void * g_hInetSess
0x180021b00  test    rax, rax
0x180021b03  jz      loc_180021BE2
0x180021b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b10  lea     rsi, WPP_GLOBAL_Control
0x180021b17  cmp     rcx, rsi
0x180021b1a  jz      short loc_180021B3C
0x180021b1c  test    byte ptr [rcx+1Ch], 8
0x180021b20  jz      short loc_180021B3C
0x180021b22  mov     rcx, [rcx+10h]
0x180021b26  lea     edx, [rbx+6Fh]
0x180021b29  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180021b30  call    WPP_SF_
0x180021b35  mov     rax, cs:?g_hInetSess@@3PEAXEA; void * g_hInetSess
0x180021b3c  mov     edx, 7530h; nResolveTimeout
0x180021b41  mov     rcx, rax; hInternet
0x180021b44  mov     r9d, edx; nSendTimeout
0x180021b47  mov     [rsp+38h+dwFlags], edx; nReceiveTimeout
0x180021b4b  mov     r8d, edx; nConnectTimeout
0x180021b4e  call    cs:__imp_WinHttpSetTimeouts
0x180021b54  test    eax, eax
0x180021b56  jnz     short loc_180021B63
0x180021b58  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180021b5d  mov     ebx, eax
0x180021b5f  test    eax, eax
0x180021b61  js      short loc_180021BB4
0x180021b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b6a  cmp     rcx, rsi
0x180021b6d  jz      short loc_180021B8A
0x180021b6f  test    byte ptr [rcx+1Ch], 8
0x180021b73  jz      short loc_180021B8A
0x180021b75  mov     rcx, [rcx+10h]
0x180021b79  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180021b80  mov     edx, 70h ; 'p'
0x180021b85  call    WPP_SF_
0x180021b8a  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hInternet
0x180021b91  lea     rdx, ?AsynchronousWinHTTPCallback@CSsdpNotifyRequest@@SAXPEAX_KK0K@Z; lpfnInternetCallback
0x180021b98  xor     r9d, r9d; dwReserved
0x180021b9b  mov     r8d, 97E0C00h; dwNotificationFlags
0x180021ba1  call    cs:__imp_WinHttpSetStatusCallback
0x180021ba7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021bab  jnz     short loc_180021BB4
0x180021bad  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180021bb2  mov     ebx, eax
0x180021bb4  test    ebx, ebx
0x180021bb6  jz      short loc_180021BE2
0x180021bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bbf  cmp     rcx, rsi
0x180021bc2  jz      short loc_180021BE2
0x180021bc4  test    byte ptr [rcx+1Ch], 1
0x180021bc8  jz      short loc_180021BE2
0x180021bca  mov     rcx, [rcx+10h]
0x180021bce  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180021bd5  mov     edx, 71h ; 'q'
0x180021bda  mov     r9d, ebx
0x180021bdd  call    WPP_SF_d
0x180021be2  mov     rcx, rdi; lpCriticalSection
0x180021be5  call    cs:__imp_LeaveCriticalSection
0x180021beb  mov     rsi, [rsp+38h+arg_8]
0x180021bf0  mov     eax, ebx
0x180021bf2  mov     rbx, [rsp+38h+arg_0]
0x180021bf7  add     rsp, 30h
0x180021bfb  pop     rdi
0x180021bfc  retn
```
