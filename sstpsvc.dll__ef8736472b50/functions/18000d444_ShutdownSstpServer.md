# ShutdownSstpServer

- ea: `0x18000d444`
- end: `0x18000d68e`
- name: `ShutdownSstpServer`
- size: `586`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800056e0`
- `0x1800059f0`
- `0x18000aa44`
- `0x1800158c0`

## callees

- `0x1800089dc`
- `0x180008b90`
- `0x180008c70`
- `0x18000d444`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `HTTPAPI!HttpCloseRequestQueue` at `0x18000d50a`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18000d50a`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18000d572`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18000d572`
- `HTTPAPI!HttpTerminate` at `0x18000d5b1`
- `HTTPAPI!HttpTerminate` at `0x18000d5b1`
- `HTTPAPI!HttpCloseServerSession` at `0x18000d591`
- `HTTPAPI!HttpCloseServerSession` at `0x18000d591`

## pseudocode

```c
ULONG __fastcall ShutdownSstpServer(char a1)
{
  ULONG result; // eax
  ULONG v3; // eax
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  ULONG v6; // eax
  volatile __int32 *v7; // rcx
  int v8; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v9[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString((wchar_t *)&v8, L"Entering %ws", L"ShutdownSstpServer");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v8);
  }
  if ( (a1 & 1) != 0 )
    SetSstpConfigFlag(2, 0);
  result = _InterlockedCompareExchange((volatile signed __int32 *)SstpSvcGlobals + 191, 1, 1);
  if ( result )
  {
    v3 = HttpCloseRequestQueue(*((HANDLE *)SstpSvcGlobals + 8));
    if ( v3 )
    {
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString((wchar_t *)&v8, L"Failure to close to the Request queue - %d", v3);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
            (const wchar_t *)&v8);
      }
    }
    v4 = SstpSvcGlobals;
    *((_QWORD *)SstpSvcGlobals + 8) = 0;
    HttpCloseUrlGroup(v4[7]);
    v5 = SstpSvcGlobals;
    *((_QWORD *)SstpSvcGlobals + 7) = 0;
    HttpCloseServerSession(v5[6]);
    *((_QWORD *)SstpSvcGlobals + 6) = 0;
    v6 = HttpTerminate(3u, 0);
    if ( v6 )
    {
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString((wchar_t *)&v8, L"HttpTerminate fails with error %d (%d)", v6, v6);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
            (const wchar_t *)&v8);
      }
    }
    v7 = (volatile __int32 *)SstpSvcGlobals;
    *((_DWORD *)SstpSvcGlobals + 191) = 0;
    result = _InterlockedExchange(v7 + 191, 0);
  }
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v8) = 0;
    result = FormatRRASErrorString((wchar_t *)&v8, L"LEaving %ws", L"ShutdownSstpServer");
    if ( (byte_18002E903 & 0x10) != 0 )
      return McTemplateU0z_EventWriteTransfer(
               (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
               (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
               (const wchar_t *)&v8);
  }
  return result;
}

```

## disassembly

```asm
0x18000d444  mov     [rsp-8+arg_0], rbx
0x18000d449  mov     [rsp-8+arg_8], rsi
0x18000d44e  push    rbp
0x18000d44f  lea     rbp, [rsp-730h]
0x18000d457  sub     rsp, 830h
0x18000d45e  mov     rax, cs:__security_cookie
0x18000d465  xor     rax, rsp
0x18000d468  mov     [rbp+730h+var_10], rax
0x18000d46f  mov     ebx, ecx
0x18000d471  xor     eax, eax
0x18000d473  lea     rcx, [rsp+830h+var_80C]; void *
0x18000d478  mov     [rsp+830h+var_810], eax
0x18000d47c  xor     edx, edx; Val
0x18000d47e  mov     r8d, 7FCh; Size
0x18000d484  call    memset_0
0x18000d489  test    cs:byte_18002E903, 10h
0x18000d490  jz      short loc_18000D4D2
0x18000d492  xor     eax, eax
0x18000d494  lea     r8, aShutdownsstpse; "ShutdownSstpServer"
0x18000d49b  lea     rdx, aEnteringWs; "Entering %ws"
0x18000d4a2  mov     word ptr [rsp+830h+var_810], ax
0x18000d4a7  lea     rcx, [rsp+830h+var_810]
0x18000d4ac  call    FormatRRASErrorString
0x18000d4b1  test    cs:byte_18002E903, 10h
0x18000d4b8  jz      short loc_18000D4D2
0x18000d4ba  lea     r8, [rsp+830h+var_810]
0x18000d4bf  lea     rdx, RasSSTPSvcTraceInfo
0x18000d4c6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d4cd  call    McTemplateU0z_EventWriteTransfer
0x18000d4d2  mov     esi, 1
0x18000d4d7  test    sil, bl
0x18000d4da  jz      short loc_18000D4E6
0x18000d4dc  xor     edx, edx
0x18000d4de  lea     ecx, [rsi+1]
0x18000d4e1  call    SetSstpConfigFlag
0x18000d4e6  mov     rcx, cs:SstpSvcGlobals
0x18000d4ed  mov     eax, esi
0x18000d4ef  lock cmpxchg [rcx+2FCh], esi
0x18000d4f7  test    eax, eax
0x18000d4f9  jz      loc_18000D620
0x18000d4ff  mov     rcx, cs:SstpSvcGlobals
0x18000d506  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000d50a  call    cs:__imp_HttpCloseRequestQueue
0x18000d511  nop     dword ptr [rax+rax+00h]
0x18000d516  mov     bl, 8
0x18000d518  test    eax, eax
0x18000d51a  jz      short loc_18000D55F
0x18000d51c  test    cs:byte_18002E903, bl
0x18000d522  jz      short loc_18000D55F
0x18000d524  xor     ecx, ecx
0x18000d526  lea     rdx, aFailureToClose; "Failure to close to the Request queue -"...
0x18000d52d  mov     word ptr [rsp+830h+var_810], cx
0x18000d532  mov     r8d, eax
0x18000d535  lea     rcx, [rsp+830h+var_810]
0x18000d53a  call    FormatRRASErrorString
0x18000d53f  test    cs:byte_18002E903, bl
0x18000d545  jz      short loc_18000D55F
0x18000d547  lea     r8, [rsp+830h+var_810]
0x18000d54c  lea     rdx, RasSSTPSvcTraceError
0x18000d553  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d55a  call    McTemplateU0z_EventWriteTransfer
0x18000d55f  mov     rcx, cs:SstpSvcGlobals
0x18000d566  mov     qword ptr [rcx+40h], 0
0x18000d56e  mov     rcx, [rcx+38h]; UrlGroupId
0x18000d572  call    cs:__imp_HttpCloseUrlGroup
0x18000d579  nop     dword ptr [rax+rax+00h]
0x18000d57e  mov     rcx, cs:SstpSvcGlobals
0x18000d585  mov     qword ptr [rcx+38h], 0
0x18000d58d  mov     rcx, [rcx+30h]; ServerSessionId
0x18000d591  call    cs:__imp_HttpCloseServerSession
0x18000d598  nop     dword ptr [rax+rax+00h]
0x18000d59d  mov     rax, cs:SstpSvcGlobals
0x18000d5a4  xor     edx, edx; pReserved
0x18000d5a6  lea     ecx, [rdx+3]; Flags
0x18000d5a9  mov     qword ptr [rax+30h], 0
0x18000d5b1  call    cs:__imp_HttpTerminate
0x18000d5b8  nop     dword ptr [rax+rax+00h]
0x18000d5bd  test    eax, eax
0x18000d5bf  jz      short loc_18000D607
0x18000d5c1  test    cs:byte_18002E903, bl
0x18000d5c7  jz      short loc_18000D607
0x18000d5c9  xor     ecx, ecx
0x18000d5cb  lea     rdx, aHttpterminateF; "HttpTerminate fails with error %d (%d)"
0x18000d5d2  mov     word ptr [rsp+830h+var_810], cx
0x18000d5d7  mov     r9d, eax
0x18000d5da  lea     rcx, [rsp+830h+var_810]
0x18000d5df  mov     r8d, eax
0x18000d5e2  call    FormatRRASErrorString
0x18000d5e7  test    cs:byte_18002E903, bl
0x18000d5ed  jz      short loc_18000D607
0x18000d5ef  lea     r8, [rsp+830h+var_810]
0x18000d5f4  lea     rdx, RasSSTPSvcTraceError
0x18000d5fb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d602  call    McTemplateU0z_EventWriteTransfer
0x18000d607  mov     rcx, cs:SstpSvcGlobals
0x18000d60e  xor     eax, eax
0x18000d610  mov     dword ptr [rcx+2FCh], 0
0x18000d61a  xchg    eax, [rcx+2FCh]
0x18000d620  test    cs:byte_18002E903, 10h
0x18000d627  jz      short loc_18000D669
0x18000d629  xor     eax, eax
0x18000d62b  lea     r8, aShutdownsstpse; "ShutdownSstpServer"
0x18000d632  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000d639  mov     word ptr [rsp+830h+var_810], ax
0x18000d63e  lea     rcx, [rsp+830h+var_810]
0x18000d643  call    FormatRRASErrorString
0x18000d648  test    cs:byte_18002E903, 10h
0x18000d64f  jz      short loc_18000D669
0x18000d651  lea     r8, [rsp+830h+var_810]
0x18000d656  lea     rdx, RasSSTPSvcTraceInfo
0x18000d65d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d664  call    McTemplateU0z_EventWriteTransfer
0x18000d669  mov     rcx, [rbp+730h+var_10]
0x18000d670  xor     rcx, rsp; StackCookie
0x18000d673  call    __security_check_cookie
0x18000d678  lea     r11, [rsp+830h+var_s0]
0x18000d680  mov     rbx, [r11+10h]
0x18000d684  mov     rsi, [r11+18h]
0x18000d688  mov     rsp, r11
0x18000d68b  pop     rbp
0x18000d68c  retn
```
