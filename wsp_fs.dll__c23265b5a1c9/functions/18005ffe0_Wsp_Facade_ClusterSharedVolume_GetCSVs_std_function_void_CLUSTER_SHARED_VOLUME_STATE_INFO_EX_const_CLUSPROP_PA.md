# Wsp::Facade::ClusterSharedVolume::GetCSVs(std::function<void (_CLUSTER_SHARED_VOLUME_STATE_INFO_EX const *,CLUSPROP_PARTITION_INFO_EX const *)> const &)

- ea: `0x18005ffe0`
- end: `0x18006017d`
- name: `?GetCSVs@ClusterSharedVolume@Facade@Wsp@@CAXAEBV?$function@$$A6AXPEBU_CLUSTER_SHARED_VOLUME_STATE_INFO_EX@@PEBUCLUSPROP_PARTITION_INFO_EX@@@Z@std@@@Z`
- size: `413`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18005fad4`
- `0x18005fc40`

## callees

- `0x180003528`
- `0x180014c94`
- `0x1800257dc`
- `0x180026588`
- `0x180027b8c`
- `0x180027ca4`
- `0x18005fd18`
- `0x18005ffe0`

## import_xrefs

- `CLUSAPI!ClusterCloseEnum` at `0x180060157`
- `CLUSAPI!ClusterCloseEnum` at `0x180060157`
- `CLUSAPI!OpenClusterResource` at `0x180060089`
- `CLUSAPI!OpenClusterResource` at `0x180060089`
- `CLUSAPI!ClusterEnum` at `0x180060072`
- `CLUSAPI!ClusterEnum` at `0x180060072`
- `CLUSAPI!ClusterOpenEnum` at `0x18006001f`
- `CLUSAPI!ClusterOpenEnum` at `0x18006001f`
- `CLUSAPI!OpenCluster` at `0x18005fff7`
- `CLUSAPI!OpenCluster` at `0x18005fff7`

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
0x18005ffe0  push    rbp
0x18005ffe2  push    rbx
0x18005ffe3  push    rsi
0x18005ffe4  push    rdi
0x18005ffe5  push    r12
0x18005ffe7  push    r14
0x18005ffe9  push    r15
0x18005ffeb  mov     rbp, rsp
0x18005ffee  sub     rsp, 60h
0x18005fff2  mov     r12, rcx
0x18005fff5  xor     ecx, ecx; lpszClusterName
0x18005fff7  call    cs:__imp_OpenCluster
0x18005fffe  nop     dword ptr [rax+rax+00h]
0x180060003  mov     rdi, rax
0x180060006  mov     [rbp+var_30], rax
0x18006000a  dec     rax
0x18006000d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180060011  ja      loc_180060164
0x180060017  mov     edx, 40000000h; dwType
0x18006001c  mov     rcx, rdi; hCluster
0x18006001f  call    cs:__imp_ClusterOpenEnum
0x180060026  nop     dword ptr [rax+rax+00h]
0x18006002b  mov     rbx, rax
0x18006002e  mov     [rbp+var_28], rax
0x180060032  dec     rax
0x180060035  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180060039  ja      loc_18006014A
0x18006003f  mov     [rbp+dwType], 0
0x180060046  xor     r14d, r14d
0x180060049  mov     edx, 800h
0x18006004e  mov     [rbp+cchName], edx
0x180060051  lea     rcx, [rbp+lpszName]
0x180060055  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18006005a  nop
0x18006005b  lea     rax, [rbp+cchName]
0x18006005f  mov     [rsp+60h+lpcchName], rax; lpcchName
0x180060064  mov     r9, [rbp+lpszName]; lpszName
0x180060068  lea     r8, [rbp+dwType]; lpdwType
0x18006006c  mov     edx, r14d; dwIndex
0x18006006f  mov     rcx, rbx; hEnum
0x180060072  call    cs:__imp_ClusterEnum
0x180060079  nop     dword ptr [rax+rax+00h]
0x18006007e  test    eax, eax
0x180060080  jnz     short loc_1800600C1
0x180060082  mov     rdx, [rbp+lpszName]; lpszResourceName
0x180060086  mov     rcx, rdi; hCluster
0x180060089  call    cs:__imp_OpenClusterResource
0x180060090  nop     dword ptr [rax+rax+00h]
0x180060095  mov     [rbp+arg_18], rax
0x180060099  dec     rax
0x18006009c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800600a0  ja      loc_180060134
0x1800600a6  inc     r14d
0x1800600a9  mov     rdx, r12
0x1800600ac  lea     rcx, [rbp+arg_18]
0x1800600b0  call    ?GetCSVInfo@ClusterSharedVolume@Facade@Wsp@@CAXAEBU?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@AEBV?$function@$$A6AXPEBU_CLUSTER_SHARED_VOLUME_STATE_INFO_EX@@PEBUCLUSPROP_PARTITION_INFO_EX@@@Z@std@@@Z; Wsp::Facade::ClusterSharedVolume::GetCSVInfo(cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0> const &,std::function<void (_CLUSTER_SHARED_VOLUME_STATE_INFO_EX const *,CLUSPROP_PARTITION_INFO_EX const *)> const &)
0x1800600b5  nop
0x1800600b6  lea     rcx, [rbp+arg_18]
0x1800600ba  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x1800600bf  jmp     short loc_18006005B
0x1800600c1  cmp     eax, 0EAh
0x1800600c6  jnz     short loc_18006013E
0x1800600c8  mov     eax, [rbp+cchName]
0x1800600cb  inc     eax
0x1800600cd  mov     [rbp+cchName], eax
0x1800600d0  mov     esi, eax
0x1800600d2  mov     rdx, [rbp+lpszName]
0x1800600d6  mov     r15, [rbp+var_18]
0x1800600da  mov     rcx, r15
0x1800600dd  sub     rcx, rdx
0x1800600e0  sar     rcx, 1
0x1800600e3  cmp     rsi, rcx
0x1800600e6  jnb     short loc_1800600F5
0x1800600e8  lea     rax, [rdx+rax*2]
0x1800600ec  mov     [rbp+var_18], rax
0x1800600f0  jmp     loc_18006005B
0x1800600f5  jbe     loc_18006005B
0x1800600fb  mov     rax, [rbp+var_10]
0x1800600ff  sub     rax, rdx
0x180060102  sar     rax, 1
0x180060105  cmp     rsi, rax
0x180060108  jbe     short loc_18006011B
0x18006010a  mov     rdx, rsi
0x18006010d  lea     rcx, [rbp+lpszName]
0x180060111  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180060116  jmp     loc_18006005B
0x18006011b  sub     rsi, rcx
0x18006011e  add     rsi, rsi
0x180060121  mov     r8, rsi; Size
0x180060124  xor     edx, edx; Val
0x180060126  mov     rcx, r15; void *
0x180060129  call    memset_0
0x18006012e  lea     rax, [rsi+r15]
0x180060132  jmp     short loc_1800600EC
0x180060134  lea     rcx, [rbp+arg_18]
0x180060138  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18006013d  nop
0x18006013e  lea     rcx, [rbp+lpszName]
0x180060142  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180060147  nop
0x180060148  jmp     short loc_180060154
0x18006014a  lea     rax, [rbx-1]
0x18006014e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180060152  ja      short loc_180060164
0x180060154  mov     rcx, rbx; hEnum
0x180060157  call    cs:__imp_ClusterCloseEnum
0x18006015e  nop     dword ptr [rax+rax+00h]
0x180060163  nop
0x180060164  lea     rcx, [rbp+var_30]
0x180060168  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x18006016d  add     rsp, 60h
0x180060171  pop     r15
0x180060173  pop     r14
0x180060175  pop     r12
0x180060177  pop     rdi
0x180060178  pop     rsi
0x180060179  pop     rbx
0x18006017a  pop     rbp
0x18006017b  retn
```
