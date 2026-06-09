# CSsdpCacheEntryManager::HrClearDirtyInterfaceGuids(long,_GUID *)

- ea: `0x18001f54c`
- end: `0x18001f6bd`
- name: `?HrClearDirtyInterfaceGuids@CSsdpCacheEntryManager@@QEAAJJPEAU_GUID@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000f950`

## callees

- `0x18000bad0`
- `0x18000bd3c`
- `0x180019920`
- `0x18001f54c`
- `0x18001f6c4`
- `0x180024490`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f604`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f604`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f574`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f574`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrClearDirtyInterfaceGuids(
        LPCRITICAL_SECTION lpCriticalSection,
        int a2,
        struct _GUID *a3)
{
  unsigned int v3; // edi
  CSsdpCacheEntry *v7; // rbx
  void **v8; // rcx
  _QWORD v10[2]; // [rsp+20h] [rbp-10h] BYREF
  void *v11; // [rsp+60h] [rbp+30h] BYREF
  CSsdpCacheEntry *v12; // [rsp+78h] [rbp+48h] BYREF

  v3 = 0;
  v11 = 0;
  EnterCriticalSection(lpCriticalSection);
  v7 = (CSsdpCacheEntry *)&lpCriticalSection[1];
  v12 = (CSsdpCacheEntry *)&lpCriticalSection[1];
LABEL_10:
  if ( *(_QWORD *)v7 )
  {
    while ( v7 && *(_QWORD *)v7 )
    {
      if ( (unsigned int)CSsdpCacheEntry::FCheckForDirtyInterfaceGuids((CSsdpCacheEntry *)(*(_QWORD *)v7 + 8LL), a2, a3) )
      {
        --lpCriticalSection[1].LockCount;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
            (unsigned int)lpCriticalSection[1].LockCount);
        v8 = *(void ***)v7;
        if ( *(_QWORD *)v7 )
        {
          *(_QWORD *)v7 = *v8;
          *v8 = v11;
          v11 = v8;
          goto LABEL_10;
        }
        break;
      }
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext(&v12) )
        break;
      v7 = v12;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  v10[0] = &v11;
  if ( v11 )
  {
    v12 = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(v10, &v12) )
        break;
      v3 = CSsdpCacheEntry::HrShutdown((struct _RTL_CRITICAL_SECTION *)v12, 0);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(v10) );
    if ( v3 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v3);
  }
  if ( v11 )
    CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(v11);
  return v3;
}

```

## disassembly

```asm
0x18001f54c  mov     [rsp-28h+arg_8], rbx
0x18001f551  mov     [rsp-28h+arg_10], rsi
0x18001f556  push    rbp
0x18001f557  push    rdi
0x18001f558  push    r13
0x18001f55a  push    r14
0x18001f55c  push    r15
0x18001f55e  mov     rbp, rsp
0x18001f561  sub     rsp, 30h
0x18001f565  xor     edi, edi
0x18001f567  mov     r14, r8
0x18001f56a  mov     [rbp+arg_0], rdi
0x18001f56e  mov     r15d, edx
0x18001f571  mov     rsi, rcx
0x18001f574  call    cs:__imp_EnterCriticalSection
0x18001f57b  nop     dword ptr [rax+rax+00h]
0x18001f580  lea     rbx, [rsi+28h]
0x18001f584  mov     [rbp+arg_18], rbx
0x18001f588  lea     r13, WPP_GLOBAL_Control
0x18001f58f  jmp     short loc_18001F5FC
0x18001f591  test    rbx, rbx
0x18001f594  jz      short loc_18001F601
0x18001f596  mov     rcx, [rbx]
0x18001f599  test    rcx, rcx
0x18001f59c  jz      short loc_18001F601
0x18001f59e  add     rcx, 8; this
0x18001f5a2  mov     r8, r14; struct _GUID *
0x18001f5a5  mov     edx, r15d; int
0x18001f5a8  call    ?FCheckForDirtyInterfaceGuids@CSsdpCacheEntry@@QEAAHJPEAU_GUID@@@Z; CSsdpCacheEntry::FCheckForDirtyInterfaceGuids(long,_GUID *)
0x18001f5ad  test    eax, eax
0x18001f5af  jz      loc_18001F6A3
0x18001f5b5  dec     dword ptr [rsi+30h]
0x18001f5b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5bf  cmp     rcx, r13
0x18001f5c2  jz      short loc_18001F5E3
0x18001f5c4  test    byte ptr [rcx+1Ch], 8
0x18001f5c8  jz      short loc_18001F5E3
0x18001f5ca  mov     r9d, [rsi+30h]
0x18001f5ce  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001f5d5  mov     rcx, [rcx+10h]
0x18001f5d9  mov     edx, 4Dh ; 'M'
0x18001f5de  call    WPP_SF_d
0x18001f5e3  mov     rcx, [rbx]
0x18001f5e6  test    rcx, rcx
0x18001f5e9  jz      short loc_18001F601
0x18001f5eb  mov     rax, [rcx]
0x18001f5ee  mov     [rbx], rax
0x18001f5f1  mov     rax, [rbp+arg_0]
0x18001f5f5  mov     [rcx], rax
0x18001f5f8  mov     [rbp+arg_0], rcx
0x18001f5fc  cmp     [rbx], rdi
0x18001f5ff  jnz     short loc_18001F591
0x18001f601  mov     rcx, rsi; lpCriticalSection
0x18001f604  call    cs:__imp_LeaveCriticalSection
0x18001f60b  nop     dword ptr [rax+rax+00h]
0x18001f610  lea     rax, [rbp+arg_0]
0x18001f614  mov     [rbp+var_10], rax
0x18001f618  cmp     [rbp+arg_0], rdi
0x18001f61c  jz      short loc_18001F67B
0x18001f61e  mov     [rbp+arg_18], rdi
0x18001f622  lea     rdx, [rbp+arg_18]
0x18001f626  lea     rcx, [rbp+var_10]
0x18001f62a  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18001f62f  test    eax, eax
0x18001f631  jnz     short loc_18001F64D
0x18001f633  mov     rcx, [rbp+arg_18]; this
0x18001f637  xor     edx, edx; int
0x18001f639  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x18001f63e  lea     rcx, [rbp+var_10]
0x18001f642  mov     edi, eax
0x18001f644  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001f649  test    eax, eax
0x18001f64b  jz      short loc_18001F622
0x18001f64d  test    edi, edi
0x18001f64f  jz      short loc_18001F67B
0x18001f651  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f658  cmp     rcx, r13
0x18001f65b  jz      short loc_18001F67B
0x18001f65d  test    byte ptr [rcx+1Ch], 1
0x18001f661  jz      short loc_18001F67B
0x18001f663  mov     rcx, [rcx+10h]
0x18001f667  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001f66e  mov     edx, 4Eh ; 'N'
0x18001f673  mov     r9d, edi
0x18001f676  call    WPP_SF_d
0x18001f67b  mov     rcx, [rbp+arg_0]; void *
0x18001f67f  test    rcx, rcx
0x18001f682  jz      short loc_18001F689
0x18001f684  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x18001f689  mov     rbx, [rsp+30h+arg_8]
0x18001f68e  mov     eax, edi
0x18001f690  mov     rsi, [rsp+30h+arg_10]
0x18001f695  add     rsp, 30h
0x18001f699  pop     r15
0x18001f69b  pop     r14
0x18001f69d  pop     r13
0x18001f69f  pop     rdi
0x18001f6a0  pop     rbp
0x18001f6a1  retn
0x18001f6a3  lea     rcx, [rbp+arg_18]
0x18001f6a7  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001f6ac  test    eax, eax
0x18001f6ae  jnz     loc_18001F601
0x18001f6b4  mov     rbx, [rbp+arg_18]
0x18001f6b8  jmp     loc_18001F591
```
