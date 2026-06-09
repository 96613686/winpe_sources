# HrInitInternetSession(void)

- ea: `0x180048790`
- end: `0x18004897e`
- name: `?HrInitInternetSession@@YAJXZ`
- size: `494`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180027500`
- `0x180037134`

## callees

- `0x1800074dc`
- `0x1800200f4`
- `0x18003b1cc`
- `0x180048790`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x1800487b3`
- `WINHTTP!WinHttpOpen` at `0x1800487b3`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800488a3`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800488a3`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800487e5`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800487e5`
- `WINHTTP!WinHttpCloseHandle` at `0x1800488d6`
- `WINHTTP!WinHttpCloseHandle` at `0x1800488d6`

## string_xrefs

- `0x180048922`: `HrInitInternetSession: InternetOpen`

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
0x180048790  mov     [rsp+arg_0], rbx
0x180048795  push    rdi
0x180048796  sub     rsp, 30h
0x18004879a  xor     r9d, r9d; pszProxyBypassW
0x18004879d  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800487a5  xor     r8d, r8d; pszProxyW
0x1800487a8  lea     rcx, pszAgentW; "Microsoft-Windows/10.0 UPnP/1.0"
0x1800487af  lea     edx, [r9+1]; dwAccessType
0x1800487b3  call    cs:__imp_WinHttpOpen
0x1800487ba  nop     dword ptr [rax+rax+00h]
0x1800487bf  mov     cs:?g_hInetSess@@3PEAXEA, rax; void * g_hInetSess
0x1800487c6  test    rax, rax
0x1800487c9  jz      loc_1800488FA
0x1800487cf  mov     edx, 3A98h; nResolveTimeout
0x1800487d4  mov     [rsp+38h+dwFlags], 2710h; nReceiveTimeout
0x1800487dc  mov     r9d, edx; nSendTimeout
0x1800487df  mov     r8d, edx; nConnectTimeout
0x1800487e2  mov     rcx, rax; hInternet
0x1800487e5  call    cs:__imp_WinHttpSetTimeouts
0x1800487ec  nop     dword ptr [rax+rax+00h]
0x1800487f1  test    eax, eax
0x1800487f3  jnz     short loc_180048857
0x1800487f5  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800487fa  mov     ebx, eax
0x1800487fc  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180048801  lea     rdi, WPP_GLOBAL_Control
0x180048808  test    eax, eax
0x18004880a  jz      short loc_18004884A
0x18004880c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048813  cmp     rcx, rdi
0x180048816  jz      short loc_180048851
0x180048818  test    byte ptr [rcx+1Ch], 1
0x18004881c  jz      short loc_180048851
0x18004881e  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180048823  mov     rcx, cs:WPP_GLOBAL_Control
0x18004882a  lea     r9, aHrfromlastwin3; "HrFromLastWin32Error: InternetSetOption"
0x180048831  mov     edx, 0Eh
0x180048836  mov     [rsp+38h+dwFlags], eax
0x18004883a  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180048841  mov     rcx, [rcx+10h]
0x180048845  call    WPP_SF_sd
0x18004884a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048851  test    ebx, ebx
0x180048853  js      short loc_1800488C7
0x180048855  jmp     short loc_18004888C
0x180048857  mov     rcx, cs:WPP_GLOBAL_Control
0x18004885e  lea     rdi, WPP_GLOBAL_Control
0x180048865  xor     ebx, ebx
0x180048867  cmp     rcx, rdi
0x18004886a  jz      short loc_18004888C
0x18004886c  test    dword ptr [rcx+1Ch], 800h
0x180048873  jz      short loc_18004888C
0x180048875  mov     rcx, [rcx+10h]
0x180048879  lea     edx, [rbx+0Fh]
0x18004887c  lea     r9d, [rbx+1Eh]
0x180048880  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180048887  call    WPP_SF_d
0x18004888c  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hInternet
0x180048893  lea     rdx, SynchronousWinHTTPCallback; lpfnInternetCallback
0x18004889a  xor     r9d, r9d; dwReserved
0x18004889d  mov     r8d, 4000h; dwNotificationFlags
0x1800488a3  call    cs:__imp_WinHttpSetStatusCallback
0x1800488aa  nop     dword ptr [rax+rax+00h]
0x1800488af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800488b3  jnz     short loc_1800488BC
0x1800488b5  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800488ba  mov     ebx, eax
0x1800488bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800488c3  test    ebx, ebx
0x1800488c5  jns     short loc_1800488F6
0x1800488c7  mov     rax, cs:?g_hInetSess@@3PEAXEA; void * g_hInetSess
0x1800488ce  test    rax, rax
0x1800488d1  jz      short loc_1800488F4
0x1800488d3  mov     rcx, rax; hInternet
0x1800488d6  call    cs:__imp_WinHttpCloseHandle
0x1800488dd  nop     dword ptr [rax+rax+00h]
0x1800488e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800488e9  mov     cs:?g_hInetSess@@3PEAXEA, 0; void * g_hInetSess
0x1800488f4  test    ebx, ebx
0x1800488f6  jz      short loc_180048970
0x1800488f8  jmp     short loc_180048945
0x1800488fa  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800488ff  mov     ebx, eax
0x180048901  test    eax, eax
0x180048903  jz      short loc_180048970
0x180048905  mov     rcx, cs:WPP_GLOBAL_Control
0x18004890c  lea     rdi, WPP_GLOBAL_Control
0x180048913  cmp     rcx, rdi
0x180048916  jz      short loc_180048970
0x180048918  test    byte ptr [rcx+1Ch], 1
0x18004891c  jz      short loc_180048945
0x18004891e  mov     rcx, [rcx+10h]
0x180048922  lea     r9, aHrinitinternet_0; "HrInitInternetSession: InternetOpen"
0x180048929  mov     edx, 10h
0x18004892e  mov     [rsp+38h+dwFlags], eax
0x180048932  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180048939  call    WPP_SF_sd
0x18004893e  mov     rcx, cs:WPP_GLOBAL_Control
0x180048945  cmp     rcx, rdi
0x180048948  jz      short loc_180048970
0x18004894a  test    byte ptr [rcx+1Ch], 1
0x18004894e  jz      short loc_180048970
0x180048950  mov     rcx, [rcx+10h]
0x180048954  lea     r9, aHrinitinternet; "HrInitInternetSession"
0x18004895b  mov     edx, 11h
0x180048960  mov     [rsp+38h+dwFlags], ebx
0x180048964  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x18004896b  call    WPP_SF_sd
0x180048970  mov     eax, ebx
0x180048972  mov     rbx, [rsp+38h+arg_0]
0x180048977  add     rsp, 30h
0x18004897b  pop     rdi
0x18004897c  retn
```
