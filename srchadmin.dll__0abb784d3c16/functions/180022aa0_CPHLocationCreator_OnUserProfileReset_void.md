# CPHLocationCreator::OnUserProfileReset(void)

- ea: `0x180022aa0`
- end: `0x180022b6f`
- name: `?OnUserProfileReset@CPHLocationCreator@@UEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(CPHLocationCreator *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180021668`
- `0x18002169c`
- `0x180021cd0`
- `0x180021f84`
- `0x180022698`
- `0x180022aa0`
- `0x180022b78`
- `0x180022cc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPHLocationCreator::OnUserProfileReset(CPHLocationCreator *this, __int64 a2, __int64 a3)
{
  int UsedKeys; // ebx
  LPVOID pv[4]; // [rsp+20h] [rbp-20h] BYREF
  HDSA v6; // [rsp+58h] [rbp+18h] BYREF
  HDSA v7; // [rsp+60h] [rbp+20h] BYREF
  HDSA v8; // [rsp+68h] [rbp+28h] BYREF

  v6 = 0;
  v8 = 0;
  UsedKeys = EnumProcessedSearchRoots(&v6, &v8, a3);
  if ( UsedKeys >= 0 )
  {
    v7 = 0;
    UsedKeys = EnumSearchRoots(&v7);
    if ( UsedKeys >= 0 )
    {
      memset(pv, 0, sizeof(pv));
      UsedKeys = GetUsedKeys(&v6, &v8, pv);
      if ( UsedKeys >= 0 )
      {
        ProcessRemovedSearchRoots(&v6);
        ProcessAddedSearchRoots(&v7, pv);
      }
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
    }
    CAutoDSA<SEARCH_ROOT>::~CAutoDSA<SEARCH_ROOT>(&v7);
  }
  CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(&v8);
  CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(&v6);
  return (unsigned int)UsedKeys;
}

```

## disassembly

```asm
0x180022aa0  mov     [rsp-8+arg_0], rbx
0x180022aa5  push    rbp
0x180022aa6  mov     rbp, rsp
0x180022aa9  sub     rsp, 40h
0x180022aad  mov     [rbp+arg_8], 0
0x180022ab5  mov     [rbp+arg_18], 0
0x180022abd  lea     rdx, [rbp+arg_18]
0x180022ac1  lea     rcx, [rbp+arg_8]
0x180022ac5  call    ?EnumProcessedSearchRoots@@YAJPEAV?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@0@Z; EnumProcessedSearchRoots(CAutoDSA<PROCESSED_SEARCH_ROOT> *,CAutoDSA<PROCESSED_SEARCH_ROOT> *)
0x180022aca  mov     ebx, eax
0x180022acc  test    eax, eax
0x180022ace  js      short loc_180022B4F
0x180022ad0  mov     [rbp+arg_10], 0
0x180022ad8  lea     rcx, [rbp+arg_10]
0x180022adc  call    ?EnumSearchRoots@@YAJPEAV?$CAutoDSA@USEARCH_ROOT@@@@@Z; EnumSearchRoots(CAutoDSA<SEARCH_ROOT> *)
0x180022ae1  mov     ebx, eax
0x180022ae3  test    eax, eax
0x180022ae5  js      short loc_180022B45
0x180022ae7  mov     [rbp+pv], 0
0x180022aef  mov     [rbp+var_18], 0
0x180022af7  mov     [rbp+var_10], 0
0x180022aff  mov     [rbp+var_8], 0
0x180022b07  lea     r8, [rbp+pv]
0x180022b0b  lea     rdx, [rbp+arg_18]
0x180022b0f  lea     rcx, [rbp+arg_8]
0x180022b13  call    ?GetUsedKeys@@YAJAEBV?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@0PEAV?$CCoSimpleArray@H$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@H@@@@@Z; GetUsedKeys(CAutoDSA<PROCESSED_SEARCH_ROOT> const &,CAutoDSA<PROCESSED_SEARCH_ROOT> const &,CCoSimpleArray<int,4294967294,CSimpleArrayStandardCompareHelper<int>> *)
0x180022b18  mov     ebx, eax
0x180022b1a  test    eax, eax
0x180022b1c  js      short loc_180022B35
0x180022b1e  lea     rcx, [rbp+arg_8]
0x180022b22  call    ?ProcessRemovedSearchRoots@@YAXPEAV?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@@Z; ProcessRemovedSearchRoots(CAutoDSA<PROCESSED_SEARCH_ROOT> *)
0x180022b27  lea     rdx, [rbp+pv]
0x180022b2b  lea     rcx, [rbp+arg_10]
0x180022b2f  call    ?ProcessAddedSearchRoots@@YAXPEAV?$CAutoDSA@USEARCH_ROOT@@@@AEBV?$CCoSimpleArray@H$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@H@@@@@Z; ProcessAddedSearchRoots(CAutoDSA<SEARCH_ROOT> *,CCoSimpleArray<int,4294967294,CSimpleArrayStandardCompareHelper<int>> const &)
0x180022b34  nop
0x180022b35  mov     rcx, [rbp+pv]; pv
0x180022b39  test    rcx, rcx
0x180022b3c  jz      short loc_180022B45
0x180022b3e  call    cs:__imp_CoTaskMemFree
0x180022b44  nop
0x180022b45  lea     rcx, [rbp+arg_10]
0x180022b49  call    ??1?$CAutoDSA@USEARCH_ROOT@@@@QEAA@XZ; CAutoDSA<SEARCH_ROOT>::~CAutoDSA<SEARCH_ROOT>(void)
0x180022b4e  nop
0x180022b4f  lea     rcx, [rbp+arg_18]
0x180022b53  call    ??1?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@QEAA@XZ; CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(void)
0x180022b58  nop
0x180022b59  lea     rcx, [rbp+arg_8]
0x180022b5d  call    ??1?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@QEAA@XZ; CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(void)
0x180022b62  mov     eax, ebx
0x180022b64  mov     rbx, [rsp+40h+arg_0]
0x180022b69  add     rsp, 40h
0x180022b6d  pop     rbp
0x180022b6e  retn
```
