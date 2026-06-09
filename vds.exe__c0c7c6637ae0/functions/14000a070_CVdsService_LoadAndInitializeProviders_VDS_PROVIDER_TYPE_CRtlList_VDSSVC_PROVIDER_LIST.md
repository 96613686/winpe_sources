# CVdsService::LoadAndInitializeProviders(_VDS_PROVIDER_TYPE,CRtlList &,_VDSSVC_PROVIDER_LIST * *)

- ea: `0x14000a070`
- end: `0x14000a869`
- name: `?LoadAndInitializeProviders@CVdsService@@CAJW4_VDS_PROVIDER_TYPE@@AEAVCRtlList@@PEAPEAU_VDSSVC_PROVIDER_LIST@@@Z`
- size: `2041`
- prototype: `__int64 __fastcall(enum _VDS_PROVIDER_TYPE, struct CRtlList *, struct _VDSSVC_PROVIDER_LIST **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140009e70`

## callees

- `0x1400069e8`
- `0x14000a070`
- `0x14000d95c`
- `0x140013298`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000a1d8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000a1d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a26c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a2ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a26c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a2ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a61c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a61c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a69b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a69b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a818`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a818`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a14b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a14b`
- `vdsutil!?InsertHeadPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000a758`
- `vdsutil!?InsertHeadPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000a758`
- `vdsutil!IsClientSKU` at `0x14000a682`
- `vdsutil!IsClientSKU` at `0x14000a682`
- `vdsutil!VdsHeapAlloc` at `0x14000a6ac`
- `vdsutil!VdsHeapAlloc` at `0x14000a6ac`
- `vdsutil!IsRunningOnAMD64` at `0x14000a678`
- `vdsutil!IsRunningOnAMD64` at `0x14000a678`
- `vdsutil!VdsTraceEx` at `0x14000a17a`
- `vdsutil!VdsTraceEx` at `0x14000a2ce`
- `vdsutil!VdsTraceEx` at `0x14000a2e5`
- `vdsutil!VdsTraceEx` at `0x14000a3ae`
- `vdsutil!VdsTraceEx` at `0x14000a4a0`
- `vdsutil!VdsTraceEx` at `0x14000a5dc`
- `vdsutil!VdsTraceEx` at `0x14000a7b6`
- `vdsutil!VdsTraceEx` at `0x14000a7ee`
- `vdsutil!VdsTraceEx` at `0x14000a17a`
- `vdsutil!VdsTraceEx` at `0x14000a2ce`
- `vdsutil!VdsTraceEx` at `0x14000a2e5`
- `vdsutil!VdsTraceEx` at `0x14000a3ae`
- `vdsutil!VdsTraceEx` at `0x14000a4a0`
- `vdsutil!VdsTraceEx` at `0x14000a5dc`
- `vdsutil!VdsTraceEx` at `0x14000a7b6`
- `vdsutil!VdsTraceEx` at `0x14000a7ee`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a0ee`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a20a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a327`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a3f0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a4de`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a0ee`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a20a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a327`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a3f0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000a4de`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a186`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a249`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a28a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a363`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a433`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a523`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a788`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a794`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a7a0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a824`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a186`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a249`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a28a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a363`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a433`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a523`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a788`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a794`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a7a0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a824`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000a748`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000a748`

## string_xrefs

- `0x14000a1f9`: `CVdsService::IsBuiltinProvider()`
- `0x14000a317`: `CVdsService::IsBuiltinProvider()`
- `0x14000a3e0`: `CVdsService::IsBuiltinProvider()`
- `0x14000a4ce`: `CVdsService::IsBuiltinProvider()`
- `0x14000a0dd`: `CVdsService::LoadAndInitializeProviders()`
- `0x14000a16c`: `CVdsService::LoadAndInitializeProviders, 1, error=%ld`
- `0x14000a7e0`: `CVdsService::LoadAndInitializeProviders, 2, error=%ld`
- `0x14000a2bd`: `CVdsService::LoadAndInitializeProviders, 2b, hr=%lX`
- `0x14000a27c`: `CVdsService::LoadAndInitializeProviders, 2c, hr=%lX`
- `0x14000a2d7`: `CVdsService::LoadAndInitializeProviders, 3, hr=%lX`
- `0x14000a3a0`: `CVdsService::LoadAndInitializeProviders, 4, hr=%lX`
- `0x14000a492`: `CVdsService::LoadAndInitializeProviders, 5, hr=%lX`
- `0x14000a5ce`: `CVdsService::LoadAndInitializeProviders, 6, hr=%lX`
- `0x14000a7a8`: `CVdsService::InitializeThread: *ppVdsProviderNext Alloc: Out of memory.`
- `0x14000a10b`: `System\CurrentControlSet\Services\vds`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsService::LoadAndInitializeProviders(
        enum _VDS_PROVIDER_TYPE a1,
        struct CRtlList *a2,
        struct _VDSSVC_PROVIDER_LIST **a3)
{
  __int64 v5; // r14
  int v6; // ebx
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  int v10; // esi
  int v11; // r13d
  int NextProviderClsid; // eax
  HRESULT v13; // eax
  int v14; // edi
  HRESULT v15; // eax
  int v16; // ebx
  int v17; // eax
  int v18; // ebx
  signed int v19; // eax
  unsigned int v20; // eax
  HANDLE ProcessHeap; // rax
  __int64 v22; // rax
  GUID *v23; // rdx
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v28[16]; // [rsp+60h] [rbp-A0h] BYREF
  struct CVdsCallbackObject *v29; // [rsp+70h] [rbp-90h]
  _BYTE v30[16]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v31[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v32[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v33[24]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v34; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID pv[2]; // [rsp+D0h] [rbp-30h]
  LPVOID v36[2]; // [rsp+E0h] [rbp-20h]
  __int128 v37; // [rsp+F0h] [rbp-10h]
  GUID rguid; // [rsp+100h] [rbp+0h] BYREF
  IID rclsid; // [rsp+110h] [rbp+10h] BYREF
  OLECHAR sz[56]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR SubKey[104]; // [rsp+190h] [rbp+90h] BYREF

  v5 = a1;
  v6 = 0;
  hKey = 0;
  ppv = 0;
  v26 = 0;
  v25 = 0;
  rclsid = 0;
  rguid = 0;
  v34 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v28, 0x5Eu, "CVdsService::LoadAndInitializeProviders()");
  StringCchPrintfW(SubKey, 0x64u, L"%s\\%s", g_wszVdsKey, &(&g_wszVdsProviderKeys)[25 * v5]);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2000000u, &hKey);
  if ( v7 )
  {
    if ( v7 > 0 )
    {
      v8 = (unsigned __int16)v7 | 0x80070000;
      if ( v7 == 2 )
      {
LABEL_6:
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
        return v8;
      }
    }
    else
    {
      v8 = v7;
    }
    VdsTraceEx(94, 0, "CVdsService::LoadAndInitializeProviders, 1, error=%ld", v7);
    goto LABEL_6;
  }
  v10 = 1;
  v29 = CVdsService::m_pCallbackObject;
  v11 = 0;
  NextProviderClsid = CVdsService::GetNextProviderClsid(hKey, 0, &rclsid, &rguid);
  if ( NextProviderClsid )
  {
    v14 = 0;
LABEL_78:
    if ( NextProviderClsid != 259 )
    {
      if ( NextProviderClsid > 0 )
        v14 = (unsigned __int16)NextProviderClsid | 0x80070000;
      else
        v14 = NextProviderClsid;
      VdsTraceEx(94, 0, "CVdsService::LoadAndInitializeProviders, 2, error=%ld", NextProviderClsid);
    }
    goto LABEL_83;
  }
  while ( 2 )
  {
    StringFromGUID2(&rguid, sz, 50);
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v30, 0x5Eu, "CVdsService::IsBuiltinProvider()");
    while ( memcmp_0(&rguid, &qword_14009A450[2 * v6], 0x10u) )
    {
      if ( (unsigned int)++v6 >= 0xC )
      {
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v30);
        v13 = CoCreateInstance(&rclsid, 0, 4u, &IID_IUnknown, &ppv);
        v14 = v13;
        if ( v13 < 0 )
        {
          VdsTraceEx(94, 0, "CVdsService::LoadAndInitializeProviders, 2c, hr=%lX", (unsigned int)v13);
          goto LABEL_17;
        }
        goto LABEL_21;
      }
    }
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v30);
    v15 = CoCreateInstance(&rclsid, 0, 1u, &IID_IUnknown, &ppv);
    v14 = v15;
    if ( v15 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsService::LoadAndInitializeProviders, 2b, hr=%lX", (unsigned int)v15);
LABEL_17:
      VdsTraceEx(94, 0, "CVdsService::LoadAndInitializeProviders, 3, hr=%lX", v14);
      VdsLogError(0xC200000F, 0, 0, v14, 0x200000Au, sz, 0);
      CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v31, 0x5Eu, "CVdsService::IsBuiltinProvider()");
      v16 = 0;
      while ( memcmp_0(&rguid, &qword_14009A450[2 * v16], 0x10u) )
      {
        if ( (unsigned int)++v16 >= 0xC )
        {
          CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v31);
          v6 = 0;
          v10 = 0;
          v14 = 1;
          goto LABEL_71;
        }
      }
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v31);
      goto LABEL_83;
    }
LABEL_21:
    v17 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IVdsProviderPrivate, &v25);
    v14 = v17;
    if ( v17 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, int *, struct CVdsCallbackObject *))(*(_QWORD *)v25 + 32LL))(
              v25,
              &dword_140063D5C,
              v29);
      if ( v25 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v6 = 0;
        v25 = 0;
      }
      else
      {
        v6 = 0;
      }
      if ( v14 < 0 )
      {
        VdsTraceEx(94, 0, "CVdsService::LoadAndInitializeProviders, 5, hr=%lX", v14);
        VdsLogError(0xC200000F, 0, 0, v14, 0x200000Cu, sz, 0);
        CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v33, 0x5Eu, "CVdsService::IsBuiltinProvider()");
        while ( memcmp_0(&rguid, &qword_14009A450[2 * v6], 0x10u) )
        {
          if ( (unsigned int)++v6 >= 0xC )
          {
            CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v33);
            v6 = 0;
            v10 = 0;
            v14 = 1;
            goto LABEL_71;
          }
        }
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v33);
        goto LABEL_83;
      }
      if ( (_DWORD)v5 == 1 )
      {
        v19 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IVdsProvider, &v26);
        if ( v19 < 0 )
        {
          VdsLogError(0xC2000010, 0, 0, v19, 0x200000Du, sz, 0);
LABEL_37:
          v10 = 0;
          v14 = 1;
          goto LABEL_71;
        }
        v14 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v26 + 24LL))(v26, &v34);
        if ( v26 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          v26 = 0;
        }
        if ( v14 < 0 )
        {
          VdsTraceEx(94, 0, "CVdsService::LoadAndInitializeProviders, 6, hr=%lX", v14);
          VdsLogError(0xC2000010, 0, 0, v14, 0x200000Eu, sz, 0);
          goto LABEL_37;
        }
        if ( pv[0] )
        {
          CoTaskMemFree(pv[0]);
          pv[0] = 0;
        }
        if ( v36[1] )
        {
          CoTaskMemFree(v36[1]);
          v36[1] = 0;
        }
        v20 = CVdsService::m_ulFlags;
        if ( SDWORD1(v37) < 0 )
        {
          v20 = CVdsService::m_ulFlags | 1;
          CVdsService::m_ulFlags |= 1u;
        }
        if ( (DWORD1(v37) & 0x40000000) != 0 )
        {
          v20 |= 2u;
          CVdsService::m_ulFlags = v20;
        }
        if ( (BYTE4(v37) & 0x20) != 0 )
        {
          v20 |= 0x100u;
          CVdsService::m_ulFlags = v20;
        }
        if ( (BYTE4(v37) & 0x40) != 0 )
        {
          v20 |= 0x200u;
          CVdsService::m_ulFlags = v20;
        }
        if ( (DWORD1(v37) & 0x20000000) != 0 )
          CVdsService::m_ulFlags = v20 | 8;
        if ( (unsigned int)IsRunningOnAMD64() || !(unsigned int)IsClientSKU() )
          CVdsService::m_ulFlags |= 0x400u;
      }
      if ( a3 )
      {
        ProcessHeap = GetProcessHeap();
        v22 = VdsHeapAlloc(ProcessHeap, 0, 32);
        *a3 = (struct _VDSSVC_PROVIDER_LIST *)v22;
        if ( !v22 )
        {
          VdsTraceEx(94, 0, "CVdsService::InitializeThread: *ppVdsProviderNext Alloc: Out of memory.");
          v14 = -2147024882;
          goto LABEL_83;
        }
        *(_OWORD *)v22 = 0;
        *(_OWORD *)(v22 + 16) = 0;
        *(_QWORD *)*a3 = ppv;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)*a3 + 8LL))(*(_QWORD *)*a3);
        *(GUID *)((char *)*a3 + 8) = rguid;
        a3 = (struct _VDSSVC_PROVIDER_LIST **)((char *)*a3 + 24);
      }
      if ( (_DWORD)v5 == 1 )
      {
        v23 = &g_guidBasicProviderId;
      }
      else
      {
        if ( (_DWORD)v5 != 2 )
          goto LABEL_69;
        if ( !memcmp_0(&rguid, &g_guidGenMpPrvProviderId, 0x10u) )
        {
LABEL_68:
          CRtlList::InsertTailPointer(a2, ppv);
LABEL_70:
          ppv = 0;
LABEL_71:
          NextProviderClsid = CVdsService::GetNextProviderClsid(hKey, ++v11, &rclsid, &rguid);
          if ( NextProviderClsid )
            goto LABEL_78;
          continue;
        }
        v23 = &g_guidGenIsPrvProviderId;
      }
      if ( !memcmp_0(&rguid, v23, 0x10u) )
        goto LABEL_68;
LABEL_69:
      CRtlList::InsertHeadPointer(a2, ppv);
      goto LABEL_70;
    }
    break;
  }
  VdsTraceEx(94, 0, "CVdsService::LoadAndInitializeProviders, 4, hr=%lX", v17);
  VdsLogError(0xC200000F, 0, 0, v14, 0x200000Bu, sz, 0);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v32, 0x5Eu, "CVdsService::IsBuiltinProvider()");
  v18 = 0;
  while ( memcmp_0(&rguid, &qword_14009A450[2 * v18], 0x10u) )
  {
    if ( (unsigned int)++v18 >= 0xC )
    {
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v32);
      v6 = 0;
      v10 = 0;
      v14 = 1;
      goto LABEL_71;
    }
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v32);
LABEL_83:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  RegCloseKey(hKey);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
  if ( v14 >= 0 )
    return v10 == 0;
  else
    return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000a070  mov     [rsp-8+arg_18], rbx
0x14000a075  push    rbp
0x14000a076  push    rsi
0x14000a077  push    rdi
0x14000a078  push    r12
0x14000a07a  push    r13
0x14000a07c  push    r14
0x14000a07e  push    r15
0x14000a080  lea     rbp, [rsp-170h]
0x14000a088  sub     rsp, 270h
0x14000a08f  mov     rax, cs:__security_cookie
0x14000a096  xor     rax, rsp
0x14000a099  mov     [rbp+1A0h+var_40], rax
0x14000a0a0  mov     r15, r8
0x14000a0a3  mov     r12, rdx
0x14000a0a6  movsxd  r14, ecx
0x14000a0a9  xor     ebx, ebx
0x14000a0ab  mov     [rsp+2A0h+hKey], rbx
0x14000a0b0  mov     [rsp+2A0h+ppv], rbx
0x14000a0b5  mov     [rsp+2A0h+var_250], rbx
0x14000a0ba  mov     [rsp+2A0h+var_258], rbx
0x14000a0bf  xorps   xmm0, xmm0
0x14000a0c2  movups  xmmword ptr [rbp+1A0h+rclsid.Data1], xmm0
0x14000a0c6  xorps   xmm1, xmm1
0x14000a0c9  movups  xmmword ptr [rbp+1A0h+rguid.Data1], xmm1
0x14000a0cd  movups  [rbp+1A0h+var_1E0], xmm0
0x14000a0d1  movups  xmmword ptr [rbp+1A0h+pv], xmm0
0x14000a0d5  movups  xmmword ptr [rbp+1A0h+var_1C0], xmm0
0x14000a0d9  movups  [rbp+1A0h+var_1B0], xmm0
0x14000a0dd  lea     r8, aCvdsserviceLoa_4; "CVdsService::LoadAndInitializeProviders"...
0x14000a0e4  mov     edx, 5Eh ; '^'
0x14000a0e9  lea     rcx, [rsp+2A0h+var_240]
0x14000a0ee  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000a0f4  nop
0x14000a0f5  imul    rcx, r14, 0C8h
0x14000a0fc  lea     rax, ?g_wszVdsProviderKeys@@3PAY0GE@GA; "Uknown"
0x14000a103  add     rcx, rax
0x14000a106  mov     [rsp+2A0h+phkResult], rcx
0x14000a10b  lea     r9, ?g_wszVdsKey@@3PAGA; "System\\CurrentControlSet\\Services\\vd"...
0x14000a112  lea     r8, aSS; "%s\\%s"
0x14000a119  mov     edx, 64h ; 'd'; unsigned __int64
0x14000a11e  lea     rcx, [rbp+1A0h+SubKey]; unsigned __int16 *
0x14000a125  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a12a  lea     rax, [rsp+2A0h+hKey]
0x14000a12f  mov     [rsp+2A0h+phkResult], rax; phkResult
0x14000a134  mov     r9d, 2000000h; samDesired
0x14000a13a  xor     r8d, r8d; ulOptions
0x14000a13d  lea     rdx, [rbp+1A0h+SubKey]; lpSubKey
0x14000a144  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a14b  call    cs:__imp_RegOpenKeyExW
0x14000a151  test    eax, eax
0x14000a153  jz      short loc_14000A193
0x14000a155  jg      short loc_14000A15B
0x14000a157  mov     ebx, eax
0x14000a159  jmp     short loc_14000A169
0x14000a15b  movzx   ebx, ax
0x14000a15e  or      ebx, 80070000h
0x14000a164  cmp     eax, 2
0x14000a167  jz      short loc_14000A181
0x14000a169  mov     r9d, eax
0x14000a16c  lea     r8, aCvdsserviceLoa_13; "CVdsService::LoadAndInitializeProviders"...
0x14000a173  xor     edx, edx
0x14000a175  mov     ecx, 5Eh ; '^'
0x14000a17a  call    cs:__imp_VdsTraceEx
0x14000a180  nop
0x14000a181  lea     rcx, [rsp+2A0h+var_240]
0x14000a186  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000a18c  mov     eax, ebx
0x14000a18e  jmp     loc_14000A83F
0x14000a193  mov     esi, 1
0x14000a198  mov     rax, cs:?m_pCallbackObject@CVdsService@@0PEAVCVdsCallbackObject@@EA; CVdsCallbackObject * CVdsService::m_pCallbackObject
0x14000a19f  mov     [rsp+2A0h+var_230], rax
0x14000a1a4  mov     r13d, ebx
0x14000a1a7  lea     r9, [rbp+1A0h+rguid]; LPCLSID
0x14000a1ab  lea     r8, [rbp+1A0h+rclsid]; pclsid
0x14000a1af  xor     edx, edx; dwIndex
0x14000a1b1  mov     rcx, [rsp+2A0h+hKey]; hKey
0x14000a1b6  call    ?GetNextProviderClsid@CVdsService@@CAKPEAUHKEY__@@HPEAU_GUID@@1@Z; CVdsService::GetNextProviderClsid(HKEY__ *,int,_GUID *,_GUID *)
0x14000a1bb  test    eax, eax
0x14000a1bd  jnz     loc_14000A7C3
0x14000a1c3  lea     rdi, qword_14009A450
0x14000a1ca  mov     r8d, 32h ; '2'; cchMax
0x14000a1d0  lea     rdx, [rbp+1A0h+sz]; lpsz
0x14000a1d4  lea     rcx, [rbp+1A0h+rguid]; rguid
0x14000a1d8  call    cs:__imp_StringFromGUID2
0x14000a1de  mov     rcx, [rsp+2A0h+ppv]
0x14000a1e3  test    rcx, rcx
0x14000a1e6  jz      short loc_14000A1F9
0x14000a1e8  mov     rax, [rcx]
0x14000a1eb  mov     rax, [rax+10h]
0x14000a1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1f4  mov     [rsp+2A0h+ppv], rbx
0x14000a1f9  lea     r8, aCvdsserviceIsb; "CVdsService::IsBuiltinProvider()"
0x14000a200  mov     edx, 5Eh ; '^'
0x14000a205  lea     rcx, [rsp+2A0h+var_228]
0x14000a20a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000a210  nop
0x14000a211  nop     dword ptr [rax+00h]
0x14000a215  nop     word ptr [rax+rax+00000000h]
0x14000a220  movsxd  rdx, ebx
0x14000a223  shl     rdx, 4
0x14000a227  add     rdx, rdi; Buf2
0x14000a22a  mov     r8d, 10h; Size
0x14000a230  lea     rcx, [rbp+1A0h+rguid]; Buf1
0x14000a234  call    memcmp_0
0x14000a239  test    eax, eax
0x14000a23b  jz      short loc_14000A285
0x14000a23d  inc     ebx
0x14000a23f  cmp     ebx, 0Ch
0x14000a242  jb      short loc_14000A220
0x14000a244  lea     rcx, [rsp+2A0h+var_228]
0x14000a249  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000a24f  lea     rax, [rsp+2A0h+ppv]
0x14000a254  mov     [rsp+2A0h+phkResult], rax; ppv
0x14000a259  lea     r9, IID_IUnknown; riid
0x14000a260  xor     edx, edx; pUnkOuter
0x14000a262  mov     r8d, 4; dwClsContext
0x14000a268  lea     rcx, [rbp+1A0h+rclsid]; rclsid
0x14000a26c  call    cs:__imp_CoCreateInstance
0x14000a272  mov     edi, eax
0x14000a274  test    eax, eax
0x14000a276  jns     loc_14000A377
0x14000a27c  lea     r8, aCvdsserviceLoa_17; "CVdsService::LoadAndInitializeProviders"...
0x14000a283  jmp     short loc_14000A2C4
0x14000a285  lea     rcx, [rsp+2A0h+var_228]
0x14000a28a  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000a290  lea     rax, [rsp+2A0h+ppv]
0x14000a295  mov     [rsp+2A0h+phkResult], rax; ppv
0x14000a29a  lea     r9, IID_IUnknown; riid
0x14000a2a1  xor     edx, edx; pUnkOuter
0x14000a2a3  mov     r8d, 1; dwClsContext
0x14000a2a9  lea     rcx, [rbp+1A0h+rclsid]; rclsid
0x14000a2ad  call    cs:__imp_CoCreateInstance
0x14000a2b3  mov     edi, eax
0x14000a2b5  test    eax, eax
0x14000a2b7  jns     loc_14000A377
0x14000a2bd  lea     r8, aCvdsserviceLoa_21; "CVdsService::LoadAndInitializeProviders"...
0x14000a2c4  mov     r9d, eax
0x14000a2c7  xor     edx, edx
0x14000a2c9  mov     ecx, 5Eh ; '^'
0x14000a2ce  call    cs:__imp_VdsTraceEx
0x14000a2d4  mov     r9d, edi
0x14000a2d7  lea     r8, aCvdsserviceLoa_10; "CVdsService::LoadAndInitializeProviders"...
0x14000a2de  xor     edx, edx
0x14000a2e0  mov     ecx, 5Eh ; '^'
0x14000a2e5  call    cs:__imp_VdsTraceEx
0x14000a2eb  mov     [rsp+2A0h+var_270], 0
0x14000a2f4  lea     rax, [rbp+1A0h+sz]
0x14000a2f8  mov     [rsp+2A0h+var_278], rax; unsigned __int16 *
0x14000a2fd  mov     dword ptr [rsp+2A0h+phkResult], 200000Ah; unsigned int
0x14000a305  mov     r9d, edi; unsigned int
0x14000a308  xor     r8d, r8d; void *
0x14000a30b  xor     edx, edx; unsigned int
0x14000a30d  mov     ecx, 0C200000Fh; unsigned int
0x14000a312  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000a317  lea     r8, aCvdsserviceIsb; "CVdsService::IsBuiltinProvider()"
0x14000a31e  mov     edx, 5Eh ; '^'
0x14000a323  lea     rcx, [rbp+1A0h+var_218]
0x14000a327  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000a32d  nop
0x14000a32e  xor     ebx, ebx
0x14000a330  movsxd  rdx, ebx
0x14000a333  shl     rdx, 4
0x14000a337  lea     rax, qword_14009A450
0x14000a33e  add     rdx, rax; Buf2
0x14000a341  mov     r8d, 10h; Size
0x14000a347  lea     rcx, [rbp+1A0h+rguid]; Buf1
0x14000a34b  call    memcmp_0
0x14000a350  test    eax, eax
0x14000a352  jz      loc_14000A784
0x14000a358  inc     ebx
0x14000a35a  cmp     ebx, 0Ch
0x14000a35d  jb      short loc_14000A330
0x14000a35f  lea     rcx, [rbp+1A0h+var_218]
0x14000a363  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000a369  xor     ebx, ebx
0x14000a36b  mov     esi, ebx
0x14000a36d  mov     edi, 1
0x14000a372  jmp     loc_14000A763
0x14000a377  mov     rcx, [rsp+2A0h+ppv]
0x14000a37c  mov     rax, [rcx]
0x14000a37f  lea     r8, [rsp+2A0h+var_258]
0x14000a384  lea     rdx, IID_IVdsProviderPrivate
0x14000a38b  mov     rax, [rax]
0x14000a38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a393  mov     edi, eax
0x14000a395  test    eax, eax
0x14000a397  jns     loc_14000A447
0x14000a39d  mov     r9d, eax
0x14000a3a0  lea     r8, aCvdsserviceLoa_19; "CVdsService::LoadAndInitializeProviders"...
0x14000a3a7  xor     edx, edx
0x14000a3a9  mov     ecx, 5Eh ; '^'
0x14000a3ae  call    cs:__imp_VdsTraceEx
0x14000a3b4  mov     [rsp+2A0h+var_270], 0
0x14000a3bd  lea     rax, [rbp+1A0h+sz]
0x14000a3c1  mov     [rsp+2A0h+var_278], rax; unsigned __int16 *
0x14000a3c6  mov     dword ptr [rsp+2A0h+phkResult], 200000Bh; unsigned int
0x14000a3ce  mov     r9d, edi; unsigned int
0x14000a3d1  xor     r8d, r8d; void *
0x14000a3d4  xor     edx, edx; unsigned int
0x14000a3d6  mov     ecx, 0C200000Fh; unsigned int
0x14000a3db  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000a3e0  lea     r8, aCvdsserviceIsb; "CVdsService::IsBuiltinProvider()"
0x14000a3e7  mov     edx, 5Eh ; '^'
0x14000a3ec  lea     rcx, [rbp+1A0h+var_208]
0x14000a3f0  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000a3f6  nop
0x14000a3f7  xor     ebx, ebx
0x14000a3f9  nop     dword ptr [rax+00000000h]
0x14000a400  movsxd  rdx, ebx
0x14000a403  shl     rdx, 4
0x14000a407  lea     rax, qword_14009A450
0x14000a40e  add     rdx, rax; Buf2
0x14000a411  mov     r8d, 10h; Size
0x14000a417  lea     rcx, [rbp+1A0h+rguid]; Buf1
0x14000a41b  call    memcmp_0
0x14000a420  test    eax, eax
0x14000a422  jz      loc_14000A790
0x14000a428  inc     ebx
0x14000a42a  cmp     ebx, 0Ch
0x14000a42d  jb      short loc_14000A400
0x14000a42f  lea     rcx, [rbp+1A0h+var_208]
0x14000a433  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000a439  xor     ebx, ebx
0x14000a43b  mov     esi, ebx
0x14000a43d  mov     edi, 1
0x14000a442  jmp     loc_14000A763
0x14000a447  mov     rcx, [rsp+2A0h+var_258]
0x14000a44c  mov     rax, [rcx]
0x14000a44f  mov     r8, [rsp+2A0h+var_230]
0x14000a454  lea     rdx, dword_140063D5C
0x14000a45b  mov     rax, [rax+20h]
0x14000a45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a464  mov     edi, eax
0x14000a466  mov     rcx, [rsp+2A0h+var_258]
0x14000a46b  test    rcx, rcx
0x14000a46e  jz      short loc_14000A485
0x14000a470  mov     rax, [rcx]
0x14000a473  mov     rax, [rax+10h]
0x14000a477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a47c  xor     ebx, ebx
0x14000a47e  mov     [rsp+2A0h+var_258], rbx
0x14000a483  jmp     short loc_14000A487
0x14000a485  xor     ebx, ebx
0x14000a487  test    edi, edi
0x14000a489  jns     loc_14000A537
0x14000a48f  mov     r9d, edi
0x14000a492  lea     r8, aCvdsserviceLoa; "CVdsService::LoadAndInitializeProviders"...
0x14000a499  xor     edx, edx
0x14000a49b  mov     ecx, 5Eh ; '^'
0x14000a4a0  call    cs:__imp_VdsTraceEx
0x14000a4a6  mov     [rsp+2A0h+var_270], rbx
0x14000a4ab  lea     rax, [rbp+1A0h+sz]
0x14000a4af  mov     [rsp+2A0h+var_278], rax; unsigned __int16 *
0x14000a4b4  mov     dword ptr [rsp+2A0h+phkResult], 200000Ch; unsigned int
0x14000a4bc  mov     r9d, edi; unsigned int
0x14000a4bf  xor     r8d, r8d; void *
0x14000a4c2  xor     edx, edx; unsigned int
0x14000a4c4  mov     ecx, 0C200000Fh; unsigned int
0x14000a4c9  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000a4ce  lea     r8, aCvdsserviceIsb; "CVdsService::IsBuiltinProvider()"
0x14000a4d5  mov     edx, 5Eh ; '^'
0x14000a4da  lea     rcx, [rbp+1A0h+var_1F8]
0x14000a4de  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000a4e4  nop
0x14000a4e5  nop     word ptr [rax+rax+00000000h]
0x14000a4f0  movsxd  rdx, ebx
0x14000a4f3  shl     rdx, 4
0x14000a4f7  lea     rax, qword_14009A450
0x14000a4fe  add     rdx, rax; Buf2
0x14000a501  mov     r8d, 10h; Size
0x14000a507  lea     rcx, [rbp+1A0h+rguid]; Buf1
0x14000a50b  call    memcmp_0
0x14000a510  test    eax, eax
0x14000a512  jz      loc_14000A79C
0x14000a518  inc     ebx
0x14000a51a  cmp     ebx, 0Ch
0x14000a51d  jb      short loc_14000A4F0
0x14000a51f  lea     rcx, [rbp+1A0h+var_1F8]
0x14000a523  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000a529  xor     ebx, ebx
0x14000a52b  mov     esi, ebx
0x14000a52d  mov     edi, 1
0x14000a532  jmp     loc_14000A763
0x14000a537  cmp     r14d, 1
0x14000a53b  jnz     loc_14000A696
0x14000a541  mov     rcx, [rsp+2A0h+ppv]
0x14000a546  mov     rax, [rcx]
0x14000a549  lea     r8, [rsp+2A0h+var_250]
0x14000a54e  lea     rdx, IID_IVdsProvider
0x14000a555  mov     rax, [rax]
0x14000a558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a55d  test    eax, eax
0x14000a55f  jns     short loc_14000A595
0x14000a561  mov     [rsp+2A0h+var_270], rbx
0x14000a566  lea     rcx, [rbp+1A0h+sz]
0x14000a56a  mov     [rsp+2A0h+var_278], rcx; unsigned __int16 *
0x14000a56f  mov     dword ptr [rsp+2A0h+phkResult], 200000Dh; unsigned int
0x14000a577  mov     r9d, eax; unsigned int
0x14000a57a  xor     r8d, r8d; void *
  ... truncated ...
```
