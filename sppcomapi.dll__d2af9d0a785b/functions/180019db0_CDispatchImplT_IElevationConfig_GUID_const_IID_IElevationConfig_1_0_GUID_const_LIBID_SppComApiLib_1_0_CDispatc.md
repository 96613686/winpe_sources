# CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)

- ea: `0x180019db0`
- end: `0x180019e3f`
- name: `??1?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a5d0`
- `0x18001a760`

## callees

- `0x180003838`
- `0x180004520`
- `0x1800049e8`
- `0x180019db0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e1f`

## pseudocode

```c
int __fastcall CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>(
        __int64 a1)
{
  bool v1; // zf
  int result; // eax
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *(_DWORD *)(a1 + 128) == 0;
  *(_QWORD *)a1 = &CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable';
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
0x180019db0  mov     [rsp+arg_0], rbx
0x180019db5  push    rdi
0x180019db6  sub     rsp, 20h
0x180019dba  cmp     dword ptr [rcx+80h], 0
0x180019dc1  lea     rax, ??_7?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@6B@; const CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable'
0x180019dc8  mov     [rcx], rax
0x180019dcb  mov     rbx, rcx
0x180019dce  jz      short loc_180019DE3
0x180019dd0  add     rcx, 18h
0x180019dd4  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x180019dd9  mov     dword ptr [rbx+80h], 0
0x180019de3  xor     edx, edx
0x180019de5  lea     rcx, [rbx+8]
0x180019de9  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180019dee  lea     rcx, [rbx+18h]
0x180019df2  call    ??1?$CRWLock2T@VCEmptyType@@@@QEAA@XZ; CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(void)
0x180019df7  xor     edx, edx
0x180019df9  lea     rcx, [rbx+8]
0x180019dfd  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180019e02  mov     rdi, [rbx+10h]
0x180019e06  test    rdi, rdi
0x180019e09  jz      short loc_180019E33
0x180019e0b  call    cs:__imp_GetProcessHeap
0x180019e12  nop     dword ptr [rax+rax+00h]
0x180019e17  mov     r8, rdi; lpMem
0x180019e1a  xor     edx, edx; dwFlags
0x180019e1c  mov     rcx, rax; hHeap
0x180019e1f  call    cs:__imp_HeapFree
0x180019e26  nop     dword ptr [rax+rax+00h]
0x180019e2b  mov     qword ptr [rbx+10h], 0
0x180019e33  mov     rbx, [rsp+28h+arg_0]
0x180019e38  add     rsp, 20h
0x180019e3c  pop     rdi
0x180019e3d  retn
```
