# SamRemoveMemberFromGroup

- ea: `0x1800114c0`
- end: `0x1800116b9`
- name: `SamRemoveMemberFromGroup`
- size: `505`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003220`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000c070`
- `0x1800114c0`
- `0x180014a50`
- `0x180014a90`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011521`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011521`
- `RPCRT4!NdrClientCall3` at `0x1800115d8`
- `RPCRT4!NdrClientCall3` at `0x1800115d8`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001161b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001161b`

## pseudocode

```c
__int64 __fastcall SamRemoveMemberFromGroup(void **a1, int a2)
{
  unsigned __int16 *CallingProcessInfo; // rax
  unsigned __int16 *v5; // rbx
  const wchar_t *v6; // rcx
  PVOID v7; // rcx
  CLIENT_CALL_RETURN v9; // rax
  unsigned int Pointer; // ebx
  PVOID v11; // rcx
  __int64 v12; // [rsp+20h] [rbp-28h]
  void *v13; // [rsp+60h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v14; // [rsp+68h] [rbp+20h]

  v13 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v5 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v6 = L"<unknown>";
      if ( CallingProcessInfo )
        v6 = CallingProcessInfo;
      McTemplateU0pqz_EventWriteTransfer(
        (__int64)v6,
        (const EVENT_DESCRIPTOR *)SamRemoveMemberFromGroupEntry,
        (__int64)a1,
        a2,
        v6);
    }
    LocalFree(v5);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1, a2);
  if ( (unsigned __int8)SampIsValidClientHandle(a1, &v13) )
  {
    v14.Simple = 0;
    LODWORD(v12) = a2;
    v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x18u, 0, v13, v12).Pointer;
    Pointer = (unsigned int)v9.Pointer;
    v14.Pointer = v9.Pointer;
    if ( LODWORD(v9.Pointer) == -1073610749 )
      Pointer = -1073741816;
    if ( (Pointer & 0x80000000) != 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v11, (const EVENT_DESCRIPTOR *)SamRemoveMemberFromGroupExit, Pointer);
    return Pointer;
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(
        (__int64)v7,
        (const EVENT_DESCRIPTOR *)SamRemoveMemberFromGroupExit,
        3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x1800114c0  mov     [rsp+arg_0], rbx
0x1800114c5  mov     [rsp+arg_8], rsi
0x1800114ca  push    r14
0x1800114cc  sub     rsp, 40h
0x1800114d0  mov     r14d, edx
0x1800114d3  mov     rsi, rcx
0x1800114d6  mov     [rsp+48h+arg_10], 0
0x1800114df  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800114e6  jz      short loc_180011527
0x1800114e8  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x1800114ed  mov     rbx, rax
0x1800114f0  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800114f7  jz      short loc_18001151E
0x1800114f9  lea     rcx, aUnknown; "<unknown>"
0x180011500  test    rax, rax
0x180011503  cmovnz  rcx, rax
0x180011507  mov     [rsp+48h+var_28], rcx
0x18001150c  mov     r9d, r14d
0x18001150f  mov     r8, rsi
0x180011512  lea     rdx, SamRemoveMemberFromGroupEntry
0x180011519  call    McTemplateU0pqz_EventWriteTransfer
0x18001151e  mov     rcx, rbx; hMem
0x180011521  call    cs:__imp_LocalFree
0x180011527  mov     rcx, cs:WPP_GLOBAL_Control
0x18001152e  test    byte ptr [rcx+1Ch], 2
0x180011532  jz      short loc_180011557
0x180011534  cmp     byte ptr [rcx+19h], 4
0x180011538  jb      short loc_180011557
0x18001153a  mov     edx, 0A3h
0x18001153f  mov     dword ptr [rsp+48h+var_28], r14d
0x180011544  mov     r9, rsi
0x180011547  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18001154e  mov     rcx, [rcx+10h]
0x180011552  call    WPP_SF_qD
0x180011557  lea     rdx, [rsp+48h+arg_10]; void **
0x18001155c  mov     rcx, rsi; void *
0x18001155f  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x180011564  test    al, al
0x180011566  jnz     short loc_1800115B7
0x180011568  mov     rcx, cs:WPP_GLOBAL_Control
0x18001156f  test    byte ptr [rcx+1Ch], 2
0x180011573  jz      short loc_180011593
0x180011575  cmp     byte ptr [rcx+19h], 2
0x180011579  jb      short loc_180011593
0x18001157b  mov     edx, 0A4h
0x180011580  mov     r9, rsi
0x180011583  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18001158a  mov     rcx, [rcx+10h]
0x18001158e  call    WPP_SF_q
0x180011593  mov     esi, 0C0000008h
0x180011598  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18001159f  jz      short loc_1800115B0
0x1800115a1  mov     r8d, esi
0x1800115a4  lea     rdx, SamRemoveMemberFromGroupExit
0x1800115ab  call    McTemplateU0d_EventWriteTransfer
0x1800115b0  mov     eax, esi
0x1800115b2  jmp     loc_1800116A8
0x1800115b7  mov     [rsp+48h+arg_18], 0
0x1800115c0  mov     dword ptr [rsp+48h+var_28], r14d
0x1800115c5  mov     r9, [rsp+48h+arg_10]
0x1800115ca  xor     r8d, r8d; pReturnValue
0x1800115cd  lea     edx, [r8+18h]; nProcNum
0x1800115d1  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800115d8  call    cs:__imp_NdrClientCall3
0x1800115de  mov     rbx, rax
0x1800115e1  mov     [rsp+48h+arg_18], rax
0x1800115e6  mov     [rsp+48h+var_18], eax
0x1800115ea  jmp     short loc_180011627
0x1800115ec  mov     ebx, eax
0x1800115ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115f5  test    byte ptr [rcx+1Ch], 2
0x1800115f9  jz      short loc_180011619
0x1800115fb  cmp     byte ptr [rcx+19h], 3
0x1800115ff  jb      short loc_180011619
0x180011601  mov     r9d, eax
0x180011604  mov     edx, 0A5h
0x180011609  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011610  mov     rcx, [rcx+10h]
0x180011614  call    WPP_SF_D
0x180011619  mov     ecx, ebx; Status
0x18001161b  call    cs:__imp_I_RpcMapWin32Status
0x180011621  mov     ebx, eax
0x180011623  mov     [rsp+48h+var_18], eax
0x180011627  mov     esi, 0C0000008h
0x18001162c  cmp     ebx, 0C0020003h
0x180011632  cmovz   ebx, esi
0x180011635  test    ebx, ebx
0x180011637  js      short loc_180011663
0x180011639  mov     rcx, cs:WPP_GLOBAL_Control
0x180011640  test    byte ptr [rcx+1Ch], 2
0x180011644  jz      short loc_18001168E
0x180011646  cmp     byte ptr [rcx+19h], 4
0x18001164a  jb      short loc_18001168E
0x18001164c  mov     edx, 0A6h
0x180011651  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011658  mov     rcx, [rcx+10h]
0x18001165c  call    WPP_SF_
0x180011661  jmp     short loc_18001168E
0x180011663  mov     rcx, cs:WPP_GLOBAL_Control
0x18001166a  test    byte ptr [rcx+1Ch], 2
0x18001166e  jz      short loc_18001168E
0x180011670  cmp     byte ptr [rcx+19h], 2
0x180011674  jb      short loc_18001168E
0x180011676  mov     edx, 0A7h
0x18001167b  mov     r9d, ebx
0x18001167e  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011685  mov     rcx, [rcx+10h]
0x180011689  call    WPP_SF_D
0x18001168e  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180011695  jz      short loc_1800116A6
0x180011697  mov     r8d, ebx
0x18001169a  lea     rdx, SamRemoveMemberFromGroupExit
0x1800116a1  call    McTemplateU0d_EventWriteTransfer
0x1800116a6  mov     eax, ebx
0x1800116a8  mov     rbx, [rsp+48h+arg_0]
0x1800116ad  mov     rsi, [rsp+48h+arg_8]
0x1800116b2  add     rsp, 40h
0x1800116b6  pop     r14
0x1800116b8  retn
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
