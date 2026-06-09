# Smb2ExecuteRead

- ea: `0x14007f4c0`
- end: `0x14007fceb`
- name: `Smb2ExecuteRead`
- size: `2091`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140032e10`
- `0x140074860`

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
- `0x140077600`
- `0x14007f4c0`
- `0x14007fd00`
- `0x1400800c4`
- `0x140080364`
- `0x140086110`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007f956`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007f9cb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007f956`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007f9cb`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007f913`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007f913`
- `ntoskrnl!IofCallDriver` at `0x14007f84b`
- `ntoskrnl!IofCallDriver` at `0x14007fc51`
- `ntoskrnl!IofCallDriver` at `0x14007f84b`
- `ntoskrnl!IofCallDriver` at `0x14007fc51`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007f8fb`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007f8fb`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14007f89d`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14007f983`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14007f89d`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14007f983`
- `srvnet!SrvLibAuditForceAccess` at `0x14007f536`
- `srvnet!SrvLibAuditForceAccess` at `0x14007f536`

## string_xrefs

- `0x14007f5fb`: `Smb2ExecuteRead`
- `0x14007fa07`: `Smb2ExecuteRead`
- `0x14007fcb9`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

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
0x14007f4c0  push    rbx
0x14007f4c2  push    rbp
0x14007f4c3  push    rsi
0x14007f4c4  push    rdi
0x14007f4c5  push    r12
0x14007f4c7  push    r13
0x14007f4c9  push    r14
0x14007f4cb  push    r15
0x14007f4cd  sub     rsp, 78h
0x14007f4d1  mov     rbx, [rcx+230h]
0x14007f4d8  xor     r12d, r12d
0x14007f4db  mov     eax, cs:Smb2DirectDataPlacementSecurity
0x14007f4e1  mov     rdi, rcx
0x14007f4e4  mov     bpl, [rbx+108h]
0x14007f4eb  lea     r13d, [r12+1]
0x14007f4f0  cmp     eax, r13d
0x14007f4f3  jz      short loc_14007F509
0x14007f4f5  cmp     eax, 2
0x14007f4f8  jnz     short loc_14007F504
0x14007f4fa  mov     rax, [rbx+38h]
0x14007f4fe  cmp     [rax+5Ch], r12b
0x14007f502  jz      short loc_14007F509
0x14007f504  mov     sil, r12b
0x14007f507  jmp     short loc_14007F50C
0x14007f509  mov     sil, r13b
0x14007f50c  cmp     [rbx+50h], r12
0x14007f510  jz      short loc_14007F563
0x14007f512  mov     rax, [rbx+48h]
0x14007f516  cmp     [rax+0EAh], r12b
0x14007f51d  jnz     short loc_14007F556
0x14007f51f  mov     rcx, rbx
0x14007f522  call    Smb2ImpersonateWorkItem
0x14007f527  test    eax, eax
0x14007f529  js      short loc_14007F556
0x14007f52b  mov     rcx, [rbx+50h]
0x14007f52f  mov     edx, r13d
0x14007f532  mov     rcx, [rcx+58h]
0x14007f536  call    cs:__imp_SrvLibAuditForceAccess
0x14007f53d  nop     dword ptr [rax+rax+00h]
0x14007f542  test    eax, eax
0x14007f544  js      short loc_14007F551
0x14007f546  mov     rax, [rbx+48h]
0x14007f54a  mov     [rax+0EAh], r13b
0x14007f551  call    Smb2Revert
0x14007f556  mov     rcx, [rbx+50h]; P
0x14007f55a  call    Smb2DereferenceHandle
0x14007f55f  mov     [rbx+50h], r12
0x14007f563  test    sil, sil
0x14007f566  jz      short loc_14007F5A4
0x14007f568  cmp     [rbx+0D8h], r12
0x14007f56f  jz      short loc_14007F5A4
0x14007f571  mov     rax, [rbx+20h]
0x14007f575  mov     ecx, [rax+130h]
0x14007f57b  test    r13b, cl
0x14007f57e  jz      short loc_14007F586
0x14007f580  cmp     dword ptr [rbx+8], 2
0x14007f584  jge     short loc_14007F59D
0x14007f586  test    cl, 2
0x14007f589  jz      short loc_14007F5A4
0x14007f58b  cmp     [rbx+8], r13d
0x14007f58f  jl      short loc_14007F5A4
0x14007f591  mov     dword ptr [rbx+104h], 2
0x14007f59b  jmp     short loc_14007F5A4
0x14007f59d  mov     [rbx+104h], r13d
0x14007f5a4  mov     al, [rbx+108h]
0x14007f5aa  test    al, 0Ch
0x14007f5ac  jnz     loc_14007FC5F
0x14007f5b2  test    al, 20h
0x14007f5b4  jnz     loc_14007FCCC
0x14007f5ba  test    bpl, 10h
0x14007f5be  jnz     loc_14007F85C
0x14007f5c4  cmp     cs:Smb2AllowSequentialRead, r12b
0x14007f5cb  mov     esi, 103h
0x14007f5d0  jz      short loc_14007F5F4
0x14007f5d2  mov     rcx, [rbx+48h]
0x14007f5d6  mov     edx, [rcx+0C0h]
0x14007f5dc  test    dl, 4
0x14007f5df  jz      short loc_14007F5F4
0x14007f5e1  mov     rcx, rdi
0x14007f5e4  call    Smb2PreSequentialRead
0x14007f5e9  cmp     eax, esi
0x14007f5eb  jnz     short loc_14007F5F4
0x14007f5ed  mov     eax, esi
0x14007f5ef  jmp     loc_14007FCD9
0x14007f5f4  test    byte ptr [rbx+108h], 2
0x14007f5fb  lea     rbp, aSmb2executerea; "Smb2ExecuteRead"
0x14007f602  jnz     loc_14007F6E7
0x14007f608  mov     rax, [rbx+48h]
0x14007f60c  cmp     [rax+0EFh], r12b
0x14007f613  jz      loc_14007F6E7
0x14007f619  mov     rax, [rbx+60h]
0x14007f61d  mov     rcx, [rax+8]
0x14007f621  mov     r14, [rcx+50h]
0x14007f625  test    r14, r14
0x14007f628  jz      loc_14007F6E7
0x14007f62e  cmp     dword ptr [r14], 80h
0x14007f635  jbe     loc_14007F6E7
0x14007f63b  cmp     [r14+80h], r12
0x14007f642  jz      loc_14007F6E7
0x14007f648  mov     rax, [rdi+78h]
0x14007f64c  lea     r15, [rdi+248h]
0x14007f653  mov     r9, rbp
0x14007f656  mov     byte ptr [rsp+0B8h+BugCheckOnFailure], r13b
0x14007f65b  mov     r8d, 7D9h
0x14007f661  mov     dl, 2
0x14007f663  mov     rcx, r15
0x14007f666  mov     [rax+8], r12
0x14007f66a  call    SRV2_PERF_ENTER_EX
0x14007f66f  mov     rax, [rdi+78h]
0x14007f673  lea     rdx, [rbx+0C0h]
0x14007f67a  mov     rcx, [rbx+60h]
0x14007f67e  mov     r9d, [rbx+0FCh]
0x14007f685  mov     [rsp+0B8h+var_88], rcx
0x14007f68a  mov     rcx, [rbx+58h]
0x14007f68e  lea     r8, [rax+30h]
0x14007f692  add     rax, 8
0x14007f696  mov     qword ptr [rsp+0B8h+Priority], r8
0x14007f69b  mov     r8d, [rbx+0ECh]
0x14007f6a2  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x14007f6a7  mov     rax, [r14+80h]
0x14007f6ae  call    _guard_dispatch_icall
0x14007f6b3  xor     edx, edx
0x14007f6b5  mov     byte ptr [rsp+0B8h+BugCheckOnFailure], r13b
0x14007f6ba  mov     r9, rbp
0x14007f6bd  mov     rcx, r15
0x14007f6c0  test    al, al
0x14007f6c2  jz      short loc_14007F6DC
0x14007f6c4  mov     r8d, 7E7h
0x14007f6ca  call    SRV2_PERF_ENTER_EX
0x14007f6cf  mov     rcx, rdi
0x14007f6d2  call    Smb2ContinueMdlRead
0x14007f6d7  jmp     loc_14007F5ED
0x14007f6dc  mov     r8d, 7EFh
0x14007f6e2  call    SRV2_PERF_ENTER_EX
0x14007f6e7  mov     rax, [rbx+0C0h]
0x14007f6ee  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x14007f6f5  mov     r9, [rbx+60h]
0x14007f6f9  xor     edx, edx
0x14007f6fb  mov     r8, [rbx+58h]
0x14007f6ff  mov     [rsp+0B8h+var_50], r12b
0x14007f704  mov     [rsp+0B8h+var_58], r12b
0x14007f709  mov     [rsp+0B8h+var_60], rcx
0x14007f70e  mov     ecx, [rbx+0FCh]
0x14007f714  mov     [rsp+0B8h+var_68], ecx
0x14007f718  mov     rcx, rdi
0x14007f71b  mov     [rsp+0B8h+var_70], rax
0x14007f720  mov     rax, [rbx+0C8h]
0x14007f727  mov     [rsp+0B8h+var_78], rax
0x14007f72c  mov     eax, [rbx+0ECh]
0x14007f732  mov     dword ptr [rsp+0B8h+var_80], eax
0x14007f736  mov     [rsp+0B8h+var_88], r12
0x14007f73b  mov     byte ptr [rsp+0B8h+Priority], 2
0x14007f740  mov     byte ptr [rsp+0B8h+BugCheckOnFailure], 3
0x14007f745  call    Smb2BuildReadOrWriteRequest
0x14007f74a  mov     r14d, eax
0x14007f74d  test    eax, eax
0x14007f74f  jns     short loc_14007F7A6
0x14007f751  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007f758  lea     rcx, WPP_GLOBAL_Control
0x14007f75f  cmp     r10, rcx
0x14007f762  jz      short loc_14007F790
0x14007f764  test    dword ptr [r10+2Ch], 800000h
0x14007f76c  jz      short loc_14007F790
0x14007f76e  cmp     [r10+29h], r13b
0x14007f772  jb      short loc_14007F790
0x14007f774  mov     rcx, [r10+18h]
0x14007f778  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14007f77f  mov     edx, 22h ; '"'
0x14007f784  mov     [rsp+0B8h+BugCheckOnFailure], eax
0x14007f788  mov     r9, rdi
0x14007f78b  call    WPP_SF_qD
0x14007f790  mov     rcx, rdi
0x14007f793  call    Smb2SequentialReadComplete
0x14007f798  mov     r9d, 80Dh
0x14007f79e  mov     edx, r14d
0x14007f7a1  jmp     loc_14007FCB9
0x14007f7a6  mov     dl, [rbx+108h]
0x14007f7ac  mov     rcx, rdi
0x14007f7af  shr     dl, 2
0x14007f7b2  and     dl, r13b
0x14007f7b5  call    Srv2MarkWorkItemCancellable
0x14007f7ba  test    eax, eax
0x14007f7bc  jns     short loc_14007F811
0x14007f7be  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007f7c5  lea     rcx, WPP_GLOBAL_Control
0x14007f7cc  cmp     r10, rcx
0x14007f7cf  jz      short loc_14007F7F9
0x14007f7d1  test    dword ptr [r10+2Ch], 800000h
0x14007f7d9  jz      short loc_14007F7F9
0x14007f7db  cmp     [r10+29h], r13b
0x14007f7df  jb      short loc_14007F7F9
0x14007f7e1  mov     rcx, [r10+18h]
0x14007f7e5  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14007f7ec  mov     edx, 23h ; '#'
0x14007f7f1  mov     r9, rdi
0x14007f7f4  call    WPP_SF_q
0x14007f7f9  mov     rcx, rdi
0x14007f7fc  call    Smb2SequentialReadComplete
0x14007f801  mov     r9d, 818h
0x14007f807  mov     edx, 0C0000120h
0x14007f80c  jmp     loc_14007FCB9
0x14007f811  mov     rax, [rbx+48h]
0x14007f815  lea     rcx, [rdi+248h]
0x14007f81c  mov     r9, rbp
0x14007f81f  mov     byte ptr [rsp+0B8h+BugCheckOnFailure], r13b
0x14007f824  mov     r8d, 822h
0x14007f82a  mov     dl, 3
0x14007f82c  mov     [rax+0EFh], r13b
0x14007f833  lea     rax, Smb2ContinueMdlRead
0x14007f83a  mov     [rdi+30h], rax
0x14007f83e  call    SRV2_PERF_ENTER_EX
0x14007f843  mov     rdx, [rdi+78h]; Irp
0x14007f847  mov     rcx, [rbx+60h]; DeviceObject
0x14007f84b  call    cs:__imp_IofCallDriver
0x14007f852  nop     dword ptr [rax+rax+00h]
0x14007f857  jmp     loc_14007F5ED
0x14007f85c  mov     rax, [rbx+60h]
0x14007f860  mov     esi, [rax+98h]
0x14007f866  cmp     esi, r13d
0x14007f869  jbe     loc_14007F97D
0x14007f86f  mov     eax, [rbx+0ECh]
0x14007f875  test    eax, 0FFFh
0x14007f87a  jz      loc_14007F97D
0x14007f880  lea     ecx, [rax+rsi]
0x14007f883  mov     [rbx+100h], esi
0x14007f889  cmp     ecx, eax
0x14007f88b  jnb     short loc_14007F89D
0x14007f88d  mov     r9d, 83Bh
0x14007f893  mov     edx, 0C000000Dh
0x14007f898  jmp     loc_14007FCB9
0x14007f89d  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14007f8a4  nop     dword ptr [rax+rax+00h]
0x14007f8a9  mov     [rbx+0A0h], rax
0x14007f8b0  mov     rdx, rax
0x14007f8b3  test    rax, rax
0x14007f8b6  jnz     short loc_14007F8C8
0x14007f8b8  mov     r9d, 842h
0x14007f8be  mov     edx, 0C0000205h
0x14007f8c3  jmp     loc_14007FCB9
0x14007f8c8  mov     r14d, [rbx+0ECh]
0x14007f8cf  lea     rbp, [rsi-1]
0x14007f8d3  add     rbp, [rax+18h]
0x14007f8d7  neg     esi
0x14007f8d9  movsxd  rax, esi
0x14007f8dc  and     rbp, rax
0x14007f8df  mov     [rbx+0D0h], rbp
0x14007f8e6  mov     rsi, [rdx+50h]
0x14007f8ea  mov     r15, [rdx+38h]
0x14007f8ee  test    byte ptr [rsi+0Ah], 20h
0x14007f8f2  jz      short loc_14007F907
0x14007f8f4  mov     rcx, [rsi+18h]; BaseAddress
0x14007f8f8  mov     rdx, rsi; MemoryDescriptorList
0x14007f8fb  call    cs:__imp_MmUnmapLockedPages
0x14007f902  nop     dword ptr [rax+rax+00h]
0x14007f907  mov     r9d, r14d; Length
0x14007f90a  mov     r8, rbp; VirtualAddress
0x14007f90d  mov     rdx, rsi; TargetMdl
0x14007f910  mov     rcx, r15; SourceMdl
0x14007f913  call    cs:__imp_IoBuildPartialMdl
0x14007f91a  nop     dword ptr [rax+rax+00h]
0x14007f91f  mov     rcx, [rbx+0A0h]
0x14007f926  mov     rax, [rcx+50h]
0x14007f92a  mov     [rbx+0C8h], rax
0x14007f931  mov     rcx, [rcx+50h]; MemoryDescriptorList
0x14007f935  test    byte ptr [rcx+0Ah], 5
0x14007f939  jz      short loc_14007F941
0x14007f93b  mov     rax, [rcx+18h]
0x14007f93f  jmp     short loc_14007F962
0x14007f941  mov     [rsp+0B8h+Priority], 40000010h; Priority
0x14007f949  xor     r9d, r9d; RequestedAddress
0x14007f94c  mov     r8d, r13d; CacheType
0x14007f94f  mov     [rsp+0B8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14007f954  xor     edx, edx; AccessMode
0x14007f956  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007f95d  nop     dword ptr [rax+rax+00h]
0x14007f962  mov     [rbx+0D0h], rax
0x14007f969  test    rax, rax
0x14007f96c  jnz     loc_14007FA00
0x14007f972  mov     r9d, 84Dh
0x14007f978  jmp     loc_14007F8BE
0x14007f97d  mov     ecx, [rbx+0ECh]
0x14007f983  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14007f98a  nop     dword ptr [rax+rax+00h]
0x14007f98f  mov     [rbx+0A0h], rax
0x14007f996  test    rax, rax
0x14007f999  jnz     short loc_14007F9A6
0x14007f99b  mov     r9d, 859h
0x14007f9a1  jmp     loc_14007F8BE
0x14007f9a6  mov     rcx, [rax+38h]; MemoryDescriptorList
0x14007f9aa  test    byte ptr [rcx+0Ah], 5
0x14007f9ae  jz      short loc_14007F9B6
0x14007f9b0  mov     rax, [rcx+18h]
0x14007f9b4  jmp     short loc_14007F9D7
0x14007f9b6  mov     [rsp+0B8h+Priority], 40000010h; Priority
0x14007f9be  xor     r9d, r9d; RequestedAddress
0x14007f9c1  mov     r8d, r13d; CacheType
0x14007f9c4  mov     [rsp+0B8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14007f9c9  xor     edx, edx; AccessMode
0x14007f9cb  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007f9d2  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
