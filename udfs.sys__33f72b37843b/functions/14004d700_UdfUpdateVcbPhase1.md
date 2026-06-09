# UdfUpdateVcbPhase1

- ea: `0x14004d700`
- end: `0x14004e00d`
- name: `UdfUpdateVcbPhase1`
- size: `2317`
- prototype: `__int64 __fastcall(int, PVOID DeferredContext)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140049f80`

## callees

- `0x14000c0ec`
- `0x14000c8d0`
- `0x14000cad4`
- `0x140010c5c`
- `0x140014cb8`
- `0x14001c080`
- `0x14003dec8`
- `0x14003f360`
- `0x140048c24`
- `0x14004cf74`
- `0x14004d700`
- `0x14004f8ac`
- `0x14004fc70`

## import_xrefs

- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14004db52`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14004dedc`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14004db52`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14004dedc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004d79a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004d83c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004d99e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004d9f5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004dcdd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004dd33`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004d79a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004d83c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004d99e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004d9f5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004dcdd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004dd33`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004d8b5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004d94a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004da6a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004da80`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004ddcc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004ddea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004dfed`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005a586`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004d8b5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004d94a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004da6a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004da80`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004ddcc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004ddea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004dfed`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005a586`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004dac7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004de6a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004dac7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004de6a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004db9c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004df15`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005a55a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004db9c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004df15`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005a55a`
- `ntoskrnl!KeInitializeTimer` at `0x14004dc29`
- `ntoskrnl!KeInitializeTimer` at `0x14004dc29`
- `ntoskrnl!KeInitializeDpc` at `0x14004dc46`
- `ntoskrnl!KeInitializeDpc` at `0x14004dc46`

## pseudocode

```c
void __fastcall UdfUpdateVcbPhase1(__int64 a1, char *DeferredContext, __int64 a3)
{
  LONGLONG v6; // rdi
  _QWORD *Scb; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r14
  __int64 v14; // rcx
  unsigned int i; // r8d
  __int64 v16; // rdx
  __int64 v17; // rax
  unsigned int v18; // edx
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // edx
  __int64 v22; // rdi
  __int64 v23; // r14
  _QWORD *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rax
  _QWORD v31[19]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v32; // [rsp+108h] [rbp+20h]
  struct _KTHREAD *CurrentThread; // [rsp+108h] [rbp+20h]
  struct _KTHREAD *v34; // [rsp+108h] [rbp+20h]

  memset(v31, 0, 0x60u);
  v6 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
  {
    WPP_SF_qq(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      39,
      WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids,
      DeferredContext,
      a3);
  }
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1648));
  *((_QWORD *)DeferredContext + 213) = KeGetCurrentThread();
  LODWORD(v32) = *(_DWORD *)(a3 + 404);
  HIDWORD(v32) = *(unsigned __int16 *)(a3 + 408) | 0x80000000;
  Scb = UdfCreateScb(a1, v32, 0x933u, 0, 0);
  *((_QWORD *)DeferredContext + 36) = Scb;
  *((_DWORD *)Scb + 44) = *(_DWORD *)(a3 + 400) & 0x3FFFFFFF;
  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 36) + 136LL) + 16LL) = *((_QWORD *)DeferredContext + 36);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1584));
  *((_QWORD *)DeferredContext + 205) = KeGetCurrentThread();
  ++*(_DWORD *)(*((_QWORD *)DeferredContext + 36) + 204LL);
  ++*(_DWORD *)(*((_QWORD *)DeferredContext + 36) + 208LL);
  v8 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 36) + 136LL) + 8LL);
  ++*(_DWORD *)(v8 + 256);
  v9 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 36) + 136LL) + 8LL);
  ++*(_DWORD *)(v9 + 260);
  *((_QWORD *)DeferredContext + 205) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1584));
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 36) + 136LL) + 76LL) |= 1u;
  *((_DWORD *)DeferredContext + 354) = *(_DWORD *)(a3 + 12);
  UdfInitializeIcbContextFromScb(a1, (__int64)v31, *((_QWORD *)DeferredContext + 36));
  UdfLookupActiveIcb(a1, v31, *(unsigned int *)(*((_QWORD *)DeferredContext + 36) + 176LL));
  UdfInitializeScbFromIcbContext(a1, *((_QWORD *)DeferredContext + 36), v31, 0);
  UdfCleanupIcbContext(a1, v31);
  *((_QWORD *)DeferredContext + 213) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1648));
  UdfCreateInternalStream(a1, (__int64)DeferredContext, *((struct _CC_FILE_SIZES **)DeferredContext + 36), 0);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 40, WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids);
  }
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1648));
  *((_QWORD *)DeferredContext + 213) = KeGetCurrentThread();
  v10 = UdfCreateScb(a1, 0, 0x934u, 0, 0);
  *((_QWORD *)DeferredContext + 35) = v10;
  *(_QWORD *)(v10[17] + 16LL) = v10;
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1584));
  *((_QWORD *)DeferredContext + 205) = KeGetCurrentThread();
  ++*(_DWORD *)(*((_QWORD *)DeferredContext + 35) + 204LL);
  ++*(_DWORD *)(*((_QWORD *)DeferredContext + 35) + 208LL);
  v11 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 35) + 136LL) + 8LL);
  ++*(_DWORD *)(v11 + 256);
  v12 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 35) + 136LL) + 8LL);
  ++*(_DWORD *)(v12 + 260);
  *((_QWORD *)DeferredContext + 205) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1584));
  *((_QWORD *)DeferredContext + 213) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1648));
  v13 = *((_QWORD *)DeferredContext + 35);
  CurrentThread = KeGetCurrentThread();
  v14 = *(_QWORD *)(v13 + 136);
  if ( CurrentThread != *(struct _KTHREAD **)(v14 + 64) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v14 + 80) + 216LL));
    *(_QWORD *)(*(_QWORD *)(v13 + 136) + 64LL) = CurrentThread;
  }
  ++*(_DWORD *)(*(_QWORD *)(v13 + 136) + 72LL);
  for ( i = 0; ; ++i )
  {
    v16 = *((_QWORD *)DeferredContext + 2);
    if ( i >= *(unsigned __int16 *)(v16 + 4) )
      break;
    v17 = 56LL * i;
    if ( *(_DWORD *)(v17 + v16 + 96) == 1 )
    {
      v18 = *(_DWORD *)(v17 + v16 + 108) + *(_DWORD *)(v17 + v16 + 104);
      if ( v18 > (unsigned int)v6 )
        v6 = v18;
    }
  }
  UdfInitializeScbMcb(1, v13, 0);
  FsRtlAddLargeMcbEntry((PLARGE_MCB)(v13 + 232), 0, 0, v6);
  *(_QWORD *)(v13 + 32) += v6 << *((_DWORD *)DeferredContext + 18);
  v19 = *(_QWORD *)(v13 + 32);
  *(_QWORD *)(v13 + 40) = v19;
  *(_QWORD *)(v13 + 24) = v19;
  --*(_DWORD *)(*(_QWORD *)(v13 + 136) + 72LL);
  v20 = *(_QWORD *)(v13 + 136);
  if ( !*(_DWORD *)(v20 + 72) )
  {
    *(_QWORD *)(v20 + 64) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v13 + 136) + 80LL) + 216LL));
  }
  *(_DWORD *)(v13 + 212) |= 0x200001u;
  *(_QWORD *)(*((_QWORD *)DeferredContext + 35) + 8LL) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 35)
                                                                               + 136LL)
                                                                   + 80LL)
                                                       + 8LL;
  *(_QWORD *)(*((_QWORD *)DeferredContext + 35) + 16LL) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 35)
                                                                                + 136LL)
                                                                    + 80LL)
                                                        + 112LL;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 41, WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids);
  }
  v21 = *((_DWORD *)DeferredContext + 12);
  if ( (v21 & 0x4000) == 0 )
  {
    KeInitializeTimer((PKTIMER)DeferredContext + 30);
    KeInitializeDpc((PRKDPC)DeferredContext + 29, UdfCleanVolumeDpcFn, DeferredContext);
    *((_DWORD *)DeferredContext + 12) |= 0x400000u;
    v21 = *((_DWORD *)DeferredContext + 12);
  }
  if ( (v21 & 0x10) == 0 )
  {
    v22 = *((_QWORD *)DeferredContext + 2);
    if ( (*(_WORD *)(v22 + 6) & 2) == 0 && (v21 & 0x20000000) == 0 )
    {
      v23 = 56LL * *(unsigned __int16 *)(v22 + 92);
      if ( (unsigned int)(8 * *(_DWORD *)(v23 + v22 + 116)) >= *((_DWORD *)DeferredContext + 166) )
      {
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1648));
        *((_QWORD *)DeferredContext + 213) = KeGetCurrentThread();
        v24 = UdfCreateScb(a1, 0, 0x933u, 0, 0);
        *((_QWORD *)DeferredContext + 37) = v24;
        *(_QWORD *)(v24[17] + 16LL) = v24;
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1584));
        *((_QWORD *)DeferredContext + 205) = KeGetCurrentThread();
        ++*(_DWORD *)(*((_QWORD *)DeferredContext + 37) + 204LL);
        ++*(_DWORD *)(*((_QWORD *)DeferredContext + 37) + 208LL);
        v25 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 37) + 136LL) + 8LL);
        ++*(_DWORD *)(v25 + 256);
        v26 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 37) + 136LL) + 8LL);
        ++*(_DWORD *)(v26 + 260);
        *(_DWORD *)(*(_QWORD *)(a1 + 16) + 264LL) += 2;
        *(_DWORD *)(*(_QWORD *)(a1 + 16) + 256LL) += 2;
        ++*(_DWORD *)(*(_QWORD *)(a1 + 16) + 268LL);
        *((_QWORD *)DeferredContext + 205) = 0;
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1584));
        *((_QWORD *)DeferredContext + 213) = 0;
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeferredContext + 1648));
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 37) + 136LL) + 76LL) |= 1u;
        v27 = *(_DWORD *)(v23 + v22 + 116) & 0x3FFFFFFF;
        *(_QWORD *)(*((_QWORD *)DeferredContext + 37) + 24LL) = v27;
        *(_QWORD *)(*((_QWORD *)DeferredContext + 37) + 40LL) = v27;
        *(_QWORD *)(*((_QWORD *)DeferredContext + 37) + 32LL) = v27;
        v28 = *((_QWORD *)DeferredContext + 37);
        v34 = KeGetCurrentThread();
        v29 = *(_QWORD *)(v28 + 136);
        if ( v34 != *(struct _KTHREAD **)(v29 + 64) )
        {
          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v29 + 80) + 216LL));
          *(_QWORD *)(*(_QWORD *)(v28 + 136) + 64LL) = v34;
        }
        ++*(_DWORD *)(*(_QWORD *)(v28 + 136) + 72LL);
        UdfInitializeScbMcb(1, *((_QWORD *)DeferredContext + 37), 0);
        FsRtlAddLargeMcbEntry(
          (PLARGE_MCB)(v28 + 232),
          0,
          (unsigned int)(*(_DWORD *)(v23 + v22 + 120)
                       + *(_DWORD *)(56LL * *(unsigned __int16 *)(*((_QWORD *)DeferredContext + 2) + 92LL)
                                   + *((_QWORD *)DeferredContext + 2)
                                   + 104)),
          (unsigned __int64)(*(_DWORD *)(v23 + v22 + 116) & 0x3FFFFFFF) >> *((_DWORD *)DeferredContext + 18));
        --*(_DWORD *)(*(_QWORD *)(v28 + 136) + 72LL);
        v30 = *(_QWORD *)(v28 + 136);
        if ( !*(_DWORD *)(v30 + 72) )
        {
          *(_QWORD *)(v30 + 64) = 0;
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v28 + 136) + 80LL) + 216LL));
        }
        *(_QWORD *)(*((_QWORD *)DeferredContext + 37) + 8LL) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 37)
                                                                                     + 136LL)
                                                                         + 80LL)
                                                             + 8LL;
        *(_QWORD *)(*((_QWORD *)DeferredContext + 37) + 16LL) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 37)
                                                                                      + 136LL)
                                                                          + 80LL)
                                                              + 112LL;
        *(_DWORD *)(*((_QWORD *)DeferredContext + 37) + 212LL) |= 1u;
        UdfCreateInternalStream(
          a1,
          (__int64)DeferredContext,
          *((struct _CC_FILE_SIZES **)DeferredContext + 37),
          (UNICODE_STRING *)&qword_1400250C0);
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            43,
            WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids);
        }
        UdfInitializeAllocationSupport(a1, (__int64)DeferredContext);
        UdfInitializeUniqueIdTable(a1);
      }
      else
      {
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            42,
            WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids);
        }
        *((_DWORD *)DeferredContext + 12) |= 0x10u;
      }
    }
  }
}

```

## disassembly

```asm
0x14004d700  mov     [rsp+arg_10], r8
0x14004d705  mov     [rsp+arg_8], rdx
0x14004d70a  mov     [rsp+arg_0], rcx
0x14004d70f  push    rbx
0x14004d710  push    rsi
0x14004d711  push    rdi
0x14004d712  push    r12
0x14004d714  push    r13
0x14004d716  push    r14
0x14004d718  push    r15
0x14004d71a  sub     rsp, 0B0h
0x14004d721  mov     rbx, r8
0x14004d724  mov     rsi, rdx
0x14004d727  mov     r13, rcx
0x14004d72a  xor     edx, edx; Val
0x14004d72c  lea     r8d, [rdx+60h]; Size
0x14004d730  lea     rcx, [rsp+0E8h+var_98]; void *
0x14004d735  call    memset
0x14004d73a  xor     r12d, r12d
0x14004d73d  mov     [rsp+0E8h+var_B0], r12
0x14004d742  mov     [rsp+0E8h+var_B7], r12b
0x14004d747  mov     [rsp+0E8h+var_B6], r12b
0x14004d74c  mov     edi, r12d
0x14004d74f  lea     rax, WPP_GLOBAL_Control
0x14004d756  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d75d  mov     r15d, 40000h
0x14004d763  cmp     rcx, rax
0x14004d766  jz      short loc_14004D78B
0x14004d768  test    [rcx+2Ch], r15d
0x14004d76c  jz      short loc_14004D78B
0x14004d76e  lea     edx, [r12+27h]
0x14004d773  mov     [rsp+0E8h+var_C8], rbx
0x14004d778  mov     r9, rsi
0x14004d77b  lea     r8, WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids
0x14004d782  mov     rcx, [rcx+18h]
0x14004d786  call    WPP_SF_qq
0x14004d78b  mov     [rsp+0E8h+var_B8], r12b
0x14004d790  lea     r14, [rsi+670h]
0x14004d797  mov     rcx, r14; FastMutex
0x14004d79a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14004d7a1  nop     dword ptr [rax+rax+00h]
0x14004d7a6  mov     rax, gs:188h
0x14004d7af  mov     [rsi+6A8h], rax
0x14004d7b6  mov     [rsp+0E8h+var_B8], 1
0x14004d7bb  mov     [rsp+0E8h+arg_18], r12
0x14004d7c3  mov     eax, [rbx+194h]
0x14004d7c9  mov     dword ptr [rsp+0E8h+arg_18], eax
0x14004d7d0  movzx   eax, word ptr [rbx+198h]
0x14004d7d7  mov     dword ptr [rsp+0E8h+arg_18+4], eax
0x14004d7de  bts     eax, 1Fh
0x14004d7e2  mov     dword ptr [rsp+0E8h+arg_18+4], eax
0x14004d7e9  mov     r8d, 933h
0x14004d7ef  mov     [rsp+0E8h+var_C8], r12
0x14004d7f4  xor     r9d, r9d
0x14004d7f7  mov     rdx, [rsp+0E8h+arg_18]
0x14004d7ff  mov     rcx, r13
0x14004d802  call    UdfCreateScb
0x14004d807  mov     [rsi+120h], rax
0x14004d80e  mov     ecx, [rbx+190h]
0x14004d814  and     ecx, 3FFFFFFFh
0x14004d81a  mov     [rax+0B0h], ecx
0x14004d820  mov     rcx, [rsi+120h]
0x14004d827  mov     rax, [rcx+88h]
0x14004d82e  mov     [rax+10h], rcx
0x14004d832  lea     r12, [rsi+630h]
0x14004d839  mov     rcx, r12; FastMutex
0x14004d83c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14004d843  nop     dword ptr [rax+rax+00h]
0x14004d848  mov     rax, gs:188h
0x14004d851  mov     [rsi+668h], rax
0x14004d858  mov     rax, [rsi+120h]
0x14004d85f  mov     edx, 1
0x14004d864  add     [rax+0CCh], edx
0x14004d86a  mov     rax, [rsi+120h]
0x14004d871  add     [rax+0D0h], edx
0x14004d877  mov     rax, [rsi+120h]
0x14004d87e  mov     rcx, [rax+88h]
0x14004d885  mov     rax, [rcx+8]
0x14004d889  add     [rax+100h], edx
0x14004d88f  mov     rax, [rsi+120h]
0x14004d896  mov     rcx, [rax+88h]
0x14004d89d  mov     rax, [rcx+8]
0x14004d8a1  add     [rax+104h], edx
0x14004d8a7  mov     qword ptr [rsi+668h], 0
0x14004d8b2  mov     rcx, r12; FastMutex
0x14004d8b5  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14004d8bc  nop     dword ptr [rax+rax+00h]
0x14004d8c1  mov     rax, [rsi+120h]
0x14004d8c8  mov     rcx, [rax+88h]
0x14004d8cf  mov     r8d, 1
0x14004d8d5  or      [rcx+4Ch], r8d
0x14004d8d9  mov     eax, [rbx+0Ch]
0x14004d8dc  mov     [rsi+588h], eax
0x14004d8e2  mov     r8, [rsi+120h]
0x14004d8e9  lea     rdx, [rsp+0E8h+var_98]
0x14004d8ee  mov     rcx, r13
0x14004d8f1  call    UdfInitializeIcbContextFromScb
0x14004d8f6  mov     [rsp+0E8h+var_B6], 1
0x14004d8fb  mov     r8, [rsi+120h]
0x14004d902  mov     r8d, [r8+0B0h]
0x14004d909  lea     rdx, [rsp+0E8h+var_98]
0x14004d90e  mov     rcx, r13
0x14004d911  call    UdfLookupActiveIcb
0x14004d916  xor     r9d, r9d
0x14004d919  lea     r8, [rsp+0E8h+var_98]
0x14004d91e  mov     rdx, [rsi+120h]
0x14004d925  mov     rcx, r13
0x14004d928  call    UdfInitializeScbFromIcbContext
0x14004d92d  lea     rdx, [rsp+0E8h+var_98]
0x14004d932  mov     rcx, r13
0x14004d935  call    UdfCleanupIcbContext
0x14004d93a  xor     ebx, ebx
0x14004d93c  mov     [rsp+0E8h+var_B6], bl
0x14004d940  mov     [rsi+6A8h], rbx
0x14004d947  mov     rcx, r14; FastMutex
0x14004d94a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14004d951  nop     dword ptr [rax+rax+00h]
0x14004d956  mov     [rsp+0E8h+var_B8], bl
0x14004d95a  xor     r9d, r9d
0x14004d95d  mov     r8, [rsi+120h]
0x14004d964  mov     rdx, rsi
0x14004d967  mov     rcx, r13
0x14004d96a  call    UdfCreateInternalStream
0x14004d96f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d976  lea     rax, WPP_GLOBAL_Control
0x14004d97d  cmp     rcx, rax
0x14004d980  jz      short loc_14004D99B
0x14004d982  test    [rcx+2Ch], r15d
0x14004d986  jz      short loc_14004D99B
0x14004d988  lea     edx, [rbx+28h]
0x14004d98b  lea     r8, WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids
0x14004d992  mov     rcx, [rcx+18h]
0x14004d996  call    WPP_SF_
0x14004d99b  mov     rcx, r14; FastMutex
0x14004d99e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14004d9a5  nop     dword ptr [rax+rax+00h]
0x14004d9aa  mov     rax, gs:188h
0x14004d9b3  mov     [rsi+6A8h], rax
0x14004d9ba  mov     [rsp+0E8h+var_B8], 1
0x14004d9bf  mov     [rsp+0E8h+arg_18], rbx
0x14004d9c7  mov     r8d, 934h
0x14004d9cd  mov     [rsp+0E8h+var_C8], rbx
0x14004d9d2  xor     r9d, r9d
0x14004d9d5  mov     rdx, rbx
0x14004d9d8  mov     rcx, r13
0x14004d9db  call    UdfCreateScb
0x14004d9e0  mov     [rsi+118h], rax
0x14004d9e7  mov     rcx, [rax+88h]
0x14004d9ee  mov     [rcx+10h], rax
0x14004d9f2  mov     rcx, r12; FastMutex
0x14004d9f5  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14004d9fc  nop     dword ptr [rax+rax+00h]
0x14004da01  mov     rax, gs:188h
0x14004da0a  mov     [rsi+668h], rax
0x14004da11  mov     rax, [rsi+118h]
0x14004da18  mov     edx, 1
0x14004da1d  add     [rax+0CCh], edx
0x14004da23  mov     rax, [rsi+118h]
0x14004da2a  add     [rax+0D0h], edx
0x14004da30  mov     rax, [rsi+118h]
0x14004da37  mov     rcx, [rax+88h]
0x14004da3e  mov     rax, [rcx+8]
0x14004da42  add     [rax+100h], edx
0x14004da48  mov     rax, [rsi+118h]
0x14004da4f  mov     rcx, [rax+88h]
0x14004da56  mov     rax, [rcx+8]
0x14004da5a  add     [rax+104h], edx
0x14004da60  mov     [rsi+668h], rbx
0x14004da67  mov     rcx, r12; FastMutex
0x14004da6a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14004da71  nop     dword ptr [rax+rax+00h]
0x14004da76  mov     [rsi+6A8h], rbx
0x14004da7d  mov     rcx, r14; FastMutex
0x14004da80  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14004da87  nop     dword ptr [rax+rax+00h]
0x14004da8c  mov     [rsp+0E8h+var_B8], bl
0x14004da90  mov     r14, [rsi+118h]
0x14004da97  mov     [rsp+0E8h+var_B0], r14
0x14004da9c  mov     rax, gs:188h
0x14004daa5  mov     [rsp+0E8h+arg_18], rax
0x14004daad  mov     rcx, [r14+88h]
0x14004dab4  mov     r12d, 0D8h
0x14004daba  cmp     rax, [rcx+40h]
0x14004dabe  jz      short loc_14004DAE6
0x14004dac0  mov     rcx, [rcx+50h]
0x14004dac4  add     rcx, r12; FastMutex
0x14004dac7  call    cs:__imp_ExAcquireFastMutex
0x14004dace  nop     dword ptr [rax+rax+00h]
0x14004dad3  mov     rax, [r14+88h]
0x14004dada  mov     rcx, [rsp+0E8h+arg_18]
0x14004dae2  mov     [rax+40h], rcx
0x14004dae6  mov     rax, [r14+88h]
0x14004daed  mov     ecx, 1
0x14004daf2  add     [rax+48h], ecx
0x14004daf5  mov     [rsp+0E8h+var_B7], cl
0x14004daf9  xor     r8d, r8d
0x14004dafc  mov     [rsp+0E8h+var_B4], r8d
0x14004db01  mov     rdx, [rsi+10h]
0x14004db05  movzx   eax, word ptr [rdx+4]
0x14004db09  cmp     r8d, eax
0x14004db0c  jnb     short loc_14004DB38
0x14004db0e  mov     eax, r8d
0x14004db11  imul    rax, 38h ; '8'
0x14004db15  cmp     [rax+rdx+60h], ecx
0x14004db19  jnz     short loc_14004DB33
0x14004db1b  mov     ecx, [rax+rdx+6Ch]
0x14004db1f  mov     edx, [rax+rdx+68h]
0x14004db23  add     edx, ecx
0x14004db25  cmp     edx, edi
0x14004db27  cmova   edi, edx
0x14004db2a  mov     [rsp+0E8h+var_A8], edi
0x14004db2e  mov     ecx, 1
0x14004db33  add     r8d, ecx
0x14004db36  jmp     short loc_14004DAFC
0x14004db38  xor     r8d, r8d
0x14004db3b  mov     rdx, r14
0x14004db3e  call    UdfInitializeScbMcb
0x14004db43  lea     rcx, [r14+0E8h]; Mcb
0x14004db4a  mov     r9, rdi; SectorCount
0x14004db4d  xor     r8d, r8d; Lbn
0x14004db50  xor     edx, edx; Vbn
0x14004db52  call    cs:__imp_FsRtlAddLargeMcbEntry
0x14004db59  nop     dword ptr [rax+rax+00h]
0x14004db5e  mov     ecx, [rsi+48h]
0x14004db61  shl     rdi, cl
0x14004db64  add     [r14+20h], rdi
0x14004db68  mov     rax, [r14+20h]
0x14004db6c  mov     [r14+28h], rax
0x14004db70  mov     [r14+18h], rax
0x14004db74  mov     rax, [r14+88h]
0x14004db7b  dec     dword ptr [rax+48h]
0x14004db7e  mov     rax, [r14+88h]
0x14004db85  cmp     [rax+48h], ebx
0x14004db88  jnz     short loc_14004DBA8
0x14004db8a  mov     [rax+40h], rbx
0x14004db8e  mov     rax, [r14+88h]
0x14004db95  mov     rcx, [rax+50h]
0x14004db99  add     rcx, r12; FastMutex
0x14004db9c  call    cs:__imp_ExReleaseFastMutex
0x14004dba3  nop     dword ptr [rax+rax+00h]
0x14004dba8  mov     [rsp+0E8h+var_B7], bl
0x14004dbac  or      dword ptr [r14+0D4h], 200001h
0x14004dbb7  mov     rdx, [rsi+118h]
0x14004dbbe  mov     rax, [rdx+88h]
0x14004dbc5  mov     rcx, [rax+50h]
0x14004dbc9  add     rcx, 8
0x14004dbcd  mov     [rdx+8], rcx
0x14004dbd1  mov     rdx, [rsi+118h]
0x14004dbd8  mov     rax, [rdx+88h]
0x14004dbdf  mov     rcx, [rax+50h]
0x14004dbe3  add     rcx, 70h ; 'p'
0x14004dbe7  mov     [rdx+10h], rcx
0x14004dbeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dbf2  lea     rax, WPP_GLOBAL_Control
0x14004dbf9  cmp     rcx, rax
0x14004dbfc  jz      short loc_14004DC19
0x14004dbfe  test    [rcx+2Ch], r15d
0x14004dc02  jz      short loc_14004DC19
0x14004dc04  mov     edx, 29h ; ')'
0x14004dc09  lea     r8, WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids
0x14004dc10  mov     rcx, [rcx+18h]
0x14004dc14  call    WPP_SF_
0x14004dc19  mov     edx, [rsi+30h]
0x14004dc1c  bt      edx, 0Eh
0x14004dc20  jb      short loc_14004DC5A
0x14004dc22  lea     rcx, [rsi+780h]; Timer
0x14004dc29  call    cs:__imp_KeInitializeTimer
0x14004dc30  nop     dword ptr [rax+rax+00h]
0x14004dc35  lea     rcx, [rsi+740h]; Dpc
0x14004dc3c  mov     r8, rsi; DeferredContext
0x14004dc3f  lea     rdx, UdfCleanVolumeDpcFn; DeferredRoutine
0x14004dc46  call    cs:__imp_KeInitializeDpc
0x14004dc4d  nop     dword ptr [rax+rax+00h]
0x14004dc52  bts     dword ptr [rsi+30h], 16h
0x14004dc57  mov     edx, [rsi+30h]
0x14004dc5a  test    dl, 10h
0x14004dc5d  jnz     loc_14004DFD4
0x14004dc63  mov     rdi, [rsi+10h]
0x14004dc67  movzx   eax, word ptr [rdi+6]
0x14004dc6b  mov     r8d, 1
0x14004dc71  bt      ax, r8w
0x14004dc76  setnb   cl
0x14004dc79  bt      edx, 1Dh
0x14004dc7d  setnb   al
0x14004dc80  test    al, cl
0x14004dc82  jz      loc_14004DFD4
0x14004dc88  movzx   eax, word ptr [rdi+5Ch]
0x14004dc8c  imul    r14, rax, 38h ; '8'
0x14004dc90  mov     eax, [r14+rdi+74h]
0x14004dc95  shl     eax, 3
0x14004dc98  cmp     eax, [rsi+298h]
0x14004dc9e  jnb     short loc_14004DCD6
0x14004dca0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dca7  lea     rax, WPP_GLOBAL_Control
0x14004dcae  cmp     rcx, rax
0x14004dcb1  jz      short loc_14004DCCD
0x14004dcb3  test    [rcx+2Ch], r15d
0x14004dcb7  jz      short loc_14004DCCD
0x14004dcb9  lea     edx, [r8+29h]
0x14004dcbd  lea     r8, WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids
  ... truncated ...
```
