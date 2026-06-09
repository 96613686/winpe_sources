# HrInitInternetSession(void)

- ea: `0x180045b04`
- end: `0x180045cd9`
- name: `?HrInitInternetSession@@YAJXZ`
- size: `469`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002643c`
- `0x180035094`

## callees

- `0x18000db4c`
- `0x18001347c`
- `0x180038ce4`
- `0x180045b04`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x180045b27`
- `WINHTTP!WinHttpOpen` at `0x180045b27`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180045c0b`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180045c0b`
- `WINHTTP!WinHttpSetTimeouts` at `0x180045b53`
- `WINHTTP!WinHttpSetTimeouts` at `0x180045b53`
- `WINHTTP!WinHttpCloseHandle` at `0x180045c38`
- `WINHTTP!WinHttpCloseHandle` at `0x180045c38`

## string_xrefs

- `0x180045c7e`: `HrInitInternetSession: InternetOpen`

## pseudocode

```c
__int64 HrInitInternetSession(void)
{
  void *v0; // rax
  int Win32Error; // ebx
  STRSAFE_PCNZWCH v2; // rcx
  char v3; // al
  bool v4; // zf
  int v5; // eax

  v0 = WinHttpOpen(pszAgentW, 1u, 0, 0, 0);
  g_hInetSess = v0;
  if ( v0 )
  {
    if ( WinHttpSetTimeouts(v0, 15000, 15000, 15000, 10000) )
    {
      Win32Error = 0;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, 30);
      }
LABEL_13:
      if ( WinHttpSetStatusCallback(g_hInetSess, SynchronousWinHTTPCallback, 0x4000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
        Win32Error = HrFromLastWin32Error();
      v2 = WPP_GLOBAL_Control;
      v4 = Win32Error == 0;
      if ( Win32Error >= 0 )
      {
LABEL_19:
        if ( v4 )
          return (unsigned int)Win32Error;
        goto LABEL_25;
      }
LABEL_16:
      if ( g_hInetSess )
      {
        WinHttpCloseHandle(g_hInetSess);
        v2 = WPP_GLOBAL_Control;
        g_hInetSess = 0;
      }
      v4 = Win32Error == 0;
      goto LABEL_19;
    }
    Win32Error = HrFromLastWin32Error();
    if ( (unsigned int)HrFromLastWin32Error() )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_8:
        if ( Win32Error < 0 )
          goto LABEL_16;
        goto LABEL_13;
      }
      v3 = HrFromLastWin32Error();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (unsigned int)"HrFromLastWin32Error: InternetSetOption",
        v3);
    }
    v2 = WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v5 = HrFromLastWin32Error();
  Win32Error = v5;
  if ( !v5 )
    return (unsigned int)Win32Error;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    return (unsigned int)Win32Error;
  if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
      (unsigned int)"HrInitInternetSession: InternetOpen",
      v5);
    v2 = WPP_GLOBAL_Control;
  }
LABEL_25:
  if ( v2 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v2[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)v2 + 2),
      17,
      (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
      (unsigned int)"HrInitInternetSession",
      Win32Error);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180045b04  mov     [rsp+arg_0], rbx
0x180045b09  push    rdi
0x180045b0a  sub     rsp, 30h
0x180045b0e  xor     r9d, r9d; pszProxyBypassW
0x180045b11  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180045b19  xor     r8d, r8d; pszProxyW
0x180045b1c  lea     rcx, pszAgentW; "Microsoft-Windows/10.0 UPnP/1.0"
0x180045b23  lea     edx, [r9+1]; dwAccessType
0x180045b27  call    cs:__imp_WinHttpOpen
0x180045b2d  mov     cs:?g_hInetSess@@3PEAXEA, rax; void * g_hInetSess
0x180045b34  test    rax, rax
0x180045b37  jz      loc_180045C56
0x180045b3d  mov     edx, 3A98h; nResolveTimeout
0x180045b42  mov     [rsp+38h+dwFlags], 2710h; nReceiveTimeout
0x180045b4a  mov     r9d, edx; nSendTimeout
0x180045b4d  mov     r8d, edx; nConnectTimeout
0x180045b50  mov     rcx, rax; hInternet
0x180045b53  call    cs:__imp_WinHttpSetTimeouts
0x180045b59  test    eax, eax
0x180045b5b  jnz     short loc_180045BBF
0x180045b5d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180045b62  mov     ebx, eax
0x180045b64  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180045b69  lea     rdi, WPP_GLOBAL_Control
0x180045b70  test    eax, eax
0x180045b72  jz      short loc_180045BB2
0x180045b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b7b  cmp     rcx, rdi
0x180045b7e  jz      short loc_180045BB9
0x180045b80  test    byte ptr [rcx+1Ch], 1
0x180045b84  jz      short loc_180045BB9
0x180045b86  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180045b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b92  lea     r9, aHrfromlastwin3; "HrFromLastWin32Error: InternetSetOption"
0x180045b99  mov     edx, 0Eh
0x180045b9e  mov     [rsp+38h+dwFlags], eax
0x180045ba2  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180045ba9  mov     rcx, [rcx+10h]
0x180045bad  call    WPP_SF_sd
0x180045bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bb9  test    ebx, ebx
0x180045bbb  js      short loc_180045C29
0x180045bbd  jmp     short loc_180045BF4
0x180045bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bc6  lea     rdi, WPP_GLOBAL_Control
0x180045bcd  xor     ebx, ebx
0x180045bcf  cmp     rcx, rdi
0x180045bd2  jz      short loc_180045BF4
0x180045bd4  test    dword ptr [rcx+1Ch], 800h
0x180045bdb  jz      short loc_180045BF4
0x180045bdd  mov     rcx, [rcx+10h]
0x180045be1  lea     edx, [rbx+0Fh]
0x180045be4  lea     r9d, [rbx+1Eh]
0x180045be8  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180045bef  call    WPP_SF_d
0x180045bf4  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hInternet
0x180045bfb  lea     rdx, SynchronousWinHTTPCallback; lpfnInternetCallback
0x180045c02  xor     r9d, r9d; dwReserved
0x180045c05  mov     r8d, 4000h; dwNotificationFlags
0x180045c0b  call    cs:__imp_WinHttpSetStatusCallback
0x180045c11  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180045c15  jnz     short loc_180045C1E
0x180045c17  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180045c1c  mov     ebx, eax
0x180045c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c25  test    ebx, ebx
0x180045c27  jns     short loc_180045C52
0x180045c29  mov     rax, cs:?g_hInetSess@@3PEAXEA; void * g_hInetSess
0x180045c30  test    rax, rax
0x180045c33  jz      short loc_180045C50
0x180045c35  mov     rcx, rax; hInternet
0x180045c38  call    cs:__imp_WinHttpCloseHandle
0x180045c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c45  mov     cs:?g_hInetSess@@3PEAXEA, 0; void * g_hInetSess
0x180045c50  test    ebx, ebx
0x180045c52  jz      short loc_180045CCC
0x180045c54  jmp     short loc_180045CA1
0x180045c56  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180045c5b  mov     ebx, eax
0x180045c5d  test    eax, eax
0x180045c5f  jz      short loc_180045CCC
0x180045c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c68  lea     rdi, WPP_GLOBAL_Control
0x180045c6f  cmp     rcx, rdi
0x180045c72  jz      short loc_180045CCC
0x180045c74  test    byte ptr [rcx+1Ch], 1
0x180045c78  jz      short loc_180045CA1
0x180045c7a  mov     rcx, [rcx+10h]
0x180045c7e  lea     r9, aHrinitinternet_0; "HrInitInternetSession: InternetOpen"
0x180045c85  mov     edx, 10h
0x180045c8a  mov     [rsp+38h+dwFlags], eax
0x180045c8e  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180045c95  call    WPP_SF_sd
0x180045c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ca1  cmp     rcx, rdi
0x180045ca4  jz      short loc_180045CCC
0x180045ca6  test    byte ptr [rcx+1Ch], 1
0x180045caa  jz      short loc_180045CCC
0x180045cac  mov     rcx, [rcx+10h]
0x180045cb0  lea     r9, aHrinitinternet; "HrInitInternetSession"
0x180045cb7  mov     edx, 11h
0x180045cbc  mov     [rsp+38h+dwFlags], ebx
0x180045cc0  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180045cc7  call    WPP_SF_sd
0x180045ccc  mov     eax, ebx
0x180045cce  mov     rbx, [rsp+38h+arg_0]
0x180045cd3  add     rsp, 30h
0x180045cd7  pop     rdi
0x180045cd8  retn
```
