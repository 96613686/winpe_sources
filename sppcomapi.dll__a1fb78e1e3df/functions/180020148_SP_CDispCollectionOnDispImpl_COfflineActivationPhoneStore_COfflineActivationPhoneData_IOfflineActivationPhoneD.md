# SP<CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::DataStore,SP_COM<CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::DataStore>>::Reset(void)

- ea: `0x180020148`
- end: `0x1800201d5`
- name: `?Reset@?$SP@VDataStore@?$CDispCollectionOnDispImpl@VCOfflineActivationPhoneStore@@VCOfflineActivationPhoneData@@UIOfflineActivationPhoneData@@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U6@B@@V?$SP_COM@VDataStore@?$CDispCollectionOnDispImpl@VCOfflineActivationPhoneStore@@VCOfflineActivationPhoneData@@UIOfflineActivationPhoneData@@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U6@B@@@@@@QEAAXXZ`
- size: `141`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e700`
- `0x180020e90`

## callees

- `0x180020148`
- `0x1800204b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002017c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800201a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002017c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800201a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020190`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800201b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020190`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800201b8`

## pseudocode

```c
void __fastcall SP<CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::DataStore,SP_COM<CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::DataStore>>::Reset(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v3; // rbp
  HANDLE ProcessHeap; // rax
  HANDLE v5; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
    {
      CArray<DP_CPP<COfflineActivationPhoneStore>,DP_CPP<COfflineActivationPhoneStore>,CAdaptorDefault,CPoliciesDefault>::SetSize(
        v1 + 1,
        0);
      v3 = (void *)v1[2];
      if ( v3 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v3);
        v1[2] = 0;
      }
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v1);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180020148  push    rbx
0x18002014a  push    rbp
0x18002014b  push    rsi
0x18002014c  push    rdi
0x18002014d  sub     rsp, 28h
0x180020151  mov     rbx, [rcx]
0x180020154  mov     rdi, rcx
0x180020157  test    rbx, rbx
0x18002015a  jz      short loc_1800201CB
0x18002015c  or      eax, 0FFFFFFFFh
0x18002015f  lock xadd [rbx], eax
0x180020163  cmp     eax, 1
0x180020166  jnz     short loc_1800201C4
0x180020168  xor     edx, edx
0x18002016a  lea     rcx, [rbx+8]
0x18002016e  call    ?SetSize@?$CArray@V?$DP_CPP@VCOfflineActivationPhoneStore@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_CPP<COfflineActivationPhoneStore>,DP_CPP<COfflineActivationPhoneStore>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180020173  mov     rbp, [rbx+10h]
0x180020177  test    rbp, rbp
0x18002017a  jz      short loc_1800201A4
0x18002017c  call    cs:__imp_GetProcessHeap
0x180020183  nop     dword ptr [rax+rax+00h]
0x180020188  mov     r8, rbp; lpMem
0x18002018b  xor     edx, edx; dwFlags
0x18002018d  mov     rcx, rax; hHeap
0x180020190  call    cs:__imp_HeapFree
0x180020197  nop     dword ptr [rax+rax+00h]
0x18002019c  mov     qword ptr [rbx+10h], 0
0x1800201a4  call    cs:__imp_GetProcessHeap
0x1800201ab  nop     dword ptr [rax+rax+00h]
0x1800201b0  mov     r8, rbx; lpMem
0x1800201b3  xor     edx, edx; dwFlags
0x1800201b5  mov     rcx, rax; hHeap
0x1800201b8  call    cs:__imp_HeapFree
0x1800201bf  nop     dword ptr [rax+rax+00h]
0x1800201c4  mov     qword ptr [rdi], 0
0x1800201cb  add     rsp, 28h
0x1800201cf  pop     rdi
0x1800201d0  pop     rsi
0x1800201d1  pop     rbp
0x1800201d2  pop     rbx
0x1800201d3  retn
```
