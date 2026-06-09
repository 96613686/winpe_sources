# SamCreateGroupInDomain

- ea: `0x18000d630`
- end: `0x18000d922`
- name: `SamCreateGroupInDomain`
- size: `754`
- prototype: `__int64 __usercall@<rax>(struct _SAMP_CLIENT_INFO *@<rcx>, struct _UNICODE_STRING *@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003220`
- `0x180003370`
- `0x180005e90`
- `0x18000807c`
- `0x18000bb64`
- `0x18000c39c`
- `0x18000d630`
- `0x180014a50`
- `0x180014a90`
- `0x180014e08`
- `0x180015e18`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6ca`
- `RPCRT4!NdrClientCall3` at `0x18000d7e2`
- `RPCRT4!NdrClientCall3` at `0x18000d7e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000d825`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000d825`

## pseudocode

```c
__int64 __fastcall SamCreateGroupInDomain(
        struct _SAMP_CLIENT_INFO *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        struct _SAMP_CLIENT_INFO **a4,
        _DWORD *a5)
{
  char v6; // r12
  struct _UNICODE_STRING *v7; // r14
  unsigned __int16 *v9; // r14
  unsigned __int16 *CallingProcessInfo; // rax
  unsigned __int16 *v11; // rsi
  const wchar_t *v12; // rcx
  int v13; // ecx
  int v15; // ecx
  int Pointer; // ebx
  CLIENT_CALL_RETURN v17; // rax
  struct _SAMP_CLIENT_INFO *v18; // r9
  int v19; // ecx
  __int64 v20; // [rsp+28h] [rbp-70h]
  struct _SAMP_CLIENT_INFO *v21; // [rsp+48h] [rbp-50h] BYREF
  void *v22; // [rsp+50h] [rbp-48h] BYREF
  __int64 v23; // [rsp+58h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v24; // [rsp+60h] [rbp-38h]

  v6 = a3;
  v7 = a2;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    v9 = SampDuplicateUnicodeString(a2);
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v11 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v12 = L"<unknown>";
      if ( CallingProcessInfo )
        v12 = CallingProcessInfo;
      McTemplateU0pzqz_EventWriteTransfer(
        (_DWORD)v12,
        (unsigned int)SamCreateGroupInDomainEntry,
        (_DWORD)a1,
        (_DWORD)v9,
        v6,
        (__int64)v12);
    }
    LocalFree(v11);
    LocalFree(v9);
    v7 = a2;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, a3, (_DWORD)a1, (__int64)v7, v6);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, &v22) )
  {
    Pointer = SampCreateNewHandle(a1, 0, &v21);
    if ( Pointer >= 0 )
    {
      *a4 = 0;
      *a5 = 0;
      v24.Simple = 0;
      LODWORD(v20) = a3;
      v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0xAu, 0, v22, v7, v20, &v23, a5).Pointer;
      Pointer = (int)v17.Pointer;
      v24.Pointer = v17.Pointer;
      if ( SLODWORD(v17.Simple) < 0 )
      {
        SampFreeHandle(&v21);
        v18 = v21;
      }
      else
      {
        v18 = v21;
        *(_QWORD *)v21 = v23;
      }
      *a4 = v18;
      if ( Pointer == -1073610749 )
        Pointer = -1073741816;
      if ( Pointer >= 0 )
      {
        v19 = (int)WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v18, *a5);
        if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
          McTemplateU0dpq_EventWriteTransfer(
            v19,
            (unsigned int)SamCreateGroupInDomainExit,
            Pointer,
            (unsigned int)*a4,
            *a5);
        return (unsigned int)Pointer;
      }
      v15 = (int)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
          (unsigned int)Pointer);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0dpq_EventWriteTransfer(v15, (unsigned int)SamCreateGroupInDomainExit, Pointer, 0, 0);
    return (unsigned int)Pointer;
  }
  v13 = (int)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dpq_EventWriteTransfer(v13, (unsigned int)SamCreateGroupInDomainExit, -1073741816, 0, 0);
  return 3221225480LL;
}

```

## disassembly

```asm
0x18000d630  mov     rax, rsp
0x18000d633  mov     [rax+20h], r9
0x18000d637  mov     [rax+18h], r8d
0x18000d63b  mov     [rax+10h], rdx
0x18000d63f  push    rbx
0x18000d640  push    rsi
0x18000d641  push    r12
0x18000d643  push    r13
0x18000d645  push    r14
0x18000d647  sub     rsp, 70h
0x18000d64b  mov     r13, r9
0x18000d64e  mov     r12d, r8d
0x18000d651  mov     r14, rdx
0x18000d654  mov     rbx, rcx
0x18000d657  mov     qword ptr [rax-50h], 0
0x18000d65f  mov     qword ptr [rax-48h], 0
0x18000d667  mov     qword ptr [rax-40h], 0
0x18000d66f  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d676  jz      short loc_18000D6D8
0x18000d678  mov     rcx, rdx; struct _UNICODE_STRING *
0x18000d67b  call    ?SampDuplicateUnicodeString@@YAPEAGPEAU_UNICODE_STRING@@@Z; SampDuplicateUnicodeString(_UNICODE_STRING *)
0x18000d680  mov     r14, rax
0x18000d683  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000d688  mov     rsi, rax
0x18000d68b  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d692  jz      short loc_18000D6BE
0x18000d694  lea     rcx, aUnknown; "<unknown>"
0x18000d69b  test    rax, rax
0x18000d69e  cmovnz  rcx, rax
0x18000d6a2  mov     [rsp+98h+var_70], rcx
0x18000d6a7  mov     dword ptr [rsp+98h+var_78], r12d
0x18000d6ac  mov     r9, r14
0x18000d6af  mov     r8, rbx
0x18000d6b2  lea     rdx, SamCreateGroupInDomainEntry
0x18000d6b9  call    McTemplateU0pzqz_EventWriteTransfer
0x18000d6be  mov     rcx, rsi; hMem
0x18000d6c1  call    cs:__imp_LocalFree
0x18000d6c7  mov     rcx, r14; hMem
0x18000d6ca  call    cs:__imp_LocalFree
0x18000d6d0  mov     r14, [rsp+98h+arg_8]
0x18000d6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6df  mov     sil, 2
0x18000d6e2  test    [rcx+1Ch], sil
0x18000d6e6  jz      short loc_18000D709
0x18000d6e8  cmp     byte ptr [rcx+19h], 4
0x18000d6ec  jb      short loc_18000D709
0x18000d6ee  mov     edx, 26h ; '&'
0x18000d6f3  mov     dword ptr [rsp+98h+var_70], r12d
0x18000d6f8  mov     [rsp+98h+var_78], r14
0x18000d6fd  mov     r9, rbx
0x18000d700  mov     rcx, [rcx+10h]
0x18000d704  call    WPP_SF_qZD
0x18000d709  lea     rdx, [rsp+98h+var_48]; void **
0x18000d70e  mov     rcx, rbx; void *
0x18000d711  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000d716  test    al, al
0x18000d718  jnz     short loc_18000D776
0x18000d71a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d721  test    [rcx+1Ch], sil
0x18000d725  jz      short loc_18000D745
0x18000d727  cmp     [rcx+19h], sil
0x18000d72b  jb      short loc_18000D745
0x18000d72d  mov     edx, 27h ; '''
0x18000d732  mov     r9, rbx
0x18000d735  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000d73c  mov     rcx, [rcx+10h]
0x18000d740  call    WPP_SF_q
0x18000d745  mov     r14d, 0C0000008h
0x18000d74b  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d752  jz      short loc_18000D76E
0x18000d754  mov     dword ptr [rsp+98h+var_78], 0
0x18000d75c  xor     r9d, r9d
0x18000d75f  mov     r8d, r14d
0x18000d762  lea     rdx, SamCreateGroupInDomainExit
0x18000d769  call    McTemplateU0dpq_EventWriteTransfer
0x18000d76e  mov     eax, r14d
0x18000d771  jmp     loc_18000D915
0x18000d776  lea     r8, [rsp+98h+var_50]; struct _SAMP_CLIENT_INFO **
0x18000d77b  xor     edx, edx; void *
0x18000d77d  mov     rcx, rbx; struct _SAMP_CLIENT_INFO *
0x18000d780  call    ?SampCreateNewHandle@@YAJPEAU_SAMP_CLIENT_INFO@@PEAXPEAPEAU1@@Z; SampCreateNewHandle(_SAMP_CLIENT_INFO *,void *,_SAMP_CLIENT_INFO * *)
0x18000d785  mov     ebx, eax
0x18000d787  test    eax, eax
0x18000d789  js      loc_18000D8F0
0x18000d78f  mov     qword ptr [r13+0], 0
0x18000d797  mov     r12, [rsp+98h+arg_20]
0x18000d79f  mov     dword ptr [r12], 0
0x18000d7a7  mov     [rsp+98h+var_38], 0
0x18000d7b0  mov     [rsp+98h+var_60], r12
0x18000d7b5  lea     rax, [rsp+98h+var_40]
0x18000d7ba  mov     [rsp+98h+var_68], rax
0x18000d7bf  mov     eax, [rsp+98h+arg_10]
0x18000d7c6  mov     dword ptr [rsp+98h+var_70], eax
0x18000d7ca  mov     [rsp+98h+var_78], r14
0x18000d7cf  mov     r9, [rsp+98h+var_48]
0x18000d7d4  xor     r8d, r8d; pReturnValue
0x18000d7d7  lea     edx, [r8+0Ah]; nProcNum
0x18000d7db  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000d7e2  call    cs:__imp_NdrClientCall3
0x18000d7e8  mov     rbx, rax
0x18000d7eb  mov     [rsp+98h+var_38], rax
0x18000d7f0  mov     [rsp+98h+var_58], eax
0x18000d7f4  jmp     short loc_18000D844
0x18000d7f6  mov     ebx, eax
0x18000d7f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7ff  test    byte ptr [rcx+1Ch], 2
0x18000d803  jz      short loc_18000D823
0x18000d805  cmp     byte ptr [rcx+19h], 3
0x18000d809  jb      short loc_18000D823
0x18000d80b  mov     r9d, eax
0x18000d80e  mov     edx, 28h ; '('
0x18000d813  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000d81a  mov     rcx, [rcx+10h]
0x18000d81e  call    WPP_SF_D
0x18000d823  mov     ecx, ebx; Status
0x18000d825  call    cs:__imp_I_RpcMapWin32Status
0x18000d82b  mov     ebx, eax
0x18000d82d  mov     [rsp+98h+var_58], eax
0x18000d831  mov     sil, 2
0x18000d834  mov     r12, [rsp+98h+arg_20]
0x18000d83c  mov     r13, [rsp+98h+arg_18]
0x18000d844  test    ebx, ebx
0x18000d846  js      short loc_18000D857
0x18000d848  mov     rax, [rsp+98h+var_40]
0x18000d84d  mov     r9, [rsp+98h+var_50]
0x18000d852  mov     [r9], rax
0x18000d855  jmp     short loc_18000D866
0x18000d857  lea     rcx, [rsp+98h+var_50]; struct _SAMP_CLIENT_INFO **
0x18000d85c  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x18000d861  mov     r9, [rsp+98h+var_50]
0x18000d866  mov     [r13+0], r9
0x18000d86a  mov     r14d, 0C0000008h
0x18000d870  cmp     ebx, 0C0020003h
0x18000d876  cmovz   ebx, r14d
0x18000d87a  test    ebx, ebx
0x18000d87c  js      short loc_18000D8C5
0x18000d87e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d885  test    [rcx+1Ch], sil
0x18000d889  jz      short loc_18000D8AE
0x18000d88b  cmp     byte ptr [rcx+19h], 4
0x18000d88f  jb      short loc_18000D8AE
0x18000d891  mov     edx, 29h ; ')'
0x18000d896  mov     eax, [r12]
0x18000d89a  mov     dword ptr [rsp+98h+var_78], eax
0x18000d89e  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000d8a5  mov     rcx, [rcx+10h]
0x18000d8a9  call    WPP_SF_qD
0x18000d8ae  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d8b5  jz      short loc_18000D913
0x18000d8b7  mov     eax, [r12]
0x18000d8bb  mov     dword ptr [rsp+98h+var_78], eax
0x18000d8bf  mov     r9, [r13+0]
0x18000d8c3  jmp     short loc_18000D904
0x18000d8c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8cc  test    [rcx+1Ch], sil
0x18000d8d0  jz      short loc_18000D8F0
0x18000d8d2  cmp     [rcx+19h], sil
0x18000d8d6  jb      short loc_18000D8F0
0x18000d8d8  mov     edx, 2Ah ; '*'
0x18000d8dd  mov     r9d, ebx
0x18000d8e0  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000d8e7  mov     rcx, [rcx+10h]
0x18000d8eb  call    WPP_SF_D
0x18000d8f0  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d8f7  jz      short loc_18000D913
0x18000d8f9  mov     dword ptr [rsp+98h+var_78], 0
0x18000d901  xor     r9d, r9d
0x18000d904  mov     r8d, ebx
0x18000d907  lea     rdx, SamCreateGroupInDomainExit
0x18000d90e  call    McTemplateU0dpq_EventWriteTransfer
0x18000d913  mov     eax, ebx
0x18000d915  add     rsp, 70h
0x18000d919  pop     r14
0x18000d91b  pop     r13
0x18000d91d  pop     r12
0x18000d91f  pop     rsi
0x18000d920  pop     rbx
0x18000d921  retn
0x180017cf0  push    rbp
0x180017cf2  sub     rsp, 40h
0x180017cf6  mov     rbp, rdx
0x180017cf9  mov     rcx, [rcx]
0x180017cfc  mov     ecx, [rcx]; ExceptionCode
0x180017cfe  call    cs:__imp_I_RpcExceptionFilter
0x180017d04  nop
0x180017d05  add     rsp, 40h
0x180017d09  pop     rbp
0x180017d0a  retn
```
