# Smb2ContinueDirectPlacementWrite

- ea: `0x14007eaa0`
- end: `0x14007f338`
- name: `Smb2ContinueDirectPlacementWrite`
- size: `2200`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x14006c1a0`

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
- `0x14007eaa0`
- `0x14007f340`
- `0x1400803b4`
- `0x140086160`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ec44`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ed3c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ee33`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ec44`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ed3c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ee33`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007f0b0`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007f0b0`
- `ntoskrnl!KeDelayExecutionThread` at `0x14007f2f8`
- `ntoskrnl!KeDelayExecutionThread` at `0x14007f2f8`
- `ntoskrnl!IofCallDriver` at `0x14007f297`
- `ntoskrnl!IofCallDriver` at `0x14007f2c8`
- `ntoskrnl!IofCallDriver` at `0x14007f297`
- `ntoskrnl!IofCallDriver` at `0x14007f2c8`
- `srvnet!SmbCryptoDecryptRdmaPayload` at `0x14007eca5`
- `srvnet!SmbCryptoDecryptRdmaPayload` at `0x14007eca5`

## string_xrefs

- `0x14007eb16`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14007ee9d`: `Smb2ContinueDirectPlacementWrite`
- `0x14007ef42`: `Smb2ContinueDirectPlacementWrite`
- `0x14007f231`: `Smb2ContinueDirectPlacementWrite`

## pseudocode

```c
NTSTATUS __fastcall Smb2ContinueDirectPlacementWrite(__int64 a1, __int64 a2)
{
  unsigned int v3; // r13d
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rcx
  NTSTATUS result; // eax
  __int64 v10; // rsi
  int v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rbx
  PVOID v15; // r11
  PVOID v16; // rax
  char v17; // dl
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rbx
  PVOID v23; // rax
  int v24; // eax
  char v25; // cl
  bool v26; // al
  __int64 v27; // rbx
  __int64 v28; // rcx
  PVOID v29; // r13
  char v30; // al
  __int64 v31; // rcx
  char v32; // r9
  bool v33; // r12
  int v34; // eax
  int v35; // eax
  __int64 (__fastcall *v36)(); // rdx
  int v37; // ecx
  int v38; // r14d
  __int64 v39; // r11
  struct _MDL *v40; // rcx
  char *v41; // rbx
  ULONG v42; // r9d
  struct _MDL *v43; // rdx
  __int64 v44; // rdx
  unsigned int v45; // r14d
  unsigned int i; // ebx
  int BugCheckOnFailure; // [rsp+20h] [rbp-88h]
  int BugCheckOnFailurea; // [rsp+20h] [rbp-88h]
  int Priority; // [rsp+28h] [rbp-80h]
  int v50; // [rsp+60h] [rbp-48h]
  int v51; // [rsp+68h] [rbp-40h]
  union _LARGE_INTEGER Interval; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v53; // [rsp+B8h] [rbp+10h]

  v3 = 0;
  v4 = *(_QWORD *)(a1 + 120);
  v5 = *(unsigned int *)(v4 + 48);
  if ( (int)v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u) )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 56, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1, v5);
    }
    v6 = 1911;
LABEL_7:
    v7 = *(unsigned int *)(*(_QWORD *)(a1 + 120) + 48LL);
LABEL_8:
    v8 = a1;
LABEL_9:
    Smb2SetError(v8, v7, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", v6);
    return Srv2CompleteWorkItem(a1, 0);
  }
  v10 = *(_QWORD *)(a1 + 560);
  if ( *(_QWORD *)(v4 + 56) != *(_DWORD *)(v10 + 252) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 57, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1, v5);
    }
    v6 = 1922;
    goto LABEL_7;
  }
  if ( *(_BYTE *)(*(_QWORD *)(v10 + 56) + 88LL)
    && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 88) + 24LL) + 40LL) + 0x2000000LL < *(_QWORD *)(v10 + 192)
    && !*(_DWORD *)(a1 + 72) )
  {
    LOBYTE(v5) = 1;
    v11 = Smb2PreGoAsync2Ex(a1, 0, v5);
    v8 = a1;
    if ( v11 < 0 )
    {
      v6 = 1944;
      v7 = (unsigned int)v11;
      goto LABEL_9;
    }
    *(_DWORD *)(a1 + 72) = 1;
    *(_QWORD *)(a1 + 48) = Smb2ContinueDirectPlacementWrite;
    return Smb2GoAsyncForSyncCall(a1);
  }
  v12 = *(_DWORD *)(v10 + 268);
  if ( v12 )
  {
    if ( (v12 & 1) != 0 )
    {
      v13 = *(_QWORD *)(v10 + 200);
      v14 = *(_QWORD *)(*(_QWORD *)(v10 + 32) + 48LL);
      if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
      {
        v15 = *(PVOID *)(v13 + 24);
      }
      else
      {
        v16 = MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x40000010u);
        v13 = *(_QWORD *)(v10 + 200);
        v15 = v16;
      }
      v17 = *(_BYTE *)(v10 + 280);
      if ( (v17 & 0x40) == 0 && v17 >= 0 )
        __int2c();
      if ( *(_QWORD *)v13 )
        __int2c();
      v18 = *(_QWORD *)(v10 + 224);
      v19 = SmbCryptoDecryptRdmaPayload(
              v14,
              v18 + 8,
              *(unsigned __int16 *)(v18 + 2),
              *(unsigned __int16 *)(v18 + 2) + v18 + 8,
              *(unsigned __int16 *)(v18 + 4),
              v15,
              *(_DWORD *)(a1 + 128));
      v20 = v19;
      if ( v19 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_dq(
            WPP_GLOBAL_Control->AttachedDevice,
            58,
            &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
            (unsigned int)v19,
            a1);
        }
        v6 = 1992;
LABEL_38:
        v7 = v20;
        goto LABEL_8;
      }
    }
    else if ( (v12 & 2) != 0 )
    {
      v21 = *(_QWORD *)(v10 + 200);
      v22 = *(_QWORD *)(v10 + 224);
      if ( (*(_BYTE *)(v21 + 10) & 5) != 0 )
        v23 = *(PVOID *)(v21 + 24);
      else
        v23 = MmMapLockedPagesSpecifyCache((PMDL)v21, 0, MmCached, 0, 0, 0x40000010u);
      v24 = Smb2ValidateIncomingSignatureForRdmaBuffer(a1, v22, v23, *(unsigned int *)(a1 + 128));
      v20 = v24;
      if ( v24 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_dq(
            WPP_GLOBAL_Control->AttachedDevice,
            59,
            &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
            (unsigned int)v24,
            a1);
        }
        v6 = 2014;
        goto LABEL_38;
      }
    }
    else
    {
      __int2c();
    }
  }
  v25 = *(_BYTE *)(v10 + 280);
  v26 = 0;
  if ( (v25 & 0x40) != 0 )
    v26 = (v25 & 8) == 0;
  if ( *(_DWORD *)(v10 + 272) == 1 && !v26 )
  {
    v27 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 96) + 8LL) + 80LL);
    if ( v27 )
    {
      if ( *(_DWORD *)v27 > 0x18u && *(_QWORD *)(v27 + 24) )
      {
        v28 = *(_QWORD *)(v10 + 200);
        if ( (*(_BYTE *)(v28 + 10) & 5) != 0 )
          v29 = *(PVOID *)(v28 + 24);
        else
          v29 = MmMapLockedPagesSpecifyCache((PMDL)v28, 0, MmCached, 0, 0, 0x40000010u);
        if ( !v29 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 60, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
          }
          v6 = 2055;
          v7 = 3221225626LL;
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
            &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
            a1,
            *(_QWORD *)(v10 + 72),
            *(_QWORD *)(v10 + 88));
        }
        v30 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, PVOID, __int64, _QWORD))(v27 + 24))(
                *(_QWORD *)(v10 + 88),
                v10 + 192,
                *(unsigned int *)(v10 + 248),
                0,
                *(_DWORD *)(v10 + 256),
                v29,
                *(_QWORD *)(a1 + 120) + 48LL,
                *(_QWORD *)(v10 + 96));
        LOBYTE(BugCheckOnFailurea) = 1;
        v3 = 0;
        v31 = a1 + 584;
        if ( v30 )
        {
          SRV2_PERF_ENTER_EX(v31, 0, 2077, "Smb2ContinueDirectPlacementWrite", BugCheckOnFailurea);
          *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
          return Smb2ContinueWrite(a1);
        }
        SRV2_PERF_ENTER_EX(v31, 0, 2084, "Smb2ContinueDirectPlacementWrite", BugCheckOnFailurea);
      }
    }
  }
  v32 = *(_BYTE *)(v10 + 280);
  v33 = (v32 & 0x10) != 0;
  if ( (v32 & 8) != 0 )
  {
    LOBYTE(v5) = 4;
    v33 = 1;
    v34 = Smb2BuildPipeReadOrWriteRequest(
            a1,
            *(_QWORD *)(v10 + 88),
            v5,
            *(_DWORD *)(*(_QWORD *)(v10 + 200) + 32LL) + *(_DWORD *)(*(_QWORD *)(v10 + 200) + 44LL),
            *(_DWORD *)(v10 + 248));
  }
  else
  {
    v35 = *(_DWORD *)(v10 + 272);
    if ( v35 != 1 )
    {
      v37 = 0;
      if ( v35 )
      {
        v38 = 0;
        do
        {
          v39 = *(_QWORD *)(v10 + 240);
          v40 = *(struct _MDL **)(v10 + 200);
          v41 = (char *)v40->StartVa + v40->ByteOffset + v38;
          Interval.QuadPart = 32LL * v3;
          v42 = *(_DWORD *)(Interval.QuadPart + v39 + 24);
          v43 = *(struct _MDL **)(Interval.QuadPart + v39 + 8);
          v53 = v39;
          IoBuildPartialMdl(v40, v43, v41, v42);
          LOBYTE(v51) = (*(_BYTE *)(v10 + 280) & 0x20) != 0;
          LOBYTE(v50) = (*(_BYTE *)(v10 + 280) & 0x40) != 0;
          LOBYTE(Priority) = 0;
          LOBYTE(BugCheckOnFailure) = 4;
          v37 = Smb2BuildReadOrWriteRequest(
                  a1,
                  *(_QWORD *)(Interval.QuadPart + v53),
                  *(_QWORD *)(v10 + 88),
                  *(_QWORD *)(v10 + 96),
                  BugCheckOnFailure,
                  Priority,
                  v41,
                  *(_DWORD *)(Interval.QuadPart + v53 + 24),
                  *(_QWORD *)(Interval.QuadPart + v53 + 8),
                  *(_QWORD *)(Interval.QuadPart + v53 + 16),
                  *(_DWORD *)(v10 + 256),
                  Smb2CompleteChainedWrite,
                  v50,
                  v51);
          if ( v37 < 0 )
            break;
          ++v3;
          v38 += *(_DWORD *)(Interval.QuadPart + v53 + 24);
        }
        while ( v3 < *(_DWORD *)(v10 + 272) );
      }
      *(_DWORD *)(v10 + 276) = *(_DWORD *)(v10 + 272);
      goto LABEL_85;
    }
    v36 = Srv2PostOnCompletionAndClearCancel;
    if ( Smb2EnableInlineSendIOCompletion )
      v36 = Srv2ClearCancelAndCallCallback;
    LOBYTE(Priority) = 0;
    LOBYTE(BugCheckOnFailure) = 4;
    v34 = Smb2BuildReadOrWriteRequest(
            a1,
            0,
            *(_QWORD *)(v10 + 88),
            *(_QWORD *)(v10 + 96),
            BugCheckOnFailure,
            Priority,
            *(_QWORD *)(*(_QWORD *)(v10 + 200) + 32LL) + *(unsigned int *)(*(_QWORD *)(v10 + 200) + 44LL),
            *(_DWORD *)(v10 + 248),
            *(_QWORD *)(v10 + 200),
            *(_QWORD *)(v10 + 192),
            *(_DWORD *)(v10 + 256),
            v36,
            (v32 & 0x40) != 0,
            (v32 & 0x20) != 0);
  }
  v37 = v34;
LABEL_85:
  if ( v37 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 62, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v6 = 2177;
    v7 = 3221225989LL;
    goto LABEL_8;
  }
  LOBYTE(a2) = v33;
  *(_QWORD *)(a1 + 48) = Smb2ContinueWrite;
  if ( (int)Srv2MarkWorkItemCancellable(a1, a2) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 63, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v6 = 2189;
    v7 = 3221225760LL;
    goto LABEL_8;
  }
  if ( v33 )
    Srv2ReferenceConnection(a1);
  LOBYTE(BugCheckOnFailure) = 1;
  LOBYTE(v44) = 3;
  result = SRV2_PERF_ENTER_EX(a1 + 584, v44, 2199, "Smb2ContinueDirectPlacementWrite", BugCheckOnFailure);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    result = WPP_SF_qqq(
               WPP_GLOBAL_Control->AttachedDevice,
               64,
               &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
               a1,
               *(_QWORD *)(v10 + 72),
               *(_QWORD *)(v10 + 88));
  }
  if ( *(_DWORD *)(v10 + 272) == 1 )
  {
    result = IofCallDriver(*(PDEVICE_OBJECT *)(v10 + 96), *(PIRP *)(a1 + 120));
  }
  else
  {
    v45 = *(_DWORD *)(v10 + 272);
    for ( i = 0; i < v45; ++i )
      result = IofCallDriver(*(PDEVICE_OBJECT *)(v10 + 96), *(PIRP *)(32LL * i + *(_QWORD *)(v10 + 240)));
  }
  if ( v33 )
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
0x14007eaa0  mov     [rsp+arg_10], rbx
0x14007eaa5  push    rbp
0x14007eaa6  push    rsi
0x14007eaa7  push    rdi
0x14007eaa8  push    r12
0x14007eaaa  push    r13
0x14007eaac  push    r14
0x14007eaae  push    r15
0x14007eab0  sub     rsp, 70h
0x14007eab4  mov     rdi, rcx
0x14007eab7  xor     r13d, r13d
0x14007eaba  mov     rcx, [rcx+78h]
0x14007eabe  mov     r8d, [rcx+30h]
0x14007eac2  test    r8d, r8d
0x14007eac5  jns     short loc_14007EB31
0x14007eac7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007eace  lea     r15, WPP_GLOBAL_Control
0x14007ead5  cmp     rcx, r15
0x14007ead8  jz      short loc_14007EB06
0x14007eada  bt      dword ptr [rcx+2Ch], 17h
0x14007eadf  jnb     short loc_14007EB06
0x14007eae1  lea     ebp, [r13+1]
0x14007eae5  cmp     [rcx+29h], bpl
0x14007eae9  jb      short loc_14007EB06
0x14007eaeb  mov     rcx, [rcx+18h]
0x14007eaef  lea     edx, [rbp+37h]
0x14007eaf2  mov     [rsp+0A8h+BugCheckOnFailure], r8d
0x14007eaf7  mov     r9, rdi
0x14007eafa  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007eb01  call    WPP_SF_qD
0x14007eb06  mov     r9d, 777h
0x14007eb0c  mov     rdx, [rdi+78h]
0x14007eb10  mov     edx, [rdx+30h]
0x14007eb13  mov     rcx, rdi
0x14007eb16  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14007eb1d  call    _Smb2SetError
0x14007eb22  xor     edx, edx
0x14007eb24  mov     rcx, rdi
0x14007eb27  call    Srv2CompleteWorkItem
0x14007eb2c  jmp     loc_14007F31F
0x14007eb31  mov     rsi, [rdi+230h]
0x14007eb38  mov     eax, [rsi+0FCh]
0x14007eb3e  cmp     [rcx+38h], rax
0x14007eb42  jz      short loc_14007EB8C
0x14007eb44  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007eb4b  lea     r15, WPP_GLOBAL_Control
0x14007eb52  cmp     rcx, r15
0x14007eb55  jz      short loc_14007EB84
0x14007eb57  bt      dword ptr [rcx+2Ch], 17h
0x14007eb5c  jnb     short loc_14007EB84
0x14007eb5e  mov     ebp, 1
0x14007eb63  cmp     [rcx+29h], bpl
0x14007eb67  jb      short loc_14007EB84
0x14007eb69  mov     rcx, [rcx+18h]
0x14007eb6d  lea     edx, [rbp+38h]
0x14007eb70  mov     [rsp+0A8h+BugCheckOnFailure], r8d
0x14007eb75  mov     r9, rdi
0x14007eb78  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007eb7f  call    WPP_SF_qD
0x14007eb84  mov     r9d, 782h
0x14007eb8a  jmp     short loc_14007EB0C
0x14007eb8c  mov     rax, [rsi+38h]
0x14007eb90  cmp     [rax+58h], r13b
0x14007eb94  jz      short loc_14007EBF5
0x14007eb96  mov     rax, [rsi+58h]
0x14007eb9a  mov     rcx, [rax+18h]
0x14007eb9e  mov     rax, [rcx+28h]
0x14007eba2  add     rax, 2000000h
0x14007eba8  cmp     rax, [rsi+0C0h]
0x14007ebaf  jge     short loc_14007EBF5
0x14007ebb1  cmp     [rdi+48h], r13d
0x14007ebb5  jnz     short loc_14007EBF5
0x14007ebb7  mov     ebp, 1
0x14007ebbc  xor     edx, edx
0x14007ebbe  mov     r8b, bpl
0x14007ebc1  mov     rcx, rdi
0x14007ebc4  call    Smb2PreGoAsync2Ex
0x14007ebc9  mov     rcx, rdi
0x14007ebcc  test    eax, eax
0x14007ebce  jns     short loc_14007EBDD
0x14007ebd0  mov     r9d, 798h
0x14007ebd6  mov     edx, eax
0x14007ebd8  jmp     loc_14007EB16
0x14007ebdd  lea     rax, Smb2ContinueDirectPlacementWrite
0x14007ebe4  mov     [rdi+48h], ebp
0x14007ebe7  mov     [rdi+30h], rax
0x14007ebeb  call    Smb2GoAsyncForSyncCall
0x14007ebf0  jmp     loc_14007F31F
0x14007ebf5  mov     eax, [rsi+10Ch]
0x14007ebfb  mov     ebp, 1
0x14007ec00  mov     r12b, 5
0x14007ec03  test    eax, eax
0x14007ec05  jz      loc_14007EDAD
0x14007ec0b  test    bpl, al
0x14007ec0e  jz      loc_14007ED05
0x14007ec14  mov     rcx, [rsi+0C8h]; MemoryDescriptorList
0x14007ec1b  mov     rax, [rsi+20h]
0x14007ec1f  mov     rbx, [rax+30h]
0x14007ec23  test    [rcx+0Ah], r12b
0x14007ec27  jz      short loc_14007EC2F
0x14007ec29  mov     r11, [rcx+18h]
0x14007ec2d  jmp     short loc_14007EC5A
0x14007ec2f  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x14007ec37  xor     r9d, r9d; RequestedAddress
0x14007ec3a  mov     r8d, ebp; CacheType
0x14007ec3d  mov     [rsp+0A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14007ec42  xor     edx, edx; AccessMode
0x14007ec44  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007ec4b  nop     dword ptr [rax+rax+00h]
0x14007ec50  mov     rcx, [rsi+0C8h]
0x14007ec57  mov     r11, rax
0x14007ec5a  mov     dl, [rsi+118h]
0x14007ec60  test    dl, 40h
0x14007ec63  jnz     short loc_14007EC6B
0x14007ec65  test    dl, dl
0x14007ec67  js      short loc_14007EC6B
0x14007ec69  int     2Ch; Windows NT - assertion failure
0x14007ec6b  cmp     [rcx], r13
0x14007ec6e  jz      short loc_14007EC72
0x14007ec70  int     2Ch; Windows NT - assertion failure
0x14007ec72  mov     rdx, [rsi+0E0h]
0x14007ec79  mov     rcx, rbx
0x14007ec7c  mov     eax, [rdi+80h]
0x14007ec82  mov     dword ptr [rsp+0A8h+var_78], eax
0x14007ec86  mov     qword ptr [rsp+0A8h+Priority], r11
0x14007ec8b  movzx   r8d, word ptr [rdx+2]
0x14007ec90  lea     r9, [rdx+8]
0x14007ec94  movzx   r10d, word ptr [rdx+4]
0x14007ec99  add     r9, r8
0x14007ec9c  add     rdx, 8
0x14007eca0  mov     [rsp+0A8h+BugCheckOnFailure], r10d
0x14007eca5  call    cs:__imp_SmbCryptoDecryptRdmaPayload
0x14007ecac  nop     dword ptr [rax+rax+00h]
0x14007ecb1  mov     ebx, eax
0x14007ecb3  test    eax, eax
0x14007ecb5  jns     loc_14007EDAD
0x14007ecbb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ecc2  lea     r15, WPP_GLOBAL_Control
0x14007ecc9  cmp     rcx, r15
0x14007eccc  jz      short loc_14007ECF8
0x14007ecce  bt      dword ptr [rcx+2Ch], 17h
0x14007ecd3  jnb     short loc_14007ECF8
0x14007ecd5  cmp     [rcx+29h], bpl
0x14007ecd9  jb      short loc_14007ECF8
0x14007ecdb  mov     rcx, [rcx+18h]
0x14007ecdf  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007ece6  mov     edx, 3Ah ; ':'
0x14007eceb  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x14007ecf0  mov     r9d, eax
0x14007ecf3  call    WPP_SF_dq
0x14007ecf8  mov     r9d, 7C8h
0x14007ecfe  mov     edx, ebx
0x14007ed00  jmp     loc_14007EB13
0x14007ed05  test    al, 2
0x14007ed07  jz      loc_14007EDAB
0x14007ed0d  mov     rcx, [rsi+0C8h]; MemoryDescriptorList
0x14007ed14  mov     rbx, [rsi+0E0h]
0x14007ed1b  test    [rcx+0Ah], r12b
0x14007ed1f  jz      short loc_14007ED27
0x14007ed21  mov     rax, [rcx+18h]
0x14007ed25  jmp     short loc_14007ED48
0x14007ed27  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x14007ed2f  xor     r9d, r9d; RequestedAddress
0x14007ed32  mov     r8d, ebp; CacheType
0x14007ed35  mov     [rsp+0A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14007ed3a  xor     edx, edx; AccessMode
0x14007ed3c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007ed43  nop     dword ptr [rax+rax+00h]
0x14007ed48  mov     r9d, [rdi+80h]
0x14007ed4f  mov     r8, rax
0x14007ed52  mov     rdx, rbx
0x14007ed55  mov     rcx, rdi
0x14007ed58  call    Smb2ValidateIncomingSignatureForRdmaBuffer
0x14007ed5d  mov     ebx, eax
0x14007ed5f  test    eax, eax
0x14007ed61  jns     short loc_14007EDAD
0x14007ed63  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ed6a  lea     r15, WPP_GLOBAL_Control
0x14007ed71  cmp     rcx, r15
0x14007ed74  jz      short loc_14007EDA0
0x14007ed76  bt      dword ptr [rcx+2Ch], 17h
0x14007ed7b  jnb     short loc_14007EDA0
0x14007ed7d  cmp     [rcx+29h], bpl
0x14007ed81  jb      short loc_14007EDA0
0x14007ed83  mov     rcx, [rcx+18h]
0x14007ed87  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007ed8e  mov     edx, 3Bh ; ';'
0x14007ed93  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x14007ed98  mov     r9d, eax
0x14007ed9b  call    WPP_SF_dq
0x14007eda0  mov     r9d, 7DEh
0x14007eda6  jmp     loc_14007ECFE
0x14007edab  int     2Ch; Windows NT - assertion failure
0x14007edad  mov     cl, [rsi+118h]
0x14007edb3  movzx   eax, r13b
0x14007edb7  test    cl, 40h
0x14007edba  jz      short loc_14007EDC2
0x14007edbc  test    cl, 8
0x14007edbf  cmovz   eax, ebp
0x14007edc2  lea     r15, WPP_GLOBAL_Control
0x14007edc9  mov     r14d, 800000h
0x14007edcf  cmp     [rsi+110h], ebp
0x14007edd5  jnz     loc_14007EF7B
0x14007eddb  test    al, al
0x14007eddd  jnz     loc_14007EF7B
0x14007ede3  mov     rax, [rsi+60h]
0x14007ede7  mov     rcx, [rax+8]
0x14007edeb  mov     rbx, [rcx+50h]
0x14007edef  test    rbx, rbx
0x14007edf2  jz      loc_14007EF7B
0x14007edf8  cmp     dword ptr [rbx], 18h
0x14007edfb  jbe     loc_14007EF7B
0x14007ee01  cmp     [rbx+18h], r13
0x14007ee05  jz      loc_14007EF7B
0x14007ee0b  mov     rcx, [rsi+0C8h]; MemoryDescriptorList
0x14007ee12  test    [rcx+0Ah], r12b
0x14007ee16  jz      short loc_14007EE1E
0x14007ee18  mov     r13, [rcx+18h]
0x14007ee1c  jmp     short loc_14007EE42
0x14007ee1e  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x14007ee26  xor     r9d, r9d; RequestedAddress
0x14007ee29  mov     r8d, ebp; CacheType
0x14007ee2c  mov     [rsp+0A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14007ee31  xor     edx, edx; AccessMode
0x14007ee33  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007ee3a  nop     dword ptr [rax+rax+00h]
0x14007ee3f  mov     r13, rax
0x14007ee42  test    r13, r13
0x14007ee45  jnz     short loc_14007EE8E
0x14007ee47  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ee4e  lea     r15, WPP_GLOBAL_Control
0x14007ee55  cmp     rcx, r15
0x14007ee58  jz      short loc_14007EE7E
0x14007ee5a  bt      dword ptr [rcx+2Ch], 17h
0x14007ee5f  jnb     short loc_14007EE7E
0x14007ee61  cmp     [rcx+29h], bpl
0x14007ee65  jb      short loc_14007EE7E
0x14007ee67  mov     rcx, [rcx+18h]
0x14007ee6b  lea     edx, [r13+3Ch]
0x14007ee6f  mov     r9, rdi
0x14007ee72  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007ee79  call    WPP_SF_q
0x14007ee7e  mov     r9d, 807h
0x14007ee84  mov     edx, 0C000009Ah
0x14007ee89  jmp     loc_14007EB13
0x14007ee8e  lea     r12, [rdi+248h]
0x14007ee95  mov     byte ptr [rsp+0A8h+BugCheckOnFailure], bpl
0x14007ee9a  mov     rcx, r12
0x14007ee9d  lea     r9, aSmb2continuedi; "Smb2ContinueDirectPlacementWrite"
0x14007eea4  mov     r8d, 80Ch
0x14007eeaa  mov     dl, 2
0x14007eeac  call    SRV2_PERF_ENTER_EX
0x14007eeb1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007eeb8  cmp     rcx, r15
0x14007eebb  jz      short loc_14007EEF3
0x14007eebd  test    [rcx+2Ch], r14d
0x14007eec1  jz      short loc_14007EEF3
0x14007eec3  cmp     byte ptr [rcx+29h], 2
0x14007eec7  jb      short loc_14007EEF3
0x14007eec9  mov     rax, [rsi+58h]
0x14007eecd  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007eed4  mov     rcx, [rcx+18h]
0x14007eed8  mov     edx, 3Dh ; '='
0x14007eedd  mov     qword ptr [rsp+0A8h+Priority], rax
0x14007eee2  mov     r9, rdi
0x14007eee5  mov     rax, [rsi+48h]
0x14007eee9  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax
0x14007eeee  call    WPP_SF_qqq
0x14007eef3  mov     rcx, [rsi+60h]
0x14007eef7  lea     rdx, [rsi+0C0h]
0x14007eefe  mov     r8, [rdi+78h]
0x14007ef02  xor     r9d, r9d
0x14007ef05  mov     rax, [rbx+18h]
0x14007ef09  add     r8, 30h ; '0'
0x14007ef0d  mov     [rsp+0A8h+var_70], rcx
0x14007ef12  mov     rcx, [rsi+58h]
0x14007ef16  mov     [rsp+0A8h+var_78], r8
0x14007ef1b  mov     r8d, [rsi+100h]
0x14007ef22  mov     qword ptr [rsp+0A8h+Priority], r13
0x14007ef27  mov     [rsp+0A8h+BugCheckOnFailure], r8d
0x14007ef2c  mov     r8d, [rsi+0F8h]
0x14007ef33  call    _guard_dispatch_icall
0x14007ef38  xor     edx, edx
0x14007ef3a  mov     byte ptr [rsp+0A8h+BugCheckOnFailure], bpl
0x14007ef3f  xor     r13d, r13d
0x14007ef42  lea     r9, aSmb2continuedi; "Smb2ContinueDirectPlacementWrite"
0x14007ef49  mov     rcx, r12
0x14007ef4c  test    al, al
0x14007ef4e  jz      short loc_14007EF70
0x14007ef50  mov     r8d, 81Dh
0x14007ef56  call    SRV2_PERF_ENTER_EX
0x14007ef5b  mov     rax, [rdi+78h]
0x14007ef5f  mov     rcx, rdi
0x14007ef62  mov     [rax+8], r13
0x14007ef66  call    Smb2ContinueWrite
0x14007ef6b  jmp     loc_14007F31F
0x14007ef70  mov     r8d, 824h
0x14007ef76  call    SRV2_PERF_ENTER_EX
0x14007ef7b  mov     r9b, [rsi+118h]
0x14007ef82  mov     r12b, r9b
  ... truncated ...
```
