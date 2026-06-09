# CSsdpCacheEntryManager::HrClearDirtyInterfaceGuids(long,_GUID *)

- ea: `0x18001e068`
- end: `0x18001e1cc`
- name: `?HrClearDirtyInterfaceGuids@CSsdpCacheEntryManager@@QEAAJJPEAU_GUID@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e500`

## callees

- `0x18000a3f0`
- `0x18000a590`
- `0x1800186a0`
- `0x18001e068`
- `0x18001e1d4`
- `0x180022a80`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e11a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e11a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e090`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e090`

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
      v3 = CSsdpCacheEntry::HrShutdown(v12, 0);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(v10) );
    if ( v3 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v3);
  }
  if ( v11 )
    CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'((_QWORD **)v11);
  return v3;
}

```

## disassembly

```asm
0x18001e068  mov     [rsp-28h+arg_8], rbx
0x18001e06d  mov     [rsp-28h+arg_10], rsi
0x18001e072  push    rbp
0x18001e073  push    rdi
0x18001e074  push    r13
0x18001e076  push    r14
0x18001e078  push    r15
0x18001e07a  mov     rbp, rsp
0x18001e07d  sub     rsp, 30h
0x18001e081  xor     edi, edi
0x18001e083  mov     r14, r8
0x18001e086  mov     [rbp+arg_0], rdi
0x18001e08a  mov     r15d, edx
0x18001e08d  mov     rsi, rcx
0x18001e090  call    cs:__imp_EnterCriticalSection
0x18001e096  lea     rbx, [rsi+28h]
0x18001e09a  mov     [rbp+arg_18], rbx
0x18001e09e  lea     r13, WPP_GLOBAL_Control
0x18001e0a5  jmp     short loc_18001E112
0x18001e0a7  test    rbx, rbx
0x18001e0aa  jz      short loc_18001E117
0x18001e0ac  mov     rcx, [rbx]
0x18001e0af  test    rcx, rcx
0x18001e0b2  jz      short loc_18001E117
0x18001e0b4  add     rcx, 8; this
0x18001e0b8  mov     r8, r14; struct _GUID *
0x18001e0bb  mov     edx, r15d; int
0x18001e0be  call    ?FCheckForDirtyInterfaceGuids@CSsdpCacheEntry@@QEAAHJPEAU_GUID@@@Z; CSsdpCacheEntry::FCheckForDirtyInterfaceGuids(long,_GUID *)
0x18001e0c3  test    eax, eax
0x18001e0c5  jz      loc_18001E1B2
0x18001e0cb  dec     dword ptr [rsi+30h]
0x18001e0ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0d5  cmp     rcx, r13
0x18001e0d8  jz      short loc_18001E0F9
0x18001e0da  test    byte ptr [rcx+1Ch], 8
0x18001e0de  jz      short loc_18001E0F9
0x18001e0e0  mov     r9d, [rsi+30h]
0x18001e0e4  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001e0eb  mov     rcx, [rcx+10h]
0x18001e0ef  mov     edx, 4Dh ; 'M'
0x18001e0f4  call    WPP_SF_d
0x18001e0f9  mov     rcx, [rbx]
0x18001e0fc  test    rcx, rcx
0x18001e0ff  jz      short loc_18001E117
0x18001e101  mov     rax, [rcx]
0x18001e104  mov     [rbx], rax
0x18001e107  mov     rax, [rbp+arg_0]
0x18001e10b  mov     [rcx], rax
0x18001e10e  mov     [rbp+arg_0], rcx
0x18001e112  cmp     [rbx], rdi
0x18001e115  jnz     short loc_18001E0A7
0x18001e117  mov     rcx, rsi; lpCriticalSection
0x18001e11a  call    cs:__imp_LeaveCriticalSection
0x18001e120  lea     rax, [rbp+arg_0]
0x18001e124  mov     [rbp+var_10], rax
0x18001e128  cmp     [rbp+arg_0], rdi
0x18001e12c  jz      short loc_18001E18B
0x18001e12e  mov     [rbp+arg_18], rdi
0x18001e132  lea     rdx, [rbp+arg_18]
0x18001e136  lea     rcx, [rbp+var_10]
0x18001e13a  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18001e13f  test    eax, eax
0x18001e141  jnz     short loc_18001E15D
0x18001e143  mov     rcx, [rbp+arg_18]; this
0x18001e147  xor     edx, edx; int
0x18001e149  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x18001e14e  lea     rcx, [rbp+var_10]
0x18001e152  mov     edi, eax
0x18001e154  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001e159  test    eax, eax
0x18001e15b  jz      short loc_18001E132
0x18001e15d  test    edi, edi
0x18001e15f  jz      short loc_18001E18B
0x18001e161  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e168  cmp     rcx, r13
0x18001e16b  jz      short loc_18001E18B
0x18001e16d  test    byte ptr [rcx+1Ch], 1
0x18001e171  jz      short loc_18001E18B
0x18001e173  mov     rcx, [rcx+10h]
0x18001e177  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001e17e  mov     edx, 4Eh ; 'N'
0x18001e183  mov     r9d, edi
0x18001e186  call    WPP_SF_d
0x18001e18b  mov     rcx, [rbp+arg_0]; void *
0x18001e18f  test    rcx, rcx
0x18001e192  jz      short loc_18001E199
0x18001e194  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x18001e199  mov     rbx, [rsp+30h+arg_8]
0x18001e19e  mov     eax, edi
0x18001e1a0  mov     rsi, [rsp+30h+arg_10]
0x18001e1a5  add     rsp, 30h
0x18001e1a9  pop     r15
0x18001e1ab  pop     r14
0x18001e1ad  pop     r13
0x18001e1af  pop     rdi
0x18001e1b0  pop     rbp
0x18001e1b1  retn
0x18001e1b2  lea     rcx, [rbp+arg_18]
0x18001e1b6  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001e1bb  test    eax, eax
0x18001e1bd  jnz     loc_18001E117
0x18001e1c3  mov     rbx, [rbp+arg_18]
0x18001e1c7  jmp     loc_18001E0A7
```
