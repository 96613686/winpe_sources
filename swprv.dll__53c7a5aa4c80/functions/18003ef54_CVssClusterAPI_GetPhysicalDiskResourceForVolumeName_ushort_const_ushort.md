# CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(ushort const *,ushort * *)

- ea: `0x18003ef54`
- end: `0x18003f1ee`
- name: `?GetPhysicalDiskResourceForVolumeName@CVssClusterAPI@@QEAAPEAU_HRESOURCE@@PEBGPEAPEAG@Z`
- size: `666`
- prototype: `struct _HRESOURCE *__fastcall(HCLUSTER *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18002d1f0`
- `0x18003e054`
- `0x18003ff6c`

## callees

- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`
- `0x180036a1c`
- `0x18003ef54`
- `0x18003f7e8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f0c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f0c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f0f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f12c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f13e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f0f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f12c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f13e`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterEnum` at `0x18003f09d`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterEnum` at `0x18003f0e4`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterEnum` at `0x18003f09d`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterEnum` at `0x18003f0e4`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x18003f105`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x18003f105`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterCloseEnum` at `0x18003f147`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterCloseEnum` at `0x18003f147`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterOpenEnum` at `0x18003f054`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterOpenEnum` at `0x18003f054`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003f123`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003f123`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterGetEnumCount` at `0x18003f060`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterGetEnumCount` at `0x18003f060`

## pseudocode

```c
struct _HRESOURCE *__fastcall CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(
        HCLUSTER *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  struct _HRESOURCE *v5; // rdi
  struct _HCLUSENUM *v6; // r14
  DWORD EnumCount; // r12d
  DWORD i; // esi
  HLOCAL v9; // rbx
  CVssClusterAPI *v10; // rcx
  unsigned __int16 **lpcchName; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v13; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v14; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v15; // [rsp+40h] [rbp-C0h]
  int v16; // [rsp+48h] [rbp-B8h]
  int v17; // [rsp+4Ch] [rbp-B4h]
  int v18; // [rsp+50h] [rbp-B0h]
  _BYTE v19[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v20; // [rsp+D0h] [rbp-30h]
  LPVOID v21[20]; // [rsp+E0h] [rbp-20h] BYREF
  DWORD dwType; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int16 **cchName; // [rsp+1A0h] [rbp+A0h] BYREF

  cchName = a3;
  v13 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v14 = L"CVssClusterAPI::GetPhysicalDiskResourceForVolumeName";
  v15 = L"CLUCLUSC";
  v16 = 815;
  v17 = 11;
  v18 = 255;
  v5 = 0;
  v20 = 0x1000000;
  memset_0(v19, 0, sizeof(v19));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v21, (__int64)&v13, 0);
  v13 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v14 = L"CVssClusterAPI::GetPhysicalDiskResourceForVolumeName";
  v15 = L"CLUCLUSC";
  v16 = 818;
  v17 = 11;
  v18 = 255;
  v20 = 0x1000000;
  memset_0(v19, 0, sizeof(v19));
  CVssFunctionTracer::Trace(v21, &v13, L"Parameters: Volume = %s", a2);
  if ( !a2 || !*a2 )
  {
    v13 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v14 = L"CVssClusterAPI::GetPhysicalDiskResourceForVolumeName";
    v15 = L"CLUCLUSC";
    v16 = 822;
    v17 = 11;
    v18 = 255;
    v20 = 0x1000000;
    memset_0(v19, 0, sizeof(v19));
    CVssFunctionTracer::Throw(v21, &v13, 2147942487LL, L"NULL parameters");
  }
  v6 = ClusterOpenEnum(*this, 4u);
  EnumCount = ClusterGetEnumCount(v6);
  for ( i = 0; i < EnumCount; ++i )
  {
    v5 = 0;
    dwType = 0;
    LODWORD(cchName) = 0;
    if ( !ClusterEnum(v6, i, &dwType, 0, (LPDWORD)&cchName) )
    {
      LODWORD(cchName) = (_DWORD)cchName + 1;
      v9 = LocalAlloc(0, 2LL * (unsigned int)cchName);
      if ( ClusterEnum(v6, i, &dwType, (LPWSTR)v9, (LPDWORD)&cchName) )
      {
        if ( v9 )
          LocalFree(v9);
      }
      else
      {
        v5 = OpenClusterResource(*this, (LPCWSTR)v9);
        if ( CVssClusterAPI::IsResourceReferringVolume(v10, v5, (const unsigned __int16 *)v9, a2, lpcchName) )
        {
          LocalFree(v9);
          break;
        }
        CloseClusterResource(v5);
        LocalFree(v9);
        v5 = 0;
      }
    }
  }
  ClusterCloseEnum(v6);
  CVssFunctionTracer::TraceInternalWithFormat((CVssFunctionTracer *)v21, L"RETURN", 0xAAu, L"Returning PTR: %p", v5);
  CVssFunctionTracer::~CVssFunctionTracer(v21);
  return v5;
}

```

## disassembly

```asm
0x18003ef54  mov     [rsp-8+arg_0], rbx
0x18003ef59  mov     [rsp-8+cchName], r8
0x18003ef5e  push    rbp
0x18003ef5f  push    rsi
0x18003ef60  push    rdi
0x18003ef61  push    r12
0x18003ef63  push    r13
0x18003ef65  push    r14
0x18003ef67  push    r15
0x18003ef69  lea     rbp, [rsp-50h]
0x18003ef6e  sub     rsp, 150h
0x18003ef75  mov     r15, rdx
0x18003ef78  mov     r13, rcx
0x18003ef7b  lea     rbx, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003ef82  mov     [rsp+180h+var_150], rbx
0x18003ef87  lea     rsi, aCvssclusterapi; "CVssClusterAPI::GetPhysicalDiskResource"...
0x18003ef8e  mov     [rsp+180h+var_148], rsi
0x18003ef93  lea     r14, aCluclusc; "CLUCLUSC"
0x18003ef9a  mov     [rsp+180h+var_140], r14
0x18003ef9f  mov     [rsp+180h+var_138], 32Fh
0x18003efa7  mov     r12d, 0Bh
0x18003efad  mov     [rsp+180h+var_134], r12d
0x18003efb2  mov     [rsp+180h+var_130], 0FFh
0x18003efba  xor     edi, edi
0x18003efbc  mov     [rbp+80h+var_B0], 1000000h
0x18003efc3  xor     edx, edx; Val
0x18003efc5  lea     r8d, [r12+6Dh]; Size
0x18003efca  lea     rcx, [rsp+180h+var_128]; void *
0x18003efcf  call    memset_0
0x18003efd4  xor     r8d, r8d
0x18003efd7  lea     rdx, [rsp+180h+var_150]
0x18003efdc  lea     rcx, [rbp+80h+var_A0]
0x18003efe0  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003efe5  nop
0x18003efe6  mov     [rsp+180h+var_150], rbx
0x18003efeb  mov     [rsp+180h+var_148], rsi
0x18003eff0  mov     [rsp+180h+var_140], r14
0x18003eff5  mov     [rsp+180h+var_138], 332h
0x18003effd  mov     [rsp+180h+var_134], r12d
0x18003f002  mov     [rsp+180h+var_130], 0FFh
0x18003f00a  mov     [rbp+80h+var_B0], 1000000h
0x18003f011  xor     edx, edx; Val
0x18003f013  lea     r8d, [r12+6Dh]; Size
0x18003f018  lea     rcx, [rsp+180h+var_128]; void *
0x18003f01d  call    memset_0
0x18003f022  mov     r9, r15
0x18003f025  lea     r8, aParametersVolu; "Parameters: Volume = %s"
0x18003f02c  lea     rdx, [rsp+180h+var_150]
0x18003f031  lea     rcx, [rbp+80h+var_A0]
0x18003f035  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003f03a  test    r15, r15
0x18003f03d  jz      loc_18003F197
0x18003f043  cmp     [r15], di
0x18003f047  jz      loc_18003F197
0x18003f04d  lea     edx, [rdi+4]; dwType
0x18003f050  mov     rcx, [r13+0]; hCluster
0x18003f054  call    cs:__imp_ClusterOpenEnum
0x18003f05a  mov     r14, rax
0x18003f05d  mov     rcx, rax; hEnum
0x18003f060  call    cs:__imp_ClusterGetEnumCount
0x18003f066  mov     r12d, eax
0x18003f069  mov     esi, edi
0x18003f06b  cmp     esi, r12d
0x18003f06e  jnb     loc_18003F144
0x18003f074  xor     edi, edi
0x18003f076  mov     [rbp+80h+dwType], edi
0x18003f07c  mov     dword ptr [rbp+80h+cchName], edi
0x18003f082  lea     rax, [rbp+80h+cchName]
0x18003f089  mov     [rsp+180h+lpcchName], rax; lpcchName
0x18003f08e  xor     r9d, r9d; lpszName
0x18003f091  lea     r8, [rbp+80h+dwType]; lpdwType
0x18003f098  mov     edx, esi; dwIndex
0x18003f09a  mov     rcx, r14; hEnum
0x18003f09d  call    cs:__imp_ClusterEnum
0x18003f0a3  test    eax, eax
0x18003f0a5  jnz     loc_18003F134
0x18003f0ab  mov     eax, dword ptr [rbp+80h+cchName]
0x18003f0b1  inc     eax
0x18003f0b3  mov     dword ptr [rbp+80h+cchName], eax
0x18003f0b9  mov     edx, eax
0x18003f0bb  add     rdx, rdx; uBytes
0x18003f0be  xor     ecx, ecx; uFlags
0x18003f0c0  call    cs:__imp_LocalAlloc
0x18003f0c6  mov     rbx, rax
0x18003f0c9  lea     rax, [rbp+80h+cchName]
0x18003f0d0  mov     [rsp+180h+lpcchName], rax; unsigned __int16 **
0x18003f0d5  mov     r9, rbx; lpszName
0x18003f0d8  lea     r8, [rbp+80h+dwType]; lpdwType
0x18003f0df  mov     edx, esi; dwIndex
0x18003f0e1  mov     rcx, r14; hEnum
0x18003f0e4  call    cs:__imp_ClusterEnum
0x18003f0ea  test    eax, eax
0x18003f0ec  jz      short loc_18003F0FE
0x18003f0ee  test    rbx, rbx
0x18003f0f1  jz      short loc_18003F134
0x18003f0f3  mov     rcx, rbx; hMem
0x18003f0f6  call    cs:__imp_LocalFree
0x18003f0fc  jmp     short loc_18003F134
0x18003f0fe  mov     rdx, rbx; lpszResourceName
0x18003f101  mov     rcx, [r13+0]; hCluster
0x18003f105  call    cs:__imp_OpenClusterResource
0x18003f10b  mov     rdi, rax
0x18003f10e  mov     r9, r15; unsigned __int16 *
0x18003f111  mov     r8, rbx; unsigned __int16 *
0x18003f114  mov     rdx, rax; struct _HRESOURCE *
0x18003f117  call    ?IsResourceReferringVolume@CVssClusterAPI@@AEAA_NPEAU_HRESOURCE@@PEBG1PEAPEAG@Z; CVssClusterAPI::IsResourceReferringVolume(_HRESOURCE *,ushort const *,ushort const *,ushort * *)
0x18003f11c  test    al, al
0x18003f11e  jnz     short loc_18003F13B
0x18003f120  mov     rcx, rdi; hResource
0x18003f123  call    cs:__imp_CloseClusterResource
0x18003f129  mov     rcx, rbx; hMem
0x18003f12c  call    cs:__imp_LocalFree
0x18003f132  xor     edi, edi
0x18003f134  inc     esi
0x18003f136  jmp     loc_18003F06B
0x18003f13b  mov     rcx, rbx; hMem
0x18003f13e  call    cs:__imp_LocalFree
0x18003f144  mov     rcx, r14; hEnum
0x18003f147  call    cs:__imp_ClusterCloseEnum
0x18003f14d  mov     [rsp+180h+lpcchName], rdi
0x18003f152  lea     r9, aReturningPtrP; "Returning PTR: %p"
0x18003f159  mov     r8d, 0AAh; unsigned int
0x18003f15f  lea     rdx, aReturn; "RETURN"
0x18003f166  lea     rcx, [rbp+80h+var_A0]; this
0x18003f16a  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18003f16f  nop
0x18003f170  lea     rcx, [rbp+80h+var_A0]; this
0x18003f174  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003f179  mov     rax, rdi
0x18003f17c  mov     rbx, [rsp+180h+arg_0]
0x18003f184  add     rsp, 150h
0x18003f18b  pop     r15
0x18003f18d  pop     r14
0x18003f18f  pop     r13
0x18003f191  pop     r12
0x18003f193  pop     rdi
0x18003f194  pop     rsi
0x18003f195  pop     rbp
0x18003f196  retn
0x18003f197  mov     [rsp+180h+var_150], rbx
0x18003f19c  mov     [rsp+180h+var_148], rsi
0x18003f1a1  mov     [rsp+180h+var_140], r14
0x18003f1a6  mov     [rsp+180h+var_138], 336h
0x18003f1ae  mov     [rsp+180h+var_134], r12d
0x18003f1b3  mov     [rsp+180h+var_130], 0FFh
0x18003f1bb  mov     [rbp+80h+var_B0], 1000000h
0x18003f1c2  xor     edx, edx; Val
0x18003f1c4  lea     r8d, [rdx+78h]; Size
0x18003f1c8  lea     rcx, [rsp+180h+var_128]; void *
0x18003f1cd  call    memset_0
0x18003f1d2  lea     r9, aNullParameters; "NULL parameters"
0x18003f1d9  mov     r8d, 80070057h
0x18003f1df  lea     rdx, [rsp+180h+var_150]
0x18003f1e4  lea     rcx, [rbp+80h+var_A0]
0x18003f1e8  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
