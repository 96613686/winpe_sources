# SamAddMemberToAlias

- ea: `0x18000c650`
- end: `0x18000c846`
- name: `SamAddMemberToAlias`
- size: `502`
- prototype: `__int64 __fastcall(void *, PSID pSid)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003220`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000bd18`
- `0x18000c650`
- `0x180014a50`
- `0x180014f80`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6b0`
- `RPCRT4!NdrClientCall3` at `0x18000c763`
- `RPCRT4!NdrClientCall3` at `0x18000c763`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c7a6`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c7a6`

## pseudocode

```c
__int64 __fastcall SamAddMemberToAlias(void **a1, PSID pSid, __int64 a3)
{
  unsigned __int16 *CallingProcessInfo; // rax
  unsigned __int16 *v6; // rdi
  const wchar_t *v7; // rcx
  PVOID v8; // rcx
  CLIENT_CALL_RETURN v10; // rax
  unsigned int Pointer; // ebx
  PVOID v12; // rcx
  void *v13; // [rsp+60h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v14; // [rsp+68h] [rbp+20h]

  v13 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v6 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v7 = L"<unknown>";
      if ( CallingProcessInfo )
        v7 = CallingProcessInfo;
      McTemplateU0pkz_EventWriteTransfer(
        (_DWORD)v7,
        (unsigned int)SamAddMemberToAliasEntry,
        (_DWORD)a1,
        (_DWORD)pSid,
        (__int64)v7);
    }
    LocalFree(v6);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xC6u, a3, a1, pSid);
  if ( (unsigned __int8)SampIsValidClientHandle(a1, &v13) )
  {
    v14.Simple = 0;
    v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x1Fu, 0, v13, pSid).Pointer;
    Pointer = (unsigned int)v10.Pointer;
    v14.Pointer = v10.Pointer;
    if ( LODWORD(v10.Pointer) == -1073610749 )
      Pointer = -1073741816;
    if ( (Pointer & 0x80000000) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v12, (const EVENT_DESCRIPTOR *)SamAddMemberToAliasExit, Pointer);
    return Pointer;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v8, (const EVENT_DESCRIPTOR *)SamAddMemberToAliasExit, 3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x18000c650  mov     [rsp+arg_0], rbx
0x18000c655  mov     [rsp+arg_8], rsi
0x18000c65a  push    rdi
0x18000c65b  sub     rsp, 40h
0x18000c65f  mov     rsi, rdx
0x18000c662  mov     rbx, rcx
0x18000c665  mov     [rsp+48h+arg_10], 0
0x18000c66e  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000c675  jz      short loc_18000C6B6
0x18000c677  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000c67c  mov     rdi, rax
0x18000c67f  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000c686  jz      short loc_18000C6AD
0x18000c688  lea     rcx, aUnknown; "<unknown>"
0x18000c68f  test    rax, rax
0x18000c692  cmovnz  rcx, rax
0x18000c696  mov     [rsp+48h+pSid], rcx
0x18000c69b  mov     r9, rsi
0x18000c69e  mov     r8, rbx
0x18000c6a1  lea     rdx, SamAddMemberToAliasEntry
0x18000c6a8  call    McTemplateU0pkz_EventWriteTransfer
0x18000c6ad  mov     rcx, rdi; hMem
0x18000c6b0  call    cs:__imp_LocalFree
0x18000c6b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6bd  mov     dil, 2
0x18000c6c0  test    [rcx+1Ch], dil
0x18000c6c4  jz      short loc_18000C6E2
0x18000c6c6  cmp     byte ptr [rcx+19h], 4
0x18000c6ca  jb      short loc_18000C6E2
0x18000c6cc  mov     edx, 0C6h
0x18000c6d1  mov     [rsp+48h+pSid], rsi; pSid
0x18000c6d6  mov     r9, rbx
0x18000c6d9  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c6dd  call    WPP_SF_q_sid_
0x18000c6e2  lea     rdx, [rsp+48h+arg_10]; void **
0x18000c6e7  mov     rcx, rbx; void *
0x18000c6ea  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000c6ef  test    al, al
0x18000c6f1  jnz     short loc_18000C742
0x18000c6f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6fa  test    [rcx+1Ch], dil
0x18000c6fe  jz      short loc_18000C71E
0x18000c700  cmp     [rcx+19h], dil
0x18000c704  jb      short loc_18000C71E
0x18000c706  mov     edx, 0C7h
0x18000c70b  mov     r9, rbx
0x18000c70e  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000c715  mov     rcx, [rcx+10h]
0x18000c719  call    WPP_SF_q
0x18000c71e  mov     esi, 0C0000008h
0x18000c723  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000c72a  jz      short loc_18000C73B
0x18000c72c  mov     r8d, esi
0x18000c72f  lea     rdx, SamAddMemberToAliasExit
0x18000c736  call    McTemplateU0d_EventWriteTransfer
0x18000c73b  mov     eax, esi
0x18000c73d  jmp     loc_18000C836
0x18000c742  mov     [rsp+48h+arg_18], 0
0x18000c74b  mov     [rsp+48h+pSid], rsi
0x18000c750  mov     r9, [rsp+48h+arg_10]
0x18000c755  xor     r8d, r8d; pReturnValue
0x18000c758  lea     edx, [r8+1Fh]; nProcNum
0x18000c75c  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000c763  call    cs:__imp_NdrClientCall3
0x18000c769  mov     rbx, rax
0x18000c76c  mov     [rsp+48h+arg_18], rax
0x18000c771  mov     [rsp+48h+var_18], eax
0x18000c775  jmp     short loc_18000C7B5
0x18000c777  mov     ebx, eax
0x18000c779  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c780  test    byte ptr [rcx+1Ch], 2
0x18000c784  jz      short loc_18000C7A4
0x18000c786  cmp     byte ptr [rcx+19h], 3
0x18000c78a  jb      short loc_18000C7A4
0x18000c78c  mov     r9d, eax
0x18000c78f  mov     edx, 0C8h
0x18000c794  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000c79b  mov     rcx, [rcx+10h]
0x18000c79f  call    WPP_SF_D
0x18000c7a4  mov     ecx, ebx; Status
0x18000c7a6  call    cs:__imp_I_RpcMapWin32Status
0x18000c7ac  mov     ebx, eax
0x18000c7ae  mov     [rsp+48h+var_18], eax
0x18000c7b2  mov     dil, 2
0x18000c7b5  mov     esi, 0C0000008h
0x18000c7ba  cmp     ebx, 0C0020003h
0x18000c7c0  cmovz   ebx, esi
0x18000c7c3  test    ebx, ebx
0x18000c7c5  js      short loc_18000C7F1
0x18000c7c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7ce  test    [rcx+1Ch], dil
0x18000c7d2  jz      short loc_18000C81C
0x18000c7d4  cmp     byte ptr [rcx+19h], 4
0x18000c7d8  jb      short loc_18000C81C
0x18000c7da  mov     edx, 0C9h
0x18000c7df  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000c7e6  mov     rcx, [rcx+10h]
0x18000c7ea  call    WPP_SF_
0x18000c7ef  jmp     short loc_18000C81C
0x18000c7f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7f8  test    [rcx+1Ch], dil
0x18000c7fc  jz      short loc_18000C81C
0x18000c7fe  cmp     [rcx+19h], dil
0x18000c802  jb      short loc_18000C81C
0x18000c804  mov     edx, 0CAh
0x18000c809  mov     r9d, ebx
0x18000c80c  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000c813  mov     rcx, [rcx+10h]
0x18000c817  call    WPP_SF_D
0x18000c81c  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000c823  jz      short loc_18000C834
0x18000c825  mov     r8d, ebx
0x18000c828  lea     rdx, SamAddMemberToAliasExit
0x18000c82f  call    McTemplateU0d_EventWriteTransfer
0x18000c834  mov     eax, ebx
0x18000c836  mov     rbx, [rsp+48h+arg_0]
0x18000c83b  mov     rsi, [rsp+48h+arg_8]
0x18000c840  add     rsp, 40h
0x18000c844  pop     rdi
0x18000c845  retn
0x180017dbc  push    rbp
0x180017dbe  sub     rsp, 30h
0x180017dc2  mov     rbp, rdx
0x180017dc5  mov     rcx, [rcx]
0x180017dc8  mov     ecx, [rcx]; ExceptionCode
0x180017dca  call    cs:__imp_I_RpcExceptionFilter
0x180017dd0  nop
0x180017dd1  add     rsp, 30h
0x180017dd5  pop     rbp
0x180017dd6  retn
```
