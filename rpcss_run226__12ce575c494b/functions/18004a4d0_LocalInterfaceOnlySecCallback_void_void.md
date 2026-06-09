# LocalInterfaceOnlySecCallback(void *,void *)

- ea: `0x18004a4d0`
- end: `0x18004aa2c`
- name: `?LocalInterfaceOnlySecCallback@@YAJPEAX0@Z`
- size: `1372`
- prototype: `__int64 __fastcall(struct _GUID *, RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180009700`
- `0x180016160`
- `0x180018344`
- `0x1800250b0`
- `0x1800297e0`
- `0x180048bf0`
- `0x18004a4d0`
- `0x180071294`
- `0x1800989b0`
- `0x1800b27e0`
- `0x1800b2bb0`
- `0x18010a078`

## import_xrefs

- `RPCRT4!I_RpcBindingInqTransportType` at `0x18004a524`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x18004a524`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a7e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a7e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004a646`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004a837`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004a646`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004a837`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a664`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a66f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a855`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a860`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a664`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a66f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a855`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a860`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004a6dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004a8ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004a6dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004a8ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004a74a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004a943`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004a74a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004a943`

## string_xrefs

- `0x18004a536`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18004a58b`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18004a618`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18004a714`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18004a90a`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18004a91c`: `DCOMSCM LocalSecurityCallback AccessCheck LOCALACTIVATE IID:%ws SID:%ws %!HRESULT!`
- `0x18004a726`: `DCOMSCM LocalSecurityCallback AccessCheck LOCALEXECUTE IID:%ws SID:%ws %!HRESULT!`

## pseudocode

```c
__int64 __fastcall LocalInterfaceOnlySecCallback(struct _GUID *a1, RPC_BINDING_HANDLE BindingHandle)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  unsigned int TokenForRPCClient; // eax
  HANDLE *v8; // rsi
  CSecDescriptor *v9; // rbx
  BOOL v10; // r14d
  CSecDescriptor *v11; // r15
  int v12; // r11^4
  HANDLE v13; // rcx
  CSecDescriptor *v14; // r15
  BOOL v15; // r13d
  struct _GUID *v16; // r15
  int v17; // r11^4
  HANDLE v18; // rcx
  unsigned int v19; // [rsp+20h] [rbp-99h]
  const wchar_t *v20; // [rsp+28h] [rbp-91h]
  __int64 v21; // [rsp+38h] [rbp-81h]
  LPWSTR StringSid; // [rsp+50h] [rbp-69h] BYREF
  unsigned int Type; // [rsp+58h] [rbp-61h] BYREF
  __int64 Buf2; // [rsp+60h] [rbp-59h] BYREF
  int v25; // [rsp+68h] [rbp-51h]
  int v26; // [rsp+6Ch] [rbp-4Dh]
  struct _GUID *v27; // [rsp+70h] [rbp-49h]
  RPC_BINDING_HANDLE v28; // [rsp+78h] [rbp-41h]
  _BYTE v29[80]; // [rsp+80h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v28 = BindingHandle;
  v27 = a1;
  Buf2 = 310;
  v25 = 192;
  v26 = 1174405120;
  Type = 0;
  v4 = I_RpcBindingInqTransportType(BindingHandle, &Type);
  if ( v4 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x652,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
      (const char *)v4,
      v19);
LABEL_3:
    v5 = 5;
    if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      CGuidStr::CGuidStr((CGuidStr *)v29, a1);
      ComTraceMessage(5, "onecore\\com\\combase\\rpcss\\olescm\\security.cxx", "LocalInterfaceOnlySecCallback", 1620);
    }
    return v5;
  }
  if ( Type != 4 )
    goto LABEL_3;
  StringSid = 0;
  TokenForRPCClient = LookupOrCreateTokenForRPCClient(BindingHandle, 0, (struct CToken **)&StringSid, 0);
  v8 = (HANDLE *)StringSid;
  v5 = TokenForRPCClient;
  if ( TokenForRPCClient )
  {
    v9 = 0;
    v10 = 1;
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x65D,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
      (const char *)TokenForRPCClient,
      v19);
  }
  else
  {
    v5 = 5;
    AcquireSRWLockShared(&gpClientLock);
    v11 = gpDefaultAccessRestrictionsSD;
    if ( gpDefaultAccessRestrictionsSD )
    {
      _InterlockedIncrement((volatile signed __int32 *)gpDefaultAccessRestrictionsSD + 3);
      ReleaseSRWLockShared(&gpClientLock);
      v9 = v11;
    }
    else
    {
      ReleaseSRWLockShared(&gpClientLock);
      v9 = gpNoRegAccessRestrictionsSD;
    }
    v10 = v11 != 0;
    if ( (unsigned int)CheckForAccess(v8[9], *(PSECURITY_DESCRIPTOR *)v9, 2u, 0) )
    {
      if ( v11 && _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)v9 )
        {
          HeapFree(g_hHeap, 0, *(LPVOID *)v9);
          *(_QWORD *)v9 = 0;
        }
        operator delete(v9, 0x10u);
      }
      v10 = 1;
      v9 = 0;
      if ( gfCheckActivationSecurity && !memcmp_0(a1, &Buf2, 0x10u) )
      {
        AcquireSRWLockShared(&gpClientLock);
        v14 = gpDefaultLaunchRestrictionsSD;
        if ( gpDefaultLaunchRestrictionsSD )
        {
          _InterlockedIncrement((volatile signed __int32 *)gpDefaultLaunchRestrictionsSD + 3);
          ReleaseSRWLockShared(&gpClientLock);
          v9 = v14;
        }
        else
        {
          ReleaseSRWLockShared(&gpClientLock);
          v9 = gpNoRegLaunchRestrictionsSD;
        }
        v15 = v14 != 0;
        if ( !(unsigned int)CheckForAccess(v8[9], *(PSECURITY_DESCRIPTOR *)v9, 8u, 0) )
        {
          if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            StringSid = 0;
            ConvertSidToStringSidW((char *)v8 + 156, &StringSid);
            v16 = v27;
            CGuidStr::CGuidStr((CGuidStr *)v29, v27);
            HIDWORD(v21) = v17;
            v20 = L"DCOMSCM LocalSecurityCallback AccessCheck LOCALACTIVATE IID:%ws SID:%ws %!HRESULT!";
            ComTraceMessage(
              2147942405LL,
              "onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
              "LocalInterfaceOnlySecCallback",
              1683);
            if ( StringSid )
              LocalFree(StringSid);
          }
          else
          {
            v16 = v27;
          }
          v18 = v8[9];
          LODWORD(StringSid) = 0;
          IsTokenBoolPresent(v18, TokenIsAppContainer, (int *)&StringSid);
          if ( gdwCallFailureLoggingLevel == 1 || (_DWORD)StringSid )
          {
            LODWORD(v21) = 0;
            LODWORD(v20) = 18219;
            LogAccessFailed(v28, v8, 0, 0, v16, v20, v8[9], v21, 1, 7);
          }
          v10 = v15;
          goto LABEL_46;
        }
        v10 = v14 != 0;
      }
      v5 = 0;
    }
    else
    {
      if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        StringSid = 0;
        ConvertSidToStringSidW((char *)v8 + 156, &StringSid);
        CGuidStr::CGuidStr((CGuidStr *)v29, a1);
        HIDWORD(v21) = v12;
        v20 = L"DCOMSCM LocalSecurityCallback AccessCheck LOCALEXECUTE IID:%ws SID:%ws %!HRESULT!";
        ComTraceMessage(
          2147942405LL,
          "onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
          "LocalInterfaceOnlySecCallback",
          1647);
        if ( StringSid )
          LocalFree(StringSid);
      }
      v13 = v8[9];
      LODWORD(StringSid) = 0;
      IsTokenBoolPresent(v13, TokenIsAppContainer, (int *)&StringSid);
      if ( gdwCallFailureLoggingLevel == 1 || (_DWORD)StringSid )
      {
        LODWORD(v21) = 0;
        LODWORD(v20) = 18219;
        LogAccessFailed(v28, v8, 0, 0, a1, v20, v8[9], v21, 2, 7);
      }
    }
  }
LABEL_46:
  if ( v8 )
    CToken::Release((CToken *)v8);
  if ( v9 && v10 && _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v9 )
    {
      HeapFree(g_hHeap, 0, *(LPVOID *)v9);
      *(_QWORD *)v9 = 0;
    }
    operator delete(v9, 0x10u);
  }
  return v5;
}

```

## disassembly

```asm
0x18004a4d0  push    rbp
0x18004a4d2  push    rbx
0x18004a4d3  push    rdi
0x18004a4d4  push    r13
0x18004a4d6  push    r15
0x18004a4d8  lea     rbp, [rsp-37h]
0x18004a4dd  sub     rsp, 0F0h
0x18004a4e4  mov     rax, cs:__security_cookie
0x18004a4eb  xor     rax, rsp
0x18004a4ee  mov     [rbp+57h+var_40], rax
0x18004a4f2  mov     rbx, rdx
0x18004a4f5  mov     [rbp+57h+var_98], rdx
0x18004a4f9  mov     r13, rcx
0x18004a4fc  mov     [rbp+57h+var_A0], rcx
0x18004a500  xor     r15d, r15d
0x18004a503  mov     [rbp+57h+Buf2], 136h
0x18004a50b  mov     rcx, rbx; Binding
0x18004a50e  mov     [rbp+57h+var_A8], 0C0h
0x18004a515  lea     rdx, [rbp+57h+Type]; Type
0x18004a519  mov     [rbp+57h+var_A4], 46000000h
0x18004a520  mov     [rbp+57h+Type], r15d
0x18004a524  call    cs:__imp_I_RpcBindingInqTransportType
0x18004a52a  test    eax, eax
0x18004a52c  jz      loc_18004A5CD
0x18004a532  mov     rcx, [rbp+5Fh]; this
0x18004a536  lea     r8, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18004a53d  mov     r9d, eax; char *
0x18004a540  mov     edx, 652h; void *
0x18004a545  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18004a54a  mov     eax, cs:dword_18014E4B8
0x18004a550  mov     edi, 5
0x18004a555  test    eax, eax
0x18004a557  jnz     short loc_18004A56F
0x18004a559  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18004a560  jz      short loc_18004A5B0
0x18004a562  mov     rax, cs:WPP_GLOBAL_Control
0x18004a569  test    byte ptr [rax+1Ch], 1
0x18004a56d  jz      short loc_18004A5B0
0x18004a56f  mov     rdx, r13; struct _GUID *
0x18004a572  lea     rcx, [rbp+57h+var_90]; this
0x18004a576  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18004a57b  mov     dword ptr [rsp+110h+var_D8], edi
0x18004a57f  lea     r8, aLocalinterface; "LocalInterfaceOnlySecCallback"
0x18004a586  mov     [rsp+110h+var_E0], rax
0x18004a58b  lea     rdx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18004a592  lea     rax, aIidWsWinerror; "IID:%ws %!WINERROR!"
0x18004a599  mov     r9d, 654h
0x18004a59f  mov     [rsp+110h+var_E8], rax
0x18004a5a4  mov     ecx, edi
0x18004a5a6  mov     dword ptr [rsp+110h+var_F0], r15d
0x18004a5ab  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18004a5b0  mov     eax, edi
0x18004a5b2  mov     rcx, [rbp+57h+var_40]
0x18004a5b6  xor     rcx, rsp; StackCookie
0x18004a5b9  call    __security_check_cookie
0x18004a5be  add     rsp, 0F0h
0x18004a5c5  pop     r15
0x18004a5c7  pop     r13
0x18004a5c9  pop     rdi
0x18004a5ca  pop     rbx
0x18004a5cb  pop     rbp
0x18004a5cc  retn
0x18004a5cd  cmp     [rbp+57h+Type], 4
0x18004a5d1  jnz     loc_18004A54A
0x18004a5d7  mov     [rsp+110h+arg_10], rsi
0x18004a5df  lea     r8, [rbp+57h+StringSid]; struct CToken **
0x18004a5e3  mov     [rsp+110h+var_28], r12
0x18004a5eb  xor     r9d, r9d; int *
0x18004a5ee  xor     edx, edx; int
0x18004a5f0  mov     [rsp+110h+var_30], r14
0x18004a5f8  mov     rcx, rbx; BindingHandle
0x18004a5fb  mov     [rbp+57h+StringSid], r15
0x18004a5ff  call    ?LookupOrCreateTokenForRPCClient@@YAJPEAXHPEAPEAVCToken@@PEAH@Z; LookupOrCreateTokenForRPCClient(void *,int,CToken * *,int *)
0x18004a604  mov     rsi, [rbp+57h+StringSid]
0x18004a608  mov     edi, eax
0x18004a60a  mov     r12d, 0FFFFFFFFh
0x18004a610  test    eax, eax
0x18004a612  jz      short loc_18004A63A
0x18004a614  mov     rcx, [rbp+5Fh]; this
0x18004a618  lea     r8, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18004a61f  mov     r9d, eax; char *
0x18004a622  mov     edx, 65Dh; void *
0x18004a627  mov     rbx, r15
0x18004a62a  mov     r14d, 1
0x18004a630  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18004a635  jmp     loc_18004A9C5
0x18004a63a  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004a641  mov     edi, 5
0x18004a646  call    cs:__imp_AcquireSRWLockShared
0x18004a64c  mov     r15, cs:?gpDefaultAccessRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpDefaultAccessRestrictionsSD
0x18004a653  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004a65a  test    r15, r15
0x18004a65d  jz      short loc_18004A66F
0x18004a65f  lock inc dword ptr [r15+0Ch]
0x18004a664  call    cs:__imp_ReleaseSRWLockShared
0x18004a66a  mov     rbx, r15
0x18004a66d  jmp     short loc_18004A67C
0x18004a66f  call    cs:__imp_ReleaseSRWLockShared
0x18004a675  mov     rbx, cs:?gpNoRegAccessRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpNoRegAccessRestrictionsSD
0x18004a67c  mov     rdx, [rbx]; pSecurityDescriptor
0x18004a67f  xor     r14d, r14d
0x18004a682  mov     rcx, [rsi+48h]; ClientToken
0x18004a686  test    r15, r15
0x18004a689  mov     r8d, 2; unsigned int
0x18004a68f  setnz   r14b
0x18004a693  xor     r9d, r9d; void *
0x18004a696  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x18004a69b  test    eax, eax
0x18004a69d  jnz     loc_18004A7C0
0x18004a6a3  mov     eax, cs:dword_18014E4B8
0x18004a6a9  test    eax, eax
0x18004a6ab  jnz     short loc_18004A6CA
0x18004a6ad  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18004a6b3  jz      loc_18004A752
0x18004a6b9  mov     rax, cs:WPP_GLOBAL_Control
0x18004a6c0  test    byte ptr [rax+1Ch], 1
0x18004a6c4  jz      loc_18004A752
0x18004a6ca  xor     r15d, r15d
0x18004a6cd  lea     rcx, [rsi+9Ch]; Sid
0x18004a6d4  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18004a6d8  mov     [rbp+57h+StringSid], r15
0x18004a6dc  call    cs:__imp_ConvertSidToStringSidW
0x18004a6e2  mov     rax, [rbp+57h+StringSid]
0x18004a6e6  lea     r11, Class
0x18004a6ed  test    rax, rax
0x18004a6f0  lea     rcx, [rbp+57h+var_90]; this
0x18004a6f4  mov     rdx, r13; struct _GUID *
0x18004a6f7  cmovnz  r11, rax
0x18004a6fb  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18004a700  mov     [rsp+110h+var_D0], 80070005h
0x18004a708  lea     r8, aLocalinterface; "LocalInterfaceOnlySecCallback"
0x18004a70f  mov     [rsp+110h+var_D8], r11
0x18004a714  lea     rdx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18004a71b  mov     [rsp+110h+var_E0], rax
0x18004a720  mov     r9d, 66Fh
0x18004a726  lea     rax, aDcomscmLocalse; "DCOMSCM LocalSecurityCallback AccessChe"...
0x18004a72d  mov     ecx, 80070005h
0x18004a732  mov     [rsp+110h+var_E8], rax
0x18004a737  mov     dword ptr [rsp+110h+var_F0], r15d
0x18004a73c  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18004a741  mov     rcx, [rbp+57h+StringSid]; hMem
0x18004a745  test    rcx, rcx
0x18004a748  jz      short loc_18004A755
0x18004a74a  call    cs:__imp_LocalFree
0x18004a750  jmp     short loc_18004A755
0x18004a752  xor     r15d, r15d
0x18004a755  mov     rcx, [rsi+48h]; void *
0x18004a759  lea     r8, [rbp+57h+StringSid]; int *
0x18004a75d  mov     edx, 1Dh; enum _TOKEN_INFORMATION_CLASS
0x18004a762  mov     dword ptr [rbp+57h+StringSid], r15d
0x18004a766  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x18004a76b  cmp     cs:?gdwCallFailureLoggingLevel@@3KA, 1; ulong gdwCallFailureLoggingLevel
0x18004a772  jz      short loc_18004A77E
0x18004a774  cmp     dword ptr [rbp+57h+StringSid], 0
0x18004a778  jz      loc_18004A9C5
0x18004a77e  mov     rax, [rsi+48h]
0x18004a782  xor     r9d, r9d
0x18004a785  mov     rcx, [rbp+57h+var_98]
0x18004a789  xor     r8d, r8d
0x18004a78c  mov     [rsp+110h+var_C8], 7
0x18004a794  mov     rdx, rsi
0x18004a797  mov     [rsp+110h+var_D0], 2
0x18004a79f  mov     dword ptr [rsp+110h+var_D8], r15d
0x18004a7a4  mov     [rsp+110h+var_E0], rax
0x18004a7a9  mov     dword ptr [rsp+110h+var_E8], 472Bh
0x18004a7b1  mov     [rsp+110h+var_F0], r13
0x18004a7b6  call    ?LogAccessFailed@@YAXPEAXPEAUIUserToken@@PEAUHSTRING__@@PEAU_GUID@@3K0HW4tagEventLogModes@@W4tagEventLogSD@@@Z; LogAccessFailed(void *,IUserToken *,HSTRING__ *,_GUID *,_GUID *,ulong,void *,int,tagEventLogModes,tagEventLogSD)
0x18004a7bb  jmp     loc_18004A9C5
0x18004a7c0  test    r15, r15
0x18004a7c3  jz      short loc_18004A7FD
0x18004a7c5  mov     eax, r12d
0x18004a7c8  lock xadd [rbx+0Ch], eax
0x18004a7cd  cmp     eax, 1
0x18004a7d0  jnz     short loc_18004A7FD
0x18004a7d2  mov     r8, [rbx]; lpMem
0x18004a7d5  test    r8, r8
0x18004a7d8  jz      short loc_18004A7F0
0x18004a7da  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18004a7e1  xor     edx, edx; dwFlags
0x18004a7e3  call    cs:__imp_HeapFree
0x18004a7e9  mov     qword ptr [rbx], 0
0x18004a7f0  mov     edx, 10h; unsigned __int64
0x18004a7f5  mov     rcx, rbx; void *
0x18004a7f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004a7fd  xor     r15d, r15d
0x18004a800  mov     r14d, 1
0x18004a806  cmp     cs:?gfCheckActivationSecurity@@3HA, r15d; int gfCheckActivationSecurity
0x18004a80d  mov     ebx, r15d
0x18004a810  jz      loc_18004A9C2
0x18004a816  mov     r8d, 10h; Size
0x18004a81c  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18004a820  mov     rcx, r13; Buf1
0x18004a823  call    memcmp_0
0x18004a828  test    eax, eax
0x18004a82a  jnz     loc_18004A9C2
0x18004a830  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004a837  call    cs:__imp_AcquireSRWLockShared
0x18004a83d  mov     r15, cs:?gpDefaultLaunchRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpDefaultLaunchRestrictionsSD
0x18004a844  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004a84b  test    r15, r15
0x18004a84e  jz      short loc_18004A860
0x18004a850  lock inc dword ptr [r15+0Ch]
0x18004a855  call    cs:__imp_ReleaseSRWLockShared
0x18004a85b  mov     rbx, r15
0x18004a85e  jmp     short loc_18004A86D
0x18004a860  call    cs:__imp_ReleaseSRWLockShared
0x18004a866  mov     rbx, cs:?gpNoRegLaunchRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpNoRegLaunchRestrictionsSD
0x18004a86d  mov     rdx, [rbx]; pSecurityDescriptor
0x18004a870  xor     r13d, r13d
0x18004a873  mov     rcx, [rsi+48h]; ClientToken
0x18004a877  test    r15, r15
0x18004a87a  mov     r8d, 8; unsigned int
0x18004a880  setnz   r13b
0x18004a884  xor     r9d, r9d; void *
0x18004a887  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x18004a88c  test    eax, eax
0x18004a88e  jnz     loc_18004A9BC
0x18004a894  mov     eax, cs:dword_18014E4B8
0x18004a89a  test    eax, eax
0x18004a89c  jnz     short loc_18004A8BB
0x18004a89e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18004a8a4  jz      loc_18004A94B
0x18004a8aa  mov     rax, cs:WPP_GLOBAL_Control
0x18004a8b1  test    [rax+1Ch], r14b
0x18004a8b5  jz      loc_18004A94B
0x18004a8bb  lea     rcx, [rsi+9Ch]; Sid
0x18004a8c2  mov     [rbp+57h+StringSid], 0
0x18004a8ca  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18004a8ce  call    cs:__imp_ConvertSidToStringSidW
0x18004a8d4  mov     rax, [rbp+57h+StringSid]
0x18004a8d8  lea     r11, Class
0x18004a8df  mov     r15, [rbp+57h+var_A0]
0x18004a8e3  lea     rcx, [rbp+57h+var_90]; this
0x18004a8e7  test    rax, rax
0x18004a8ea  mov     rdx, r15; struct _GUID *
0x18004a8ed  cmovnz  r11, rax
0x18004a8f1  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18004a8f6  mov     [rsp+110h+var_D0], 80070005h
0x18004a8fe  lea     r8, aLocalinterface; "LocalInterfaceOnlySecCallback"
0x18004a905  mov     [rsp+110h+var_D8], r11
0x18004a90a  lea     rdx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18004a911  mov     [rsp+110h+var_E0], rax
0x18004a916  mov     r9d, 693h
0x18004a91c  lea     rax, aDcomscmLocalse_0; "DCOMSCM LocalSecurityCallback AccessChe"...
0x18004a923  mov     ecx, 80070005h
0x18004a928  mov     [rsp+110h+var_E8], rax
0x18004a92d  mov     dword ptr [rsp+110h+var_F0], 0
0x18004a935  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18004a93a  mov     rcx, [rbp+57h+StringSid]; hMem
0x18004a93e  test    rcx, rcx
0x18004a941  jz      short loc_18004A94F
0x18004a943  call    cs:__imp_LocalFree
0x18004a949  jmp     short loc_18004A94F
0x18004a94b  mov     r15, [rbp+57h+var_A0]
0x18004a94f  mov     rcx, [rsi+48h]; void *
0x18004a953  lea     r8, [rbp+57h+StringSid]; int *
0x18004a957  mov     edx, 1Dh; enum _TOKEN_INFORMATION_CLASS
0x18004a95c  mov     dword ptr [rbp+57h+StringSid], 0
0x18004a963  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x18004a968  cmp     cs:?gdwCallFailureLoggingLevel@@3KA, r14d; ulong gdwCallFailureLoggingLevel
0x18004a96f  jz      short loc_18004A977
0x18004a971  cmp     dword ptr [rbp+57h+StringSid], 0
0x18004a975  jz      short loc_18004A9B4
0x18004a977  mov     rax, [rsi+48h]
0x18004a97b  xor     r9d, r9d
0x18004a97e  mov     rcx, [rbp+57h+var_98]
0x18004a982  xor     r8d, r8d
0x18004a985  mov     [rsp+110h+var_C8], 7
0x18004a98d  mov     rdx, rsi
0x18004a990  mov     [rsp+110h+var_D0], r14d
0x18004a995  mov     dword ptr [rsp+110h+var_D8], 0
0x18004a99d  mov     [rsp+110h+var_E0], rax
0x18004a9a2  mov     dword ptr [rsp+110h+var_E8], 472Bh
0x18004a9aa  mov     [rsp+110h+var_F0], r15
0x18004a9af  call    ?LogAccessFailed@@YAXPEAXPEAUIUserToken@@PEAUHSTRING__@@PEAU_GUID@@3K0HW4tagEventLogModes@@W4tagEventLogSD@@@Z; LogAccessFailed(void *,IUserToken *,HSTRING__ *,_GUID *,_GUID *,ulong,void *,int,tagEventLogModes,tagEventLogSD)
0x18004a9b4  mov     r14d, r13d
0x18004a9b7  xor     r15d, r15d
0x18004a9ba  jmp     short loc_18004A9C5
0x18004a9bc  mov     r14d, r13d
0x18004a9bf  xor     r15d, r15d
0x18004a9c2  mov     edi, r15d
0x18004a9c5  test    rsi, rsi
0x18004a9c8  jz      short loc_18004A9D2
0x18004a9ca  mov     rcx, rsi; this
0x18004a9cd  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x18004a9d2  mov     rsi, [rsp+110h+arg_10]
0x18004a9da  test    rbx, rbx
0x18004a9dd  jz      short loc_18004AA17
0x18004a9df  test    r14d, r14d
0x18004a9e2  jz      short loc_18004AA17
0x18004a9e4  lock xadd [rbx+0Ch], r12d
0x18004a9ea  cmp     r12d, 1
0x18004a9ee  jnz     short loc_18004AA17
0x18004a9f0  mov     r8, [rbx]; lpMem
0x18004a9f3  test    r8, r8
0x18004a9f6  jz      short loc_18004AA0A
0x18004a9f8  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18004a9ff  xor     edx, edx; dwFlags
0x18004aa01  call    cs:__imp_HeapFree
0x18004aa07  mov     [rbx], r15
  ... truncated ...
```
