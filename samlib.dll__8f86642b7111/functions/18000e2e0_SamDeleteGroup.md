# SamDeleteGroup

- ea: `0x18000e2e0`
- end: `0x18000e4cb`
- name: `SamDeleteGroup`
- size: `491`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003220`
- `0x180003370`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000c210`
- `0x18000e2e0`
- `0x180014a50`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e335`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e335`
- `RPCRT4!NdrClientCall3` at `0x18000e3e2`
- `RPCRT4!NdrClientCall3` at `0x18000e3e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e425`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e425`

## pseudocode

```c
__int64 __fastcall SamDeleteGroup(struct _SAMP_CLIENT_INFO *a1)
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
      McTemplateU0pz_EventWriteTransfer(v3, (const EVENT_DESCRIPTOR *)SamDeleteGroupEntry, (__int64)a1, v5);
    }
    LocalFree(v4);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, &v12) )
  {
    v13.Simple = 0;
    v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x17u, 0, &v12).Pointer;
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
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v10, (const EVENT_DESCRIPTOR *)SamDeleteGroupExit, Pointer);
    return Pointer;
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v6, (const EVENT_DESCRIPTOR *)SamDeleteGroupExit, 3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x18000e2e0  mov     [rsp+arg_18], rbx
0x18000e2e5  mov     [rsp+arg_0], rcx
0x18000e2ea  push    rdi
0x18000e2eb  sub     rsp, 30h
0x18000e2ef  mov     rbx, rcx
0x18000e2f2  mov     [rsp+38h+arg_8], 0
0x18000e2fb  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e302  jz      short loc_18000E33B
0x18000e304  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000e309  mov     rdi, rax
0x18000e30c  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e313  jz      short loc_18000E332
0x18000e315  lea     r9, aUnknown; "<unknown>"
0x18000e31c  test    rax, rax
0x18000e31f  cmovnz  r9, rax
0x18000e323  mov     r8, rbx
0x18000e326  lea     rdx, SamDeleteGroupEntry
0x18000e32d  call    McTemplateU0pz_EventWriteTransfer
0x18000e332  mov     rcx, rdi; hMem
0x18000e335  call    cs:__imp_LocalFree
0x18000e33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e342  test    byte ptr [rcx+1Ch], 2
0x18000e346  jz      short loc_18000E366
0x18000e348  cmp     byte ptr [rcx+19h], 4
0x18000e34c  jb      short loc_18000E366
0x18000e34e  mov     edx, 9Eh
0x18000e353  mov     r9, rbx
0x18000e356  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e35d  mov     rcx, [rcx+10h]
0x18000e361  call    WPP_SF_q
0x18000e366  lea     rdx, [rsp+38h+arg_8]; void **
0x18000e36b  mov     rcx, rbx; void *
0x18000e36e  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000e373  test    al, al
0x18000e375  jnz     short loc_18000E3C6
0x18000e377  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e37e  test    byte ptr [rcx+1Ch], 2
0x18000e382  jz      short loc_18000E3A2
0x18000e384  cmp     byte ptr [rcx+19h], 2
0x18000e388  jb      short loc_18000E3A2
0x18000e38a  mov     edx, 9Fh
0x18000e38f  mov     r9, rbx
0x18000e392  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e399  mov     rcx, [rcx+10h]
0x18000e39d  call    WPP_SF_q
0x18000e3a2  mov     edi, 0C0000008h
0x18000e3a7  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e3ae  jz      short loc_18000E3BF
0x18000e3b0  mov     r8d, edi
0x18000e3b3  lea     rdx, SamDeleteGroupExit
0x18000e3ba  call    McTemplateU0d_EventWriteTransfer
0x18000e3bf  mov     eax, edi
0x18000e3c1  jmp     loc_18000E4C0
0x18000e3c6  mov     [rsp+38h+arg_10], 0
0x18000e3cf  lea     r9, [rsp+38h+arg_8]
0x18000e3d4  xor     r8d, r8d; pReturnValue
0x18000e3d7  lea     edx, [r8+17h]; nProcNum
0x18000e3db  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000e3e2  call    cs:__imp_NdrClientCall3
0x18000e3e8  mov     rbx, rax
0x18000e3eb  mov     [rsp+38h+arg_10], rax
0x18000e3f0  mov     [rsp+38h+var_18], eax
0x18000e3f4  jmp     short loc_18000E431
0x18000e3f6  mov     ebx, eax
0x18000e3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3ff  test    byte ptr [rcx+1Ch], 2
0x18000e403  jz      short loc_18000E423
0x18000e405  cmp     byte ptr [rcx+19h], 3
0x18000e409  jb      short loc_18000E423
0x18000e40b  mov     r9d, eax
0x18000e40e  mov     edx, 0A0h
0x18000e413  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e41a  mov     rcx, [rcx+10h]
0x18000e41e  call    WPP_SF_D
0x18000e423  mov     ecx, ebx; Status
0x18000e425  call    cs:__imp_I_RpcMapWin32Status
0x18000e42b  mov     ebx, eax
0x18000e42d  mov     [rsp+38h+var_18], eax
0x18000e431  test    ebx, ebx
0x18000e433  js      short loc_18000E43F
0x18000e435  lea     rcx, [rsp+38h+arg_0]; struct _SAMP_CLIENT_INFO **
0x18000e43a  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x18000e43f  mov     edi, 0C0000008h
0x18000e444  cmp     ebx, 0C0020003h
0x18000e44a  cmovz   ebx, edi
0x18000e44d  test    ebx, ebx
0x18000e44f  js      short loc_18000E47B
0x18000e451  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e458  test    byte ptr [rcx+1Ch], 2
0x18000e45c  jz      short loc_18000E4A6
0x18000e45e  cmp     byte ptr [rcx+19h], 4
0x18000e462  jb      short loc_18000E4A6
0x18000e464  mov     edx, 0A1h
0x18000e469  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e470  mov     rcx, [rcx+10h]
0x18000e474  call    WPP_SF_
0x18000e479  jmp     short loc_18000E4A6
0x18000e47b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e482  test    byte ptr [rcx+1Ch], 2
0x18000e486  jz      short loc_18000E4A6
0x18000e488  cmp     byte ptr [rcx+19h], 2
0x18000e48c  jb      short loc_18000E4A6
0x18000e48e  mov     edx, 0A2h
0x18000e493  mov     r9d, ebx
0x18000e496  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e49d  mov     rcx, [rcx+10h]
0x18000e4a1  call    WPP_SF_D
0x18000e4a6  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e4ad  jz      short loc_18000E4BE
0x18000e4af  mov     r8d, ebx
0x18000e4b2  lea     rdx, SamDeleteGroupExit
0x18000e4b9  call    McTemplateU0d_EventWriteTransfer
0x18000e4be  mov     eax, ebx
0x18000e4c0  mov     rbx, [rsp+38h+arg_18]
0x18000e4c5  add     rsp, 30h
0x18000e4c9  pop     rdi
0x18000e4ca  retn
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
