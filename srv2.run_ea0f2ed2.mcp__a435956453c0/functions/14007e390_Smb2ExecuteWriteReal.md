# Smb2ExecuteWriteReal

- ea: `0x14007e390`
- end: `0x14007ea99`
- name: `Smb2ExecuteWriteReal`
- size: `1801`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007e2d0`

## callees

- `0x140005070`
- `0x140006ad0`
- `0x140007090`
- `0x140007400`
- `0x140008190`
- `0x1400125d0`
- `0x140013810`
- `0x140015000`
- `0x1400152a0`
- `0x140017730`
- `0x1400186f0`
- `0x14001f050`
- `0x1400222ec`
- `0x140022958`
- `0x1400384d0`
- `0x140038680`
- `0x14006c548`
- `0x140077650`
- `0x14007e390`
- `0x14007f340`
- `0x1400803b4`
- `0x140086160`
- `0x1400918d8`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14007e788`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007e788`
- `ntoskrnl!KeDelayExecutionThread` at `0x14007e9f2`
- `ntoskrnl!KeDelayExecutionThread` at `0x14007e9f2`
- `ntoskrnl!ExAllocatePool2` at `0x14007e5f6`
- `ntoskrnl!ExAllocatePool2` at `0x14007e5f6`
- `ntoskrnl!IofCallDriver` at `0x14007e9c6`
- `ntoskrnl!IofCallDriver` at `0x14007e9c6`
- `ntoskrnl!IoFreeIrp` at `0x14007e455`
- `ntoskrnl!IoFreeIrp` at `0x14007e455`
- `ntoskrnl!IoAllocateIrpEx` at `0x14007e439`
- `ntoskrnl!IoAllocateIrpEx` at `0x14007e439`
- `srvnet!SrvLibAuditForceAccess` at `0x14007e3dd`
- `srvnet!SrvLibAuditForceAccess` at `0x14007e3dd`

## string_xrefs

- `0x14007ea6a`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14007e6d2`: `Smb2ExecuteWriteReal`
- `0x14007e732`: `Smb2ExecuteWriteReal`
- `0x14007e9aa`: `Smb2ExecuteWriteReal`

## pseudocode

```c
NTSTATUS __fastcall Smb2ExecuteWriteReal(__int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rbp
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rax
  char v7; // cl
  __int64 v8; // rdx
  __int64 Irp; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  char v14; // al
  NTSTATUS result; // eax
  char v16; // al
  void *v17; // rbp
  unsigned int v18; // edx
  unsigned int v19; // eax
  __int64 Pool2; // rax
  void *v21; // rbx
  __int64 v22; // rbx
  char v23; // al
  __int64 v24; // rcx
  int v25; // r8d
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 (__fastcall *v29)(); // rdx
  int v30; // eax
  __int64 v31; // rdx
  char v32; // al
  char v33; // bl
  int v34; // [rsp+20h] [rbp-68h]
  int v35; // [rsp+20h] [rbp-68h]
  int v36; // [rsp+20h] [rbp-68h]
  int v37; // [rsp+28h] [rbp-60h]
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 304) + 24LL);
  if ( !*(_BYTE *)(*(_QWORD *)(v2 + 72) + 235LL) && (int)Smb2ImpersonateWorkItem(*(_QWORD *)(a1 + 560)) >= 0 )
  {
    if ( (int)SrvLibAuditForceAccess(*(_QWORD *)(*(_QWORD *)(v2 + 80) + 88LL), 2) >= 0 )
      *(_BYTE *)(*(_QWORD *)(v2 + 72) + 235LL) = 1;
    Smb2Revert();
  }
  Smb2DereferenceHandle(*(PVOID *)(v2 + 80));
  v6 = *(_QWORD *)(v2 + 96);
  *(_QWORD *)(v2 + 80) = 0;
  v7 = *(_BYTE *)(v6 + 76);
  if ( *(char *)(*(_QWORD *)(a1 + 120) + 66LL) < v7 || (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    v8 = 15;
    if ( v7 > 15 )
      v8 = *(unsigned __int8 *)(v6 + 76);
    Irp = IoAllocateIrpEx(-1, v8, 0);
    if ( !Irp )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          70,
          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
          a1,
          -1073741670);
      }
      v12 = 2635;
      v13 = 3221225626LL;
      goto LABEL_92;
    }
    IoFreeIrp(*(PIRP *)(a1 + 120));
    *(_QWORD *)(a1 + 120) = Irp;
  }
  if ( (*(_BYTE *)(v2 + 280) & 0x18) != 0 )
  {
    LOBYTE(v5) = 1;
    v10 = Smb2PreGoAsync2Ex(a1, 0, v5);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 71, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1, v10);
      }
      v12 = 2653;
      v13 = v11;
      goto LABEL_92;
    }
  }
  if ( *(_QWORD *)(v2 + 216) )
  {
    v14 = *(_BYTE *)(v2 + 280);
    if ( (v14 & 0x40) != 0 || v14 < 0 )
      return Smb2ExecuteDirectPlacementWrite(a1);
    else
      return Smb2ExecuteDirectPlacementMdlWrite(a1);
  }
  if ( *(_DWORD *)(a1 + 404) < *(_DWORD *)(v3 + 68) + (unsigned int)*(unsigned __int16 *)(v3 + 66) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 72, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v12 = 2706;
LABEL_30:
    v13 = 3221225485LL;
LABEL_92:
    Smb2SetError(a1, v13, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", v12);
    return Srv2CompleteWorkItem(a1, 0);
  }
  v16 = *(_BYTE *)(v2 + 280);
  v17 = (void *)(*(unsigned __int16 *)(v3 + 66) + v3);
  if ( (v16 & 0x40) == 0 || (v16 & 8) != 0 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(v2 + 72) + 239LL) )
    {
      v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 96) + 8LL) + 80LL);
      if ( v22 )
      {
        if ( *(_DWORD *)v22 > 0x18u && *(_QWORD *)(v22 + 24) )
        {
          LOBYTE(v4) = 2;
          SRV2_PERF_ENTER_EX(a1 + 584, v4, 2771, "Smb2ExecuteWriteReal", 1);
          v23 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, void *, __int64, _QWORD))(v22 + 24))(
                  *(_QWORD *)(v2 + 88),
                  v2 + 192,
                  *(unsigned int *)(v2 + 248),
                  0,
                  *(_DWORD *)(v2 + 256),
                  v17,
                  *(_QWORD *)(a1 + 120) + 48LL,
                  *(_QWORD *)(v2 + 96));
          LOBYTE(v35) = 1;
          v24 = a1 + 584;
          if ( v23 )
          {
            SRV2_PERF_ENTER_EX(v24, 0, 2783, "Smb2ExecuteWriteReal", v35);
            *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
            return Smb2ContinueWrite(a1);
          }
          SRV2_PERF_ENTER_EX(v24, 0, 2789, "Smb2ExecuteWriteReal", v35);
        }
      }
    }
  }
  else
  {
    v18 = *(_DWORD *)(*(_QWORD *)(v2 + 96) + 152LL);
    if ( v18 > 1 && ((*(_DWORD *)(*(_QWORD *)(v2 + 96) + 152LL) - 1) & (unsigned int)v17) != 0 )
    {
      v19 = *(_DWORD *)(v2 + 248);
      if ( v19 + v18 < v19 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 73, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
        }
        v12 = 2737;
        goto LABEL_30;
      }
      Pool2 = ExAllocatePool2(258, v19 + v18, 1647465292);
      *(_QWORD *)(v2 + 208) = Pool2;
      if ( !Pool2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 74, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
        }
        v12 = 2752;
LABEL_47:
        v13 = 3221225989LL;
        goto LABEL_92;
      }
      v21 = (void *)(~(unsigned __int64)*(unsigned int *)(*(_QWORD *)(v2 + 96) + 152LL)
                   & (*(unsigned int *)(*(_QWORD *)(v2 + 96) + 152LL) + Pool2));
      memmove(v21, v17, *(unsigned int *)(v2 + 248));
      v17 = v21;
    }
  }
  IoBuildPartialMdl(
    *(PMDL *)(*(_QWORD *)(a1 + 304) + 56LL),
    *(PMDL *)(*(_QWORD *)(a1 + 304) + 80LL),
    v17,
    *(_DWORD *)(v2 + 248));
  LOBYTE(v25) = *(_BYTE *)(v2 + 280);
  if ( (v25 & 8) != 0 )
  {
    LOBYTE(v25) = 4;
    v26 = Smb2BuildPipeReadOrWriteRequest(a1, *(_QWORD *)(v2 + 88), v25, (_DWORD)v17, *(_DWORD *)(v2 + 248));
  }
  else
  {
    v29 = Srv2PostOnCompletionAndClearCancel;
    if ( Smb2EnableInlineSendIOCompletion )
      v29 = Srv2ClearCancelAndCallCallback;
    LOBYTE(v37) = 0;
    LOBYTE(v34) = 4;
    v26 = Smb2BuildReadOrWriteRequest(
            a1,
            0,
            *(_QWORD *)(v2 + 88),
            *(_QWORD *)(v2 + 96),
            v34,
            v37,
            v17,
            *(_DWORD *)(v2 + 248),
            *(_QWORD *)(*(_QWORD *)(a1 + 304) + 80LL),
            *(_QWORD *)(v2 + 192),
            *(_DWORD *)(v2 + 256),
            v29,
            (v25 & 0x40) != 0,
            (v25 & 0x20) != 0);
  }
  if ( v26 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 75, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v12 = 2837;
    goto LABEL_47;
  }
  *(_BYTE *)(*(_QWORD *)(v2 + 72) + 239LL) = 1;
  if ( (*(_BYTE *)(v2 + 280) & 8) == 0
    && *(_BYTE *)(*(_QWORD *)(v2 + 56) + 88LL)
    && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 88) + 24LL) + 40LL) + 0x2000000LL < *(_QWORD *)(v2 + 192) )
  {
    if ( *(_QWORD *)(v2 + 168) != -1 || (LOBYTE(v28) = 1, v30 = Smb2PreGoAsync2Ex(a1, 0, v28), v30 >= 0) )
    {
      *(_DWORD *)(a1 + 72) = 1;
      *(_QWORD *)(a1 + 48) = Smb2ExecuteVdlWriteReal;
      return Smb2GoAsyncForSyncCall(a1);
    }
    v12 = 2858;
    v13 = (unsigned int)v30;
    goto LABEL_92;
  }
  *(_QWORD *)(a1 + 48) = Smb2ContinueWrite;
  LOBYTE(v27) = (*(_BYTE *)(v2 + 280) & 8) != 0;
  if ( (int)Srv2MarkWorkItemCancellable(a1, v27) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 76, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v12 = 2884;
    v13 = 3221225760LL;
    goto LABEL_92;
  }
  v32 = *(_BYTE *)(v2 + 280);
  if ( (v32 & 8) != 0 || (v33 = 0, (v32 & 0x10) != 0) )
  {
    v33 = 1;
    Srv2ReferenceConnection(a1);
  }
  LOBYTE(v36) = 1;
  LOBYTE(v31) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v31, 2895, "Smb2ExecuteWriteReal", v36);
  result = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 96), *(PIRP *)(a1 + 120));
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
0x14007e390  mov     [rsp+arg_8], rbx
0x14007e395  mov     [rsp+arg_10], rbp
0x14007e39a  push    rsi
0x14007e39b  push    rdi
0x14007e39c  push    r14
0x14007e39e  sub     rsp, 70h
0x14007e3a2  mov     rax, [rcx+130h]
0x14007e3a9  mov     rdi, rcx
0x14007e3ac  mov     rsi, [rcx+230h]
0x14007e3b3  mov     rbp, [rax+18h]
0x14007e3b7  mov     rax, [rsi+48h]
0x14007e3bb  cmp     byte ptr [rax+0EBh], 0
0x14007e3c2  jnz     short loc_14007E3FD
0x14007e3c4  mov     rcx, rsi
0x14007e3c7  call    Smb2ImpersonateWorkItem
0x14007e3cc  test    eax, eax
0x14007e3ce  js      short loc_14007E3FD
0x14007e3d0  mov     rcx, [rsi+50h]
0x14007e3d4  mov     edx, 2
0x14007e3d9  mov     rcx, [rcx+58h]
0x14007e3dd  call    cs:__imp_SrvLibAuditForceAccess
0x14007e3e4  nop     dword ptr [rax+rax+00h]
0x14007e3e9  test    eax, eax
0x14007e3eb  js      short loc_14007E3F8
0x14007e3ed  mov     rax, [rsi+48h]
0x14007e3f1  mov     byte ptr [rax+0EBh], 1
0x14007e3f8  call    Smb2Revert
0x14007e3fd  mov     rcx, [rsi+50h]; P
0x14007e401  call    Smb2DereferenceHandle
0x14007e406  mov     rax, [rsi+60h]
0x14007e40a  mov     qword ptr [rsi+50h], 0
0x14007e412  movzx   ecx, byte ptr [rax+4Ch]
0x14007e416  mov     rax, [rdi+78h]
0x14007e41a  cmp     [rax+42h], cl
0x14007e41d  jl      short loc_14007E428
0x14007e41f  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x14007e426  jz      short loc_14007E465
0x14007e428  mov     edx, 0Fh
0x14007e42d  cmp     cl, dl
0x14007e42f  cmovg   edx, ecx
0x14007e432  xor     r8d, r8d
0x14007e435  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14007e439  call    cs:__imp_IoAllocateIrpEx
0x14007e440  nop     dword ptr [rax+rax+00h]
0x14007e445  mov     rbx, rax
0x14007e448  test    rax, rax
0x14007e44b  jz      loc_14007EA1B
0x14007e451  mov     rcx, [rdi+78h]; Irp
0x14007e455  call    cs:__imp_IoFreeIrp
0x14007e45c  nop     dword ptr [rax+rax+00h]
0x14007e461  mov     [rdi+78h], rbx
0x14007e465  test    byte ptr [rsi+118h], 18h
0x14007e46c  jz      short loc_14007E4CE
0x14007e46e  mov     r8b, 1
0x14007e471  xor     edx, edx
0x14007e473  mov     rcx, rdi
0x14007e476  call    Smb2PreGoAsync2Ex
0x14007e47b  mov     ebx, eax
0x14007e47d  test    eax, eax
0x14007e47f  jns     short loc_14007E4CE
0x14007e481  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e488  lea     rcx, WPP_GLOBAL_Control
0x14007e48f  cmp     r10, rcx
0x14007e492  jz      short loc_14007E4C1
0x14007e494  test    dword ptr [r10+2Ch], 800000h
0x14007e49c  jz      short loc_14007E4C1
0x14007e49e  cmp     byte ptr [r10+29h], 1
0x14007e4a3  jb      short loc_14007E4C1
0x14007e4a5  mov     rcx, [r10+18h]
0x14007e4a9  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e4b0  mov     edx, 47h ; 'G'
0x14007e4b5  mov     [rsp+88h+var_68], eax
0x14007e4b9  mov     r9, rdi
0x14007e4bc  call    WPP_SF_qD
0x14007e4c1  mov     r9d, 0A5Dh
0x14007e4c7  mov     edx, ebx
0x14007e4c9  jmp     loc_14007EA6A
0x14007e4ce  cmp     qword ptr [rsi+0D8h], 0
0x14007e4d6  jz      short loc_14007E500
0x14007e4d8  mov     al, [rsi+118h]
0x14007e4de  test    al, 40h
0x14007e4e0  jnz     short loc_14007E4F3
0x14007e4e2  test    al, al
0x14007e4e4  js      short loc_14007E4F3
0x14007e4e6  mov     rcx, rdi
0x14007e4e9  call    Smb2ExecuteDirectPlacementMdlWrite
0x14007e4ee  jmp     loc_14007EA83
0x14007e4f3  mov     rcx, rdi
0x14007e4f6  call    Smb2ExecuteDirectPlacementWrite
0x14007e4fb  jmp     loc_14007EA83
0x14007e500  movzx   ecx, word ptr [rbp+42h]
0x14007e504  mov     eax, ecx
0x14007e506  add     eax, [rbp+44h]
0x14007e509  cmp     [rdi+194h], eax
0x14007e50f  jnb     short loc_14007E55D
0x14007e511  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e518  lea     rcx, WPP_GLOBAL_Control
0x14007e51f  cmp     r10, rcx
0x14007e522  jz      short loc_14007E54D
0x14007e524  test    dword ptr [r10+2Ch], 800000h
0x14007e52c  jz      short loc_14007E54D
0x14007e52e  cmp     byte ptr [r10+29h], 1
0x14007e533  jb      short loc_14007E54D
0x14007e535  mov     rcx, [r10+18h]
0x14007e539  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e540  mov     edx, 48h ; 'H'
0x14007e545  mov     r9, rdi
0x14007e548  call    WPP_SF_q
0x14007e54d  mov     r9d, 0A92h
0x14007e553  mov     edx, 0C000000Dh
0x14007e558  jmp     loc_14007EA6A
0x14007e55d  mov     al, [rsi+118h]
0x14007e563  add     rbp, rcx
0x14007e566  test    al, 40h
0x14007e568  jz      loc_14007E689
0x14007e56e  test    al, 8
0x14007e570  jnz     loc_14007E689
0x14007e576  mov     rax, [rsi+60h]
0x14007e57a  mov     edx, [rax+98h]
0x14007e580  cmp     edx, 1
0x14007e583  jbe     loc_14007E76F
0x14007e589  lea     ecx, [rdx-1]
0x14007e58c  test    rbp, rcx
0x14007e58f  jz      loc_14007E76F
0x14007e595  mov     eax, [rsi+0F8h]
0x14007e59b  lea     ecx, [rax+rdx]
0x14007e59e  cmp     ecx, eax
0x14007e5a0  jnb     short loc_14007E5E9
0x14007e5a2  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e5a9  lea     rcx, WPP_GLOBAL_Control
0x14007e5b0  cmp     r10, rcx
0x14007e5b3  jz      short loc_14007E5DE
0x14007e5b5  test    dword ptr [r10+2Ch], 800000h
0x14007e5bd  jz      short loc_14007E5DE
0x14007e5bf  cmp     byte ptr [r10+29h], 1
0x14007e5c4  jb      short loc_14007E5DE
0x14007e5c6  mov     rcx, [r10+18h]
0x14007e5ca  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e5d1  mov     edx, 49h ; 'I'
0x14007e5d6  mov     r9, rdi
0x14007e5d9  call    WPP_SF_q
0x14007e5de  mov     r9d, 0AB1h
0x14007e5e4  jmp     loc_14007E553
0x14007e5e9  mov     edx, ecx
0x14007e5eb  mov     r8d, 6232534Ch
0x14007e5f1  mov     ecx, 102h
0x14007e5f6  call    cs:__imp_ExAllocatePool2
0x14007e5fd  nop     dword ptr [rax+rax+00h]
0x14007e602  mov     [rsi+0D0h], rax
0x14007e609  mov     rdx, rax
0x14007e60c  test    rax, rax
0x14007e60f  jnz     short loc_14007E65B
0x14007e611  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e618  lea     rcx, WPP_GLOBAL_Control
0x14007e61f  cmp     r10, rcx
0x14007e622  jz      short loc_14007E64B
0x14007e624  test    dword ptr [r10+2Ch], 800000h
0x14007e62c  jz      short loc_14007E64B
0x14007e62e  cmp     byte ptr [r10+29h], 1
0x14007e633  jb      short loc_14007E64B
0x14007e635  mov     rcx, [r10+18h]
0x14007e639  lea     edx, [rax+4Ah]
0x14007e63c  mov     r9, rdi
0x14007e63f  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e646  call    WPP_SF_q
0x14007e64b  mov     r9d, 0AC0h
0x14007e651  mov     edx, 0C0000205h
0x14007e656  jmp     loc_14007EA6A
0x14007e65b  mov     rax, [rsi+60h]
0x14007e65f  mov     r8d, [rsi+0F8h]; Size
0x14007e666  mov     ecx, [rax+98h]
0x14007e66c  lea     rbx, [rcx+rdx]
0x14007e670  not     rcx
0x14007e673  and     rbx, rcx
0x14007e676  mov     rdx, rbp; Src
0x14007e679  mov     rcx, rbx; void *
0x14007e67c  call    memmove
0x14007e681  mov     rbp, rbx
0x14007e684  jmp     loc_14007E76F
0x14007e689  mov     rax, [rsi+48h]
0x14007e68d  cmp     byte ptr [rax+0EFh], 0
0x14007e694  jz      loc_14007E76F
0x14007e69a  mov     rax, [rsi+60h]
0x14007e69e  mov     rcx, [rax+8]
0x14007e6a2  mov     rbx, [rcx+50h]
0x14007e6a6  test    rbx, rbx
0x14007e6a9  jz      loc_14007E76F
0x14007e6af  cmp     dword ptr [rbx], 18h
0x14007e6b2  jbe     loc_14007E76F
0x14007e6b8  cmp     qword ptr [rbx+18h], 0
0x14007e6bd  jz      loc_14007E76F
0x14007e6c3  lea     r14, [rdi+248h]
0x14007e6ca  mov     byte ptr [rsp+88h+var_68], 1
0x14007e6cf  mov     rcx, r14
0x14007e6d2  lea     r9, aSmb2executewri; "Smb2ExecuteWriteReal"
0x14007e6d9  mov     r8d, 0AD3h
0x14007e6df  mov     dl, 2
0x14007e6e1  call    SRV2_PERF_ENTER_EX
0x14007e6e6  mov     rcx, [rsi+60h]
0x14007e6ea  lea     rdx, [rsi+0C0h]
0x14007e6f1  mov     r8, [rdi+78h]
0x14007e6f5  xor     r9d, r9d
0x14007e6f8  mov     rax, [rbx+18h]
0x14007e6fc  add     r8, 30h ; '0'
0x14007e700  mov     [rsp+88h+var_50], rcx
0x14007e705  mov     rcx, [rsi+58h]
0x14007e709  mov     [rsp+88h+var_58], r8
0x14007e70e  mov     r8d, [rsi+100h]
0x14007e715  mov     [rsp+88h+var_60], rbp
0x14007e71a  mov     [rsp+88h+var_68], r8d
0x14007e71f  mov     r8d, [rsi+0F8h]
0x14007e726  call    _guard_dispatch_icall
0x14007e72b  xor     edx, edx
0x14007e72d  mov     byte ptr [rsp+88h+var_68], 1
0x14007e732  lea     r9, aSmb2executewri; "Smb2ExecuteWriteReal"
0x14007e739  mov     rcx, r14
0x14007e73c  test    al, al
0x14007e73e  jz      short loc_14007E764
0x14007e740  mov     r8d, 0ADFh
0x14007e746  call    SRV2_PERF_ENTER_EX
0x14007e74b  mov     rax, [rdi+78h]
0x14007e74f  mov     rcx, rdi
0x14007e752  mov     qword ptr [rax+8], 0
0x14007e75a  call    Smb2ContinueWrite
0x14007e75f  jmp     loc_14007EA83
0x14007e764  mov     r8d, 0AE5h
0x14007e76a  call    SRV2_PERF_ENTER_EX
0x14007e76f  mov     rcx, [rdi+130h]
0x14007e776  mov     r8, rbp; VirtualAddress
0x14007e779  mov     r9d, [rsi+0F8h]; Length
0x14007e780  mov     rdx, [rcx+50h]; TargetMdl
0x14007e784  mov     rcx, [rcx+38h]; SourceMdl
0x14007e788  call    cs:__imp_IoBuildPartialMdl
0x14007e78f  nop     dword ptr [rax+rax+00h]
0x14007e794  mov     r8b, [rsi+118h]
0x14007e79b  test    r8b, 8
0x14007e79f  jz      short loc_14007E7C2
0x14007e7a1  mov     eax, [rsi+0F8h]
0x14007e7a7  mov     r9, rbp
0x14007e7aa  mov     rdx, [rsi+58h]
0x14007e7ae  mov     r8b, 4
0x14007e7b1  mov     rcx, rdi
0x14007e7b4  mov     [rsp+88h+var_68], eax
0x14007e7b8  call    Smb2BuildPipeReadOrWriteRequest
0x14007e7bd  jmp     loc_14007E84A
0x14007e7c2  mov     rcx, [rdi+130h]
0x14007e7c9  lea     rax, Srv2ClearCancelAndCallCallback
0x14007e7d0  cmp     cs:Smb2EnableInlineSendIOCompletion, 0
0x14007e7d7  lea     rdx, Srv2PostOnCompletionAndClearCancel
0x14007e7de  mov     r9, [rsi+60h]
0x14007e7e2  cmovnz  rdx, rax
0x14007e7e6  mov     al, r8b
0x14007e7e9  shr     al, 5
0x14007e7ec  and     al, 1
0x14007e7ee  shr     r8b, 6
0x14007e7f2  mov     [rsp+88h+var_20], al
0x14007e7f6  and     r8b, 1
0x14007e7fa  mov     eax, [rsi+100h]
0x14007e800  mov     [rsp+88h+var_28], r8b
0x14007e805  mov     r8, [rsi+58h]
0x14007e809  mov     [rsp+88h+var_30], rdx
0x14007e80e  xor     edx, edx
0x14007e810  mov     [rsp+88h+var_38], eax
0x14007e814  mov     rax, [rsi+0C0h]
0x14007e81b  mov     [rsp+88h+var_40], rax
0x14007e820  mov     rax, [rcx+50h]
0x14007e824  mov     rcx, rdi
0x14007e827  mov     [rsp+88h+var_48], rax
0x14007e82c  mov     eax, [rsi+0F8h]
0x14007e832  mov     dword ptr [rsp+88h+var_50], eax
0x14007e836  mov     [rsp+88h+var_58], rbp
0x14007e83b  mov     byte ptr [rsp+88h+var_60], 0
0x14007e840  mov     byte ptr [rsp+88h+var_68], 4
0x14007e845  call    Smb2BuildReadOrWriteRequest
0x14007e84a  test    eax, eax
0x14007e84c  jns     short loc_14007E895
0x14007e84e  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e855  lea     rcx, WPP_GLOBAL_Control
0x14007e85c  cmp     r10, rcx
0x14007e85f  jz      short loc_14007E88A
0x14007e861  test    dword ptr [r10+2Ch], 800000h
0x14007e869  jz      short loc_14007E88A
0x14007e86b  cmp     byte ptr [r10+29h], 1
0x14007e870  jb      short loc_14007E88A
0x14007e872  mov     rcx, [r10+18h]
0x14007e876  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e87d  mov     edx, 4Bh ; 'K'
0x14007e882  mov     r9, rdi
0x14007e885  call    WPP_SF_q
0x14007e88a  mov     r9d, 0B15h
0x14007e890  jmp     loc_14007E651
0x14007e895  mov     rax, [rsi+48h]
0x14007e899  mov     byte ptr [rax+0EFh], 1
0x14007e8a0  test    byte ptr [rsi+118h], 8
0x14007e8a7  jnz     short loc_14007E915
0x14007e8a9  mov     rax, [rsi+38h]
0x14007e8ad  cmp     byte ptr [rax+58h], 0
0x14007e8b1  jz      short loc_14007E915
0x14007e8b3  mov     rax, [rsi+58h]
0x14007e8b7  mov     rcx, [rax+18h]
  ... truncated ...
```
