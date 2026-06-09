# SamDeleteUser

- ea: `0x18000e4e0`
- end: `0x18000e6cb`
- name: `SamDeleteUser`
- size: `491`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000d930`

## callees

- `0x180003220`
- `0x180003370`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000c210`
- `0x18000e4e0`
- `0x180014a50`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e535`
- `RPCRT4!NdrClientCall3` at `0x18000e5e2`
- `RPCRT4!NdrClientCall3` at `0x18000e5e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e625`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e625`

## pseudocode

```c
__int64 __fastcall SamDeleteUser(struct _SAMP_CLIENT_INFO *a1)
{
  unsigned __int16 *CallingProcessInfo; // rax
  __int64 v3; // rcx
  unsigned __int16 *v4; // rdi
  const wchar_t *v5; // r9
  PVOID v6; // rcx
  CLIENT_CALL_RETURN v8; // rax
  unsigned int Pointer; // ebx
  PVOID v10; // rcx
  struct _SAMP_CLIENT_INFO *v11; // [rsp+40h] [rbp+8h] BYREF
  void *v12; // [rsp+48h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+50h] [rbp+18h]

  v11 = a1;
  v12 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v4 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v5 = L"<unknown>";
      if ( CallingProcessInfo )
        v5 = CallingProcessInfo;
      McTemplateU0pz_EventWriteTransfer(v3, (const EVENT_DESCRIPTOR *)SamDeleteUserEntry, (__int64)a1, v5);
    }
    LocalFree(v4);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, &v12) )
  {
    v13.Simple = 0;
    v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x23u, 0, &v12).Pointer;
    Pointer = (unsigned int)v8.Pointer;
    v13.Pointer = v8.Pointer;
    if ( SLODWORD(v8.Simple) >= 0 )
      SampFreeHandle(&v11);
    if ( Pointer == -1073610749 )
      Pointer = -1073741816;
    if ( (Pointer & 0x80000000) != 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v10, (const EVENT_DESCRIPTOR *)SamDeleteUserExit, Pointer);
    return Pointer;
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v6, (const EVENT_DESCRIPTOR *)SamDeleteUserExit, 3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x18000e4e0  mov     [rsp+arg_18], rbx
0x18000e4e5  mov     [rsp+arg_0], rcx
0x18000e4ea  push    rdi
0x18000e4eb  sub     rsp, 30h
0x18000e4ef  mov     rbx, rcx
0x18000e4f2  mov     [rsp+38h+arg_8], 0
0x18000e4fb  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e502  jz      short loc_18000E53B
0x18000e504  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000e509  mov     rdi, rax
0x18000e50c  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e513  jz      short loc_18000E532
0x18000e515  lea     r9, aUnknown; "<unknown>"
0x18000e51c  test    rax, rax
0x18000e51f  cmovnz  r9, rax
0x18000e523  mov     r8, rbx
0x18000e526  lea     rdx, SamDeleteUserEntry
0x18000e52d  call    McTemplateU0pz_EventWriteTransfer
0x18000e532  mov     rcx, rdi; hMem
0x18000e535  call    cs:__imp_LocalFree
0x18000e53b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e542  test    byte ptr [rcx+1Ch], 2
0x18000e546  jz      short loc_18000E566
0x18000e548  cmp     byte ptr [rcx+19h], 4
0x18000e54c  jb      short loc_18000E566
0x18000e54e  mov     edx, 0E9h
0x18000e553  mov     r9, rbx
0x18000e556  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e55d  mov     rcx, [rcx+10h]
0x18000e561  call    WPP_SF_q
0x18000e566  lea     rdx, [rsp+38h+arg_8]; void **
0x18000e56b  mov     rcx, rbx; void *
0x18000e56e  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000e573  test    al, al
0x18000e575  jnz     short loc_18000E5C6
0x18000e577  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e57e  test    byte ptr [rcx+1Ch], 2
0x18000e582  jz      short loc_18000E5A2
0x18000e584  cmp     byte ptr [rcx+19h], 2
0x18000e588  jb      short loc_18000E5A2
0x18000e58a  mov     edx, 0EAh
0x18000e58f  mov     r9, rbx
0x18000e592  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e599  mov     rcx, [rcx+10h]
0x18000e59d  call    WPP_SF_q
0x18000e5a2  mov     edi, 0C0000008h
0x18000e5a7  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e5ae  jz      short loc_18000E5BF
0x18000e5b0  mov     r8d, edi
0x18000e5b3  lea     rdx, SamDeleteUserExit
0x18000e5ba  call    McTemplateU0d_EventWriteTransfer
0x18000e5bf  mov     eax, edi
0x18000e5c1  jmp     loc_18000E6C0
0x18000e5c6  mov     [rsp+38h+arg_10], 0
0x18000e5cf  lea     r9, [rsp+38h+arg_8]
0x18000e5d4  xor     r8d, r8d; pReturnValue
0x18000e5d7  lea     edx, [r8+23h]; nProcNum
0x18000e5db  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000e5e2  call    cs:__imp_NdrClientCall3
0x18000e5e8  mov     rbx, rax
0x18000e5eb  mov     [rsp+38h+arg_10], rax
0x18000e5f0  mov     [rsp+38h+var_18], eax
0x18000e5f4  jmp     short loc_18000E631
0x18000e5f6  mov     ebx, eax
0x18000e5f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5ff  test    byte ptr [rcx+1Ch], 2
0x18000e603  jz      short loc_18000E623
0x18000e605  cmp     byte ptr [rcx+19h], 3
0x18000e609  jb      short loc_18000E623
0x18000e60b  mov     r9d, eax
0x18000e60e  mov     edx, 0EBh
0x18000e613  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e61a  mov     rcx, [rcx+10h]
0x18000e61e  call    WPP_SF_D
0x18000e623  mov     ecx, ebx; Status
0x18000e625  call    cs:__imp_I_RpcMapWin32Status
0x18000e62b  mov     ebx, eax
0x18000e62d  mov     [rsp+38h+var_18], eax
0x18000e631  test    ebx, ebx
0x18000e633  js      short loc_18000E63F
0x18000e635  lea     rcx, [rsp+38h+arg_0]; struct _SAMP_CLIENT_INFO **
0x18000e63a  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x18000e63f  mov     edi, 0C0000008h
0x18000e644  cmp     ebx, 0C0020003h
0x18000e64a  cmovz   ebx, edi
0x18000e64d  test    ebx, ebx
0x18000e64f  js      short loc_18000E67B
0x18000e651  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e658  test    byte ptr [rcx+1Ch], 2
0x18000e65c  jz      short loc_18000E6A6
0x18000e65e  cmp     byte ptr [rcx+19h], 4
0x18000e662  jb      short loc_18000E6A6
0x18000e664  mov     edx, 0ECh
0x18000e669  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e670  mov     rcx, [rcx+10h]
0x18000e674  call    WPP_SF_
0x18000e679  jmp     short loc_18000E6A6
0x18000e67b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e682  test    byte ptr [rcx+1Ch], 2
0x18000e686  jz      short loc_18000E6A6
0x18000e688  cmp     byte ptr [rcx+19h], 2
0x18000e68c  jb      short loc_18000E6A6
0x18000e68e  mov     edx, 0EDh
0x18000e693  mov     r9d, ebx
0x18000e696  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e69d  mov     rcx, [rcx+10h]
0x18000e6a1  call    WPP_SF_D
0x18000e6a6  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e6ad  jz      short loc_18000E6BE
0x18000e6af  mov     r8d, ebx
0x18000e6b2  lea     rdx, SamDeleteUserExit
0x18000e6b9  call    McTemplateU0d_EventWriteTransfer
0x18000e6be  mov     eax, ebx
0x18000e6c0  mov     rbx, [rsp+38h+arg_18]
0x18000e6c5  add     rsp, 30h
0x18000e6c9  pop     rdi
0x18000e6ca  retn
0x180017e00  push    rbp
0x180017e02  sub     rsp, 20h
0x180017e06  mov     rbp, rdx
0x180017e09  mov     rcx, [rcx]
0x180017e0c  mov     ecx, [rcx]; ExceptionCode
0x180017e0e  call    cs:__imp_I_RpcExceptionFilter
0x180017e14  nop
0x180017e15  add     rsp, 20h
0x180017e19  pop     rbp
0x180017e1a  retn
```
