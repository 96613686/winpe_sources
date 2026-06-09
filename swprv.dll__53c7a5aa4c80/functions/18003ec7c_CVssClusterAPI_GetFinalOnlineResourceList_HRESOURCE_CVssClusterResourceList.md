# CVssClusterAPI::GetFinalOnlineResourceList(_HRESOURCE *,CVssClusterResourceList &)

- ea: `0x18003ec7c`
- end: `0x18003ef4e`
- name: `?GetFinalOnlineResourceList@CVssClusterAPI@@AEAAXPEAU_HRESOURCE@@AEAVCVssClusterResourceList@@@Z`
- size: `722`
- prototype: `void __fastcall(HCLUSTER *this, struct _HRESOURCE *, struct CVssClusterResourceList *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18003e054`
- `0x18003ff6c`

## callees

- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x18003df54`
- `0x18003dfac`
- `0x18003ec7c`
- `0x18003fe60`
- `0x18003feac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ee02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ee02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003edea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ef19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003edea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ef19`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x18003ee44`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x18003ee44`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceCloseEnum` at `0x18003ee7f`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceCloseEnum` at `0x18003ee7f`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceOpenEnum` at `0x18003ed86`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceOpenEnum` at `0x18003ed86`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceGetEnumCount` at `0x18003ed92`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceGetEnumCount` at `0x18003ed92`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceEnum` at `0x18003edc6`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceEnum` at `0x18003ee2b`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceEnum` at `0x18003edc6`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceEnum` at `0x18003ee2b`
- `ext-ms-win-cluster-clusapi-l1-1-2!GetClusterResourceState` at `0x18003ed24`
- `ext-ms-win-cluster-clusapi-l1-1-2!GetClusterResourceState` at `0x18003ee61`
- `ext-ms-win-cluster-clusapi-l1-1-2!GetClusterResourceState` at `0x18003ed24`
- `ext-ms-win-cluster-clusapi-l1-1-2!GetClusterResourceState` at `0x18003ee61`

## pseudocode

```c
void __fastcall CVssClusterAPI::GetFinalOnlineResourceList(
        HCLUSTER *this,
        struct _HRESOURCE *a2,
        struct CVssClusterResourceList *a3)
{
  WCHAR *v5; // rbx
  DWORD v6; // r15d
  struct _HRESOURCE *v7; // rdi
  struct _HRESENUM *v8; // r14
  DWORD EnumCount; // r12d
  DWORD i; // esi
  DWORD v11; // eax
  signed int v12; // edi
  struct _HRESOURCE *v13; // rdi
  DWORD dwType; // [rsp+30h] [rbp-D0h] BYREF
  HRESOURCE hResource; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v16; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v17; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v18; // [rsp+50h] [rbp-B0h]
  int v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+5Ch] [rbp-A4h]
  int v21; // [rsp+60h] [rbp-A0h]
  _BYTE v22[120]; // [rsp+68h] [rbp-98h] BYREF
  int v23; // [rsp+E0h] [rbp-20h]
  _BYTE v24[40]; // [rsp+E8h] [rbp-18h] BYREF
  LPVOID v25[20]; // [rsp+110h] [rbp+10h] BYREF
  DWORD cchName; // [rsp+1D8h] [rbp+D8h] BYREF

  v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v17 = L"CVssClusterAPI::GetFinalOnlineResourceList";
  v18 = L"CLUCLUSC";
  v19 = 1451;
  v20 = 11;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v25, (__int64)&v16, 0);
  dwType = 0;
  if ( GetClusterResourceState(a2, 0, 0, 0, 0) == ClusterResourceOnline )
  {
    v5 = 0;
    v6 = 0;
    CVssClusterResourceList::CVssClusterResourceList((CVssClusterResourceList *)v24);
    CVssClusterResourceList::Push((CVssClusterResourceList *)v24, a2);
    while ( 1 )
    {
      hResource = 0;
      CVssClusterResourceList::Pop((CVssClusterResourceList *)v24, &hResource);
      v7 = hResource;
      if ( !hResource )
        break;
      CVssClusterResourceList::Push(a3, hResource);
      v8 = ClusterResourceOpenEnum(v7, 2u);
      EnumCount = ClusterResourceGetEnumCount(v8);
      for ( i = 0; i < EnumCount; ++i )
      {
        cchName = v6;
        v11 = ClusterResourceEnum(v8, i, &dwType, v5, &cchName);
        v12 = v11;
        if ( v11 == 234 )
          goto LABEL_9;
        if ( v11 )
          goto LABEL_16;
        if ( !v5 )
        {
LABEL_9:
          if ( v5 )
            LocalFree(v5);
          v6 = cchName + 1;
          v5 = (WCHAR *)LocalAlloc(0, 2LL * (cchName + 1));
          cchName = v6;
          v12 = ClusterResourceEnum(v8, i, &dwType, v5, &cchName);
          if ( v12 )
          {
LABEL_16:
            if ( v5 )
              LocalFree(v5);
            if ( v12 > 0 )
              v12 = (unsigned __int16)v12 | 0x80070000;
            v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
            v17 = L"CVssClusterAPI::GetFinalOnlineResourceList";
            v18 = L"CLUCLUSC";
            v19 = 1525;
            v20 = 11;
            v21 = 255;
            v23 = 0x1000000;
            memset_0(v22, 0, sizeof(v22));
            CVssFunctionTracer::Throw(v25, &v16, (unsigned int)v12, L"Couldn't enumerate dependent resources.");
          }
        }
        v13 = OpenClusterResource(*this, v5);
        if ( GetClusterResourceState(v13, 0, 0, 0, 0) == ClusterResourceOnline )
          CVssClusterResourceList::Push((CVssClusterResourceList *)v24, v13);
      }
      ClusterResourceCloseEnum(v8);
    }
    if ( v5 )
      LocalFree(v5);
    std::deque<_HRESOURCE *>::~deque<_HRESOURCE *>(v24);
  }
  CVssFunctionTracer::~CVssFunctionTracer(v25);
}

```

## disassembly

```asm
0x18003ec7c  mov     [rsp-8+arg_8], rbx
0x18003ec81  mov     [rsp-8+arg_0], rcx
0x18003ec86  push    rbp
0x18003ec87  push    rsi
0x18003ec88  push    rdi
0x18003ec89  push    r12
0x18003ec8b  push    r13
0x18003ec8d  push    r14
0x18003ec8f  push    r15
0x18003ec91  lea     rbp, [rsp-80h]
0x18003ec96  sub     rsp, 180h
0x18003ec9d  mov     r13, r8
0x18003eca0  mov     rdi, rdx
0x18003eca3  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003ecaa  mov     [rsp+1B0h+var_170], rax
0x18003ecaf  lea     rax, aCvssclusterapi_4; "CVssClusterAPI::GetFinalOnlineResourceL"...
0x18003ecb6  mov     [rsp+1B0h+var_168], rax
0x18003ecbb  lea     rax, aCluclusc; "CLUCLUSC"
0x18003ecc2  mov     [rsp+1B0h+var_160], rax
0x18003ecc7  mov     [rsp+1B0h+var_158], 5ABh
0x18003eccf  mov     [rsp+1B0h+var_154], 0Bh
0x18003ecd7  mov     [rsp+1B0h+var_150], 0FFh
0x18003ecdf  mov     [rbp+0B0h+var_D0], 1000000h
0x18003ece6  xor     edx, edx; Val
0x18003ece8  lea     r8d, [rdx+78h]; Size
0x18003ecec  lea     rcx, [rsp+1B0h+var_148]; void *
0x18003ecf1  call    memset_0
0x18003ecf6  xor     r8d, r8d
0x18003ecf9  lea     rdx, [rsp+1B0h+var_170]
0x18003ecfe  lea     rcx, [rbp+0B0h+var_A0]
0x18003ed02  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003ed07  nop
0x18003ed08  mov     [rsp+1B0h+dwType], 0
0x18003ed10  mov     [rsp+1B0h+lpcchGroupName], 0; lpcchGroupName
0x18003ed19  xor     r9d, r9d; lpszGroupName
0x18003ed1c  xor     r8d, r8d; lpcchNodeName
0x18003ed1f  xor     edx, edx; lpszNodeName
0x18003ed21  mov     rcx, rdi; hResource
0x18003ed24  call    cs:__imp_GetClusterResourceState
0x18003ed2a  cmp     eax, 2
0x18003ed2d  jnz     loc_18003EF2A
0x18003ed33  xor     ebx, ebx
0x18003ed35  xor     r15d, r15d
0x18003ed38  lea     rcx, [rbp+0B0h+var_C8]; this
0x18003ed3c  call    ??0CVssClusterResourceList@@QEAA@XZ; CVssClusterResourceList::CVssClusterResourceList(void)
0x18003ed41  nop
0x18003ed42  mov     rdx, rdi; struct _HRESOURCE *
0x18003ed45  lea     rcx, [rbp+0B0h+var_C8]; this
0x18003ed49  call    ?Push@CVssClusterResourceList@@QEAAXPEAU_HRESOURCE@@@Z; CVssClusterResourceList::Push(_HRESOURCE *)
0x18003ed4e  mov     [rsp+1B0h+hResource], 0
0x18003ed57  lea     rdx, [rsp+1B0h+hResource]; struct _HRESOURCE **
0x18003ed5c  lea     rcx, [rbp+0B0h+var_C8]; this
0x18003ed60  call    ?Pop@CVssClusterResourceList@@QEAAXAEAPEAU_HRESOURCE@@@Z; CVssClusterResourceList::Pop(_HRESOURCE * &)
0x18003ed65  mov     rdi, [rsp+1B0h+hResource]
0x18003ed6a  test    rdi, rdi
0x18003ed6d  jz      loc_18003EF11
0x18003ed73  mov     rdx, rdi; struct _HRESOURCE *
0x18003ed76  mov     rcx, r13; this
0x18003ed79  call    ?Push@CVssClusterResourceList@@QEAAXPEAU_HRESOURCE@@@Z; CVssClusterResourceList::Push(_HRESOURCE *)
0x18003ed7e  mov     edx, 2; dwType
0x18003ed83  mov     rcx, rdi; hResource
0x18003ed86  call    cs:__imp_ClusterResourceOpenEnum
0x18003ed8c  mov     r14, rax
0x18003ed8f  mov     rcx, rax; hResEnum
0x18003ed92  call    cs:__imp_ClusterResourceGetEnumCount
0x18003ed98  mov     r12d, eax
0x18003ed9b  xor     esi, esi
0x18003ed9d  mov     rcx, r14; hResEnum
0x18003eda0  cmp     esi, r12d
0x18003eda3  jnb     loc_18003EE7F
0x18003eda9  mov     [rbp+0B0h+cchName], r15d
0x18003edb0  lea     rax, [rbp+0B0h+cchName]
0x18003edb7  mov     [rsp+1B0h+lpcchGroupName], rax; lpcchName
0x18003edbc  mov     r9, rbx; lpszName
0x18003edbf  lea     r8, [rsp+1B0h+dwType]; lpdwType
0x18003edc4  mov     edx, esi; dwIndex
0x18003edc6  call    cs:__imp_ClusterResourceEnum
0x18003edcc  mov     edi, eax
0x18003edce  cmp     eax, 0EAh
0x18003edd3  jz      short loc_18003EDE2
0x18003edd5  test    eax, eax
0x18003edd7  jnz     loc_18003EE8A
0x18003eddd  test    rbx, rbx
0x18003ede0  jnz     short loc_18003EE37
0x18003ede2  test    rbx, rbx
0x18003ede5  jz      short loc_18003EDF0
0x18003ede7  mov     rcx, rbx; hMem
0x18003edea  call    cs:__imp_LocalFree
0x18003edf0  mov     r15d, [rbp+0B0h+cchName]
0x18003edf7  inc     r15d
0x18003edfa  mov     edx, r15d
0x18003edfd  add     rdx, rdx; uBytes
0x18003ee00  xor     ecx, ecx; uFlags
0x18003ee02  call    cs:__imp_LocalAlloc
0x18003ee08  mov     rbx, rax
0x18003ee0b  mov     [rbp+0B0h+cchName], r15d
0x18003ee12  lea     rax, [rbp+0B0h+cchName]
0x18003ee19  mov     [rsp+1B0h+lpcchGroupName], rax; lpcchName
0x18003ee1e  mov     r9, rbx; lpszName
0x18003ee21  lea     r8, [rsp+1B0h+dwType]; lpdwType
0x18003ee26  mov     edx, esi; dwIndex
0x18003ee28  mov     rcx, r14; hResEnum
0x18003ee2b  call    cs:__imp_ClusterResourceEnum
0x18003ee31  mov     edi, eax
0x18003ee33  test    eax, eax
0x18003ee35  jnz     short loc_18003EE8A
0x18003ee37  mov     rdx, rbx; lpszResourceName
0x18003ee3a  mov     rax, [rbp+0B0h+arg_0]
0x18003ee41  mov     rcx, [rax]; hCluster
0x18003ee44  call    cs:__imp_OpenClusterResource
0x18003ee4a  mov     rdi, rax
0x18003ee4d  mov     [rsp+1B0h+lpcchGroupName], 0; lpcchGroupName
0x18003ee56  xor     r9d, r9d; lpszGroupName
0x18003ee59  xor     r8d, r8d; lpcchNodeName
0x18003ee5c  xor     edx, edx; lpszNodeName
0x18003ee5e  mov     rcx, rax; hResource
0x18003ee61  call    cs:__imp_GetClusterResourceState
0x18003ee67  cmp     eax, 2
0x18003ee6a  jnz     short loc_18003EE78
0x18003ee6c  mov     rdx, rdi; struct _HRESOURCE *
0x18003ee6f  lea     rcx, [rbp+0B0h+var_C8]; this
0x18003ee73  call    ?Push@CVssClusterResourceList@@QEAAXPEAU_HRESOURCE@@@Z; CVssClusterResourceList::Push(_HRESOURCE *)
0x18003ee78  inc     esi
0x18003ee7a  jmp     loc_18003ED9D
0x18003ee7f  call    cs:__imp_ClusterResourceCloseEnum
0x18003ee85  jmp     loc_18003ED4E
0x18003ee8a  test    rbx, rbx
0x18003ee8d  jz      short loc_18003EE98
0x18003ee8f  mov     rcx, rbx; hMem
0x18003ee92  call    cs:__imp_LocalFree
0x18003ee98  test    edi, edi
0x18003ee9a  jle     short loc_18003EEA5
0x18003ee9c  movzx   edi, di
0x18003ee9f  or      edi, 80070000h
0x18003eea5  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003eeac  mov     [rsp+1B0h+var_170], rax
0x18003eeb1  lea     rax, aCvssclusterapi_4; "CVssClusterAPI::GetFinalOnlineResourceL"...
0x18003eeb8  mov     [rsp+1B0h+var_168], rax
0x18003eebd  lea     rax, aCluclusc; "CLUCLUSC"
0x18003eec4  mov     [rsp+1B0h+var_160], rax
0x18003eec9  mov     [rsp+1B0h+var_158], 5F5h
0x18003eed1  mov     [rsp+1B0h+var_154], 0Bh
0x18003eed9  mov     [rsp+1B0h+var_150], 0FFh
0x18003eee1  mov     [rbp+0B0h+var_D0], 1000000h
0x18003eee8  xor     edx, edx; Val
0x18003eeea  lea     r8d, [rdx+78h]; Size
0x18003eeee  lea     rcx, [rsp+1B0h+var_148]; void *
0x18003eef3  call    memset_0
0x18003eef8  lea     r9, aCouldnTEnumera; "Couldn't enumerate dependent resources."
0x18003eeff  mov     r8d, edi
0x18003ef02  lea     rdx, [rsp+1B0h+var_170]
0x18003ef07  lea     rcx, [rbp+0B0h+var_A0]
0x18003ef0b  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003ef11  test    rbx, rbx
0x18003ef14  jz      short loc_18003EF20
0x18003ef16  mov     rcx, rbx; hMem
0x18003ef19  call    cs:__imp_LocalFree
0x18003ef1f  nop
0x18003ef20  lea     rcx, [rbp+0B0h+var_C8]
0x18003ef24  call    ??1?$deque@PEAU_HRESOURCE@@V?$allocator@PEAU_HRESOURCE@@@std@@@std@@QEAA@XZ; std::deque<_HRESOURCE *>::~deque<_HRESOURCE *>(void)
0x18003ef29  nop
0x18003ef2a  lea     rcx, [rbp+0B0h+var_A0]; this
0x18003ef2e  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003ef33  mov     rbx, [rsp+1B0h+arg_8]
0x18003ef3b  add     rsp, 180h
0x18003ef42  pop     r15
0x18003ef44  pop     r14
0x18003ef46  pop     r13
0x18003ef48  pop     r12
0x18003ef4a  pop     rdi
0x18003ef4b  pop     rsi
0x18003ef4c  pop     rbp
0x18003ef4d  retn
```
