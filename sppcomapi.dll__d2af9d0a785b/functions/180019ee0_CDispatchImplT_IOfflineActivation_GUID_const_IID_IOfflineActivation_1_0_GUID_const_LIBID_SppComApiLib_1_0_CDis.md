# CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)

- ea: `0x180019ee0`
- end: `0x180019f6f`
- name: `??1?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a1fc`
- `0x18001a670`

## callees

- `0x180003838`
- `0x180004520`
- `0x1800049e8`
- `0x180019ee0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019f3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019f3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019f4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019f4f`

## pseudocode

```c
int __fastcall CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(
        __int64 a1)
{
  bool v1; // zf
  int result; // eax
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *(_DWORD *)(a1 + 128) == 0;
  *(_QWORD *)a1 = &CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable';
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
0x180019ee0  mov     [rsp+arg_0], rbx
0x180019ee5  push    rdi
0x180019ee6  sub     rsp, 20h
0x180019eea  cmp     dword ptr [rcx+80h], 0
0x180019ef1  lea     rax, ??_7?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@6B@; const CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable'
0x180019ef8  mov     [rcx], rax
0x180019efb  mov     rbx, rcx
0x180019efe  jz      short loc_180019F13
0x180019f00  add     rcx, 18h
0x180019f04  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x180019f09  mov     dword ptr [rbx+80h], 0
0x180019f13  xor     edx, edx
0x180019f15  lea     rcx, [rbx+8]
0x180019f19  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180019f1e  lea     rcx, [rbx+18h]
0x180019f22  call    ??1?$CRWLock2T@VCEmptyType@@@@QEAA@XZ; CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(void)
0x180019f27  xor     edx, edx
0x180019f29  lea     rcx, [rbx+8]
0x180019f2d  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180019f32  mov     rdi, [rbx+10h]
0x180019f36  test    rdi, rdi
0x180019f39  jz      short loc_180019F63
0x180019f3b  call    cs:__imp_GetProcessHeap
0x180019f42  nop     dword ptr [rax+rax+00h]
0x180019f47  mov     r8, rdi; lpMem
0x180019f4a  xor     edx, edx; dwFlags
0x180019f4c  mov     rcx, rax; hHeap
0x180019f4f  call    cs:__imp_HeapFree
0x180019f56  nop     dword ptr [rax+rax+00h]
0x180019f5b  mov     qword ptr [rbx+10h], 0
0x180019f63  mov     rbx, [rsp+28h+arg_0]
0x180019f68  add     rsp, 20h
0x180019f6c  pop     rdi
0x180019f6d  retn
```
