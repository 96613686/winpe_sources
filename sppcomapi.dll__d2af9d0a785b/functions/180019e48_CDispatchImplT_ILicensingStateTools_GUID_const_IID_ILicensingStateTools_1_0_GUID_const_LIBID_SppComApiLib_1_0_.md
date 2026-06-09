# CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)

- ea: `0x180019e48`
- end: `0x180019ed7`
- name: `??1?$CDispatchImplT@UILicensingStateTools@@$1?IID_ILicensingStateTools@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a620`
- `0x18001a7e0`

## callees

- `0x180003838`
- `0x180004520`
- `0x1800049e8`
- `0x180019e48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ea3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019eb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019eb7`

## pseudocode

```c
int __fastcall CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>(
        __int64 a1)
{
  bool v1; // zf
  int result; // eax
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *(_DWORD *)(a1 + 128) == 0;
  *(_QWORD *)a1 = &CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable';
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
0x180019e48  mov     [rsp+arg_0], rbx
0x180019e4d  push    rdi
0x180019e4e  sub     rsp, 20h
0x180019e52  cmp     dword ptr [rcx+80h], 0
0x180019e59  lea     rax, ??_7?$CDispatchImplT@UILicensingStateTools@@$1?IID_ILicensingStateTools@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@6B@; const CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable'
0x180019e60  mov     [rcx], rax
0x180019e63  mov     rbx, rcx
0x180019e66  jz      short loc_180019E7B
0x180019e68  add     rcx, 18h
0x180019e6c  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x180019e71  mov     dword ptr [rbx+80h], 0
0x180019e7b  xor     edx, edx
0x180019e7d  lea     rcx, [rbx+8]
0x180019e81  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180019e86  lea     rcx, [rbx+18h]
0x180019e8a  call    ??1?$CRWLock2T@VCEmptyType@@@@QEAA@XZ; CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(void)
0x180019e8f  xor     edx, edx
0x180019e91  lea     rcx, [rbx+8]
0x180019e95  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180019e9a  mov     rdi, [rbx+10h]
0x180019e9e  test    rdi, rdi
0x180019ea1  jz      short loc_180019ECB
0x180019ea3  call    cs:__imp_GetProcessHeap
0x180019eaa  nop     dword ptr [rax+rax+00h]
0x180019eaf  mov     r8, rdi; lpMem
0x180019eb2  xor     edx, edx; dwFlags
0x180019eb4  mov     rcx, rax; hHeap
0x180019eb7  call    cs:__imp_HeapFree
0x180019ebe  nop     dword ptr [rax+rax+00h]
0x180019ec3  mov     qword ptr [rbx+10h], 0
0x180019ecb  mov     rbx, [rsp+28h+arg_0]
0x180019ed0  add     rsp, 20h
0x180019ed4  pop     rdi
0x180019ed5  retn
```
