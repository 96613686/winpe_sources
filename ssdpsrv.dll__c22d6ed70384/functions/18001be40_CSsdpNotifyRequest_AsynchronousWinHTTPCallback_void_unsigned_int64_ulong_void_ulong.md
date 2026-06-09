# CSsdpNotifyRequest::AsynchronousWinHTTPCallback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x18001be40`
- end: `0x18001c232`
- name: `?AsynchronousWinHTTPCallback@CSsdpNotifyRequest@@SAXPEAX_KK0K@Z`
- size: `1010`
- prototype: `void __fastcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, _DWORD *lpvStatusInformation)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000554c`
- `0x18001be40`
- `0x18001d7a0`
- `0x1800255a8`
- `0x180028000`
- `0x18002c8cc`
- `0x18002c90c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c166`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c166`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bf19`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c1b1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bf19`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c1b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bfc1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bfc1`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001c04f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001c04f`

## string_xrefs

- `0x18001c1e0`: `AsynchronousWinHTTPCallback: Failed to trigger WinHTTP completion event.`

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
          WPP_SF_q(*((_QWORD *)v8 + 2), 144, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, dwContext);
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
0x18001be40  push    rbx
0x18001be42  push    rbp
0x18001be43  push    rsi
0x18001be44  push    rdi
0x18001be45  push    r12
0x18001be47  push    r13
0x18001be49  push    r14
0x18001be4b  push    r15
0x18001be4d  sub     rsp, 38h
0x18001be51  mov     rbx, r9
0x18001be54  mov     edi, r8d
0x18001be57  mov     rsi, rdx
0x18001be5a  mov     r14, rcx
0x18001be5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be64  lea     r12, WPP_GLOBAL_Control
0x18001be6b  lea     r13, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18001be72  cmp     rcx, r12
0x18001be75  jz      short loc_18001BE95
0x18001be77  test    byte ptr [rcx+1Ch], 80h
0x18001be7b  jz      short loc_18001BE95
0x18001be7d  mov     rcx, [rcx+10h]
0x18001be81  mov     edx, 84h
0x18001be86  mov     r8, r13
0x18001be89  call    WPP_SF_
0x18001be8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be95  test    rsi, rsi
0x18001be98  jnz     short loc_18001BEEE
0x18001be9a  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001be9f  test    eax, eax
0x18001bea1  jz      loc_18001C221
0x18001bea7  mov     rax, cs:WPP_GLOBAL_Control
0x18001beae  cmp     rax, r12
0x18001beb1  jz      loc_18001C221
0x18001beb7  test    byte ptr [rax+1Ch], 1
0x18001bebb  jz      loc_18001C221
0x18001bec1  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001bec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001becd  lea     r9, aAsynchronouswi_0; "AsynchronousWinHTTPCallback"
0x18001bed4  mov     edx, 85h
0x18001bed9  mov     [rsp+78h+var_58], eax
0x18001bedd  mov     r8, r13
0x18001bee0  mov     rcx, [rcx+10h]
0x18001bee4  call    WPP_SF_sd
0x18001bee9  jmp     loc_18001C221
0x18001beee  cmp     edi, 800h
0x18001bef4  jnz     short loc_18001BF64
0x18001bef6  cmp     rcx, r12
0x18001bef9  jz      short loc_18001BF12
0x18001befb  test    byte ptr [rcx+1Ch], 80h
0x18001beff  jz      short loc_18001BF12
0x18001bf01  mov     rcx, [rcx+10h]
0x18001bf05  mov     edx, 86h
0x18001bf0a  mov     r8, r13
0x18001bf0d  call    WPP_SF_
0x18001bf12  mov     rcx, [rsi+138h]; hEvent
0x18001bf19  call    cs:__imp_SetEvent
0x18001bf1f  test    eax, eax
0x18001bf21  jnz     loc_18001C1FE
0x18001bf27  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001bf2c  test    eax, eax
0x18001bf2e  jz      loc_18001C1FE
0x18001bf34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf3b  cmp     rcx, r12
0x18001bf3e  jz      loc_18001C221
0x18001bf44  test    byte ptr [rcx+1Ch], 1
0x18001bf48  jz      loc_18001C205
0x18001bf4e  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001bf53  mov     edx, 87h
0x18001bf58  lea     r9, aAsynchronouswi_2; "AsynchronousWinHTTPCallback: Failed to "...
0x18001bf5f  jmp     loc_18001C1E7
0x18001bf64  cmp     edi, 200000h
0x18001bf6a  jnz     short loc_18001BFB3
0x18001bf6c  cmp     rcx, r12
0x18001bf6f  jz      short loc_18001BF8F
0x18001bf71  test    byte ptr [rcx+1Ch], 80h
0x18001bf75  jz      short loc_18001BF8F
0x18001bf77  mov     rcx, [rcx+10h]
0x18001bf7b  mov     edx, 88h
0x18001bf80  mov     r8, r13
0x18001bf83  call    WPP_SF_
0x18001bf88  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf8f  test    rbx, rbx
0x18001bf92  jz      short loc_18001BFA0
0x18001bf94  mov     ebx, [rbx+8]
0x18001bf97  test    ebx, ebx
0x18001bf99  jg      short loc_18001BFA5
0x18001bf9b  jmp     loc_18001C17B
0x18001bfa0  mov     ebx, 1
0x18001bfa5  movzx   ebx, bx
0x18001bfa8  or      ebx, 80070000h
0x18001bfae  jmp     loc_18001C17B
0x18001bfb3  lea     r15, [rsi+110h]
0x18001bfba  xor     ebp, ebp
0x18001bfbc  mov     rcx, r15; lpCriticalSection
0x18001bfbf  xor     ebx, ebx
0x18001bfc1  call    cs:__imp_EnterCriticalSection
0x18001bfc7  cmp     [rsi+108h], rbx
0x18001bfce  jz      loc_18001C140
0x18001bfd4  cmp     edi, 4000h
0x18001bfda  jz      loc_18001C111
0x18001bfe0  cmp     edi, 20000h
0x18001bfe6  jz      loc_18001C0A7
0x18001bfec  cmp     edi, 400000h
0x18001bff2  jz      short loc_18001C027
0x18001bff4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bffb  cmp     rcx, r12
0x18001bffe  jz      loc_18001C163
0x18001c004  test    byte ptr [rcx+1Ch], 80h
0x18001c008  jz      loc_18001C163
0x18001c00e  mov     rcx, [rcx+10h]
0x18001c012  mov     edx, 8Eh
0x18001c017  mov     r9d, edi
0x18001c01a  mov     r8, r13
0x18001c01d  call    WPP_SF_d
0x18001c022  jmp     loc_18001C163
0x18001c027  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c02e  cmp     rcx, r12
0x18001c031  jz      short loc_18001C04A
0x18001c033  test    byte ptr [rcx+1Ch], 80h
0x18001c037  jz      short loc_18001C04A
0x18001c039  mov     rcx, [rcx+10h]
0x18001c03d  mov     edx, 89h
0x18001c042  mov     r8, r13
0x18001c045  call    WPP_SF_
0x18001c04a  xor     edx, edx; lpReserved
0x18001c04c  mov     rcx, r14; hRequest
0x18001c04f  call    cs:__imp_WinHttpReceiveResponse
0x18001c055  test    eax, eax
0x18001c057  jnz     loc_18001C163
0x18001c05d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001c062  mov     ebx, eax
0x18001c064  test    eax, eax
0x18001c066  jz      loc_18001C139
0x18001c06c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c073  cmp     rcx, r12
0x18001c076  jz      loc_18001C139
0x18001c07c  test    byte ptr [rcx+1Ch], 1
0x18001c080  jz      loc_18001C139
0x18001c086  mov     rcx, [rcx+10h]
0x18001c08a  lea     r9, aAsynchronouswi_3; "AsynchronousWinHTTPCallback: WinHttpRec"...
0x18001c091  mov     edx, 8Ah
0x18001c096  mov     [rsp+78h+var_58], eax
0x18001c09a  mov     r8, r13
0x18001c09d  call    WPP_SF_sd
0x18001c0a2  jmp     loc_18001C139
0x18001c0a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0ae  cmp     rcx, r12
0x18001c0b1  jz      short loc_18001C0CA
0x18001c0b3  test    byte ptr [rcx+1Ch], 80h
0x18001c0b7  jz      short loc_18001C0CA
0x18001c0b9  mov     rcx, [rcx+10h]
0x18001c0bd  mov     edx, 8Bh
0x18001c0c2  mov     r8, r13
0x18001c0c5  call    WPP_SF_
0x18001c0ca  mov     rcx, rsi; this
0x18001c0cd  call    ?HrFetchHeaders@CSsdpNotifyRequest@@QEAAJXZ; CSsdpNotifyRequest::HrFetchHeaders(void)
0x18001c0d2  mov     ebx, eax
0x18001c0d4  mov     ebp, 1
0x18001c0d9  test    eax, eax
0x18001c0db  jz      loc_18001C163
0x18001c0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0e8  cmp     rcx, r12
0x18001c0eb  jz      short loc_18001C163
0x18001c0ed  test    [rcx+1Ch], bpl
0x18001c0f1  jz      short loc_18001C163
0x18001c0f3  mov     rcx, [rcx+10h]
0x18001c0f7  lea     r9, aAsynchronouswi_1; "AsynchronousWinHTTPCallback: Failed to "...
0x18001c0fe  mov     edx, 8Ch
0x18001c103  mov     [rsp+78h+var_58], eax
0x18001c107  mov     r8, r13
0x18001c10a  call    WPP_SF_sd
0x18001c10f  jmp     short loc_18001C163
0x18001c111  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c118  cmp     rcx, r12
0x18001c11b  jz      short loc_18001C134
0x18001c11d  test    byte ptr [rcx+1Ch], 80h
0x18001c121  jz      short loc_18001C134
0x18001c123  mov     rcx, [rcx+10h]
0x18001c127  mov     edx, 8Dh
0x18001c12c  mov     r8, r13
0x18001c12f  call    WPP_SF_
0x18001c134  mov     ebx, 80004005h
0x18001c139  mov     ebp, 1
0x18001c13e  jmp     short loc_18001C163
0x18001c140  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c147  cmp     rcx, r12
0x18001c14a  jz      short loc_18001C163
0x18001c14c  test    byte ptr [rcx+1Ch], 80h
0x18001c150  jz      short loc_18001C163
0x18001c152  mov     rcx, [rcx+10h]
0x18001c156  mov     edx, 8Fh
0x18001c15b  mov     r8, r13
0x18001c15e  call    WPP_SF_
0x18001c163  mov     rcx, r15; lpCriticalSection
0x18001c166  call    cs:__imp_LeaveCriticalSection
0x18001c16c  test    ebp, ebp
0x18001c16e  jz      loc_18001C1FE
0x18001c174  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c17b  cmp     rcx, r12
0x18001c17e  jz      short loc_18001C19A
0x18001c180  test    byte ptr [rcx+1Ch], 80h
0x18001c184  jz      short loc_18001C19A
0x18001c186  mov     rcx, [rcx+10h]
0x18001c18a  mov     edx, 90h
0x18001c18f  mov     r9, rsi
0x18001c192  mov     r8, r13
0x18001c195  call    WPP_SF_q
0x18001c19a  mov     rcx, [rsi+140h]; hEvent
0x18001c1a1  mov     dword ptr [rsi+160h], 0
0x18001c1ab  mov     [rsi+15Ch], ebx
0x18001c1b1  call    cs:__imp_SetEvent
0x18001c1b7  test    eax, eax
0x18001c1b9  jnz     short loc_18001C1FE
0x18001c1bb  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001c1c0  test    eax, eax
0x18001c1c2  jz      short loc_18001C1FE
0x18001c1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1cb  cmp     rcx, r12
0x18001c1ce  jz      short loc_18001C221
0x18001c1d0  test    byte ptr [rcx+1Ch], 1
0x18001c1d4  jz      short loc_18001C205
0x18001c1d6  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001c1db  mov     edx, 91h
0x18001c1e0  lea     r9, aAsynchronouswi; "AsynchronousWinHTTPCallback: Failed to "...
0x18001c1e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1ee  mov     r8, r13
0x18001c1f1  mov     [rsp+78h+var_58], eax
0x18001c1f5  mov     rcx, [rcx+10h]
0x18001c1f9  call    WPP_SF_sd
0x18001c1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c205  cmp     rcx, r12
0x18001c208  jz      short loc_18001C221
0x18001c20a  test    byte ptr [rcx+1Ch], 80h
0x18001c20e  jz      short loc_18001C221
0x18001c210  mov     rcx, [rcx+10h]
0x18001c214  mov     edx, 92h
0x18001c219  mov     r8, r13
0x18001c21c  call    WPP_SF_
0x18001c221  add     rsp, 38h
0x18001c225  pop     r15
0x18001c227  pop     r14
0x18001c229  pop     r13
0x18001c22b  pop     r12
0x18001c22d  pop     rdi
0x18001c22e  pop     rsi
0x18001c22f  pop     rbp
0x18001c230  pop     rbx
0x18001c231  retn
```
