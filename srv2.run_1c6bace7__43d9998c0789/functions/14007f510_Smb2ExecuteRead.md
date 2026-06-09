# Smb2ExecuteRead

- ea: `0x14007f510`
- end: `0x14007fd3b`
- name: `Smb2ExecuteRead`
- size: `2091`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140032e10`
- `0x1400748b0`

## callees

- `0x1400041a0`
- `0x140004560`
- `0x140005070`
- `0x140007400`
- `0x1400125d0`
- `0x140013810`
- `0x1400152a0`
- `0x14001c4c4`
- `0x1400222ec`
- `0x140022958`
- `0x1400384d0`
- `0x140077650`
- `0x14007f510`
- `0x14007fd50`
- `0x140080114`
- `0x1400803b4`
- `0x140086160`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007f9a6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007fa1b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007f9a6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007fa1b`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007f963`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007f963`
- `ntoskrnl!IofCallDriver` at `0x14007f89b`
- `ntoskrnl!IofCallDriver` at `0x14007fca1`
- `ntoskrnl!IofCallDriver` at `0x14007f89b`
- `ntoskrnl!IofCallDriver` at `0x14007fca1`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007f94b`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007f94b`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14007f8ed`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14007f9d3`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14007f8ed`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14007f9d3`
- `srvnet!SrvLibAuditForceAccess` at `0x14007f586`
- `srvnet!SrvLibAuditForceAccess` at `0x14007f586`

## string_xrefs

- `0x14007f64b`: `Smb2ExecuteRead`
- `0x14007fa57`: `Smb2ExecuteRead`
- `0x14007fd09`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteRead(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  char v5; // bp
  bool v6; // si
  int v7; // ecx
  char v8; // al
  __int64 v10; // r14
  char v11; // al
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // r14d
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rsi
  unsigned int v20; // eax
  __int64 v21; // rcx
  __int64 BufferNoTransportHeader; // rax
  ULONG v23; // r14d
  void *v24; // rbp
  __int64 v25; // rsi
  struct _MDL *v26; // r15
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rcx
  PVOID v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  PVOID v33; // rax
  __int64 v34; // rcx
  char v35; // r9
  __int64 v36; // rsi
  char v37; // al
  __int64 v38; // rcx
  __int64 (__fastcall *v39)(); // rcx
  int v40; // eax
  __int64 v41; // rdx
  unsigned int v42; // esi
  __int64 v43; // rdx
  int v44; // eax
  unsigned int v45; // ebx
  int BugCheckOnFailure; // [rsp+20h] [rbp-98h]
  int BugCheckOnFailurea; // [rsp+20h] [rbp-98h]
  int BugCheckOnFailureb; // [rsp+20h] [rbp-98h]
  int BugCheckOnFailurec; // [rsp+20h] [rbp-98h]
  int BugCheckOnFailured; // [rsp+20h] [rbp-98h]
  int Priority; // [rsp+28h] [rbp-90h]

  v3 = *(_QWORD *)(a1 + 560);
  v5 = *(_BYTE *)(v3 + 264);
  v6 = Smb2DirectDataPlacementSecurity == 1
    || Smb2DirectDataPlacementSecurity == 2 && !*(_BYTE *)(*(_QWORD *)(v3 + 56) + 92LL);
  if ( *(_QWORD *)(v3 + 80) )
  {
    if ( !*(_BYTE *)(*(_QWORD *)(v3 + 72) + 234LL) && (int)Smb2ImpersonateWorkItem(*(_QWORD *)(a1 + 560)) >= 0 )
    {
      if ( (int)SrvLibAuditForceAccess(*(_QWORD *)(*(_QWORD *)(v3 + 80) + 88LL), 1) >= 0 )
        *(_BYTE *)(*(_QWORD *)(v3 + 72) + 234LL) = 1;
      Smb2Revert();
    }
    Smb2DereferenceHandle(*(PVOID *)(v3 + 80));
    *(_QWORD *)(v3 + 80) = 0;
  }
  if ( v6 && *(_QWORD *)(v3 + 216) )
  {
    v7 = *(_DWORD *)(*(_QWORD *)(v3 + 32) + 304LL);
    if ( (v7 & 1) != 0 && *(int *)(v3 + 8) >= 2 )
    {
      *(_DWORD *)(v3 + 260) = 1;
    }
    else if ( (v7 & 2) != 0 && *(int *)(v3 + 8) >= 1 )
    {
      *(_DWORD *)(v3 + 260) = 2;
    }
  }
  v8 = *(_BYTE *)(v3 + 264);
  if ( (v8 & 0xC) != 0 )
  {
    LOBYTE(a3) = 1;
    v44 = Smb2PreGoAsync2Ex(a1, 0, a3);
    v45 = v44;
    if ( v44 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1, v44);
      }
      v16 = 1965;
      v17 = v45;
      goto LABEL_99;
    }
    goto LABEL_100;
  }
  if ( (v8 & 0x20) != 0 )
  {
LABEL_100:
    Smb2RestartNonMdlRead(a1);
    return 259;
  }
  if ( (v5 & 0x10) == 0 )
  {
    if ( Smb2AllowSequentialRead )
    {
      a2 = *(unsigned int *)(*(_QWORD *)(v3 + 72) + 192LL);
      if ( (a2 & 4) != 0 && (unsigned int)Smb2PreSequentialRead(a1) == 259 )
        return 259;
    }
    if ( (*(_BYTE *)(v3 + 264) & 2) == 0 )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v3 + 72) + 239LL) )
      {
        v10 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 96) + 8LL) + 80LL);
        if ( v10 )
        {
          if ( *(_DWORD *)v10 > 0x80u && *(_QWORD *)(v10 + 128) )
          {
            LOBYTE(a2) = 2;
            *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
            SRV2_PERF_ENTER_EX(a1 + 584, a2, 2009, "Smb2ExecuteRead", 1);
            v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64, __int64, _QWORD))(v10 + 128))(
                    *(_QWORD *)(v3 + 88),
                    v3 + 192,
                    *(unsigned int *)(v3 + 236),
                    *(unsigned int *)(v3 + 252),
                    *(_QWORD *)(a1 + 120) + 8LL,
                    *(_QWORD *)(a1 + 120) + 48LL,
                    *(_QWORD *)(v3 + 96));
            LOBYTE(BugCheckOnFailurea) = 1;
            v12 = a1 + 584;
            if ( v11 )
            {
              SRV2_PERF_ENTER_EX(v12, 0, 2023, "Smb2ExecuteRead", BugCheckOnFailurea);
              Smb2ContinueMdlRead(a1);
              return 259;
            }
            SRV2_PERF_ENTER_EX(v12, 0, 2031, "Smb2ExecuteRead", BugCheckOnFailurea);
          }
        }
      }
    }
    LOBYTE(Priority) = 2;
    LOBYTE(BugCheckOnFailure) = 3;
    v13 = Smb2BuildReadOrWriteRequest(
            a1,
            0,
            *(_QWORD *)(v3 + 88),
            *(_QWORD *)(v3 + 96),
            BugCheckOnFailure,
            Priority,
            0,
            *(_DWORD *)(v3 + 236),
            *(_QWORD *)(v3 + 200),
            *(_QWORD *)(v3 + 192),
            *(_DWORD *)(v3 + 252),
            Srv2PostOnCompletionAndClearCancel,
            0,
            0);
    v15 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1, v13);
      }
      Smb2SequentialReadComplete(a1);
      v16 = 2061;
      v17 = v15;
      goto LABEL_99;
    }
    LOBYTE(v14) = (*(_BYTE *)(v3 + 264) & 4) != 0;
    if ( (int)Srv2MarkWorkItemCancellable(a1, v14) >= 0 )
    {
      LOBYTE(BugCheckOnFailureb) = 1;
      LOBYTE(v18) = 3;
      *(_BYTE *)(*(_QWORD *)(v3 + 72) + 239LL) = 1;
      *(_QWORD *)(a1 + 48) = Smb2ContinueMdlRead;
      SRV2_PERF_ENTER_EX(a1 + 584, v18, 2082, "Smb2ExecuteRead", BugCheckOnFailureb);
      IofCallDriver(*(PDEVICE_OBJECT *)(v3 + 96), *(PIRP *)(a1 + 120));
      return 259;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
    }
    Smb2SequentialReadComplete(a1);
    v16 = 2072;
    goto LABEL_48;
  }
  v19 = *(unsigned int *)(*(_QWORD *)(v3 + 96) + 152LL);
  if ( (unsigned int)v19 > 1 && (v20 = *(_DWORD *)(v3 + 236), (v20 & 0xFFF) != 0) )
  {
    v21 = v20 + (unsigned int)v19;
    *(_DWORD *)(v3 + 256) = v19;
    if ( (unsigned int)v21 < v20 )
    {
      v16 = 2107;
      v17 = 3221225485LL;
      goto LABEL_99;
    }
    BufferNoTransportHeader = SrvNetAllocateBufferNoTransportHeader(v21);
    *(_QWORD *)(v3 + 160) = BufferNoTransportHeader;
    if ( !BufferNoTransportHeader )
    {
      v16 = 2114;
LABEL_56:
      v17 = 3221225989LL;
      goto LABEL_99;
    }
    v23 = *(_DWORD *)(v3 + 236);
    v24 = (void *)(-(int)v19 & (unsigned __int64)(*(_QWORD *)(BufferNoTransportHeader + 24) + v19 - 1));
    *(_QWORD *)(v3 + 208) = v24;
    v25 = *(_QWORD *)(BufferNoTransportHeader + 80);
    v26 = *(struct _MDL **)(BufferNoTransportHeader + 56);
    if ( (*(_BYTE *)(v25 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v25 + 24), *(PMDL *)(BufferNoTransportHeader + 80));
    IoBuildPartialMdl(v26, (PMDL)v25, v24, v23);
    v28 = *(_QWORD *)(v3 + 160);
    *(_QWORD *)(v3 + 200) = *(_QWORD *)(v28 + 80);
    v29 = *(_QWORD *)(v28 + 80);
    if ( (*(_BYTE *)(v29 + 10) & 5) != 0 )
      v30 = *(PVOID *)(v29 + 24);
    else
      v30 = MmMapLockedPagesSpecifyCache((PMDL)v29, 0, MmCached, 0, 0, 0x40000010u);
    *(_QWORD *)(v3 + 208) = v30;
    if ( !v30 )
    {
      v16 = 2125;
      goto LABEL_56;
    }
  }
  else
  {
    v31 = SrvNetAllocateBufferNoTransportHeader(*(unsigned int *)(v3 + 236));
    *(_QWORD *)(v3 + 160) = v31;
    if ( !v31 )
    {
      v16 = 2137;
      goto LABEL_56;
    }
    v32 = *(_QWORD *)(v31 + 56);
    if ( (*(_BYTE *)(v32 + 10) & 5) != 0 )
      v33 = *(PVOID *)(v32 + 24);
    else
      v33 = MmMapLockedPagesSpecifyCache((PMDL)v32, 0, MmCached, 0, 0, 0x40000010u);
    v34 = *(_QWORD *)(v3 + 160);
    *(_QWORD *)(v3 + 208) = v33;
    v27 = *(_QWORD *)(v34 + 56);
    *(_QWORD *)(v3 + 200) = v27;
    if ( !v33 )
    {
      v16 = 2146;
      goto LABEL_56;
    }
  }
  v35 = *(_BYTE *)(v3 + 264);
  if ( (v35 & 2) == 0 )
  {
    v36 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 96) + 8LL) + 80LL);
    if ( v36 )
    {
      if ( *(_DWORD *)v36 > 0x10u && *(_QWORD *)(v36 + 16) )
      {
        LOBYTE(BugCheckOnFailure) = 1;
        LOBYTE(v27) = 2;
        SRV2_PERF_ENTER_EX(a1 + 584, v27, 2159, "Smb2ExecuteRead", BugCheckOnFailure);
        v37 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _QWORD, __int64, _QWORD))(v36 + 16))(
                *(_QWORD *)(v3 + 88),
                v3 + 192,
                *(unsigned int *)(v3 + 236),
                0,
                *(_DWORD *)(v3 + 252),
                *(_QWORD *)(*(_QWORD *)(v3 + 200) + 32LL) + *(unsigned int *)(*(_QWORD *)(v3 + 200) + 44LL),
                *(_QWORD *)(a1 + 120) + 48LL,
                *(_QWORD *)(v3 + 96));
        LOBYTE(BugCheckOnFailurec) = 1;
        v38 = a1 + 584;
        if ( v37 )
        {
          SRV2_PERF_ENTER_EX(v38, 0, 2174, "Smb2ExecuteRead", BugCheckOnFailurec);
          Smb2ContinueUncachedRead(a1);
          return 259;
        }
        SRV2_PERF_ENTER_EX(v38, 0, 2179, "Smb2ExecuteRead", BugCheckOnFailurec);
        v35 = *(_BYTE *)(v3 + 264);
      }
    }
  }
  v39 = Srv2PostOnCompletionAndClearCancel;
  if ( Smb2EnableInlineSendIOCompletion )
    v39 = Srv2ClearCancelAndCallCallback;
  LOBYTE(Priority) = 0;
  LOBYTE(BugCheckOnFailure) = 3;
  v40 = Smb2BuildReadOrWriteRequest(
          a1,
          0,
          *(_QWORD *)(v3 + 88),
          *(_QWORD *)(v3 + 96),
          BugCheckOnFailure,
          Priority,
          *(_QWORD *)(*(_QWORD *)(v3 + 200) + 32LL) + *(unsigned int *)(*(_QWORD *)(v3 + 200) + 44LL),
          *(_DWORD *)(v3 + 236),
          *(_QWORD *)(v3 + 200),
          *(_QWORD *)(v3 + 192),
          *(_DWORD *)(v3 + 252),
          v39,
          (v35 & 0x10) != 0,
          0);
  v42 = v40;
  if ( v40 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1, v40);
    }
    v16 = 2211;
    v17 = v42;
    goto LABEL_99;
  }
  *(_QWORD *)(a1 + 48) = Smb2ContinueUncachedIrpRead;
  LOBYTE(v41) = (*(_BYTE *)(v3 + 264) & 4) != 0;
  if ( (int)Srv2MarkWorkItemCancellable(a1, v41) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
    }
    v16 = 2222;
LABEL_48:
    v17 = 3221225760LL;
LABEL_99:
    Smb2SetError(a1, v17, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", v16);
    return 0;
  }
  LOBYTE(BugCheckOnFailured) = 1;
  LOBYTE(v43) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v43, 2226, "Smb2ExecuteRead", BugCheckOnFailured);
  IofCallDriver(*(PDEVICE_OBJECT *)(v3 + 96), *(PIRP *)(a1 + 120));
  return 259;
}

```

## disassembly

```asm
0x14007f510  push    rbx
0x14007f512  push    rbp
0x14007f513  push    rsi
0x14007f514  push    rdi
0x14007f515  push    r12
0x14007f517  push    r13
0x14007f519  push    r14
0x14007f51b  push    r15
0x14007f51d  sub     rsp, 78h
0x14007f521  mov     rbx, [rcx+230h]
0x14007f528  xor     r12d, r12d
0x14007f52b  mov     eax, cs:Smb2DirectDataPlacementSecurity
0x14007f531  mov     rdi, rcx
0x14007f534  mov     bpl, [rbx+108h]
0x14007f53b  lea     r13d, [r12+1]
0x14007f540  cmp     eax, r13d
0x14007f543  jz      short loc_14007F559
0x14007f545  cmp     eax, 2
0x14007f548  jnz     short loc_14007F554
0x14007f54a  mov     rax, [rbx+38h]
0x14007f54e  cmp     [rax+5Ch], r12b
0x14007f552  jz      short loc_14007F559
0x14007f554  mov     sil, r12b
0x14007f557  jmp     short loc_14007F55C
0x14007f559  mov     sil, r13b
0x14007f55c  cmp     [rbx+50h], r12
0x14007f560  jz      short loc_14007F5B3
0x14007f562  mov     rax, [rbx+48h]
0x14007f566  cmp     [rax+0EAh], r12b
0x14007f56d  jnz     short loc_14007F5A6
0x14007f56f  mov     rcx, rbx
0x14007f572  call    Smb2ImpersonateWorkItem
0x14007f577  test    eax, eax
0x14007f579  js      short loc_14007F5A6
0x14007f57b  mov     rcx, [rbx+50h]
0x14007f57f  mov     edx, r13d
0x14007f582  mov     rcx, [rcx+58h]
0x14007f586  call    cs:__imp_SrvLibAuditForceAccess
0x14007f58d  nop     dword ptr [rax+rax+00h]
0x14007f592  test    eax, eax
0x14007f594  js      short loc_14007F5A1
0x14007f596  mov     rax, [rbx+48h]
0x14007f59a  mov     [rax+0EAh], r13b
0x14007f5a1  call    Smb2Revert
0x14007f5a6  mov     rcx, [rbx+50h]; P
0x14007f5aa  call    Smb2DereferenceHandle
0x14007f5af  mov     [rbx+50h], r12
0x14007f5b3  test    sil, sil
0x14007f5b6  jz      short loc_14007F5F4
0x14007f5b8  cmp     [rbx+0D8h], r12
0x14007f5bf  jz      short loc_14007F5F4
0x14007f5c1  mov     rax, [rbx+20h]
0x14007f5c5  mov     ecx, [rax+130h]
0x14007f5cb  test    r13b, cl
0x14007f5ce  jz      short loc_14007F5D6
0x14007f5d0  cmp     dword ptr [rbx+8], 2
0x14007f5d4  jge     short loc_14007F5ED
0x14007f5d6  test    cl, 2
0x14007f5d9  jz      short loc_14007F5F4
0x14007f5db  cmp     [rbx+8], r13d
0x14007f5df  jl      short loc_14007F5F4
0x14007f5e1  mov     dword ptr [rbx+104h], 2
0x14007f5eb  jmp     short loc_14007F5F4
0x14007f5ed  mov     [rbx+104h], r13d
0x14007f5f4  mov     al, [rbx+108h]
0x14007f5fa  test    al, 0Ch
0x14007f5fc  jnz     loc_14007FCAF
0x14007f602  test    al, 20h
0x14007f604  jnz     loc_14007FD1C
0x14007f60a  test    bpl, 10h
0x14007f60e  jnz     loc_14007F8AC
0x14007f614  cmp     cs:Smb2AllowSequentialRead, r12b
0x14007f61b  mov     esi, 103h
0x14007f620  jz      short loc_14007F644
0x14007f622  mov     rcx, [rbx+48h]
0x14007f626  mov     edx, [rcx+0C0h]
0x14007f62c  test    dl, 4
0x14007f62f  jz      short loc_14007F644
0x14007f631  mov     rcx, rdi
0x14007f634  call    Smb2PreSequentialRead
0x14007f639  cmp     eax, esi
0x14007f63b  jnz     short loc_14007F644
0x14007f63d  mov     eax, esi
0x14007f63f  jmp     loc_14007FD29
0x14007f644  test    byte ptr [rbx+108h], 2
0x14007f64b  lea     rbp, aSmb2executerea; "Smb2ExecuteRead"
0x14007f652  jnz     loc_14007F737
0x14007f658  mov     rax, [rbx+48h]
0x14007f65c  cmp     [rax+0EFh], r12b
0x14007f663  jz      loc_14007F737
0x14007f669  mov     rax, [rbx+60h]
0x14007f66d  mov     rcx, [rax+8]
0x14007f671  mov     r14, [rcx+50h]
0x14007f675  test    r14, r14
0x14007f678  jz      loc_14007F737
0x14007f67e  cmp     dword ptr [r14], 80h
0x14007f685  jbe     loc_14007F737
0x14007f68b  cmp     [r14+80h], r12
0x14007f692  jz      loc_14007F737
0x14007f698  mov     rax, [rdi+78h]
0x14007f69c  lea     r15, [rdi+248h]
0x14007f6a3  mov     r9, rbp
0x14007f6a6  mov     byte ptr [rsp+0B8h+BugCheckOnFailure], r13b
0x14007f6ab  mov     r8d, 7D9h
0x14007f6b1  mov     dl, 2
0x14007f6b3  mov     rcx, r15
0x14007f6b6  mov     [rax+8], r12
0x14007f6ba  call    SRV2_PERF_ENTER_EX
0x14007f6bf  mov     rax, [rdi+78h]
0x14007f6c3  lea     rdx, [rbx+0C0h]
0x14007f6ca  mov     rcx, [rbx+60h]
0x14007f6ce  mov     r9d, [rbx+0FCh]
0x14007f6d5  mov     [rsp+0B8h+var_88], rcx
0x14007f6da  mov     rcx, [rbx+58h]
0x14007f6de  lea     r8, [rax+30h]
0x14007f6e2  add     rax, 8
0x14007f6e6  mov     qword ptr [rsp+0B8h+Priority], r8
0x14007f6eb  mov     r8d, [rbx+0ECh]
0x14007f6f2  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x14007f6f7  mov     rax, [r14+80h]
0x14007f6fe  call    _guard_dispatch_icall
0x14007f703  xor     edx, edx
0x14007f705  mov     byte ptr [rsp+0B8h+BugCheckOnFailure], r13b
0x14007f70a  mov     r9, rbp
0x14007f70d  mov     rcx, r15
0x14007f710  test    al, al
0x14007f712  jz      short loc_14007F72C
0x14007f714  mov     r8d, 7E7h
0x14007f71a  call    SRV2_PERF_ENTER_EX
0x14007f71f  mov     rcx, rdi
0x14007f722  call    Smb2ContinueMdlRead
0x14007f727  jmp     loc_14007F63D
0x14007f72c  mov     r8d, 7EFh
0x14007f732  call    SRV2_PERF_ENTER_EX
0x14007f737  mov     rax, [rbx+0C0h]
0x14007f73e  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x14007f745  mov     r9, [rbx+60h]
0x14007f749  xor     edx, edx
0x14007f74b  mov     r8, [rbx+58h]
0x14007f74f  mov     [rsp+0B8h+var_50], r12b
0x14007f754  mov     [rsp+0B8h+var_58], r12b
0x14007f759  mov     [rsp+0B8h+var_60], rcx
0x14007f75e  mov     ecx, [rbx+0FCh]
0x14007f764  mov     [rsp+0B8h+var_68], ecx
0x14007f768  mov     rcx, rdi
0x14007f76b  mov     [rsp+0B8h+var_70], rax
0x14007f770  mov     rax, [rbx+0C8h]
0x14007f777  mov     [rsp+0B8h+var_78], rax
0x14007f77c  mov     eax, [rbx+0ECh]
0x14007f782  mov     dword ptr [rsp+0B8h+var_80], eax
0x14007f786  mov     [rsp+0B8h+var_88], r12
0x14007f78b  mov     byte ptr [rsp+0B8h+Priority], 2
0x14007f790  mov     byte ptr [rsp+0B8h+BugCheckOnFailure], 3
0x14007f795  call    Smb2BuildReadOrWriteRequest
0x14007f79a  mov     r14d, eax
0x14007f79d  test    eax, eax
0x14007f79f  jns     short loc_14007F7F6
0x14007f7a1  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007f7a8  lea     rcx, WPP_GLOBAL_Control
0x14007f7af  cmp     r10, rcx
0x14007f7b2  jz      short loc_14007F7E0
0x14007f7b4  test    dword ptr [r10+2Ch], 800000h
0x14007f7bc  jz      short loc_14007F7E0
0x14007f7be  cmp     [r10+29h], r13b
0x14007f7c2  jb      short loc_14007F7E0
0x14007f7c4  mov     rcx, [r10+18h]
0x14007f7c8  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14007f7cf  mov     edx, 22h ; '"'
0x14007f7d4  mov     [rsp+0B8h+BugCheckOnFailure], eax
0x14007f7d8  mov     r9, rdi
0x14007f7db  call    WPP_SF_qD
0x14007f7e0  mov     rcx, rdi
0x14007f7e3  call    Smb2SequentialReadComplete
0x14007f7e8  mov     r9d, 80Dh
0x14007f7ee  mov     edx, r14d
0x14007f7f1  jmp     loc_14007FD09
0x14007f7f6  mov     dl, [rbx+108h]
0x14007f7fc  mov     rcx, rdi
0x14007f7ff  shr     dl, 2
0x14007f802  and     dl, r13b
0x14007f805  call    Srv2MarkWorkItemCancellable
0x14007f80a  test    eax, eax
0x14007f80c  jns     short loc_14007F861
0x14007f80e  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007f815  lea     rcx, WPP_GLOBAL_Control
0x14007f81c  cmp     r10, rcx
0x14007f81f  jz      short loc_14007F849
0x14007f821  test    dword ptr [r10+2Ch], 800000h
0x14007f829  jz      short loc_14007F849
0x14007f82b  cmp     [r10+29h], r13b
0x14007f82f  jb      short loc_14007F849
0x14007f831  mov     rcx, [r10+18h]
0x14007f835  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14007f83c  mov     edx, 23h ; '#'
0x14007f841  mov     r9, rdi
0x14007f844  call    WPP_SF_q
0x14007f849  mov     rcx, rdi
0x14007f84c  call    Smb2SequentialReadComplete
0x14007f851  mov     r9d, 818h
0x14007f857  mov     edx, 0C0000120h
0x14007f85c  jmp     loc_14007FD09
0x14007f861  mov     rax, [rbx+48h]
0x14007f865  lea     rcx, [rdi+248h]
0x14007f86c  mov     r9, rbp
0x14007f86f  mov     byte ptr [rsp+0B8h+BugCheckOnFailure], r13b
0x14007f874  mov     r8d, 822h
0x14007f87a  mov     dl, 3
0x14007f87c  mov     [rax+0EFh], r13b
0x14007f883  lea     rax, Smb2ContinueMdlRead
0x14007f88a  mov     [rdi+30h], rax
0x14007f88e  call    SRV2_PERF_ENTER_EX
0x14007f893  mov     rdx, [rdi+78h]; Irp
0x14007f897  mov     rcx, [rbx+60h]; DeviceObject
0x14007f89b  call    cs:__imp_IofCallDriver
0x14007f8a2  nop     dword ptr [rax+rax+00h]
0x14007f8a7  jmp     loc_14007F63D
0x14007f8ac  mov     rax, [rbx+60h]
0x14007f8b0  mov     esi, [rax+98h]
0x14007f8b6  cmp     esi, r13d
0x14007f8b9  jbe     loc_14007F9CD
0x14007f8bf  mov     eax, [rbx+0ECh]
0x14007f8c5  test    eax, 0FFFh
0x14007f8ca  jz      loc_14007F9CD
0x14007f8d0  lea     ecx, [rax+rsi]
0x14007f8d3  mov     [rbx+100h], esi
0x14007f8d9  cmp     ecx, eax
0x14007f8db  jnb     short loc_14007F8ED
0x14007f8dd  mov     r9d, 83Bh
0x14007f8e3  mov     edx, 0C000000Dh
0x14007f8e8  jmp     loc_14007FD09
0x14007f8ed  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14007f8f4  nop     dword ptr [rax+rax+00h]
0x14007f8f9  mov     [rbx+0A0h], rax
0x14007f900  mov     rdx, rax
0x14007f903  test    rax, rax
0x14007f906  jnz     short loc_14007F918
0x14007f908  mov     r9d, 842h
0x14007f90e  mov     edx, 0C0000205h
0x14007f913  jmp     loc_14007FD09
0x14007f918  mov     r14d, [rbx+0ECh]
0x14007f91f  lea     rbp, [rsi-1]
0x14007f923  add     rbp, [rax+18h]
0x14007f927  neg     esi
0x14007f929  movsxd  rax, esi
0x14007f92c  and     rbp, rax
0x14007f92f  mov     [rbx+0D0h], rbp
0x14007f936  mov     rsi, [rdx+50h]
0x14007f93a  mov     r15, [rdx+38h]
0x14007f93e  test    byte ptr [rsi+0Ah], 20h
0x14007f942  jz      short loc_14007F957
0x14007f944  mov     rcx, [rsi+18h]; BaseAddress
0x14007f948  mov     rdx, rsi; MemoryDescriptorList
0x14007f94b  call    cs:__imp_MmUnmapLockedPages
0x14007f952  nop     dword ptr [rax+rax+00h]
0x14007f957  mov     r9d, r14d; Length
0x14007f95a  mov     r8, rbp; VirtualAddress
0x14007f95d  mov     rdx, rsi; TargetMdl
0x14007f960  mov     rcx, r15; SourceMdl
0x14007f963  call    cs:__imp_IoBuildPartialMdl
0x14007f96a  nop     dword ptr [rax+rax+00h]
0x14007f96f  mov     rcx, [rbx+0A0h]
0x14007f976  mov     rax, [rcx+50h]
0x14007f97a  mov     [rbx+0C8h], rax
0x14007f981  mov     rcx, [rcx+50h]; MemoryDescriptorList
0x14007f985  test    byte ptr [rcx+0Ah], 5
0x14007f989  jz      short loc_14007F991
0x14007f98b  mov     rax, [rcx+18h]
0x14007f98f  jmp     short loc_14007F9B2
0x14007f991  mov     [rsp+0B8h+Priority], 40000010h; Priority
0x14007f999  xor     r9d, r9d; RequestedAddress
0x14007f99c  mov     r8d, r13d; CacheType
0x14007f99f  mov     [rsp+0B8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14007f9a4  xor     edx, edx; AccessMode
0x14007f9a6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007f9ad  nop     dword ptr [rax+rax+00h]
0x14007f9b2  mov     [rbx+0D0h], rax
0x14007f9b9  test    rax, rax
0x14007f9bc  jnz     loc_14007FA50
0x14007f9c2  mov     r9d, 84Dh
0x14007f9c8  jmp     loc_14007F90E
0x14007f9cd  mov     ecx, [rbx+0ECh]
0x14007f9d3  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14007f9da  nop     dword ptr [rax+rax+00h]
0x14007f9df  mov     [rbx+0A0h], rax
0x14007f9e6  test    rax, rax
0x14007f9e9  jnz     short loc_14007F9F6
0x14007f9eb  mov     r9d, 859h
0x14007f9f1  jmp     loc_14007F90E
0x14007f9f6  mov     rcx, [rax+38h]; MemoryDescriptorList
0x14007f9fa  test    byte ptr [rcx+0Ah], 5
0x14007f9fe  jz      short loc_14007FA06
0x14007fa00  mov     rax, [rcx+18h]
0x14007fa04  jmp     short loc_14007FA27
0x14007fa06  mov     [rsp+0B8h+Priority], 40000010h; Priority
0x14007fa0e  xor     r9d, r9d; RequestedAddress
0x14007fa11  mov     r8d, r13d; CacheType
0x14007fa14  mov     [rsp+0B8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14007fa19  xor     edx, edx; AccessMode
0x14007fa1b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007fa22  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
