# RDCameraServiceExtension::ServiceControlHandler(ulong,ulong,void *)

- ea: `0x180004b90`
- end: `0x180004d30`
- name: `?ServiceControlHandler@RDCameraServiceExtension@@UEAAKKKPEAX@Z`
- size: `416`
- prototype: `unsigned int __fastcall(RDCameraServiceExtension *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004b90`
- `0x180007ce0`
- `0x180009bc0`
- `0x18000a4f0`
- `0x18000afb8`
- `0x18000b8f8`
- `0x18000b98c`
- `0x180031a98`
- `0x180031d24`
- `0x180033374`
- `0x180049010`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180004d17`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180004d17`

## pseudocode

```c
__int64 __fastcall RDCameraServiceExtension::ServiceControlHandler(
        RDCameraServiceExtension *this,
        __int64 a2,
        __int64 a3,
        _DWORD *a4)
{
  unsigned int v6; // edx
  int v7; // r8d
  unsigned int v8; // ebp
  char *i; // rsi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  char v14; // r14
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int j; // ebp
  PVOID pv[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( (_DWORD)a2 == 5 || (a2 = (unsigned int)(a2 - 1), !(_DWORD)a2) )
  {
    v8 = 0;
    for ( i = (char *)this + 32; v8 < *((_DWORD *)this + 9); ++v8 )
    {
      pv[0] = 0;
      Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(pv, a2, a3, a4);
      if ( (unsigned int)SmartArray<RDCameraDeviceManager,unsigned long>::GetAt(i, v8, pv) )
      {
        if ( pv[0] )
        {
          v13 = RDCameraDeviceManager::Terminate(pv[0]);
          v14 = v13;
          if ( v13 < 0
            && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
            && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
              22,
              (unsigned int)WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids,
              CurrentThreadActivityIdPrefix,
              (__int64)"spDeviceManager->Terminate failed",
              v14);
          }
        }
      }
      Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(pv, v10, v11, v12);
    }
    for ( j = 0; j < *((_DWORD *)i + 1); ++j )
    {
      pv[0] = 0;
      if ( (unsigned int)DynArray<SmartArray<RDCameraDeviceManager,unsigned long>::CCleanType,unsigned long>::GetAt(
                           i,
                           j,
                           pv,
                           a4)
        && pv[0] )
      {
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
        pv[0] = 0;
        DynArray<SmartArray<RDCameraDeviceManager,unsigned long>::CCleanType,unsigned long>::AddAt(i, j, pv);
        --*((_DWORD *)i + 4);
      }
    }
    *((_DWORD *)i + 1) = 0;
    CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 18), 0, 0);
  }
  else
  {
    if ( (_DWORD)a2 != 13 )
      return 120;
    v6 = a4[1];
    v7 = a3 - 3;
    if ( v7 )
    {
      if ( v7 == 1 )
        RDCameraServiceExtension::OnRemoteDisconnect(this, v6);
    }
    else
    {
      RDCameraServiceExtension::OnRemoteConnect(this, v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004b90  push    rbx
0x180004b92  push    rdi
0x180004b93  sub     rsp, 48h
0x180004b97  xor     edi, edi
0x180004b99  mov     rbx, rcx
0x180004b9c  cmp     edx, 5
0x180004b9f  jz      short loc_180004BDD
0x180004ba1  sub     edx, 1
0x180004ba4  jz      short loc_180004BDD
0x180004ba6  cmp     edx, 0Dh
0x180004ba9  jz      short loc_180004BB5
0x180004bab  mov     eax, 78h ; 'x'
0x180004bb0  jmp     loc_180004D29
0x180004bb5  mov     edx, [r9+4]; unsigned int
0x180004bb9  sub     r8d, 3
0x180004bbd  jz      short loc_180004BD3
0x180004bbf  cmp     r8d, 1
0x180004bc3  jnz     loc_180004D27
0x180004bc9  call    ?OnRemoteDisconnect@RDCameraServiceExtension@@AEAAXK@Z; RDCameraServiceExtension::OnRemoteDisconnect(ulong)
0x180004bce  jmp     loc_180004D27
0x180004bd3  call    ?OnRemoteConnect@RDCameraServiceExtension@@AEAAXK@Z; RDCameraServiceExtension::OnRemoteConnect(ulong)
0x180004bd8  jmp     loc_180004D27
0x180004bdd  mov     [rsp+58h+arg_0], rbp
0x180004be2  xor     ebp, ebp
0x180004be4  mov     [rsp+58h+arg_8], rsi
0x180004be9  lea     rsi, [rcx+20h]
0x180004bed  cmp     [rcx+24h], edi
0x180004bf0  jbe     loc_180004CB5
0x180004bf6  mov     [rsp+58h+arg_10], r12
0x180004bfb  lea     r12, aSpdevicemanage; "spDeviceManager->Terminate failed"
0x180004c02  mov     [rsp+58h+var_18], r15
0x180004c07  lea     r15, WPP_GLOBAL_Control
0x180004c0e  mov     [rsp+58h+arg_18], r14
0x180004c13  lea     rcx, [rsp+58h+pv]
0x180004c18  mov     [rsp+58h+pv], rdi
0x180004c1d  call    ?InternalRelease@?$ComPtr@UIServerVCChannelManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(void)
0x180004c22  lea     r8, [rsp+58h+pv]
0x180004c27  mov     edx, ebp
0x180004c29  mov     rcx, rsi
0x180004c2c  call    ?GetAt@?$SmartArray@VRDCameraDeviceManager@@K@@QEAAHKPEAPEAVRDCameraDeviceManager@@@Z; SmartArray<RDCameraDeviceManager,ulong>::GetAt(ulong,RDCameraDeviceManager * *)
0x180004c31  test    eax, eax
0x180004c33  jz      short loc_180004C91
0x180004c35  mov     rcx, [rsp+58h+pv]; pv
0x180004c3a  test    rcx, rcx
0x180004c3d  jz      short loc_180004C91
0x180004c3f  call    ?Terminate@RDCameraDeviceManager@@QEAAJXZ; RDCameraDeviceManager::Terminate(void)
0x180004c44  mov     r14d, eax
0x180004c47  test    eax, eax
0x180004c49  jns     short loc_180004C91
0x180004c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c52  cmp     rcx, r15
0x180004c55  jz      short loc_180004C91
0x180004c57  test    byte ptr [rcx+1Ch], 8
0x180004c5b  jz      short loc_180004C91
0x180004c5d  cmp     byte ptr [rcx+19h], 2
0x180004c61  jb      short loc_180004C91
0x180004c63  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180004c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c6f  lea     r8, WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids
0x180004c76  mov     edx, 16h
0x180004c7b  mov     [rsp+58h+var_30], r14d
0x180004c80  mov     r9d, eax
0x180004c83  mov     [rsp+58h+var_38], r12
0x180004c88  mov     rcx, [rcx+10h]
0x180004c8c  call    WPP_SF_DsD
0x180004c91  lea     rcx, [rsp+58h+pv]
0x180004c96  call    ?InternalRelease@?$ComPtr@UIServerVCChannelManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(void)
0x180004c9b  inc     ebp
0x180004c9d  cmp     ebp, [rbx+24h]
0x180004ca0  jb      loc_180004C13
0x180004ca6  mov     r15, [rsp+58h+var_18]
0x180004cab  mov     r14, [rsp+58h+arg_18]
0x180004cb0  mov     r12, [rsp+58h+arg_10]
0x180004cb5  xor     ebp, ebp
0x180004cb7  cmp     [rsi+4], edi
0x180004cba  jbe     short loc_180004D08
0x180004cbc  lea     r8, [rsp+58h+pv]
0x180004cc1  mov     [rsp+58h+pv], rdi
0x180004cc6  mov     edx, ebp
0x180004cc8  mov     rcx, rsi
0x180004ccb  call    ?GetAt@?$DynArray@VCCleanType@?$SmartArray@VRDCameraDeviceManager@@K@@K@@QEAAHKPEAVCCleanType@?$SmartArray@VRDCameraDeviceManager@@K@@@Z; DynArray<SmartArray<RDCameraDeviceManager,ulong>::CCleanType,ulong>::GetAt(ulong,SmartArray<RDCameraDeviceManager,ulong>::CCleanType *)
0x180004cd0  test    eax, eax
0x180004cd2  jz      short loc_180004D01
0x180004cd4  mov     rcx, [rsp+58h+pv]
0x180004cd9  test    rcx, rcx
0x180004cdc  jz      short loc_180004D01
0x180004cde  mov     rax, [rcx]
0x180004ce1  mov     rax, [rax+10h]
0x180004ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cea  lea     r8, [rsp+58h+pv]
0x180004cef  mov     [rsp+58h+pv], rdi
0x180004cf4  mov     edx, ebp
0x180004cf6  mov     rcx, rsi
0x180004cf9  call    ?AddAt@?$DynArray@VCCleanType@?$SmartArray@VRDCameraDeviceManager@@K@@K@@QEAAHKAEAVCCleanType@?$SmartArray@VRDCameraDeviceManager@@K@@@Z; DynArray<SmartArray<RDCameraDeviceManager,ulong>::CCleanType,ulong>::AddAt(ulong,SmartArray<RDCameraDeviceManager,ulong>::CCleanType &)
0x180004cfe  dec     dword ptr [rsi+10h]
0x180004d01  inc     ebp
0x180004d03  cmp     ebp, [rsi+4]
0x180004d06  jb      short loc_180004CBC
0x180004d08  mov     [rsi+4], edi
0x180004d0b  xor     r8d, r8d; pvCleanupContext
0x180004d0e  mov     rcx, [rbx+90h]; ptpcg
0x180004d15  xor     edx, edx; fCancelPendingCallbacks
0x180004d17  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180004d1d  mov     rsi, [rsp+58h+arg_8]
0x180004d22  mov     rbp, [rsp+58h+arg_0]
0x180004d27  mov     eax, edi
0x180004d29  add     rsp, 48h
0x180004d2d  pop     rdi
0x180004d2e  pop     rbx
0x180004d2f  retn
```
