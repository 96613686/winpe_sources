# CSsdpNotifyRequest::AsynchronousWinHTTPCallback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x18001d270`
- end: `0x18001d681`
- name: `?AsynchronousWinHTTPCallback@CSsdpNotifyRequest@@SAXPEAX_KK0K@Z`
- size: `1041`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000683c`
- `0x18001d270`
- `0x18001ec18`
- `0x1800271fc`
- `0x180029df0`
- `0x18002e8ac`
- `0x18002e8f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d349`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d5f9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d349`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d5f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d3f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d3f7`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001d48b`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001d48b`

## string_xrefs

- `0x18001d62e`: `AsynchronousWinHTTPCallback: Failed to trigger WinHTTP completion event.`

## pseudocode

```c
void __fastcall CSsdpNotifyRequest::AsynchronousWinHTTPCallback(
        HINTERNET hInternet,
        DWORD_PTR dwContext,
        DWORD dwInternetStatus,
        _DWORD *lpvStatusInformation)
{
  LPCSTR v8; // rcx
  char Win32Error; // al
  LPCSTR v10; // rcx
  char v11; // al
  int v12; // edx
  const char *v13; // r9
  signed int v14; // ebx
  int v15; // ebp
  signed int v16; // eax
  signed int Headers; // eax
  void *v18; // rcx

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && WPP_GLOBAL_Control[28] < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !dwContext )
  {
    if ( (unsigned int)HrFromLastWin32Error()
      && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      Win32Error = HrFromLastWin32Error();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        (unsigned int)WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
        (unsigned int)"AsynchronousWinHTTPCallback",
        Win32Error);
    }
    return;
  }
  if ( dwInternetStatus == 2048 )
  {
    if ( v8 != (LPCSTR)&WPP_GLOBAL_Control && v8[28] < 0 )
      WPP_SF_(*((_QWORD *)v8 + 2), 134, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
    if ( SetEvent(*(HANDLE *)(dwContext + 312)) || !(unsigned int)HrFromLastWin32Error() )
      goto LABEL_68;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
      return;
    if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_69;
    v11 = HrFromLastWin32Error();
    v12 = 135;
    v13 = "AsynchronousWinHTTPCallback: Failed to ack cancellation.";
    goto LABEL_67;
  }
  if ( dwInternetStatus == 0x200000 )
  {
    if ( v8 != (LPCSTR)&WPP_GLOBAL_Control && v8[28] < 0 )
    {
      WPP_SF_(*((_QWORD *)v8 + 2), 136, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    if ( lpvStatusInformation )
    {
      v14 = lpvStatusInformation[2];
      if ( v14 <= 0 )
      {
LABEL_59:
        if ( v8 != (LPCSTR)&WPP_GLOBAL_Control && v8[28] < 0 )
          WPP_SF_q(*((_QWORD *)v8 + 2), 144, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
        v18 = *(void **)(dwContext + 320);
        *(_DWORD *)(dwContext + 352) = 0;
        *(_DWORD *)(dwContext + 348) = v14;
        if ( SetEvent(v18) || !(unsigned int)HrFromLastWin32Error() )
          goto LABEL_68;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
          return;
        if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
          goto LABEL_69;
        v11 = HrFromLastWin32Error();
        v12 = 145;
        v13 = "AsynchronousWinHTTPCallback: Failed to trigger WinHTTP completion event.";
LABEL_67:
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          (unsigned int)WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
          (_DWORD)v13,
          v11);
        goto LABEL_68;
      }
    }
    else
    {
      LOWORD(v14) = 1;
    }
    v14 = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_59;
  }
  v15 = 0;
  v14 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(dwContext + 272));
  if ( *(_QWORD *)(dwContext + 264) )
  {
    switch ( dwInternetStatus )
    {
      case 0x4000u:
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && WPP_GLOBAL_Control[28] < 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
        v14 = -2147467259;
        goto LABEL_53;
      case 0x20000u:
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && WPP_GLOBAL_Control[28] < 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
        Headers = CSsdpNotifyRequest::HrFetchHeaders((CSsdpNotifyRequest *)dwContext);
        v14 = Headers;
        v15 = 1;
        if ( Headers && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            140,
            (unsigned int)WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
            (unsigned int)"AsynchronousWinHTTPCallback: Failed to fetch headers",
            Headers);
        break;
      case 0x400000u:
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && WPP_GLOBAL_Control[28] < 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
        if ( !WinHttpReceiveResponse(hInternet, 0) )
        {
          v16 = HrFromLastWin32Error();
          v14 = v16;
          if ( v16 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              138,
              (unsigned int)WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
              (unsigned int)"AsynchronousWinHTTPCallback: WinHttpReceiveResponse failed.",
              v16);
LABEL_53:
          v15 = 1;
        }
        break;
      default:
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && WPP_GLOBAL_Control[28] < 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            142,
            WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
            dwInternetStatus);
        break;
    }
  }
  else if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && WPP_GLOBAL_Control[28] < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(dwContext + 272));
  if ( v15 )
  {
    v8 = WPP_GLOBAL_Control;
    goto LABEL_59;
  }
LABEL_68:
  v10 = WPP_GLOBAL_Control;
LABEL_69:
  if ( v10 != (LPCSTR)&WPP_GLOBAL_Control && v10[28] < 0 )
    WPP_SF_(*((_QWORD *)v10 + 2), 146, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
}

```

## disassembly

```asm
0x18001d270  push    rbx
0x18001d272  push    rbp
0x18001d273  push    rsi
0x18001d274  push    rdi
0x18001d275  push    r12
0x18001d277  push    r13
0x18001d279  push    r14
0x18001d27b  push    r15
0x18001d27d  sub     rsp, 38h
0x18001d281  mov     rbx, r9
0x18001d284  mov     edi, r8d
0x18001d287  mov     rsi, rdx
0x18001d28a  mov     r14, rcx
0x18001d28d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d294  lea     r12, WPP_GLOBAL_Control
0x18001d29b  lea     r13, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18001d2a2  cmp     rcx, r12
0x18001d2a5  jz      short loc_18001D2C5
0x18001d2a7  test    byte ptr [rcx+1Ch], 80h
0x18001d2ab  jz      short loc_18001D2C5
0x18001d2ad  mov     rcx, [rcx+10h]
0x18001d2b1  mov     edx, 84h
0x18001d2b6  mov     r8, r13
0x18001d2b9  call    WPP_SF_
0x18001d2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2c5  test    rsi, rsi
0x18001d2c8  jnz     short loc_18001D31E
0x18001d2ca  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001d2cf  test    eax, eax
0x18001d2d1  jz      loc_18001D66F
0x18001d2d7  mov     rax, cs:WPP_GLOBAL_Control
0x18001d2de  cmp     rax, r12
0x18001d2e1  jz      loc_18001D66F
0x18001d2e7  test    byte ptr [rax+1Ch], 1
0x18001d2eb  jz      loc_18001D66F
0x18001d2f1  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001d2f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2fd  lea     r9, aAsynchronouswi_0; "AsynchronousWinHTTPCallback"
0x18001d304  mov     edx, 85h
0x18001d309  mov     [rsp+78h+var_58], eax
0x18001d30d  mov     r8, r13
0x18001d310  mov     rcx, [rcx+10h]
0x18001d314  call    WPP_SF_sd
0x18001d319  jmp     loc_18001D66F
0x18001d31e  cmp     edi, 800h
0x18001d324  jnz     short loc_18001D39A
0x18001d326  cmp     rcx, r12
0x18001d329  jz      short loc_18001D342
0x18001d32b  test    byte ptr [rcx+1Ch], 80h
0x18001d32f  jz      short loc_18001D342
0x18001d331  mov     rcx, [rcx+10h]
0x18001d335  mov     edx, 86h
0x18001d33a  mov     r8, r13
0x18001d33d  call    WPP_SF_
0x18001d342  mov     rcx, [rsi+138h]; hEvent
0x18001d349  call    cs:__imp_SetEvent
0x18001d350  nop     dword ptr [rax+rax+00h]
0x18001d355  test    eax, eax
0x18001d357  jnz     loc_18001D64C
0x18001d35d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001d362  test    eax, eax
0x18001d364  jz      loc_18001D64C
0x18001d36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d371  cmp     rcx, r12
0x18001d374  jz      loc_18001D66F
0x18001d37a  test    byte ptr [rcx+1Ch], 1
0x18001d37e  jz      loc_18001D653
0x18001d384  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001d389  mov     edx, 87h
0x18001d38e  lea     r9, aAsynchronouswi_2; "AsynchronousWinHTTPCallback: Failed to "...
0x18001d395  jmp     loc_18001D635
0x18001d39a  cmp     edi, 200000h
0x18001d3a0  jnz     short loc_18001D3E9
0x18001d3a2  cmp     rcx, r12
0x18001d3a5  jz      short loc_18001D3C5
0x18001d3a7  test    byte ptr [rcx+1Ch], 80h
0x18001d3ab  jz      short loc_18001D3C5
0x18001d3ad  mov     rcx, [rcx+10h]
0x18001d3b1  mov     edx, 88h
0x18001d3b6  mov     r8, r13
0x18001d3b9  call    WPP_SF_
0x18001d3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3c5  test    rbx, rbx
0x18001d3c8  jz      short loc_18001D3D6
0x18001d3ca  mov     ebx, [rbx+8]
0x18001d3cd  test    ebx, ebx
0x18001d3cf  jg      short loc_18001D3DB
0x18001d3d1  jmp     loc_18001D5C3
0x18001d3d6  mov     ebx, 1
0x18001d3db  movzx   ebx, bx
0x18001d3de  or      ebx, 80070000h
0x18001d3e4  jmp     loc_18001D5C3
0x18001d3e9  lea     r15, [rsi+110h]
0x18001d3f0  xor     ebp, ebp
0x18001d3f2  mov     rcx, r15; lpCriticalSection
0x18001d3f5  xor     ebx, ebx
0x18001d3f7  call    cs:__imp_EnterCriticalSection
0x18001d3fe  nop     dword ptr [rax+rax+00h]
0x18001d403  cmp     [rsi+108h], rbx
0x18001d40a  jz      loc_18001D582
0x18001d410  cmp     edi, 4000h
0x18001d416  jz      loc_18001D553
0x18001d41c  cmp     edi, 20000h
0x18001d422  jz      loc_18001D4E9
0x18001d428  cmp     edi, 400000h
0x18001d42e  jz      short loc_18001D463
0x18001d430  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d437  cmp     rcx, r12
0x18001d43a  jz      loc_18001D5A5
0x18001d440  test    byte ptr [rcx+1Ch], 80h
0x18001d444  jz      loc_18001D5A5
0x18001d44a  mov     rcx, [rcx+10h]
0x18001d44e  mov     edx, 8Eh
0x18001d453  mov     r9d, edi
0x18001d456  mov     r8, r13
0x18001d459  call    WPP_SF_d
0x18001d45e  jmp     loc_18001D5A5
0x18001d463  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d46a  cmp     rcx, r12
0x18001d46d  jz      short loc_18001D486
0x18001d46f  test    byte ptr [rcx+1Ch], 80h
0x18001d473  jz      short loc_18001D486
0x18001d475  mov     rcx, [rcx+10h]
0x18001d479  mov     edx, 89h
0x18001d47e  mov     r8, r13
0x18001d481  call    WPP_SF_
0x18001d486  xor     edx, edx; lpReserved
0x18001d488  mov     rcx, r14; hRequest
0x18001d48b  call    cs:__imp_WinHttpReceiveResponse
0x18001d492  nop     dword ptr [rax+rax+00h]
0x18001d497  test    eax, eax
0x18001d499  jnz     loc_18001D5A5
0x18001d49f  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001d4a4  mov     ebx, eax
0x18001d4a6  test    eax, eax
0x18001d4a8  jz      loc_18001D57B
0x18001d4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4b5  cmp     rcx, r12
0x18001d4b8  jz      loc_18001D57B
0x18001d4be  test    byte ptr [rcx+1Ch], 1
0x18001d4c2  jz      loc_18001D57B
0x18001d4c8  mov     rcx, [rcx+10h]
0x18001d4cc  lea     r9, aAsynchronouswi_3; "AsynchronousWinHTTPCallback: WinHttpRec"...
0x18001d4d3  mov     edx, 8Ah
0x18001d4d8  mov     [rsp+78h+var_58], eax
0x18001d4dc  mov     r8, r13
0x18001d4df  call    WPP_SF_sd
0x18001d4e4  jmp     loc_18001D57B
0x18001d4e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4f0  cmp     rcx, r12
0x18001d4f3  jz      short loc_18001D50C
0x18001d4f5  test    byte ptr [rcx+1Ch], 80h
0x18001d4f9  jz      short loc_18001D50C
0x18001d4fb  mov     rcx, [rcx+10h]
0x18001d4ff  mov     edx, 8Bh
0x18001d504  mov     r8, r13
0x18001d507  call    WPP_SF_
0x18001d50c  mov     rcx, rsi; this
0x18001d50f  call    ?HrFetchHeaders@CSsdpNotifyRequest@@QEAAJXZ; CSsdpNotifyRequest::HrFetchHeaders(void)
0x18001d514  mov     ebx, eax
0x18001d516  mov     ebp, 1
0x18001d51b  test    eax, eax
0x18001d51d  jz      loc_18001D5A5
0x18001d523  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d52a  cmp     rcx, r12
0x18001d52d  jz      short loc_18001D5A5
0x18001d52f  test    [rcx+1Ch], bpl
0x18001d533  jz      short loc_18001D5A5
0x18001d535  mov     rcx, [rcx+10h]
0x18001d539  lea     r9, aAsynchronouswi_1; "AsynchronousWinHTTPCallback: Failed to "...
0x18001d540  mov     edx, 8Ch
0x18001d545  mov     [rsp+78h+var_58], eax
0x18001d549  mov     r8, r13
0x18001d54c  call    WPP_SF_sd
0x18001d551  jmp     short loc_18001D5A5
0x18001d553  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d55a  cmp     rcx, r12
0x18001d55d  jz      short loc_18001D576
0x18001d55f  test    byte ptr [rcx+1Ch], 80h
0x18001d563  jz      short loc_18001D576
0x18001d565  mov     rcx, [rcx+10h]
0x18001d569  mov     edx, 8Dh
0x18001d56e  mov     r8, r13
0x18001d571  call    WPP_SF_
0x18001d576  mov     ebx, 80004005h
0x18001d57b  mov     ebp, 1
0x18001d580  jmp     short loc_18001D5A5
0x18001d582  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d589  cmp     rcx, r12
0x18001d58c  jz      short loc_18001D5A5
0x18001d58e  test    byte ptr [rcx+1Ch], 80h
0x18001d592  jz      short loc_18001D5A5
0x18001d594  mov     rcx, [rcx+10h]
0x18001d598  mov     edx, 8Fh
0x18001d59d  mov     r8, r13
0x18001d5a0  call    WPP_SF_
0x18001d5a5  mov     rcx, r15; lpCriticalSection
0x18001d5a8  call    cs:__imp_LeaveCriticalSection
0x18001d5af  nop     dword ptr [rax+rax+00h]
0x18001d5b4  test    ebp, ebp
0x18001d5b6  jz      loc_18001D64C
0x18001d5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5c3  cmp     rcx, r12
0x18001d5c6  jz      short loc_18001D5E2
0x18001d5c8  test    byte ptr [rcx+1Ch], 80h
0x18001d5cc  jz      short loc_18001D5E2
0x18001d5ce  mov     rcx, [rcx+10h]
0x18001d5d2  mov     edx, 90h
0x18001d5d7  mov     r9, rsi
0x18001d5da  mov     r8, r13
0x18001d5dd  call    WPP_SF_q
0x18001d5e2  mov     rcx, [rsi+140h]; hEvent
0x18001d5e9  mov     dword ptr [rsi+160h], 0
0x18001d5f3  mov     [rsi+15Ch], ebx
0x18001d5f9  call    cs:__imp_SetEvent
0x18001d600  nop     dword ptr [rax+rax+00h]
0x18001d605  test    eax, eax
0x18001d607  jnz     short loc_18001D64C
0x18001d609  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001d60e  test    eax, eax
0x18001d610  jz      short loc_18001D64C
0x18001d612  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d619  cmp     rcx, r12
0x18001d61c  jz      short loc_18001D66F
0x18001d61e  test    byte ptr [rcx+1Ch], 1
0x18001d622  jz      short loc_18001D653
0x18001d624  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001d629  mov     edx, 91h
0x18001d62e  lea     r9, aAsynchronouswi; "AsynchronousWinHTTPCallback: Failed to "...
0x18001d635  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d63c  mov     r8, r13
0x18001d63f  mov     [rsp+78h+var_58], eax
0x18001d643  mov     rcx, [rcx+10h]
0x18001d647  call    WPP_SF_sd
0x18001d64c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d653  cmp     rcx, r12
0x18001d656  jz      short loc_18001D66F
0x18001d658  test    byte ptr [rcx+1Ch], 80h
0x18001d65c  jz      short loc_18001D66F
0x18001d65e  mov     rcx, [rcx+10h]
0x18001d662  mov     edx, 92h
0x18001d667  mov     r8, r13
0x18001d66a  call    WPP_SF_
0x18001d66f  add     rsp, 38h
0x18001d673  pop     r15
0x18001d675  pop     r14
0x18001d677  pop     r13
0x18001d679  pop     r12
0x18001d67b  pop     rdi
0x18001d67c  pop     rsi
0x18001d67d  pop     rbp
0x18001d67e  pop     rbx
0x18001d67f  retn
```
