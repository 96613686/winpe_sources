# CSsdpCacheEntryManager::HrShutdown(void)

- ea: `0x180031944`
- end: `0x180031a1b`
- name: `?HrShutdown@CSsdpCacheEntryManager@@QEAAJXZ`
- size: `215`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002e970`
- `0x18002f900`

## callees

- `0x18000bad0`
- `0x18000bd3c`
- `0x180024490`
- `0x1800271fc`
- `0x180031944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800319fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800319fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031958`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031958`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrShutdown(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // edi
  LPCRITICAL_SECTION v3; // rbx
  _QWORD *p_Type; // rcx
  CSsdpCacheEntry *v6; // [rsp+30h] [rbp+8h] BYREF
  LPCRITICAL_SECTION v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  EnterCriticalSection(lpCriticalSection);
  v3 = lpCriticalSection + 1;
  v7 = lpCriticalSection + 1;
  if ( lpCriticalSection[1].DebugInfo )
  {
    v6 = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v7, &v6) )
        break;
      v2 = CSsdpCacheEntry::HrShutdown((struct _RTL_CRITICAL_SECTION *)v6, 0);
      if ( lpCriticalSection == (LPCRITICAL_SECTION)-40LL )
        break;
      p_Type = &v3->DebugInfo->Type;
      if ( !v3->DebugInfo )
        break;
      v3->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)*p_Type;
      *p_Type = 0;
      CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(p_Type);
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
0x180031944  mov     [rsp+arg_10], rbx
0x180031949  mov     [rsp+arg_18], rsi
0x18003194e  push    rdi
0x18003194f  sub     rsp, 20h
0x180031953  mov     rsi, rcx
0x180031956  xor     edi, edi
0x180031958  call    cs:__imp_EnterCriticalSection
0x18003195f  nop     dword ptr [rax+rax+00h]
0x180031964  lea     rbx, [rsi+28h]
0x180031968  mov     [rsp+28h+arg_8], rbx
0x18003196d  cmp     [rbx], rdi
0x180031970  jz      short loc_1800319BD
0x180031972  mov     [rsp+28h+arg_0], rdi
0x180031977  lea     rdx, [rsp+28h+arg_0]
0x18003197c  lea     rcx, [rsp+28h+arg_8]
0x180031981  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x180031986  test    eax, eax
0x180031988  jnz     short loc_1800319BD
0x18003198a  mov     rcx, [rsp+28h+arg_0]; this
0x18003198f  xor     edx, edx; int
0x180031991  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x180031996  mov     edi, eax
0x180031998  test    rbx, rbx
0x18003199b  jz      short loc_1800319BD
0x18003199d  mov     rcx, [rbx]; void *
0x1800319a0  test    rcx, rcx
0x1800319a3  jz      short loc_1800319BD
0x1800319a5  mov     rdx, [rcx]
0x1800319a8  mov     [rbx], rdx
0x1800319ab  mov     qword ptr [rcx], 0
0x1800319b2  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x1800319b7  cmp     qword ptr [rbx], 0
0x1800319bb  jnz     short loc_180031977
0x1800319bd  mov     dword ptr [rsi+30h], 0
0x1800319c4  test    edi, edi
0x1800319c6  jz      short loc_1800319F9
0x1800319c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319cf  lea     rax, WPP_GLOBAL_Control
0x1800319d6  cmp     rcx, rax
0x1800319d9  jz      short loc_1800319F9
0x1800319db  test    byte ptr [rcx+1Ch], 1
0x1800319df  jz      short loc_1800319F9
0x1800319e1  mov     rcx, [rcx+10h]
0x1800319e5  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x1800319ec  mov     edx, 3Ch ; '<'
0x1800319f1  mov     r9d, edi
0x1800319f4  call    WPP_SF_d
0x1800319f9  mov     rcx, rsi; lpCriticalSection
0x1800319fc  call    cs:__imp_LeaveCriticalSection
0x180031a03  nop     dword ptr [rax+rax+00h]
0x180031a08  mov     rbx, [rsp+28h+arg_10]
0x180031a0d  mov     eax, edi
0x180031a0f  mov     rsi, [rsp+28h+arg_18]
0x180031a14  add     rsp, 20h
0x180031a18  pop     rdi
0x180031a19  retn
```
