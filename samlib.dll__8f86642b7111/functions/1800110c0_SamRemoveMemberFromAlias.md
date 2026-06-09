# SamRemoveMemberFromAlias

- ea: `0x1800110c0`
- end: `0x1800112b6`
- name: `SamRemoveMemberFromAlias`
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
- `0x1800110c0`
- `0x180014a50`
- `0x180014f80`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011120`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011120`
- `RPCRT4!NdrClientCall3` at `0x1800111d3`
- `RPCRT4!NdrClientCall3` at `0x1800111d3`
- `RPCRT4!I_RpcMapWin32Status` at `0x180011216`
- `RPCRT4!I_RpcMapWin32Status` at `0x180011216`

## pseudocode

```c
__int64 __fastcall SamRemoveMemberFromAlias(void **a1, PSID pSid, __int64 a3)
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
        (unsigned int)SamRemoveMemberFromAliasEntry,
        (_DWORD)a1,
        (_DWORD)pSid,
        (__int64)v7);
    }
    LocalFree(v6);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xCBu, a3, a1, pSid);
  if ( (unsigned __int8)SampIsValidClientHandle(a1, &v13) )
  {
    v14.Simple = 0;
    v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x20u, 0, v13, pSid).Pointer;
    Pointer = (unsigned int)v10.Pointer;
    v14.Pointer = v10.Pointer;
    if ( LODWORD(v10.Pointer) == -1073610749 )
      Pointer = -1073741816;
    if ( (Pointer & 0x80000000) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 206, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v12, (const EVENT_DESCRIPTOR *)SamRemoveMemberFromAliasExit, Pointer);
    return Pointer;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(
        (__int64)v8,
        (const EVENT_DESCRIPTOR *)SamRemoveMemberFromAliasExit,
        3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x1800110c0  mov     [rsp+arg_0], rbx
0x1800110c5  mov     [rsp+arg_8], rsi
0x1800110ca  push    rdi
0x1800110cb  sub     rsp, 40h
0x1800110cf  mov     rsi, rdx
0x1800110d2  mov     rbx, rcx
0x1800110d5  mov     [rsp+48h+arg_10], 0
0x1800110de  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800110e5  jz      short loc_180011126
0x1800110e7  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x1800110ec  mov     rdi, rax
0x1800110ef  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800110f6  jz      short loc_18001111D
0x1800110f8  lea     rcx, aUnknown; "<unknown>"
0x1800110ff  test    rax, rax
0x180011102  cmovnz  rcx, rax
0x180011106  mov     [rsp+48h+pSid], rcx
0x18001110b  mov     r9, rsi
0x18001110e  mov     r8, rbx
0x180011111  lea     rdx, SamRemoveMemberFromAliasEntry
0x180011118  call    McTemplateU0pkz_EventWriteTransfer
0x18001111d  mov     rcx, rdi; hMem
0x180011120  call    cs:__imp_LocalFree
0x180011126  mov     rcx, cs:WPP_GLOBAL_Control
0x18001112d  mov     dil, 2
0x180011130  test    [rcx+1Ch], dil
0x180011134  jz      short loc_180011152
0x180011136  cmp     byte ptr [rcx+19h], 4
0x18001113a  jb      short loc_180011152
0x18001113c  mov     edx, 0CBh
0x180011141  mov     [rsp+48h+pSid], rsi; pSid
0x180011146  mov     r9, rbx
0x180011149  mov     rcx, [rcx+10h]; LoggerHandle
0x18001114d  call    WPP_SF_q_sid_
0x180011152  lea     rdx, [rsp+48h+arg_10]; void **
0x180011157  mov     rcx, rbx; void *
0x18001115a  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18001115f  test    al, al
0x180011161  jnz     short loc_1800111B2
0x180011163  mov     rcx, cs:WPP_GLOBAL_Control
0x18001116a  test    [rcx+1Ch], dil
0x18001116e  jz      short loc_18001118E
0x180011170  cmp     [rcx+19h], dil
0x180011174  jb      short loc_18001118E
0x180011176  mov     edx, 0CCh
0x18001117b  mov     r9, rbx
0x18001117e  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011185  mov     rcx, [rcx+10h]
0x180011189  call    WPP_SF_q
0x18001118e  mov     esi, 0C0000008h
0x180011193  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18001119a  jz      short loc_1800111AB
0x18001119c  mov     r8d, esi
0x18001119f  lea     rdx, SamRemoveMemberFromAliasExit
0x1800111a6  call    McTemplateU0d_EventWriteTransfer
0x1800111ab  mov     eax, esi
0x1800111ad  jmp     loc_1800112A6
0x1800111b2  mov     [rsp+48h+arg_18], 0
0x1800111bb  mov     [rsp+48h+pSid], rsi
0x1800111c0  mov     r9, [rsp+48h+arg_10]
0x1800111c5  xor     r8d, r8d; pReturnValue
0x1800111c8  lea     edx, [r8+20h]; nProcNum
0x1800111cc  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800111d3  call    cs:__imp_NdrClientCall3
0x1800111d9  mov     rbx, rax
0x1800111dc  mov     [rsp+48h+arg_18], rax
0x1800111e1  mov     [rsp+48h+var_18], eax
0x1800111e5  jmp     short loc_180011225
0x1800111e7  mov     ebx, eax
0x1800111e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111f0  test    byte ptr [rcx+1Ch], 2
0x1800111f4  jz      short loc_180011214
0x1800111f6  cmp     byte ptr [rcx+19h], 3
0x1800111fa  jb      short loc_180011214
0x1800111fc  mov     r9d, eax
0x1800111ff  mov     edx, 0CDh
0x180011204  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18001120b  mov     rcx, [rcx+10h]
0x18001120f  call    WPP_SF_D
0x180011214  mov     ecx, ebx; Status
0x180011216  call    cs:__imp_I_RpcMapWin32Status
0x18001121c  mov     ebx, eax
0x18001121e  mov     [rsp+48h+var_18], eax
0x180011222  mov     dil, 2
0x180011225  mov     esi, 0C0000008h
0x18001122a  cmp     ebx, 0C0020003h
0x180011230  cmovz   ebx, esi
0x180011233  test    ebx, ebx
0x180011235  js      short loc_180011261
0x180011237  mov     rcx, cs:WPP_GLOBAL_Control
0x18001123e  test    [rcx+1Ch], dil
0x180011242  jz      short loc_18001128C
0x180011244  cmp     byte ptr [rcx+19h], 4
0x180011248  jb      short loc_18001128C
0x18001124a  mov     edx, 0CEh
0x18001124f  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011256  mov     rcx, [rcx+10h]
0x18001125a  call    WPP_SF_
0x18001125f  jmp     short loc_18001128C
0x180011261  mov     rcx, cs:WPP_GLOBAL_Control
0x180011268  test    [rcx+1Ch], dil
0x18001126c  jz      short loc_18001128C
0x18001126e  cmp     [rcx+19h], dil
0x180011272  jb      short loc_18001128C
0x180011274  mov     edx, 0CFh
0x180011279  mov     r9d, ebx
0x18001127c  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011283  mov     rcx, [rcx+10h]
0x180011287  call    WPP_SF_D
0x18001128c  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180011293  jz      short loc_1800112A4
0x180011295  mov     r8d, ebx
0x180011298  lea     rdx, SamRemoveMemberFromAliasExit
0x18001129f  call    McTemplateU0d_EventWriteTransfer
0x1800112a4  mov     eax, ebx
0x1800112a6  mov     rbx, [rsp+48h+arg_0]
0x1800112ab  mov     rsi, [rsp+48h+arg_8]
0x1800112b0  add     rsp, 40h
0x1800112b4  pop     rdi
0x1800112b5  retn
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
