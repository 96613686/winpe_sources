# SamCreateAliasInDomain

- ea: `0x18000d330`
- end: `0x18000d622`
- name: `SamCreateAliasInDomain`
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
- `0x18000d330`
- `0x180014a50`
- `0x180014a90`
- `0x180014e08`
- `0x180015e18`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3ca`
- `RPCRT4!NdrClientCall3` at `0x18000d4e2`
- `RPCRT4!NdrClientCall3` at `0x18000d4e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000d525`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000d525`

## pseudocode

```c
__int64 __fastcall SamCreateAliasInDomain(
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
        (unsigned int)SamCreateAliasInDomainEntry,
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
    WPP_SF_qZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, a3, (_DWORD)a1, (__int64)v7, v6);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, &v22) )
  {
    Pointer = SampCreateNewHandle(a1, 0, &v21);
    if ( Pointer >= 0 )
    {
      *a4 = 0;
      *a5 = 0;
      v24.Simple = 0;
      LODWORD(v20) = a3;
      v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0xEu, 0, v22, v7, v20, &v23, a5).Pointer;
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
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v18, *a5);
        if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
          McTemplateU0dpq_EventWriteTransfer(
            v19,
            (unsigned int)SamCreateAliasInDomainExit,
            Pointer,
            (unsigned int)*a4,
            *a5);
        return (unsigned int)Pointer;
      }
      v15 = (int)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
          (unsigned int)Pointer);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0dpq_EventWriteTransfer(v15, (unsigned int)SamCreateAliasInDomainExit, Pointer, 0, 0);
    return (unsigned int)Pointer;
  }
  v13 = (int)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dpq_EventWriteTransfer(v13, (unsigned int)SamCreateAliasInDomainExit, -1073741816, 0, 0);
  return 3221225480LL;
}

```

## disassembly

```asm
0x18000d330  mov     rax, rsp
0x18000d333  mov     [rax+20h], r9
0x18000d337  mov     [rax+18h], r8d
0x18000d33b  mov     [rax+10h], rdx
0x18000d33f  push    rbx
0x18000d340  push    rsi
0x18000d341  push    r12
0x18000d343  push    r13
0x18000d345  push    r14
0x18000d347  sub     rsp, 70h
0x18000d34b  mov     r13, r9
0x18000d34e  mov     r12d, r8d
0x18000d351  mov     r14, rdx
0x18000d354  mov     rbx, rcx
0x18000d357  mov     qword ptr [rax-50h], 0
0x18000d35f  mov     qword ptr [rax-48h], 0
0x18000d367  mov     qword ptr [rax-40h], 0
0x18000d36f  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d376  jz      short loc_18000D3D8
0x18000d378  mov     rcx, rdx; struct _UNICODE_STRING *
0x18000d37b  call    ?SampDuplicateUnicodeString@@YAPEAGPEAU_UNICODE_STRING@@@Z; SampDuplicateUnicodeString(_UNICODE_STRING *)
0x18000d380  mov     r14, rax
0x18000d383  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000d388  mov     rsi, rax
0x18000d38b  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d392  jz      short loc_18000D3BE
0x18000d394  lea     rcx, aUnknown; "<unknown>"
0x18000d39b  test    rax, rax
0x18000d39e  cmovnz  rcx, rax
0x18000d3a2  mov     [rsp+98h+var_70], rcx
0x18000d3a7  mov     dword ptr [rsp+98h+var_78], r12d
0x18000d3ac  mov     r9, r14
0x18000d3af  mov     r8, rbx
0x18000d3b2  lea     rdx, SamCreateAliasInDomainEntry
0x18000d3b9  call    McTemplateU0pzqz_EventWriteTransfer
0x18000d3be  mov     rcx, rsi; hMem
0x18000d3c1  call    cs:__imp_LocalFree
0x18000d3c7  mov     rcx, r14; hMem
0x18000d3ca  call    cs:__imp_LocalFree
0x18000d3d0  mov     r14, [rsp+98h+arg_8]
0x18000d3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3df  mov     sil, 2
0x18000d3e2  test    [rcx+1Ch], sil
0x18000d3e6  jz      short loc_18000D409
0x18000d3e8  cmp     byte ptr [rcx+19h], 4
0x18000d3ec  jb      short loc_18000D409
0x18000d3ee  mov     edx, 4Ah ; 'J'
0x18000d3f3  mov     dword ptr [rsp+98h+var_70], r12d
0x18000d3f8  mov     [rsp+98h+var_78], r14
0x18000d3fd  mov     r9, rbx
0x18000d400  mov     rcx, [rcx+10h]
0x18000d404  call    WPP_SF_qZD
0x18000d409  lea     rdx, [rsp+98h+var_48]; void **
0x18000d40e  mov     rcx, rbx; void *
0x18000d411  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000d416  test    al, al
0x18000d418  jnz     short loc_18000D476
0x18000d41a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d421  test    [rcx+1Ch], sil
0x18000d425  jz      short loc_18000D445
0x18000d427  cmp     [rcx+19h], sil
0x18000d42b  jb      short loc_18000D445
0x18000d42d  mov     edx, 4Bh ; 'K'
0x18000d432  mov     r9, rbx
0x18000d435  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000d43c  mov     rcx, [rcx+10h]
0x18000d440  call    WPP_SF_q
0x18000d445  mov     r14d, 0C0000008h
0x18000d44b  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d452  jz      short loc_18000D46E
0x18000d454  mov     dword ptr [rsp+98h+var_78], 0
0x18000d45c  xor     r9d, r9d
0x18000d45f  mov     r8d, r14d
0x18000d462  lea     rdx, SamCreateAliasInDomainExit
0x18000d469  call    McTemplateU0dpq_EventWriteTransfer
0x18000d46e  mov     eax, r14d
0x18000d471  jmp     loc_18000D615
0x18000d476  lea     r8, [rsp+98h+var_50]; struct _SAMP_CLIENT_INFO **
0x18000d47b  xor     edx, edx; void *
0x18000d47d  mov     rcx, rbx; struct _SAMP_CLIENT_INFO *
0x18000d480  call    ?SampCreateNewHandle@@YAJPEAU_SAMP_CLIENT_INFO@@PEAXPEAPEAU1@@Z; SampCreateNewHandle(_SAMP_CLIENT_INFO *,void *,_SAMP_CLIENT_INFO * *)
0x18000d485  mov     ebx, eax
0x18000d487  test    eax, eax
0x18000d489  js      loc_18000D5F0
0x18000d48f  mov     qword ptr [r13+0], 0
0x18000d497  mov     r12, [rsp+98h+arg_20]
0x18000d49f  mov     dword ptr [r12], 0
0x18000d4a7  mov     [rsp+98h+var_38], 0
0x18000d4b0  mov     [rsp+98h+var_60], r12
0x18000d4b5  lea     rax, [rsp+98h+var_40]
0x18000d4ba  mov     [rsp+98h+var_68], rax
0x18000d4bf  mov     eax, [rsp+98h+arg_10]
0x18000d4c6  mov     dword ptr [rsp+98h+var_70], eax
0x18000d4ca  mov     [rsp+98h+var_78], r14
0x18000d4cf  mov     r9, [rsp+98h+var_48]
0x18000d4d4  xor     r8d, r8d; pReturnValue
0x18000d4d7  lea     edx, [r8+0Eh]; nProcNum
0x18000d4db  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000d4e2  call    cs:__imp_NdrClientCall3
0x18000d4e8  mov     rbx, rax
0x18000d4eb  mov     [rsp+98h+var_38], rax
0x18000d4f0  mov     [rsp+98h+var_58], eax
0x18000d4f4  jmp     short loc_18000D544
0x18000d4f6  mov     ebx, eax
0x18000d4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4ff  test    byte ptr [rcx+1Ch], 2
0x18000d503  jz      short loc_18000D523
0x18000d505  cmp     byte ptr [rcx+19h], 3
0x18000d509  jb      short loc_18000D523
0x18000d50b  mov     r9d, eax
0x18000d50e  mov     edx, 4Ch ; 'L'
0x18000d513  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000d51a  mov     rcx, [rcx+10h]
0x18000d51e  call    WPP_SF_D
0x18000d523  mov     ecx, ebx; Status
0x18000d525  call    cs:__imp_I_RpcMapWin32Status
0x18000d52b  mov     ebx, eax
0x18000d52d  mov     [rsp+98h+var_58], eax
0x18000d531  mov     sil, 2
0x18000d534  mov     r12, [rsp+98h+arg_20]
0x18000d53c  mov     r13, [rsp+98h+arg_18]
0x18000d544  test    ebx, ebx
0x18000d546  js      short loc_18000D557
0x18000d548  mov     rax, [rsp+98h+var_40]
0x18000d54d  mov     r9, [rsp+98h+var_50]
0x18000d552  mov     [r9], rax
0x18000d555  jmp     short loc_18000D566
0x18000d557  lea     rcx, [rsp+98h+var_50]; struct _SAMP_CLIENT_INFO **
0x18000d55c  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x18000d561  mov     r9, [rsp+98h+var_50]
0x18000d566  mov     [r13+0], r9
0x18000d56a  mov     r14d, 0C0000008h
0x18000d570  cmp     ebx, 0C0020003h
0x18000d576  cmovz   ebx, r14d
0x18000d57a  test    ebx, ebx
0x18000d57c  js      short loc_18000D5C5
0x18000d57e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d585  test    [rcx+1Ch], sil
0x18000d589  jz      short loc_18000D5AE
0x18000d58b  cmp     byte ptr [rcx+19h], 4
0x18000d58f  jb      short loc_18000D5AE
0x18000d591  mov     edx, 4Dh ; 'M'
0x18000d596  mov     eax, [r12]
0x18000d59a  mov     dword ptr [rsp+98h+var_78], eax
0x18000d59e  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000d5a5  mov     rcx, [rcx+10h]
0x18000d5a9  call    WPP_SF_qD
0x18000d5ae  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d5b5  jz      short loc_18000D613
0x18000d5b7  mov     eax, [r12]
0x18000d5bb  mov     dword ptr [rsp+98h+var_78], eax
0x18000d5bf  mov     r9, [r13+0]
0x18000d5c3  jmp     short loc_18000D604
0x18000d5c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5cc  test    [rcx+1Ch], sil
0x18000d5d0  jz      short loc_18000D5F0
0x18000d5d2  cmp     [rcx+19h], sil
0x18000d5d6  jb      short loc_18000D5F0
0x18000d5d8  mov     edx, 4Eh ; 'N'
0x18000d5dd  mov     r9d, ebx
0x18000d5e0  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000d5e7  mov     rcx, [rcx+10h]
0x18000d5eb  call    WPP_SF_D
0x18000d5f0  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d5f7  jz      short loc_18000D613
0x18000d5f9  mov     dword ptr [rsp+98h+var_78], 0
0x18000d601  xor     r9d, r9d
0x18000d604  mov     r8d, ebx
0x18000d607  lea     rdx, SamCreateAliasInDomainExit
0x18000d60e  call    McTemplateU0dpq_EventWriteTransfer
0x18000d613  mov     eax, ebx
0x18000d615  add     rsp, 70h
0x18000d619  pop     r14
0x18000d61b  pop     r13
0x18000d61d  pop     r12
0x18000d61f  pop     rsi
0x18000d620  pop     rbx
0x18000d621  retn
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
