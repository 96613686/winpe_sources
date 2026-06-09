# ScUnregisterServicesTriggerAction(uchar)

- ea: `0x140041eb8`
- end: `0x1400420c7`
- name: `?ScUnregisterServicesTriggerAction@@YAXE@Z`
- size: `527`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140038d98`

## callees

- `0x140003310`
- `0x140003e54`
- `0x14000512c`
- `0x140007130`
- `0x14002e844`
- `0x140041eb8`
- `0x1400644c0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140041eec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140041eec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140041f0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140041f0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140041ed0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140041ed0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400420a8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400420a8`
- `ntdll!RtlAcquireResourceExclusive` at `0x140041edf`
- `ntdll!RtlAcquireResourceExclusive` at `0x14004207d`
- `ntdll!RtlAcquireResourceExclusive` at `0x140041edf`
- `ntdll!RtlAcquireResourceExclusive` at `0x14004207d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140041eca`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140041eca`
- `ntdll!RtlReleaseResource` at `0x140041f65`
- `ntdll!RtlReleaseResource` at `0x140041f65`
- `ntdll!RtlReleaseResource` at `0x1400420c0`
- `ntdll!RtlFreeHeap` at `0x14004206e`
- `ntdll!RtlFreeHeap` at `0x14004206e`

## pseudocode

```c
void __fastcall ScUnregisterServicesTriggerAction()
{
  CServiceRecord *v0; // rbx
  __int64 v1; // rcx
  unsigned __int16 *v2; // rdx
  struct _SERVICE_CONFIG_ROOT *v3; // rcx
  unsigned int v4; // eax
  PVOID v5; // r8
  int v6; // eax
  __int128 v7; // [rsp+30h] [rbp-28h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]
  PVOID P; // [rsp+68h] [rbp+10h] BYREF
  SmartPtrRef *v10; // [rsp+70h] [rbp+18h] BYREF

  RtlAcquireSRWLockExclusive(&g_TriggerRegistrationLock);
  GetCurrentThreadId();
  RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
  AcquireSRWLockShared(&stru_1400BB330);
  v0 = xmmword_1400BB320;
  v10 = xmmword_1400BB320;
  if ( xmmword_1400BB320 )
    _InterlockedIncrement((volatile signed __int32 *)xmmword_1400BB320 + 3);
  ReleaseSRWLockShared(&stru_1400BB330);
  while ( v0 )
  {
    if ( (*((_BYTE *)v0 + 80) & 0x30) != 0
      && *((_DWORD *)v0 + 9) != 4
      && ((*((_DWORD *)v0 + 13) & 0x400) != 0
       || (*(__int64 (__fastcall **)(CServiceRecord *))(*(_QWORD *)v0 + 176LL))(v0)) )
    {
      RtlReleaseResource(&ScServiceRecordLock);
      ScUnregisterDirectTriggerAction(v0);
      if ( (*((_DWORD *)v0 + 13) & 0x400) != 0 )
      {
        v8 = 0;
        v7 = 0;
        v2 = (unsigned __int16 *)*((_QWORD *)v0 + 7);
        v3 = (struct _SERVICE_CONFIG_ROOT *)*((_QWORD *)v0 + 27);
        P = 0;
        v4 = ScResolveServiceAccount(v3, v2, &P);
        if ( v4
          && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            288,
            (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
            *((_QWORD *)v0 + 7),
            v4);
        }
        v5 = P;
        if ( !P )
          v5 = LocalSystemSid;
        v6 = ((__int64 (__fastcall *)(__int128 *, _QWORD, PVOID, _QWORD, int))g_pScExtFunctionPointers[10])(
               &v7,
               *((_QWORD *)v0 + 7),
               v5,
               0,
               8);
        if ( v6 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              289,
              (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
              *((_QWORD *)v0 + 7),
              v6);
          }
        }
        else
        {
          CServiceRecord::ClearStatusFlag(v0, 1024);
        }
        if ( P )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      }
      RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
    }
    CServiceDatabase::GetNext(v1, &v10);
    v0 = v10;
  }
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v10);
  RtlReleaseSRWLockExclusive(&g_TriggerRegistrationLock);
  RtlReleaseResource(&ScServiceRecordLock);
}

```

## disassembly

```asm
0x140041eb8  mov     [rsp+arg_0], rbx
0x140041ebd  push    r14
0x140041ebf  sub     rsp, 50h
0x140041ec3  lea     rcx, g_TriggerRegistrationLock
0x140041eca  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140041ed0  call    cs:__imp_GetCurrentThreadId
0x140041ed6  mov     dl, 1; Wait
0x140041ed8  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140041edf  call    cs:__imp_RtlAcquireResourceExclusive
0x140041ee5  lea     rcx, stru_1400BB330; SRWLock
0x140041eec  call    cs:__imp_AcquireSRWLockShared
0x140041ef2  mov     rbx, qword ptr cs:xmmword_1400BB320
0x140041ef9  mov     [rsp+58h+arg_10], rbx
0x140041efe  test    rbx, rbx
0x140041f01  jz      short loc_140041F07
0x140041f03  lock inc dword ptr [rbx+0Ch]
0x140041f07  lea     rcx, stru_1400BB330; SRWLock
0x140041f0e  call    cs:__imp_ReleaseSRWLockShared
0x140041f14  lea     r14, WPP_GLOBAL_Control
0x140041f1b  test    rbx, rbx
0x140041f1e  jz      loc_140042097
0x140041f24  test    byte ptr [rbx+50h], 30h
0x140041f28  jz      loc_140042083
0x140041f2e  mov     eax, [rbx+24h]
0x140041f31  cmp     eax, 4
0x140041f34  jz      loc_140042083
0x140041f3a  mov     eax, [rbx+34h]
0x140041f3d  bt      eax, 0Ah
0x140041f41  jb      short loc_140041F5E
0x140041f43  mov     rax, [rbx]
0x140041f46  mov     rcx, rbx
0x140041f49  mov     rax, [rax+0B0h]
0x140041f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041f55  test    rax, rax
0x140041f58  jz      loc_140042083
0x140041f5e  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140041f65  call    cs:__imp_RtlReleaseResource
0x140041f6b  mov     rcx, rbx; struct CServiceRecord *
0x140041f6e  call    ?ScUnregisterDirectTriggerAction@@YAXPEAVCServiceRecord@@@Z; ScUnregisterDirectTriggerAction(CServiceRecord *)
0x140041f73  mov     eax, [rbx+34h]
0x140041f76  bt      eax, 0Ah
0x140041f7a  jnb     loc_140042074
0x140041f80  xor     eax, eax
0x140041f82  lea     r8, [rsp+58h+P]; void **
0x140041f87  mov     [rsp+58h+var_18], rax
0x140041f8c  xorps   xmm0, xmm0
0x140041f8f  movups  [rsp+58h+var_28], xmm0
0x140041f94  mov     rdx, [rbx+38h]; unsigned __int16 *
0x140041f98  mov     rcx, [rbx+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x140041f9f  mov     [rsp+58h+P], rax
0x140041fa4  call    ?ScResolveServiceAccount@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAGPEAPEAX@Z; ScResolveServiceAccount(_SERVICE_CONFIG_ROOT *,ushort *,void * *)
0x140041fa9  test    eax, eax
0x140041fab  jz      short loc_140041FDC
0x140041fad  mov     rcx, cs:WPP_GLOBAL_Control
0x140041fb4  cmp     rcx, r14
0x140041fb7  jz      short loc_140041FDC
0x140041fb9  test    byte ptr [rcx+1Ch], 1
0x140041fbd  jz      short loc_140041FDC
0x140041fbf  mov     r9, [rbx+38h]
0x140041fc3  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140041fca  mov     rcx, [rcx+10h]
0x140041fce  mov     edx, 120h
0x140041fd3  mov     [rsp+58h+var_38], eax
0x140041fd7  call    WPP_SF_Sd
0x140041fdc  mov     r8, [rsp+58h+P]
0x140041fe1  lea     rcx, [rsp+58h+var_28]
0x140041fe6  mov     rax, cs:?g_pScExtFunctionPointers@@3PEAPEAXEA; void * * g_pScExtFunctionPointers
0x140041fed  test    r8, r8
0x140041ff0  mov     rdx, [rbx+38h]
0x140041ff4  cmovz   r8, cs:LocalSystemSid
0x140041ffc  xor     r9d, r9d
0x140041fff  mov     [rsp+58h+var_38], 8
0x140042007  mov     rax, [rax+50h]
0x14004200b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042010  test    eax, eax
0x140042012  jz      short loc_140042045
0x140042014  mov     rcx, cs:WPP_GLOBAL_Control
0x14004201b  cmp     rcx, r14
0x14004201e  jz      short loc_140042052
0x140042020  test    byte ptr [rcx+1Ch], 1
0x140042024  jz      short loc_140042052
0x140042026  mov     r9, [rbx+38h]
0x14004202a  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140042031  mov     rcx, [rcx+10h]
0x140042035  mov     edx, 121h
0x14004203a  mov     [rsp+58h+var_38], eax
0x14004203e  call    WPP_SF_Sd
0x140042043  jmp     short loc_140042052
0x140042045  mov     edx, 400h; unsigned int
0x14004204a  mov     rcx, rbx; this
0x14004204d  call    ?ClearStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::ClearStatusFlag(ulong)
0x140042052  cmp     [rsp+58h+P], 0
0x140042058  jz      short loc_140042074
0x14004205a  mov     rcx, gs:60h
0x140042063  xor     edx, edx; Flags
0x140042065  mov     r8, [rsp+58h+P]; P
0x14004206a  mov     rcx, [rcx+30h]; HeapHandle
0x14004206e  call    cs:__imp_RtlFreeHeap
0x140042074  mov     dl, 1; Wait
0x140042076  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14004207d  call    cs:__imp_RtlAcquireResourceExclusive
0x140042083  lea     rdx, [rsp+58h+arg_10]
0x140042088  call    ?GetNext@CServiceDatabase@@QEAAXAEAV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z; CServiceDatabase::GetNext(Microsoft::WRL::ComPtr<CServiceRecord> &)
0x14004208d  mov     rbx, [rsp+58h+arg_10]
0x140042092  jmp     loc_140041F1B
0x140042097  lea     rcx, [rsp+58h+arg_10]
0x14004209c  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x1400420a1  lea     rcx, g_TriggerRegistrationLock
0x1400420a8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400420ae  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; CServiceRecordLock ScServiceRecordLock
0x1400420b5  mov     rbx, [rsp+58h+arg_0]
0x1400420ba  add     rsp, 50h
0x1400420be  pop     r14
0x1400420c0  jmp     cs:__imp_RtlReleaseResource
```
