# Smb2ContinueDirectPlacementWrite

- ea: `0x14007ea50`
- end: `0x14007f2e8`
- name: `Smb2ContinueDirectPlacementWrite`
- size: `2200`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x14006c150`

## callees

- `0x140005070`
- `0x140006ad0`
- `0x140007090`
- `0x140007400`
- `0x140008190`
- `0x1400125d0`
- `0x140015000`
- `0x140017730`
- `0x1400186f0`
- `0x14001f050`
- `0x1400222ec`
- `0x1400225c4`
- `0x140022958`
- `0x1400240e4`
- `0x140029ed8`
- `0x1400384d0`
- `0x14007ea50`
- `0x14007f2f0`
- `0x140080364`
- `0x140086110`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ebf4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ecec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ede3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ebf4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ecec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ede3`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007f060`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007f060`
- `ntoskrnl!KeDelayExecutionThread` at `0x14007f2a8`
- `ntoskrnl!KeDelayExecutionThread` at `0x14007f2a8`
- `ntoskrnl!IofCallDriver` at `0x14007f247`
- `ntoskrnl!IofCallDriver` at `0x14007f278`
- `ntoskrnl!IofCallDriver` at `0x14007f247`
- `ntoskrnl!IofCallDriver` at `0x14007f278`
- `srvnet!SmbCryptoDecryptRdmaPayload` at `0x14007ec55`
- `srvnet!SmbCryptoDecryptRdmaPayload` at `0x14007ec55`

## string_xrefs

- `0x14007eac6`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14007ee4d`: `Smb2ContinueDirectPlacementWrite`
- `0x14007eef2`: `Smb2ContinueDirectPlacementWrite`
- `0x14007f1e1`: `Smb2ContinueDirectPlacementWrite`

## pseudocode

```c
NTSTATUS __fastcall Smb2ContinueDirectPlacementWrite(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // r13d
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  NTSTATUS result; // eax
  __int64 v12; // rsi
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rbx
  PVOID v20; // r11
  PVOID v21; // rax
  char v22; // dl
  __int64 v23; // rdx
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rcx
  __int64 v27; // rbx
  PVOID v28; // rax
  int v29; // eax
  char v30; // cl
  bool v31; // al
  __int64 v32; // rbx
  __int64 v33; // rcx
  PVOID v34; // r13
  char v35; // al
  __int64 v36; // rcx
  char v37; // r9
  bool v38; // r12
  int v39; // eax
  int v40; // eax
  __int64 (__fastcall *v41)(); // rdx
  int v42; // ecx
  int v43; // r14d
  __int64 v44; // r11
  struct _MDL *v45; // rcx
  char *v46; // rbx
  ULONG v47; // r9d
  struct _MDL *v48; // rdx
  __int64 v49; // rdx
  unsigned int v50; // r14d
  unsigned int i; // ebx
  int BugCheckOnFailure; // [rsp+20h] [rbp-88h]
  int BugCheckOnFailurea; // [rsp+20h] [rbp-88h]
  int Priority; // [rsp+28h] [rbp-80h]
  int v55; // [rsp+60h] [rbp-48h]
  int v56; // [rsp+68h] [rbp-40h]
  union _LARGE_INTEGER Interval; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v58; // [rsp+B8h] [rbp+10h]

  v5 = 0;
  v6 = *(_QWORD *)(a1 + 120);
  v7 = *(unsigned int *)(v6 + 48);
  if ( (int)v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u) )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1, v7);
    }
    v8 = 1911;
LABEL_7:
    v9 = *(unsigned int *)(*(_QWORD *)(a1 + 120) + 48LL);
LABEL_8:
    v10 = a1;
LABEL_9:
    Smb2SetError(v10, v9, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", v8);
    return Srv2CompleteWorkItem(a1, 0);
  }
  v12 = *(_QWORD *)(a1 + 560);
  if ( *(_QWORD *)(v6 + 56) != *(_DWORD *)(v12 + 252) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1, v7);
    }
    v8 = 1922;
    goto LABEL_7;
  }
  if ( *(_BYTE *)(*(_QWORD *)(v12 + 56) + 88LL)
    && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 88) + 24LL) + 40LL) + 0x2000000LL < *(_QWORD *)(v12 + 192)
    && !*(_DWORD *)(a1 + 72) )
  {
    LOBYTE(v7) = 1;
    v13 = Smb2PreGoAsync2Ex(a1, 0, v7, a4);
    v10 = a1;
    if ( v13 < 0 )
    {
      v8 = 1944;
      v9 = (unsigned int)v13;
      goto LABEL_9;
    }
    *(_DWORD *)(a1 + 72) = 1;
    *(_QWORD *)(a1 + 48) = Smb2ContinueDirectPlacementWrite;
    return Smb2GoAsyncForSyncCall(a1, v14, v15, v16);
  }
  v17 = *(_DWORD *)(v12 + 268);
  if ( v17 )
  {
    if ( (v17 & 1) != 0 )
    {
      v18 = *(_QWORD *)(v12 + 200);
      v19 = *(_QWORD *)(*(_QWORD *)(v12 + 32) + 48LL);
      if ( (*(_BYTE *)(v18 + 10) & 5) != 0 )
      {
        v20 = *(PVOID *)(v18 + 24);
      }
      else
      {
        v21 = MmMapLockedPagesSpecifyCache((PMDL)v18, 0, MmCached, 0, 0, 0x40000010u);
        v18 = *(_QWORD *)(v12 + 200);
        v20 = v21;
      }
      v22 = *(_BYTE *)(v12 + 280);
      if ( (v22 & 0x40) == 0 && v22 >= 0 )
        __int2c();
      if ( *(_QWORD *)v18 )
        __int2c();
      v23 = *(_QWORD *)(v12 + 224);
      v24 = SmbCryptoDecryptRdmaPayload(
              v19,
              v23 + 8,
              *(unsigned __int16 *)(v23 + 2),
              *(unsigned __int16 *)(v23 + 2) + v23 + 8,
              *(unsigned __int16 *)(v23 + 4),
              v20,
              *(_DWORD *)(a1 + 128));
      v25 = v24;
      if ( v24 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_dq(
            WPP_GLOBAL_Control->AttachedDevice,
            58,
            WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
            (unsigned int)v24,
            a1);
        }
        v8 = 1992;
LABEL_38:
        v9 = v25;
        goto LABEL_8;
      }
    }
    else if ( (v17 & 2) != 0 )
    {
      v26 = *(_QWORD *)(v12 + 200);
      v27 = *(_QWORD *)(v12 + 224);
      if ( (*(_BYTE *)(v26 + 10) & 5) != 0 )
        v28 = *(PVOID *)(v26 + 24);
      else
        v28 = MmMapLockedPagesSpecifyCache((PMDL)v26, 0, MmCached, 0, 0, 0x40000010u);
      v29 = Smb2ValidateIncomingSignatureForRdmaBuffer(a1, v27, v28, *(unsigned int *)(a1 + 128));
      v25 = v29;
      if ( v29 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_dq(
            WPP_GLOBAL_Control->AttachedDevice,
            59,
            WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
            (unsigned int)v29,
            a1);
        }
        v8 = 2014;
        goto LABEL_38;
      }
    }
    else
    {
      __int2c();
    }
  }
  v30 = *(_BYTE *)(v12 + 280);
  v31 = 0;
  if ( (v30 & 0x40) != 0 )
    v31 = (v30 & 8) == 0;
  if ( *(_DWORD *)(v12 + 272) == 1 && !v31 )
  {
    v32 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 96) + 8LL) + 80LL);
    if ( v32 )
    {
      if ( *(_DWORD *)v32 > 0x18u && *(_QWORD *)(v32 + 24) )
      {
        v33 = *(_QWORD *)(v12 + 200);
        if ( (*(_BYTE *)(v33 + 10) & 5) != 0 )
          v34 = *(PVOID *)(v33 + 24);
        else
          v34 = MmMapLockedPagesSpecifyCache((PMDL)v33, 0, MmCached, 0, 0, 0x40000010u);
        if ( !v34 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
          }
          v8 = 2055;
          v9 = 3221225626LL;
          goto LABEL_8;
        }
        LOBYTE(BugCheckOnFailure) = 1;
        LOBYTE(a2) = 2;
        SRV2_PERF_ENTER_EX(a1 + 584, a2, 2060, "Smb2ContinueDirectPlacementWrite", BugCheckOnFailure);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqq(
            WPP_GLOBAL_Control->AttachedDevice,
            61,
            WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
            a1,
            *(_QWORD *)(v12 + 72),
            *(_QWORD *)(v12 + 88));
        }
        v35 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, PVOID, __int64, _QWORD))(v32 + 24))(
                *(_QWORD *)(v12 + 88),
                v12 + 192,
                *(unsigned int *)(v12 + 248),
                0,
                *(_DWORD *)(v12 + 256),
                v34,
                *(_QWORD *)(a1 + 120) + 48LL,
                *(_QWORD *)(v12 + 96));
        LOBYTE(BugCheckOnFailurea) = 1;
        v5 = 0;
        v36 = a1 + 584;
        if ( v35 )
        {
          SRV2_PERF_ENTER_EX(v36, 0, 2077, "Smb2ContinueDirectPlacementWrite", BugCheckOnFailurea);
          *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
          return Smb2ContinueWrite(a1);
        }
        SRV2_PERF_ENTER_EX(v36, 0, 2084, "Smb2ContinueDirectPlacementWrite", BugCheckOnFailurea);
      }
    }
  }
  v37 = *(_BYTE *)(v12 + 280);
  v38 = (v37 & 0x10) != 0;
  if ( (v37 & 8) != 0 )
  {
    LOBYTE(v7) = 4;
    v38 = 1;
    v39 = Smb2BuildPipeReadOrWriteRequest(
            a1,
            *(_QWORD *)(v12 + 88),
            v7,
            *(_DWORD *)(*(_QWORD *)(v12 + 200) + 32LL) + *(_DWORD *)(*(_QWORD *)(v12 + 200) + 44LL),
            *(_DWORD *)(v12 + 248));
  }
  else
  {
    v40 = *(_DWORD *)(v12 + 272);
    if ( v40 != 1 )
    {
      v42 = 0;
      if ( v40 )
      {
        v43 = 0;
        do
        {
          v44 = *(_QWORD *)(v12 + 240);
          v45 = *(struct _MDL **)(v12 + 200);
          v46 = (char *)v45->StartVa + v45->ByteOffset + v43;
          Interval.QuadPart = 32LL * v5;
          v47 = *(_DWORD *)(Interval.QuadPart + v44 + 24);
          v48 = *(struct _MDL **)(Interval.QuadPart + v44 + 8);
          v58 = v44;
          IoBuildPartialMdl(v45, v48, v46, v47);
          LOBYTE(v56) = (*(_BYTE *)(v12 + 280) & 0x20) != 0;
          LOBYTE(v55) = (*(_BYTE *)(v12 + 280) & 0x40) != 0;
          LOBYTE(Priority) = 0;
          LOBYTE(BugCheckOnFailure) = 4;
          v42 = Smb2BuildReadOrWriteRequest(
                  a1,
                  *(_QWORD *)(Interval.QuadPart + v58),
                  *(_QWORD *)(v12 + 88),
                  *(_QWORD *)(v12 + 96),
                  BugCheckOnFailure,
                  Priority,
                  v46,
                  *(_DWORD *)(Interval.QuadPart + v58 + 24),
                  *(_QWORD *)(Interval.QuadPart + v58 + 8),
                  *(_QWORD *)(Interval.QuadPart + v58 + 16),
                  *(_DWORD *)(v12 + 256),
                  Smb2CompleteChainedWrite,
                  v55,
                  v56);
          if ( v42 < 0 )
            break;
          ++v5;
          v43 += *(_DWORD *)(Interval.QuadPart + v58 + 24);
        }
        while ( v5 < *(_DWORD *)(v12 + 272) );
      }
      *(_DWORD *)(v12 + 276) = *(_DWORD *)(v12 + 272);
      goto LABEL_85;
    }
    v41 = Srv2PostOnCompletionAndClearCancel;
    if ( Smb2EnableInlineSendIOCompletion )
      v41 = Srv2ClearCancelAndCallCallback;
    LOBYTE(Priority) = 0;
    LOBYTE(BugCheckOnFailure) = 4;
    v39 = Smb2BuildReadOrWriteRequest(
            a1,
            0,
            *(_QWORD *)(v12 + 88),
            *(_QWORD *)(v12 + 96),
            BugCheckOnFailure,
            Priority,
            *(_QWORD *)(*(_QWORD *)(v12 + 200) + 32LL) + *(unsigned int *)(*(_QWORD *)(v12 + 200) + 44LL),
            *(_DWORD *)(v12 + 248),
            *(_QWORD *)(v12 + 200),
            *(_QWORD *)(v12 + 192),
            *(_DWORD *)(v12 + 256),
            v41,
            (v37 & 0x40) != 0,
            (v37 & 0x20) != 0);
  }
  v42 = v39;
LABEL_85:
  if ( v42 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v8 = 2177;
    v9 = 3221225989LL;
    goto LABEL_8;
  }
  LOBYTE(a2) = v38;
  *(_QWORD *)(a1 + 48) = Smb2ContinueWrite;
  if ( (int)Srv2MarkWorkItemCancellable(a1, a2) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v8 = 2189;
    v9 = 3221225760LL;
    goto LABEL_8;
  }
  if ( v38 )
    Srv2ReferenceConnection(a1);
  LOBYTE(BugCheckOnFailure) = 1;
  LOBYTE(v49) = 3;
  result = SRV2_PERF_ENTER_EX(a1 + 584, v49, 2199, "Smb2ContinueDirectPlacementWrite", BugCheckOnFailure);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    result = WPP_SF_qqq(
               WPP_GLOBAL_Control->AttachedDevice,
               64,
               WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
               a1,
               *(_QWORD *)(v12 + 72),
               *(_QWORD *)(v12 + 88));
  }
  if ( *(_DWORD *)(v12 + 272) == 1 )
  {
    result = IofCallDriver(*(PDEVICE_OBJECT *)(v12 + 96), *(PIRP *)(a1 + 120));
  }
  else
  {
    v50 = *(_DWORD *)(v12 + 272);
    for ( i = 0; i < v50; ++i )
      result = IofCallDriver(*(PDEVICE_OBJECT *)(v12 + 96), *(PIRP *)(32LL * i + *(_QWORD *)(v12 + 240)));
  }
  if ( v38 )
  {
    Interval.QuadPart = -5000;
    KeDelayExecutionThread(0, 0, &Interval);
    if ( (unsigned int)Srv2MarkWorkItemPending(a1) )
      return Srv2DereferenceWorkItem(a1);
    else
      return Smb2GoAsync2(a1);
  }
  return result;
}

```

## disassembly

```asm
0x14007ea50  mov     [rsp+arg_10], rbx
0x14007ea55  push    rbp
0x14007ea56  push    rsi
0x14007ea57  push    rdi
0x14007ea58  push    r12
0x14007ea5a  push    r13
0x14007ea5c  push    r14
0x14007ea5e  push    r15
0x14007ea60  sub     rsp, 70h
0x14007ea64  mov     rdi, rcx
0x14007ea67  xor     r13d, r13d
0x14007ea6a  mov     rcx, [rcx+78h]
0x14007ea6e  mov     r8d, [rcx+30h]
0x14007ea72  test    r8d, r8d
0x14007ea75  jns     short loc_14007EAE1
0x14007ea77  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ea7e  lea     r15, WPP_GLOBAL_Control
0x14007ea85  cmp     rcx, r15
0x14007ea88  jz      short loc_14007EAB6
0x14007ea8a  bt      dword ptr [rcx+2Ch], 17h
0x14007ea8f  jnb     short loc_14007EAB6
0x14007ea91  lea     ebp, [r13+1]
0x14007ea95  cmp     [rcx+29h], bpl
0x14007ea99  jb      short loc_14007EAB6
0x14007ea9b  mov     rcx, [rcx+18h]
0x14007ea9f  lea     edx, [rbp+37h]
0x14007eaa2  mov     [rsp+0A8h+BugCheckOnFailure], r8d
0x14007eaa7  mov     r9, rdi
0x14007eaaa  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007eab1  call    WPP_SF_qD
0x14007eab6  mov     r9d, 777h
0x14007eabc  mov     rdx, [rdi+78h]
0x14007eac0  mov     edx, [rdx+30h]
0x14007eac3  mov     rcx, rdi
0x14007eac6  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14007eacd  call    _Smb2SetError
0x14007ead2  xor     edx, edx
0x14007ead4  mov     rcx, rdi
0x14007ead7  call    Srv2CompleteWorkItem
0x14007eadc  jmp     loc_14007F2CF
0x14007eae1  mov     rsi, [rdi+230h]
0x14007eae8  mov     eax, [rsi+0FCh]
0x14007eaee  cmp     [rcx+38h], rax
0x14007eaf2  jz      short loc_14007EB3C
0x14007eaf4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007eafb  lea     r15, WPP_GLOBAL_Control
0x14007eb02  cmp     rcx, r15
0x14007eb05  jz      short loc_14007EB34
0x14007eb07  bt      dword ptr [rcx+2Ch], 17h
0x14007eb0c  jnb     short loc_14007EB34
0x14007eb0e  mov     ebp, 1
0x14007eb13  cmp     [rcx+29h], bpl
0x14007eb17  jb      short loc_14007EB34
0x14007eb19  mov     rcx, [rcx+18h]
0x14007eb1d  lea     edx, [rbp+38h]
0x14007eb20  mov     [rsp+0A8h+BugCheckOnFailure], r8d
0x14007eb25  mov     r9, rdi
0x14007eb28  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007eb2f  call    WPP_SF_qD
0x14007eb34  mov     r9d, 782h
0x14007eb3a  jmp     short loc_14007EABC
0x14007eb3c  mov     rax, [rsi+38h]
0x14007eb40  cmp     [rax+58h], r13b
0x14007eb44  jz      short loc_14007EBA5
0x14007eb46  mov     rax, [rsi+58h]
0x14007eb4a  mov     rcx, [rax+18h]
0x14007eb4e  mov     rax, [rcx+28h]
0x14007eb52  add     rax, 2000000h
0x14007eb58  cmp     rax, [rsi+0C0h]
0x14007eb5f  jge     short loc_14007EBA5
0x14007eb61  cmp     [rdi+48h], r13d
0x14007eb65  jnz     short loc_14007EBA5
0x14007eb67  mov     ebp, 1
0x14007eb6c  xor     edx, edx
0x14007eb6e  mov     r8b, bpl
0x14007eb71  mov     rcx, rdi
0x14007eb74  call    Smb2PreGoAsync2Ex
0x14007eb79  mov     rcx, rdi
0x14007eb7c  test    eax, eax
0x14007eb7e  jns     short loc_14007EB8D
0x14007eb80  mov     r9d, 798h
0x14007eb86  mov     edx, eax
0x14007eb88  jmp     loc_14007EAC6
0x14007eb8d  lea     rax, Smb2ContinueDirectPlacementWrite
0x14007eb94  mov     [rdi+48h], ebp
0x14007eb97  mov     [rdi+30h], rax
0x14007eb9b  call    Smb2GoAsyncForSyncCall
0x14007eba0  jmp     loc_14007F2CF
0x14007eba5  mov     eax, [rsi+10Ch]
0x14007ebab  mov     ebp, 1
0x14007ebb0  mov     r12b, 5
0x14007ebb3  test    eax, eax
0x14007ebb5  jz      loc_14007ED5D
0x14007ebbb  test    bpl, al
0x14007ebbe  jz      loc_14007ECB5
0x14007ebc4  mov     rcx, [rsi+0C8h]; MemoryDescriptorList
0x14007ebcb  mov     rax, [rsi+20h]
0x14007ebcf  mov     rbx, [rax+30h]
0x14007ebd3  test    [rcx+0Ah], r12b
0x14007ebd7  jz      short loc_14007EBDF
0x14007ebd9  mov     r11, [rcx+18h]
0x14007ebdd  jmp     short loc_14007EC0A
0x14007ebdf  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x14007ebe7  xor     r9d, r9d; RequestedAddress
0x14007ebea  mov     r8d, ebp; CacheType
0x14007ebed  mov     [rsp+0A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14007ebf2  xor     edx, edx; AccessMode
0x14007ebf4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007ebfb  nop     dword ptr [rax+rax+00h]
0x14007ec00  mov     rcx, [rsi+0C8h]
0x14007ec07  mov     r11, rax
0x14007ec0a  mov     dl, [rsi+118h]
0x14007ec10  test    dl, 40h
0x14007ec13  jnz     short loc_14007EC1B
0x14007ec15  test    dl, dl
0x14007ec17  js      short loc_14007EC1B
0x14007ec19  int     2Ch; Windows NT - assertion failure
0x14007ec1b  cmp     [rcx], r13
0x14007ec1e  jz      short loc_14007EC22
0x14007ec20  int     2Ch; Windows NT - assertion failure
0x14007ec22  mov     rdx, [rsi+0E0h]
0x14007ec29  mov     rcx, rbx
0x14007ec2c  mov     eax, [rdi+80h]
0x14007ec32  mov     dword ptr [rsp+0A8h+var_78], eax
0x14007ec36  mov     qword ptr [rsp+0A8h+Priority], r11
0x14007ec3b  movzx   r8d, word ptr [rdx+2]
0x14007ec40  lea     r9, [rdx+8]
0x14007ec44  movzx   r10d, word ptr [rdx+4]
0x14007ec49  add     r9, r8
0x14007ec4c  add     rdx, 8
0x14007ec50  mov     [rsp+0A8h+BugCheckOnFailure], r10d
0x14007ec55  call    cs:__imp_SmbCryptoDecryptRdmaPayload
0x14007ec5c  nop     dword ptr [rax+rax+00h]
0x14007ec61  mov     ebx, eax
0x14007ec63  test    eax, eax
0x14007ec65  jns     loc_14007ED5D
0x14007ec6b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ec72  lea     r15, WPP_GLOBAL_Control
0x14007ec79  cmp     rcx, r15
0x14007ec7c  jz      short loc_14007ECA8
0x14007ec7e  bt      dword ptr [rcx+2Ch], 17h
0x14007ec83  jnb     short loc_14007ECA8
0x14007ec85  cmp     [rcx+29h], bpl
0x14007ec89  jb      short loc_14007ECA8
0x14007ec8b  mov     rcx, [rcx+18h]
0x14007ec8f  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007ec96  mov     edx, 3Ah ; ':'
0x14007ec9b  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x14007eca0  mov     r9d, eax
0x14007eca3  call    WPP_SF_dq
0x14007eca8  mov     r9d, 7C8h
0x14007ecae  mov     edx, ebx
0x14007ecb0  jmp     loc_14007EAC3
0x14007ecb5  test    al, 2
0x14007ecb7  jz      loc_14007ED5B
0x14007ecbd  mov     rcx, [rsi+0C8h]; MemoryDescriptorList
0x14007ecc4  mov     rbx, [rsi+0E0h]
0x14007eccb  test    [rcx+0Ah], r12b
0x14007eccf  jz      short loc_14007ECD7
0x14007ecd1  mov     rax, [rcx+18h]
0x14007ecd5  jmp     short loc_14007ECF8
0x14007ecd7  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x14007ecdf  xor     r9d, r9d; RequestedAddress
0x14007ece2  mov     r8d, ebp; CacheType
0x14007ece5  mov     [rsp+0A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14007ecea  xor     edx, edx; AccessMode
0x14007ecec  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007ecf3  nop     dword ptr [rax+rax+00h]
0x14007ecf8  mov     r9d, [rdi+80h]
0x14007ecff  mov     r8, rax
0x14007ed02  mov     rdx, rbx
0x14007ed05  mov     rcx, rdi
0x14007ed08  call    Smb2ValidateIncomingSignatureForRdmaBuffer
0x14007ed0d  mov     ebx, eax
0x14007ed0f  test    eax, eax
0x14007ed11  jns     short loc_14007ED5D
0x14007ed13  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ed1a  lea     r15, WPP_GLOBAL_Control
0x14007ed21  cmp     rcx, r15
0x14007ed24  jz      short loc_14007ED50
0x14007ed26  bt      dword ptr [rcx+2Ch], 17h
0x14007ed2b  jnb     short loc_14007ED50
0x14007ed2d  cmp     [rcx+29h], bpl
0x14007ed31  jb      short loc_14007ED50
0x14007ed33  mov     rcx, [rcx+18h]
0x14007ed37  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007ed3e  mov     edx, 3Bh ; ';'
0x14007ed43  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x14007ed48  mov     r9d, eax
0x14007ed4b  call    WPP_SF_dq
0x14007ed50  mov     r9d, 7DEh
0x14007ed56  jmp     loc_14007ECAE
0x14007ed5b  int     2Ch; Windows NT - assertion failure
0x14007ed5d  mov     cl, [rsi+118h]
0x14007ed63  movzx   eax, r13b
0x14007ed67  test    cl, 40h
0x14007ed6a  jz      short loc_14007ED72
0x14007ed6c  test    cl, 8
0x14007ed6f  cmovz   eax, ebp
0x14007ed72  lea     r15, WPP_GLOBAL_Control
0x14007ed79  mov     r14d, 800000h
0x14007ed7f  cmp     [rsi+110h], ebp
0x14007ed85  jnz     loc_14007EF2B
0x14007ed8b  test    al, al
0x14007ed8d  jnz     loc_14007EF2B
0x14007ed93  mov     rax, [rsi+60h]
0x14007ed97  mov     rcx, [rax+8]
0x14007ed9b  mov     rbx, [rcx+50h]
0x14007ed9f  test    rbx, rbx
0x14007eda2  jz      loc_14007EF2B
0x14007eda8  cmp     dword ptr [rbx], 18h
0x14007edab  jbe     loc_14007EF2B
0x14007edb1  cmp     [rbx+18h], r13
0x14007edb5  jz      loc_14007EF2B
0x14007edbb  mov     rcx, [rsi+0C8h]; MemoryDescriptorList
0x14007edc2  test    [rcx+0Ah], r12b
0x14007edc6  jz      short loc_14007EDCE
0x14007edc8  mov     r13, [rcx+18h]
0x14007edcc  jmp     short loc_14007EDF2
0x14007edce  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x14007edd6  xor     r9d, r9d; RequestedAddress
0x14007edd9  mov     r8d, ebp; CacheType
0x14007eddc  mov     [rsp+0A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14007ede1  xor     edx, edx; AccessMode
0x14007ede3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007edea  nop     dword ptr [rax+rax+00h]
0x14007edef  mov     r13, rax
0x14007edf2  test    r13, r13
0x14007edf5  jnz     short loc_14007EE3E
0x14007edf7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007edfe  lea     r15, WPP_GLOBAL_Control
0x14007ee05  cmp     rcx, r15
0x14007ee08  jz      short loc_14007EE2E
0x14007ee0a  bt      dword ptr [rcx+2Ch], 17h
0x14007ee0f  jnb     short loc_14007EE2E
0x14007ee11  cmp     [rcx+29h], bpl
0x14007ee15  jb      short loc_14007EE2E
0x14007ee17  mov     rcx, [rcx+18h]
0x14007ee1b  lea     edx, [r13+3Ch]
0x14007ee1f  mov     r9, rdi
0x14007ee22  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007ee29  call    WPP_SF_q
0x14007ee2e  mov     r9d, 807h
0x14007ee34  mov     edx, 0C000009Ah
0x14007ee39  jmp     loc_14007EAC3
0x14007ee3e  lea     r12, [rdi+248h]
0x14007ee45  mov     byte ptr [rsp+0A8h+BugCheckOnFailure], bpl
0x14007ee4a  mov     rcx, r12
0x14007ee4d  lea     r9, aSmb2continuedi; "Smb2ContinueDirectPlacementWrite"
0x14007ee54  mov     r8d, 80Ch
0x14007ee5a  mov     dl, 2
0x14007ee5c  call    SRV2_PERF_ENTER_EX
0x14007ee61  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ee68  cmp     rcx, r15
0x14007ee6b  jz      short loc_14007EEA3
0x14007ee6d  test    [rcx+2Ch], r14d
0x14007ee71  jz      short loc_14007EEA3
0x14007ee73  cmp     byte ptr [rcx+29h], 2
0x14007ee77  jb      short loc_14007EEA3
0x14007ee79  mov     rax, [rsi+58h]
0x14007ee7d  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007ee84  mov     rcx, [rcx+18h]
0x14007ee88  mov     edx, 3Dh ; '='
0x14007ee8d  mov     qword ptr [rsp+0A8h+Priority], rax
0x14007ee92  mov     r9, rdi
0x14007ee95  mov     rax, [rsi+48h]
0x14007ee99  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax
0x14007ee9e  call    WPP_SF_qqq
0x14007eea3  mov     rcx, [rsi+60h]
0x14007eea7  lea     rdx, [rsi+0C0h]
0x14007eeae  mov     r8, [rdi+78h]
0x14007eeb2  xor     r9d, r9d
0x14007eeb5  mov     rax, [rbx+18h]
0x14007eeb9  add     r8, 30h ; '0'
0x14007eebd  mov     [rsp+0A8h+var_70], rcx
0x14007eec2  mov     rcx, [rsi+58h]
0x14007eec6  mov     [rsp+0A8h+var_78], r8
0x14007eecb  mov     r8d, [rsi+100h]
0x14007eed2  mov     qword ptr [rsp+0A8h+Priority], r13
0x14007eed7  mov     [rsp+0A8h+BugCheckOnFailure], r8d
0x14007eedc  mov     r8d, [rsi+0F8h]
0x14007eee3  call    _guard_dispatch_icall
0x14007eee8  xor     edx, edx
0x14007eeea  mov     byte ptr [rsp+0A8h+BugCheckOnFailure], bpl
0x14007eeef  xor     r13d, r13d
0x14007eef2  lea     r9, aSmb2continuedi; "Smb2ContinueDirectPlacementWrite"
0x14007eef9  mov     rcx, r12
0x14007eefc  test    al, al
0x14007eefe  jz      short loc_14007EF20
0x14007ef00  mov     r8d, 81Dh
0x14007ef06  call    SRV2_PERF_ENTER_EX
0x14007ef0b  mov     rax, [rdi+78h]
0x14007ef0f  mov     rcx, rdi
0x14007ef12  mov     [rax+8], r13
0x14007ef16  call    Smb2ContinueWrite
0x14007ef1b  jmp     loc_14007F2CF
0x14007ef20  mov     r8d, 824h
0x14007ef26  call    SRV2_PERF_ENTER_EX
0x14007ef2b  mov     r9b, [rsi+118h]
0x14007ef32  mov     r12b, r9b
  ... truncated ...
```
