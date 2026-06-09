# CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)

- ea: `0x180004950`
- end: `0x1800049df`
- name: `??1?$CDispatchImplT@UILicensingStatusData@@$1?IID_ILicensingStatusData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004ab0`

## callees

- `0x180003838`
- `0x180004520`
- `0x180004950`
- `0x1800049e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800049ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800049ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049bf`

## pseudocode

```c
int __fastcall CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>(
        __int64 a1)
{
  bool v1; // zf
  int result; // eax
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *(_DWORD *)(a1 + 128) == 0;
  *(_QWORD *)a1 = &CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable';
  if ( !v1 )
  {
    CRWLock2T<CEmptyType>::Done(a1 + 24);
    *(_DWORD *)(a1 + 128) = 0;
  }
  CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::SetSize(
    a1 + 8,
    0);
  CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(a1 + 24);
  result = CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::SetSize(
             a1 + 8,
             0);
  v4 = *(void **)(a1 + 16);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    result = HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(a1 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004950  mov     [rsp+arg_0], rbx
0x180004955  push    rdi
0x180004956  sub     rsp, 20h
0x18000495a  cmp     dword ptr [rcx+80h], 0
0x180004961  lea     rax, ??_7?$CDispatchImplT@UILicensingStatusData@@$1?IID_ILicensingStatusData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@6B@; const CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable'
0x180004968  mov     [rcx], rax
0x18000496b  mov     rbx, rcx
0x18000496e  jz      short loc_180004983
0x180004970  add     rcx, 18h
0x180004974  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x180004979  mov     dword ptr [rbx+80h], 0
0x180004983  xor     edx, edx
0x180004985  lea     rcx, [rbx+8]
0x180004989  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18000498e  lea     rcx, [rbx+18h]
0x180004992  call    ??1?$CRWLock2T@VCEmptyType@@@@QEAA@XZ; CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(void)
0x180004997  xor     edx, edx
0x180004999  lea     rcx, [rbx+8]
0x18000499d  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1800049a2  mov     rdi, [rbx+10h]
0x1800049a6  test    rdi, rdi
0x1800049a9  jz      short loc_1800049D3
0x1800049ab  call    cs:__imp_GetProcessHeap
0x1800049b2  nop     dword ptr [rax+rax+00h]
0x1800049b7  mov     r8, rdi; lpMem
0x1800049ba  xor     edx, edx; dwFlags
0x1800049bc  mov     rcx, rax; hHeap
0x1800049bf  call    cs:__imp_HeapFree
0x1800049c6  nop     dword ptr [rax+rax+00h]
0x1800049cb  mov     qword ptr [rbx+10h], 0
0x1800049d3  mov     rbx, [rsp+28h+arg_0]
0x1800049d8  add     rsp, 20h
0x1800049dc  pop     rdi
0x1800049dd  retn
```
