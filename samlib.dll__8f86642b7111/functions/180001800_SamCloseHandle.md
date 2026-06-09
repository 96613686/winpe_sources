# SamCloseHandle

- ea: `0x180001800`
- end: `0x180001a27`
- name: `SamCloseHandle`
- size: `551`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `10`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008104`
- `0x1800083a0`
- `0x180008590`
- `0x180008dc4`
- `0x180008f5c`
- `0x18000918c`
- `0x18000a5a0`
- `0x180010cf0`
- `0x1800127a0`
- `0x180015090`

## callees

- `0x180001800`
- `0x180003220`
- `0x180003370`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000c210`
- `0x180014a50`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001850`
- `RPCRT4!NdrClientCall3` at `0x1800018fd`
- `RPCRT4!NdrClientCall3` at `0x1800018fd`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001940`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001940`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18000195d`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18000195d`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017a1e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017a3a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017a1e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017a3a`

## pseudocode

```c
__int64 __fastcall SamCloseHandle(struct _SAMP_CLIENT_INFO *a1)
{
  unsigned __int16 *CallingProcessInfo; // rax
  __int64 v3; // rcx
  unsigned __int16 *v4; // rdi
  const wchar_t *v5; // r9
  PVOID v6; // rcx
  CLIENT_CALL_RETURN v8; // rax
  int Pointer; // ebx
  PVOID v10; // rcx
  struct _SAMP_CLIENT_INFO *v11; // [rsp+50h] [rbp+8h] BYREF
  void *ContextHandle; // [rsp+58h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+60h] [rbp+18h]

  v11 = a1;
  ContextHandle = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v4 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v5 = L"<unknown>";
      if ( CallingProcessInfo )
        v5 = CallingProcessInfo;
      McTemplateU0pz_EventWriteTransfer(v3, (const EVENT_DESCRIPTOR *)SamCloseHandleEntry, (__int64)a1, v5);
    }
    LocalFree(v4);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAu, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, a1);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, &ContextHandle) )
  {
    v13.Simple = 0;
    v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 1u, 0, &ContextHandle).Pointer;
    Pointer = (int)v8.Pointer;
    v13.Pointer = v8.Pointer;
    if ( SLODWORD(v8.Simple) < 0 && ContextHandle )
      RpcSsDestroyClientContext(&ContextHandle);
    SampFreeHandle(&v11);
    if ( Pointer == -1073610749 )
      Pointer = -1073741816;
    if ( Pointer < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xFu, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, Pointer);
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xEu, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(
        (__int64)v10,
        (const EVENT_DESCRIPTOR *)SamCloseHandleExit,
        (unsigned int)Pointer);
    return (unsigned int)Pointer;
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xBu, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v6, (const EVENT_DESCRIPTOR *)SamCloseHandleExit, 3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x180001800  mov     [rsp+arg_0], rcx
0x180001805  push    rbx
0x180001806  push    rsi
0x180001807  push    rdi
0x180001808  sub     rsp, 30h
0x18000180c  mov     rbx, rcx
0x18000180f  xor     esi, esi
0x180001811  mov     [rsp+48h+ContextHandle], rsi
0x180001816  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000181d  jz      short loc_180001856
0x18000181f  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x180001824  mov     rdi, rax
0x180001827  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000182e  jz      short loc_18000184D
0x180001830  lea     r9, aUnknown; "<unknown>"
0x180001837  test    rax, rax
0x18000183a  cmovnz  r9, rax
0x18000183e  mov     r8, rbx
0x180001841  lea     rdx, SamCloseHandleEntry
0x180001848  call    McTemplateU0pz_EventWriteTransfer
0x18000184d  mov     rcx, rdi; hMem
0x180001850  call    cs:__imp_LocalFree
0x180001856  mov     rcx, cs:WPP_GLOBAL_Control
0x18000185d  test    byte ptr [rcx+1Ch], 2
0x180001861  jz      short loc_180001881
0x180001863  cmp     byte ptr [rcx+19h], 4
0x180001867  jb      short loc_180001881
0x180001869  mov     edx, 0Ah
0x18000186e  mov     r9, rbx
0x180001871  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180001878  mov     rcx, [rcx+10h]
0x18000187c  call    WPP_SF_q
0x180001881  lea     rdx, [rsp+48h+ContextHandle]; void **
0x180001886  mov     rcx, rbx; void *
0x180001889  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000188e  test    al, al
0x180001890  jnz     short loc_1800018E4
0x180001892  mov     rcx, cs:WPP_GLOBAL_Control
0x180001899  test    byte ptr [rcx+1Ch], 2
0x18000189d  jz      short loc_1800018BD
0x18000189f  cmp     byte ptr [rcx+19h], 2
0x1800018a3  jb      short loc_1800018BD
0x1800018a5  mov     edx, 0Bh
0x1800018aa  mov     r9, rbx
0x1800018ad  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800018b4  mov     rcx, [rcx+10h]
0x1800018b8  call    WPP_SF_q
0x1800018bd  mov     edi, 0C0000008h
0x1800018c2  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800018c9  jz      short loc_1800018DA
0x1800018cb  mov     r8d, edi
0x1800018ce  lea     rdx, SamCloseHandleExit
0x1800018d5  call    McTemplateU0d_EventWriteTransfer
0x1800018da  mov     eax, edi
0x1800018dc  add     rsp, 30h
0x1800018e0  pop     rdi
0x1800018e1  pop     rsi
0x1800018e2  pop     rbx
0x1800018e3  retn
0x1800018e4  mov     [rsp+48h+arg_10], rsi
0x1800018e9  lea     r9, [rsp+48h+ContextHandle]
0x1800018ee  xor     r8d, r8d; pReturnValue
0x1800018f1  mov     edx, 1; nProcNum
0x1800018f6  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800018fd  call    cs:__imp_NdrClientCall3
0x180001903  mov     rbx, rax
0x180001906  mov     [rsp+48h+arg_10], rax
0x18000190b  mov     [rsp+48h+var_28], eax
0x18000190f  jmp     short loc_18000194C
0x180001911  mov     ebx, eax
0x180001913  mov     rcx, cs:WPP_GLOBAL_Control
0x18000191a  test    byte ptr [rcx+1Ch], 2
0x18000191e  jz      short loc_18000193E
0x180001920  cmp     byte ptr [rcx+19h], 3
0x180001924  jb      short loc_18000193E
0x180001926  mov     r9d, eax
0x180001929  mov     edx, 0Ch
0x18000192e  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180001935  mov     rcx, [rcx+10h]
0x180001939  call    WPP_SF_D
0x18000193e  mov     ecx, ebx; Status
0x180001940  call    cs:__imp_I_RpcMapWin32Status
0x180001946  mov     ebx, eax
0x180001948  mov     [rsp+48h+var_28], eax
0x18000194c  test    ebx, ebx
0x18000194e  jns     short loc_180001994
0x180001950  cmp     [rsp+48h+ContextHandle], 0
0x180001956  jz      short loc_180001994
0x180001958  lea     rcx, [rsp+48h+ContextHandle]; ContextHandle
0x18000195d  call    cs:__imp_RpcSsDestroyClientContext
0x180001963  jmp     short loc_180001994
0x180001965  mov     rcx, cs:WPP_GLOBAL_Control
0x18000196c  test    byte ptr [rcx+1Ch], 2
0x180001970  jz      short loc_180001990
0x180001972  cmp     byte ptr [rcx+19h], 3
0x180001976  jb      short loc_180001990
0x180001978  mov     r9d, eax
0x18000197b  mov     edx, 0Dh
0x180001980  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180001987  mov     rcx, [rcx+10h]
0x18000198b  call    WPP_SF_D
0x180001990  mov     ebx, [rsp+48h+var_28]
0x180001994  lea     rcx, [rsp+48h+arg_0]; struct _SAMP_CLIENT_INFO **
0x180001999  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x18000199e  mov     edi, 0C0000008h
0x1800019a3  cmp     ebx, 0C0020003h
0x1800019a9  cmovz   ebx, edi
0x1800019ac  test    ebx, ebx
0x1800019ae  js      short loc_1800019DA
0x1800019b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019b7  test    byte ptr [rcx+1Ch], 2
0x1800019bb  jz      short loc_180001A05
0x1800019bd  cmp     byte ptr [rcx+19h], 4
0x1800019c1  jb      short loc_180001A05
0x1800019c3  mov     edx, 0Eh
0x1800019c8  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800019cf  mov     rcx, [rcx+10h]
0x1800019d3  call    WPP_SF_
0x1800019d8  jmp     short loc_180001A05
0x1800019da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019e1  test    byte ptr [rcx+1Ch], 2
0x1800019e5  jz      short loc_180001A05
0x1800019e7  cmp     byte ptr [rcx+19h], 2
0x1800019eb  jb      short loc_180001A05
0x1800019ed  mov     edx, 0Fh
0x1800019f2  mov     r9d, ebx
0x1800019f5  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800019fc  mov     rcx, [rcx+10h]
0x180001a00  call    WPP_SF_D
0x180001a05  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001a0c  jz      short loc_180001A1D
0x180001a0e  mov     r8d, ebx
0x180001a11  lea     rdx, SamCloseHandleExit
0x180001a18  call    McTemplateU0d_EventWriteTransfer
0x180001a1d  mov     eax, ebx
0x180001a1f  add     rsp, 30h
0x180001a23  pop     rdi
0x180001a24  pop     rsi
0x180001a25  pop     rbx
0x180001a26  retn
0x180017a10  push    rbp
0x180017a12  sub     rsp, 20h
0x180017a16  mov     rbp, rdx
0x180017a19  mov     rcx, [rcx]
0x180017a1c  mov     ecx, [rcx]; ExceptionCode
0x180017a1e  call    cs:__imp_I_RpcExceptionFilter
0x180017a24  nop
0x180017a25  add     rsp, 20h
0x180017a29  pop     rbp
0x180017a2a  retn
0x180017a2c  push    rbp
0x180017a2e  sub     rsp, 20h
0x180017a32  mov     rbp, rdx
0x180017a35  mov     rcx, [rcx]
0x180017a38  mov     ecx, [rcx]; ExceptionCode
0x180017a3a  call    cs:__imp_I_RpcExceptionFilter
0x180017a40  nop
0x180017a41  add     rsp, 20h
0x180017a45  pop     rbp
0x180017a46  retn
```
