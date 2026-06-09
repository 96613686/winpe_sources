# ClusApi::ClusterHelper::CreateCluster(_CREATE_CLUSTER_CONFIG *,int (*)(void *,_CLUSTER_SETUP_PHASE,_CLUSTER_SETUP_PHASE_TYPE,_CLUSTER_SETUP_PHASE_SEVERITY,ulong,wchar_t const *,ulong),void *,std::shared_ptr<ClusApi::ICluster> *)

- ea: `0x180031a30`
- end: `0x180031ad5`
- name: `?CreateCluster@ClusterHelper@ClusApi@@UEAAJPEAU_CREATE_CLUSTER_CONFIG@@P6AHPEAXW4_CLUSTER_SETUP_PHASE@@W4_CLUSTER_SETUP_PHASE_TYPE@@W4_CLUSTER_SETUP_PHASE_SEVERITY@@KPEB_WK@Z1PEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000c5c4`
- `0x18001c8f0`
- `0x18001cf18`
- `0x180027b8c`
- `0x180031a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031aa7`
- `CLUSAPI!CreateCluster` at `0x180031a4b`
- `CLUSAPI!CreateCluster` at `0x180031a4b`

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
  _QWORD *Instance; // rax
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
      Instance = (_QWORD *)ClusWmi::DataStore::GetInstance(v11);
      v6 = ClusWmi::DataStore::GetCluster(*Instance, a5);
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
0x180031a30  push    rbx
0x180031a32  sub     rsp, 40h
0x180031a36  mov     rax, r8
0x180031a39  mov     rcx, rdx; pConfig
0x180031a3c  mov     [rsp+48h+var_28], 0
0x180031a45  mov     r8, r9; pvCallbackArg
0x180031a48  mov     rdx, rax; pfnProgressCallback
0x180031a4b  call    cs:__imp_CreateCluster
0x180031a52  nop     dword ptr [rax+rax+00h]
0x180031a57  mov     rbx, rax
0x180031a5a  lea     rcx, [rsp+48h+var_28]
0x180031a5f  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x180031a64  mov     [rsp+48h+var_28], rbx
0x180031a69  lea     rax, [rbx-1]
0x180031a6d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031a71  ja      short loc_180031AA7
0x180031a73  xor     ebx, ebx
0x180031a75  cmp     [rsp+48h+arg_20], rbx
0x180031a7a  jz      short loc_180031AC2
0x180031a7c  lea     rcx, [rsp+48h+var_20]
0x180031a81  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x180031a86  nop
0x180031a87  mov     rdx, [rsp+48h+arg_20]
0x180031a8c  mov     rcx, [rax]
0x180031a8f  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x180031a94  mov     ebx, eax
0x180031a96  mov     rcx, [rsp+48h+var_18]; this
0x180031a9b  test    rcx, rcx
0x180031a9e  jz      short loc_180031AC2
0x180031aa0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031aa5  jmp     short loc_180031AC2
0x180031aa7  call    cs:__imp_GetLastError
0x180031aae  nop     dword ptr [rax+rax+00h]
0x180031ab3  mov     ebx, eax
0x180031ab5  test    eax, eax
0x180031ab7  jle     short loc_180031AC2
0x180031ab9  movzx   ebx, ax
0x180031abc  or      ebx, 80070000h
0x180031ac2  lea     rcx, [rsp+48h+var_28]
0x180031ac7  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x180031acc  mov     eax, ebx
0x180031ace  add     rsp, 40h
0x180031ad2  pop     rbx
0x180031ad3  retn
```
