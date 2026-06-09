# CTrkWksSvc::UnInitialize(long)

- ea: `0x1800016f4`
- end: `0x1800017d6`
- name: `?UnInitialize@CTrkWksSvc@@QEAAXJ@Z`
- size: `226`
- prototype: `void __fastcall(CTrkWksSvc *__hidden this, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ef50`

## callees

- `0x1800016f4`
- `0x180001940`
- `0x1800019c8`
- `0x180001b64`
- `0x18000c7c0`
- `0x18000d4dc`
- `0x18000d5e4`
- `0x18000d9e4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000179d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000179d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180001758`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180001758`

## pseudocode

```c
void __fastcall CTrkWksSvc::UnInitialize(CTrkWksSvc *this, int a2)
{
  CVolumeManager *v3; // rdi
  void *v4; // rdx
  CActiveThreadList *v5; // rcx

  if ( (*((_BYTE *)this + 368) & 1) != 0 )
  {
    v3 = (CTrkWksSvc *)((char *)this + 576);
    CVolumeManager::FlushAllVolumes((CTrkWksSvc *)((char *)this + 576), a2);
    CVolumeManager::CloseVolumeHandles(v3, v4);
    if ( g_pActiveThreadList )
      CActiveThreadList::CancelAllRpc(v5);
    CRpcServer::UnInitialize((CTrkWksSvc *)((char *)this + 448));
    CPort::UnInitialize((CTrkWksSvc *)((char *)this + 384));
    if ( CVerifyAuthentication::_psidAuthenticatedUsersGroup )
    {
      FreeSid(CVerifyAuthentication::_psidAuthenticatedUsersGroup);
      CVerifyAuthentication::_psidAuthenticatedUsersGroup = 0;
    }
    CVolumeManager::UnInitialize(v3);
    *((_DWORD *)this + 260) = 0;
    if ( *((_DWORD *)this + 12) )
      *((_DWORD *)this + 12) = 0;
    *((_DWORD *)this + 92) &= ~1u;
    if ( (*((_BYTE *)this + 552) & 2) != 0 )
      Sleep(0xEA60u);
    g_ptrkwks = 0;
    CTrkRpcConfig::_fInitialized = 0;
    CSvcCtrlInterface::SetServiceStatus((CTrkWksSvc *)((char *)this + 496), 1u, 0);
  }
}

```

## disassembly

```asm
0x1800016f4  mov     [rsp+arg_0], rbx
0x1800016f9  push    rdi
0x1800016fa  sub     rsp, 20h
0x1800016fe  test    byte ptr [rcx+170h], 1
0x180001705  mov     rbx, rcx
0x180001708  jz      loc_1800017CB
0x18000170e  lea     rdi, [rcx+240h]
0x180001715  mov     rcx, rdi; this
0x180001718  call    ?FlushAllVolumes@CVolumeManager@@QEAAXH@Z; CVolumeManager::FlushAllVolumes(int)
0x18000171d  mov     rcx, rdi; this
0x180001720  call    ?CloseVolumeHandles@CVolumeManager@@QEAAXPEAX@Z; CVolumeManager::CloseVolumeHandles(void *)
0x180001725  cmp     cs:g_pActiveThreadList, 0
0x18000172d  jz      short loc_180001734
0x18000172f  call    ?CancelAllRpc@CActiveThreadList@@QEAAXXZ; CActiveThreadList::CancelAllRpc(void)
0x180001734  lea     rcx, [rbx+1C0h]; this
0x18000173b  call    ?UnInitialize@CRpcServer@@QEAAXXZ; CRpcServer::UnInitialize(void)
0x180001740  lea     rcx, [rbx+180h]; this
0x180001747  call    ?UnInitialize@CPort@@QEAAXXZ; CPort::UnInitialize(void)
0x18000174c  mov     rcx, cs:?_psidAuthenticatedUsersGroup@CVerifyAuthentication@@0PEAXEA; pSid
0x180001753  test    rcx, rcx
0x180001756  jz      short loc_180001769
0x180001758  call    cs:__imp_FreeSid
0x18000175e  mov     cs:?_psidAuthenticatedUsersGroup@CVerifyAuthentication@@0PEAXEA, 0; void * CVerifyAuthentication::_psidAuthenticatedUsersGroup
0x180001769  mov     rcx, rdi; this
0x18000176c  call    ?UnInitialize@CVolumeManager@@QEAAXXZ; CVolumeManager::UnInitialize(void)
0x180001771  mov     dword ptr [rbx+410h], 0
0x18000177b  cmp     dword ptr [rbx+30h], 0
0x18000177f  jz      short loc_180001788
0x180001781  mov     dword ptr [rbx+30h], 0
0x180001788  and     dword ptr [rbx+170h], 0FFFFFFFEh
0x18000178f  test    byte ptr [rbx+228h], 2
0x180001796  jz      short loc_1800017A3
0x180001798  mov     ecx, 0EA60h; dwMilliseconds
0x18000179d  call    cs:__imp_Sleep
0x1800017a3  xor     r8d, r8d; unsigned int
0x1800017a6  mov     cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA, 0; CTrkWksSvc * g_ptrkwks
0x1800017b1  lea     rcx, [rbx+1F0h]; this
0x1800017b8  mov     cs:?_fInitialized@CTrkRpcConfig@@1HA, 0; int CTrkRpcConfig::_fInitialized
0x1800017c2  lea     edx, [r8+1]; unsigned int
0x1800017c6  call    ?SetServiceStatus@CSvcCtrlInterface@@QEAAXKKK@Z; CSvcCtrlInterface::SetServiceStatus(ulong,ulong,ulong)
0x1800017cb  mov     rbx, [rsp+28h+arg_0]
0x1800017d0  add     rsp, 20h
0x1800017d4  pop     rdi
0x1800017d5  retn
```
