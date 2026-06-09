# Smb2ExecuteCreateReal

- ea: `0x140079c30`
- end: `0x14007a230`
- name: `Smb2ExecuteCreateReal`
- size: `1536`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14006574c`
- `0x140079bd0`

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
- `0x1400791c8`
- `0x140079c30`
- `0x14007a240`
- `0x14007a84c`
- `0x140085d40`
- `0x140086110`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140097cfa`
- `ntoskrnl!ExAllocatePool2` at `0x140097cfa`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007a0e0`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007a0e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079fdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a195`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097f59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079fdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a195`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097f59`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007a1c2`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097dd4`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007a1c2`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097dd4`
- `srvnet!SrvXsSchedulePrintJob` at `0x14007a09f`
- `srvnet!SrvXsSchedulePrintJob` at `0x14007a09f`
- `srvnet!SrvXsAddPrintJob` at `0x140097da5`
- `srvnet!SrvXsAddPrintJob` at `0x140097da5`
- `ksecdd!FreeContextBuffer` at `0x140097dbd`
- `ksecdd!FreeContextBuffer` at `0x140097dbd`

## string_xrefs

- `0x140079f1d`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14007a0bf`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x140097f42`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14007a129`: `Srv2PostToThreadPool`
- `0x14007a167`: `Srv2PostToThreadPool`

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
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdi
  __int64 v19; // rax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // eax
  __int64 FileHandle; // rax
  int v25; // edi
  __int64 v26; // rdi
  USHORT CurrentNodeNumber; // ax
  bool v28; // zf
  void *v30; // rsi
  unsigned int v31; // edi
  _DWORD *ExtendedErrorBuffer; // rcx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // [rsp+20h] [rbp-120h]
  unsigned int v37; // [rsp+C0h] [rbp-80h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-78h] BYREF
  PVOID P; // [rsp+D0h] [rbp-70h]
  PVOID pvContextBuffer; // [rsp+D8h] [rbp-68h] BYREF
  int v41[2]; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+E8h] [rbp-58h]
  int v43; // [rsp+F0h] [rbp-50h] BYREF
  int v44; // [rsp+F4h] [rbp-4Ch]
  _QWORD v45[2]; // [rsp+F8h] [rbp-48h] BYREF
  void *Src[2]; // [rsp+108h] [rbp-38h] BYREF
  __int64 v47; // [rsp+118h] [rbp-28h] BYREF
  int v48; // [rsp+120h] [rbp-20h]

  v2 = *(_QWORD *)(a1 + 560);
  v4 = *(unsigned int **)(*(_QWORD *)(a1 + 304) + 24LL);
  *(_OWORD *)Src = 0;
  v47 = 0;
  v5 = v2 + 192;
  v48 = 0;
  v6 = v4[22];
  v7 = v4[24];
  v38 = 0;
  P = 0;
  v37 = 0;
  v43 = 0;
  v44 = v6;
  if ( *(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL) == 127 )
  {
    v23 = v4[25];
    if ( v23 == 1 || v23 == 4 )
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
      v28 = *(_DWORD *)(a1 + 8) == 5;
      *(_QWORD *)(a1 + 48) = Smb2ExecuteCreateReal;
      *(_DWORD *)(a1 + 72) = 2;
      if ( v28 )
      {
        LOBYTE(a2) = 1;
        SRV2_PERF_ENTER_EX(a1 + 584, a2, 391, "Srv2PostToThreadPool", 1);
      }
      v26 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 152LL);
      goto LABEL_62;
    }
    P = (PVOID)ExAllocatePool2(258, 520, 1647465292);
    if ( !P )
    {
      Ecps = -1073741670;
      goto LABEL_44;
    }
    LODWORD(v38) = 34078720;
    Ecps = Smb2ImpersonateWorkItem(v2);
    if ( Ecps < 0 )
      goto LABEL_44;
    pvContextBuffer = 0;
    v45[0] = 0;
    v45[1] = 0;
    *(_QWORD *)v41 = 0;
    v42 = 0;
    Smb2GetUserAndDomainName(v2, &pvContextBuffer, v45, v41);
    Ecps = SrvXsAddPrintJob(
             *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 96LL) + 360LL),
             *(_QWORD *)(a1 + 96) + 360LL,
             &v38,
             *(_QWORD *)(a1 + 96) + 216LL,
             v45,
             v41,
             &v37,
             &v43);
    if ( pvContextBuffer )
      FreeContextBuffer(pvContextBuffer);
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    if ( Ecps < 0 )
      goto LABEL_44;
    LODWORD(pvContextBuffer) = 1;
    *(_QWORD *)v41 = &v38;
    v7 |= 1u;
  }
  else
  {
    LODWORD(pvContextBuffer) = 0;
    *(_QWORD *)v41 = v2 + 192;
  }
  LODWORD(v47) = 12;
  v8 = v4[17];
  LOWORD(v48) = 0;
  HIDWORD(v47) = v8;
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
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1, Ecps);
      }
      v20 = 3570;
LABEL_41:
      v21 = (unsigned int)Ecps;
LABEL_29:
      Smb2SetError(a1, v21, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", v20);
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
          *(struct _UNICODE_STRING **)v41,
          v44,
          v4[23],
          v7,
          v4[25],
          v9,
          (union _LARGE_INTEGER *)(v2 + 240),
          *(void **)(v2 + 208),
          *(_DWORD *)(v2 + 216),
          *(_QWORD *)(v2 + 224),
          &v47,
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
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1, Ecps);
    }
  }
  if ( Ecps < 0 )
  {
    if ( Ecps == -1073741790 )
      ++*(_DWORD *)(Srv2Statistics + 48);
    if ( !(_WORD)v38 )
    {
      if ( Ecps == -1073741757 )
      {
        if ( *(_DWORD *)(a1 + 72) != 1 )
          return Smb2CreateRetryOnSharingViolation(a1);
      }
      else if ( Ecps == -2147483603 )
      {
        v30 = Src[1];
        v31 = *((unsigned __int16 *)Src[1] + 2) + 8;
        Src[1] = 0;
        ExtendedErrorBuffer = (_DWORD *)Smb2AllocateExtendedErrorBuffer(a1, 0, v31 + 8, 0);
        if ( ExtendedErrorBuffer )
        {
          ExtendedErrorBuffer[1] = 1280137555;
          *ExtendedErrorBuffer = v31 + 4;
          memmove(ExtendedErrorBuffer + 2, v30, v31);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, v5);
          }
          Ecps = -1073741670;
        }
        Smb2SetError(a1, (unsigned int)Ecps, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", 3764);
        ExFreePoolWithTag(v30, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_Zd(
            WPP_GLOBAL_Control->AttachedDevice,
            84,
            (unsigned int)WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
            v5,
            Ecps);
        }
        return Srv2CompleteWorkItem(a1, 0);
      }
LABEL_35:
      if ( *(_BYTE *)(v2 + 306) )
      {
        v22 = *(_QWORD *)(v2 + 104);
        if ( v22 )
        {
          Smb2LeaseDecrementOpensInProgressAndCloseIfUnused(v22, a2, 0);
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
          (unsigned int)WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
          v2 + 192,
          Ecps);
      }
      v20 = 3785;
      goto LABEL_41;
    }
    SrvXsSchedulePrintJob(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 96LL) + 360LL), v37);
LABEL_44:
    if ( (_WORD)v38 )
    {
      ExFreePoolWithTag(P, 0);
      LOWORD(v38) = 0;
    }
    goto LABEL_35;
  }
  *(_QWORD *)(*(_QWORD *)(v2 + 72) + 304LL) = v4[8];
  *(_DWORD *)(*(_QWORD *)(v2 + 72) + 328LL) = v37;
  *(_BYTE *)(*(_QWORD *)(v2 + 72) + 243LL) = *(_BYTE *)(v2 + 309);
  if ( (_WORD)v38 )
  {
    ExFreePoolWithTag(P, 0);
    LOWORD(v38) = 0;
    *(_BYTE *)(*(_QWORD *)(v2 + 72) + 232LL) = 1;
  }
  if ( *(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL) == 1 )
  {
    if ( *(_QWORD *)(v2 + 80)
      || (FileHandle = Smb2GetFileHandle(*(_QWORD *)(v2 + 72), a2, v16), (*(_QWORD *)(v2 + 80) = FileHandle) != 0) )
    {
      v25 = Smb2ImpersonateWorkItem(v2);
      Smb2SetDefaultPipeMode(*(HANDLE *)(*(_QWORD *)(v2 + 80) + 88LL));
      if ( v25 >= 0 )
        PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    }
    *(_BYTE *)(*(_QWORD *)(v2 + 72) + 239LL) = 1;
  }
  if ( Ecps != 264 )
    goto LABEL_9;
  v18 = *(_QWORD *)(a1 + 560);
  if ( !*(_QWORD *)(v18 + 80) )
  {
    v19 = Smb2GetFileHandle(*(_QWORD *)(v18 + 72), a2, v16);
    *(_QWORD *)(v18 + 80) = v19;
    if ( !v19 )
    {
      Smb2CloseFile(*(_QWORD *)(v18 + 72));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
      }
      v20 = 3321;
      v21 = 3221225768LL;
      goto LABEL_29;
    }
  }
  LOBYTE(a2) = 1;
  *(_QWORD *)(a1 + 48) = Smb2WaitForOplockBreakReal;
  if ( (int)Smb2PreGoAsync2Ex(a1, a2, 0, v17) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
    }
    v28 = *(_DWORD *)(a1 + 8) == 5;
    *(_DWORD *)(a1 + 72) = 1;
    if ( v28 )
    {
      LOBYTE(v36) = 1;
      LOBYTE(v33) = 1;
      SRV2_PERF_ENTER_EX(a1 + 584, v33, 391, "Srv2PostToThreadPool", v36);
    }
    v26 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 144LL);
LABEL_62:
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    return RfspThreadPoolNodeQueueWorkItem(*(_QWORD *)(v26 + 8LL * CurrentNodeNumber + 8), a1 + 32, 0);
  }
  return Smb2GoAsyncForSyncCall(a1, v33, v34, v35);
}

```

## disassembly

```asm
0x140079c30  push    rbp
0x140079c32  push    rbx
0x140079c33  push    rsi
0x140079c34  push    rdi
0x140079c35  push    r12
0x140079c37  push    r13
0x140079c39  push    r14
0x140079c3b  push    r15
0x140079c3d  lea     rbp, [rsp+8]
0x140079c42  sub     rsp, 138h
0x140079c49  mov     rax, cs:__security_cookie
0x140079c50  xor     rax, rsp
0x140079c53  mov     [rbp+30h+var_48], rax
0x140079c57  mov     rax, [rcx+130h]
0x140079c5e  xor     r14d, r14d
0x140079c61  mov     rsi, [rcx+230h]
0x140079c68  xorps   xmm0, xmm0
0x140079c6b  mov     rbx, rcx
0x140079c6e  mov     rdi, [rax+18h]
0x140079c72  xor     eax, eax
0x140079c74  movups  xmmword ptr [rbp+30h+Src], xmm0
0x140079c78  mov     [rbp+30h+var_58], rax
0x140079c7c  lea     r12, [rsi+0C0h]
0x140079c83  mov     [rbp+30h+var_50], eax
0x140079c86  mov     eax, [rdi+58h]
0x140079c89  mov     r15d, [rdi+60h]
0x140079c8d  mov     [rbp+30h+var_A8], r14
0x140079c91  mov     [rbp+30h+P], r14
0x140079c95  mov     [rbp+30h+var_B0], r14d
0x140079c99  mov     [rbp+30h+var_80], r14d
0x140079c9d  mov     [rbp+30h+var_7C], eax
0x140079ca0  mov     rax, [rsi+38h]
0x140079ca4  cmp     dword ptr [rax+4Ch], 7Fh
0x140079ca8  jz      loc_140079FB5
0x140079cae  mov     dword ptr [rbp+30h+pvContextBuffer], r14d
0x140079cb2  mov     qword ptr [rbp+30h+var_90], r12
0x140079cb6  mov     dword ptr [rbp+30h+var_58], 0Ch
0x140079cbd  mov     eax, [rdi+44h]
0x140079cc0  mov     word ptr [rbp+30h+var_50], r14w
0x140079cc5  mov     dword ptr [rbp+30h+var_58+4], eax
0x140079cc8  mov     ecx, [rdi+68h]
0x140079ccb  mov     r14d, ecx
0x140079cce  bts     r14d, 8
0x140079cd3  cmp     dword ptr [rbx+48h], 0
0x140079cd7  cmovnz  r14d, ecx
0x140079cdb  cmp     byte ptr [rsi+179h], 0
0x140079ce2  jz      short loc_140079D4E
0x140079ce4  mov     rax, [rsi+38h]
0x140079ce8  cmp     dword ptr [rax+4Ch], 0
0x140079cec  jnz     short loc_140079D4E
0x140079cee  cmp     byte ptr [rsi+5], 0
0x140079cf2  jz      short loc_140079D4E
0x140079cf4  mov     rcx, rbx
0x140079cf7  call    Smb2RetrieveCreate
0x140079cfc  mov     r13d, eax
0x140079cff  test    eax, eax
0x140079d01  jnz     loc_140097E01
0x140079d07  mov     rcx, rbx
0x140079d0a  call    Smb2CreateBuildResponse
0x140079d0f  mov     edi, eax
0x140079d11  test    eax, eax
0x140079d13  js      loc_14007A0B0
0x140079d19  xor     edx, edx
0x140079d1b  mov     rcx, rbx
0x140079d1e  call    Smb2SetSuccess
0x140079d23  xor     edx, edx
0x140079d25  mov     rcx, rbx
0x140079d28  call    Srv2CompleteWorkItem
0x140079d2d  mov     rcx, [rbp+30h+var_48]
0x140079d31  xor     rcx, rsp; StackCookie
0x140079d34  call    __security_check_cookie
0x140079d39  add     rsp, 138h
0x140079d40  pop     r15
0x140079d42  pop     r14
0x140079d44  pop     r13
0x140079d46  pop     r12
0x140079d48  pop     rdi
0x140079d49  pop     rsi
0x140079d4a  pop     rbx
0x140079d4b  pop     rbp
0x140079d4c  retn
0x140079d4e  mov     rcx, rbx
0x140079d51  call    Smb2CreateEcps
0x140079d56  mov     r13d, eax
0x140079d59  test    eax, eax
0x140079d5b  js      loc_140079FC7
0x140079d61  cmp     byte ptr [rsi+17Bh], 0
0x140079d68  jnz     loc_140079FF2
0x140079d6e  cmp     byte ptr [rsi+17Eh], 0
0x140079d75  jnz     loc_140079FF2
0x140079d7b  xor     r9b, r9b
0x140079d7e  mov     rcx, [rsi+38h]
0x140079d82  lea     r8, [rsi+0F0h]
0x140079d89  xor     eax, eax
0x140079d8b  lea     rdx, [rsi+0E8h]
0x140079d92  cmp     [rdx], rax
0x140079d95  mov     [rsp+170h+var_C0], al; char
0x140079d9c  mov     [rsp+170h+var_C8], r9b; char
0x140079da4  cmovz   rdx, rax
0x140079da8  mov     rax, [rsi+140h]
0x140079daf  mov     r9d, r15d; int
0x140079db2  mov     [rsp+170h+var_D0], 0FFFFFFFFFFFFFFFFh; __int64
0x140079dbe  mov     [rsp+170h+var_D8], rax; __int64
0x140079dc6  lea     rax, [rbp+30h+Src]
0x140079dca  mov     qword ptr [rsp+170h+var_E0], 0; int
0x140079dd6  mov     [rsp+170h+var_E8], rax; __int64
0x140079dde  mov     eax, [rcx+4Ch]
0x140079de1  mov     rcx, qword ptr [rbp+30h+var_90]; int
0x140079de5  mov     [rsp+170h+var_F0], rbx; __int64
0x140079ded  mov     [rsp+170h+var_F8], 209h; int
0x140079df5  mov     qword ptr [rsp+170h+var_100], 0; int
0x140079dfe  mov     [rsp+170h+var_108], eax; int
0x140079e02  mov     eax, dword ptr [rbp+30h+pvContextBuffer]
0x140079e05  mov     [rsp+170h+var_110], rdx; __int64
0x140079e0a  mov     edx, [rbp+30h+var_7C]; int
0x140079e0d  mov     dword ptr [rsp+170h+var_118], eax; char
0x140079e11  lea     rax, [rbp+30h+var_58]
0x140079e15  mov     [rsp+170h+var_120], rax; __int64
0x140079e1a  mov     rax, [rsi+0E0h]
0x140079e21  mov     [rsp+170h+var_128], rax; __int64
0x140079e26  mov     eax, [rsi+0D8h]
0x140079e2c  mov     [rsp+170h+var_130], eax; ULONG
0x140079e30  mov     rax, [rsi+0D0h]
0x140079e37  mov     [rsp+170h+var_138], rax; __int64
0x140079e3c  mov     eax, [rdi+64h]
0x140079e3f  mov     [rsp+170h+var_140], r8; __int64
0x140079e44  mov     r8d, [rdi+5Ch]; int
0x140079e48  mov     [rsp+170h+var_148], r14d; int
0x140079e4d  mov     [rsp+170h+var_150], eax; ULONG
0x140079e51  call    Smb2CreateFile
0x140079e56  lea     r14, WPP_GLOBAL_Control
0x140079e5d  mov     r13d, eax
0x140079e60  cmp     eax, 0C000022Ah
0x140079e65  jz      loc_14007A04C
0x140079e6b  cmp     eax, 0C0000035h
0x140079e70  jz      loc_14007A04C
0x140079e76  test    r13d, r13d
0x140079e79  js      loc_140079F31
0x140079e7f  mov     rax, [rsi+48h]
0x140079e83  mov     ecx, [rdi+20h]
0x140079e86  mov     [rax+130h], rcx
0x140079e8d  mov     rcx, [rsi+48h]
0x140079e91  mov     eax, [rbp+30h+var_B0]
0x140079e94  mov     [rcx+148h], eax
0x140079e9a  mov     rcx, [rsi+48h]
0x140079e9e  movzx   eax, byte ptr [rsi+135h]
0x140079ea5  mov     [rcx+0F3h], al
0x140079eab  cmp     word ptr [rbp+30h+var_A8], 0
0x140079eb0  ja      loc_14007A18F
0x140079eb6  mov     rax, [rsi+38h]
0x140079eba  cmp     dword ptr [rax+4Ch], 1
0x140079ebe  jz      loc_14007A004
0x140079ec4  cmp     r13d, 108h
0x140079ecb  jnz     loc_140079D07
0x140079ed1  mov     rdi, [rbx+230h]
0x140079ed8  cmp     qword ptr [rdi+50h], 0
0x140079edd  jnz     loc_140097FAF
0x140079ee3  mov     rcx, [rdi+48h]
0x140079ee7  call    Smb2GetFileHandle
0x140079eec  mov     [rdi+50h], rax
0x140079ef0  test    rax, rax
0x140079ef3  jnz     loc_140097FAF
0x140079ef9  mov     rcx, [rdi+48h]
0x140079efd  call    Smb2CloseFile
0x140079f02  mov     rcx, cs:WPP_GLOBAL_Control
0x140079f09  cmp     rcx, r14
0x140079f0c  jnz     loc_14007A1D3
0x140079f12  mov     r9d, 0CF9h
0x140079f18  mov     edx, 0C0000128h
0x140079f1d  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140079f24  mov     rcx, rbx
0x140079f27  call    _Smb2SetError
0x140079f2c  jmp     loc_140079D23
0x140079f31  cmp     r13d, 0C0000022h
0x140079f38  jz      loc_14007A180
0x140079f3e  cmp     word ptr [rbp+30h+var_A8], 0
0x140079f43  jnz     loc_14007A08D
0x140079f49  cmp     r13d, 0C0000043h
0x140079f50  jz      loc_14007A076
0x140079f56  cmp     r13d, 8000002Dh
0x140079f5d  jz      loc_140097EBA
0x140079f63  cmp     byte ptr [rsi+132h], 0
0x140079f6a  jz      short loc_140079F8E
0x140079f6c  mov     rcx, [rsi+68h]
0x140079f70  test    rcx, rcx
0x140079f73  jz      short loc_140079F8E
0x140079f75  xor     r8d, r8d
0x140079f78  call    Smb2LeaseDecrementOpensInProgressAndCloseIfUnused
0x140079f7d  mov     rcx, [rsi+68h]
0x140079f81  call    Smb2DereferenceLease
0x140079f86  mov     qword ptr [rsi+68h], 0
0x140079f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140079f95  cmp     rcx, r14
0x140079f98  jz      short loc_140079FA7
0x140079f9a  test    dword ptr [rcx+2Ch], 100000h
0x140079fa1  jnz     loc_14007A204
0x140079fa7  mov     r9d, 0EC9h
0x140079fad  mov     edx, r13d
0x140079fb0  jmp     loc_140079F1D
0x140079fb5  mov     eax, [rdi+64h]
0x140079fb8  cmp     eax, 1
0x140079fbb  jnz     loc_140097CC0
0x140079fc1  mov     r13d, 0C0000034h
0x140079fc7  lea     r14, WPP_GLOBAL_Control
0x140079fce  cmp     word ptr [rbp+30h+var_A8], 0
0x140079fd3  jbe     short loc_140079F63
0x140079fd5  mov     rcx, [rbp+30h+P]; P
0x140079fd9  xor     edx, edx; Tag
0x140079fdb  call    cs:__imp_ExFreePoolWithTag
0x140079fe2  nop     dword ptr [rax+rax+00h]
0x140079fe7  xor     eax, eax
0x140079fe9  mov     word ptr [rbp+30h+var_A8], ax
0x140079fed  jmp     loc_140079F63
0x140079ff2  cmp     byte ptr [rsi+5], 0
0x140079ff6  jz      loc_140079D7B
0x140079ffc  mov     r9b, 1
0x140079fff  jmp     loc_140079D7E
0x14007a004  cmp     qword ptr [rsi+50h], 0
0x14007a009  jnz     short loc_14007A01D
0x14007a00b  mov     rcx, [rsi+48h]
0x14007a00f  call    Smb2GetFileHandle
0x14007a014  mov     [rsi+50h], rax
0x14007a018  test    rax, rax
0x14007a01b  jz      short loc_14007A03C
0x14007a01d  mov     rcx, rsi
0x14007a020  call    Smb2ImpersonateWorkItem
0x14007a025  mov     rcx, [rsi+50h]
0x14007a029  mov     edi, eax
0x14007a02b  mov     rcx, [rcx+58h]; FileHandle
0x14007a02f  call    Smb2SetDefaultPipeMode
0x14007a034  test    edi, edi
0x14007a036  jns     loc_14007A1B7
0x14007a03c  mov     rax, [rsi+48h]
0x14007a040  mov     byte ptr [rax+0EFh], 1
0x14007a047  jmp     loc_140079EC4
0x14007a04c  cmp     byte ptr [rsi+179h], 0
0x14007a053  jz      loc_140079E76
0x14007a059  mov     rax, [rsi+38h]
0x14007a05d  cmp     dword ptr [rax+4Ch], 0
0x14007a061  jnz     loc_140079E76
0x14007a067  cmp     byte ptr [rsi+5], 0
0x14007a06b  jz      loc_140079E76
0x14007a071  jmp     loc_140097E60
0x14007a076  cmp     dword ptr [rbx+48h], 1
0x14007a07a  jz      loc_140079F63
0x14007a080  mov     rcx, rbx
0x14007a083  call    Smb2CreateRetryOnSharingViolation
0x14007a088  jmp     loc_140079D2D
0x14007a08d  mov     rax, [rsi+38h]
0x14007a091  mov     edx, [rbp+30h+var_B0]
0x14007a094  mov     rcx, [rax+60h]
0x14007a098  mov     rcx, [rcx+168h]
0x14007a09f  call    cs:__imp_SrvXsSchedulePrintJob
0x14007a0a6  nop     dword ptr [rax+rax+00h]
0x14007a0ab  jmp     loc_140079FCE
0x14007a0b0  mov     rcx, [rsi+48h]
0x14007a0b4  call    Smb2CloseFile
0x14007a0b9  mov     r9d, 0F09h
0x14007a0bf  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14007a0c6  mov     edx, edi
0x14007a0c8  mov     rcx, rbx
0x14007a0cb  call    _Smb2SetError
0x14007a0d0  jmp     loc_140079D23
0x14007a0d5  mov     rax, [rbx+40h]
0x14007a0d9  mov     rdi, [rax+90h]
0x14007a0e0  call    cs:__imp_KeGetCurrentNodeNumber
0x14007a0e7  nop     dword ptr [rax+rax+00h]
0x14007a0ec  movzx   ecx, ax
0x14007a0ef  xor     r8d, r8d
0x14007a0f2  lea     rdx, [rbx+20h]
0x14007a0f6  mov     rcx, [rdi+rcx*8+8]
0x14007a0fb  call    RfspThreadPoolNodeQueueWorkItem
0x14007a100  jmp     loc_140079D2D
0x14007a105  cmp     dword ptr [rcx+8], 5
0x14007a109  lea     rax, Smb2ExecuteCreateReal
0x14007a110  mov     [rcx+30h], rax
0x14007a114  mov     dword ptr [rcx+48h], 2
0x14007a11b  jnz     short loc_14007A13D
0x14007a11d  add     rcx, 248h
0x14007a124  mov     byte ptr [rsp+170h+var_150], 1
0x14007a129  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14007a130  mov     r8d, 187h
0x14007a136  mov     dl, 1
0x14007a138  call    SRV2_PERF_ENTER_EX
0x14007a13d  mov     rax, [rbx+40h]
0x14007a141  mov     rdi, [rax+98h]
0x14007a148  jmp     short loc_14007A0E0
0x14007a14a  cmp     dword ptr [rbx+8], 5
0x14007a14e  mov     dword ptr [rbx+48h], 1
0x14007a155  jnz     loc_14007A0D5
0x14007a15b  lea     rcx, [rbx+248h]
0x14007a162  mov     byte ptr [rsp+170h+var_150], 1
0x14007a167  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14007a16e  mov     r8d, 187h
0x14007a174  mov     dl, 1
0x14007a176  call    SRV2_PERF_ENTER_EX
0x14007a17b  jmp     loc_14007A0D5
0x14007a180  mov     rax, cs:Srv2Statistics
0x14007a187  inc     dword ptr [rax+30h]
0x14007a18a  jmp     loc_140079F3E
  ... truncated ...
```
