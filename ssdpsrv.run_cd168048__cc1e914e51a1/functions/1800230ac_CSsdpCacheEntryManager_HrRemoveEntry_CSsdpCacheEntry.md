# CSsdpCacheEntryManager::HrRemoveEntry(CSsdpCacheEntry *)

- ea: `0x1800230ac`
- end: `0x1800231ee`
- name: `?HrRemoveEntry@CSsdpCacheEntryManager@@QEAAJPEAVCSsdpCacheEntry@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct CSsdpCacheEntry *this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180031840`

## callees

- `0x18000bad0`
- `0x18000bd3c`
- `0x180019920`
- `0x18001c374`
- `0x1800230ac`
- `0x180023e70`
- `0x180024490`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002315a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002315a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800230c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800230c6`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrRemoveEntry(LPCRITICAL_SECTION lpCriticalSection, void **this)
{
  unsigned int v2; // edi
  void *v6; // [rsp+50h] [rbp+30h] BYREF
  CSsdpCacheEntry *v7; // [rsp+60h] [rbp+40h] BYREF
  void **v8; // [rsp+68h] [rbp+48h] BYREF

  v2 = 0;
  v6 = 0;
  EnterCriticalSection(lpCriticalSection);
  v7 = (CSsdpCacheEntry *)&lpCriticalSection[1];
  if ( lpCriticalSection[1].DebugInfo )
  {
    v8 = 0;
    while ( !(unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v7, &v8) )
    {
      if ( v8 == this )
      {
        if ( (unsigned int)CSsdpCacheEntry::FTimerFired((CSsdpCacheEntry *)this) )
        {
          CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(&v7, &v6);
          --lpCriticalSection[1].LockCount;
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
              (unsigned int)lpCriticalSection[1].LockCount);
        }
        break;
      }
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext(&v7) )
        break;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  v8 = &v6;
  if ( v6 )
  {
    v7 = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v8, &v7) )
        break;
      v2 = CSsdpCacheEntry::HrShutdown(v7, 1);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(&v8) );
    if ( v2 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v2);
  }
  if ( v6 )
    CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(v6);
  return v2;
}

```

## disassembly

```asm
0x1800230ac  push    rbp
0x1800230ae  push    rbx
0x1800230af  push    rsi
0x1800230b0  push    rdi
0x1800230b1  push    r15
0x1800230b3  mov     rbp, rsp
0x1800230b6  sub     rsp, 20h
0x1800230ba  xor     edi, edi
0x1800230bc  mov     rsi, rdx
0x1800230bf  mov     [rbp+arg_0], rdi
0x1800230c3  mov     rbx, rcx
0x1800230c6  call    cs:__imp_EnterCriticalSection
0x1800230cd  nop     dword ptr [rax+rax+00h]
0x1800230d2  lea     rax, [rbx+28h]
0x1800230d6  lea     r15, WPP_GLOBAL_Control
0x1800230dd  mov     [rbp+arg_10], rax
0x1800230e1  cmp     [rax], rdi
0x1800230e4  jz      short loc_180023157
0x1800230e6  mov     [rbp+arg_18], rdi
0x1800230ea  lea     rdx, [rbp+arg_18]
0x1800230ee  lea     rcx, [rbp+arg_10]
0x1800230f2  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x1800230f7  test    eax, eax
0x1800230f9  jnz     short loc_180023157
0x1800230fb  cmp     [rbp+arg_18], rsi
0x1800230ff  jz      short loc_180023110
0x180023101  lea     rcx, [rbp+arg_10]
0x180023105  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18002310a  test    eax, eax
0x18002310c  jz      short loc_1800230EA
0x18002310e  jmp     short loc_180023157
0x180023110  mov     rcx, rsi; this
0x180023113  call    ?FTimerFired@CSsdpCacheEntry@@QEAAHXZ; CSsdpCacheEntry::FTimerFired(void)
0x180023118  test    eax, eax
0x18002311a  jz      short loc_180023157
0x18002311c  lea     rdx, [rbp+arg_0]
0x180023120  lea     rcx, [rbp+arg_10]
0x180023124  call    ?HrMoveToList@Iterator@?$CUList@VCSsdpCacheEntry@@@@QEAAJAEAV2@@Z; CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(CUList<CSsdpCacheEntry> &)
0x180023129  dec     dword ptr [rbx+30h]
0x18002312c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023133  cmp     rcx, r15
0x180023136  jz      short loc_180023157
0x180023138  test    byte ptr [rcx+1Ch], 8
0x18002313c  jz      short loc_180023157
0x18002313e  mov     r9d, [rbx+30h]
0x180023142  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180023149  mov     rcx, [rcx+10h]
0x18002314d  mov     edx, 40h ; '@'
0x180023152  call    WPP_SF_d
0x180023157  mov     rcx, rbx; lpCriticalSection
0x18002315a  call    cs:__imp_LeaveCriticalSection
0x180023161  nop     dword ptr [rax+rax+00h]
0x180023166  lea     rax, [rbp+arg_0]
0x18002316a  mov     [rbp+arg_18], rax
0x18002316e  cmp     [rbp+arg_0], rdi
0x180023172  jz      short loc_1800231D2
0x180023174  mov     [rbp+arg_10], rdi
0x180023178  lea     rdx, [rbp+arg_10]
0x18002317c  lea     rcx, [rbp+arg_18]
0x180023180  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x180023185  test    eax, eax
0x180023187  jnz     short loc_1800231A4
0x180023189  mov     rcx, [rbp+arg_10]; this
0x18002318d  lea     edx, [rax+1]; int
0x180023190  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x180023195  lea     rcx, [rbp+arg_18]
0x180023199  mov     edi, eax
0x18002319b  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x1800231a0  test    eax, eax
0x1800231a2  jz      short loc_180023178
0x1800231a4  test    edi, edi
0x1800231a6  jz      short loc_1800231D2
0x1800231a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231af  cmp     rcx, r15
0x1800231b2  jz      short loc_1800231D2
0x1800231b4  test    byte ptr [rcx+1Ch], 1
0x1800231b8  jz      short loc_1800231D2
0x1800231ba  mov     rcx, [rcx+10h]
0x1800231be  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x1800231c5  mov     edx, 41h ; 'A'
0x1800231ca  mov     r9d, edi
0x1800231cd  call    WPP_SF_d
0x1800231d2  mov     rcx, [rbp+arg_0]; void *
0x1800231d6  test    rcx, rcx
0x1800231d9  jz      short loc_1800231E0
0x1800231db  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x1800231e0  mov     eax, edi
0x1800231e2  add     rsp, 20h
0x1800231e6  pop     r15
0x1800231e8  pop     rdi
0x1800231e9  pop     rsi
0x1800231ea  pop     rbx
0x1800231eb  pop     rbp
0x1800231ec  retn
```
