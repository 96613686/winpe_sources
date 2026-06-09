# CSsdpCacheEntryManager::NotifyByeByeAndShutdownEntries(void)

- ea: `0x18001cc54`
- end: `0x18001cdab`
- name: `?NotifyByeByeAndShutdownEntries@CSsdpCacheEntryManager@@QEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001ca60`

## callees

- `0x18000aef4`
- `0x18000bad0`
- `0x18000bd3c`
- `0x180019920`
- `0x18001cc54`
- `0x180024490`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ccda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ccda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cca0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cca0`

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
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v9, &v8) )
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
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(&v9) );
    if ( v1 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v1);
  }
  if ( v7 )
    CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(v7);
  return v1;
}

```

## disassembly

```asm
0x18001cc54  mov     [rsp-18h+arg_18], rbx
0x18001cc59  push    rbp
0x18001cc5a  push    rdi
0x18001cc5b  push    r14
0x18001cc5d  mov     rbp, rsp
0x18001cc60  sub     rsp, 20h
0x18001cc64  xor     edi, edi
0x18001cc66  mov     rbx, rcx
0x18001cc69  mov     [rbp+arg_0], rdi
0x18001cc6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc74  lea     r14, WPP_GLOBAL_Control
0x18001cc7b  cmp     rcx, r14
0x18001cc7e  jz      short loc_18001CC9D
0x18001cc80  test    byte ptr [rcx+1Ch], 8
0x18001cc84  jz      short loc_18001CC9D
0x18001cc86  mov     r9d, [rbx+30h]
0x18001cc8a  lea     edx, [rdi+3Dh]
0x18001cc8d  mov     rcx, [rcx+10h]
0x18001cc91  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001cc98  call    WPP_SF_d
0x18001cc9d  mov     rcx, rbx; lpCriticalSection
0x18001cca0  call    cs:__imp_EnterCriticalSection
0x18001cca7  nop     dword ptr [rax+rax+00h]
0x18001ccac  mov     rcx, [rbp+arg_0]
0x18001ccb0  test    rcx, rcx
0x18001ccb3  jz      short loc_18001CCC5
0x18001ccb5  mov     rax, [rcx]
0x18001ccb8  mov     rdx, rcx
0x18001ccbb  mov     rcx, rax
0x18001ccbe  test    rax, rax
0x18001ccc1  jnz     short loc_18001CCB5
0x18001ccc3  jmp     short loc_18001CCC9
0x18001ccc5  lea     rdx, [rbp+arg_0]
0x18001ccc9  mov     rax, [rbx+28h]
0x18001cccd  mov     rcx, rbx; lpCriticalSection
0x18001ccd0  mov     [rdx], rax
0x18001ccd3  mov     [rbx+28h], rdi
0x18001ccd7  mov     [rbx+30h], edi
0x18001ccda  call    cs:__imp_LeaveCriticalSection
0x18001cce1  nop     dword ptr [rax+rax+00h]
0x18001cce6  lea     rax, [rbp+arg_0]
0x18001ccea  mov     [rbp+arg_10], rax
0x18001ccee  cmp     [rbp+arg_0], rdi
0x18001ccf2  jz      loc_18001CD8C
0x18001ccf8  mov     [rbp+arg_8], rdi
0x18001ccfc  lea     rdx, [rbp+arg_8]
0x18001cd00  lea     rcx, [rbp+arg_10]
0x18001cd04  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18001cd09  test    eax, eax
0x18001cd0b  jnz     short loc_18001CD5E
0x18001cd0d  mov     rcx, [rbp+arg_8]; this
0x18001cd11  call    ?NotifyByeByeForAllAddressFamily@CSsdpCacheEntry@@QEAAJXZ; CSsdpCacheEntry::NotifyByeByeForAllAddressFamily(void)
0x18001cd16  test    eax, eax
0x18001cd18  jns     short loc_18001CD44
0x18001cd1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd21  cmp     rcx, r14
0x18001cd24  jz      short loc_18001CD44
0x18001cd26  test    byte ptr [rcx+1Ch], 1
0x18001cd2a  jz      short loc_18001CD44
0x18001cd2c  mov     rcx, [rcx+10h]
0x18001cd30  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001cd37  mov     edx, 3Eh ; '>'
0x18001cd3c  mov     r9d, eax
0x18001cd3f  call    WPP_SF_d
0x18001cd44  mov     rcx, [rbp+arg_8]; this
0x18001cd48  xor     edx, edx; int
0x18001cd4a  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x18001cd4f  lea     rcx, [rbp+arg_10]
0x18001cd53  mov     edi, eax
0x18001cd55  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001cd5a  test    eax, eax
0x18001cd5c  jz      short loc_18001CCFC
0x18001cd5e  test    edi, edi
0x18001cd60  jz      short loc_18001CD8C
0x18001cd62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd69  cmp     rcx, r14
0x18001cd6c  jz      short loc_18001CD8C
0x18001cd6e  test    byte ptr [rcx+1Ch], 1
0x18001cd72  jz      short loc_18001CD8C
0x18001cd74  mov     rcx, [rcx+10h]
0x18001cd78  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001cd7f  mov     edx, 3Fh ; '?'
0x18001cd84  mov     r9d, edi
0x18001cd87  call    WPP_SF_d
0x18001cd8c  mov     rcx, [rbp+arg_0]; void *
0x18001cd90  test    rcx, rcx
0x18001cd93  jz      short loc_18001CD9A
0x18001cd95  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x18001cd9a  mov     rbx, [rsp+20h+arg_18]
0x18001cd9f  mov     eax, edi
0x18001cda1  add     rsp, 20h
0x18001cda5  pop     r14
0x18001cda7  pop     rdi
0x18001cda8  pop     rbp
0x18001cda9  retn
```
