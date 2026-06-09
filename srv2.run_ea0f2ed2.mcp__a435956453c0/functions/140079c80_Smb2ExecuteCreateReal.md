# Smb2ExecuteCreateReal

- ea: `0x140079c80`
- end: `0x14007a280`
- name: `Smb2ExecuteCreateReal`
- size: `1536`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14006574c`
- `0x140079c20`

## callees

- `0x140005070`
- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x14000ca00`
- `0x14000e340`
- `0x14000f4d0`
- `0x140010af8`
- `0x140011214`
- `0x140012c30`
- `0x140014d60`
- `0x1400152a0`
- `0x140015354`
- `0x14001f050`
- `0x14001f9e4`
- `0x14001ffc4`
- `0x14002019c`
- `0x1400222ec`
- `0x140022958`
- `0x140038490`
- `0x140038680`
- `0x140059008`
- `0x140068080`
- `0x140079218`
- `0x140079c80`
- `0x14007a290`
- `0x14007a89c`
- `0x140085d90`
- `0x140086160`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140097d4a`
- `ntoskrnl!ExAllocatePool2` at `0x140097d4a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007a130`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007a130`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a02b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097fa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a02b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097fa9`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007a212`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097e24`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007a212`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097e24`
- `srvnet!SrvXsSchedulePrintJob` at `0x14007a0ef`
- `srvnet!SrvXsSchedulePrintJob` at `0x14007a0ef`
- `srvnet!SrvXsAddPrintJob` at `0x140097df5`
- `srvnet!SrvXsAddPrintJob` at `0x140097df5`
- `ksecdd!FreeContextBuffer` at `0x140097e0d`
- `ksecdd!FreeContextBuffer` at `0x140097e0d`

## string_xrefs

- `0x140079f6d`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14007a10f`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x140097f92`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14007a179`: `Srv2PostToThreadPool`
- `0x14007a1b7`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteCreateReal(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  unsigned int *v4; // rdi
  __int64 v5; // r12
  int v6; // eax
  ULONG v7; // r15d
  unsigned int v8; // eax
  unsigned int v9; // r14d
  int Ecps; // r13d
  int BuildResponse; // edi
  unsigned __int8 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 FileHandle; // rax
  int v23; // edi
  __int64 v24; // rdi
  USHORT CurrentNodeNumber; // ax
  bool v26; // zf
  void *v28; // rsi
  unsigned int v29; // edi
  _DWORD *ExtendedErrorBuffer; // rcx
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-120h]
  unsigned int v33; // [rsp+C0h] [rbp-80h] BYREF
  __int64 v34; // [rsp+C8h] [rbp-78h] BYREF
  PVOID P; // [rsp+D0h] [rbp-70h]
  PVOID pvContextBuffer; // [rsp+D8h] [rbp-68h] BYREF
  int v37[2]; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+E8h] [rbp-58h]
  int v39; // [rsp+F0h] [rbp-50h] BYREF
  int v40; // [rsp+F4h] [rbp-4Ch]
  _QWORD v41[2]; // [rsp+F8h] [rbp-48h] BYREF
  void *Src[2]; // [rsp+108h] [rbp-38h] BYREF
  __int64 v43; // [rsp+118h] [rbp-28h] BYREF
  int v44; // [rsp+120h] [rbp-20h]

  v2 = *(_QWORD *)(a1 + 560);
  v4 = *(unsigned int **)(*(_QWORD *)(a1 + 304) + 24LL);
  *(_OWORD *)Src = 0;
  v43 = 0;
  v5 = v2 + 192;
  v44 = 0;
  v6 = v4[22];
  v7 = v4[24];
  v34 = 0;
  P = 0;
  v33 = 0;
  v39 = 0;
  v40 = v6;
  if ( *(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL) == 127 )
  {
    v21 = v4[25];
    if ( v21 == 1 || v21 == 4 )
    {
      Ecps = -1073741772;
      goto LABEL_44;
    }
    if ( (v4[22] & 0x40000006) == 0 || (v4[23] & 0x10) != 0 )
    {
      Ecps = -1073741637;
      goto LABEL_44;
    }
    if ( *(_DWORD *)(a1 + 72) != 2 )
    {
      v26 = *(_DWORD *)(a1 + 8) == 5;
      *(_QWORD *)(a1 + 48) = Smb2ExecuteCreateReal;
      *(_DWORD *)(a1 + 72) = 2;
      if ( v26 )
      {
        LOBYTE(a2) = 1;
        SRV2_PERF_ENTER_EX(a1 + 584, a2, 391, "Srv2PostToThreadPool", 1);
      }
      v24 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 152LL);
      goto LABEL_62;
    }
    P = (PVOID)ExAllocatePool2(258, 520, 1647465292);
    if ( !P )
    {
      Ecps = -1073741670;
      goto LABEL_44;
    }
    LODWORD(v34) = 34078720;
    Ecps = Smb2ImpersonateWorkItem(v2);
    if ( Ecps < 0 )
      goto LABEL_44;
    pvContextBuffer = 0;
    v41[0] = 0;
    v41[1] = 0;
    *(_QWORD *)v37 = 0;
    v38 = 0;
    Smb2GetUserAndDomainName(v2, &pvContextBuffer, v41, v37);
    Ecps = SrvXsAddPrintJob(
             *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 96LL) + 360LL),
             *(_QWORD *)(a1 + 96) + 360LL,
             &v34,
             *(_QWORD *)(a1 + 96) + 216LL,
             v41,
             v37,
             &v33,
             &v39);
    if ( pvContextBuffer )
      FreeContextBuffer(pvContextBuffer);
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    if ( Ecps < 0 )
      goto LABEL_44;
    LODWORD(pvContextBuffer) = 1;
    *(_QWORD *)v37 = &v34;
    v7 |= 1u;
  }
  else
  {
    LODWORD(pvContextBuffer) = 0;
    *(_QWORD *)v37 = v2 + 192;
  }
  LODWORD(v43) = 12;
  v8 = v4[17];
  LOWORD(v44) = 0;
  HIDWORD(v43) = v8;
  v9 = v4[26] | 0x100;
  if ( *(_DWORD *)(a1 + 72) )
    v9 = v4[26];
  if ( *(_BYTE *)(v2 + 377) && !*(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL) && *(_BYTE *)(v2 + 5) )
  {
    Ecps = Smb2RetrieveCreate(a1);
    if ( !Ecps )
    {
LABEL_9:
      BuildResponse = Smb2CreateBuildResponse((_QWORD *)a1);
      if ( BuildResponse < 0 )
      {
        Smb2CloseFile(*(_QWORD *)(v2 + 72));
        Smb2SetError(
          a1,
          (unsigned int)BuildResponse,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c",
          3849);
      }
      else
      {
        Smb2SetSuccess(a1, 0);
      }
      return Srv2CompleteWorkItem(a1, 0);
    }
    if ( Ecps != -1073741802 )
    {
      Smb2ReleaseLeaseReferenceForWorkItem(v2);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 81, &WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1, Ecps);
      }
      v18 = 3570;
LABEL_41:
      v19 = (unsigned int)Ecps;
LABEL_29:
      Smb2SetError(a1, v19, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", v18);
      return Srv2CompleteWorkItem(a1, 0);
    }
  }
  Ecps = Smb2CreateEcps(a1);
  if ( Ecps < 0 )
    goto LABEL_44;
  v13 = (*(_BYTE *)(v2 + 379) || *(_BYTE *)(v2 + 382)) && *(_BYTE *)(v2 + 5);
  v14 = v2 + 232;
  if ( !*(_QWORD *)(v2 + 232) )
    v14 = 0;
  v15 = Smb2CreateFile(
          *(struct _UNICODE_STRING **)v37,
          v40,
          v4[23],
          v7,
          v4[25],
          v9,
          (union _LARGE_INTEGER *)(v2 + 240),
          *(void **)(v2 + 208),
          *(_DWORD *)(v2 + 216),
          *(_QWORD *)(v2 + 224),
          &v43,
          (char)pvContextBuffer,
          v14,
          *(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL),
          0,
          521,
          (_QWORD *)a1,
          (struct _IO_STATUS_BLOCK *)Src,
          0,
          *(struct _ECP_LIST **)(v2 + 320),
          -1,
          v13,
          0);
  Ecps = v15;
  if ( (v15 == -1073741270 || v15 == -1073741771)
    && *(_BYTE *)(v2 + 377)
    && !*(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL)
    && *(_BYTE *)(v2 + 5) )
  {
    if ( !(unsigned int)Smb2RetrieveCreate(a1) )
      goto LABEL_9;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 82, &WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1, Ecps);
    }
  }
  if ( Ecps < 0 )
  {
    if ( Ecps == -1073741790 )
      ++*(_DWORD *)(Srv2Statistics + 48);
    if ( !(_WORD)v34 )
    {
      if ( Ecps == -1073741757 )
      {
        if ( *(_DWORD *)(a1 + 72) != 1 )
          return Smb2CreateRetryOnSharingViolation(a1);
      }
      else if ( Ecps == -2147483603 )
      {
        v28 = Src[1];
        v29 = *((unsigned __int16 *)Src[1] + 2) + 8;
        Src[1] = 0;
        ExtendedErrorBuffer = (_DWORD *)Smb2AllocateExtendedErrorBuffer(a1, 0, v29 + 8, 0);
        if ( ExtendedErrorBuffer )
        {
          ExtendedErrorBuffer[1] = 1280137555;
          *ExtendedErrorBuffer = v29 + 4;
          memmove(ExtendedErrorBuffer + 2, v28, v29);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 83, &WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, v5);
          }
          Ecps = -1073741670;
        }
        Smb2SetError(a1, (unsigned int)Ecps, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", 3764);
        ExFreePoolWithTag(v28, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_Zd(
            WPP_GLOBAL_Control->AttachedDevice,
            84,
            (unsigned int)&WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
            v5,
            Ecps);
        }
        return Srv2CompleteWorkItem(a1, 0);
      }
LABEL_35:
      if ( *(_BYTE *)(v2 + 306) )
      {
        v20 = *(_QWORD *)(v2 + 104);
        if ( v20 )
        {
          Smb2LeaseDecrementOpensInProgressAndCloseIfUnused(v20, a2, 0);
          Smb2DereferenceLease(*(PVOID *)(v2 + 104));
          *(_QWORD *)(v2 + 104) = 0;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_Zd(
          WPP_GLOBAL_Control->AttachedDevice,
          85,
          (unsigned int)&WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
          v2 + 192,
          Ecps);
      }
      v18 = 3785;
      goto LABEL_41;
    }
    SrvXsSchedulePrintJob(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 96LL) + 360LL), v33);
LABEL_44:
    if ( (_WORD)v34 )
    {
      ExFreePoolWithTag(P, 0);
      LOWORD(v34) = 0;
    }
    goto LABEL_35;
  }
  *(_QWORD *)(*(_QWORD *)(v2 + 72) + 304LL) = v4[8];
  *(_DWORD *)(*(_QWORD *)(v2 + 72) + 328LL) = v33;
  *(_BYTE *)(*(_QWORD *)(v2 + 72) + 243LL) = *(_BYTE *)(v2 + 309);
  if ( (_WORD)v34 )
  {
    ExFreePoolWithTag(P, 0);
    LOWORD(v34) = 0;
    *(_BYTE *)(*(_QWORD *)(v2 + 72) + 232LL) = 1;
  }
  if ( *(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL) == 1 )
  {
    if ( *(_QWORD *)(v2 + 80)
      || (FileHandle = Smb2GetFileHandle(*(_QWORD *)(v2 + 72)), (*(_QWORD *)(v2 + 80) = FileHandle) != 0) )
    {
      v23 = Smb2ImpersonateWorkItem(v2);
      Smb2SetDefaultPipeMode(*(HANDLE *)(*(_QWORD *)(v2 + 80) + 88LL));
      if ( v23 >= 0 )
        PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    }
    *(_BYTE *)(*(_QWORD *)(v2 + 72) + 239LL) = 1;
  }
  if ( Ecps != 264 )
    goto LABEL_9;
  v16 = *(_QWORD *)(a1 + 560);
  if ( !*(_QWORD *)(v16 + 80) )
  {
    v17 = Smb2GetFileHandle(*(_QWORD *)(v16 + 72));
    *(_QWORD *)(v16 + 80) = v17;
    if ( !v17 )
    {
      Smb2CloseFile(*(_QWORD *)(v16 + 72));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, &WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
      }
      v18 = 3321;
      v19 = 3221225768LL;
      goto LABEL_29;
    }
  }
  LOBYTE(a2) = 1;
  *(_QWORD *)(a1 + 48) = Smb2WaitForOplockBreakReal;
  if ( (int)Smb2PreGoAsync2Ex(a1, a2, 0) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 79, &WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
    }
    v26 = *(_DWORD *)(a1 + 8) == 5;
    *(_DWORD *)(a1 + 72) = 1;
    if ( v26 )
    {
      LOBYTE(v32) = 1;
      LOBYTE(v31) = 1;
      SRV2_PERF_ENTER_EX(a1 + 584, v31, 391, "Srv2PostToThreadPool", v32);
    }
    v24 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 144LL);
LABEL_62:
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    return RfspThreadPoolNodeQueueWorkItem(*(_QWORD *)(v24 + 8LL * CurrentNodeNumber + 8), a1 + 32, 0);
  }
  return Smb2GoAsyncForSyncCall(a1);
}

```

## disassembly

```asm
0x140079c80  push    rbp
0x140079c82  push    rbx
0x140079c83  push    rsi
0x140079c84  push    rdi
0x140079c85  push    r12
0x140079c87  push    r13
0x140079c89  push    r14
0x140079c8b  push    r15
0x140079c8d  lea     rbp, [rsp+8]
0x140079c92  sub     rsp, 138h
0x140079c99  mov     rax, cs:__security_cookie
0x140079ca0  xor     rax, rsp
0x140079ca3  mov     [rbp+30h+var_48], rax
0x140079ca7  mov     rax, [rcx+130h]
0x140079cae  xor     r14d, r14d
0x140079cb1  mov     rsi, [rcx+230h]
0x140079cb8  xorps   xmm0, xmm0
0x140079cbb  mov     rbx, rcx
0x140079cbe  mov     rdi, [rax+18h]
0x140079cc2  xor     eax, eax
0x140079cc4  movups  xmmword ptr [rbp+30h+Src], xmm0
0x140079cc8  mov     [rbp+30h+var_58], rax
0x140079ccc  lea     r12, [rsi+0C0h]
0x140079cd3  mov     [rbp+30h+var_50], eax
0x140079cd6  mov     eax, [rdi+58h]
0x140079cd9  mov     r15d, [rdi+60h]
0x140079cdd  mov     [rbp+30h+var_A8], r14
0x140079ce1  mov     [rbp+30h+P], r14
0x140079ce5  mov     [rbp+30h+var_B0], r14d
0x140079ce9  mov     [rbp+30h+var_80], r14d
0x140079ced  mov     [rbp+30h+var_7C], eax
0x140079cf0  mov     rax, [rsi+38h]
0x140079cf4  cmp     dword ptr [rax+4Ch], 7Fh
0x140079cf8  jz      loc_14007A005
0x140079cfe  mov     dword ptr [rbp+30h+pvContextBuffer], r14d
0x140079d02  mov     qword ptr [rbp+30h+var_90], r12
0x140079d06  mov     dword ptr [rbp+30h+var_58], 0Ch
0x140079d0d  mov     eax, [rdi+44h]
0x140079d10  mov     word ptr [rbp+30h+var_50], r14w
0x140079d15  mov     dword ptr [rbp+30h+var_58+4], eax
0x140079d18  mov     ecx, [rdi+68h]
0x140079d1b  mov     r14d, ecx
0x140079d1e  bts     r14d, 8
0x140079d23  cmp     dword ptr [rbx+48h], 0
0x140079d27  cmovnz  r14d, ecx
0x140079d2b  cmp     byte ptr [rsi+179h], 0
0x140079d32  jz      short loc_140079D9E
0x140079d34  mov     rax, [rsi+38h]
0x140079d38  cmp     dword ptr [rax+4Ch], 0
0x140079d3c  jnz     short loc_140079D9E
0x140079d3e  cmp     byte ptr [rsi+5], 0
0x140079d42  jz      short loc_140079D9E
0x140079d44  mov     rcx, rbx
0x140079d47  call    Smb2RetrieveCreate
0x140079d4c  mov     r13d, eax
0x140079d4f  test    eax, eax
0x140079d51  jnz     loc_140097E51
0x140079d57  mov     rcx, rbx
0x140079d5a  call    Smb2CreateBuildResponse
0x140079d5f  mov     edi, eax
0x140079d61  test    eax, eax
0x140079d63  js      loc_14007A100
0x140079d69  xor     edx, edx
0x140079d6b  mov     rcx, rbx
0x140079d6e  call    Smb2SetSuccess
0x140079d73  xor     edx, edx
0x140079d75  mov     rcx, rbx
0x140079d78  call    Srv2CompleteWorkItem
0x140079d7d  mov     rcx, [rbp+30h+var_48]
0x140079d81  xor     rcx, rsp; StackCookie
0x140079d84  call    __security_check_cookie
0x140079d89  add     rsp, 138h
0x140079d90  pop     r15
0x140079d92  pop     r14
0x140079d94  pop     r13
0x140079d96  pop     r12
0x140079d98  pop     rdi
0x140079d99  pop     rsi
0x140079d9a  pop     rbx
0x140079d9b  pop     rbp
0x140079d9c  retn
0x140079d9e  mov     rcx, rbx
0x140079da1  call    Smb2CreateEcps
0x140079da6  mov     r13d, eax
0x140079da9  test    eax, eax
0x140079dab  js      loc_14007A017
0x140079db1  cmp     byte ptr [rsi+17Bh], 0
0x140079db8  jnz     loc_14007A042
0x140079dbe  cmp     byte ptr [rsi+17Eh], 0
0x140079dc5  jnz     loc_14007A042
0x140079dcb  xor     r9b, r9b
0x140079dce  mov     rcx, [rsi+38h]
0x140079dd2  lea     r8, [rsi+0F0h]
0x140079dd9  xor     eax, eax
0x140079ddb  lea     rdx, [rsi+0E8h]
0x140079de2  cmp     [rdx], rax
0x140079de5  mov     [rsp+170h+var_C0], al; char
0x140079dec  mov     [rsp+170h+var_C8], r9b; char
0x140079df4  cmovz   rdx, rax
0x140079df8  mov     rax, [rsi+140h]
0x140079dff  mov     r9d, r15d; int
0x140079e02  mov     [rsp+170h+var_D0], 0FFFFFFFFFFFFFFFFh; __int64
0x140079e0e  mov     [rsp+170h+var_D8], rax; __int64
0x140079e16  lea     rax, [rbp+30h+Src]
0x140079e1a  mov     qword ptr [rsp+170h+var_E0], 0; int
0x140079e26  mov     [rsp+170h+var_E8], rax; __int64
0x140079e2e  mov     eax, [rcx+4Ch]
0x140079e31  mov     rcx, qword ptr [rbp+30h+var_90]; int
0x140079e35  mov     [rsp+170h+var_F0], rbx; __int64
0x140079e3d  mov     [rsp+170h+var_F8], 209h; int
0x140079e45  mov     qword ptr [rsp+170h+var_100], 0; int
0x140079e4e  mov     [rsp+170h+var_108], eax; int
0x140079e52  mov     eax, dword ptr [rbp+30h+pvContextBuffer]
0x140079e55  mov     [rsp+170h+var_110], rdx; __int64
0x140079e5a  mov     edx, [rbp+30h+var_7C]; int
0x140079e5d  mov     dword ptr [rsp+170h+var_118], eax; char
0x140079e61  lea     rax, [rbp+30h+var_58]
0x140079e65  mov     [rsp+170h+var_120], rax; __int64
0x140079e6a  mov     rax, [rsi+0E0h]
0x140079e71  mov     [rsp+170h+var_128], rax; __int64
0x140079e76  mov     eax, [rsi+0D8h]
0x140079e7c  mov     [rsp+170h+var_130], eax; ULONG
0x140079e80  mov     rax, [rsi+0D0h]
0x140079e87  mov     [rsp+170h+var_138], rax; __int64
0x140079e8c  mov     eax, [rdi+64h]
0x140079e8f  mov     [rsp+170h+var_140], r8; __int64
0x140079e94  mov     r8d, [rdi+5Ch]; int
0x140079e98  mov     [rsp+170h+var_148], r14d; int
0x140079e9d  mov     [rsp+170h+var_150], eax; ULONG
0x140079ea1  call    Smb2CreateFile
0x140079ea6  lea     r14, WPP_GLOBAL_Control
0x140079ead  mov     r13d, eax
0x140079eb0  cmp     eax, 0C000022Ah
0x140079eb5  jz      loc_14007A09C
0x140079ebb  cmp     eax, 0C0000035h
0x140079ec0  jz      loc_14007A09C
0x140079ec6  test    r13d, r13d
0x140079ec9  js      loc_140079F81
0x140079ecf  mov     rax, [rsi+48h]
0x140079ed3  mov     ecx, [rdi+20h]
0x140079ed6  mov     [rax+130h], rcx
0x140079edd  mov     rcx, [rsi+48h]
0x140079ee1  mov     eax, [rbp+30h+var_B0]
0x140079ee4  mov     [rcx+148h], eax
0x140079eea  mov     rcx, [rsi+48h]
0x140079eee  movzx   eax, byte ptr [rsi+135h]
0x140079ef5  mov     [rcx+0F3h], al
0x140079efb  cmp     word ptr [rbp+30h+var_A8], 0
0x140079f00  ja      loc_14007A1DF
0x140079f06  mov     rax, [rsi+38h]
0x140079f0a  cmp     dword ptr [rax+4Ch], 1
0x140079f0e  jz      loc_14007A054
0x140079f14  cmp     r13d, 108h
0x140079f1b  jnz     loc_140079D57
0x140079f21  mov     rdi, [rbx+230h]
0x140079f28  cmp     qword ptr [rdi+50h], 0
0x140079f2d  jnz     loc_140097FFF
0x140079f33  mov     rcx, [rdi+48h]
0x140079f37  call    Smb2GetFileHandle
0x140079f3c  mov     [rdi+50h], rax
0x140079f40  test    rax, rax
0x140079f43  jnz     loc_140097FFF
0x140079f49  mov     rcx, [rdi+48h]
0x140079f4d  call    Smb2CloseFile
0x140079f52  mov     rcx, cs:WPP_GLOBAL_Control
0x140079f59  cmp     rcx, r14
0x140079f5c  jnz     loc_14007A223
0x140079f62  mov     r9d, 0CF9h
0x140079f68  mov     edx, 0C0000128h
0x140079f6d  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140079f74  mov     rcx, rbx
0x140079f77  call    _Smb2SetError
0x140079f7c  jmp     loc_140079D73
0x140079f81  cmp     r13d, 0C0000022h
0x140079f88  jz      loc_14007A1D0
0x140079f8e  cmp     word ptr [rbp+30h+var_A8], 0
0x140079f93  jnz     loc_14007A0DD
0x140079f99  cmp     r13d, 0C0000043h
0x140079fa0  jz      loc_14007A0C6
0x140079fa6  cmp     r13d, 8000002Dh
0x140079fad  jz      loc_140097F0A
0x140079fb3  cmp     byte ptr [rsi+132h], 0
0x140079fba  jz      short loc_140079FDE
0x140079fbc  mov     rcx, [rsi+68h]
0x140079fc0  test    rcx, rcx
0x140079fc3  jz      short loc_140079FDE
0x140079fc5  xor     r8d, r8d
0x140079fc8  call    Smb2LeaseDecrementOpensInProgressAndCloseIfUnused
0x140079fcd  mov     rcx, [rsi+68h]
0x140079fd1  call    Smb2DereferenceLease
0x140079fd6  mov     qword ptr [rsi+68h], 0
0x140079fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140079fe5  cmp     rcx, r14
0x140079fe8  jz      short loc_140079FF7
0x140079fea  test    dword ptr [rcx+2Ch], 100000h
0x140079ff1  jnz     loc_14007A254
0x140079ff7  mov     r9d, 0EC9h
0x140079ffd  mov     edx, r13d
0x14007a000  jmp     loc_140079F6D
0x14007a005  mov     eax, [rdi+64h]
0x14007a008  cmp     eax, 1
0x14007a00b  jnz     loc_140097D10
0x14007a011  mov     r13d, 0C0000034h
0x14007a017  lea     r14, WPP_GLOBAL_Control
0x14007a01e  cmp     word ptr [rbp+30h+var_A8], 0
0x14007a023  jbe     short loc_140079FB3
0x14007a025  mov     rcx, [rbp+30h+P]; P
0x14007a029  xor     edx, edx; Tag
0x14007a02b  call    cs:__imp_ExFreePoolWithTag
0x14007a032  nop     dword ptr [rax+rax+00h]
0x14007a037  xor     eax, eax
0x14007a039  mov     word ptr [rbp+30h+var_A8], ax
0x14007a03d  jmp     loc_140079FB3
0x14007a042  cmp     byte ptr [rsi+5], 0
0x14007a046  jz      loc_140079DCB
0x14007a04c  mov     r9b, 1
0x14007a04f  jmp     loc_140079DCE
0x14007a054  cmp     qword ptr [rsi+50h], 0
0x14007a059  jnz     short loc_14007A06D
0x14007a05b  mov     rcx, [rsi+48h]
0x14007a05f  call    Smb2GetFileHandle
0x14007a064  mov     [rsi+50h], rax
0x14007a068  test    rax, rax
0x14007a06b  jz      short loc_14007A08C
0x14007a06d  mov     rcx, rsi
0x14007a070  call    Smb2ImpersonateWorkItem
0x14007a075  mov     rcx, [rsi+50h]
0x14007a079  mov     edi, eax
0x14007a07b  mov     rcx, [rcx+58h]; FileHandle
0x14007a07f  call    Smb2SetDefaultPipeMode
0x14007a084  test    edi, edi
0x14007a086  jns     loc_14007A207
0x14007a08c  mov     rax, [rsi+48h]
0x14007a090  mov     byte ptr [rax+0EFh], 1
0x14007a097  jmp     loc_140079F14
0x14007a09c  cmp     byte ptr [rsi+179h], 0
0x14007a0a3  jz      loc_140079EC6
0x14007a0a9  mov     rax, [rsi+38h]
0x14007a0ad  cmp     dword ptr [rax+4Ch], 0
0x14007a0b1  jnz     loc_140079EC6
0x14007a0b7  cmp     byte ptr [rsi+5], 0
0x14007a0bb  jz      loc_140079EC6
0x14007a0c1  jmp     loc_140097EB0
0x14007a0c6  cmp     dword ptr [rbx+48h], 1
0x14007a0ca  jz      loc_140079FB3
0x14007a0d0  mov     rcx, rbx
0x14007a0d3  call    Smb2CreateRetryOnSharingViolation
0x14007a0d8  jmp     loc_140079D7D
0x14007a0dd  mov     rax, [rsi+38h]
0x14007a0e1  mov     edx, [rbp+30h+var_B0]
0x14007a0e4  mov     rcx, [rax+60h]
0x14007a0e8  mov     rcx, [rcx+168h]
0x14007a0ef  call    cs:__imp_SrvXsSchedulePrintJob
0x14007a0f6  nop     dword ptr [rax+rax+00h]
0x14007a0fb  jmp     loc_14007A01E
0x14007a100  mov     rcx, [rsi+48h]
0x14007a104  call    Smb2CloseFile
0x14007a109  mov     r9d, 0F09h
0x14007a10f  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14007a116  mov     edx, edi
0x14007a118  mov     rcx, rbx
0x14007a11b  call    _Smb2SetError
0x14007a120  jmp     loc_140079D73
0x14007a125  mov     rax, [rbx+40h]
0x14007a129  mov     rdi, [rax+90h]
0x14007a130  call    cs:__imp_KeGetCurrentNodeNumber
0x14007a137  nop     dword ptr [rax+rax+00h]
0x14007a13c  movzx   ecx, ax
0x14007a13f  xor     r8d, r8d
0x14007a142  lea     rdx, [rbx+20h]
0x14007a146  mov     rcx, [rdi+rcx*8+8]
0x14007a14b  call    RfspThreadPoolNodeQueueWorkItem
0x14007a150  jmp     loc_140079D7D
0x14007a155  cmp     dword ptr [rcx+8], 5
0x14007a159  lea     rax, Smb2ExecuteCreateReal
0x14007a160  mov     [rcx+30h], rax
0x14007a164  mov     dword ptr [rcx+48h], 2
0x14007a16b  jnz     short loc_14007A18D
0x14007a16d  add     rcx, 248h
0x14007a174  mov     byte ptr [rsp+170h+var_150], 1
0x14007a179  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14007a180  mov     r8d, 187h
0x14007a186  mov     dl, 1
0x14007a188  call    SRV2_PERF_ENTER_EX
0x14007a18d  mov     rax, [rbx+40h]
0x14007a191  mov     rdi, [rax+98h]
0x14007a198  jmp     short loc_14007A130
0x14007a19a  cmp     dword ptr [rbx+8], 5
0x14007a19e  mov     dword ptr [rbx+48h], 1
0x14007a1a5  jnz     loc_14007A125
0x14007a1ab  lea     rcx, [rbx+248h]
0x14007a1b2  mov     byte ptr [rsp+170h+var_150], 1
0x14007a1b7  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14007a1be  mov     r8d, 187h
0x14007a1c4  mov     dl, 1
0x14007a1c6  call    SRV2_PERF_ENTER_EX
0x14007a1cb  jmp     loc_14007A125
0x14007a1d0  mov     rax, cs:Srv2Statistics
0x14007a1d7  inc     dword ptr [rax+30h]
0x14007a1da  jmp     loc_140079F8E
  ... truncated ...
```
