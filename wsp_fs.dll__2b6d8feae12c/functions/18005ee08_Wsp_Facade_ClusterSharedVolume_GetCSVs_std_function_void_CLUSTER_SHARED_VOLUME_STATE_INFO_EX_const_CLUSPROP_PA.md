# Wsp::Facade::ClusterSharedVolume::GetCSVs(std::function<void (_CLUSTER_SHARED_VOLUME_STATE_INFO_EX const *,CLUSPROP_PARTITION_INFO_EX const *)> const &)

- ea: `0x18005ee08`
- end: `0x18005ef86`
- name: `?GetCSVs@ClusterSharedVolume@Facade@Wsp@@CAXAEBV?$function@$$A6AXPEBU_CLUSTER_SHARED_VOLUME_STATE_INFO_EX@@PEBUCLUSPROP_PARTITION_INFO_EX@@@Z@std@@@Z`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18005e904`
- `0x18005ea70`

## callees

- `0x180003498`
- `0x180014630`
- `0x180024ae8`
- `0x180025888`
- `0x180026e8c`
- `0x180026f7c`
- `0x18005eb48`
- `0x18005ee08`

## import_xrefs

- `CLUSAPI!ClusterCloseEnum` at `0x18005ef67`
- `CLUSAPI!ClusterCloseEnum` at `0x18005ef67`
- `CLUSAPI!OpenClusterResource` at `0x18005ee9f`
- `CLUSAPI!OpenClusterResource` at `0x18005ee9f`
- `CLUSAPI!ClusterEnum` at `0x18005ee8e`
- `CLUSAPI!ClusterEnum` at `0x18005ee8e`
- `CLUSAPI!ClusterOpenEnum` at `0x18005ee41`
- `CLUSAPI!ClusterOpenEnum` at `0x18005ee41`
- `CLUSAPI!OpenCluster` at `0x18005ee1f`
- `CLUSAPI!OpenCluster` at `0x18005ee1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Wsp::Facade::ClusterSharedVolume::GetCSVs(__int64 a1)
{
  struct _HCLUSTER *v2; // rdi
  struct _HCLUSENUM *v3; // rbx
  DWORD v4; // r14d
  DWORD v5; // eax
  __int64 v6; // rax
  char *v7; // r15
  unsigned __int64 v8; // rcx
  WCHAR *v9; // rax
  size_t v10; // rsi
  _QWORD v12[2]; // [rsp+30h] [rbp-30h] BYREF
  LPWSTR lpszName; // [rsp+40h] [rbp-20h] BYREF
  void *v14; // [rsp+48h] [rbp-18h]
  __int64 v15; // [rsp+50h] [rbp-10h]
  DWORD cchName; // [rsp+A8h] [rbp+48h] BYREF
  DWORD dwType; // [rsp+B0h] [rbp+50h] BYREF
  HRESOURCE v18; // [rsp+B8h] [rbp+58h] BYREF

  v2 = OpenCluster(0);
  v12[0] = v2;
  if ( (unsigned __int64)v2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(v12);
  v3 = ClusterOpenEnum(v2, 0x40000000u);
  v12[1] = v3;
  if ( (unsigned __int64)v3 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(v12);
  dwType = 0;
  v4 = 0;
  cchName = 2048;
  std::vector<wchar_t>::vector<wchar_t>(&lpszName, 2048);
  while ( 1 )
  {
    while ( 1 )
    {
      v5 = ClusterEnum(v3, v4, &dwType, lpszName, &cchName);
      if ( !v5 )
        break;
      if ( v5 != 234 )
        goto LABEL_16;
      v6 = cchName + 1;
      cchName = v6;
      v7 = (char *)v14;
      v8 = ((_BYTE *)v14 - (_BYTE *)lpszName) >> 1;
      if ( (unsigned int)v6 < v8 )
      {
        v9 = &lpszName[v6];
        goto LABEL_10;
      }
      if ( (unsigned int)v6 > v8 )
      {
        if ( (unsigned int)v6 <= (unsigned __int64)((v15 - (__int64)lpszName) >> 1) )
        {
          v10 = 2 * ((unsigned int)v6 - v8);
          memset_0(v14, 0, v10);
          v9 = (WCHAR *)&v7[v10];
LABEL_10:
          v14 = v9;
        }
        else
        {
          std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&lpszName, (unsigned int)v6);
        }
      }
    }
    v18 = OpenClusterResource(v2, lpszName);
    if ( (unsigned __int64)v18 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      break;
    ++v4;
    Wsp::Facade::ClusterSharedVolume::GetCSVInfo(&v18, a1);
    cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v18);
  }
  cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v18);
LABEL_16:
  std::vector<unsigned short>::_Tidy(&lpszName);
  ClusterCloseEnum(v3);
  return cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(v12);
}

```

## disassembly

```asm
0x18005ee08  push    rbp
0x18005ee0a  push    rbx
0x18005ee0b  push    rsi
0x18005ee0c  push    rdi
0x18005ee0d  push    r12
0x18005ee0f  push    r14
0x18005ee11  push    r15
0x18005ee13  mov     rbp, rsp
0x18005ee16  sub     rsp, 60h
0x18005ee1a  mov     r12, rcx
0x18005ee1d  xor     ecx, ecx; lpszClusterName
0x18005ee1f  call    cs:__imp_OpenCluster
0x18005ee25  mov     rdi, rax
0x18005ee28  mov     [rbp+var_30], rax
0x18005ee2c  dec     rax
0x18005ee2f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005ee33  ja      loc_18005EF6E
0x18005ee39  mov     edx, 40000000h; dwType
0x18005ee3e  mov     rcx, rdi; hCluster
0x18005ee41  call    cs:__imp_ClusterOpenEnum
0x18005ee47  mov     rbx, rax
0x18005ee4a  mov     [rbp+var_28], rax
0x18005ee4e  dec     rax
0x18005ee51  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005ee55  ja      loc_18005EF5A
0x18005ee5b  mov     [rbp+dwType], 0
0x18005ee62  xor     r14d, r14d
0x18005ee65  mov     edx, 800h
0x18005ee6a  mov     [rbp+cchName], edx
0x18005ee6d  lea     rcx, [rbp+lpszName]
0x18005ee71  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18005ee76  nop
0x18005ee77  lea     rax, [rbp+cchName]
0x18005ee7b  mov     [rsp+60h+lpcchName], rax; lpcchName
0x18005ee80  mov     r9, [rbp+lpszName]; lpszName
0x18005ee84  lea     r8, [rbp+dwType]; lpdwType
0x18005ee88  mov     edx, r14d; dwIndex
0x18005ee8b  mov     rcx, rbx; hEnum
0x18005ee8e  call    cs:__imp_ClusterEnum
0x18005ee94  test    eax, eax
0x18005ee96  jnz     short loc_18005EED1
0x18005ee98  mov     rdx, [rbp+lpszName]; lpszResourceName
0x18005ee9c  mov     rcx, rdi; hCluster
0x18005ee9f  call    cs:__imp_OpenClusterResource
0x18005eea5  mov     [rbp+arg_18], rax
0x18005eea9  dec     rax
0x18005eeac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005eeb0  ja      loc_18005EF44
0x18005eeb6  inc     r14d
0x18005eeb9  mov     rdx, r12
0x18005eebc  lea     rcx, [rbp+arg_18]
0x18005eec0  call    ?GetCSVInfo@ClusterSharedVolume@Facade@Wsp@@CAXAEBU?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@AEBV?$function@$$A6AXPEBU_CLUSTER_SHARED_VOLUME_STATE_INFO_EX@@PEBUCLUSPROP_PARTITION_INFO_EX@@@Z@std@@@Z; Wsp::Facade::ClusterSharedVolume::GetCSVInfo(cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0> const &,std::function<void (_CLUSTER_SHARED_VOLUME_STATE_INFO_EX const *,CLUSPROP_PARTITION_INFO_EX const *)> const &)
0x18005eec5  nop
0x18005eec6  lea     rcx, [rbp+arg_18]
0x18005eeca  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18005eecf  jmp     short loc_18005EE77
0x18005eed1  cmp     eax, 0EAh
0x18005eed6  jnz     short loc_18005EF4E
0x18005eed8  mov     eax, [rbp+cchName]
0x18005eedb  inc     eax
0x18005eedd  mov     [rbp+cchName], eax
0x18005eee0  mov     esi, eax
0x18005eee2  mov     rdx, [rbp+lpszName]
0x18005eee6  mov     r15, [rbp+var_18]
0x18005eeea  mov     rcx, r15
0x18005eeed  sub     rcx, rdx
0x18005eef0  sar     rcx, 1
0x18005eef3  cmp     rsi, rcx
0x18005eef6  jnb     short loc_18005EF05
0x18005eef8  lea     rax, [rdx+rax*2]
0x18005eefc  mov     [rbp+var_18], rax
0x18005ef00  jmp     loc_18005EE77
0x18005ef05  jbe     loc_18005EE77
0x18005ef0b  mov     rax, [rbp+var_10]
0x18005ef0f  sub     rax, rdx
0x18005ef12  sar     rax, 1
0x18005ef15  cmp     rsi, rax
0x18005ef18  jbe     short loc_18005EF2B
0x18005ef1a  mov     rdx, rsi
0x18005ef1d  lea     rcx, [rbp+lpszName]
0x18005ef21  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005ef26  jmp     loc_18005EE77
0x18005ef2b  sub     rsi, rcx
0x18005ef2e  add     rsi, rsi
0x18005ef31  mov     r8, rsi; Size
0x18005ef34  xor     edx, edx; Val
0x18005ef36  mov     rcx, r15; void *
0x18005ef39  call    memset_0
0x18005ef3e  lea     rax, [rsi+r15]
0x18005ef42  jmp     short loc_18005EEFC
0x18005ef44  lea     rcx, [rbp+arg_18]
0x18005ef48  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18005ef4d  nop
0x18005ef4e  lea     rcx, [rbp+lpszName]
0x18005ef52  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18005ef57  nop
0x18005ef58  jmp     short loc_18005EF64
0x18005ef5a  lea     rax, [rbx-1]
0x18005ef5e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005ef62  ja      short loc_18005EF6E
0x18005ef64  mov     rcx, rbx; hEnum
0x18005ef67  call    cs:__imp_ClusterCloseEnum
0x18005ef6d  nop
0x18005ef6e  lea     rcx, [rbp+var_30]
0x18005ef72  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x18005ef77  add     rsp, 60h
0x18005ef7b  pop     r15
0x18005ef7d  pop     r14
0x18005ef7f  pop     r12
0x18005ef81  pop     rdi
0x18005ef82  pop     rsi
0x18005ef83  pop     rbx
0x18005ef84  pop     rbp
0x18005ef85  retn
```
