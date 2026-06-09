# ClusApi::ClusterHelper::CreateCluster(_CREATE_CLUSTER_CONFIG *,int (*)(void *,_CLUSTER_SETUP_PHASE,_CLUSTER_SETUP_PHASE_TYPE,_CLUSTER_SETUP_PHASE_SEVERITY,ulong,wchar_t const *,ulong),void *,std::shared_ptr<ClusApi::ICluster> *)

- ea: `0x18002dc10`
- end: `0x18002dcb5`
- name: `?CreateCluster@ClusterHelper@ClusApi@@UEAAJPEAU_CREATE_CLUSTER_CONFIG@@P6AHPEAXW4_CLUSTER_SETUP_PHASE@@W4_CLUSTER_SETUP_PHASE_TYPE@@W4_CLUSTER_SETUP_PHASE_SEVERITY@@KPEB_WK@Z1PEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000bc64`
- `0x180019720`
- `0x180019d40`
- `0x180023d4c`
- `0x18002dc10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc87`
- `CLUSAPI!CreateCluster` at `0x18002dc2b`
- `CLUSAPI!CreateCluster` at `0x18002dc2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ClusApi::ClusterHelper::CreateCluster(
        __int64 a1,
        struct _CREATE_CLUSTER_CONFIG *a2,
        BOOL (__stdcall *a3)(PVOID pvCallbackArg, CLUSTER_SETUP_PHASE eSetupPhase, CLUSTER_SETUP_PHASE_TYPE ePhaseType, CLUSTER_SETUP_PHASE_SEVERITY ePhaseSeverity, DWORD dwPercentComplete, PCWSTR lpszObjectName, DWORD dwStatus),
        void *a4,
        __int64 a5)
{
  HCLUSTER Cluster; // rbx
  unsigned int v6; // ebx
  struct ProtectedPwd **Instance; // rax
  signed int LastError; // eax
  HCLUSTER v10; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v11[8]; // [rsp+28h] [rbp-20h] BYREF
  std::_Ref_count_base *v12; // [rsp+30h] [rbp-18h]

  v10 = 0;
  Cluster = CreateCluster(a2, a3, a4);
  cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(&v10);
  v10 = Cluster;
  if ( (unsigned __int64)Cluster - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v6 = 0;
    if ( a5 )
    {
      Instance = (struct ProtectedPwd **)ClusWmi::DataStore::GetInstance(v11);
      v6 = ClusWmi::DataStore::GetCluster(*Instance);
      if ( v12 )
        std::_Ref_count_base::_Decref(v12);
    }
  }
  cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(&v10);
  return v6;
}

```

## disassembly

```asm
0x18002dc10  push    rbx
0x18002dc12  sub     rsp, 40h
0x18002dc16  mov     rax, r8
0x18002dc19  mov     rcx, rdx; pConfig
0x18002dc1c  mov     [rsp+48h+var_28], 0
0x18002dc25  mov     r8, r9; pvCallbackArg
0x18002dc28  mov     rdx, rax; pfnProgressCallback
0x18002dc2b  call    cs:__imp_CreateCluster
0x18002dc32  nop     dword ptr [rax+rax+00h]
0x18002dc37  mov     rbx, rax
0x18002dc3a  lea     rcx, [rsp+48h+var_28]
0x18002dc3f  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x18002dc44  mov     [rsp+48h+var_28], rbx
0x18002dc49  lea     rax, [rbx-1]
0x18002dc4d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002dc51  ja      short loc_18002DC87
0x18002dc53  xor     ebx, ebx
0x18002dc55  cmp     [rsp+48h+arg_20], rbx
0x18002dc5a  jz      short loc_18002DCA2
0x18002dc5c  lea     rcx, [rsp+48h+var_20]
0x18002dc61  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x18002dc66  nop
0x18002dc67  mov     rdx, [rsp+48h+arg_20]
0x18002dc6c  mov     rcx, [rax]; struct ProtectedPwd *
0x18002dc6f  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x18002dc74  mov     ebx, eax
0x18002dc76  mov     rcx, [rsp+48h+var_18]; this
0x18002dc7b  test    rcx, rcx
0x18002dc7e  jz      short loc_18002DCA2
0x18002dc80  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002dc85  jmp     short loc_18002DCA2
0x18002dc87  call    cs:__imp_GetLastError
0x18002dc8e  nop     dword ptr [rax+rax+00h]
0x18002dc93  mov     ebx, eax
0x18002dc95  test    eax, eax
0x18002dc97  jle     short loc_18002DCA2
0x18002dc99  movzx   ebx, ax
0x18002dc9c  or      ebx, 80070000h
0x18002dca2  lea     rcx, [rsp+48h+var_28]
0x18002dca7  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x18002dcac  mov     eax, ebx
0x18002dcae  add     rsp, 40h
0x18002dcb2  pop     rbx
0x18002dcb3  retn
```
