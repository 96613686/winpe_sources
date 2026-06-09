# CVssClusterAPI::IsDependencyAlreadyEstablished(_HRESOURCE *,_HRESOURCE *)

- ea: `0x18003f52c`
- end: `0x18003f7e1`
- name: `?IsDependencyAlreadyEstablished@CVssClusterAPI@@QEAA_NPEAU_HRESOURCE@@0@Z`
- size: `693`
- prototype: `char __fastcall(HCLUSTER *this, struct _HRESOURCE *, struct _HRESOURCE *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18002d1f0`
- `0x18003e054`
- `0x18003ff6c`

## callees

- `0x18000212c`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`
- `0x18003e574`
- `0x18003f52c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f6ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f6ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f750`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x18003f6e8`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x18003f6e8`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003f708`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003f742`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003f708`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003f742`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceCloseEnum` at `0x18003f734`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceCloseEnum` at `0x18003f734`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceOpenEnum` at `0x18003f640`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceOpenEnum` at `0x18003f640`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceGetEnumCount` at `0x18003f65b`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceGetEnumCount` at `0x18003f65b`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceEnum` at `0x18003f689`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceEnum` at `0x18003f6d1`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceEnum` at `0x18003f689`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceEnum` at `0x18003f6d1`

## string_xrefs

- `0x18003f55f`: `CVssClusterAPI::IsDependencyAlreadyEstablished`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CVssClusterAPI::IsDependencyAlreadyEstablished(
        HCLUSTER *this,
        struct _HRESOURCE *a2,
        struct _HRESOURCE *a3)
{
  DWORD v5; // r14d
  char v6; // r15
  struct _HRESENUM *v7; // rax
  struct _HRESENUM *v8; // rsi
  WCHAR *v9; // rbx
  struct _HRESOURCE *v10; // rdi
  DWORD EnumCount; // r13d
  struct _HRESOURCE *v12; // rax
  CVssClusterAPI *v13; // rcx
  char v14; // bl
  const unsigned __int16 *v16; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v17; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+50h] [rbp-B0h]
  int v20; // [rsp+54h] [rbp-ACh]
  int v21; // [rsp+58h] [rbp-A8h]
  _BYTE v22[120]; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+D8h] [rbp-28h]
  LPVOID v24[20]; // [rsp+E0h] [rbp-20h] BYREF
  DWORD cchName; // [rsp+198h] [rbp+98h] BYREF
  DWORD dwType; // [rsp+1A8h] [rbp+A8h] BYREF

  v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v17 = L"CVssClusterAPI::IsDependencyAlreadyEstablished";
  v18 = L"CLUCLUSC";
  v19 = 918;
  v20 = 11;
  v21 = 255;
  v5 = 0;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v24, (__int64)&v16, 0);
  v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v17 = L"CVssClusterAPI::IsDependencyAlreadyEstablished";
  v18 = L"CLUCLUSC";
  v19 = 921;
  v20 = 11;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CVssFunctionTracer::Trace(v24, &v16, L"Parameters: pFromResource = %p, pToResource = %p", a2, a3);
  if ( !a2 || !a3 )
  {
    v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v17 = L"CVssClusterAPI::IsDependencyAlreadyEstablished";
    v18 = L"CLUCLUSC";
    v19 = 925;
    v20 = 11;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CVssFunctionTracer::Throw(v24, &v16, 2147942487LL, L"NULL parameters");
  }
  cchName = 0;
  dwType = 0;
  v6 = 0;
  v7 = ClusterResourceOpenEnum(a2, 1u);
  v8 = v7;
  if ( v7 )
  {
    v9 = 0;
    v10 = 0;
    EnumCount = ClusterResourceGetEnumCount(v7);
    while ( v5 < EnumCount )
    {
      if ( ClusterResourceEnum(v8, v5, &dwType, v9, &cchName) )
        break;
      v9 = (WCHAR *)LocalAlloc(0, 2LL * ++cchName);
      if ( ClusterResourceEnum(v8, v5, &dwType, v9, &cchName) )
        break;
      v12 = OpenClusterResource(*this, v9);
      v10 = v12;
      if ( v12 )
      {
        if ( CVssClusterAPI::AreResourcesEqual(v13, a3, v12) )
        {
          v6 = 1;
          break;
        }
        CloseClusterResource(v10);
        v10 = 0;
      }
      if ( v9 )
      {
        LocalFree(v9);
        v9 = 0;
        cchName = 0;
      }
      ++v5;
    }
    ClusterResourceCloseEnum(v8);
    if ( v10 )
      CloseClusterResource(v10);
    if ( v9 )
      LocalFree(v9);
  }
  v14 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v24, v6);
  CVssFunctionTracer::~CVssFunctionTracer(v24);
  return v14;
}

```

## disassembly

```asm
0x18003f52c  mov     [rsp-8+arg_10], rbx
0x18003f531  mov     [rsp-8+arg_0], rcx
0x18003f536  push    rbp
0x18003f537  push    rsi
0x18003f538  push    rdi
0x18003f539  push    r12
0x18003f53b  push    r13
0x18003f53d  push    r14
0x18003f53f  push    r15
0x18003f541  lea     rbp, [rsp-50h]
0x18003f546  sub     rsp, 150h
0x18003f54d  mov     r12, r8
0x18003f550  mov     rbx, rdx
0x18003f553  lea     rdi, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003f55a  mov     [rsp+180h+var_148], rdi
0x18003f55f  lea     rsi, aCvssclusterapi_8; "CVssClusterAPI::IsDependencyAlreadyEsta"...
0x18003f566  mov     [rsp+180h+var_140], rsi
0x18003f56b  lea     r15, aCluclusc; "CLUCLUSC"
0x18003f572  mov     [rsp+180h+var_138], r15
0x18003f577  mov     [rsp+180h+var_130], 396h
0x18003f57f  mov     r13d, 0Bh
0x18003f585  mov     [rsp+180h+var_12C], r13d
0x18003f58a  mov     [rsp+180h+var_128], 0FFh
0x18003f592  xor     r14d, r14d
0x18003f595  mov     [rbp+80h+var_A8], 1000000h
0x18003f59c  xor     edx, edx; Val
0x18003f59e  lea     r8d, [r13+6Dh]; Size
0x18003f5a2  lea     rcx, [rsp+180h+var_120]; void *
0x18003f5a7  call    memset_0
0x18003f5ac  xor     r8d, r8d
0x18003f5af  lea     rdx, [rsp+180h+var_148]
0x18003f5b4  lea     rcx, [rbp+80h+var_A0]
0x18003f5b8  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003f5bd  nop
0x18003f5be  mov     [rsp+180h+var_148], rdi
0x18003f5c3  mov     [rsp+180h+var_140], rsi
0x18003f5c8  mov     [rsp+180h+var_138], r15
0x18003f5cd  mov     [rsp+180h+var_130], 399h
0x18003f5d5  mov     [rsp+180h+var_12C], r13d
0x18003f5da  mov     [rsp+180h+var_128], 0FFh
0x18003f5e2  mov     [rbp+80h+var_A8], 1000000h
0x18003f5e9  xor     edx, edx; Val
0x18003f5eb  lea     r8d, [r13+6Dh]; Size
0x18003f5ef  lea     rcx, [rsp+180h+var_120]; void *
0x18003f5f4  call    memset_0
0x18003f5f9  mov     [rsp+180h+lpcchName], r12
0x18003f5fe  mov     r9, rbx
0x18003f601  lea     r8, aParametersPfro; "Parameters: pFromResource = %p, pToReso"...
0x18003f608  lea     rdx, [rsp+180h+var_148]
0x18003f60d  lea     rcx, [rbp+80h+var_A0]
0x18003f611  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003f616  test    rbx, rbx
0x18003f619  jz      loc_18003F78A
0x18003f61f  test    r12, r12
0x18003f622  jz      loc_18003F78A
0x18003f628  mov     [rbp+80h+cchName], r14d
0x18003f62f  mov     [rbp+80h+dwType], r14d
0x18003f636  mov     r15b, r14b
0x18003f639  lea     edx, [r13-0Ah]; dwType
0x18003f63d  mov     rcx, rbx; hResource
0x18003f640  call    cs:__imp_ClusterResourceOpenEnum
0x18003f646  mov     rsi, rax
0x18003f649  test    rax, rax
0x18003f64c  jz      loc_18003F756
0x18003f652  mov     ebx, r14d
0x18003f655  mov     edi, r14d
0x18003f658  mov     rcx, rax; hResEnum
0x18003f65b  call    cs:__imp_ClusterResourceGetEnumCount
0x18003f661  mov     r13d, eax
0x18003f664  cmp     r14d, r13d
0x18003f667  jnb     loc_18003F731
0x18003f66d  lea     rax, [rbp+80h+cchName]
0x18003f674  mov     [rsp+180h+lpcchName], rax; lpcchName
0x18003f679  mov     r9, rbx; lpszName
0x18003f67c  lea     r8, [rbp+80h+dwType]; lpdwType
0x18003f683  mov     edx, r14d; dwIndex
0x18003f686  mov     rcx, rsi; hResEnum
0x18003f689  call    cs:__imp_ClusterResourceEnum
0x18003f68f  test    eax, eax
0x18003f691  jnz     loc_18003F731
0x18003f697  mov     eax, [rbp+80h+cchName]
0x18003f69d  inc     eax
0x18003f69f  mov     [rbp+80h+cchName], eax
0x18003f6a5  mov     edx, eax
0x18003f6a7  add     rdx, rdx; uBytes
0x18003f6aa  xor     ecx, ecx; uFlags
0x18003f6ac  call    cs:__imp_LocalAlloc
0x18003f6b2  mov     rbx, rax
0x18003f6b5  lea     rax, [rbp+80h+cchName]
0x18003f6bc  mov     [rsp+180h+lpcchName], rax; lpcchName
0x18003f6c1  mov     r9, rbx; lpszName
0x18003f6c4  lea     r8, [rbp+80h+dwType]; lpdwType
0x18003f6cb  mov     edx, r14d; dwIndex
0x18003f6ce  mov     rcx, rsi; hResEnum
0x18003f6d1  call    cs:__imp_ClusterResourceEnum
0x18003f6d7  test    eax, eax
0x18003f6d9  jnz     short loc_18003F731
0x18003f6db  mov     rdx, rbx; lpszResourceName
0x18003f6de  mov     rax, [rbp+80h+arg_0]
0x18003f6e5  mov     rcx, [rax]; hCluster
0x18003f6e8  call    cs:__imp_OpenClusterResource
0x18003f6ee  mov     rdi, rax
0x18003f6f1  test    rax, rax
0x18003f6f4  jz      short loc_18003F710
0x18003f6f6  mov     r8, rax; struct _HRESOURCE *
0x18003f6f9  mov     rdx, r12; struct _HRESOURCE *
0x18003f6fc  call    ?AreResourcesEqual@CVssClusterAPI@@QEAA_NPEAU_HRESOURCE@@0@Z; CVssClusterAPI::AreResourcesEqual(_HRESOURCE *,_HRESOURCE *)
0x18003f701  test    al, al
0x18003f703  jnz     short loc_18003F72E
0x18003f705  mov     rcx, rdi; hResource
0x18003f708  call    cs:__imp_CloseClusterResource
0x18003f70e  xor     edi, edi
0x18003f710  test    rbx, rbx
0x18003f713  jz      short loc_18003F726
0x18003f715  mov     rcx, rbx; hMem
0x18003f718  call    cs:__imp_LocalFree
0x18003f71e  xor     ebx, ebx
0x18003f720  mov     [rbp+80h+cchName], ebx
0x18003f726  inc     r14d
0x18003f729  jmp     loc_18003F664
0x18003f72e  mov     r15b, 1
0x18003f731  mov     rcx, rsi; hResEnum
0x18003f734  call    cs:__imp_ClusterResourceCloseEnum
0x18003f73a  test    rdi, rdi
0x18003f73d  jz      short loc_18003F748
0x18003f73f  mov     rcx, rdi; hResource
0x18003f742  call    cs:__imp_CloseClusterResource
0x18003f748  test    rbx, rbx
0x18003f74b  jz      short loc_18003F756
0x18003f74d  mov     rcx, rbx; hMem
0x18003f750  call    cs:__imp_LocalFree
0x18003f756  mov     dl, r15b; bool
0x18003f759  lea     rcx, [rbp+80h+var_A0]; this
0x18003f75d  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x18003f762  mov     bl, al
0x18003f764  lea     rcx, [rbp+80h+var_A0]; this
0x18003f768  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003f76d  mov     al, bl
0x18003f76f  mov     rbx, [rsp+180h+arg_10]
0x18003f777  add     rsp, 150h
0x18003f77e  pop     r15
0x18003f780  pop     r14
0x18003f782  pop     r13
0x18003f784  pop     r12
0x18003f786  pop     rdi
0x18003f787  pop     rsi
0x18003f788  pop     rbp
0x18003f789  retn
0x18003f78a  mov     [rsp+180h+var_148], rdi
0x18003f78f  mov     [rsp+180h+var_140], rsi
0x18003f794  mov     [rsp+180h+var_138], r15
0x18003f799  mov     [rsp+180h+var_130], 39Dh
0x18003f7a1  mov     [rsp+180h+var_12C], r13d
0x18003f7a6  mov     [rsp+180h+var_128], 0FFh
0x18003f7ae  mov     [rbp+80h+var_A8], 1000000h
0x18003f7b5  xor     edx, edx; Val
0x18003f7b7  lea     r8d, [rdx+78h]; Size
0x18003f7bb  lea     rcx, [rsp+180h+var_120]; void *
0x18003f7c0  call    memset_0
0x18003f7c5  lea     r9, aNullParameters; "NULL parameters"
0x18003f7cc  mov     r8d, 80070057h
0x18003f7d2  lea     rdx, [rsp+180h+var_148]
0x18003f7d7  lea     rcx, [rbp+80h+var_A0]
0x18003f7db  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
