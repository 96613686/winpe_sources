# SamOpenDomain

- ea: `0x1800b34b8`
- end: `0x1800b37ad`
- name: `SamOpenDomain`
- size: `757`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009fab4`

## callees

- `0x1800372ac`
- `0x1800372ec`
- `0x180059e48`
- `0x1800b2460`
- `0x1800b2560`
- `0x1800b25ac`
- `0x1800b285c`
- `0x1800b28cc`
- `0x1800b34b8`
- `0x1800b3e24`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800b35d5`
- `ntdll!RtlValidSid` at `0x1800b35d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b3533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b3533`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800b36cf`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800b36cf`
- `RPCRT4!NdrClientCall3` at `0x1800b368c`
- `RPCRT4!NdrClientCall3` at `0x1800b368c`

## pseudocode

```c
__int64 __fastcall SamOpenDomain(struct _SAMP_CLIENT_INFO *a1, __int64 a2, void *a3, struct _SAMP_CLIENT_INFO **a4)
{
  unsigned __int16 *CallingProcessInfo; // rax
  int v8; // edx
  int v9; // r9d
  unsigned __int16 *v10; // rbx
  const unsigned __int16 *v11; // rcx
  PUNICODE_STRING v12; // rcx
  BOOLEAN valid; // al
  CLIENT_CALL_RETURN v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rdx
  struct _SAMP_CLIENT_INFO *v18; // r9
  struct _SAMP_CLIENT_INFO *v19; // r9
  char v20[8]; // [rsp+20h] [rbp-68h]
  struct _SAMP_CLIENT_INFO *v21; // [rsp+48h] [rbp-40h] BYREF
  void *v22; // [rsp+50h] [rbp-38h] BYREF
  __int64 v23; // [rsp+58h] [rbp-30h] BYREF
  CLIENT_CALL_RETURN v24; // [rsp+60h] [rbp-28h]

  v21 = 0;
  v23 = 0;
  v22 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v10 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v11 = L"<unknown>";
      if ( CallingProcessInfo )
        v11 = CallingProcessInfo;
      McTemplateU0pqkz_EventWriteTransfer((_DWORD)v11, v8, (_DWORD)a1, v9, (__int64)a3, (__int64)v11);
    }
    LocalFree(v10);
  }
  if ( (BYTE4(WPP_GLOBAL_Control[1].Buffer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control[1].Buffer) >= 4u )
    WPP_SF_qD_sid_(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Length,
      0x1Cu,
      (__int64)&WPP_02389d7df6583a073e538dcda8c3a574_Traceguids,
      (__int64)a1,
      0,
      a3);
  if ( SampIsValidClientHandle(a1, &v22) )
  {
    valid = RtlValidSid(a3);
    LODWORD(v15.Pointer) = 0;
    v16 = 3221225485LL;
    if ( !valid )
      LODWORD(v15.Pointer) = -1073741811;
    if ( SLODWORD(v15.Simple) < 0 )
      goto LABEL_39;
    LODWORD(v15.Pointer) = SampCreateNewHandle(a1, a3, &v21);
    if ( SLODWORD(v15.Simple) >= 0 )
    {
      *a4 = 0;
      v24.Simple = 0;
      *(_DWORD *)v20 = 0x20000000;
      v15.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 7u, 0, v22, *(_QWORD *)v20, a3, &v23).Pointer;
      v24.Pointer = v15.Pointer;
      if ( SLODWORD(v15.Simple) < 0 )
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
      if ( LODWORD(v15.Pointer) == -1073610749 )
        LODWORD(v15.Pointer) = -1073741816;
      if ( SLODWORD(v15.Simple) >= 0 )
      {
        v16 = (__int64)WPP_GLOBAL_Control;
        if ( (BYTE4(WPP_GLOBAL_Control[1].Buffer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control[1].Buffer) >= 4u )
          WPP_SF_q(*(_QWORD *)&WPP_GLOBAL_Control[1].Length, 32, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, v18);
        if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
          return LODWORD(v15.Pointer);
        v19 = *a4;
        goto LABEL_41;
      }
      v16 = (__int64)WPP_GLOBAL_Control;
      if ( (BYTE4(WPP_GLOBAL_Control[1].Buffer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control[1].Buffer) < 2u )
      {
LABEL_39:
        if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
          return LODWORD(v15.Pointer);
        v19 = 0;
LABEL_41:
        McTemplateU0dp_EventWriteTransfer(v16, SamOpenDomainExit, LODWORD(v15.Pointer), v19);
        return LODWORD(v15.Pointer);
      }
      v17 = 33;
    }
    else
    {
      v16 = (__int64)WPP_GLOBAL_Control;
      if ( (BYTE4(WPP_GLOBAL_Control[1].Buffer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control[1].Buffer) < 2u )
        goto LABEL_39;
      v17 = 30;
    }
    WPP_SF_d(*(_QWORD *)(v16 + 16), v17, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, LODWORD(v15.Pointer));
    goto LABEL_39;
  }
  v12 = WPP_GLOBAL_Control;
  if ( (BYTE4(WPP_GLOBAL_Control[1].Buffer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control[1].Buffer) >= 2u )
    WPP_SF_q(*(_QWORD *)&WPP_GLOBAL_Control[1].Length, 29, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, a1);
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dp_EventWriteTransfer(v12, SamOpenDomainExit, 0, 0);
  return 3221225480LL;
}

```

## disassembly

```asm
0x1800b34b8  mov     rax, rsp
0x1800b34bb  mov     [rax+10h], rbx
0x1800b34bf  mov     [rax+20h], r9
0x1800b34c3  mov     [rax+18h], r8
0x1800b34c7  mov     [rax+8], rcx
0x1800b34cb  push    r12
0x1800b34cd  push    r14
0x1800b34cf  push    r15
0x1800b34d1  sub     rsp, 70h
0x1800b34d5  mov     r12, r9
0x1800b34d8  mov     r15, r8
0x1800b34db  mov     r14, rcx
0x1800b34de  mov     qword ptr [rax-40h], 0
0x1800b34e6  mov     qword ptr [rax-30h], 0
0x1800b34ee  mov     qword ptr [rax-38h], 0
0x1800b34f6  test    cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800b34fd  jz      short loc_1800B3539
0x1800b34ff  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x1800b3504  mov     rbx, rax
0x1800b3507  test    cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800b350e  jz      short loc_1800B3530
0x1800b3510  lea     rcx, aUnknown; "<unknown>"
0x1800b3517  test    rax, rax
0x1800b351a  cmovnz  rcx, rax
0x1800b351e  mov     [rsp+88h+pSid], rcx
0x1800b3523  mov     qword ptr [rsp+88h+var_68], r15
0x1800b3528  mov     r8, r14
0x1800b352b  call    McTemplateU0pqkz_EventWriteTransfer
0x1800b3530  mov     rcx, rbx; hMem
0x1800b3533  call    cs:__imp_LocalFree
0x1800b3539  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3540  test    byte ptr [rcx+1Ch], 2
0x1800b3544  jz      short loc_1800B3571
0x1800b3546  cmp     byte ptr [rcx+19h], 4
0x1800b354a  jb      short loc_1800B3571
0x1800b354c  mov     edx, 1Ch; int
0x1800b3551  mov     [rsp+88h+pSid], r15; pSid
0x1800b3556  mov     dword ptr [rsp+88h+var_68], 20000000h; char
0x1800b355e  mov     r9, r14; int
0x1800b3561  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids; int
0x1800b3568  mov     rcx, [rcx+10h]; int
0x1800b356c  call    WPP_SF_qD_sid_
0x1800b3571  lea     rdx, [rsp+88h+var_38]; void **
0x1800b3576  mov     rcx, r14; void *
0x1800b3579  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x1800b357e  test    al, al
0x1800b3580  jnz     short loc_1800B35D2
0x1800b3582  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3589  test    byte ptr [rcx+1Ch], 2
0x1800b358d  jz      short loc_1800B35AD
0x1800b358f  cmp     byte ptr [rcx+19h], 2
0x1800b3593  jb      short loc_1800B35AD
0x1800b3595  mov     edx, 1Dh
0x1800b359a  mov     r9, r14
0x1800b359d  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800b35a4  mov     rcx, [rcx+10h]
0x1800b35a8  call    WPP_SF_q
0x1800b35ad  test    cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800b35b4  jz      short loc_1800B35C8
0x1800b35b6  xor     r9d, r9d
0x1800b35b9  xor     r8d, r8d
0x1800b35bc  lea     rdx, SamOpenDomainExit
0x1800b35c3  call    McTemplateU0dp_EventWriteTransfer
0x1800b35c8  mov     eax, 0C0000008h
0x1800b35cd  jmp     loc_1800B379A
0x1800b35d2  mov     rcx, r15; Sid
0x1800b35d5  call    cs:__imp_RtlValidSid
0x1800b35db  xor     ebx, ebx
0x1800b35dd  mov     ecx, 0C000000Dh
0x1800b35e2  test    al, al
0x1800b35e4  cmovz   ebx, ecx
0x1800b35e7  mov     [rsp+88h+var_48], ebx
0x1800b35eb  jmp     short loc_1800B360E
0x1800b35ed  mov     ebx, 0C000000Dh
0x1800b35f2  mov     [rsp+88h+var_48], ebx
0x1800b35f6  mov     r12, [rsp+88h+arg_18]
0x1800b35fe  mov     r15, [rsp+88h+arg_10]
0x1800b3606  mov     r14, [rsp+88h+arg_0]
0x1800b360e  test    ebx, ebx
0x1800b3610  js      loc_1800B377D
0x1800b3616  lea     r8, [rsp+88h+var_40]; struct _SAMP_CLIENT_INFO **
0x1800b361b  mov     rdx, r15; void *
0x1800b361e  mov     rcx, r14; struct _SAMP_CLIENT_INFO *
0x1800b3621  call    ?SampCreateNewHandle@@YAJPEAU_SAMP_CLIENT_INFO@@PEAXPEAPEAU1@@Z; SampCreateNewHandle(_SAMP_CLIENT_INFO *,void *,_SAMP_CLIENT_INFO * *)
0x1800b3626  mov     ebx, eax
0x1800b3628  test    eax, eax
0x1800b362a  jns     short loc_1800B3651
0x1800b362c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3633  test    byte ptr [rcx+1Ch], 2
0x1800b3637  jz      loc_1800B377D
0x1800b363d  cmp     byte ptr [rcx+19h], 2
0x1800b3641  jb      loc_1800B377D
0x1800b3647  mov     edx, 1Eh
0x1800b364c  jmp     loc_1800B376A
0x1800b3651  mov     qword ptr [r12], 0
0x1800b3659  mov     [rsp+88h+var_28], 0
0x1800b3662  lea     rax, [rsp+88h+var_30]
0x1800b3667  mov     [rsp+88h+var_58], rax
0x1800b366c  mov     [rsp+88h+pSid], r15
0x1800b3671  mov     dword ptr [rsp+88h+var_68], 20000000h
0x1800b3679  mov     r9, [rsp+88h+var_38]
0x1800b367e  xor     r8d, r8d; pReturnValue
0x1800b3681  lea     edx, [r8+7]; nProcNum
0x1800b3685  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800b368c  call    cs:__imp_NdrClientCall3
0x1800b3692  mov     rbx, rax
0x1800b3695  mov     [rsp+88h+var_28], rax
0x1800b369a  mov     [rsp+88h+var_48], eax
0x1800b369e  jmp     short loc_1800B36E3
0x1800b36a0  mov     ebx, eax
0x1800b36a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b36a9  test    byte ptr [rcx+1Ch], 2
0x1800b36ad  jz      short loc_1800B36CD
0x1800b36af  cmp     byte ptr [rcx+19h], 3
0x1800b36b3  jb      short loc_1800B36CD
0x1800b36b5  mov     r9d, eax
0x1800b36b8  mov     edx, 1Fh
0x1800b36bd  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800b36c4  mov     rcx, [rcx+10h]
0x1800b36c8  call    WPP_SF_d
0x1800b36cd  mov     ecx, ebx; Status
0x1800b36cf  call    cs:__imp_I_RpcMapWin32Status
0x1800b36d5  mov     ebx, eax
0x1800b36d7  mov     [rsp+88h+var_48], eax
0x1800b36db  mov     r12, [rsp+88h+arg_18]
0x1800b36e3  test    ebx, ebx
0x1800b36e5  js      short loc_1800B36F6
0x1800b36e7  mov     rax, [rsp+88h+var_30]
0x1800b36ec  mov     r9, [rsp+88h+var_40]
0x1800b36f1  mov     [r9], rax
0x1800b36f4  jmp     short loc_1800B3705
0x1800b36f6  lea     rcx, [rsp+88h+var_40]; struct _SAMP_CLIENT_INFO **
0x1800b36fb  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x1800b3700  mov     r9, [rsp+88h+var_40]
0x1800b3705  mov     [r12], r9
0x1800b3709  mov     eax, 0C0000008h
0x1800b370e  cmp     ebx, 0C0020003h
0x1800b3714  cmovz   ebx, eax
0x1800b3717  test    ebx, ebx
0x1800b3719  js      short loc_1800B3752
0x1800b371b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3722  test    byte ptr [rcx+1Ch], 2
0x1800b3726  jz      short loc_1800B3743
0x1800b3728  cmp     byte ptr [rcx+19h], 4
0x1800b372c  jb      short loc_1800B3743
0x1800b372e  mov     edx, 20h ; ' '
0x1800b3733  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800b373a  mov     rcx, [rcx+10h]
0x1800b373e  call    WPP_SF_q
0x1800b3743  test    cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800b374a  jz      short loc_1800B3798
0x1800b374c  mov     r9, [r12]
0x1800b3750  jmp     short loc_1800B3789
0x1800b3752  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3759  test    byte ptr [rcx+1Ch], 2
0x1800b375d  jz      short loc_1800B377D
0x1800b375f  cmp     byte ptr [rcx+19h], 2
0x1800b3763  jb      short loc_1800B377D
0x1800b3765  mov     edx, 21h ; '!'
0x1800b376a  mov     r9d, ebx
0x1800b376d  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800b3774  mov     rcx, [rcx+10h]
0x1800b3778  call    WPP_SF_d
0x1800b377d  test    cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800b3784  jz      short loc_1800B3798
0x1800b3786  xor     r9d, r9d
0x1800b3789  mov     r8d, ebx
0x1800b378c  lea     rdx, SamOpenDomainExit
0x1800b3793  call    McTemplateU0dp_EventWriteTransfer
0x1800b3798  mov     eax, ebx
0x1800b379a  mov     rbx, [rsp+88h+arg_8]
0x1800b37a2  add     rsp, 70h
0x1800b37a6  pop     r15
0x1800b37a8  pop     r14
0x1800b37aa  pop     r12
0x1800b37ac  retn
0x1800bba0a  push    rbp
0x1800bba0c  sub     rsp, 40h
0x1800bba10  mov     rbp, rdx
0x1800bba13  mov     rcx, [rcx]
0x1800bba16  mov     ecx, [rcx]; ExceptionCode
0x1800bba18  call    cs:__imp_I_RpcExceptionFilter
0x1800bba1e  nop
0x1800bba1f  add     rsp, 40h
0x1800bba23  pop     rbp
0x1800bba24  retn
```
