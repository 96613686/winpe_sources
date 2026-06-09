# SamOpenDomain

- ea: `0x180002a80`
- end: `0x180002e87`
- name: `SamOpenDomain`
- size: `1031`
- prototype: `__int64 __fastcall(void *, char, PSID pSid)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800083a0`
- `0x18000918c`
- `0x18000a5a0`
- `0x1800127a0`

## callees

- `0x180002a80`
- `0x180003220`
- `0x1800078c0`
- `0x18000807c`
- `0x18000baf8`
- `0x180014a50`
- `0x1800152bc`
- `0x180015a74`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002afe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002c97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002dc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ddb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002afe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002c97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002dc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ddb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002bf2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002bf2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c72`
- `ntdll!RtlValidSid` at `0x180002b91`
- `ntdll!RtlValidSid` at `0x180002b91`
- `ntdll!RtlLengthSid` at `0x180002c63`
- `ntdll!RtlLengthSid` at `0x180002c63`
- `ntdll!RtlCopySid` at `0x180002c89`
- `ntdll!RtlCopySid` at `0x180002c89`
- `RPCRT4!NdrClientCall3` at `0x180002d53`
- `RPCRT4!NdrClientCall3` at `0x180002d53`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002d96`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002d96`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017b4e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017b4e`

## pseudocode

```c
__int64 __fastcall SamOpenDomain(void *a1, int a2, PSID pSid, __int64 *a4)
{
  unsigned __int16 *CallingProcessInfo; // rax
  int v9; // edx
  unsigned __int16 *v10; // rbx
  const wchar_t *v11; // rcx
  PVOID v12; // rcx
  BOOLEAN valid; // al
  CLIENT_CALL_RETURN v15; // rbx
  __int64 v16; // rcx
  _QWORD *v17; // rdi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  PSID v20; // rbx
  SIZE_T v21; // rsi
  HLOCAL v22; // rax
  void *v23; // rcx
  __int64 v24; // r9
  char v25[8]; // [rsp+20h] [rbp-88h]
  void *v26; // [rsp+48h] [rbp-60h] BYREF
  __int64 v27; // [rsp+50h] [rbp-58h] BYREF
  CLIENT_CALL_RETURN v28; // [rsp+58h] [rbp-50h]
  _QWORD *v29; // [rsp+60h] [rbp-48h]

  v27 = 0;
  v26 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v10 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v11 = L"<unknown>";
      if ( CallingProcessInfo )
        v11 = CallingProcessInfo;
      McTemplateU0pqkz_EventWriteTransfer((_DWORD)v11, v9, (_DWORD)a1, a2, (__int64)pSid, (__int64)v11);
    }
    LocalFree(v10);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qD_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, pSid);
  if ( !SampIsValidClientHandle(a1, &v26) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0dp_EventWriteTransfer(v12, SamOpenDomainExit, 0, 0);
    return 3221225480LL;
  }
  valid = RtlValidSid(pSid);
  LODWORD(v15.Pointer) = 0;
  v16 = 3221225485LL;
  if ( !valid )
    LODWORD(v15.Pointer) = -1073741811;
  if ( SLODWORD(v15.Simple) < 0 )
  {
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
      return LODWORD(v15.Pointer);
    goto LABEL_61;
  }
  v17 = LocalAlloc(0x40u, 0x18u);
  v29 = v17;
  if ( !v17 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 44;
LABEL_37:
        WPP_SF_(v18[2], v19, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids);
        v18 = WPP_GLOBAL_Control;
        goto LABEL_38;
      }
      goto LABEL_38;
    }
    goto LABEL_41;
  }
  v20 = 0;
  *(_OWORD *)v17 = 0;
  v17[2] = 0;
  if ( a1 )
  {
    v17[1] = *((_QWORD *)a1 + 1);
    if ( *((_QWORD *)a1 + 2) )
      v20 = (PSID)*((_QWORD *)a1 + 2);
  }
  if ( pSid )
    v20 = pSid;
  if ( !v20 )
  {
LABEL_44:
    *a4 = 0;
    v28.Simple = 0;
    *(_DWORD *)v25 = a2;
    v15.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 7u, 0, v26, *(_QWORD *)v25, pSid, &v27).Pointer;
    v28.Pointer = v15.Pointer;
    if ( SLODWORD(v15.Simple) < 0 )
    {
      v23 = (void *)v17[2];
      if ( v23 )
        LocalFree(v23);
      *(_OWORD *)v17 = 0;
      v17[2] = 0;
      LocalFree(v17);
      v17 = 0;
    }
    else
    {
      *v17 = v27;
    }
    *a4 = (__int64)v17;
    if ( LODWORD(v15.Pointer) == -1073610749 )
      LODWORD(v15.Pointer) = -1073741816;
    if ( SLODWORD(v15.Simple) >= 0 )
    {
      v16 = (__int64)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, v17);
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
        return LODWORD(v15.Pointer);
      v24 = *a4;
      goto LABEL_62;
    }
    v16 = (__int64)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids,
        LODWORD(v15.Pointer));
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
      return LODWORD(v15.Pointer);
LABEL_61:
    v24 = 0;
LABEL_62:
    McTemplateU0dp_EventWriteTransfer(v16, SamOpenDomainExit, LODWORD(v15.Pointer), v24);
    return LODWORD(v15.Pointer);
  }
  v21 = RtlLengthSid(v20);
  v22 = LocalAlloc(0x40u, v21);
  v17[2] = v22;
  if ( v22 )
  {
    RtlCopySid(v21, v22, v20);
    goto LABEL_44;
  }
  LocalFree(v17);
  v18 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = 45;
      goto LABEL_37;
    }
LABEL_38:
    if ( (*((_BYTE *)v18 + 28) & 2) != 0 && *((_BYTE *)v18 + 25) >= 2u )
      WPP_SF_D(v18[2], 30, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, 3221225495LL);
  }
LABEL_41:
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dp_EventWriteTransfer(v18, SamOpenDomainExit, 3221225495LL, 0);
  return 3221225495LL;
}

```

## disassembly

```asm
0x180002a80  mov     [rsp+arg_18], r9
0x180002a85  mov     [rsp+arg_10], r8
0x180002a8a  mov     [rsp+arg_8], edx
0x180002a8e  mov     [rsp+arg_0], rcx
0x180002a93  push    rbx
0x180002a94  push    rsi
0x180002a95  push    rdi
0x180002a96  push    r12
0x180002a98  push    r14
0x180002a9a  push    r15
0x180002a9c  sub     rsp, 78h
0x180002aa0  mov     r15, r9
0x180002aa3  mov     r14, r8
0x180002aa6  mov     r12d, edx
0x180002aa9  mov     rsi, rcx
0x180002aac  mov     [rsp+0A8h+var_58], 0
0x180002ab5  mov     [rsp+0A8h+var_60], 0
0x180002abe  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002ac5  jz      short loc_180002B04
0x180002ac7  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x180002acc  mov     rbx, rax
0x180002acf  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002ad6  jz      short loc_180002AFB
0x180002ad8  lea     rcx, aUnknown; "<unknown>"
0x180002adf  test    rax, rax
0x180002ae2  cmovnz  rcx, rax
0x180002ae6  mov     [rsp+0A8h+pSid], rcx
0x180002aeb  mov     qword ptr [rsp+0A8h+var_88], r14
0x180002af0  mov     r9d, r12d
0x180002af3  mov     r8, rsi
0x180002af6  call    McTemplateU0pqkz_EventWriteTransfer
0x180002afb  mov     rcx, rbx; hMem
0x180002afe  call    cs:__imp_LocalFree
0x180002b04  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b0b  test    byte ptr [rcx+1Ch], 2
0x180002b0f  jz      short loc_180002B2D
0x180002b11  cmp     byte ptr [rcx+19h], 4
0x180002b15  jb      short loc_180002B2D
0x180002b17  mov     [rsp+0A8h+pSid], r14; pSid
0x180002b1c  mov     dword ptr [rsp+0A8h+var_88], r12d; char
0x180002b21  mov     r9, rsi
0x180002b24  mov     rcx, [rcx+10h]; LoggerHandle
0x180002b28  call    WPP_SF_qD_sid_
0x180002b2d  lea     rdx, [rsp+0A8h+var_60]; void **
0x180002b32  mov     rcx, rsi; void *
0x180002b35  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x180002b3a  test    al, al
0x180002b3c  jnz     short loc_180002B8E
0x180002b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b45  test    byte ptr [rcx+1Ch], 2
0x180002b49  jz      short loc_180002B69
0x180002b4b  cmp     byte ptr [rcx+19h], 2
0x180002b4f  jb      short loc_180002B69
0x180002b51  mov     edx, 1Dh
0x180002b56  mov     r9, rsi
0x180002b59  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180002b60  mov     rcx, [rcx+10h]
0x180002b64  call    WPP_SF_q
0x180002b69  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002b70  jz      short loc_180002B84
0x180002b72  xor     r9d, r9d
0x180002b75  xor     r8d, r8d
0x180002b78  lea     rdx, SamOpenDomainExit
0x180002b7f  call    McTemplateU0dp_EventWriteTransfer
0x180002b84  mov     eax, 0C0000008h
0x180002b89  jmp     loc_180002E79
0x180002b8e  mov     rcx, r14; Sid
0x180002b91  call    cs:__imp_RtlValidSid
0x180002b97  xor     ebx, ebx
0x180002b99  mov     ecx, 0C000000Dh
0x180002b9e  test    al, al
0x180002ba0  cmovz   ebx, ecx
0x180002ba3  mov     [rsp+0A8h+var_68], ebx
0x180002ba7  jmp     short loc_180002BD2
0x180002ba9  mov     ebx, 0C000000Dh
0x180002bae  mov     [rsp+0A8h+var_68], ebx
0x180002bb2  mov     r15, [rsp+0A8h+arg_18]
0x180002bba  mov     r14, [rsp+0A8h+arg_10]
0x180002bc2  mov     r12d, [rsp+0A8h+arg_8]
0x180002bca  mov     rsi, [rsp+0A8h+arg_0]
0x180002bd2  test    ebx, ebx
0x180002bd4  jns     short loc_180002BE8
0x180002bd6  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002bdd  jnz     loc_180002E65
0x180002be3  jmp     loc_180002E77
0x180002be8  mov     edx, 18h; uBytes
0x180002bed  mov     ecx, 40h ; '@'; uFlags
0x180002bf2  call    cs:__imp_LocalAlloc
0x180002bf8  mov     rdi, rax
0x180002bfb  mov     [rsp+0A8h+var_48], rax
0x180002c00  test    rax, rax
0x180002c03  jnz     short loc_180002C2A
0x180002c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c0c  test    byte ptr [rcx+1Ch], 2
0x180002c10  jz      loc_180002CF3
0x180002c16  cmp     byte ptr [rcx+19h], 2
0x180002c1a  jb      loc_180002CCC
0x180002c20  mov     edx, 2Ch ; ','
0x180002c25  jmp     loc_180002CB5
0x180002c2a  xor     ebx, ebx
0x180002c2c  xorps   xmm0, xmm0
0x180002c2f  xor     eax, eax
0x180002c31  movups  xmmword ptr [rdi], xmm0
0x180002c34  mov     [rdi+10h], rax
0x180002c38  test    rsi, rsi
0x180002c3b  jz      short loc_180002C50
0x180002c3d  mov     rax, [rsi+8]
0x180002c41  mov     [rdi+8], rax
0x180002c45  mov     rax, [rsi+10h]
0x180002c49  test    rax, rax
0x180002c4c  cmovnz  rbx, rax
0x180002c50  test    r14, r14
0x180002c53  cmovnz  rbx, r14
0x180002c57  test    rbx, rbx
0x180002c5a  jz      loc_180002D1B
0x180002c60  mov     rcx, rbx; Sid
0x180002c63  call    cs:__imp_RtlLengthSid
0x180002c69  mov     esi, eax
0x180002c6b  mov     edx, eax; uBytes
0x180002c6d  mov     ecx, 40h ; '@'; uFlags
0x180002c72  call    cs:__imp_LocalAlloc
0x180002c78  mov     [rdi+10h], rax
0x180002c7c  test    rax, rax
0x180002c7f  jz      short loc_180002C94
0x180002c81  mov     r8, rbx; SourceSid
0x180002c84  mov     rdx, rax; DestinationSid
0x180002c87  mov     ecx, esi; DestinationSidLength
0x180002c89  call    cs:__imp_RtlCopySid
0x180002c8f  jmp     loc_180002D1B
0x180002c94  mov     rcx, rdi; hMem
0x180002c97  call    cs:__imp_LocalFree
0x180002c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ca4  test    byte ptr [rcx+1Ch], 2
0x180002ca8  jz      short loc_180002CF3
0x180002caa  cmp     byte ptr [rcx+19h], 2
0x180002cae  jb      short loc_180002CCC
0x180002cb0  mov     edx, 2Dh ; '-'
0x180002cb5  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180002cbc  mov     rcx, [rcx+10h]
0x180002cc0  call    WPP_SF_
0x180002cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ccc  test    byte ptr [rcx+1Ch], 2
0x180002cd0  jz      short loc_180002CF3
0x180002cd2  cmp     byte ptr [rcx+19h], 2
0x180002cd6  jb      short loc_180002CF3
0x180002cd8  mov     edx, 1Eh
0x180002cdd  mov     r9d, 0C0000017h
0x180002ce3  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180002cea  mov     rcx, [rcx+10h]
0x180002cee  call    WPP_SF_D
0x180002cf3  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002cfa  jz      short loc_180002D11
0x180002cfc  xor     r9d, r9d
0x180002cff  mov     r8d, 0C0000017h
0x180002d05  lea     rdx, SamOpenDomainExit
0x180002d0c  call    McTemplateU0dp_EventWriteTransfer
0x180002d11  mov     eax, 0C0000017h
0x180002d16  jmp     loc_180002E79
0x180002d1b  mov     qword ptr [r15], 0
0x180002d22  mov     [rsp+0A8h+var_50], 0
0x180002d2b  lea     rax, [rsp+0A8h+var_58]
0x180002d30  mov     [rsp+0A8h+var_78], rax
0x180002d35  mov     [rsp+0A8h+pSid], r14
0x180002d3a  mov     dword ptr [rsp+0A8h+var_88], r12d
0x180002d3f  mov     r9, [rsp+0A8h+var_60]
0x180002d44  xor     r8d, r8d; pReturnValue
0x180002d47  mov     edx, 7; nProcNum
0x180002d4c  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180002d53  call    cs:__imp_NdrClientCall3
0x180002d59  mov     rbx, rax
0x180002d5c  mov     [rsp+0A8h+var_50], rax
0x180002d61  mov     [rsp+0A8h+var_68], eax
0x180002d65  jmp     short loc_180002DAF
0x180002d67  mov     ebx, eax
0x180002d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d70  test    byte ptr [rcx+1Ch], 2
0x180002d74  jz      short loc_180002D94
0x180002d76  cmp     byte ptr [rcx+19h], 3
0x180002d7a  jb      short loc_180002D94
0x180002d7c  mov     r9d, eax
0x180002d7f  mov     edx, 1Fh
0x180002d84  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180002d8b  mov     rcx, [rcx+10h]
0x180002d8f  call    WPP_SF_D
0x180002d94  mov     ecx, ebx; Status
0x180002d96  call    cs:__imp_I_RpcMapWin32Status
0x180002d9c  mov     ebx, eax
0x180002d9e  mov     [rsp+0A8h+var_68], eax
0x180002da2  mov     r15, [rsp+0A8h+arg_18]
0x180002daa  mov     rdi, [rsp+0A8h+var_48]
0x180002daf  test    ebx, ebx
0x180002db1  js      short loc_180002DBD
0x180002db3  mov     rax, [rsp+0A8h+var_58]
0x180002db8  mov     [rdi], rax
0x180002dbb  jmp     short loc_180002DE3
0x180002dbd  mov     rcx, [rdi+10h]; hMem
0x180002dc1  test    rcx, rcx
0x180002dc4  jz      short loc_180002DCC
0x180002dc6  call    cs:__imp_LocalFree
0x180002dcc  xorps   xmm0, xmm0
0x180002dcf  xor     eax, eax
0x180002dd1  movups  xmmword ptr [rdi], xmm0
0x180002dd4  mov     [rdi+10h], rax
0x180002dd8  mov     rcx, rdi; hMem
0x180002ddb  call    cs:__imp_LocalFree
0x180002de1  xor     edi, edi
0x180002de3  mov     [r15], rdi
0x180002de6  mov     eax, 0C0000008h
0x180002deb  cmp     ebx, 0C0020003h
0x180002df1  cmovz   ebx, eax
0x180002df4  test    ebx, ebx
0x180002df6  js      short loc_180002E31
0x180002df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dff  test    byte ptr [rcx+1Ch], 2
0x180002e03  jz      short loc_180002E23
0x180002e05  cmp     byte ptr [rcx+19h], 4
0x180002e09  jb      short loc_180002E23
0x180002e0b  mov     edx, 20h ; ' '
0x180002e10  mov     r9, rdi
0x180002e13  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180002e1a  mov     rcx, [rcx+10h]
0x180002e1e  call    WPP_SF_q
0x180002e23  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002e2a  jz      short loc_180002E77
0x180002e2c  mov     r9, [r15]
0x180002e2f  jmp     short loc_180002E68
0x180002e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e38  test    byte ptr [rcx+1Ch], 2
0x180002e3c  jz      short loc_180002E5C
0x180002e3e  cmp     byte ptr [rcx+19h], 2
0x180002e42  jb      short loc_180002E5C
0x180002e44  mov     edx, 21h ; '!'
0x180002e49  mov     r9d, ebx
0x180002e4c  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180002e53  mov     rcx, [rcx+10h]
0x180002e57  call    WPP_SF_D
0x180002e5c  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002e63  jz      short loc_180002E77
0x180002e65  xor     r9d, r9d
0x180002e68  mov     r8d, ebx
0x180002e6b  lea     rdx, SamOpenDomainExit
0x180002e72  call    McTemplateU0dp_EventWriteTransfer
0x180002e77  mov     eax, ebx
0x180002e79  add     rsp, 78h
0x180002e7d  pop     r15
0x180002e7f  pop     r14
0x180002e81  pop     r12
0x180002e83  pop     rdi
0x180002e84  pop     rsi
0x180002e85  pop     rbx
0x180002e86  retn
0x180017b40  push    rbp
0x180017b42  sub     rsp, 40h
0x180017b46  mov     rbp, rdx
0x180017b49  mov     rcx, [rcx]
0x180017b4c  mov     ecx, [rcx]; ExceptionCode
0x180017b4e  call    cs:__imp_I_RpcExceptionFilter
0x180017b54  nop
0x180017b55  add     rsp, 40h
0x180017b59  pop     rbp
0x180017b5a  retn
```
