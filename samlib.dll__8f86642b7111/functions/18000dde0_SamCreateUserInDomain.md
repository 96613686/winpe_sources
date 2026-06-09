# SamCreateUserInDomain

- ea: `0x18000dde0`
- end: `0x18000e0d3`
- name: `SamCreateUserInDomain`
- size: `755`
- prototype: `__int64 __usercall@<rax>(struct _SAMP_CLIENT_INFO *@<rcx>, struct _UNICODE_STRING *@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000d930`

## callees

- `0x180003220`
- `0x180003370`
- `0x180005e90`
- `0x18000807c`
- `0x18000bb64`
- `0x18000c39c`
- `0x18000dde0`
- `0x180014a50`
- `0x180014a90`
- `0x180014e08`
- `0x180015e18`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de7a`
- `RPCRT4!NdrClientCall3` at `0x18000df93`
- `RPCRT4!NdrClientCall3` at `0x18000df93`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000dfd6`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000dfd6`

## pseudocode

```c
__int64 __fastcall SamCreateUserInDomain(
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
  __int64 v22; // [rsp+50h] [rbp-48h] BYREF
  void *v23; // [rsp+58h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v24; // [rsp+60h] [rbp-38h]

  v6 = a3;
  v7 = a2;
  v21 = 0;
  v23 = 0;
  v22 = 0;
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
        (unsigned int)SamCreateUserInDomainEntry,
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
    WPP_SF_qZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, a3, (_DWORD)a1, (__int64)v7, v6);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, &v23) )
  {
    Pointer = SampCreateNewHandle(a1, 0, &v21);
    if ( Pointer >= 0 )
    {
      v22 = 0;
      *a5 = 0;
      v24.Simple = 0;
      LODWORD(v20) = a3;
      v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0xCu, 0, v23, v7, v20, &v22, a5).Pointer;
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
        *(_QWORD *)v21 = v22;
      }
      *a4 = v18;
      if ( Pointer == -1073610749 )
        Pointer = -1073741816;
      if ( Pointer >= 0 )
      {
        v19 = (int)WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v18, *a5);
        if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
          McTemplateU0dpq_EventWriteTransfer(
            v19,
            (unsigned int)SamCreateUserInDomainExit,
            Pointer,
            (unsigned int)*a4,
            *a5);
        return (unsigned int)Pointer;
      }
      v15 = (int)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
          (unsigned int)Pointer);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0dpq_EventWriteTransfer(v15, (unsigned int)SamCreateUserInDomainExit, Pointer, 0, 0);
    return (unsigned int)Pointer;
  }
  v13 = (int)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dpq_EventWriteTransfer(v13, (unsigned int)SamCreateUserInDomainExit, -1073741816, 0, 0);
  return 3221225480LL;
}

```

## disassembly

```asm
0x18000dde0  mov     rax, rsp
0x18000dde3  mov     [rax+20h], r9
0x18000dde7  mov     [rax+18h], r8d
0x18000ddeb  mov     [rax+10h], rdx
0x18000ddef  push    rbx
0x18000ddf0  push    rsi
0x18000ddf1  push    r12
0x18000ddf3  push    r13
0x18000ddf5  push    r14
0x18000ddf7  sub     rsp, 70h
0x18000ddfb  mov     r13, r9
0x18000ddfe  mov     r12d, r8d
0x18000de01  mov     r14, rdx
0x18000de04  mov     rbx, rcx
0x18000de07  mov     qword ptr [rax-50h], 0
0x18000de0f  mov     qword ptr [rax-40h], 0
0x18000de17  mov     qword ptr [rax-48h], 0
0x18000de1f  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000de26  jz      short loc_18000DE88
0x18000de28  mov     rcx, rdx; struct _UNICODE_STRING *
0x18000de2b  call    ?SampDuplicateUnicodeString@@YAPEAGPEAU_UNICODE_STRING@@@Z; SampDuplicateUnicodeString(_UNICODE_STRING *)
0x18000de30  mov     r14, rax
0x18000de33  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000de38  mov     rsi, rax
0x18000de3b  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000de42  jz      short loc_18000DE6E
0x18000de44  lea     rcx, aUnknown; "<unknown>"
0x18000de4b  test    rax, rax
0x18000de4e  cmovnz  rcx, rax
0x18000de52  mov     [rsp+98h+var_70], rcx
0x18000de57  mov     dword ptr [rsp+98h+var_78], r12d
0x18000de5c  mov     r9, r14
0x18000de5f  mov     r8, rbx
0x18000de62  lea     rdx, SamCreateUserInDomainEntry
0x18000de69  call    McTemplateU0pzqz_EventWriteTransfer
0x18000de6e  mov     rcx, rsi; hMem
0x18000de71  call    cs:__imp_LocalFree
0x18000de77  mov     rcx, r14; hMem
0x18000de7a  call    cs:__imp_LocalFree
0x18000de80  mov     r14, [rsp+98h+arg_8]
0x18000de88  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de8f  mov     sil, 2
0x18000de92  test    [rcx+1Ch], sil
0x18000de96  jz      short loc_18000DEB9
0x18000de98  cmp     byte ptr [rcx+19h], 4
0x18000de9c  jb      short loc_18000DEB9
0x18000de9e  mov     edx, 3Ah ; ':'
0x18000dea3  mov     dword ptr [rsp+98h+var_70], r12d
0x18000dea8  mov     [rsp+98h+var_78], r14
0x18000dead  mov     r9, rbx
0x18000deb0  mov     rcx, [rcx+10h]
0x18000deb4  call    WPP_SF_qZD
0x18000deb9  lea     rdx, [rsp+98h+var_40]; void **
0x18000debe  mov     rcx, rbx; void *
0x18000dec1  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000dec6  test    al, al
0x18000dec8  jnz     short loc_18000DF26
0x18000deca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ded1  test    [rcx+1Ch], sil
0x18000ded5  jz      short loc_18000DEF5
0x18000ded7  cmp     [rcx+19h], sil
0x18000dedb  jb      short loc_18000DEF5
0x18000dedd  mov     edx, 3Bh ; ';'
0x18000dee2  mov     r9, rbx
0x18000dee5  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000deec  mov     rcx, [rcx+10h]
0x18000def0  call    WPP_SF_q
0x18000def5  mov     r14d, 0C0000008h
0x18000defb  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000df02  jz      short loc_18000DF1E
0x18000df04  mov     dword ptr [rsp+98h+var_78], 0
0x18000df0c  xor     r9d, r9d
0x18000df0f  mov     r8d, r14d
0x18000df12  lea     rdx, SamCreateUserInDomainExit
0x18000df19  call    McTemplateU0dpq_EventWriteTransfer
0x18000df1e  mov     eax, r14d
0x18000df21  jmp     loc_18000E0C6
0x18000df26  lea     r8, [rsp+98h+var_50]; struct _SAMP_CLIENT_INFO **
0x18000df2b  xor     edx, edx; void *
0x18000df2d  mov     rcx, rbx; struct _SAMP_CLIENT_INFO *
0x18000df30  call    ?SampCreateNewHandle@@YAJPEAU_SAMP_CLIENT_INFO@@PEAXPEAPEAU1@@Z; SampCreateNewHandle(_SAMP_CLIENT_INFO *,void *,_SAMP_CLIENT_INFO * *)
0x18000df35  mov     ebx, eax
0x18000df37  test    eax, eax
0x18000df39  js      loc_18000E0A1
0x18000df3f  mov     [rsp+98h+var_48], 0
0x18000df48  mov     r12, [rsp+98h+arg_20]
0x18000df50  mov     dword ptr [r12], 0
0x18000df58  mov     [rsp+98h+var_38], 0
0x18000df61  mov     [rsp+98h+var_60], r12
0x18000df66  lea     rax, [rsp+98h+var_48]
0x18000df6b  mov     [rsp+98h+var_68], rax
0x18000df70  mov     eax, [rsp+98h+arg_10]
0x18000df77  mov     dword ptr [rsp+98h+var_70], eax
0x18000df7b  mov     [rsp+98h+var_78], r14
0x18000df80  mov     r9, [rsp+98h+var_40]
0x18000df85  xor     r8d, r8d; pReturnValue
0x18000df88  lea     edx, [r8+0Ch]; nProcNum
0x18000df8c  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000df93  call    cs:__imp_NdrClientCall3
0x18000df99  mov     rbx, rax
0x18000df9c  mov     [rsp+98h+var_38], rax
0x18000dfa1  mov     [rsp+98h+var_58], eax
0x18000dfa5  jmp     short loc_18000DFF5
0x18000dfa7  mov     ebx, eax
0x18000dfa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfb0  test    byte ptr [rcx+1Ch], 2
0x18000dfb4  jz      short loc_18000DFD4
0x18000dfb6  cmp     byte ptr [rcx+19h], 3
0x18000dfba  jb      short loc_18000DFD4
0x18000dfbc  mov     r9d, eax
0x18000dfbf  mov     edx, 3Ch ; '<'
0x18000dfc4  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000dfcb  mov     rcx, [rcx+10h]
0x18000dfcf  call    WPP_SF_D
0x18000dfd4  mov     ecx, ebx; Status
0x18000dfd6  call    cs:__imp_I_RpcMapWin32Status
0x18000dfdc  mov     ebx, eax
0x18000dfde  mov     [rsp+98h+var_58], eax
0x18000dfe2  mov     sil, 2
0x18000dfe5  mov     r12, [rsp+98h+arg_20]
0x18000dfed  mov     r13, [rsp+98h+arg_18]
0x18000dff5  test    ebx, ebx
0x18000dff7  js      short loc_18000E008
0x18000dff9  mov     rax, [rsp+98h+var_48]
0x18000dffe  mov     r9, [rsp+98h+var_50]
0x18000e003  mov     [r9], rax
0x18000e006  jmp     short loc_18000E017
0x18000e008  lea     rcx, [rsp+98h+var_50]; struct _SAMP_CLIENT_INFO **
0x18000e00d  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x18000e012  mov     r9, [rsp+98h+var_50]
0x18000e017  mov     [r13+0], r9
0x18000e01b  mov     r14d, 0C0000008h
0x18000e021  cmp     ebx, 0C0020003h
0x18000e027  cmovz   ebx, r14d
0x18000e02b  test    ebx, ebx
0x18000e02d  js      short loc_18000E076
0x18000e02f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e036  test    [rcx+1Ch], sil
0x18000e03a  jz      short loc_18000E05F
0x18000e03c  cmp     byte ptr [rcx+19h], 4
0x18000e040  jb      short loc_18000E05F
0x18000e042  mov     edx, 3Dh ; '='
0x18000e047  mov     eax, [r12]
0x18000e04b  mov     dword ptr [rsp+98h+var_78], eax
0x18000e04f  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e056  mov     rcx, [rcx+10h]
0x18000e05a  call    WPP_SF_qD
0x18000e05f  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e066  jz      short loc_18000E0C4
0x18000e068  mov     eax, [r12]
0x18000e06c  mov     dword ptr [rsp+98h+var_78], eax
0x18000e070  mov     r9, [r13+0]
0x18000e074  jmp     short loc_18000E0B5
0x18000e076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e07d  test    [rcx+1Ch], sil
0x18000e081  jz      short loc_18000E0A1
0x18000e083  cmp     [rcx+19h], sil
0x18000e087  jb      short loc_18000E0A1
0x18000e089  mov     edx, 3Eh ; '>'
0x18000e08e  mov     r9d, ebx
0x18000e091  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e098  mov     rcx, [rcx+10h]
0x18000e09c  call    WPP_SF_D
0x18000e0a1  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e0a8  jz      short loc_18000E0C4
0x18000e0aa  mov     dword ptr [rsp+98h+var_78], 0
0x18000e0b2  xor     r9d, r9d
0x18000e0b5  mov     r8d, ebx
0x18000e0b8  lea     rdx, SamCreateUserInDomainExit
0x18000e0bf  call    McTemplateU0dpq_EventWriteTransfer
0x18000e0c4  mov     eax, ebx
0x18000e0c6  add     rsp, 70h
0x18000e0ca  pop     r14
0x18000e0cc  pop     r13
0x18000e0ce  pop     r12
0x18000e0d0  pop     rsi
0x18000e0d1  pop     rbx
0x18000e0d2  retn
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
