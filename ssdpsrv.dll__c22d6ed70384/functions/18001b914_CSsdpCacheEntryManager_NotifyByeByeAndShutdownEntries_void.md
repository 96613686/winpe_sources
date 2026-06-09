# CSsdpCacheEntryManager::NotifyByeByeAndShutdownEntries(void)

- ea: `0x18001b914`
- end: `0x18001ba5e`
- name: `?NotifyByeByeAndShutdownEntries@CSsdpCacheEntryManager@@QEAAJXZ`
- size: `330`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b720`

## callees

- `0x18000993c`
- `0x18000a3f0`
- `0x18000a590`
- `0x1800186a0`
- `0x18001b914`
- `0x180022a80`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b994`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b994`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b960`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b960`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::NotifyByeByeAndShutdownEntries(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v1; // edi
  void **v3; // rcx
  void **v4; // rdx
  int v5; // eax
  void *v7; // [rsp+40h] [rbp+20h] BYREF
  CSsdpCacheEntry *v8; // [rsp+48h] [rbp+28h] BYREF
  void **v9; // [rsp+50h] [rbp+30h] BYREF

  v1 = 0;
  v7 = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
      (unsigned int)lpCriticalSection[1].LockCount);
  EnterCriticalSection(lpCriticalSection);
  v3 = (void **)v7;
  if ( v7 )
  {
    do
    {
      v4 = v3;
      v3 = (void **)*v3;
    }
    while ( v3 );
  }
  else
  {
    v4 = &v7;
  }
  *v4 = lpCriticalSection[1].DebugInfo;
  lpCriticalSection[1].DebugInfo = 0;
  lpCriticalSection[1].LockCount = 0;
  LeaveCriticalSection(lpCriticalSection);
  v9 = &v7;
  if ( v7 )
  {
    v8 = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&v9, &v8) )
        break;
      v5 = CSsdpCacheEntry::NotifyByeByeForAllAddressFamily(v8);
      if ( v5 < 0 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          (unsigned int)v5);
      v1 = CSsdpCacheEntry::HrShutdown((struct _RTL_CRITICAL_SECTION *)v8, 0);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v9) );
    if ( v1 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v1);
  }
  if ( v7 )
    CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'((_QWORD **)v7);
  return v1;
}

```

## disassembly

```asm
0x18001b914  mov     [rsp-18h+arg_18], rbx
0x18001b919  push    rbp
0x18001b91a  push    rdi
0x18001b91b  push    r14
0x18001b91d  mov     rbp, rsp
0x18001b920  sub     rsp, 20h
0x18001b924  xor     edi, edi
0x18001b926  mov     rbx, rcx
0x18001b929  mov     [rbp+arg_0], rdi
0x18001b92d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b934  lea     r14, WPP_GLOBAL_Control
0x18001b93b  cmp     rcx, r14
0x18001b93e  jz      short loc_18001B95D
0x18001b940  test    byte ptr [rcx+1Ch], 8
0x18001b944  jz      short loc_18001B95D
0x18001b946  mov     r9d, [rbx+30h]
0x18001b94a  lea     edx, [rdi+3Dh]
0x18001b94d  mov     rcx, [rcx+10h]
0x18001b951  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001b958  call    WPP_SF_d
0x18001b95d  mov     rcx, rbx; lpCriticalSection
0x18001b960  call    cs:__imp_EnterCriticalSection
0x18001b966  mov     rcx, [rbp+arg_0]
0x18001b96a  test    rcx, rcx
0x18001b96d  jz      short loc_18001B97F
0x18001b96f  mov     rax, [rcx]
0x18001b972  mov     rdx, rcx
0x18001b975  mov     rcx, rax
0x18001b978  test    rax, rax
0x18001b97b  jnz     short loc_18001B96F
0x18001b97d  jmp     short loc_18001B983
0x18001b97f  lea     rdx, [rbp+arg_0]
0x18001b983  mov     rax, [rbx+28h]
0x18001b987  mov     rcx, rbx; lpCriticalSection
0x18001b98a  mov     [rdx], rax
0x18001b98d  mov     [rbx+28h], rdi
0x18001b991  mov     [rbx+30h], edi
0x18001b994  call    cs:__imp_LeaveCriticalSection
0x18001b99a  lea     rax, [rbp+arg_0]
0x18001b99e  mov     [rbp+arg_10], rax
0x18001b9a2  cmp     [rbp+arg_0], rdi
0x18001b9a6  jz      loc_18001BA40
0x18001b9ac  mov     [rbp+arg_8], rdi
0x18001b9b0  lea     rdx, [rbp+arg_8]
0x18001b9b4  lea     rcx, [rbp+arg_10]
0x18001b9b8  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18001b9bd  test    eax, eax
0x18001b9bf  jnz     short loc_18001BA12
0x18001b9c1  mov     rcx, [rbp+arg_8]; this
0x18001b9c5  call    ?NotifyByeByeForAllAddressFamily@CSsdpCacheEntry@@QEAAJXZ; CSsdpCacheEntry::NotifyByeByeForAllAddressFamily(void)
0x18001b9ca  test    eax, eax
0x18001b9cc  jns     short loc_18001B9F8
0x18001b9ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9d5  cmp     rcx, r14
0x18001b9d8  jz      short loc_18001B9F8
0x18001b9da  test    byte ptr [rcx+1Ch], 1
0x18001b9de  jz      short loc_18001B9F8
0x18001b9e0  mov     rcx, [rcx+10h]
0x18001b9e4  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001b9eb  mov     edx, 3Eh ; '>'
0x18001b9f0  mov     r9d, eax
0x18001b9f3  call    WPP_SF_d
0x18001b9f8  mov     rcx, [rbp+arg_8]; this
0x18001b9fc  xor     edx, edx; int
0x18001b9fe  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x18001ba03  lea     rcx, [rbp+arg_10]
0x18001ba07  mov     edi, eax
0x18001ba09  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001ba0e  test    eax, eax
0x18001ba10  jz      short loc_18001B9B0
0x18001ba12  test    edi, edi
0x18001ba14  jz      short loc_18001BA40
0x18001ba16  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba1d  cmp     rcx, r14
0x18001ba20  jz      short loc_18001BA40
0x18001ba22  test    byte ptr [rcx+1Ch], 1
0x18001ba26  jz      short loc_18001BA40
0x18001ba28  mov     rcx, [rcx+10h]
0x18001ba2c  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001ba33  mov     edx, 3Fh ; '?'
0x18001ba38  mov     r9d, edi
0x18001ba3b  call    WPP_SF_d
0x18001ba40  mov     rcx, [rbp+arg_0]; void *
0x18001ba44  test    rcx, rcx
0x18001ba47  jz      short loc_18001BA4E
0x18001ba49  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x18001ba4e  mov     rbx, [rsp+20h+arg_18]
0x18001ba53  mov     eax, edi
0x18001ba55  add     rsp, 20h
0x18001ba59  pop     r14
0x18001ba5b  pop     rdi
0x18001ba5c  pop     rbp
0x18001ba5d  retn
```
