# CSsdpCacheEntryManager::HrShutdown(void)

- ea: `0x18002f680`
- end: `0x18002f74a`
- name: `?HrShutdown@CSsdpCacheEntryManager@@QEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002c980`
- `0x18002d870`

## callees

- `0x18000a3f0`
- `0x18000a590`
- `0x180022a80`
- `0x1800255a8`
- `0x18002f680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f732`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f732`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f694`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f694`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrShutdown(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // edi
  LPCRITICAL_SECTION v3; // rbx
  PRTL_CRITICAL_SECTION_DEBUG *DebugInfo; // rcx
  CSsdpCacheEntry *v6; // [rsp+30h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  EnterCriticalSection(lpCriticalSection);
  v3 = lpCriticalSection + 1;
  v7 = lpCriticalSection + 1;
  if ( lpCriticalSection[1].DebugInfo )
  {
    v6 = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&v7, &v6) )
        break;
      v2 = CSsdpCacheEntry::HrShutdown((struct _RTL_CRITICAL_SECTION *)v6, 0);
      if ( lpCriticalSection == (LPCRITICAL_SECTION)-40LL )
        break;
      DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG *)v3->DebugInfo;
      if ( !v3->DebugInfo )
        break;
      v3->DebugInfo = *DebugInfo;
      *DebugInfo = 0;
      CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'((_QWORD **)DebugInfo);
    }
    while ( v3->DebugInfo );
  }
  lpCriticalSection[1].LockCount = 0;
  if ( v2 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v2);
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x18002f680  mov     [rsp+arg_10], rbx
0x18002f685  mov     [rsp+arg_18], rsi
0x18002f68a  push    rdi
0x18002f68b  sub     rsp, 20h
0x18002f68f  mov     rsi, rcx
0x18002f692  xor     edi, edi
0x18002f694  call    cs:__imp_EnterCriticalSection
0x18002f69a  lea     rbx, [rsi+28h]
0x18002f69e  mov     [rsp+28h+arg_8], rbx
0x18002f6a3  cmp     [rbx], rdi
0x18002f6a6  jz      short loc_18002F6F3
0x18002f6a8  mov     [rsp+28h+arg_0], rdi
0x18002f6ad  lea     rdx, [rsp+28h+arg_0]
0x18002f6b2  lea     rcx, [rsp+28h+arg_8]
0x18002f6b7  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18002f6bc  test    eax, eax
0x18002f6be  jnz     short loc_18002F6F3
0x18002f6c0  mov     rcx, [rsp+28h+arg_0]; this
0x18002f6c5  xor     edx, edx; int
0x18002f6c7  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x18002f6cc  mov     edi, eax
0x18002f6ce  test    rbx, rbx
0x18002f6d1  jz      short loc_18002F6F3
0x18002f6d3  mov     rcx, [rbx]; void *
0x18002f6d6  test    rcx, rcx
0x18002f6d9  jz      short loc_18002F6F3
0x18002f6db  mov     rdx, [rcx]
0x18002f6de  mov     [rbx], rdx
0x18002f6e1  mov     qword ptr [rcx], 0
0x18002f6e8  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x18002f6ed  cmp     qword ptr [rbx], 0
0x18002f6f1  jnz     short loc_18002F6AD
0x18002f6f3  mov     dword ptr [rsi+30h], 0
0x18002f6fa  test    edi, edi
0x18002f6fc  jz      short loc_18002F72F
0x18002f6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f705  lea     rax, WPP_GLOBAL_Control
0x18002f70c  cmp     rcx, rax
0x18002f70f  jz      short loc_18002F72F
0x18002f711  test    byte ptr [rcx+1Ch], 1
0x18002f715  jz      short loc_18002F72F
0x18002f717  mov     rcx, [rcx+10h]
0x18002f71b  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18002f722  mov     edx, 3Ch ; '<'
0x18002f727  mov     r9d, edi
0x18002f72a  call    WPP_SF_d
0x18002f72f  mov     rcx, rsi; lpCriticalSection
0x18002f732  call    cs:__imp_LeaveCriticalSection
0x18002f738  mov     rbx, [rsp+28h+arg_10]
0x18002f73d  mov     eax, edi
0x18002f73f  mov     rsi, [rsp+28h+arg_18]
0x18002f744  add     rsp, 20h
0x18002f748  pop     rdi
0x18002f749  retn
```
