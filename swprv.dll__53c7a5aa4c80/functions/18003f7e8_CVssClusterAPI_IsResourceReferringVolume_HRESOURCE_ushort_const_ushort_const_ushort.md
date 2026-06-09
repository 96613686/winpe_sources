# CVssClusterAPI::IsResourceReferringVolume(_HRESOURCE *,ushort const *,ushort const *,ushort * *)

- ea: `0x18003f7e8`
- end: `0x18003fe5a`
- name: `?IsResourceReferringVolume@CVssClusterAPI@@AEAA_NPEAU_HRESOURCE@@PEBG1PEAPEAG@Z`
- size: `1650`
- prototype: `char __fastcall(CVssClusterAPI *this, struct _HRESOURCE *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18003ef54`

## callees

- `0x180001580`
- `0x18000212c`
- `0x18001c208`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x18003f7e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003fc5d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003fc84`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003fc5d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003fc84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f9de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003fa82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003fb5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f9de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003fa82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003fb5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fd99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fda7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fd99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fda7`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003fc45`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003fc45`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003fc0d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003fc0d`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003f925`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003f9ba`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fa13`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fa69`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fab5`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fb45`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fb8d`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003f925`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003f9ba`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fa13`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fa69`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fab5`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fb45`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18003fb8d`

## string_xrefs

- `0x18003fb14`: `Couldn't read disk private properties [0x%08lx]`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall CVssClusterAPI::IsResourceReferringVolume(
        CVssClusterAPI *this,
        struct _HRESOURCE *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  char v7; // r12
  DWORD v8; // ebx
  const wchar_t *v9; // r8
  HLOCAL v10; // rsi
  HLOCAL lpOutBuffer; // r15
  const wchar_t *v12; // rcx
  int v13; // eax
  int v14; // edx
  DWORD v15; // eax
  DWORD v16; // ebx
  DWORD v17; // ebx
  GUID *v18; // r14
  const GUID *i; // rbx
  int v20; // edi
  int v21; // eax
  char v22; // bl
  DWORD cbInBufferSize[2]; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v26; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v27; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+6Ch] [rbp-94h]
  int v31; // [rsp+70h] [rbp-90h]
  _BYTE v32[120]; // [rsp+78h] [rbp-88h] BYREF
  int v33; // [rsp+F0h] [rbp-10h]
  __int64 OutBuffer; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID v35[14]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR sz[40]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR szVolumeName[264]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR szVolumeMountPoint[264]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v26 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v27 = L"CVssClusterAPI::IsResourceReferringVolume";
  v28 = L"CLUCLUSC";
  v29 = 1047;
  v30 = 11;
  v31 = 255;
  v33 = 0x1000000;
  memset_0(v32, 0, sizeof(v32));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v35, (__int64)&v26, 0);
  BytesReturned[0] = 0;
  v7 = 0;
  v26 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v27 = L"CVssClusterAPI::IsResourceReferringVolume";
  v28 = L"CLUCLUSC";
  v29 = 1062;
  v30 = 11;
  v31 = 255;
  v33 = 0x1000000;
  memset_0(v32, 0, sizeof(v32));
  CVssFunctionTracer::Trace(v35, &v26, L"Parameters: resource name = %s, pwszVolumeName = %s", a3, a4);
  OutBuffer = 0;
  v8 = ClusterResourceControl(a2, 0, 0x100000Du, 0, 0, &OutBuffer, 8u, BytesReturned);
  if ( v8 )
  {
    v26 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v27 = L"CVssClusterAPI::IsResourceReferringVolume";
    v28 = L"CLUCLUSC";
    v29 = 1078;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    v9 = L"Couldn't get resource class for %s: [0x%08lx]";
LABEL_34:
    cbInBufferSize[0] = v8;
    CVssFunctionTracer::Trace(v35, &v26, v9, a3, *(_QWORD *)cbInBufferSize);
    goto LABEL_35;
  }
  if ( (_DWORD)OutBuffer == 1 )
  {
    v8 = ClusterResourceControl(a2, 0, 0x100002Du, 0, 0, 0, 0, BytesReturned);
    if ( v8 )
    {
      v26 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
      v27 = L"CVssClusterAPI::IsResourceReferringVolume";
      v28 = L"CLUCLUSC";
      v29 = 1112;
      v30 = 11;
      v31 = 255;
      v33 = 0x1000000;
      memset_0(v32, 0, sizeof(v32));
      v9 = L"Couldn't get resource type for %s: [0x%08lx]";
      goto LABEL_34;
    }
    v10 = 0;
    ++BytesReturned[0];
    lpOutBuffer = LocalAlloc(0, 2LL * BytesReturned[0]);
    ClusterResourceControl(a2, 0, 0x100002Du, 0, 0, lpOutBuffer, BytesReturned[0] + 1, BytesReturned);
    v12 = L"Physical Disk";
    do
    {
      v13 = *(const wchar_t *)((char *)v12 + (_BYTE *)lpOutBuffer - (_BYTE *)L"Physical Disk");
      v14 = *v12 - v13;
      if ( v14 )
        break;
      ++v12;
    }
    while ( v13 );
    if ( !v14 )
    {
      v15 = ClusterResourceControl(a2, 0, 0x1000081u, 0, 0, 0, 0, BytesReturned);
      v16 = v15;
      if ( !v15 || v15 == 234 )
      {
        v10 = LocalAlloc(0, BytesReturned[0]);
        v16 = ClusterResourceControl(a2, 0, 0x1000081u, 0, 0, v10, BytesReturned[0], BytesReturned);
      }
      if ( v16 )
      {
        v26 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
        v27 = L"CVssClusterAPI::IsResourceReferringVolume";
        v28 = L"CLUCLUSC";
        v29 = 1167;
        v30 = 11;
        v31 = 255;
        v33 = 0x1000000;
        memset_0(v32, 0, sizeof(v32));
        CVssFunctionTracer::Trace(v35, &v26, L"Couldn't read disk private properties [0x%08lx]", v16);
      }
      else
      {
        v17 = ClusterResourceControl(a2, 0, 0x10001F1u, 0, 0, 0, 0, BytesReturned);
        if ( v17
          || (v18 = (GUID *)LocalAlloc(0, BytesReturned[0]),
              (v17 = ClusterResourceControl(a2, 0, 0x10001F1u, 0, 0, v18, BytesReturned[0], BytesReturned)) != 0) )
        {
          v26 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
          v27 = L"CVssClusterAPI::IsResourceReferringVolume";
          v28 = L"CLUCLUSC";
          v29 = 1210;
          v30 = 11;
          v31 = 255;
          v33 = 0x1000000;
          memset_0(v32, 0, sizeof(v32));
          CVssFunctionTracer::Trace(v35, &v26, L"Couldn't get disk info [0x%08lx]", v17);
        }
        else
        {
          for ( i = v18;
                i < (GUID *)((char *)v18 + BytesReturned[0]) && i->Data1;
                i = (const GUID *)((char *)i + *(unsigned int *)&i->Data2 + 8) )
          {
            if ( i->Data1 == 851969 )
            {
              memset_0(szVolumeMountPoint, 0, 0x208u);
              memset_0(szVolumeName, 0, 0x208u);
              memset_0(sz, 0, sizeof(sz));
              v20 = StringFromGUID2(i + 72, sz, 40);
              StringCchPrintfW(szVolumeMountPoint, 0x104u, L"\\\\?\\Volume%s\\", sz);
              if ( GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x104u) )
              {
                if ( v20 && !(unsigned int)_o__wcsicmp(szVolumeName, a4) )
                {
                  v21 = _o__wcsicmp(&i[33].Data2, &qword_180050E70);
                  v30 = 11;
                  v31 = 255;
                  v33 = 0x1000000;
                  v26 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
                  v27 = L"CVssClusterAPI::IsResourceReferringVolume";
                  v28 = L"CLUCLUSC";
                  if ( v21 )
                  {
                    v29 = 1274;
                    memset_0(v32, 0, sizeof(v32));
                    CVssFunctionTracer::Trace(
                      v35,
                      &v26,
                      L"Partition has volume GUID %s and does not match the volume name",
                      szVolumeName);
                  }
                  else
                  {
                    v29 = 1270;
                    memset_0(v32, 0, sizeof(v32));
                    CVssFunctionTracer::Trace(v35, &v26, L"Returning cluster resource with empty volume name");
                  }
                  v7 = 1;
                  break;
                }
              }
            }
          }
        }
      }
    }
    if ( lpOutBuffer )
      LocalFree(lpOutBuffer);
    if ( v10 )
      LocalFree(v10);
  }
LABEL_35:
  v22 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v35, v7);
  CVssFunctionTracer::~CVssFunctionTracer(v35);
  return v22;
}

```

## disassembly

```asm
0x18003f7e8  mov     [rsp-8+arg_0], rbx
0x18003f7ed  push    rbp
0x18003f7ee  push    rsi
0x18003f7ef  push    rdi
0x18003f7f0  push    r12
0x18003f7f2  push    r13
0x18003f7f4  push    r14
0x18003f7f6  push    r15
0x18003f7f8  lea     rbp, [rsp-4F0h]
0x18003f800  sub     rsp, 5F0h
0x18003f807  mov     rax, cs:__security_cookie
0x18003f80e  xor     rax, rsp
0x18003f811  mov     [rbp+520h+var_40], rax
0x18003f818  mov     r13, r9
0x18003f81b  mov     rsi, r8
0x18003f81e  mov     rdi, rdx
0x18003f821  lea     r15, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003f828  mov     [rsp+620h+var_5D0], r15
0x18003f82d  lea     rbx, aCvssclusterapi_7; "CVssClusterAPI::IsResourceReferringVolu"...
0x18003f834  mov     [rsp+620h+var_5C8], rbx
0x18003f839  lea     rax, aCluclusc; "CLUCLUSC"
0x18003f840  mov     [rsp+620h+var_5C0], rax
0x18003f845  mov     [rsp+620h+var_5B8], 417h
0x18003f84d  mov     [rsp+620h+var_5B4], 0Bh
0x18003f855  mov     [rsp+620h+var_5B0], 0FFh
0x18003f85d  xor     r14d, r14d
0x18003f860  mov     [rbp+520h+var_530], 1000000h
0x18003f867  xor     edx, edx; Val
0x18003f869  lea     r8d, [r14+78h]; Size
0x18003f86d  lea     rcx, [rsp+620h+var_5A8]; void *
0x18003f872  call    memset_0
0x18003f877  xor     r8d, r8d
0x18003f87a  lea     rdx, [rsp+620h+var_5D0]
0x18003f87f  lea     rcx, [rbp+520h+var_520]
0x18003f883  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003f888  nop
0x18003f889  mov     [rsp+620h+BytesReturned], r14d
0x18003f88e  mov     r12b, r14b
0x18003f891  mov     [rsp+620h+var_5D0], r15
0x18003f896  mov     [rsp+620h+var_5C8], rbx
0x18003f89b  lea     rax, aCluclusc; "CLUCLUSC"
0x18003f8a2  mov     [rsp+620h+var_5C0], rax
0x18003f8a7  mov     [rsp+620h+var_5B8], 426h
0x18003f8af  mov     [rsp+620h+var_5B4], 0Bh
0x18003f8b7  mov     [rsp+620h+var_5B0], 0FFh
0x18003f8bf  mov     [rbp+520h+var_530], 1000000h
0x18003f8c6  xor     edx, edx; Val
0x18003f8c8  lea     r8d, [r14+78h]; Size
0x18003f8cc  lea     rcx, [rsp+620h+var_5A8]; void *
0x18003f8d1  call    memset_0
0x18003f8d6  mov     qword ptr [rsp+620h+cbInBufferSize], r13
0x18003f8db  mov     r9, rsi
0x18003f8de  lea     r8, aParametersReso; "Parameters: resource name = %s, pwszVol"...
0x18003f8e5  lea     rdx, [rsp+620h+var_5D0]
0x18003f8ea  lea     rcx, [rbp+520h+var_520]
0x18003f8ee  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003f8f3  mov     [rbp+520h+OutBuffer], r14
0x18003f8f7  lea     rax, [rsp+620h+BytesReturned]
0x18003f8fc  mov     [rsp+620h+lpBytesReturned], rax; lpBytesReturned
0x18003f901  mov     [rsp+620h+cbOutBufferSize], 8; cbOutBufferSize
0x18003f909  lea     rax, [rbp+520h+OutBuffer]
0x18003f90d  mov     [rsp+620h+lpOutBuffer], rax; lpOutBuffer
0x18003f912  mov     [rsp+620h+cbInBufferSize], r14d; cbInBufferSize
0x18003f917  xor     r9d, r9d; lpInBuffer
0x18003f91a  xor     edx, edx; hHostNode
0x18003f91c  mov     r8d, 100000Dh; dwControlCode
0x18003f922  mov     rcx, rdi; hResource
0x18003f925  call    cs:__imp_ClusterResourceControl
0x18003f92b  mov     ebx, eax
0x18003f92d  test    eax, eax
0x18003f92f  jz      short loc_18003F989
0x18003f931  mov     [rsp+620h+var_5D0], r15
0x18003f936  lea     rax, aCvssclusterapi_7; "CVssClusterAPI::IsResourceReferringVolu"...
0x18003f93d  mov     [rsp+620h+var_5C8], rax
0x18003f942  lea     rax, aCluclusc; "CLUCLUSC"
0x18003f949  mov     [rsp+620h+var_5C0], rax
0x18003f94e  mov     [rsp+620h+var_5B8], 436h
0x18003f956  mov     [rsp+620h+var_5B4], 0Bh
0x18003f95e  mov     [rsp+620h+var_5B0], 0FFh
0x18003f966  mov     [rbp+520h+var_530], 1000000h
0x18003f96d  xor     edx, edx; Val
0x18003f96f  lea     r8d, [r14+78h]; Size
0x18003f973  lea     rcx, [rsp+620h+var_5A8]; void *
0x18003f978  call    memset_0
0x18003f97d  lea     r8, aCouldnTGetReso; "Couldn't get resource class for %s: [0x"...
0x18003f984  jmp     loc_18003FE02
0x18003f989  cmp     dword ptr [rbp+520h+OutBuffer], 1
0x18003f98d  jnz     loc_18003FE17
0x18003f993  lea     rax, [rsp+620h+BytesReturned]
0x18003f998  mov     [rsp+620h+lpBytesReturned], rax; lpBytesReturned
0x18003f99d  mov     [rsp+620h+cbOutBufferSize], r14d; cbOutBufferSize
0x18003f9a2  mov     [rsp+620h+lpOutBuffer], r14; lpOutBuffer
0x18003f9a7  mov     [rsp+620h+cbInBufferSize], r14d; cbInBufferSize
0x18003f9ac  xor     r9d, r9d; lpInBuffer
0x18003f9af  xor     edx, edx; hHostNode
0x18003f9b1  mov     r8d, 100002Dh; dwControlCode
0x18003f9b7  mov     rcx, rdi; hResource
0x18003f9ba  call    cs:__imp_ClusterResourceControl
0x18003f9c0  mov     ebx, eax
0x18003f9c2  test    eax, eax
0x18003f9c4  jnz     loc_18003FDAF
0x18003f9ca  mov     rsi, r14
0x18003f9cd  mov     eax, [rsp+620h+BytesReturned]
0x18003f9d1  inc     eax
0x18003f9d3  mov     [rsp+620h+BytesReturned], eax
0x18003f9d7  mov     edx, eax
0x18003f9d9  add     rdx, rdx; uBytes
0x18003f9dc  xor     ecx, ecx; uFlags
0x18003f9de  call    cs:__imp_LocalAlloc
0x18003f9e4  mov     r15, rax
0x18003f9e7  mov     ecx, [rsp+620h+BytesReturned]
0x18003f9eb  inc     ecx
0x18003f9ed  lea     rax, [rsp+620h+BytesReturned]
0x18003f9f2  mov     [rsp+620h+lpBytesReturned], rax; lpBytesReturned
0x18003f9f7  mov     [rsp+620h+cbOutBufferSize], ecx; cbOutBufferSize
0x18003f9fb  mov     [rsp+620h+lpOutBuffer], r15; lpOutBuffer
0x18003fa00  mov     [rsp+620h+cbInBufferSize], r14d; cbInBufferSize
0x18003fa05  xor     r9d, r9d; lpInBuffer
0x18003fa08  xor     edx, edx; hHostNode
0x18003fa0a  mov     r8d, 100002Dh; dwControlCode
0x18003fa10  mov     rcx, rdi; hResource
0x18003fa13  call    cs:__imp_ClusterResourceControl
0x18003fa19  lea     rcx, aPhysicalDisk; "Physical Disk"
0x18003fa20  mov     r8, r15
0x18003fa23  sub     r8, rcx
0x18003fa26  movzx   edx, word ptr [rcx]
0x18003fa29  movzx   eax, word ptr [rcx+r8]
0x18003fa2e  sub     edx, eax
0x18003fa30  jnz     short loc_18003FA3A
0x18003fa32  add     rcx, 2
0x18003fa36  test    eax, eax
0x18003fa38  jnz     short loc_18003FA26
0x18003fa3a  test    edx, edx
0x18003fa3c  jnz     loc_18003FD91
0x18003fa42  lea     rax, [rsp+620h+BytesReturned]
0x18003fa47  mov     [rsp+620h+lpBytesReturned], rax; lpBytesReturned
0x18003fa4c  mov     [rsp+620h+cbOutBufferSize], r14d; cbOutBufferSize
0x18003fa51  mov     [rsp+620h+lpOutBuffer], r14; lpOutBuffer
0x18003fa56  mov     [rsp+620h+cbInBufferSize], r14d; cbInBufferSize
0x18003fa5b  xor     r9d, r9d; lpInBuffer
0x18003fa5e  xor     edx, edx; hHostNode
0x18003fa60  mov     r8d, 1000081h; dwControlCode
0x18003fa66  mov     rcx, rdi; hResource
0x18003fa69  call    cs:__imp_ClusterResourceControl
0x18003fa6f  mov     ebx, eax
0x18003fa71  test    eax, eax
0x18003fa73  jz      short loc_18003FA7C
0x18003fa75  cmp     eax, 0EAh
0x18003fa7a  jnz     short loc_18003FABD
0x18003fa7c  mov     edx, [rsp+620h+BytesReturned]; uBytes
0x18003fa80  xor     ecx, ecx; uFlags
0x18003fa82  call    cs:__imp_LocalAlloc
0x18003fa88  mov     rsi, rax
0x18003fa8b  lea     rax, [rsp+620h+BytesReturned]
0x18003fa90  mov     [rsp+620h+lpBytesReturned], rax; lpBytesReturned
0x18003fa95  mov     ecx, [rsp+620h+BytesReturned]
0x18003fa99  mov     [rsp+620h+cbOutBufferSize], ecx; cbOutBufferSize
0x18003fa9d  mov     [rsp+620h+lpOutBuffer], rsi; lpOutBuffer
0x18003faa2  mov     [rsp+620h+cbInBufferSize], r14d; cbInBufferSize
0x18003faa7  xor     r9d, r9d; lpInBuffer
0x18003faaa  xor     edx, edx; hHostNode
0x18003faac  mov     r8d, 1000081h; dwControlCode
0x18003fab2  mov     rcx, rdi; hResource
0x18003fab5  call    cs:__imp_ClusterResourceControl
0x18003fabb  mov     ebx, eax
0x18003fabd  xor     edx, edx; hHostNode
0x18003fabf  test    ebx, ebx
0x18003fac1  jz      short loc_18003FB20
0x18003fac3  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003faca  mov     [rsp+620h+var_5D0], rax
0x18003facf  lea     rax, aCvssclusterapi_7; "CVssClusterAPI::IsResourceReferringVolu"...
0x18003fad6  mov     [rsp+620h+var_5C8], rax
0x18003fadb  lea     rax, aCluclusc; "CLUCLUSC"
0x18003fae2  mov     [rsp+620h+var_5C0], rax
0x18003fae7  mov     [rsp+620h+var_5B8], 48Fh
0x18003faef  mov     [rsp+620h+var_5B4], 0Bh
0x18003faf7  mov     [rsp+620h+var_5B0], 0FFh
0x18003faff  mov     [rbp+520h+var_530], 1000000h
0x18003fb06  lea     r8d, [rdx+78h]; Size
0x18003fb0a  lea     rcx, [rsp+620h+var_5A8]; void *
0x18003fb0f  call    memset_0
0x18003fb14  lea     r8, aCouldnTReadDis; "Couldn't read disk private properties ["...
0x18003fb1b  jmp     loc_18003FD80
0x18003fb20  lea     rax, [rsp+620h+BytesReturned]
0x18003fb25  mov     [rsp+620h+lpBytesReturned], rax; lpBytesReturned
0x18003fb2a  mov     [rsp+620h+cbOutBufferSize], r14d; cbOutBufferSize
0x18003fb2f  mov     [rsp+620h+lpOutBuffer], r14; lpOutBuffer
0x18003fb34  mov     [rsp+620h+cbInBufferSize], r14d; cbInBufferSize
0x18003fb39  xor     r9d, r9d; lpInBuffer
0x18003fb3c  mov     r8d, 10001F1h; dwControlCode
0x18003fb42  mov     rcx, rdi; hResource
0x18003fb45  call    cs:__imp_ClusterResourceControl
0x18003fb4b  mov     ebx, eax
0x18003fb4d  test    eax, eax
0x18003fb4f  jnz     loc_18003FD26
0x18003fb55  mov     edx, [rsp+620h+BytesReturned]; uBytes
0x18003fb59  xor     ecx, ecx; uFlags
0x18003fb5b  call    cs:__imp_LocalAlloc
0x18003fb61  mov     r14, rax
0x18003fb64  lea     rax, [rsp+620h+BytesReturned]
0x18003fb69  mov     [rsp+620h+lpBytesReturned], rax; lpBytesReturned
0x18003fb6e  mov     edx, [rsp+620h+BytesReturned]
0x18003fb72  mov     [rsp+620h+cbOutBufferSize], edx; cbOutBufferSize
0x18003fb76  mov     [rsp+620h+lpOutBuffer], r14; lpOutBuffer
0x18003fb7b  mov     [rsp+620h+cbInBufferSize], ebx; cbInBufferSize
0x18003fb7f  xor     r9d, r9d; lpInBuffer
0x18003fb82  xor     edx, edx; hHostNode
0x18003fb84  mov     r8d, 10001F1h; dwControlCode
0x18003fb8a  mov     rcx, rdi; hResource
0x18003fb8d  call    cs:__imp_ClusterResourceControl
0x18003fb93  mov     ebx, eax
0x18003fb95  test    eax, eax
0x18003fb97  jnz     loc_18003FD26
0x18003fb9d  mov     rbx, r14
0x18003fba0  mov     eax, [rsp+620h+BytesReturned]
0x18003fba4  add     rax, r14
0x18003fba7  cmp     rbx, rax
0x18003fbaa  jnb     loc_18003FD91
0x18003fbb0  cmp     dword ptr [rbx], 0
0x18003fbb3  jz      loc_18003FD91
0x18003fbb9  cmp     dword ptr [rbx], 0D0001h
0x18003fbbf  jnz     loc_18003FC67
0x18003fbc5  xor     edx, edx; Val
0x18003fbc7  mov     r8d, 208h; Size
0x18003fbcd  lea     rcx, [rbp+520h+szVolumeMountPoint]; void *
0x18003fbd4  call    memset_0
0x18003fbd9  xor     edx, edx; Val
0x18003fbdb  mov     r8d, 208h; Size
0x18003fbe1  lea     rcx, [rbp+520h+szVolumeName]; void *
0x18003fbe8  call    memset_0
0x18003fbed  xor     edx, edx; Val
0x18003fbef  lea     r8d, [rdx+50h]; Size
0x18003fbf3  lea     rcx, [rbp+520h+sz]; void *
0x18003fbf7  call    memset_0
0x18003fbfc  lea     rcx, [rbx+480h]; rguid
0x18003fc03  mov     r8d, 28h ; '('; cchMax
0x18003fc09  lea     rdx, [rbp+520h+sz]; lpsz
0x18003fc0d  call    cs:__imp_StringFromGUID2
0x18003fc13  mov     edi, eax
0x18003fc15  lea     r9, [rbp+520h+sz]
0x18003fc19  lea     r8, aVolumeS; "\\\\?\\Volume%s\\"
0x18003fc20  mov     edx, 104h; unsigned __int64
0x18003fc25  lea     rcx, [rbp+520h+szVolumeMountPoint]; unsigned __int16 *
0x18003fc2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003fc31  mov     r8d, 104h; cchBufferLength
0x18003fc37  lea     rdx, [rbp+520h+szVolumeName]; lpszVolumeName
0x18003fc3e  lea     rcx, [rbp+520h+szVolumeMountPoint]; lpszVolumeMountPoint
0x18003fc45  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18003fc4b  test    eax, eax
0x18003fc4d  jz      short loc_18003FC67
0x18003fc4f  test    edi, edi
0x18003fc51  jz      short loc_18003FC67
0x18003fc53  mov     rdx, r13
0x18003fc56  lea     rcx, [rbp+520h+szVolumeName]
0x18003fc5d  call    cs:__imp__o__wcsicmp
0x18003fc63  test    eax, eax
0x18003fc65  jz      short loc_18003FC76
0x18003fc67  mov     eax, [rbx+4]
0x18003fc6a  add     rbx, 8
0x18003fc6e  add     rbx, rax
0x18003fc71  jmp     loc_18003FBA0
0x18003fc76  lea     rcx, [rbx+214h]
0x18003fc7d  lea     rdx, qword_180050E70
0x18003fc84  call    cs:__imp__o__wcsicmp
0x18003fc8a  mov     [rsp+620h+var_5B4], 0Bh
0x18003fc92  mov     [rsp+620h+var_5B0], 0FFh
0x18003fc9a  mov     [rbp+520h+var_530], 1000000h
0x18003fca1  xor     edx, edx; Val
0x18003fca3  lea     r8d, [rdx+78h]; Size
0x18003fca7  lea     rcx, [rsp+620h+var_5A8]; void *
0x18003fcac  test    eax, eax
0x18003fcae  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003fcb5  mov     [rsp+620h+var_5D0], rax
0x18003fcba  lea     rax, aCvssclusterapi_7; "CVssClusterAPI::IsResourceReferringVolu"...
0x18003fcc1  mov     [rsp+620h+var_5C8], rax
0x18003fcc6  lea     rax, aCluclusc; "CLUCLUSC"
0x18003fccd  mov     [rsp+620h+var_5C0], rax
0x18003fcd2  jnz     short loc_18003FCF8
0x18003fcd4  mov     [rsp+620h+var_5B8], 4F6h
0x18003fcdc  call    memset_0
0x18003fce1  lea     r8, aReturningClust; "Returning cluster resource with empty v"...
0x18003fce8  lea     rdx, [rsp+620h+var_5D0]
0x18003fced  lea     rcx, [rbp+520h+var_520]
0x18003fcf1  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003fcf6  jmp     short loc_18003FD21
0x18003fcf8  mov     [rsp+620h+var_5B8], 4FAh
0x18003fd00  call    memset_0
0x18003fd05  lea     r9, [rbp+520h+szVolumeName]
0x18003fd0c  lea     r8, aPartitionHasVo; "Partition has volume GUID %s and does n"...
0x18003fd13  lea     rdx, [rsp+620h+var_5D0]
0x18003fd18  lea     rcx, [rbp+520h+var_520]
0x18003fd1c  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003fd21  mov     r12b, 1
0x18003fd24  jmp     short loc_18003FD91
0x18003fd26  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003fd2d  mov     [rsp+620h+var_5D0], rax
0x18003fd32  lea     rax, aCvssclusterapi_7; "CVssClusterAPI::IsResourceReferringVolu"...
0x18003fd39  mov     [rsp+620h+var_5C8], rax
0x18003fd3e  lea     rax, aCluclusc; "CLUCLUSC"
0x18003fd45  mov     [rsp+620h+var_5C0], rax
  ... truncated ...
```
