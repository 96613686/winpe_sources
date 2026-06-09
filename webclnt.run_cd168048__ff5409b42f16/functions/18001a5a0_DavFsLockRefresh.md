# DavFsLockRefresh

- ea: `0x18001a5a0`
- end: `0x18001ad06`
- name: `DavFsLockRefresh`
- size: `1894`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x180010478`
- `0x180010770`
- `0x180012468`
- `0x1800134d8`
- `0x180013c08`
- `0x18001a5a0`
- `0x1800283fc`
- `0x180028440`
- `0x180028584`
- `0x180028680`
- `0x1800297e4`
- `0x180029bec`
- `0x18002cf62`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a94b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a94b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a9a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a9a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a691`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001acfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a691`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001acfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a622`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a622`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001abc4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001abc4`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x18001a615`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x18001a615`
- `KERNEL32!LocalFree` at `0x18001abb5`
- `KERNEL32!LocalFree` at `0x18001abb5`
- `KERNEL32!LocalAlloc` at `0x18001aa20`
- `KERNEL32!LocalAlloc` at `0x18001aa20`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001a7fd`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001a8a7`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001a8f4`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001a941`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001a7fd`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001a8a7`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001a8f4`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001a941`
- `WINHTTP!WinHttpReadData` at `0x18001aa8f`
- `WINHTTP!WinHttpReadData` at `0x18001ab39`
- `WINHTTP!WinHttpReadData` at `0x18001aa8f`
- `WINHTTP!WinHttpReadData` at `0x18001ab39`
- `WINHTTP!WinHttpSetOption` at `0x18001a7a7`
- `WINHTTP!WinHttpSetOption` at `0x18001a7a7`
- `WINHTTP!WinHttpCloseHandle` at `0x18001ab96`
- `WINHTTP!WinHttpCloseHandle` at `0x18001ab96`

## pseudocode

```c
__int64 __fastcall DavFsLockRefresh(__int64 a1)
{
  __int64 v2; // r15
  __int64 v3; // rbx
  __int64 v4; // rdx
  _BYTE hMem[64]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v7; // [rsp+190h] [rbp+90h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+198h] [rbp+98h]
  int Buffer; // [rsp+1A0h] [rbp+A0h]
  int v10; // [rsp+1A8h] [rbp+A8h]

  v7 = 0;
  memset_0(hMem, 0, 0xA0u);
  v2 = *(_QWORD *)(a1 + 640);
  v3 = *(_QWORD *)(a1 + 632);
  dwNumberOfBytesRead = 0;
  v10 = 0;
  Buffer = 0;
  DavRemoveDummyShareFromFileName(v2 + 2, v4);
  EnterCriticalSection(&HashServerEntryTableLock);
  DavDoesUserEntryExist((HLOCAL)(v3 + 2), (__int64)&v7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
  LeaveCriticalSection(&HashServerEntryTableLock);
  DavCloseContext(0, 0);
  if ( v10 )
    RevertToSelf();
  return 1223;
}

```

## disassembly

```asm
0x18001a5a0  push    rbp
0x18001a5a2  push    rbx
0x18001a5a3  push    rsi
0x18001a5a4  push    rdi
0x18001a5a5  push    r12
0x18001a5a7  push    r13
0x18001a5a9  push    r14
0x18001a5ab  push    r15
0x18001a5ad  lea     rbp, [rsp-48h]
0x18001a5b2  sub     rsp, 148h
0x18001a5b9  xor     esi, esi
0x18001a5bb  mov     r13, rcx
0x18001a5be  lea     rcx, [rbp+80h+hMem]; void *
0x18001a5c2  mov     [rsp+180h+hInternet], rsi
0x18001a5c7  xor     edx, edx; Val
0x18001a5c9  mov     [rbp+80h+var_F0], rsi
0x18001a5cd  mov     r8d, 0A0h; Size
0x18001a5d3  mov     [rbp+80h+arg_0], rsi
0x18001a5da  mov     r14d, esi
0x18001a5dd  call    memset_0
0x18001a5e2  mov     r15, [r13+280h]
0x18001a5e9  mov     r12d, esi
0x18001a5ec  mov     rbx, [r13+278h]
0x18001a5f3  mov     [rbp+80h+var_F8], rsi
0x18001a5f7  mov     [rbp+80h+var_100], rsi
0x18001a5fb  lea     rcx, [r15+2]
0x18001a5ff  mov     [rbp+80h+dwNumberOfBytesRead], esi
0x18001a605  mov     [rsp+180h+var_108], esi
0x18001a609  mov     [rbp+80h+arg_18], esi
0x18001a60f  mov     [rbp+80h+Buffer], esi
0x18001a615  call    cs:__imp_DavRemoveDummyShareFromFileName
0x18001a61b  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x18001a622  call    cs:__imp_EnterCriticalSection
0x18001a628  mov     edx, [r13+290h]
0x18001a62f  lea     rax, [rbp+80h+arg_0]
0x18001a636  lea     r8, [r13+294h]
0x18001a63d  mov     qword ptr [rsp+180h+var_160], rax; __int64
0x18001a642  lea     r9, [rbp+80h+var_F0]
0x18001a646  lea     rcx, [rbx+2]; hMem
0x18001a64a  call    DavDoesUserEntryExist
0x18001a64f  test    eax, eax
0x18001a651  jz      loc_18001ACB9
0x18001a657  mov     rax, [rbp+80h+arg_0]
0x18001a65e  test    rax, rax
0x18001a661  jz      loc_18001ACB9
0x18001a667  mov     rdi, [rbp+80h+var_F0]
0x18001a66b  test    rdi, rdi
0x18001a66e  jz      loc_18001ACB9
0x18001a674  mov     [r13+1F0h], rdi
0x18001a67b  lea     esi, [r12+1]
0x18001a680  mov     [r13+1F8h], rax
0x18001a687  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x18001a68e  add     [rdi+40h], esi
0x18001a691  call    cs:__imp_LeaveCriticalSection
0x18001a697  mov     rdx, [r13+48h]
0x18001a69b  mov     rcx, r13
0x18001a69e  call    UMReflectorImpersonate
0x18001a6a3  mov     ebx, eax
0x18001a6a5  test    eax, eax
0x18001a6a7  jz      short loc_18001A6E7
0x18001a6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6b0  lea     rdi, WPP_GLOBAL_Control
0x18001a6b7  cmp     rcx, rdi
0x18001a6ba  jz      loc_18001AB7E
0x18001a6c0  test    [rcx+1Ch], sil
0x18001a6c4  jz      loc_18001AB7E
0x18001a6ca  mov     edx, 110h
0x18001a6cf  mov     r9d, eax
0x18001a6d2  mov     rcx, [rcx+10h]
0x18001a6d6  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001a6dd  call    WPP_SF_d
0x18001a6e2  jmp     loc_18001AB7E
0x18001a6e7  mov     rax, [r13+1F8h]
0x18001a6ee  lea     rcx, [rsp+180h+hInternet]
0x18001a6f3  mov     rdx, [rdi+28h]
0x18001a6f7  lea     r9, [r15+2]
0x18001a6fb  mov     [rsp+180h+var_120], rcx
0x18001a700  lea     r8, aLock; "LOCK"
0x18001a707  mov     rcx, [rdi+20h]
0x18001a70b  mov     eax, [rax+20h]
0x18001a70e  mov     [rsp+180h+var_130], eax
0x18001a712  lea     rax, aDavfslockrefre; "DavFsLockRefresh"
0x18001a719  mov     [rsp+180h+var_138], rax
0x18001a71e  mov     dword ptr [rsp+180h+var_148], 100h
0x18001a726  mov     [rbp+80h+arg_18], esi
0x18001a72c  call    DavHttpOpenRequestW
0x18001a731  test    eax, eax
0x18001a733  jnz     short loc_18001A747
0x18001a735  call    cs:__imp_GetLastError
0x18001a73b  mov     r14, [rsp+180h+hInternet]
0x18001a740  mov     ebx, eax
0x18001a742  jmp     loc_18001AB7E
0x18001a747  mov     r14, [rsp+180h+hInternet]
0x18001a74c  test    r14, r14
0x18001a74f  jnz     short loc_18001A784
0x18001a751  call    cs:__imp_GetLastError
0x18001a757  mov     ebx, eax
0x18001a759  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a760  lea     rdi, WPP_GLOBAL_Control
0x18001a767  cmp     rcx, rdi
0x18001a76a  jz      loc_18001AB7E
0x18001a770  test    [rcx+1Ch], sil
0x18001a774  jz      loc_18001AB7E
0x18001a77a  mov     edx, 111h
0x18001a77f  jmp     loc_18001A6CF
0x18001a784  cmp     cs:g_DisableCookies, r12d
0x18001a78b  mov     [rbp+80h+Buffer], esi
0x18001a791  jz      short loc_18001A7E4
0x18001a793  mov     r9d, 4; dwBufferLength
0x18001a799  lea     r8, [rbp+80h+Buffer]; lpBuffer
0x18001a7a0  mov     rcx, r14; hInternet
0x18001a7a3  lea     edx, [r9+3Bh]; dwOption
0x18001a7a7  call    cs:__imp_WinHttpSetOption
0x18001a7ad  test    eax, eax
0x18001a7af  jnz     short loc_18001A7E4
0x18001a7b1  call    cs:__imp_GetLastError
0x18001a7b7  mov     ebx, eax
0x18001a7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7c0  lea     rdi, WPP_GLOBAL_Control
0x18001a7c7  cmp     rcx, rdi
0x18001a7ca  jz      loc_18001AB7E
0x18001a7d0  test    [rcx+1Ch], sil
0x18001a7d4  jz      loc_18001AB7E
0x18001a7da  mov     edx, 112h
0x18001a7df  jmp     loc_18001A6CF
0x18001a7e4  mov     edi, 0A0000000h
0x18001a7e9  lea     rdx, szHeaders; "translate: f\n"
0x18001a7f0  or      r15d, 0FFFFFFFFh
0x18001a7f4  mov     r9d, edi; dwModifiers
0x18001a7f7  mov     r8d, r15d; dwHeadersLength
0x18001a7fa  mov     rcx, r14; hRequest
0x18001a7fd  call    cs:__imp_WinHttpAddRequestHeaders
0x18001a803  test    eax, eax
0x18001a805  jnz     short loc_18001A83A
0x18001a807  call    cs:__imp_GetLastError
0x18001a80d  mov     ebx, eax
0x18001a80f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a816  lea     rdi, WPP_GLOBAL_Control
0x18001a81d  cmp     rcx, rdi
0x18001a820  jz      loc_18001AB7E
0x18001a826  test    [rcx+1Ch], sil
0x18001a82a  jz      loc_18001AB7E
0x18001a830  mov     edx, 113h
0x18001a835  jmp     loc_18001A6CF
0x18001a83a  mov     rax, [r13+1F0h]
0x18001a841  test    rax, rax
0x18001a844  jz      short loc_18001A851
0x18001a846  cmp     dword ptr [rax+68h], 2
0x18001a84a  jnz     short loc_18001A851
0x18001a84c  xor     r9d, r9d
0x18001a84f  jmp     short loc_18001A854
0x18001a851  mov     r9d, esi
0x18001a854  mov     r8, r14
0x18001a857  mov     [rsp+180h+var_160], r12d
0x18001a85c  xor     edx, edx
0x18001a85e  mov     rcx, r13
0x18001a861  call    DavInternetSetOption
0x18001a866  mov     ebx, eax
0x18001a868  test    eax, eax
0x18001a86a  jz      short loc_18001A897
0x18001a86c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a873  lea     rdi, WPP_GLOBAL_Control
0x18001a87a  cmp     rcx, rdi
0x18001a87d  jz      loc_18001AB7E
0x18001a883  test    [rcx+1Ch], sil
0x18001a887  jz      loc_18001AB7E
0x18001a88d  mov     edx, 114h
0x18001a892  jmp     loc_18001A6CF
0x18001a897  mov     r9d, edi; dwModifiers
0x18001a89a  lea     rdx, aTimeoutSecond3; "Timeout: Second-3600\n"
0x18001a8a1  mov     r8d, r15d; dwHeadersLength
0x18001a8a4  mov     rcx, r14; hRequest
0x18001a8a7  call    cs:__imp_WinHttpAddRequestHeaders
0x18001a8ad  test    eax, eax
0x18001a8af  jnz     short loc_18001A8E4
0x18001a8b1  call    cs:__imp_GetLastError
0x18001a8b7  mov     ebx, eax
0x18001a8b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8c0  lea     rdi, WPP_GLOBAL_Control
0x18001a8c7  cmp     rcx, rdi
0x18001a8ca  jz      loc_18001AB7E
0x18001a8d0  test    [rcx+1Ch], sil
0x18001a8d4  jz      loc_18001AB7E
0x18001a8da  mov     edx, 115h
0x18001a8df  jmp     loc_18001A6CF
0x18001a8e4  mov     rdx, [r13+288h]; lpszHeaders
0x18001a8eb  mov     r9d, edi; dwModifiers
0x18001a8ee  mov     r8d, r15d; dwHeadersLength
0x18001a8f1  mov     rcx, r14; hRequest
0x18001a8f4  call    cs:__imp_WinHttpAddRequestHeaders
0x18001a8fa  test    eax, eax
0x18001a8fc  jnz     short loc_18001A931
0x18001a8fe  call    cs:__imp_GetLastError
0x18001a904  mov     ebx, eax
0x18001a906  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a90d  lea     rdi, WPP_GLOBAL_Control
0x18001a914  cmp     rcx, rdi
0x18001a917  jz      loc_18001AB7E
0x18001a91d  test    [rcx+1Ch], sil
0x18001a921  jz      loc_18001AB7E
0x18001a927  mov     edx, 116h
0x18001a92c  jmp     loc_18001A6CF
0x18001a931  mov     r9d, edi; dwModifiers
0x18001a934  lea     rdx, aContentLength0; "Content-Length: 0"
0x18001a93b  mov     r8d, r15d; dwHeadersLength
0x18001a93e  mov     rcx, r14; hRequest
0x18001a941  call    cs:__imp_WinHttpAddRequestHeaders
0x18001a947  test    eax, eax
0x18001a949  jnz     short loc_18001A97E
0x18001a94b  call    cs:__imp_GetLastError
0x18001a951  mov     ebx, eax
0x18001a953  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a95a  lea     rdi, WPP_GLOBAL_Control
0x18001a961  cmp     rcx, rdi
0x18001a964  jz      loc_18001AB7E
0x18001a96a  test    [rcx+1Ch], sil
0x18001a96e  jz      loc_18001AB7E
0x18001a974  mov     edx, 117h
0x18001a979  jmp     loc_18001A6CF
0x18001a97e  mov     [rsp+180h+var_148], r13; __int64
0x18001a983  xor     r9d, r9d
0x18001a986  mov     [rsp+180h+var_158], r12d; DWORD
0x18001a98b  xor     r8d, r8d
0x18001a98e  xor     edx, edx
0x18001a990  mov     [rsp+180h+var_160], r12d; DWORD
0x18001a995  mov     rcx, r14; hRequest
0x18001a998  call    DavSendRequest
0x18001a99d  mov     ebx, eax
0x18001a99f  test    eax, eax
0x18001a9a1  jz      short loc_18001A9D9
0x18001a9a3  mov     ecx, eax; dwErrCode
0x18001a9a5  call    cs:__imp_SetLastError
0x18001a9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9b2  lea     rdi, WPP_GLOBAL_Control
0x18001a9b9  cmp     rcx, rdi
0x18001a9bc  jz      loc_18001AB7E
0x18001a9c2  test    [rcx+1Ch], sil
0x18001a9c6  jz      loc_18001AB7E
0x18001a9cc  mov     edx, 118h
0x18001a9d1  mov     r9d, ebx
0x18001a9d4  jmp     loc_18001A6D2
0x18001a9d9  xor     edx, edx
0x18001a9db  mov     rcx, r14
0x18001a9de  call    DavQueryAndParseResponseEx
0x18001a9e3  mov     ebx, eax
0x18001a9e5  test    eax, eax
0x18001a9e7  jz      short loc_18001AA14
0x18001a9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9f0  lea     rdi, WPP_GLOBAL_Control
0x18001a9f7  cmp     rcx, rdi
0x18001a9fa  jz      loc_18001AB7E
0x18001aa00  test    [rcx+1Ch], sil
0x18001aa04  jz      loc_18001AB7E
0x18001aa0a  mov     edx, 119h
0x18001aa0f  jmp     loc_18001A6CF
0x18001aa14  mov     ebx, 1000h
0x18001aa19  mov     ecx, 40h ; '@'; uFlags
0x18001aa1e  mov     edx, ebx; uBytes
0x18001aa20  call    cs:__imp_LocalAlloc
0x18001aa26  mov     [rsp+180h+hInternet], rax
0x18001aa2b  mov     r12, rax
0x18001aa2e  test    rax, rax
0x18001aa31  jnz     short loc_18001AA79
0x18001aa33  call    cs:__imp_GetLastError
0x18001aa39  mov     ebx, eax
0x18001aa3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa42  lea     rdi, WPP_GLOBAL_Control
0x18001aa49  cmp     rcx, rdi
0x18001aa4c  jz      loc_18001AB7E
0x18001aa52  test    [rcx+1Ch], sil
0x18001aa56  jz      loc_18001AB7E
0x18001aa5c  mov     rcx, [rcx+10h]
0x18001aa60  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001aa67  mov     edx, 11Ah
0x18001aa6c  mov     r9d, eax
0x18001aa6f  call    WPP_SF_d
0x18001aa74  jmp     loc_18001AB7E
0x18001aa79  mov     r8d, ebx; dwNumberOfBytesToRead
0x18001aa7c  lea     r9, [rbp+80h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18001aa83  xor     r12d, r12d
0x18001aa86  mov     rdx, rax; lpBuffer
0x18001aa89  mov     rcx, r14; hRequest
0x18001aa8c  mov     rbx, rax
0x18001aa8f  call    cs:__imp_WinHttpReadData
0x18001aa95  lea     rdi, WPP_GLOBAL_Control
0x18001aa9c  jmp     loc_18001AB3F
0x18001aaa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aaa8  cmp     rcx, rdi
0x18001aaab  jz      short loc_18001AAD6
0x18001aaad  test    byte ptr [rcx+1Ch], 2
0x18001aab1  jz      short loc_18001AAD6
0x18001aab3  mov     r9d, [rbp+80h+dwNumberOfBytesRead]
0x18001aaba  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001aac1  mov     rcx, [rcx+10h]
0x18001aac5  mov     edx, 11Ch
0x18001aaca  call    WPP_SF_d
0x18001aacf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aad6  mov     r9d, [rbp+80h+dwNumberOfBytesRead]
0x18001aadd  add     r12d, r9d
0x18001aae0  mov     eax, cs:DavFileAttributesLimitInBytes
  ... truncated ...
```
