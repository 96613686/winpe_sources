# SamRemoveMultipleMembersFromAlias

- ea: `0x1800116c0`
- end: `0x1800118ff`
- name: `SamRemoveMultipleMembersFromAlias`
- size: `575`
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
- `0x1800116c0`
- `0x180014a50`
- `0x180014a90`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001172a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001172a`
- `RPCRT4!NdrClientCall3` at `0x18001181d`
- `RPCRT4!NdrClientCall3` at `0x18001181d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180011863`
- `RPCRT4!I_RpcMapWin32Status` at `0x180011863`

## pseudocode

```c
__int64 __fastcall SamRemoveMultipleMembersFromAlias(void **a1, __int64 a2, int a3)
{
  unsigned __int16 *CallingProcessInfo; // rax
  unsigned __int16 *v7; // rbx
  const wchar_t *v8; // rcx
  PVOID v9; // rcx
  PVOID v11; // rcx
  CLIENT_CALL_RETURN v12; // rax
  unsigned int Pointer; // ebx
  PVOID v14; // rcx
  __int128 v15; // [rsp+38h] [rbp-30h] BYREF
  void *v16; // [rsp+78h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v17; // [rsp+88h] [rbp+20h]

  v16 = 0;
  v15 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v7 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v8 = L"<unknown>";
      if ( CallingProcessInfo )
        v8 = CallingProcessInfo;
      McTemplateU0pqz_EventWriteTransfer(
        (__int64)v8,
        (const EVENT_DESCRIPTOR *)SamRemoveMultipleMembersFromAliasEntry,
        (__int64)a1,
        a3,
        v8);
    }
    LocalFree(v7);
  }
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1, a3);
  if ( a2 )
  {
    if ( (unsigned __int8)SampIsValidClientHandle(a1, &v16) )
    {
      LODWORD(v15) = a3;
      *((_QWORD *)&v15 + 1) = a2;
      v17.Simple = 0;
      v12.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x35u, 0, v16, &v15).Pointer;
      Pointer = (unsigned int)v12.Pointer;
      v17.Pointer = v12.Pointer;
      if ( LODWORD(v12.Pointer) == -1073610749 )
        Pointer = -1073741816;
      if ( (Pointer & 0x80000000) != 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
      }
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
        McTemplateU0d_EventWriteTransfer(
          (__int64)v14,
          (const EVENT_DESCRIPTOR *)SamRemoveMultipleMembersFromAliasExit,
          Pointer);
      return Pointer;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
        McTemplateU0d_EventWriteTransfer(
          (__int64)v11,
          (const EVENT_DESCRIPTOR *)SamRemoveMultipleMembersFromAliasExit,
          3221225480LL);
      return 3221225480LL;
    }
  }
  else
  {
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(
        (__int64)v9,
        (const EVENT_DESCRIPTOR *)SamRemoveMultipleMembersFromAliasExit,
        3221225712LL);
    return 3221225712LL;
  }
}

```

## disassembly

```asm
0x1800116c0  mov     [rsp+arg_0], rbx
0x1800116c5  push    rsi
0x1800116c6  push    r12
0x1800116c8  push    r15
0x1800116ca  sub     rsp, 50h
0x1800116ce  mov     r15d, r8d
0x1800116d1  mov     r12, rdx
0x1800116d4  mov     rsi, rcx
0x1800116d7  mov     [rsp+68h+arg_8], 0
0x1800116e0  xorps   xmm0, xmm0
0x1800116e3  movups  [rsp+68h+var_30], xmm0
0x1800116e8  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800116ef  jz      short loc_180011730
0x1800116f1  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x1800116f6  mov     rbx, rax
0x1800116f9  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180011700  jz      short loc_180011727
0x180011702  lea     rcx, aUnknown; "<unknown>"
0x180011709  test    rax, rax
0x18001170c  cmovnz  rcx, rax
0x180011710  mov     [rsp+68h+var_48], rcx
0x180011715  mov     r9d, r15d
0x180011718  mov     r8, rsi
0x18001171b  lea     rdx, SamRemoveMultipleMembersFromAliasEntry
0x180011722  call    McTemplateU0pqz_EventWriteTransfer
0x180011727  mov     rcx, rbx; hMem
0x18001172a  call    cs:__imp_LocalFree
0x180011730  mov     rcx, cs:WPP_GLOBAL_Control
0x180011737  test    byte ptr [rcx+1Ch], 2
0x18001173b  jz      short loc_180011760
0x18001173d  cmp     byte ptr [rcx+19h], 4
0x180011741  jb      short loc_180011760
0x180011743  mov     edx, 0DFh
0x180011748  mov     dword ptr [rsp+68h+var_48], r15d
0x18001174d  mov     r9, rsi
0x180011750  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011757  mov     rcx, [rcx+10h]
0x18001175b  call    WPP_SF_qD
0x180011760  test    r12, r12
0x180011763  jnz     short loc_18001178A
0x180011765  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18001176c  jz      short loc_180011780
0x18001176e  mov     r8d, 0C00000F0h
0x180011774  lea     rdx, SamRemoveMultipleMembersFromAliasExit
0x18001177b  call    McTemplateU0d_EventWriteTransfer
0x180011780  mov     eax, 0C00000F0h
0x180011785  jmp     loc_1800118F0
0x18001178a  lea     rdx, [rsp+68h+arg_8]; void **
0x18001178f  mov     rcx, rsi; void *
0x180011792  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x180011797  test    al, al
0x180011799  jnz     short loc_1800117EA
0x18001179b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117a2  test    byte ptr [rcx+1Ch], 2
0x1800117a6  jz      short loc_1800117C6
0x1800117a8  cmp     byte ptr [rcx+19h], 2
0x1800117ac  jb      short loc_1800117C6
0x1800117ae  mov     edx, 0E0h
0x1800117b3  mov     r9, rsi
0x1800117b6  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800117bd  mov     rcx, [rcx+10h]
0x1800117c1  call    WPP_SF_q
0x1800117c6  mov     esi, 0C0000008h
0x1800117cb  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800117d2  jz      short loc_1800117E3
0x1800117d4  mov     r8d, esi
0x1800117d7  lea     rdx, SamRemoveMultipleMembersFromAliasExit
0x1800117de  call    McTemplateU0d_EventWriteTransfer
0x1800117e3  mov     eax, esi
0x1800117e5  jmp     loc_1800118F0
0x1800117ea  mov     dword ptr [rsp+68h+var_30], r15d
0x1800117ef  mov     qword ptr [rsp+68h+var_30+8], r12
0x1800117f4  mov     [rsp+68h+arg_18], 0
0x180011800  lea     rax, [rsp+68h+var_30]
0x180011805  mov     [rsp+68h+var_48], rax
0x18001180a  mov     r9, [rsp+68h+arg_8]
0x18001180f  xor     r8d, r8d; pReturnValue
0x180011812  lea     edx, [r8+35h]; nProcNum
0x180011816  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001181d  call    cs:__imp_NdrClientCall3
0x180011823  mov     rbx, rax
0x180011826  mov     [rsp+68h+arg_18], rax
0x18001182e  mov     [rsp+68h+var_38], eax
0x180011832  jmp     short loc_18001186F
0x180011834  mov     ebx, eax
0x180011836  mov     rcx, cs:WPP_GLOBAL_Control
0x18001183d  test    byte ptr [rcx+1Ch], 2
0x180011841  jz      short loc_180011861
0x180011843  cmp     byte ptr [rcx+19h], 3
0x180011847  jb      short loc_180011861
0x180011849  mov     r9d, eax
0x18001184c  mov     edx, 0E1h
0x180011851  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180011858  mov     rcx, [rcx+10h]
0x18001185c  call    WPP_SF_D
0x180011861  mov     ecx, ebx; Status
0x180011863  call    cs:__imp_I_RpcMapWin32Status
0x180011869  mov     ebx, eax
0x18001186b  mov     [rsp+68h+var_38], eax
0x18001186f  mov     esi, 0C0000008h
0x180011874  cmp     ebx, 0C0020003h
0x18001187a  cmovz   ebx, esi
0x18001187d  test    ebx, ebx
0x18001187f  js      short loc_1800118AB
0x180011881  mov     rcx, cs:WPP_GLOBAL_Control
0x180011888  test    byte ptr [rcx+1Ch], 2
0x18001188c  jz      short loc_1800118D6
0x18001188e  cmp     byte ptr [rcx+19h], 4
0x180011892  jb      short loc_1800118D6
0x180011894  mov     edx, 0E2h
0x180011899  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800118a0  mov     rcx, [rcx+10h]
0x1800118a4  call    WPP_SF_
0x1800118a9  jmp     short loc_1800118D6
0x1800118ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118b2  test    byte ptr [rcx+1Ch], 2
0x1800118b6  jz      short loc_1800118D6
0x1800118b8  cmp     byte ptr [rcx+19h], 2
0x1800118bc  jb      short loc_1800118D6
0x1800118be  mov     edx, 0E3h
0x1800118c3  mov     r9d, ebx
0x1800118c6  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800118cd  mov     rcx, [rcx+10h]
0x1800118d1  call    WPP_SF_D
0x1800118d6  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800118dd  jz      short loc_1800118EE
0x1800118df  mov     r8d, ebx
0x1800118e2  lea     rdx, SamRemoveMultipleMembersFromAliasExit
0x1800118e9  call    McTemplateU0d_EventWriteTransfer
0x1800118ee  mov     eax, ebx
0x1800118f0  mov     rbx, [rsp+68h+arg_0]
0x1800118f5  add     rsp, 50h
0x1800118f9  pop     r15
0x1800118fb  pop     r12
0x1800118fd  pop     rsi
0x1800118fe  retn
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
