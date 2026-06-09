# CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)

- ea: `0x18001e3c8`
- end: `0x18001e457`
- name: `??1?$CDispatchImplT@UIOfflineActivationPhoneData@@$1?IID_IOfflineActivationPhoneData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e4f8`
- `0x18001e610`

## callees

- `0x180003838`
- `0x180004520`
- `0x1800049e8`
- `0x18001e3c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e423`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e423`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e437`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e437`

## pseudocode

```c
int __fastcall CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>(
        __int64 a1)
{
  bool v1; // zf
  int result; // eax
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *(_DWORD *)(a1 + 128) == 0;
  *(_QWORD *)a1 = &CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable';
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
0x18001e3c8  mov     [rsp+arg_0], rbx
0x18001e3cd  push    rdi
0x18001e3ce  sub     rsp, 20h
0x18001e3d2  cmp     dword ptr [rcx+80h], 0
0x18001e3d9  lea     rax, ??_7?$CDispatchImplT@UIOfflineActivationPhoneData@@$1?IID_IOfflineActivationPhoneData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@6B@; const CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vftable'
0x18001e3e0  mov     [rcx], rax
0x18001e3e3  mov     rbx, rcx
0x18001e3e6  jz      short loc_18001E3FB
0x18001e3e8  add     rcx, 18h
0x18001e3ec  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x18001e3f1  mov     dword ptr [rbx+80h], 0
0x18001e3fb  xor     edx, edx
0x18001e3fd  lea     rcx, [rbx+8]
0x18001e401  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001e406  lea     rcx, [rbx+18h]
0x18001e40a  call    ??1?$CRWLock2T@VCEmptyType@@@@QEAA@XZ; CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(void)
0x18001e40f  xor     edx, edx
0x18001e411  lea     rcx, [rbx+8]
0x18001e415  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001e41a  mov     rdi, [rbx+10h]
0x18001e41e  test    rdi, rdi
0x18001e421  jz      short loc_18001E44B
0x18001e423  call    cs:__imp_GetProcessHeap
0x18001e42a  nop     dword ptr [rax+rax+00h]
0x18001e42f  mov     r8, rdi; lpMem
0x18001e432  xor     edx, edx; dwFlags
0x18001e434  mov     rcx, rax; hHeap
0x18001e437  call    cs:__imp_HeapFree
0x18001e43e  nop     dword ptr [rax+rax+00h]
0x18001e443  mov     qword ptr [rbx+10h], 0
0x18001e44b  mov     rbx, [rsp+28h+arg_0]
0x18001e450  add     rsp, 20h
0x18001e454  pop     rdi
0x18001e455  retn
```
