# SamRemoveMemberFromForeignDomain

- ea: `0x1800112c0`
- end: `0x1800114b6`
- name: `SamRemoveMemberFromForeignDomain`
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
- `0x1800112c0`
- `0x180014a50`
- `0x180014f80`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011320`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011320`
- `RPCRT4!NdrClientCall3` at `0x1800113d3`
- `RPCRT4!NdrClientCall3` at `0x1800113d3`
- `RPCRT4!I_RpcMapWin32Status` at `0x180011416`
- `RPCRT4!I_RpcMapWin32Status` at `0x180011416`

## pseudocode

```c
__int64 __fastcall SamRemoveMemberFromForeignDomain(void **a1, PSID pSid, __int64 a3)
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
        (unsigned int)SamRemoveMemberFromForeignDomainEntry,
        (_DWORD)a1,
        (_DWORD)pSid,
        (__int64)v7);
    }
    LocalFree(v6);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xD0u, a3, a1, pSid);
  if ( (unsigned __int8)SampIsValidClientHandle(a1, &v13) )
  {
    v14.Simple = 0;
    v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x2Du, 0, v13, pSid).Pointer;
    Pointer = (unsigned int)v10.Pointer;
    v14.Pointer = v10.Pointer;
    if ( LODWORD(v10.Pointer) == -1073610749 )
      Pointer = -1073741816;
    if ( (Pointer & 0x80000000) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(
        (__int64)v12,
        (const EVENT_DESCRIPTOR *)SamRemoveMemberFromForeignDomainExit,
        Pointer);
    return Pointer;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(
        (__int64)v8,
        (const EVENT_DESCRIPTOR *)SamRemoveMemberFromForeignDomainExit,
        3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x1800112c0  mov     [rsp+arg_0], rbx
0x1800112c5  mov     [rsp+arg_8], rsi
0x1800112ca  push    rdi
0x1800112cb  sub     rsp, 40h
0x1800112cf  mov     rsi, rdx
0x1800112d2  mov     rbx, rcx
0x1800112d5  mov     [rsp+48h+arg_10], 0
0x1800112de  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800112e5  jz      short loc_180011326
0x1800112e7  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x1800112ec  mov     rdi, rax
0x1800112ef  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800112f6  jz      short loc_18001131D
0x1800112f8  lea     rcx, aUnknown; "<unknown>"
0x1800112ff  test    rax, rax
0x180011302  cmovnz  rcx, rax
0x180011306  mov     [rsp+48h+pSid], rcx
0x18001130b  mov     r9, rsi
0x18001130e  mov     r8, rbx
0x180011311  lea     rdx, SamRemoveMemberFromForeignDomainEntry
0x180011318  call    McTemplateU0pkz_EventWriteTransfer
0x18001131d  mov     rcx, rdi; hMem
0x180011320  call    cs:__imp_LocalFree
0x180011326  mov     rcx, cs:WPP_GLOBAL_Control
0x18001132d  mov     dil, 2
0x180011330  test    [rcx+1Ch], dil
0x180011334  jz      short loc_180011352
0x180011336  cmp     byte ptr [rcx+19h], 4
0x18001133a  jb      short loc_180011352
0x18001133c  mov     edx, 0D0h
0x180011341  mov     [rsp+48h+pSid], rsi; pSid
0x180011346  mov     r9, rbx
0x180011349  mov     rcx, [rcx+10h]; LoggerHandle
0x18001134d  call    WPP_SF_q_sid_
0x180011352  lea     rdx, [rsp+48h+arg_10]; void **
0x180011357  mov     rcx, rbx; void *
0x18001135a  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18001135f  test    al, al
0x180011361  jnz     short loc_1800113B2
0x180011363  mov     rcx, cs:WPP_GLOBAL_Control
0x18001136a  test    [rcx+1Ch], dil
0x18001136e  jz      short loc_18001138E
0x180011370  cmp     [rcx+19h], dil
0x180011374  jb      short loc_18001138E
0x180011376  mov     edx, 0D1h
0x18001137b  mov     r9, rbx
0x18001137e  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011385  mov     rcx, [rcx+10h]
0x180011389  call    WPP_SF_q
0x18001138e  mov     esi, 0C0000008h
0x180011393  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18001139a  jz      short loc_1800113AB
0x18001139c  mov     r8d, esi
0x18001139f  lea     rdx, SamRemoveMemberFromForeignDomainExit
0x1800113a6  call    McTemplateU0d_EventWriteTransfer
0x1800113ab  mov     eax, esi
0x1800113ad  jmp     loc_1800114A6
0x1800113b2  mov     [rsp+48h+arg_18], 0
0x1800113bb  mov     [rsp+48h+pSid], rsi
0x1800113c0  mov     r9, [rsp+48h+arg_10]
0x1800113c5  xor     r8d, r8d; pReturnValue
0x1800113c8  lea     edx, [r8+2Dh]; nProcNum
0x1800113cc  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800113d3  call    cs:__imp_NdrClientCall3
0x1800113d9  mov     rbx, rax
0x1800113dc  mov     [rsp+48h+arg_18], rax
0x1800113e1  mov     [rsp+48h+var_18], eax
0x1800113e5  jmp     short loc_180011425
0x1800113e7  mov     ebx, eax
0x1800113e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113f0  test    byte ptr [rcx+1Ch], 2
0x1800113f4  jz      short loc_180011414
0x1800113f6  cmp     byte ptr [rcx+19h], 3
0x1800113fa  jb      short loc_180011414
0x1800113fc  mov     r9d, eax
0x1800113ff  mov     edx, 0D2h
0x180011404  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18001140b  mov     rcx, [rcx+10h]
0x18001140f  call    WPP_SF_D
0x180011414  mov     ecx, ebx; Status
0x180011416  call    cs:__imp_I_RpcMapWin32Status
0x18001141c  mov     ebx, eax
0x18001141e  mov     [rsp+48h+var_18], eax
0x180011422  mov     dil, 2
0x180011425  mov     esi, 0C0000008h
0x18001142a  cmp     ebx, 0C0020003h
0x180011430  cmovz   ebx, esi
0x180011433  test    ebx, ebx
0x180011435  js      short loc_180011461
0x180011437  mov     rcx, cs:WPP_GLOBAL_Control
0x18001143e  test    [rcx+1Ch], dil
0x180011442  jz      short loc_18001148C
0x180011444  cmp     byte ptr [rcx+19h], 4
0x180011448  jb      short loc_18001148C
0x18001144a  mov     edx, 0D3h
0x18001144f  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011456  mov     rcx, [rcx+10h]
0x18001145a  call    WPP_SF_
0x18001145f  jmp     short loc_18001148C
0x180011461  mov     rcx, cs:WPP_GLOBAL_Control
0x180011468  test    [rcx+1Ch], dil
0x18001146c  jz      short loc_18001148C
0x18001146e  cmp     [rcx+19h], dil
0x180011472  jb      short loc_18001148C
0x180011474  mov     edx, 0D4h
0x180011479  mov     r9d, ebx
0x18001147c  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011483  mov     rcx, [rcx+10h]
0x180011487  call    WPP_SF_D
0x18001148c  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180011493  jz      short loc_1800114A4
0x180011495  mov     r8d, ebx
0x180011498  lea     rdx, SamRemoveMemberFromForeignDomainExit
0x18001149f  call    McTemplateU0d_EventWriteTransfer
0x1800114a4  mov     eax, ebx
0x1800114a6  mov     rbx, [rsp+48h+arg_0]
0x1800114ab  mov     rsi, [rsp+48h+arg_8]
0x1800114b0  add     rsp, 40h
0x1800114b4  pop     rdi
0x1800114b5  retn
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
