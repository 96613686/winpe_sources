# ScShutdownServices(void)

- ea: `0x140002dc0`
- end: `0x140002ff2`
- name: `?ScShutdownServices@@YAXXZ`
- size: `562`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140038d98`

## callees

- `0x140002890`
- `0x140002dc0`
- `0x140003310`
- `0x140003e54`
- `0x140004c58`
- `0x140007130`
- `0x140092060`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002ea5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002ee9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002ea5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140002ee9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140002ec6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140002f7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140002ec6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140002f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f3d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x140002fcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x140002fcc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140002f9b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140002f9b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x140002de9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x140002de9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x140002fd5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x140002fd5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140002f32`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140002f32`
- `ntdll!RtlAcquireResourceExclusive` at `0x140002e81`
- `ntdll!RtlAcquireResourceExclusive` at `0x140002e81`
- `ntdll!RtlReleaseResource` at `0x140002fbe`
- `ntdll!RtlReleaseResource` at `0x140002fbe`

## pseudocode

```c
void ScShutdownServices(void)
{
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // r14
  DWORD v1; // eax
  struct _IMAGE_RECORD *i; // rdi
  CServiceRecord *v3; // rbx
  PRPC_ASYNC_STATE v4; // rcx
  bool v5; // zf
  struct _TP_WORK *v6; // rax
  char LastError; // al
  _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+30h] [rbp-50h] BYREF
  SmartPtrRef *v9; // [rsp+B0h] [rbp+30h] BYREF
  char *v10; // [rsp+B8h] [rbp+38h] BYREF

  memset(&pcbe, 0, sizeof(pcbe));
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  if ( ThreadpoolCleanupGroup )
  {
    pcbe.Pool = g_TpPool;
    pcbe.Version = 3;
    pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    pcbe.Size = 72;
    pcbe.CleanupGroup = ThreadpoolCleanupGroup;
    memset(&pcbe.CleanupGroupCancelCallback, 0, 36);
    RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
    for ( i = qword_1400BC300; i; i = (struct _IMAGE_RECORD *)*((_QWORD *)i + 2) )
    {
      AcquireSRWLockShared(&stru_1400BB330);
      v3 = xmmword_1400BB320;
      v9 = xmmword_1400BB320;
      if ( xmmword_1400BB320 )
        _InterlockedIncrement((volatile signed __int32 *)xmmword_1400BB320 + 3);
      ReleaseSRWLockShared(&stru_1400BB330);
      while ( v3 )
      {
        if ( (*((_BYTE *)v3 + 80) & 0x30) != 0 )
        {
          AcquireSRWLockShared((PSRWLOCK)v3 + 39);
          v5 = (*((_BYTE *)v3 + 88) & 4) == 0;
          v10 = (char *)v3 + 312;
          if ( !v5
            && (struct _IMAGE_RECORD *)(*(__int64 (__fastcall **)(CServiceRecord *))(*(_QWORD *)v3 + 160LL))(v3) == i
            && ((*((_DWORD *)v3 + 21) - 1) & 0xFFFFFFFD) != 0 )
          {
            Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v10);
            v6 = CreateThreadpoolWork(ScShutdownServiceProcessCallback, 0, &pcbe);
            if ( v6 )
            {
              *((_DWORD *)i + 26) |= 0x20u;
              SubmitThreadpoolWork(v6);
              break;
            }
            LastError = GetLastError();
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                142,
                (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
                *((_QWORD *)i + 3),
                LastError);
            }
          }
          else if ( v3 != (CServiceRecord *)-312LL )
          {
            ReleaseSRWLockShared((PSRWLOCK)v3 + 39);
          }
        }
        CServiceDatabase::GetNext((__int64)v4, &v9);
        v3 = v9;
      }
      Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v9);
    }
    RtlReleaseResource(&ScServiceRecordLock);
    CloseThreadpoolCleanupGroupMembers(ThreadpoolCleanupGroup, 0, 0);
    CloseThreadpoolCleanupGroup(ThreadpoolCleanupGroup);
  }
  else
  {
    v1 = GetLastError();
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 141, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v1);
  }
}

```

## disassembly

```asm
0x140002dc0  mov     [rsp-28h+arg_10], rbx
0x140002dc5  push    rbp
0x140002dc6  push    rsi
0x140002dc7  push    rdi
0x140002dc8  push    r14
0x140002dca  push    r15
0x140002dcc  mov     rbp, rsp
0x140002dcf  sub     rsp, 80h
0x140002dd6  mov     ebx, 48h ; 'H'
0x140002ddb  lea     rcx, [rbp+pcbe]; void *
0x140002ddf  mov     r8d, ebx; Size
0x140002de2  xor     edx, edx; Val
0x140002de4  call    memset
0x140002de9  call    cs:__imp_CreateThreadpoolCleanupGroup
0x140002def  mov     r14, rax
0x140002df2  test    rax, rax
0x140002df5  jnz     short loc_140002E39
0x140002df7  call    cs:__imp_GetLastError
0x140002dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e04  lea     r15, WPP_GLOBAL_Control
0x140002e0b  cmp     rcx, r15
0x140002e0e  jz      loc_140002FDB
0x140002e14  test    byte ptr [rcx+1Ch], 1
0x140002e18  jz      loc_140002FDB
0x140002e1e  mov     rcx, [rcx+10h]
0x140002e22  lea     edx, [rbx+45h]
0x140002e25  mov     r9d, eax
0x140002e28  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140002e2f  call    WPP_SF_d
0x140002e34  jmp     loc_140002FDB
0x140002e39  mov     rax, cs:?g_TpPool@@3PEAU_TP_POOL@@EA; _TP_POOL * g_TpPool
0x140002e40  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140002e47  xorps   xmm0, xmm0
0x140002e4a  mov     [rbp+pcbe.Pool], rax
0x140002e4e  mov     dl, 1; Wait
0x140002e50  movdqa  xmmword ptr [rbp+pcbe.RaceDll], xmm0
0x140002e55  mov     [rbp+pcbe.Version], 3
0x140002e5c  mov     [rbp+pcbe.FinalizationCallback], 0
0x140002e64  mov     dword ptr [rbp+pcbe.u], 0
0x140002e6b  mov     [rbp+pcbe.CallbackPriority], 1
0x140002e72  mov     [rbp+pcbe.Size], ebx
0x140002e75  mov     [rbp+pcbe.CleanupGroup], r14
0x140002e79  mov     [rbp+pcbe.CleanupGroupCancelCallback], 0
0x140002e81  call    cs:__imp_RtlAcquireResourceExclusive
0x140002e87  mov     rdi, cs:qword_1400BC300
0x140002e8e  test    rdi, rdi
0x140002e91  jz      loc_140002FB7
0x140002e97  lea     r15, WPP_GLOBAL_Control
0x140002e9e  lea     rcx, stru_1400BB330; SRWLock
0x140002ea5  call    cs:__imp_AcquireSRWLockShared
0x140002eab  mov     rbx, qword ptr cs:xmmword_1400BB320
0x140002eb2  mov     [rbp+arg_0], rbx
0x140002eb6  test    rbx, rbx
0x140002eb9  jz      short loc_140002EBF
0x140002ebb  lock inc dword ptr [rbx+0Ch]
0x140002ebf  lea     rcx, stru_1400BB330; SRWLock
0x140002ec6  call    cs:__imp_ReleaseSRWLockShared
0x140002ecc  test    rbx, rbx
0x140002ecf  jz      loc_140002FA1
0x140002ed5  test    byte ptr [rbx+50h], 30h
0x140002ed9  jz      loc_140002F82
0x140002edf  lea     rsi, [rbx+138h]
0x140002ee6  mov     rcx, rsi; SRWLock
0x140002ee9  call    cs:__imp_AcquireSRWLockShared
0x140002eef  test    byte ptr [rbx+58h], 4
0x140002ef3  mov     [rbp+arg_8], rsi
0x140002ef7  jz      short loc_140002F74
0x140002ef9  mov     rax, [rbx]
0x140002efc  mov     rcx, rbx
0x140002eff  mov     rax, [rax+0A0h]
0x140002f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f0b  cmp     rax, rdi
0x140002f0e  jnz     short loc_140002F74
0x140002f10  mov     eax, [rbx+54h]
0x140002f13  dec     eax
0x140002f15  test    eax, 0FFFFFFFDh
0x140002f1a  jz      short loc_140002F74
0x140002f1c  lea     rcx, [rbp+arg_8]; this
0x140002f20  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x140002f25  lea     r8, [rbp+pcbe]; pcbe
0x140002f29  xor     edx, edx; pv
0x140002f2b  lea     rcx, ?ScShutdownServiceProcessCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140002f32  call    cs:__imp_CreateThreadpoolWork
0x140002f38  test    rax, rax
0x140002f3b  jnz     short loc_140002F94
0x140002f3d  call    cs:__imp_GetLastError
0x140002f43  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f4a  cmp     rcx, r15
0x140002f4d  jz      short loc_140002F82
0x140002f4f  test    byte ptr [rcx+1Ch], 1
0x140002f53  jz      short loc_140002F82
0x140002f55  mov     r9, [rdi+18h]
0x140002f59  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140002f60  mov     rcx, [rcx+10h]
0x140002f64  mov     edx, 8Eh
0x140002f69  mov     [rsp+80h+var_60], eax
0x140002f6d  call    WPP_SF_Sd
0x140002f72  jmp     short loc_140002F82
0x140002f74  test    rsi, rsi
0x140002f77  jz      short loc_140002F82
0x140002f79  mov     rcx, rsi; SRWLock
0x140002f7c  call    cs:__imp_ReleaseSRWLockShared
0x140002f82  lea     rdx, [rbp+arg_0]
0x140002f86  call    ?GetNext@CServiceDatabase@@QEAAXAEAV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z; CServiceDatabase::GetNext(Microsoft::WRL::ComPtr<CServiceRecord> &)
0x140002f8b  mov     rbx, [rbp+arg_0]
0x140002f8f  jmp     loc_140002ECC
0x140002f94  or      dword ptr [rdi+68h], 20h
0x140002f98  mov     rcx, rax; pwk
0x140002f9b  call    cs:__imp_SubmitThreadpoolWork
0x140002fa1  lea     rcx, [rbp+arg_0]
0x140002fa5  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140002faa  mov     rdi, [rdi+10h]
0x140002fae  test    rdi, rdi
0x140002fb1  jnz     loc_140002E9E
0x140002fb7  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140002fbe  call    cs:__imp_RtlReleaseResource
0x140002fc4  xor     r8d, r8d; pvCleanupContext
0x140002fc7  xor     edx, edx; fCancelPendingCallbacks
0x140002fc9  mov     rcx, r14; ptpcg
0x140002fcc  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x140002fd2  mov     rcx, r14; ptpcg
0x140002fd5  call    cs:__imp_CloseThreadpoolCleanupGroup
0x140002fdb  mov     rbx, [rsp+80h+arg_10]
0x140002fe3  add     rsp, 80h
0x140002fea  pop     r15
0x140002fec  pop     r14
0x140002fee  pop     rdi
0x140002fef  pop     rsi
0x140002ff0  pop     rbp
0x140002ff1  retn
```
