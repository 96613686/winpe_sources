# LocalInterfaceOnlySecCallback(void *,void *)

- ea: `0x1800562a0`
- end: `0x18005684b`
- name: `?LocalInterfaceOnlySecCallback@@YAJPEAX0@Z`
- size: `1451`
- prototype: `__int64 __fastcall(struct _GUID *, RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000a130`
- `0x18001a374`
- `0x18001c624`
- `0x18001ecf0`
- `0x18002f3e0`
- `0x180054bc0`
- `0x1800562a0`
- `0x180075b1c`
- `0x18009dfb4`
- `0x1800b7ac0`
- `0x1800b7e90`
- `0x180112d78`

## import_xrefs

- `RPCRT4!I_RpcBindingInqTransportType` at `0x1800562f4`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x1800562f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800565d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005681a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800565d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005681a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005641d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180056632`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005641d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180056632`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056441`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056452`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056656`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056667`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056441`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056452`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056656`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056667`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800564c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800566db`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800564c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800566db`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180056539`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180056756`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180056539`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180056756`

## string_xrefs

- `0x18005630c`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x180056361`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x1800563ef`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x180056503`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18005671d`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x180056515`: `DCOMSCM LocalSecurityCallback AccessCheck LOCALEXECUTE IID:%ws SID:%ws %!HRESULT!`
- `0x18005672f`: `DCOMSCM LocalSecurityCallback AccessCheck LOCALACTIVATE IID:%ws SID:%ws %!HRESULT!`

## pseudocode

```c
__int64 __fastcall LocalInterfaceOnlySecCallback(struct _GUID *a1, RPC_BINDING_HANDLE BindingHandle)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  CGuidStr *v6; // rax
  unsigned int TokenForRPCClient; // eax
  HANDLE *v9; // rsi
  CSecDescriptor *v10; // rbx
  BOOL v11; // r14d
  CSecDescriptor *v12; // r15
  CGuidStr *v13; // rax
  __int64 v14; // r11
  HANDLE v15; // rcx
  CSecDescriptor *v16; // r15
  BOOL v17; // r13d
  struct _GUID *v18; // r15
  CGuidStr *v19; // rax
  __int64 v20; // r11
  HANDLE v21; // rcx
  __int64 v22; // [rsp+20h] [rbp-99h]
  LPWSTR StringSid; // [rsp+50h] [rbp-69h] BYREF
  unsigned int Type; // [rsp+58h] [rbp-61h] BYREF
  __int64 Buf2; // [rsp+60h] [rbp-59h] BYREF
  int v26; // [rsp+68h] [rbp-51h]
  int v27; // [rsp+6Ch] [rbp-4Dh]
  struct _GUID *v28; // [rsp+70h] [rbp-49h]
  RPC_BINDING_HANDLE v29; // [rsp+78h] [rbp-41h]
  _BYTE v30[80]; // [rsp+80h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v29 = BindingHandle;
  v28 = a1;
  Buf2 = 310;
  v26 = 192;
  v27 = 1174405120;
  Type = 0;
  v4 = I_RpcBindingInqTransportType(BindingHandle, &Type);
  if ( v4 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x652,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
      (const char *)v4,
      v22);
LABEL_3:
    v5 = 5;
    if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = CGuidStr::CGuidStr((CGuidStr *)v30, a1);
      LODWORD(v22) = 0;
      ComTraceMessage(
        5,
        "onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
        "LocalInterfaceOnlySecCallback",
        1620,
        v22,
        L"IID:%ws %!WINERROR!",
        v6,
        5);
    }
    return v5;
  }
  if ( Type != 4 )
    goto LABEL_3;
  StringSid = 0;
  TokenForRPCClient = LookupOrCreateTokenForRPCClient(BindingHandle, 0, (struct CToken **)&StringSid, 0);
  v9 = (HANDLE *)StringSid;
  v5 = TokenForRPCClient;
  if ( TokenForRPCClient )
  {
    v10 = 0;
    v11 = 1;
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x65D,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
      (const char *)TokenForRPCClient,
      v22);
  }
  else
  {
    v5 = 5;
    AcquireSRWLockShared(&gpClientLock);
    v12 = gpDefaultAccessRestrictionsSD;
    if ( gpDefaultAccessRestrictionsSD )
    {
      _InterlockedIncrement((volatile signed __int32 *)gpDefaultAccessRestrictionsSD + 3);
      ReleaseSRWLockShared(&gpClientLock);
      v10 = v12;
    }
    else
    {
      ReleaseSRWLockShared(&gpClientLock);
      v10 = gpNoRegAccessRestrictionsSD;
    }
    v11 = v12 != 0;
    if ( (unsigned int)CheckForAccess(v9[9], *(PSECURITY_DESCRIPTOR *)v10, 2u, 0) )
    {
      if ( v12 && _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 3, 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)v10 )
        {
          HeapFree(g_hHeap, 0, *(LPVOID *)v10);
          *(_QWORD *)v10 = 0;
        }
        operator delete(v10, 0x10u);
      }
      v11 = 1;
      v10 = 0;
      if ( gfCheckActivationSecurity && !memcmp_0(a1, &Buf2, 0x10u) )
      {
        AcquireSRWLockShared(&gpClientLock);
        v16 = gpDefaultLaunchRestrictionsSD;
        if ( gpDefaultLaunchRestrictionsSD )
        {
          _InterlockedIncrement((volatile signed __int32 *)gpDefaultLaunchRestrictionsSD + 3);
          ReleaseSRWLockShared(&gpClientLock);
          v10 = v16;
        }
        else
        {
          ReleaseSRWLockShared(&gpClientLock);
          v10 = gpNoRegLaunchRestrictionsSD;
        }
        v17 = v16 != 0;
        if ( !(unsigned int)CheckForAccess(v9[9], *(PSECURITY_DESCRIPTOR *)v10, 8u, 0) )
        {
          if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            StringSid = 0;
            ConvertSidToStringSidW((char *)v9 + 156, &StringSid);
            v18 = v28;
            v19 = CGuidStr::CGuidStr((CGuidStr *)v30, v28);
            LODWORD(v22) = 0;
            ComTraceMessage(
              2147942405LL,
              "onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
              "LocalInterfaceOnlySecCallback",
              1683,
              v22,
              L"DCOMSCM LocalSecurityCallback AccessCheck LOCALACTIVATE IID:%ws SID:%ws %!HRESULT!",
              v19,
              v20,
              -2147024891);
            if ( StringSid )
              LocalFree(StringSid);
          }
          else
          {
            v18 = v28;
          }
          v21 = v9[9];
          LODWORD(StringSid) = 0;
          IsTokenBoolPresent(v21, TokenIsAppContainer, (int *)&StringSid);
          if ( gdwCallFailureLoggingLevel == 1 || (_DWORD)StringSid )
            LogAccessFailed(v29, v9, 0, 0, v18, 18219, v9[9], 0, 1, 7);
          v11 = v17;
          goto LABEL_46;
        }
        v11 = v16 != 0;
      }
      v5 = 0;
    }
    else
    {
      if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        StringSid = 0;
        ConvertSidToStringSidW((char *)v9 + 156, &StringSid);
        v13 = CGuidStr::CGuidStr((CGuidStr *)v30, a1);
        LODWORD(v22) = 0;
        ComTraceMessage(
          2147942405LL,
          "onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
          "LocalInterfaceOnlySecCallback",
          1647,
          v22,
          L"DCOMSCM LocalSecurityCallback AccessCheck LOCALEXECUTE IID:%ws SID:%ws %!HRESULT!",
          v13,
          v14,
          -2147024891);
        if ( StringSid )
          LocalFree(StringSid);
      }
      v15 = v9[9];
      LODWORD(StringSid) = 0;
      IsTokenBoolPresent(v15, TokenIsAppContainer, (int *)&StringSid);
      if ( gdwCallFailureLoggingLevel == 1 || (_DWORD)StringSid )
        LogAccessFailed(v29, v9, 0, 0, a1, 18219, v9[9], 0, 2, 7);
    }
  }
LABEL_46:
  if ( v9 )
    CToken::Release((CToken *)v9);
  if ( v10 && v11 && _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 3, 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v10 )
    {
      HeapFree(g_hHeap, 0, *(LPVOID *)v10);
      *(_QWORD *)v10 = 0;
    }
    operator delete(v10, 0x10u);
  }
  return v5;
}

```

## disassembly

```asm
0x1800562a0  push    rbp
0x1800562a2  push    rbx
0x1800562a3  push    rdi
0x1800562a4  push    r13
0x1800562a6  push    r15
0x1800562a8  lea     rbp, [rsp-37h]
0x1800562ad  sub     rsp, 0F0h
0x1800562b4  mov     rax, cs:__security_cookie
0x1800562bb  xor     rax, rsp
0x1800562be  mov     [rbp+57h+var_40], rax
0x1800562c2  mov     rbx, rdx
0x1800562c5  mov     [rbp+57h+var_98], rdx
0x1800562c9  mov     r13, rcx
0x1800562cc  mov     [rbp+57h+var_A0], rcx
0x1800562d0  xor     r15d, r15d
0x1800562d3  mov     [rbp+57h+Buf2], 136h
0x1800562db  mov     rcx, rbx; Binding
0x1800562de  mov     [rbp+57h+var_A8], 0C0h
0x1800562e5  lea     rdx, [rbp+57h+Type]; Type
0x1800562e9  mov     [rbp+57h+var_A4], 46000000h
0x1800562f0  mov     [rbp+57h+Type], r15d
0x1800562f4  call    cs:__imp_I_RpcBindingInqTransportType
0x1800562fb  nop     dword ptr [rax+rax+00h]
0x180056300  test    eax, eax
0x180056302  jz      loc_1800563A4
0x180056308  mov     rcx, [rbp+5Fh]; this
0x18005630c  lea     r8, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180056313  mov     r9d, eax; char *
0x180056316  mov     edx, 652h; void *
0x18005631b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180056320  mov     eax, cs:dword_1801574B8
0x180056326  mov     edi, 5
0x18005632b  test    eax, eax
0x18005632d  jnz     short loc_180056345
0x18005632f  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180056336  jz      short loc_180056386
0x180056338  mov     rax, cs:WPP_GLOBAL_Control
0x18005633f  test    byte ptr [rax+1Ch], 1
0x180056343  jz      short loc_180056386
0x180056345  mov     rdx, r13; struct _GUID *
0x180056348  lea     rcx, [rbp+57h+var_90]; this
0x18005634c  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180056351  mov     dword ptr [rsp+110h+var_D8], edi
0x180056355  lea     r8, aLocalinterface; "LocalInterfaceOnlySecCallback"
0x18005635c  mov     [rsp+110h+var_E0], rax
0x180056361  lea     rdx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180056368  lea     rax, aIidWsWinerror; "IID:%ws %!WINERROR!"
0x18005636f  mov     r9d, 654h
0x180056375  mov     [rsp+110h+var_E8], rax
0x18005637a  mov     ecx, edi
0x18005637c  mov     dword ptr [rsp+110h+var_F0], r15d
0x180056381  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180056386  mov     eax, edi
0x180056388  mov     rcx, [rbp+57h+var_40]
0x18005638c  xor     rcx, rsp; StackCookie
0x18005638f  call    __security_check_cookie
0x180056394  add     rsp, 0F0h
0x18005639b  pop     r15
0x18005639d  pop     r13
0x18005639f  pop     rdi
0x1800563a0  pop     rbx
0x1800563a1  pop     rbp
0x1800563a2  retn
0x1800563a4  cmp     [rbp+57h+Type], 4
0x1800563a8  jnz     loc_180056320
0x1800563ae  mov     [rsp+110h+arg_10], rsi
0x1800563b6  lea     r8, [rbp+57h+StringSid]; struct CToken **
0x1800563ba  mov     [rsp+110h+var_28], r12
0x1800563c2  xor     r9d, r9d; int *
0x1800563c5  xor     edx, edx; int
0x1800563c7  mov     [rsp+110h+var_30], r14
0x1800563cf  mov     rcx, rbx; BindingHandle
0x1800563d2  mov     [rbp+57h+StringSid], r15
0x1800563d6  call    ?LookupOrCreateTokenForRPCClient@@YAJPEAXHPEAPEAVCToken@@PEAH@Z; LookupOrCreateTokenForRPCClient(void *,int,CToken * *,int *)
0x1800563db  mov     rsi, [rbp+57h+StringSid]
0x1800563df  mov     edi, eax
0x1800563e1  mov     r12d, 0FFFFFFFFh
0x1800563e7  test    eax, eax
0x1800563e9  jz      short loc_180056411
0x1800563eb  mov     rcx, [rbp+5Fh]; this
0x1800563ef  lea     r8, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800563f6  mov     r9d, eax; char *
0x1800563f9  mov     edx, 65Dh; void *
0x1800563fe  mov     rbx, r15
0x180056401  mov     r14d, 1
0x180056407  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005640c  jmp     loc_1800567DE
0x180056411  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180056418  mov     edi, 5
0x18005641d  call    cs:__imp_AcquireSRWLockShared
0x180056424  nop     dword ptr [rax+rax+00h]
0x180056429  mov     r15, cs:?gpDefaultAccessRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpDefaultAccessRestrictionsSD
0x180056430  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180056437  test    r15, r15
0x18005643a  jz      short loc_180056452
0x18005643c  lock inc dword ptr [r15+0Ch]
0x180056441  call    cs:__imp_ReleaseSRWLockShared
0x180056448  nop     dword ptr [rax+rax+00h]
0x18005644d  mov     rbx, r15
0x180056450  jmp     short loc_180056465
0x180056452  call    cs:__imp_ReleaseSRWLockShared
0x180056459  nop     dword ptr [rax+rax+00h]
0x18005645e  mov     rbx, cs:?gpNoRegAccessRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpNoRegAccessRestrictionsSD
0x180056465  mov     rdx, [rbx]; pSecurityDescriptor
0x180056468  xor     r14d, r14d
0x18005646b  mov     rcx, [rsi+48h]; ClientToken
0x18005646f  test    r15, r15
0x180056472  mov     r8d, 2; unsigned int
0x180056478  setnz   r14b
0x18005647c  xor     r9d, r9d; void *
0x18005647f  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x180056484  test    eax, eax
0x180056486  jnz     loc_1800565B5
0x18005648c  mov     eax, cs:dword_1801574B8
0x180056492  test    eax, eax
0x180056494  jnz     short loc_1800564B3
0x180056496  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18005649c  jz      loc_180056547
0x1800564a2  mov     rax, cs:WPP_GLOBAL_Control
0x1800564a9  test    byte ptr [rax+1Ch], 1
0x1800564ad  jz      loc_180056547
0x1800564b3  xor     r15d, r15d
0x1800564b6  lea     rcx, [rsi+9Ch]; Sid
0x1800564bd  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800564c1  mov     [rbp+57h+StringSid], r15
0x1800564c5  call    cs:__imp_ConvertSidToStringSidW
0x1800564cc  nop     dword ptr [rax+rax+00h]
0x1800564d1  mov     rax, [rbp+57h+StringSid]
0x1800564d5  lea     r11, Class
0x1800564dc  test    rax, rax
0x1800564df  lea     rcx, [rbp+57h+var_90]; this
0x1800564e3  mov     rdx, r13; struct _GUID *
0x1800564e6  cmovnz  r11, rax
0x1800564ea  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800564ef  mov     [rsp+110h+var_D0], 80070005h
0x1800564f7  lea     r8, aLocalinterface; "LocalInterfaceOnlySecCallback"
0x1800564fe  mov     [rsp+110h+var_D8], r11
0x180056503  lea     rdx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18005650a  mov     [rsp+110h+var_E0], rax
0x18005650f  mov     r9d, 66Fh
0x180056515  lea     rax, aDcomscmLocalse; "DCOMSCM LocalSecurityCallback AccessChe"...
0x18005651c  mov     ecx, 80070005h
0x180056521  mov     [rsp+110h+var_E8], rax
0x180056526  mov     dword ptr [rsp+110h+var_F0], r15d
0x18005652b  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180056530  mov     rcx, [rbp+57h+StringSid]; hMem
0x180056534  test    rcx, rcx
0x180056537  jz      short loc_18005654A
0x180056539  call    cs:__imp_LocalFree
0x180056540  nop     dword ptr [rax+rax+00h]
0x180056545  jmp     short loc_18005654A
0x180056547  xor     r15d, r15d
0x18005654a  mov     rcx, [rsi+48h]; void *
0x18005654e  lea     r8, [rbp+57h+StringSid]; int *
0x180056552  mov     edx, 1Dh; enum _TOKEN_INFORMATION_CLASS
0x180056557  mov     dword ptr [rbp+57h+StringSid], r15d
0x18005655b  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x180056560  cmp     cs:?gdwCallFailureLoggingLevel@@3KA, 1; ulong gdwCallFailureLoggingLevel
0x180056567  jz      short loc_180056573
0x180056569  cmp     dword ptr [rbp+57h+StringSid], 0
0x18005656d  jz      loc_1800567DE
0x180056573  mov     rax, [rsi+48h]
0x180056577  xor     r9d, r9d
0x18005657a  mov     rcx, [rbp+57h+var_98]
0x18005657e  xor     r8d, r8d
0x180056581  mov     [rsp+110h+var_C8], 7
0x180056589  mov     rdx, rsi
0x18005658c  mov     [rsp+110h+var_D0], 2
0x180056594  mov     dword ptr [rsp+110h+var_D8], r15d
0x180056599  mov     [rsp+110h+var_E0], rax
0x18005659e  mov     dword ptr [rsp+110h+var_E8], 472Bh
0x1800565a6  mov     [rsp+110h+var_F0], r13
0x1800565ab  call    ?LogAccessFailed@@YAXPEAXPEAUIUserToken@@PEAUHSTRING__@@PEAU_GUID@@3K0HW4tagEventLogModes@@W4tagEventLogSD@@@Z; LogAccessFailed(void *,IUserToken *,HSTRING__ *,_GUID *,_GUID *,ulong,void *,int,tagEventLogModes,tagEventLogSD)
0x1800565b0  jmp     loc_1800567DE
0x1800565b5  test    r15, r15
0x1800565b8  jz      short loc_1800565F8
0x1800565ba  mov     eax, r12d
0x1800565bd  lock xadd [rbx+0Ch], eax
0x1800565c2  cmp     eax, 1
0x1800565c5  jnz     short loc_1800565F8
0x1800565c7  mov     r8, [rbx]; lpMem
0x1800565ca  test    r8, r8
0x1800565cd  jz      short loc_1800565EB
0x1800565cf  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800565d6  xor     edx, edx; dwFlags
0x1800565d8  call    cs:__imp_HeapFree
0x1800565df  nop     dword ptr [rax+rax+00h]
0x1800565e4  mov     qword ptr [rbx], 0
0x1800565eb  mov     edx, 10h; unsigned __int64
0x1800565f0  mov     rcx, rbx; void *
0x1800565f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800565f8  xor     r15d, r15d
0x1800565fb  mov     r14d, 1
0x180056601  cmp     cs:?gfCheckActivationSecurity@@3HA, r15d; int gfCheckActivationSecurity
0x180056608  mov     ebx, r15d
0x18005660b  jz      loc_1800567DB
0x180056611  mov     r8d, 10h; Size
0x180056617  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18005661b  mov     rcx, r13; Buf1
0x18005661e  call    memcmp_0
0x180056623  test    eax, eax
0x180056625  jnz     loc_1800567DB
0x18005662b  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180056632  call    cs:__imp_AcquireSRWLockShared
0x180056639  nop     dword ptr [rax+rax+00h]
0x18005663e  mov     r15, cs:?gpDefaultLaunchRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpDefaultLaunchRestrictionsSD
0x180056645  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18005664c  test    r15, r15
0x18005664f  jz      short loc_180056667
0x180056651  lock inc dword ptr [r15+0Ch]
0x180056656  call    cs:__imp_ReleaseSRWLockShared
0x18005665d  nop     dword ptr [rax+rax+00h]
0x180056662  mov     rbx, r15
0x180056665  jmp     short loc_18005667A
0x180056667  call    cs:__imp_ReleaseSRWLockShared
0x18005666e  nop     dword ptr [rax+rax+00h]
0x180056673  mov     rbx, cs:?gpNoRegLaunchRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpNoRegLaunchRestrictionsSD
0x18005667a  mov     rdx, [rbx]; pSecurityDescriptor
0x18005667d  xor     r13d, r13d
0x180056680  mov     rcx, [rsi+48h]; ClientToken
0x180056684  test    r15, r15
0x180056687  mov     r8d, 8; unsigned int
0x18005668d  setnz   r13b
0x180056691  xor     r9d, r9d; void *
0x180056694  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x180056699  test    eax, eax
0x18005669b  jnz     loc_1800567D5
0x1800566a1  mov     eax, cs:dword_1801574B8
0x1800566a7  test    eax, eax
0x1800566a9  jnz     short loc_1800566C8
0x1800566ab  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800566b1  jz      loc_180056764
0x1800566b7  mov     rax, cs:WPP_GLOBAL_Control
0x1800566be  test    [rax+1Ch], r14b
0x1800566c2  jz      loc_180056764
0x1800566c8  lea     rcx, [rsi+9Ch]; Sid
0x1800566cf  mov     [rbp+57h+StringSid], 0
0x1800566d7  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800566db  call    cs:__imp_ConvertSidToStringSidW
0x1800566e2  nop     dword ptr [rax+rax+00h]
0x1800566e7  mov     rax, [rbp+57h+StringSid]
0x1800566eb  lea     r11, Class
0x1800566f2  mov     r15, [rbp+57h+var_A0]
0x1800566f6  lea     rcx, [rbp+57h+var_90]; this
0x1800566fa  test    rax, rax
0x1800566fd  mov     rdx, r15; struct _GUID *
0x180056700  cmovnz  r11, rax
0x180056704  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180056709  mov     [rsp+110h+var_D0], 80070005h
0x180056711  lea     r8, aLocalinterface; "LocalInterfaceOnlySecCallback"
0x180056718  mov     [rsp+110h+var_D8], r11
0x18005671d  lea     rdx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180056724  mov     [rsp+110h+var_E0], rax
0x180056729  mov     r9d, 693h
0x18005672f  lea     rax, aDcomscmLocalse_0; "DCOMSCM LocalSecurityCallback AccessChe"...
0x180056736  mov     ecx, 80070005h
0x18005673b  mov     [rsp+110h+var_E8], rax
0x180056740  mov     dword ptr [rsp+110h+var_F0], 0
0x180056748  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18005674d  mov     rcx, [rbp+57h+StringSid]; hMem
0x180056751  test    rcx, rcx
0x180056754  jz      short loc_180056768
0x180056756  call    cs:__imp_LocalFree
0x18005675d  nop     dword ptr [rax+rax+00h]
0x180056762  jmp     short loc_180056768
0x180056764  mov     r15, [rbp+57h+var_A0]
0x180056768  mov     rcx, [rsi+48h]; void *
0x18005676c  lea     r8, [rbp+57h+StringSid]; int *
0x180056770  mov     edx, 1Dh; enum _TOKEN_INFORMATION_CLASS
0x180056775  mov     dword ptr [rbp+57h+StringSid], 0
0x18005677c  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x180056781  cmp     cs:?gdwCallFailureLoggingLevel@@3KA, r14d; ulong gdwCallFailureLoggingLevel
0x180056788  jz      short loc_180056790
0x18005678a  cmp     dword ptr [rbp+57h+StringSid], 0
0x18005678e  jz      short loc_1800567CD
0x180056790  mov     rax, [rsi+48h]
0x180056794  xor     r9d, r9d
0x180056797  mov     rcx, [rbp+57h+var_98]
0x18005679b  xor     r8d, r8d
0x18005679e  mov     [rsp+110h+var_C8], 7
0x1800567a6  mov     rdx, rsi
0x1800567a9  mov     [rsp+110h+var_D0], r14d
0x1800567ae  mov     dword ptr [rsp+110h+var_D8], 0
0x1800567b6  mov     [rsp+110h+var_E0], rax
0x1800567bb  mov     dword ptr [rsp+110h+var_E8], 472Bh
0x1800567c3  mov     [rsp+110h+var_F0], r15
0x1800567c8  call    ?LogAccessFailed@@YAXPEAXPEAUIUserToken@@PEAUHSTRING__@@PEAU_GUID@@3K0HW4tagEventLogModes@@W4tagEventLogSD@@@Z; LogAccessFailed(void *,IUserToken *,HSTRING__ *,_GUID *,_GUID *,ulong,void *,int,tagEventLogModes,tagEventLogSD)
0x1800567cd  mov     r14d, r13d
0x1800567d0  xor     r15d, r15d
0x1800567d3  jmp     short loc_1800567DE
0x1800567d5  mov     r14d, r13d
0x1800567d8  xor     r15d, r15d
0x1800567db  mov     edi, r15d
0x1800567de  test    rsi, rsi
0x1800567e1  jz      short loc_1800567EB
0x1800567e3  mov     rcx, rsi; this
0x1800567e6  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x1800567eb  mov     rsi, [rsp+110h+arg_10]
0x1800567f3  test    rbx, rbx
0x1800567f6  jz      short loc_180056836
  ... truncated ...
```
