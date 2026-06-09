# CVssClusterAPI::RemoveDependency(ushort const *,ushort const *)

- ea: `0x18003ff6c`
- end: `0x1800402de`
- name: `?RemoveDependency@CVssClusterAPI@@QEAA_NPEBG0@Z`
- size: `882`
- prototype: `bool __fastcall(CVssClusterAPI *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180027ca0`
- `0x180028aa0`

## callees

- `0x18000212c`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`
- `0x18003df54`
- `0x18003dfac`
- `0x18003e574`
- `0x18003e874`
- `0x18003ec7c`
- `0x18003ef54`
- `0x18003f52c`
- `0x18003ff6c`
- `0x1800402e4`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18004023d`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18004024b`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18004023d`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x18004024b`
- `ext-ms-win-cluster-clusapi-l1-1-2!RemoveClusterResourceDependency` at `0x180040143`
- `ext-ms-win-cluster-clusapi-l1-1-2!RemoveClusterResourceDependency` at `0x180040143`

## string_xrefs

- `0x18003ff9a`: `CVssClusterAPI::RemoveDependency`
- `0x1800400ac`: `CVssClusterAPI::RemoveDependency`
- `0x18004015c`: `CVssClusterAPI::RemoveDependency`
- `0x1800400f3`: `Volumes belong to the same resource. No dependency is removed`
- `0x1800401b0`: `Unable to remove dependency between %s and %s: [0x%08lx]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CVssClusterAPI::RemoveDependency(
        HCLUSTER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 **v6; // r8
  struct _HRESOURCE *PhysicalDiskResourceForVolumeName; // rbx
  unsigned __int16 **v8; // r8
  struct _HRESOURCE *v9; // rax
  CVssClusterAPI *v10; // rcx
  struct _HRESOURCE *v11; // rdi
  char v12; // r14
  DWORD v13; // r12d
  char v14; // bl
  const unsigned __int16 *v16; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v17; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v18; // [rsp+40h] [rbp-C0h]
  int v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+4Ch] [rbp-B4h]
  int v21; // [rsp+50h] [rbp-B0h]
  _BYTE v22[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+D0h] [rbp-30h]
  _BYTE v24[40]; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID v25[22]; // [rsp+100h] [rbp+0h] BYREF

  v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v17 = L"CVssClusterAPI::RemoveDependency";
  v18 = L"CLUCLUSC";
  v19 = 302;
  v20 = 11;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v25, (__int64)&v16, 0);
  CVssClusterResourceList::CVssClusterResourceList((CVssClusterResourceList *)v24);
  v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v17 = L"CVssClusterAPI::RemoveDependency";
  v18 = L"CLUCLUSC";
  v19 = 309;
  v20 = 11;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CVssFunctionTracer::Trace(v25, &v16, L"Parameters: From = %s, To = %s", a2, a3);
  if ( !a2 || !a3 )
  {
    v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v17 = L"CVssClusterAPI::RemoveDependency";
    v18 = L"CLUCLUSC";
    v19 = 312;
    v20 = 11;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CVssFunctionTracer::Throw(v25, &v16, 2147942487LL, L"NULL parameters");
  }
  PhysicalDiskResourceForVolumeName = CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(this, a2, v6);
  v9 = CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(this, a3, v8);
  v11 = v9;
  if ( PhysicalDiskResourceForVolumeName && v9 )
  {
    v12 = 0;
    if ( CVssClusterAPI::AreResourcesEqual(v10, PhysicalDiskResourceForVolumeName, v9) )
    {
      v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
      v17 = L"CVssClusterAPI::RemoveDependency";
      v18 = L"CLUCLUSC";
      v19 = 326;
      v20 = 11;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::Trace(v25, &v16, L"Volumes belong to the same resource. No dependency is removed");
    }
    else if ( CVssClusterAPI::IsDependencyAlreadyEstablished(this, PhysicalDiskResourceForVolumeName, v11) )
    {
      CVssClusterAPI::GetFinalOnlineResourceList(
        this,
        PhysicalDiskResourceForVolumeName,
        (struct CVssClusterResourceList *)v24);
      CVssClusterAPI::TakeResourceOffline((CVssClusterAPI *)this, PhysicalDiskResourceForVolumeName);
      v13 = RemoveClusterResourceDependency(PhysicalDiskResourceForVolumeName, v11);
      if ( v13 )
      {
        v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
        v17 = L"CVssClusterAPI::RemoveDependency";
        v18 = L"CLUCLUSC";
        v19 = 346;
        v20 = 11;
        v21 = 255;
        v23 = 0x1000000;
        memset_0(v22, 0, sizeof(v22));
        CVssFunctionTracer::Trace(v25, &v16, L"Unable to remove dependency between %s and %s: [0x%08lx]", a2, a3, v13);
      }
      else
      {
        CVssClusterAPI::BringResourceListOnline((CVssClusterAPI *)this, (struct CVssClusterResourceList *)v24);
        v12 = 1;
      }
    }
  }
  else
  {
    v16 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
    v17 = L"CVssClusterAPI::RemoveDependency";
    v18 = L"CLUCLUSC";
    v19 = 321;
    v20 = 11;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CVssFunctionTracer::Trace(v25, &v16, L"One of the volumes does not belong to a physical disk resource.");
    v12 = 0;
    if ( !PhysicalDiskResourceForVolumeName )
      goto LABEL_13;
  }
  CloseClusterResource(PhysicalDiskResourceForVolumeName);
LABEL_13:
  if ( v11 )
    CloseClusterResource(v11);
  v14 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v25, v12);
  std::deque<_HRESOURCE *>::~deque<_HRESOURCE *>(v24);
  CVssFunctionTracer::~CVssFunctionTracer(v25);
  return v14;
}

```

## disassembly

```asm
0x18003ff6c  push    rbp
0x18003ff6e  push    rbx
0x18003ff6f  push    rsi
0x18003ff70  push    rdi
0x18003ff71  push    r12
0x18003ff73  push    r13
0x18003ff75  push    r14
0x18003ff77  push    r15
0x18003ff79  lea     rbp, [rsp-78h]
0x18003ff7e  sub     rsp, 178h
0x18003ff85  mov     r15, r8
0x18003ff88  mov     r13, rdx
0x18003ff8b  mov     rsi, rcx
0x18003ff8e  lea     r12, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003ff95  mov     [rsp+1B0h+var_180], r12
0x18003ff9a  lea     r14, aCvssclusterapi_9; "CVssClusterAPI::RemoveDependency"
0x18003ffa1  mov     [rsp+1B0h+var_178], r14
0x18003ffa6  lea     rbx, aCluclusc; "CLUCLUSC"
0x18003ffad  mov     [rsp+1B0h+var_170], rbx
0x18003ffb2  mov     [rsp+1B0h+var_168], 12Eh
0x18003ffba  mov     edi, 0Bh
0x18003ffbf  mov     [rsp+1B0h+var_164], edi
0x18003ffc3  mov     [rsp+1B0h+var_160], 0FFh
0x18003ffcb  mov     [rbp+0B0h+var_E0], 1000000h
0x18003ffd2  xor     edx, edx; Val
0x18003ffd4  lea     r8d, [rdi+6Dh]; Size
0x18003ffd8  lea     rcx, [rsp+1B0h+var_158]; void *
0x18003ffdd  call    memset_0
0x18003ffe2  xor     r8d, r8d
0x18003ffe5  lea     rdx, [rsp+1B0h+var_180]
0x18003ffea  lea     rcx, [rbp+0B0h+var_B0]
0x18003ffee  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003fff3  nop
0x18003fff4  lea     rcx, [rbp+0B0h+var_D8]; this
0x18003fff8  call    ??0CVssClusterResourceList@@QEAA@XZ; CVssClusterResourceList::CVssClusterResourceList(void)
0x18003fffd  nop
0x18003fffe  mov     [rsp+1B0h+var_180], r12
0x180040003  mov     [rsp+1B0h+var_178], r14
0x180040008  mov     [rsp+1B0h+var_170], rbx
0x18004000d  mov     [rsp+1B0h+var_168], 135h
0x180040015  mov     [rsp+1B0h+var_164], edi
0x180040019  mov     [rsp+1B0h+var_160], 0FFh
0x180040021  mov     [rbp+0B0h+var_E0], 1000000h
0x180040028  xor     edx, edx; Val
0x18004002a  lea     r8d, [rdi+6Dh]; Size
0x18004002e  lea     rcx, [rsp+1B0h+var_158]; void *
0x180040033  call    memset_0
0x180040038  mov     [rsp+1B0h+var_190], r15
0x18004003d  mov     r9, r13
0x180040040  lea     r8, aParametersFrom; "Parameters: From = %s, To = %s"
0x180040047  lea     rdx, [rsp+1B0h+var_180]
0x18004004c  lea     rcx, [rbp+0B0h+var_B0]
0x180040050  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180040055  test    r13, r13
0x180040058  jz      loc_180040288
0x18004005e  test    r15, r15
0x180040061  jz      loc_180040288
0x180040067  mov     rdx, r13; unsigned __int16 *
0x18004006a  mov     rcx, rsi; this
0x18004006d  call    ?GetPhysicalDiskResourceForVolumeName@CVssClusterAPI@@QEAAPEAU_HRESOURCE@@PEBGPEAPEAG@Z; CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(ushort const *,ushort * *)
0x180040072  mov     rbx, rax
0x180040075  mov     rdx, r15; unsigned __int16 *
0x180040078  mov     rcx, rsi; this
0x18004007b  call    ?GetPhysicalDiskResourceForVolumeName@CVssClusterAPI@@QEAAPEAU_HRESOURCE@@PEBGPEAPEAG@Z; CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(ushort const *,ushort * *)
0x180040080  mov     rdi, rax
0x180040083  test    rbx, rbx
0x180040086  jz      loc_1800401D8
0x18004008c  test    rax, rax
0x18004008f  jz      loc_1800401D8
0x180040095  xor     r14b, r14b
0x180040098  mov     r8, rax; struct _HRESOURCE *
0x18004009b  mov     rdx, rbx; struct _HRESOURCE *
0x18004009e  call    ?AreResourcesEqual@CVssClusterAPI@@QEAA_NPEAU_HRESOURCE@@0@Z; CVssClusterAPI::AreResourcesEqual(_HRESOURCE *,_HRESOURCE *)
0x1800400a3  test    al, al
0x1800400a5  jz      short loc_18004010D
0x1800400a7  mov     [rsp+1B0h+var_180], r12
0x1800400ac  lea     rax, aCvssclusterapi_9; "CVssClusterAPI::RemoveDependency"
0x1800400b3  mov     [rsp+1B0h+var_178], rax
0x1800400b8  lea     rax, aCluclusc; "CLUCLUSC"
0x1800400bf  mov     [rsp+1B0h+var_170], rax
0x1800400c4  mov     [rsp+1B0h+var_168], 146h
0x1800400cc  mov     [rsp+1B0h+var_164], 0Bh
0x1800400d4  mov     [rsp+1B0h+var_160], 0FFh
0x1800400dc  mov     [rbp+0B0h+var_E0], 1000000h
0x1800400e3  xor     edx, edx; Val
0x1800400e5  lea     r8d, [rdx+78h]; Size
0x1800400e9  lea     rcx, [rsp+1B0h+var_158]; void *
0x1800400ee  call    memset_0
0x1800400f3  lea     r8, aVolumesBelongT; "Volumes belong to the same resource. No"...
0x1800400fa  lea     rdx, [rsp+1B0h+var_180]
0x1800400ff  lea     rcx, [rbp+0B0h+var_B0]
0x180040103  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180040108  jmp     loc_18004023A
0x18004010d  mov     r8, rdi; struct _HRESOURCE *
0x180040110  mov     rdx, rbx; struct _HRESOURCE *
0x180040113  mov     rcx, rsi; this
0x180040116  call    ?IsDependencyAlreadyEstablished@CVssClusterAPI@@QEAA_NPEAU_HRESOURCE@@0@Z; CVssClusterAPI::IsDependencyAlreadyEstablished(_HRESOURCE *,_HRESOURCE *)
0x18004011b  test    al, al
0x18004011d  jz      loc_18004023A
0x180040123  lea     r8, [rbp+0B0h+var_D8]; struct CVssClusterResourceList *
0x180040127  mov     rdx, rbx; struct _HRESOURCE *
0x18004012a  mov     rcx, rsi; this
0x18004012d  call    ?GetFinalOnlineResourceList@CVssClusterAPI@@AEAAXPEAU_HRESOURCE@@AEAVCVssClusterResourceList@@@Z; CVssClusterAPI::GetFinalOnlineResourceList(_HRESOURCE *,CVssClusterResourceList &)
0x180040132  mov     rdx, rbx; struct _HRESOURCE *
0x180040135  mov     rcx, rsi; this
0x180040138  call    ?TakeResourceOffline@CVssClusterAPI@@AEAAXPEAU_HRESOURCE@@@Z; CVssClusterAPI::TakeResourceOffline(_HRESOURCE *)
0x18004013d  mov     rdx, rdi; hDependsOn
0x180040140  mov     rcx, rbx; hResource
0x180040143  call    cs:__imp_RemoveClusterResourceDependency
0x180040149  mov     r12d, eax
0x18004014c  test    eax, eax
0x18004014e  jz      short loc_1800401C7
0x180040150  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x180040157  mov     [rsp+1B0h+var_180], rax
0x18004015c  lea     rax, aCvssclusterapi_9; "CVssClusterAPI::RemoveDependency"
0x180040163  mov     [rsp+1B0h+var_178], rax
0x180040168  lea     rax, aCluclusc; "CLUCLUSC"
0x18004016f  mov     [rsp+1B0h+var_170], rax
0x180040174  mov     [rsp+1B0h+var_168], 15Ah
0x18004017c  mov     [rsp+1B0h+var_164], 0Bh
0x180040184  mov     [rsp+1B0h+var_160], 0FFh
0x18004018c  mov     [rbp+0B0h+var_E0], 1000000h
0x180040193  xor     edx, edx; Val
0x180040195  lea     r8d, [rdx+78h]; Size
0x180040199  lea     rcx, [rsp+1B0h+var_158]; void *
0x18004019e  call    memset_0
0x1800401a3  mov     [rsp+1B0h+var_188], r12d
0x1800401a8  mov     [rsp+1B0h+var_190], r15
0x1800401ad  mov     r9, r13
0x1800401b0  lea     r8, aUnableToRemove; "Unable to remove dependency between %s "...
0x1800401b7  lea     rdx, [rsp+1B0h+var_180]
0x1800401bc  lea     rcx, [rbp+0B0h+var_B0]
0x1800401c0  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800401c5  jmp     short loc_18004023A
0x1800401c7  lea     rdx, [rbp+0B0h+var_D8]; struct CVssClusterResourceList *
0x1800401cb  mov     rcx, rsi; this
0x1800401ce  call    ?BringResourceListOnline@CVssClusterAPI@@AEAAXAEAVCVssClusterResourceList@@@Z; CVssClusterAPI::BringResourceListOnline(CVssClusterResourceList &)
0x1800401d3  mov     r14b, 1
0x1800401d6  jmp     short loc_18004023A
0x1800401d8  mov     [rsp+1B0h+var_180], r12
0x1800401dd  mov     [rsp+1B0h+var_178], r14
0x1800401e2  lea     rax, aCluclusc; "CLUCLUSC"
0x1800401e9  mov     [rsp+1B0h+var_170], rax
0x1800401ee  mov     [rsp+1B0h+var_168], 141h
0x1800401f6  mov     [rsp+1B0h+var_164], 0Bh
0x1800401fe  mov     [rsp+1B0h+var_160], 0FFh
0x180040206  mov     [rbp+0B0h+var_E0], 1000000h
0x18004020d  xor     edx, edx; Val
0x18004020f  lea     r8d, [rdx+78h]; Size
0x180040213  lea     rcx, [rsp+1B0h+var_158]; void *
0x180040218  call    memset_0
0x18004021d  lea     r8, aOneOfTheVolume; "One of the volumes does not belong to a"...
0x180040224  lea     rdx, [rsp+1B0h+var_180]
0x180040229  lea     rcx, [rbp+0B0h+var_B0]
0x18004022d  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180040232  xor     r14b, r14b
0x180040235  test    rbx, rbx
0x180040238  jz      short loc_180040243
0x18004023a  mov     rcx, rbx; hResource
0x18004023d  call    cs:__imp_CloseClusterResource
0x180040243  test    rdi, rdi
0x180040246  jz      short loc_180040251
0x180040248  mov     rcx, rdi; hResource
0x18004024b  call    cs:__imp_CloseClusterResource
0x180040251  mov     dl, r14b; bool
0x180040254  lea     rcx, [rbp+0B0h+var_B0]; this
0x180040258  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x18004025d  mov     bl, al
0x18004025f  lea     rcx, [rbp+0B0h+var_D8]
0x180040263  call    ??1?$deque@PEAU_HRESOURCE@@V?$allocator@PEAU_HRESOURCE@@@std@@@std@@QEAA@XZ; std::deque<_HRESOURCE *>::~deque<_HRESOURCE *>(void)
0x180040268  nop
0x180040269  lea     rcx, [rbp+0B0h+var_B0]; this
0x18004026d  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180040272  mov     al, bl
0x180040274  add     rsp, 178h
0x18004027b  pop     r15
0x18004027d  pop     r14
0x18004027f  pop     r13
0x180040281  pop     r12
0x180040283  pop     rdi
0x180040284  pop     rsi
0x180040285  pop     rbx
0x180040286  pop     rbp
0x180040287  retn
0x180040288  mov     [rsp+1B0h+var_180], r12
0x18004028d  mov     [rsp+1B0h+var_178], r14
0x180040292  mov     [rsp+1B0h+var_170], rbx
0x180040297  mov     [rsp+1B0h+var_168], 138h
0x18004029f  mov     [rsp+1B0h+var_164], edi
0x1800402a3  mov     [rsp+1B0h+var_160], 0FFh
0x1800402ab  mov     [rbp+0B0h+var_E0], 1000000h
0x1800402b2  xor     edx, edx; Val
0x1800402b4  lea     r8d, [rdx+78h]; Size
0x1800402b8  lea     rcx, [rsp+1B0h+var_158]; void *
0x1800402bd  call    memset_0
0x1800402c2  lea     r9, aNullParameters; "NULL parameters"
0x1800402c9  mov     r8d, 80070057h
0x1800402cf  lea     rdx, [rsp+1B0h+var_180]
0x1800402d4  lea     rcx, [rbp+0B0h+var_B0]
0x1800402d8  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
