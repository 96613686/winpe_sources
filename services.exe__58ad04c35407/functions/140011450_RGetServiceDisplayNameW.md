# RGetServiceDisplayNameW

- ea: `0x140011450`
- end: `0x14001166a`
- name: `RGetServiceDisplayNameW`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400112c0`

## callees

- `0x140003e54`
- `0x140007130`
- `0x1400083f0`
- `0x140008b90`
- `0x14000cf60`
- `0x140011450`
- `0x140011ba0`
- `0x140013b0c`
- `0x14001c87c`
- `0x140020d84`
- `0x14004401c`
- `0x1400795ac`
- `0x140094020`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1400114c5`
- `RPCRT4!RpcImpersonateClient` at `0x1400114c5`
- `RPCRT4!RpcRevertToSelf` at `0x1400115b1`
- `RPCRT4!RpcRevertToSelf` at `0x1400115b1`
- `ntdll!RtlReleaseResource` at `0x1400114ad`
- `ntdll!RtlReleaseResource` at `0x140011648`
- `ntdll!RtlReleaseResource` at `0x1400114ad`
- `ntdll!RtlReleaseResource` at `0x140011648`
- `ntdll!RtlAcquireResourceShared` at `0x140011489`
- `ntdll!RtlAcquireResourceShared` at `0x140011489`
- `ntdll!RtlFreeHeap` at `0x140011632`
- `ntdll!RtlFreeHeap` at `0x140011632`

## pseudocode

```c
__int64 __fastcall RGetServiceDisplayNameW(__int64 a1, wchar_t *a2, unsigned __int16 *a3, _DWORD *a4)
{
  unsigned int NamedServiceRecord; // ebx
  RPC_STATUS v9; // eax
  unsigned int v10; // esi
  struct CServiceRecord *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int16 v14; // ax
  unsigned int ServiceDisplayName; // eax
  unsigned __int16 *JITReadDisplayName; // rdi
  __int64 v17; // r11
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // r14d
  struct CServiceRecord *v21; // [rsp+30h] [rbp-28h] BYREF
  PVOID P; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v23[24]; // [rsp+40h] [rbp-18h] BYREF

  v21 = 0;
  P = 0;
  ScSetTcpKeepalive();
  RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v21);
  NamedServiceRecord = ScGetNamedServiceRecord(a2, &v21);
  if ( NamedServiceRecord )
  {
    RtlReleaseResource(&ScServiceRecordLock);
    Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v21);
    return NamedServiceRecord;
  }
  v9 = RpcImpersonateClient(0);
  v10 = v9;
  if ( !v9 )
  {
    v11 = v21;
    CScmLock::LockAutoExclusive((char *)v21 + 312, v23);
    if ( g_SystemLanguageId == ((unsigned __int16 (*)(void))g_pScExtFunctionPointers[7])() )
    {
      JITReadDisplayName = CServiceRecord::GetJITReadDisplayName(v11, v12, v13);
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)v11 + 48LL))(v11);
      ServiceDisplayName = ScGetServiceDisplayName(
                             *((struct _SERVICE_CONFIG_ROOT **)v11 + 27),
                             *((unsigned __int16 **)v11 + 7),
                             v14,
                             (unsigned __int16 **)&P);
      v10 = ServiceDisplayName;
      if ( ServiceDisplayName )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            97,
            (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
            (_DWORD)a2,
            ServiceDisplayName);
        }
        JITReadDisplayName = (unsigned __int16 *)P;
        goto LABEL_19;
      }
      JITReadDisplayName = (unsigned __int16 *)P;
    }
    v17 = -1;
    do
      ++v17;
    while ( JITReadDisplayName[v17] );
    if ( *a4 >= (unsigned int)(v17 + 1) )
      StringCchCopyW(a3, (unsigned int)(v17 + 1), JITReadDisplayName);
    else
      v10 = 122;
    *a4 = v17;
LABEL_19:
    v20 = RpcRevertToSelf();
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          98,
          (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
          (_DWORD)a2,
          v20);
      ScLogEvent(5u, L"RpcRevertToSelf", v20);
    }
    if ( JITReadDisplayName != *((unsigned __int16 **)v11 + 7)
      && JITReadDisplayName != CServiceRecord::GetJITReadDisplayName(v11, v18, v19) )
    {
      if ( JITReadDisplayName )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, JITReadDisplayName);
    }
    CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v23);
    goto LABEL_29;
  }
  ScLogImpersonateFailureEvent(v9);
LABEL_29:
  RtlReleaseResource(&ScServiceRecordLock);
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v21);
  return v10;
}

```

## disassembly

```asm
0x140011450  push    rbp
0x140011452  push    rbx
0x140011453  push    rsi
0x140011454  push    rdi
0x140011455  push    r12
0x140011457  push    r13
0x140011459  push    r14
0x14001145b  push    r15
0x14001145d  mov     rbp, rsp
0x140011460  sub     rsp, 58h
0x140011464  xor     r13d, r13d
0x140011467  mov     r14, r9
0x14001146a  mov     [rbp+var_28], r13
0x14001146e  mov     r12, r8
0x140011471  mov     [rbp+P], r13
0x140011475  mov     r15, rdx
0x140011478  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x14001147d  lea     rdi, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; CServiceRecordLock ScServiceRecordLock
0x140011484  mov     dl, 1; Wait
0x140011486  mov     rcx, rdi; Resource
0x140011489  call    cs:__imp_RtlAcquireResourceShared
0x14001148f  lea     rcx, [rbp+var_28]
0x140011493  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140011498  lea     rdx, [rbp+var_28]; struct CServiceRecord **
0x14001149c  mov     rcx, r15; String2
0x14001149f  call    ?ScGetNamedServiceRecord@@YAKPEBGPEAPEAVCServiceRecord@@@Z; ScGetNamedServiceRecord(ushort const *,CServiceRecord * *)
0x1400114a4  mov     ebx, eax
0x1400114a6  test    eax, eax
0x1400114a8  jz      short loc_1400114C3
0x1400114aa  mov     rcx, rdi; Resource
0x1400114ad  call    cs:__imp_RtlReleaseResource
0x1400114b3  lea     rcx, [rbp+var_28]
0x1400114b7  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x1400114bc  mov     eax, ebx
0x1400114be  jmp     loc_140011659
0x1400114c3  xor     ecx, ecx; BindingHandle
0x1400114c5  call    cs:__imp_RpcImpersonateClient
0x1400114cb  mov     esi, eax
0x1400114cd  test    eax, eax
0x1400114cf  jz      short loc_1400114E0
0x1400114d1  mov     ecx, eax; int
0x1400114d3  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x1400114d8  mov     rcx, rdi
0x1400114db  jmp     loc_140011648
0x1400114e0  mov     rbx, [rbp+var_28]
0x1400114e4  lea     rdx, [rbp+var_18]
0x1400114e8  lea     rcx, [rbx+138h]
0x1400114ef  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x1400114f4  mov     rax, cs:?g_pScExtFunctionPointers@@3PEAPEAXEA; void * * g_pScExtFunctionPointers
0x1400114fb  mov     rax, [rax+38h]
0x1400114ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011504  cmp     cs:?g_SystemLanguageId@@3GA, ax; ushort g_SystemLanguageId
0x14001150b  lea     rdi, WPP_GLOBAL_Control
0x140011512  mov     rcx, rbx; this
0x140011515  jz      short loc_14001157B
0x140011517  mov     rax, [rbx]
0x14001151a  mov     rax, [rax+30h]
0x14001151e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011523  mov     rdx, [rbx+38h]; unsigned __int16 *
0x140011527  lea     r9, [rbp+P]; unsigned __int16 **
0x14001152b  mov     rcx, [rbx+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x140011532  movzx   r8d, ax; unsigned __int16
0x140011536  call    ?ScGetServiceDisplayName@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAGGPEAPEAG@Z; ScGetServiceDisplayName(_SERVICE_CONFIG_ROOT *,ushort *,ushort,ushort * *)
0x14001153b  mov     esi, eax
0x14001153d  test    eax, eax
0x14001153f  jz      short loc_140011575
0x140011541  mov     rcx, cs:WPP_GLOBAL_Control
0x140011548  cmp     rcx, rdi
0x14001154b  jz      short loc_14001156F
0x14001154d  test    byte ptr [rcx+1Ch], 1
0x140011551  jz      short loc_14001156F
0x140011553  mov     rcx, [rcx+10h]
0x140011557  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x14001155e  mov     edx, 61h ; 'a'
0x140011563  mov     [rsp+58h+var_38], eax
0x140011567  mov     r9, r15
0x14001156a  call    WPP_SF_Sd
0x14001156f  mov     rdi, [rbp+P]
0x140011573  jmp     short loc_1400115B1
0x140011575  mov     rdi, [rbp+P]
0x140011579  jmp     short loc_140011583
0x14001157b  call    ?GetJITReadDisplayName@CServiceRecord@@QEAAPEAGXZ; CServiceRecord::GetJITReadDisplayName(void)
0x140011580  mov     rdi, rax
0x140011583  or      r11, 0FFFFFFFFFFFFFFFFh
0x140011587  inc     r11
0x14001158a  cmp     [rdi+r11*2], r13w
0x14001158f  jnz     short loc_140011587
0x140011591  lea     eax, [r11+1]
0x140011595  cmp     [r14], eax
0x140011598  jnb     short loc_1400115A1
0x14001159a  mov     esi, 7Ah ; 'z'
0x14001159f  jmp     short loc_1400115AE
0x1400115a1  mov     edx, eax; unsigned __int64
0x1400115a3  mov     r8, rdi; unsigned __int16 *
0x1400115a6  mov     rcx, r12; unsigned __int16 *
0x1400115a9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400115ae  mov     [r14], r11d
0x1400115b1  call    cs:__imp_RpcRevertToSelf
0x1400115b7  mov     r14d, eax
0x1400115ba  test    eax, eax
0x1400115bc  jz      short loc_140011608
0x1400115be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115c5  lea     rax, WPP_GLOBAL_Control
0x1400115cc  cmp     rcx, rax
0x1400115cf  jz      short loc_1400115F4
0x1400115d1  test    byte ptr [rcx+1Ch], 1
0x1400115d5  jz      short loc_1400115F4
0x1400115d7  mov     rcx, [rcx+10h]
0x1400115db  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x1400115e2  mov     edx, 62h ; 'b'
0x1400115e7  mov     [rsp+58h+var_38], r14d
0x1400115ec  mov     r9, r15
0x1400115ef  call    WPP_SF_Sd
0x1400115f4  mov     r8d, r14d
0x1400115f7  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x1400115fe  mov     ecx, 5; unsigned int
0x140011603  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x140011608  cmp     rdi, [rbx+38h]
0x14001160c  jz      short loc_140011638
0x14001160e  mov     rcx, rbx; this
0x140011611  call    ?GetJITReadDisplayName@CServiceRecord@@QEAAPEAGXZ; CServiceRecord::GetJITReadDisplayName(void)
0x140011616  cmp     rdi, rax
0x140011619  jz      short loc_140011638
0x14001161b  test    rdi, rdi
0x14001161e  jz      short loc_140011638
0x140011620  mov     rcx, gs:60h
0x140011629  mov     r8, rdi; P
0x14001162c  xor     edx, edx; Flags
0x14001162e  mov     rcx, [rcx+30h]; HeapHandle
0x140011632  call    cs:__imp_RtlFreeHeap
0x140011638  lea     rcx, [rbp+var_18]; this
0x14001163c  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x140011641  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140011648  call    cs:__imp_RtlReleaseResource
0x14001164e  lea     rcx, [rbp+var_28]
0x140011652  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140011657  mov     eax, esi
0x140011659  add     rsp, 58h
0x14001165d  pop     r15
0x14001165f  pop     r14
0x140011661  pop     r13
0x140011663  pop     r12
0x140011665  pop     rdi
0x140011666  pop     rsi
0x140011667  pop     rbx
0x140011668  pop     rbp
0x140011669  retn
```
