# CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)

- ea: `0x180019f78`
- end: `0x18001a007`
- name: `??1?$CDispatchImplT@UIOnlineActivation@@$1?IID_IOnlineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a6c0`
- `0x18001a8b0`

## callees

- `0x180003838`
- `0x180004520`
- `0x1800049e8`
- `0x180019f78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019fd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019fd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019fe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019fe7`

## pseudocode

```c
int __fastcall CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(
        __int64 a1)
{
  bool v1; // zf
  int result; // eax
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *(_DWORD *)(a1 + 128) == 0;
  *(_QWORD *)a1 = &CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable';
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
0x180019f78  mov     [rsp+arg_0], rbx
0x180019f7d  push    rdi
0x180019f7e  sub     rsp, 20h
0x180019f82  cmp     dword ptr [rcx+80h], 0
0x180019f89  lea     rax, ??_7?$CDispatchImplT@UIOnlineActivation@@$1?IID_IOnlineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@6B@; const CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable'
0x180019f90  mov     [rcx], rax
0x180019f93  mov     rbx, rcx
0x180019f96  jz      short loc_180019FAB
0x180019f98  add     rcx, 18h
0x180019f9c  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x180019fa1  mov     dword ptr [rbx+80h], 0
0x180019fab  xor     edx, edx
0x180019fad  lea     rcx, [rbx+8]
0x180019fb1  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180019fb6  lea     rcx, [rbx+18h]
0x180019fba  call    ??1?$CRWLock2T@VCEmptyType@@@@QEAA@XZ; CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(void)
0x180019fbf  xor     edx, edx
0x180019fc1  lea     rcx, [rbx+8]
0x180019fc5  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180019fca  mov     rdi, [rbx+10h]
0x180019fce  test    rdi, rdi
0x180019fd1  jz      short loc_180019FFB
0x180019fd3  call    cs:__imp_GetProcessHeap
0x180019fda  nop     dword ptr [rax+rax+00h]
0x180019fdf  mov     r8, rdi; lpMem
0x180019fe2  xor     edx, edx; dwFlags
0x180019fe4  mov     rcx, rax; hHeap
0x180019fe7  call    cs:__imp_HeapFree
0x180019fee  nop     dword ptr [rax+rax+00h]
0x180019ff3  mov     qword ptr [rbx+10h], 0
0x180019ffb  mov     rbx, [rsp+28h+arg_0]
0x18001a000  add     rsp, 20h
0x18001a004  pop     rdi
0x18001a005  retn
```
