# CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)

- ea: `0x18001a010`
- end: `0x18001a09f`
- name: `??1?$CDispatchImplT@UITokenActivation@@$1?IID_ITokenActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a404`
- `0x18001a710`

## callees

- `0x180003838`
- `0x180004520`
- `0x1800049e8`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a06b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a06b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a07f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a07f`

## pseudocode

```c
int __fastcall CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(
        __int64 a1)
{
  bool v1; // zf
  int result; // eax
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *(_DWORD *)(a1 + 128) == 0;
  *(_QWORD *)a1 = &CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable';
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
0x18001a010  mov     [rsp+arg_0], rbx
0x18001a015  push    rdi
0x18001a016  sub     rsp, 20h
0x18001a01a  cmp     dword ptr [rcx+80h], 0
0x18001a021  lea     rax, ??_7?$CDispatchImplT@UITokenActivation@@$1?IID_ITokenActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@6B@; const CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable'
0x18001a028  mov     [rcx], rax
0x18001a02b  mov     rbx, rcx
0x18001a02e  jz      short loc_18001A043
0x18001a030  add     rcx, 18h
0x18001a034  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x18001a039  mov     dword ptr [rbx+80h], 0
0x18001a043  xor     edx, edx
0x18001a045  lea     rcx, [rbx+8]
0x18001a049  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001a04e  lea     rcx, [rbx+18h]
0x18001a052  call    ??1?$CRWLock2T@VCEmptyType@@@@QEAA@XZ; CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(void)
0x18001a057  xor     edx, edx
0x18001a059  lea     rcx, [rbx+8]
0x18001a05d  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001a062  mov     rdi, [rbx+10h]
0x18001a066  test    rdi, rdi
0x18001a069  jz      short loc_18001A093
0x18001a06b  call    cs:__imp_GetProcessHeap
0x18001a072  nop     dword ptr [rax+rax+00h]
0x18001a077  mov     r8, rdi; lpMem
0x18001a07a  xor     edx, edx; dwFlags
0x18001a07c  mov     rcx, rax; hHeap
0x18001a07f  call    cs:__imp_HeapFree
0x18001a086  nop     dword ptr [rax+rax+00h]
0x18001a08b  mov     qword ptr [rbx+10h], 0
0x18001a093  mov     rbx, [rsp+28h+arg_0]
0x18001a098  add     rsp, 20h
0x18001a09c  pop     rdi
0x18001a09d  retn
```
