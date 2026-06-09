# ScStartPhase2Services(utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>> &)

- ea: `0x140032cd8`
- end: `0x1400330f9`
- name: `?ScStartPhase2Services@@YAXAEAV?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@@Z`
- size: `1057`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140039bd4`

## callees

- `0x140003e54`
- `0x140005824`
- `0x140005840`
- `0x140006df4`
- `0x1400070d0`
- `0x140007130`
- `0x140007770`
- `0x1400188fc`
- `0x14001f99c`
- `0x14002d730`
- `0x140032cd8`
- `0x140033100`
- `0x1400430b0`
- `0x1400575b0`
- `0x14006fb40`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x140033060`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x140033060`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140032f4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140032f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032fe6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140032f83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140032f8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140032f83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140032f8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400330a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400330a6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140032fbe`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140032fbe`
- `ntdll!RtlFreeHeap` at `0x140032f39`
- `ntdll!RtlFreeHeap` at `0x140032f39`
- `ntdll!TpPostWork` at `0x14003302d`
- `ntdll!TpPostWork` at `0x14003302d`
- `ntdll!RtlAllocateHeap` at `0x140032ea9`
- `ntdll!RtlAllocateHeap` at `0x140032ea9`

## pseudocode

```c
__int64 __fastcall ScStartPhase2Services(_QWORD *a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rax
  CServiceRecord *v3; // rbx
  unsigned __int16 *GroupName; // rax
  const wchar_t *v5; // r13
  PRPC_ASYNC_STATE v6; // rcx
  char GroupIndex; // al
  __int64 **v8; // rbx
  DWORD v9; // r15d
  __int64 *v10; // rsi
  __int64 v11; // rdx
  _QWORD *Heap; // rax
  _QWORD *v13; // r14
  int v14; // eax
  HANDLE EventW; // r12
  char LastError; // al
  int v17; // edx
  HANDLE CurrentProcess; // rdi
  HANDLE v19; // rax
  __int64 v20; // rax
  DWORD i; // ebx
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  struct _TP_WORK *v24; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v25; // [rsp+50h] [rbp-B0h]
  _QWORD *v26; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v28[3]; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handles[64]; // [rsp+80h] [rbp-80h] BYREF

  v1 = a1;
  v25 = a1;
  v24 = 0;
  memset(Handles, 0, sizeof(Handles));
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(v28);
  v27 = 0;
  ScUpdateAndPublishScmGlobalState(0x40u);
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::sort<bool (*)(Microsoft::WRL::ComPtr<CServiceRecord> const &,Microsoft::WRL::ComPtr<CServiceRecord> const &)>(v1);
  v2 = *v1;
  v23 = *v1;
  v26 = v1;
  while ( (_QWORD *)v2 != v1 )
  {
    v3 = *(CServiceRecord **)(v2 + 16);
    if ( !(unsigned int)ScMarkStartSetStartNow(&v23, &v26, v28) )
      goto LABEL_56;
    GroupName = CServiceRecord::GetGroupName(v3);
    v5 = L"Null";
    if ( GroupName )
      v5 = GroupName;
    if ( g_RelaxGroupLoadOrder )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 0x40) == 0 )
      {
        goto LABEL_14;
      }
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 13, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 0x40) == 0 )
      {
        goto LABEL_14;
      }
      GroupIndex = CServiceRecord::GetGroupIndex(v3);
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        12,
        (unsigned int)WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
        (_DWORD)v5,
        GroupIndex);
    }
    v6 = WPP_GLOBAL_Control;
LABEL_14:
    v8 = (__int64 **)v28[0];
    v9 = 0;
    while ( v8 != v28 )
    {
      v10 = v8[2];
      if ( *((_DWORD *)v10 + 21) == 1 )
      {
        if ( CServiceRecord::GetStartState((CServiceRecord *)v8[2]) == 4 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x10000) != 0 )
          {
            v11 = 15;
            goto LABEL_20;
          }
        }
        else
        {
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x18u);
          v13 = Heap;
          if ( Heap )
          {
            *Heap = v10;
            Heap[1] = 0;
            v14 = ScAllocWork(&v24, ScStartServiceCallback, Heap);
            if ( v14 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control->StubInfo,
                  17,
                  (unsigned int)WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
                  v10[7],
                  v14);
              }
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
              goto LABEL_47;
            }
            EventW = CreateEventW(0, 0, 0, 0);
            if ( EventW )
            {
              CurrentProcess = GetCurrentProcess();
              v19 = GetCurrentProcess();
              if ( DuplicateHandle(v19, EventW, CurrentProcess, &Handles[v9], 0, 0, 2u) )
              {
                ++v9;
              }
              else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                     && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                LastError = GetLastError();
                v17 = 19;
LABEL_43:
                WPP_SF_Sd(
                  WPP_GLOBAL_Control->StubInfo,
                  v17,
                  (unsigned int)WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
                  v10[7],
                  LastError);
              }
            }
            else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                   && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              LastError = GetLastError();
              v17 = 18;
              goto LABEL_43;
            }
            v13[2] = EventW;
            _InterlockedIncrement((volatile signed __int32 *)v10 + 3);
            v20 = v13[1];
            if ( v20 )
              _InterlockedIncrement((volatile signed __int32 *)(v20 + 12));
            TpPostWork(v24);
            goto LABEL_47;
          }
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            v11 = 16;
LABEL_20:
            WPP_SF_S(v6->StubInfo, v11, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v10[7]);
LABEL_47:
            v6 = WPP_GLOBAL_Control;
          }
        }
      }
      else if ( v6 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (HIDWORD(v6->UserInfo) & 0x10000) != 0 )
      {
        v11 = 14;
        goto LABEL_20;
      }
      v8 = (__int64 **)*v8;
    }
    if ( v9 )
    {
      if ( WaitForMultipleObjectsEx(v9, Handles, 1, g_ServiceStartTimeout, 0) == 258
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 20, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v5);
      }
      for ( i = 0; i < v9; ++i )
        CloseHandle(Handles[i]);
    }
LABEL_56:
    v2 = v23;
    v1 = v25;
  }
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v27);
  return utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear(v28);
}

```

## disassembly

```asm
0x140032cd8  push    rbp
0x140032cda  push    rbx
0x140032cdb  push    rsi
0x140032cdc  push    rdi
0x140032cdd  push    r12
0x140032cdf  push    r13
0x140032ce1  push    r14
0x140032ce3  push    r15
0x140032ce5  lea     rbp, [rsp-198h]
0x140032ced  sub     rsp, 298h
0x140032cf4  mov     rax, cs:__security_cookie
0x140032cfb  xor     rax, rsp
0x140032cfe  mov     [rbp+1D0h+var_50], rax
0x140032d05  mov     rbx, rcx
0x140032d08  mov     [rsp+2D0h+var_280], rcx
0x140032d0d  xor     r12d, r12d
0x140032d10  lea     rcx, [rbp+1D0h+Handles]; void *
0x140032d14  xor     edx, edx; Val
0x140032d16  mov     [rsp+2D0h+var_288], r12
0x140032d1b  mov     r8d, 200h; Size
0x140032d21  call    memset
0x140032d26  lea     rcx, [rsp+2D0h+var_268]
0x140032d2b  call    ??0?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAA@XZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(void)
0x140032d30  mov     cl, 40h ; '@'; unsigned __int8
0x140032d32  mov     [rsp+2D0h+var_270], r12
0x140032d37  call    ?ScUpdateAndPublishScmGlobalState@@YAXE@Z; ScUpdateAndPublishScmGlobalState(uchar)
0x140032d3c  mov     rcx, rbx
0x140032d3f  call    ??$sort@P6A_NAEBV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@0@Z@?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAAXP6A_NAEBV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@0@Z@Z; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::sort<bool (*)(Microsoft::WRL::ComPtr<CServiceRecord> const &,Microsoft::WRL::ComPtr<CServiceRecord> const &)>(bool (*)(Microsoft::WRL::ComPtr<CServiceRecord> const &,Microsoft::WRL::ComPtr<CServiceRecord> const &))
0x140032d44  mov     rax, [rbx]
0x140032d47  lea     rdi, WPP_GLOBAL_Control
0x140032d4e  mov     [rsp+2D0h+var_290], rax
0x140032d53  mov     [rsp+2D0h+var_278], rbx
0x140032d58  cmp     rax, rbx
0x140032d5b  jz      loc_1400330C2
0x140032d61  mov     rbx, [rax+10h]
0x140032d65  lea     r8, [rsp+2D0h+var_268]
0x140032d6a  lea     rdx, [rsp+2D0h+var_278]
0x140032d6f  lea     rcx, [rsp+2D0h+var_290]
0x140032d74  call    ?ScMarkStartSetStartNow@@YAHAEAV?$_DlistIt@U?$_DlistNode@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@0PEAV?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@2@@Z; ScMarkStartSetStartNow(utl::_DlistIt<utl::_DlistNode<Microsoft::WRL::ComPtr<CServiceRecord>>,Microsoft::WRL::ComPtr<CServiceRecord>> &,utl::_DlistIt<utl::_DlistNode<Microsoft::WRL::ComPtr<CServiceRecord>>,Microsoft::WRL::ComPtr<CServiceRecord>> &,utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>> *)
0x140032d79  test    eax, eax
0x140032d7b  jz      loc_1400330B3
0x140032d81  mov     rcx, rbx; this
0x140032d84  call    ?GetGroupName@CServiceRecord@@QEAAPEAGXZ; CServiceRecord::GetGroupName(void)
0x140032d89  test    rax, rax
0x140032d8c  lea     r13, aNull_1; "Null"
0x140032d93  cmovnz  r13, rax
0x140032d97  cmp     cs:?g_RelaxGroupLoadOrder@@3HA, r12d; int g_RelaxGroupLoadOrder
0x140032d9e  jnz     short loc_140032DDF
0x140032da0  mov     rcx, cs:WPP_GLOBAL_Control
0x140032da7  cmp     rcx, rdi
0x140032daa  jz      short loc_140032E0D
0x140032dac  test    byte ptr [rcx+1Ch], 40h
0x140032db0  jz      short loc_140032E0D
0x140032db2  mov     rcx, rbx; this
0x140032db5  call    ?GetGroupIndex@CServiceRecord@@QEAAKXZ; CServiceRecord::GetGroupIndex(void)
0x140032dba  mov     rcx, cs:WPP_GLOBAL_Control
0x140032dc1  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140032dc8  mov     edx, 0Ch
0x140032dcd  mov     [rsp+2D0h+dwDesiredAccess], eax
0x140032dd1  mov     r9, r13
0x140032dd4  mov     rcx, [rcx+10h]
0x140032dd8  call    WPP_SF_Sd
0x140032ddd  jmp     short loc_140032E06
0x140032ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x140032de6  cmp     rcx, rdi
0x140032de9  jz      short loc_140032E0D
0x140032deb  test    byte ptr [rcx+1Ch], 40h
0x140032def  jz      short loc_140032E0D
0x140032df1  mov     rcx, [rcx+10h]
0x140032df5  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140032dfc  mov     edx, 0Dh
0x140032e01  call    WPP_SF_
0x140032e06  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e0d  mov     rbx, [rsp+2D0h+var_268]
0x140032e12  mov     r15d, r12d
0x140032e15  lea     rax, [rsp+2D0h+var_268]
0x140032e1a  cmp     rbx, rax
0x140032e1d  jz      loc_140033042
0x140032e23  mov     rsi, [rbx+10h]
0x140032e27  cmp     dword ptr [rsi+54h], 1
0x140032e2b  jz      short loc_140032E61
0x140032e2d  cmp     rcx, rdi
0x140032e30  jz      loc_14003303A
0x140032e36  test    dword ptr [rcx+1Ch], 10000h
0x140032e3d  jz      loc_14003303A
0x140032e43  mov     edx, 0Eh
0x140032e48  mov     r9, [rsi+38h]
0x140032e4c  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140032e53  mov     rcx, [rcx+10h]
0x140032e57  call    WPP_SF_S
0x140032e5c  jmp     loc_140033033
0x140032e61  mov     rcx, rsi; this
0x140032e64  call    ?GetStartState@CServiceRecord@@QEAAGXZ; CServiceRecord::GetStartState(void)
0x140032e69  cmp     ax, 4
0x140032e6d  jnz     short loc_140032E93
0x140032e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e76  cmp     rcx, rdi
0x140032e79  jz      loc_14003303A
0x140032e7f  test    dword ptr [rcx+1Ch], 10000h
0x140032e86  jz      loc_14003303A
0x140032e8c  mov     edx, 0Fh
0x140032e91  jmp     short loc_140032E48
0x140032e93  mov     rcx, gs:60h
0x140032e9c  mov     edx, 8; Flags
0x140032ea1  mov     rcx, [rcx+30h]; HeapHandle
0x140032ea5  lea     r8d, [rdx+10h]; Size
0x140032ea9  call    cs:__imp_RtlAllocateHeap
0x140032eaf  mov     r14, rax
0x140032eb2  test    rax, rax
0x140032eb5  jnz     short loc_140032ED9
0x140032eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ebe  cmp     rcx, rdi
0x140032ec1  jz      loc_14003303A
0x140032ec7  test    byte ptr [rcx+1Ch], 1
0x140032ecb  jz      loc_14003303A
0x140032ed1  lea     edx, [rax+10h]
0x140032ed4  jmp     loc_140032E48
0x140032ed9  mov     r8, r14; void *
0x140032edc  mov     [rax], rsi
0x140032edf  lea     rdx, ?ScStartServiceCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x140032ee6  mov     [rax+8], r12
0x140032eea  lea     rcx, [rsp+2D0h+var_288]; struct _TP_WORK **
0x140032eef  call    ?ScAllocWork@@YAJPEAPEAU_TP_WORK@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z2@Z; ScAllocWork(_TP_WORK * *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x140032ef4  test    eax, eax
0x140032ef6  jns     short loc_140032F44
0x140032ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x140032eff  cmp     rcx, rdi
0x140032f02  jz      short loc_140032F27
0x140032f04  test    byte ptr [rcx+1Ch], 1
0x140032f08  jz      short loc_140032F27
0x140032f0a  mov     r9, [rsi+38h]
0x140032f0e  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140032f15  mov     rcx, [rcx+10h]
0x140032f19  mov     edx, 11h
0x140032f1e  mov     [rsp+2D0h+dwDesiredAccess], eax
0x140032f22  call    WPP_SF_Sd
0x140032f27  mov     rcx, gs:60h
0x140032f30  mov     r8, r14; P
0x140032f33  xor     edx, edx; Flags
0x140032f35  mov     rcx, [rcx+30h]; HeapHandle
0x140032f39  call    cs:__imp_RtlFreeHeap
0x140032f3f  jmp     loc_140033033
0x140032f44  xor     r9d, r9d; lpName
0x140032f47  xor     r8d, r8d; bInitialState
0x140032f4a  xor     edx, edx; bManualReset
0x140032f4c  xor     ecx, ecx; lpEventAttributes
0x140032f4e  call    cs:__imp_CreateEventW
0x140032f54  mov     r12, rax
0x140032f57  test    rax, rax
0x140032f5a  jnz     short loc_140032F83
0x140032f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f63  cmp     rcx, rdi
0x140032f66  jz      loc_140033010
0x140032f6c  test    byte ptr [rcx+1Ch], 1
0x140032f70  jz      loc_140033010
0x140032f76  call    cs:__imp_GetLastError
0x140032f7c  lea     edx, [r12+12h]
0x140032f81  jmp     short loc_140032FF1
0x140032f83  call    cs:__imp_GetCurrentProcess
0x140032f89  mov     rdi, rax
0x140032f8c  call    cs:__imp_GetCurrentProcess
0x140032f92  mov     ecx, r15d
0x140032f95  lea     r9, [rbp+1D0h+Handles]
0x140032f99  mov     [rsp+2D0h+dwOptions], 2; dwOptions
0x140032fa1  mov     r8, rdi; hTargetProcessHandle
0x140032fa4  mov     [rsp+2D0h+bInheritHandle], 0; bInheritHandle
0x140032fac  mov     rdx, r12; hSourceHandle
0x140032faf  mov     [rsp+2D0h+dwDesiredAccess], 0; dwDesiredAccess
0x140032fb7  lea     r9, [r9+rcx*8]; lpTargetHandle
0x140032fbb  mov     rcx, rax; hSourceProcessHandle
0x140032fbe  call    cs:__imp_DuplicateHandle
0x140032fc4  lea     rdi, WPP_GLOBAL_Control
0x140032fcb  test    eax, eax
0x140032fcd  jz      short loc_140032FD4
0x140032fcf  inc     r15d
0x140032fd2  jmp     short loc_140033010
0x140032fd4  mov     rax, cs:WPP_GLOBAL_Control
0x140032fdb  cmp     rax, rdi
0x140032fde  jz      short loc_140033010
0x140032fe0  test    byte ptr [rax+1Ch], 1
0x140032fe4  jz      short loc_140033010
0x140032fe6  call    cs:__imp_GetLastError
0x140032fec  mov     edx, 13h
0x140032ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ff8  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140032fff  mov     r9, [rsi+38h]
0x140033003  mov     [rsp+2D0h+dwDesiredAccess], eax
0x140033007  mov     rcx, [rcx+10h]
0x14003300b  call    WPP_SF_Sd
0x140033010  mov     [r14+10h], r12
0x140033014  lock inc dword ptr [rsi+0Ch]
0x140033018  mov     rax, [r14+8]
0x14003301c  xor     r12d, r12d
0x14003301f  test    rax, rax
0x140033022  jz      short loc_140033028
0x140033024  lock inc dword ptr [rax+0Ch]
0x140033028  mov     rcx, [rsp+2D0h+var_288]
0x14003302d  call    cs:__imp_TpPostWork
0x140033033  mov     rcx, cs:WPP_GLOBAL_Control
0x14003303a  mov     rbx, [rbx]
0x14003303d  jmp     loc_140032E15
0x140033042  test    r15d, r15d
0x140033045  jz      short loc_1400330B3
0x140033047  mov     r9d, cs:?g_ServiceStartTimeout@@3KA; dwMilliseconds
0x14003304e  lea     rdx, [rbp+1D0h+Handles]; lpHandles
0x140033052  mov     r8d, 1; bWaitAll
0x140033058  mov     [rsp+2D0h+dwDesiredAccess], r12d; bAlertable
0x14003305d  mov     ecx, r15d; nCount
0x140033060  call    cs:__imp_WaitForMultipleObjectsEx
0x140033066  cmp     eax, 102h
0x14003306b  jnz     short loc_140033097
0x14003306d  mov     rcx, cs:WPP_GLOBAL_Control
0x140033074  cmp     rcx, rdi
0x140033077  jz      short loc_140033097
0x140033079  test    byte ptr [rcx+1Ch], 1
0x14003307d  jz      short loc_140033097
0x14003307f  mov     rcx, [rcx+10h]
0x140033083  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x14003308a  mov     edx, 14h
0x14003308f  mov     r9, r13
0x140033092  call    WPP_SF_S
0x140033097  mov     ebx, r12d
0x14003309a  test    r15d, r15d
0x14003309d  jz      short loc_1400330B3
0x14003309f  mov     ecx, ebx
0x1400330a1  mov     rcx, [rbp+rcx*8+1D0h+Handles]; hObject
0x1400330a6  call    cs:__imp_CloseHandle
0x1400330ac  inc     ebx
0x1400330ae  cmp     ebx, r15d
0x1400330b1  jb      short loc_14003309F
0x1400330b3  mov     rax, [rsp+2D0h+var_290]
0x1400330b8  mov     rbx, [rsp+2D0h+var_280]
0x1400330bd  jmp     loc_140032D58
0x1400330c2  lea     rcx, [rsp+2D0h+var_270]
0x1400330c7  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x1400330cc  lea     rcx, [rsp+2D0h+var_268]
0x1400330d1  call    ?clear@?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAAXXZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear(void)
0x1400330d6  mov     rcx, [rbp+1D0h+var_50]
0x1400330dd  xor     rcx, rsp; StackCookie
0x1400330e0  call    __security_check_cookie
0x1400330e5  add     rsp, 298h
0x1400330ec  pop     r15
0x1400330ee  pop     r14
0x1400330f0  pop     r13
0x1400330f2  pop     r12
0x1400330f4  pop     rdi
0x1400330f5  pop     rsi
0x1400330f6  pop     rbx
0x1400330f7  pop     rbp
0x1400330f8  retn
```
