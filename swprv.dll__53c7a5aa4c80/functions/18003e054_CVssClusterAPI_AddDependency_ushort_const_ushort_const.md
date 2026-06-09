# CVssClusterAPI::AddDependency(ushort const *,ushort const *)

- ea: `0x18003e054`
- end: `0x18003e56d`
- name: `?AddDependency@CVssClusterAPI@@QEAA_NPEBG0@Z`
- size: `1305`
- prototype: `bool __fastcall(CVssClusterAPI *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x180027ca0`

## callees

- `0x18000212c`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x18003609c`
- `0x18003649c`
- `0x1800367b8`
- `0x18003df54`
- `0x18003dfac`
- `0x18003e054`
- `0x18003e574`
- `0x18003e874`
- `0x18003eafc`
- `0x18003ec7c`
- `0x18003ef54`
- `0x18003f52c`
- `0x1800402e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003e166`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003e166`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003e3f1`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003e401`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003e3f1`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18003e401`
- `ext-ms-win-cluster-clusapi-l1-1-2!AddClusterResourceDependency` at `0x18003e3c0`
- `ext-ms-win-cluster-clusapi-l1-1-2!AddClusterResourceDependency` at `0x18003e3c0`

## string_xrefs

- `0x18003e380`: `Dependency already exists.`
- `0x18003e44a`: `Cannot create a dependency between different volumes on the same disk resource`
- `0x18003e4a9`: `Cannot create a dependency between volumes`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall CVssClusterAPI::AddDependency(
        CVssClusterAPI *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  bool v6; // bl
  unsigned __int16 **v7; // r8
  char v8; // r12
  char v9; // r13
  struct _HRESOURCE *PhysicalDiskResourceForVolumeName; // rsi
  unsigned __int16 **v11; // r8
  struct _HRESOURCE *v12; // rax
  CVssClusterAPI *v13; // rcx
  struct _HRESOURCE *v14; // rbx
  signed __int64 v15; // r14
  int v16; // eax
  int v17; // ecx
  CVssClusterAPI *v18; // rcx
  bool v19; // bl
  const unsigned __int16 *v21; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v22; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+4Ch] [rbp-B4h]
  int v26; // [rsp+50h] [rbp-B0h]
  _BYTE v27[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+D0h] [rbp-30h]
  LPVOID v29; // [rsp+E0h] [rbp-20h] BYREF
  int v30; // [rsp+E8h] [rbp-18h]
  _BYTE v31[96]; // [rsp+150h] [rbp+50h] BYREF
  char v32; // [rsp+1C8h] [rbp+C8h]

  v21 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v22 = L"CVssClusterAPI::AddDependency";
  v23 = L"CLUCLUSC";
  v24 = 181;
  v25 = 11;
  v26 = 255;
  v28 = 0x1000000;
  memset_0(v27, 0, sizeof(v27));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v29, (__int64)&v21, 0);
  CVssClusterResourceList::CVssClusterResourceList((CVssClusterResourceList *)v31);
  v21 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v22 = L"CVssClusterAPI::AddDependency";
  v23 = L"CLUCLUSC";
  v24 = 193;
  v25 = 11;
  v26 = 255;
  v28 = 0x1000000;
  memset_0(v27, 0, sizeof(v27));
  CVssFunctionTracer::Trace(&v29, &v21, L"Parameters: From = %s, To = %s", a2, a3);
  if ( !a2 || !a3 )
  {
    v21 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v22 = L"CVssClusterAPI::AddDependency";
    v23 = L"CLUCLUSC";
    v24 = 196;
    v25 = 11;
    v26 = 255;
    v28 = 0x1000000;
    memset_0(v27, 0, sizeof(v27));
    CVssFunctionTracer::Throw(&v29, &v21, 2147942487LL, L"NULL parameters");
  }
  v6 = 0;
  v32 = 0;
  if ( !(unsigned int)_o__wcsicmp(a2, a3) )
  {
    v21 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v22 = L"CVssClusterAPI::AddDependency";
    v23 = L"CLUCLUSC";
    v24 = 201;
    v25 = 11;
    v26 = 255;
    v28 = 0x1000000;
    memset_0(v27, 0, sizeof(v27));
    CVssFunctionTracer::Trace(&v29, &v21, L"Volumes are identical. No dependency is added");
    goto LABEL_28;
  }
  v8 = 0;
  v9 = 0;
  PhysicalDiskResourceForVolumeName = CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(this, a2, v7);
  v12 = CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(this, a3, v11);
  v14 = v12;
  if ( PhysicalDiskResourceForVolumeName )
  {
    if ( v12 )
    {
      if ( CVssClusterAPI::AreResourcesEqual(v13, PhysicalDiskResourceForVolumeName, v12) )
      {
        v15 = (char *)a3 - (char *)a2;
        do
        {
          v16 = *(const unsigned __int16 *)((char *)a2 + v15);
          v17 = *a2 - v16;
          if ( v17 )
            break;
          ++a2;
        }
        while ( v16 );
        if ( v17 )
        {
          v8 = 1;
        }
        else
        {
          v21 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
          v22 = L"CVssClusterAPI::AddDependency";
          v23 = L"CLUCLUSC";
          v24 = 224;
          v25 = 11;
          v26 = 255;
          v28 = 0x1000000;
          memset_0(v27, 0, sizeof(v27));
          CVssFunctionTracer::Trace(&v29, &v21, L"Volumes are identical. No dependency is added");
        }
      }
      else if ( CVssClusterAPI::IsDependencyAlreadyEstablished(this, PhysicalDiskResourceForVolumeName, v14) )
      {
        v21 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
        v22 = L"CVssClusterAPI::AddDependency";
        v23 = L"CLUCLUSC";
        v24 = 237;
        v25 = 11;
        v26 = 255;
        v28 = 0x1000000;
        memset_0(v27, 0, sizeof(v27));
        CVssFunctionTracer::Trace(&v29, &v21, L"Dependency already exists.");
      }
      else if ( CVssClusterAPI::CanEstablishDependency(v18, PhysicalDiskResourceForVolumeName, v14) )
      {
        CVssClusterAPI::GetFinalOnlineResourceList(
          this,
          PhysicalDiskResourceForVolumeName,
          (struct CVssClusterResourceList *)v31);
        CVssClusterAPI::TakeResourceOffline(this, PhysicalDiskResourceForVolumeName);
        AddClusterResourceDependency(PhysicalDiskResourceForVolumeName, v14);
        CVssClusterAPI::BringResourceListOnline(this, (struct CVssClusterResourceList *)v31);
        v32 = 1;
      }
      else
      {
        v9 = 1;
      }
    }
    CloseClusterResource(PhysicalDiskResourceForVolumeName);
    if ( !v14 )
      goto LABEL_23;
  }
  else if ( !v12 )
  {
    v21 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v22 = L"CVssClusterAPI::AddDependency";
    v23 = L"CLUCLUSC";
    v24 = 210;
    v25 = 11;
    v26 = 255;
    v28 = 0x1000000;
    memset_0(v27, 0, sizeof(v27));
    CVssFunctionTracer::Trace(
      &v29,
      &v21,
      L"Original and diff area volumes are no shared. No dependency cannot be added");
    v6 = 0;
    goto LABEL_28;
  }
  CloseClusterResource(v14);
LABEL_23:
  if ( v8 )
  {
    v21 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v22 = L"CVssClusterAPI::AddDependency";
    v23 = L"CLUCLUSC";
    v24 = 276;
    v25 = 11;
    v26 = 255;
    v28 = 0x1000000;
    memset_0(v27, 0, sizeof(v27));
    CVssFunctionTracer::Throw(
      &v29,
      &v21,
      2147754764LL,
      L"Cannot create a dependency between different volumes on the same disk resource");
  }
  if ( v9 )
  {
    v21 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v22 = L"CVssClusterAPI::AddDependency";
    v23 = L"CLUCLUSC";
    v24 = 281;
    v25 = 11;
    v26 = 255;
    v28 = 0x1000000;
    memset_0(v27, 0, sizeof(v27));
    CVssFunctionTracer::Throw(&v29, &v21, 2147754764LL, L"Cannot create a dependency between volumes");
  }
  v6 = v32;
LABEL_28:
  if ( v30 < 0 )
    CVssFunctionTracer::ReThrow((CVssFunctionTracer *)&v29);
  v19 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v29, v6);
  std::deque<_HRESOURCE *>::~deque<_HRESOURCE *>(v31);
  CVssFunctionTracer::~CVssFunctionTracer(&v29);
  return v19;
}

```

## disassembly

```asm
0x18003e054  mov     [rsp-8+arg_0], rbx
0x18003e059  push    rbp
0x18003e05a  push    rsi
0x18003e05b  push    rdi
0x18003e05c  push    r12
0x18003e05e  push    r13
0x18003e060  push    r14
0x18003e062  push    r15
0x18003e064  lea     rbp, [rsp-80h]
0x18003e069  sub     rsp, 180h
0x18003e070  mov     r14, r8
0x18003e073  mov     rdi, rdx
0x18003e076  mov     r15, rcx
0x18003e079  lea     r12, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003e080  mov     [rsp+1B0h+var_180], r12
0x18003e085  lea     r13, aCvssclusterapi_6; "CVssClusterAPI::AddDependency"
0x18003e08c  mov     [rsp+1B0h+var_178], r13
0x18003e091  lea     rbx, aCluclusc; "CLUCLUSC"
0x18003e098  mov     [rsp+1B0h+var_170], rbx
0x18003e09d  mov     [rsp+1B0h+var_168], 0B5h
0x18003e0a5  mov     [rsp+1B0h+var_164], 0Bh
0x18003e0ad  mov     [rsp+1B0h+var_160], 0FFh
0x18003e0b5  xor     esi, esi
0x18003e0b7  mov     [rbp+0B0h+var_E0], 1000000h
0x18003e0be  xor     edx, edx; Val
0x18003e0c0  lea     r8d, [rsi+78h]; Size
0x18003e0c4  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003e0c9  call    memset_0
0x18003e0ce  xor     r8d, r8d
0x18003e0d1  lea     rdx, [rsp+1B0h+var_180]
0x18003e0d6  lea     rcx, [rbp+0B0h+var_D0]
0x18003e0da  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003e0df  nop
0x18003e0e0  lea     rcx, [rbp+0B0h+var_60]; this
0x18003e0e4  call    ??0CVssClusterResourceList@@QEAA@XZ; CVssClusterResourceList::CVssClusterResourceList(void)
0x18003e0e9  nop
0x18003e0ea  mov     [rsp+1B0h+var_180], r12
0x18003e0ef  mov     [rsp+1B0h+var_178], r13
0x18003e0f4  mov     [rsp+1B0h+var_170], rbx
0x18003e0f9  mov     [rsp+1B0h+var_168], 0C1h
0x18003e101  mov     [rsp+1B0h+var_164], 0Bh
0x18003e109  mov     [rsp+1B0h+var_160], 0FFh
0x18003e111  mov     [rbp+0B0h+var_E0], 1000000h
0x18003e118  xor     edx, edx; Val
0x18003e11a  lea     r8d, [rsi+78h]; Size
0x18003e11e  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003e123  call    memset_0
0x18003e128  mov     [rsp+1B0h+var_190], r14
0x18003e12d  mov     r9, rdi
0x18003e130  lea     r8, aParametersFrom; "Parameters: From = %s, To = %s"
0x18003e137  lea     rdx, [rsp+1B0h+var_180]
0x18003e13c  lea     rcx, [rbp+0B0h+var_D0]
0x18003e140  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003e145  test    rdi, rdi
0x18003e148  jz      loc_18003E513
0x18003e14e  test    r14, r14
0x18003e151  jz      loc_18003E513
0x18003e157  mov     bl, sil
0x18003e15a  mov     [rbp+0B0h+arg_8], bl
0x18003e160  mov     rdx, r14
0x18003e163  mov     rcx, rdi
0x18003e166  call    cs:__imp__o__wcsicmp
0x18003e16c  test    eax, eax
0x18003e16e  jnz     short loc_18003E1CF
0x18003e170  mov     [rsp+1B0h+var_180], r12
0x18003e175  mov     [rsp+1B0h+var_178], r13
0x18003e17a  lea     r15, aCluclusc; "CLUCLUSC"
0x18003e181  mov     [rsp+1B0h+var_170], r15
0x18003e186  mov     [rsp+1B0h+var_168], 0C9h
0x18003e18e  mov     [rsp+1B0h+var_164], 0Bh
0x18003e196  mov     [rsp+1B0h+var_160], 0FFh
0x18003e19e  mov     [rbp+0B0h+var_E0], 1000000h
0x18003e1a5  xor     edx, edx; Val
0x18003e1a7  lea     r8d, [rsi+78h]; Size
0x18003e1ab  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003e1b0  call    memset_0
0x18003e1b5  lea     r8, aVolumesAreIden; "Volumes are identical. No dependency is"...
0x18003e1bc  lea     rdx, [rsp+1B0h+var_180]
0x18003e1c1  lea     rcx, [rbp+0B0h+var_D0]
0x18003e1c5  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003e1ca  jmp     loc_18003E4CB
0x18003e1cf  mov     r12b, sil
0x18003e1d2  mov     r13b, sil
0x18003e1d5  mov     rdx, rdi; unsigned __int16 *
0x18003e1d8  mov     rcx, r15; this
0x18003e1db  call    ?GetPhysicalDiskResourceForVolumeName@CVssClusterAPI@@QEAAPEAU_HRESOURCE@@PEBGPEAPEAG@Z; CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(ushort const *,ushort * *)
0x18003e1e0  mov     rsi, rax
0x18003e1e3  mov     rdx, r14; unsigned __int16 *
0x18003e1e6  mov     rcx, r15; this
0x18003e1e9  call    ?GetPhysicalDiskResourceForVolumeName@CVssClusterAPI@@QEAAPEAU_HRESOURCE@@PEBGPEAPEAG@Z; CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(ushort const *,ushort * *)
0x18003e1ee  mov     rbx, rax
0x18003e1f1  test    rsi, rsi
0x18003e1f4  jnz     short loc_18003E26F
0x18003e1f6  lea     rdi, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003e1fd  lea     r14, aCvssclusterapi_6; "CVssClusterAPI::AddDependency"
0x18003e204  lea     r15, aCluclusc; "CLUCLUSC"
0x18003e20b  test    rax, rax
0x18003e20e  jnz     loc_18003E3FE
0x18003e214  mov     [rsp+1B0h+var_180], rdi
0x18003e219  mov     [rsp+1B0h+var_178], r14
0x18003e21e  mov     [rsp+1B0h+var_170], r15
0x18003e223  mov     [rsp+1B0h+var_168], 0D2h
0x18003e22b  mov     [rsp+1B0h+var_164], 0Bh
0x18003e233  mov     [rsp+1B0h+var_160], 0FFh
0x18003e23b  mov     [rbp+0B0h+var_E0], 1000000h
0x18003e242  xor     edx, edx; Val
0x18003e244  lea     r8d, [rax+78h]; Size
0x18003e248  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003e24d  call    memset_0
0x18003e252  lea     r8, aOriginalAndDif; "Original and diff area volumes are no s"...
0x18003e259  lea     rdx, [rsp+1B0h+var_180]
0x18003e25e  lea     rcx, [rbp+0B0h+var_D0]
0x18003e262  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003e267  mov     bl, sil
0x18003e26a  jmp     loc_18003E4CB
0x18003e26f  test    rbx, rbx
0x18003e272  jz      loc_18003E3D9
0x18003e278  mov     r8, rbx; struct _HRESOURCE *
0x18003e27b  mov     rdx, rsi; struct _HRESOURCE *
0x18003e27e  call    ?AreResourcesEqual@CVssClusterAPI@@QEAA_NPEAU_HRESOURCE@@0@Z; CVssClusterAPI::AreResourcesEqual(_HRESOURCE *,_HRESOURCE *)
0x18003e283  test    al, al
0x18003e285  jz      loc_18003E31B
0x18003e28b  sub     r14, rdi
0x18003e28e  movzx   ecx, word ptr [rdi]
0x18003e291  movzx   eax, word ptr [rdi+r14]
0x18003e296  sub     ecx, eax
0x18003e298  jnz     short loc_18003E2A2
0x18003e29a  add     rdi, 2
0x18003e29e  test    eax, eax
0x18003e2a0  jnz     short loc_18003E28E
0x18003e2a2  lea     rdi, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003e2a9  lea     r14, aCvssclusterapi_6; "CVssClusterAPI::AddDependency"
0x18003e2b0  lea     r15, aCluclusc; "CLUCLUSC"
0x18003e2b7  test    ecx, ecx
0x18003e2b9  jnz     short loc_18003E313
0x18003e2bb  mov     [rsp+1B0h+var_180], rdi
0x18003e2c0  mov     [rsp+1B0h+var_178], r14
0x18003e2c5  mov     [rsp+1B0h+var_170], r15
0x18003e2ca  mov     [rsp+1B0h+var_168], 0E0h
0x18003e2d2  mov     [rsp+1B0h+var_164], 0Bh
0x18003e2da  mov     [rsp+1B0h+var_160], 0FFh
0x18003e2e2  mov     [rbp+0B0h+var_E0], 1000000h
0x18003e2e9  xor     edx, edx; Val
0x18003e2eb  lea     r8d, [rcx+78h]; Size
0x18003e2ef  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003e2f4  call    memset_0
0x18003e2f9  lea     r8, aVolumesAreIden; "Volumes are identical. No dependency is"...
0x18003e300  lea     rdx, [rsp+1B0h+var_180]
0x18003e305  lea     rcx, [rbp+0B0h+var_D0]
0x18003e309  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003e30e  jmp     loc_18003E3EE
0x18003e313  mov     r12b, 1
0x18003e316  jmp     loc_18003E3EE
0x18003e31b  mov     r8, rbx; struct _HRESOURCE *
0x18003e31e  mov     rdx, rsi; struct _HRESOURCE *
0x18003e321  mov     rcx, r15; this
0x18003e324  call    ?IsDependencyAlreadyEstablished@CVssClusterAPI@@QEAA_NPEAU_HRESOURCE@@0@Z; CVssClusterAPI::IsDependencyAlreadyEstablished(_HRESOURCE *,_HRESOURCE *)
0x18003e329  test    al, al
0x18003e32b  jz      short loc_18003E38C
0x18003e32d  lea     rdi, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003e334  mov     [rsp+1B0h+var_180], rdi
0x18003e339  lea     r14, aCvssclusterapi_6; "CVssClusterAPI::AddDependency"
0x18003e340  mov     [rsp+1B0h+var_178], r14
0x18003e345  lea     r15, aCluclusc; "CLUCLUSC"
0x18003e34c  mov     [rsp+1B0h+var_170], r15
0x18003e351  mov     [rsp+1B0h+var_168], 0EDh
0x18003e359  mov     [rsp+1B0h+var_164], 0Bh
0x18003e361  mov     [rsp+1B0h+var_160], 0FFh
0x18003e369  mov     [rbp+0B0h+var_E0], 1000000h
0x18003e370  xor     edx, edx; Val
0x18003e372  lea     r8d, [rdx+78h]; Size
0x18003e376  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003e37b  call    memset_0
0x18003e380  lea     r8, aDependencyAlre; "Dependency already exists."
0x18003e387  jmp     loc_18003E300
0x18003e38c  mov     r8, rbx; struct _HRESOURCE *
0x18003e38f  mov     rdx, rsi; struct _HRESOURCE *
0x18003e392  call    ?CanEstablishDependency@CVssClusterAPI@@QEAA_NPEAU_HRESOURCE@@0@Z; CVssClusterAPI::CanEstablishDependency(_HRESOURCE *,_HRESOURCE *)
0x18003e397  test    al, al
0x18003e399  jnz     short loc_18003E3A0
0x18003e39b  mov     r13b, 1
0x18003e39e  jmp     short loc_18003E3D9
0x18003e3a0  lea     r8, [rbp+0B0h+var_60]; struct CVssClusterResourceList *
0x18003e3a4  mov     rdx, rsi; struct _HRESOURCE *
0x18003e3a7  mov     rcx, r15; this
0x18003e3aa  call    ?GetFinalOnlineResourceList@CVssClusterAPI@@AEAAXPEAU_HRESOURCE@@AEAVCVssClusterResourceList@@@Z; CVssClusterAPI::GetFinalOnlineResourceList(_HRESOURCE *,CVssClusterResourceList &)
0x18003e3af  mov     rdx, rsi; struct _HRESOURCE *
0x18003e3b2  mov     rcx, r15; this
0x18003e3b5  call    ?TakeResourceOffline@CVssClusterAPI@@AEAAXPEAU_HRESOURCE@@@Z; CVssClusterAPI::TakeResourceOffline(_HRESOURCE *)
0x18003e3ba  mov     rdx, rbx; hDependsOn
0x18003e3bd  mov     rcx, rsi; hResource
0x18003e3c0  call    cs:__imp_AddClusterResourceDependency
0x18003e3c6  lea     rdx, [rbp+0B0h+var_60]; struct CVssClusterResourceList *
0x18003e3ca  mov     rcx, r15; this
0x18003e3cd  call    ?BringResourceListOnline@CVssClusterAPI@@AEAAXAEAVCVssClusterResourceList@@@Z; CVssClusterAPI::BringResourceListOnline(CVssClusterResourceList &)
0x18003e3d2  mov     [rbp+0B0h+arg_8], 1
0x18003e3d9  lea     rdi, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003e3e0  lea     r14, aCvssclusterapi_6; "CVssClusterAPI::AddDependency"
0x18003e3e7  lea     r15, aCluclusc; "CLUCLUSC"
0x18003e3ee  mov     rcx, rsi; hResource
0x18003e3f1  call    cs:__imp_CloseClusterResource
0x18003e3f7  xor     esi, esi
0x18003e3f9  test    rbx, rbx
0x18003e3fc  jz      short loc_18003E407
0x18003e3fe  mov     rcx, rbx; hResource
0x18003e401  call    cs:__imp_CloseClusterResource
0x18003e407  test    r12b, r12b
0x18003e40a  jz      short loc_18003E466
0x18003e40c  mov     [rsp+1B0h+var_180], rdi
0x18003e411  mov     [rsp+1B0h+var_178], r14
0x18003e416  mov     [rsp+1B0h+var_170], r15
0x18003e41b  mov     [rsp+1B0h+var_168], 114h
0x18003e423  mov     [rsp+1B0h+var_164], 0Bh
0x18003e42b  mov     [rsp+1B0h+var_160], 0FFh
0x18003e433  mov     [rbp+0B0h+var_E0], 1000000h
0x18003e43a  xor     edx, edx; Val
0x18003e43c  lea     r8d, [rdx+78h]; Size
0x18003e440  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003e445  call    memset_0
0x18003e44a  lea     r9, aCannotCreateAD_0; "Cannot create a dependency between diff"...
0x18003e451  mov     r8d, 8004230Ch
0x18003e457  lea     rdx, [rsp+1B0h+var_180]
0x18003e45c  lea     rcx, [rbp+0B0h+var_D0]
0x18003e460  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003e466  test    r13b, r13b
0x18003e469  jz      short loc_18003E4C5
0x18003e46b  mov     [rsp+1B0h+var_180], rdi
0x18003e470  mov     [rsp+1B0h+var_178], r14
0x18003e475  mov     [rsp+1B0h+var_170], r15
0x18003e47a  mov     [rsp+1B0h+var_168], 119h
0x18003e482  mov     [rsp+1B0h+var_164], 0Bh
0x18003e48a  mov     [rsp+1B0h+var_160], 0FFh
0x18003e492  mov     [rbp+0B0h+var_E0], 1000000h
0x18003e499  xor     edx, edx; Val
0x18003e49b  lea     r8d, [rdx+78h]; Size
0x18003e49f  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003e4a4  call    memset_0
0x18003e4a9  lea     r9, aCannotCreateAD; "Cannot create a dependency between volu"...
0x18003e4b0  mov     r8d, 8004230Ch
0x18003e4b6  lea     rdx, [rsp+1B0h+var_180]
0x18003e4bb  lea     rcx, [rbp+0B0h+var_D0]
0x18003e4bf  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003e4c5  mov     bl, [rbp+0B0h+arg_8]
0x18003e4cb  lea     rcx, [rbp+0B0h+var_D0]; this
0x18003e4cf  cmp     [rbp+0B0h+var_C8], esi
0x18003e4d2  jge     short loc_18003E4DA
0x18003e4d4  call    ?ReThrow@CVssFunctionTracer@@QEAAXXZ; CVssFunctionTracer::ReThrow(void)
0x18003e4da  mov     dl, bl; bool
0x18003e4dc  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x18003e4e1  mov     bl, al
0x18003e4e3  lea     rcx, [rbp+0B0h+var_60]
0x18003e4e7  call    ??1?$deque@PEAU_HRESOURCE@@V?$allocator@PEAU_HRESOURCE@@@std@@@std@@QEAA@XZ; std::deque<_HRESOURCE *>::~deque<_HRESOURCE *>(void)
0x18003e4ec  nop
0x18003e4ed  lea     rcx, [rbp+0B0h+var_D0]; this
0x18003e4f1  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003e4f6  mov     al, bl
0x18003e4f8  mov     rbx, [rsp+1B0h+arg_0]
0x18003e500  add     rsp, 180h
0x18003e507  pop     r15
0x18003e509  pop     r14
0x18003e50b  pop     r13
0x18003e50d  pop     r12
0x18003e50f  pop     rdi
0x18003e510  pop     rsi
0x18003e511  pop     rbp
0x18003e512  retn
0x18003e513  mov     [rsp+1B0h+var_180], r12
0x18003e518  mov     [rsp+1B0h+var_178], r13
0x18003e51d  mov     [rsp+1B0h+var_170], rbx
0x18003e522  mov     [rsp+1B0h+var_168], 0C4h
0x18003e52a  mov     [rsp+1B0h+var_164], 0Bh
0x18003e532  mov     [rsp+1B0h+var_160], 0FFh
0x18003e53a  mov     [rbp+0B0h+var_E0], 1000000h
0x18003e541  xor     edx, edx; Val
0x18003e543  lea     r8d, [rdx+78h]; Size
0x18003e547  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003e54c  call    memset_0
0x18003e551  lea     r9, aNullParameters; "NULL parameters"
0x18003e558  mov     r8d, 80070057h
0x18003e55e  lea     rdx, [rsp+1B0h+var_180]
0x18003e563  lea     rcx, [rbp+0B0h+var_D0]
0x18003e567  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
