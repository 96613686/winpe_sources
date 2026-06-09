# ShutdownSstpServer

- ea: `0x18000c8d0`
- end: `0x18000cb01`
- name: `ShutdownSstpServer`
- size: `561`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005280`
- `0x180005560`
- `0x18000a0d4`
- `0x180014840`

## callees

- `0x18000827c`
- `0x180008360`
- `0x180008434`
- `0x18000c8d0`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `HTTPAPI!HttpCloseRequestQueue` at `0x18000c996`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18000c996`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18000c9f8`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18000c9f8`
- `HTTPAPI!HttpTerminate` at `0x18000ca2b`
- `HTTPAPI!HttpTerminate` at `0x18000ca2b`
- `HTTPAPI!HttpCloseServerSession` at `0x18000ca11`
- `HTTPAPI!HttpCloseServerSession` at `0x18000ca11`

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
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString((wchar_t *)&v8, L"Entering %ws", L"ShutdownSstpServer");
    if ( (byte_18002D803 & 0x10) != 0 )
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
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString((wchar_t *)&v8, L"Failure to close to the Request queue - %d", v3);
        if ( (byte_18002D803 & 8) != 0 )
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
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString((wchar_t *)&v8, L"HttpTerminate fails with error %d (%d)", v6, v6);
        if ( (byte_18002D803 & 8) != 0 )
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
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v8) = 0;
    result = FormatRRASErrorString((wchar_t *)&v8, L"LEaving %ws", L"ShutdownSstpServer");
    if ( (byte_18002D803 & 0x10) != 0 )
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
0x18000c8d0  mov     [rsp-8+arg_0], rbx
0x18000c8d5  mov     [rsp-8+arg_8], rsi
0x18000c8da  push    rbp
0x18000c8db  lea     rbp, [rsp-730h]
0x18000c8e3  sub     rsp, 830h
0x18000c8ea  mov     rax, cs:__security_cookie
0x18000c8f1  xor     rax, rsp
0x18000c8f4  mov     [rbp+730h+var_10], rax
0x18000c8fb  mov     ebx, ecx
0x18000c8fd  xor     eax, eax
0x18000c8ff  lea     rcx, [rsp+830h+var_80C]; void *
0x18000c904  mov     [rsp+830h+var_810], eax
0x18000c908  xor     edx, edx; Val
0x18000c90a  mov     r8d, 7FCh; Size
0x18000c910  call    memset_0
0x18000c915  test    cs:byte_18002D803, 10h
0x18000c91c  jz      short loc_18000C95E
0x18000c91e  xor     eax, eax
0x18000c920  lea     r8, aShutdownsstpse; "ShutdownSstpServer"
0x18000c927  lea     rdx, aEnteringWs; "Entering %ws"
0x18000c92e  mov     word ptr [rsp+830h+var_810], ax
0x18000c933  lea     rcx, [rsp+830h+var_810]
0x18000c938  call    FormatRRASErrorString
0x18000c93d  test    cs:byte_18002D803, 10h
0x18000c944  jz      short loc_18000C95E
0x18000c946  lea     r8, [rsp+830h+var_810]
0x18000c94b  lea     rdx, RasSSTPSvcTraceInfo
0x18000c952  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c959  call    McTemplateU0z_EventWriteTransfer
0x18000c95e  mov     esi, 1
0x18000c963  test    sil, bl
0x18000c966  jz      short loc_18000C972
0x18000c968  xor     edx, edx
0x18000c96a  lea     ecx, [rsi+1]
0x18000c96d  call    SetSstpConfigFlag
0x18000c972  mov     rcx, cs:SstpSvcGlobals
0x18000c979  mov     eax, esi
0x18000c97b  lock cmpxchg [rcx+2FCh], esi
0x18000c983  test    eax, eax
0x18000c985  jz      loc_18000CA94
0x18000c98b  mov     rcx, cs:SstpSvcGlobals
0x18000c992  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000c996  call    cs:__imp_HttpCloseRequestQueue
0x18000c99c  mov     bl, 8
0x18000c99e  test    eax, eax
0x18000c9a0  jz      short loc_18000C9E5
0x18000c9a2  test    cs:byte_18002D803, bl
0x18000c9a8  jz      short loc_18000C9E5
0x18000c9aa  xor     ecx, ecx
0x18000c9ac  lea     rdx, aFailureToClose; "Failure to close to the Request queue -"...
0x18000c9b3  mov     word ptr [rsp+830h+var_810], cx
0x18000c9b8  mov     r8d, eax
0x18000c9bb  lea     rcx, [rsp+830h+var_810]
0x18000c9c0  call    FormatRRASErrorString
0x18000c9c5  test    cs:byte_18002D803, bl
0x18000c9cb  jz      short loc_18000C9E5
0x18000c9cd  lea     r8, [rsp+830h+var_810]
0x18000c9d2  lea     rdx, RasSSTPSvcTraceError
0x18000c9d9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c9e0  call    McTemplateU0z_EventWriteTransfer
0x18000c9e5  mov     rcx, cs:SstpSvcGlobals
0x18000c9ec  mov     qword ptr [rcx+40h], 0
0x18000c9f4  mov     rcx, [rcx+38h]; UrlGroupId
0x18000c9f8  call    cs:__imp_HttpCloseUrlGroup
0x18000c9fe  mov     rcx, cs:SstpSvcGlobals
0x18000ca05  mov     qword ptr [rcx+38h], 0
0x18000ca0d  mov     rcx, [rcx+30h]; ServerSessionId
0x18000ca11  call    cs:__imp_HttpCloseServerSession
0x18000ca17  mov     rax, cs:SstpSvcGlobals
0x18000ca1e  xor     edx, edx; pReserved
0x18000ca20  lea     ecx, [rdx+3]; Flags
0x18000ca23  mov     qword ptr [rax+30h], 0
0x18000ca2b  call    cs:__imp_HttpTerminate
0x18000ca31  test    eax, eax
0x18000ca33  jz      short loc_18000CA7B
0x18000ca35  test    cs:byte_18002D803, bl
0x18000ca3b  jz      short loc_18000CA7B
0x18000ca3d  xor     ecx, ecx
0x18000ca3f  lea     rdx, aHttpterminateF; "HttpTerminate fails with error %d (%d)"
0x18000ca46  mov     word ptr [rsp+830h+var_810], cx
0x18000ca4b  mov     r9d, eax
0x18000ca4e  lea     rcx, [rsp+830h+var_810]
0x18000ca53  mov     r8d, eax
0x18000ca56  call    FormatRRASErrorString
0x18000ca5b  test    cs:byte_18002D803, bl
0x18000ca61  jz      short loc_18000CA7B
0x18000ca63  lea     r8, [rsp+830h+var_810]
0x18000ca68  lea     rdx, RasSSTPSvcTraceError
0x18000ca6f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ca76  call    McTemplateU0z_EventWriteTransfer
0x18000ca7b  mov     rcx, cs:SstpSvcGlobals
0x18000ca82  xor     eax, eax
0x18000ca84  mov     dword ptr [rcx+2FCh], 0
0x18000ca8e  xchg    eax, [rcx+2FCh]
0x18000ca94  test    cs:byte_18002D803, 10h
0x18000ca9b  jz      short loc_18000CADD
0x18000ca9d  xor     eax, eax
0x18000ca9f  lea     r8, aShutdownsstpse; "ShutdownSstpServer"
0x18000caa6  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000caad  mov     word ptr [rsp+830h+var_810], ax
0x18000cab2  lea     rcx, [rsp+830h+var_810]
0x18000cab7  call    FormatRRASErrorString
0x18000cabc  test    cs:byte_18002D803, 10h
0x18000cac3  jz      short loc_18000CADD
0x18000cac5  lea     r8, [rsp+830h+var_810]
0x18000caca  lea     rdx, RasSSTPSvcTraceInfo
0x18000cad1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cad8  call    McTemplateU0z_EventWriteTransfer
0x18000cadd  mov     rcx, [rbp+730h+var_10]
0x18000cae4  xor     rcx, rsp; StackCookie
0x18000cae7  call    __security_check_cookie
0x18000caec  lea     r11, [rsp+830h+var_s0]
0x18000caf4  mov     rbx, [r11+10h]
0x18000caf8  mov     rsi, [r11+18h]
0x18000cafc  mov     rsp, r11
0x18000caff  pop     rbp
0x18000cb00  retn
```
