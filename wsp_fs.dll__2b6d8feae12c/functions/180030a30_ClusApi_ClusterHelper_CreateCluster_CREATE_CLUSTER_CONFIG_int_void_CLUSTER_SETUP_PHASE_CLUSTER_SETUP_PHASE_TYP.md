# ClusApi::ClusterHelper::CreateCluster(_CREATE_CLUSTER_CONFIG *,int (*)(void *,_CLUSTER_SETUP_PHASE,_CLUSTER_SETUP_PHASE_TYPE,_CLUSTER_SETUP_PHASE_SEVERITY,ulong,wchar_t const *,ulong),void *,std::shared_ptr<ClusApi::ICluster> *)

- ea: `0x180030a30`
- end: `0x180030ac8`
- name: `?CreateCluster@ClusterHelper@ClusApi@@UEAAJPEAU_CREATE_CLUSTER_CONFIG@@P6AHPEAXW4_CLUSTER_SETUP_PHASE@@W4_CLUSTER_SETUP_PHASE_TYPE@@W4_CLUSTER_SETUP_PHASE_SEVERITY@@KPEB_WK@Z1PEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000c284`
- `0x18001be30`
- `0x18001c424`
- `0x180026e8c`
- `0x180030a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030aa1`
- `CLUSAPI!CreateCluster` at `0x180030a4b`
- `CLUSAPI!CreateCluster` at `0x180030a4b`

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
0x180030a30  push    rbx
0x180030a32  sub     rsp, 40h
0x180030a36  mov     rax, r8
0x180030a39  mov     rcx, rdx; pConfig
0x180030a3c  mov     [rsp+48h+var_28], 0
0x180030a45  mov     r8, r9; pvCallbackArg
0x180030a48  mov     rdx, rax; pfnProgressCallback
0x180030a4b  call    cs:__imp_CreateCluster
0x180030a51  mov     rbx, rax
0x180030a54  lea     rcx, [rsp+48h+var_28]
0x180030a59  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x180030a5e  mov     [rsp+48h+var_28], rbx
0x180030a63  lea     rax, [rbx-1]
0x180030a67  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180030a6b  ja      short loc_180030AA1
0x180030a6d  xor     ebx, ebx
0x180030a6f  cmp     [rsp+48h+arg_20], rbx
0x180030a74  jz      short loc_180030AB6
0x180030a76  lea     rcx, [rsp+48h+var_20]
0x180030a7b  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x180030a80  nop
0x180030a81  mov     rdx, [rsp+48h+arg_20]
0x180030a86  mov     rcx, [rax]
0x180030a89  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x180030a8e  mov     ebx, eax
0x180030a90  mov     rcx, [rsp+48h+var_18]; this
0x180030a95  test    rcx, rcx
0x180030a98  jz      short loc_180030AB6
0x180030a9a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180030a9f  jmp     short loc_180030AB6
0x180030aa1  call    cs:__imp_GetLastError
0x180030aa7  mov     ebx, eax
0x180030aa9  test    eax, eax
0x180030aab  jle     short loc_180030AB6
0x180030aad  movzx   ebx, ax
0x180030ab0  or      ebx, 80070000h
0x180030ab6  lea     rcx, [rsp+48h+var_28]
0x180030abb  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x180030ac0  mov     eax, ebx
0x180030ac2  add     rsp, 40h
0x180030ac6  pop     rbx
0x180030ac7  retn
```
