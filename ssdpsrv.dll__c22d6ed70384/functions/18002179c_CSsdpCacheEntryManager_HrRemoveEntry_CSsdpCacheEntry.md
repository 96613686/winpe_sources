# CSsdpCacheEntryManager::HrRemoveEntry(CSsdpCacheEntry *)

- ea: `0x18002179c`
- end: `0x1800218f7`
- name: `?HrRemoveEntry@CSsdpCacheEntryManager@@QEAAJPEAVCSsdpCacheEntry@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002f580`

## callees

- `0x18000a3f0`
- `0x18000a590`
- `0x1800186a0`
- `0x18001b070`
- `0x18002179c`
- `0x180022a80`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021861`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021861`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800217bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002180e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800217bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002180e`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrRemoveEntry(LPCRITICAL_SECTION lpCriticalSection, void **a2)
{
  unsigned int v2; // r14d
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  int v6; // ebx
  void *v8; // [rsp+50h] [rbp+30h] BYREF
  CSsdpCacheEntry *v9; // [rsp+60h] [rbp+40h] BYREF
  void **v10; // [rsp+68h] [rbp+48h] BYREF

  v2 = 0;
  v8 = 0;
  EnterCriticalSection(lpCriticalSection);
  v9 = (CSsdpCacheEntry *)&lpCriticalSection[1];
  if ( lpCriticalSection[1].DebugInfo )
  {
    v10 = 0;
    while ( !(unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&v9, &v10) )
    {
      if ( v10 == a2 )
      {
        v5 = (struct _RTL_CRITICAL_SECTION *)(a2 + 27);
        EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 27));
        v6 = *(_DWORD *)a2;
        LeaveCriticalSection(v5);
        if ( v6 )
        {
          CUList<CSsdpCacheEntry>::Iterator::HrMoveToList((_QWORD ***)&v9, &v8);
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
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v9) )
        break;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  v10 = &v8;
  if ( v8 )
  {
    v9 = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&v10, &v9) )
        break;
      v2 = CSsdpCacheEntry::HrShutdown(v9, 1);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v10) );
    if ( v2 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v2);
  }
  if ( v8 )
    CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'((_QWORD **)v8);
  return v2;
}

```

## disassembly

```asm
0x18002179c  mov     [rsp-28h+arg_8], rbx
0x1800217a1  push    rbp
0x1800217a2  push    rsi
0x1800217a3  push    rdi
0x1800217a4  push    r12
0x1800217a6  push    r14
0x1800217a8  mov     rbp, rsp
0x1800217ab  sub     rsp, 20h
0x1800217af  xor     r14d, r14d
0x1800217b2  mov     rbx, rdx
0x1800217b5  mov     [rbp+arg_0], r14
0x1800217b9  mov     rsi, rcx
0x1800217bc  call    cs:__imp_EnterCriticalSection
0x1800217c2  lea     rax, [rsi+28h]
0x1800217c6  lea     r12, WPP_GLOBAL_Control
0x1800217cd  mov     [rbp+arg_10], rax
0x1800217d1  cmp     [rax], r14
0x1800217d4  jz      loc_18002185E
0x1800217da  mov     [rbp+arg_18], r14
0x1800217de  lea     rdx, [rbp+arg_18]
0x1800217e2  lea     rcx, [rbp+arg_10]
0x1800217e6  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x1800217eb  test    eax, eax
0x1800217ed  jnz     short loc_18002185E
0x1800217ef  cmp     [rbp+arg_18], rbx
0x1800217f3  jz      short loc_180021804
0x1800217f5  lea     rcx, [rbp+arg_10]
0x1800217f9  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x1800217fe  test    eax, eax
0x180021800  jz      short loc_1800217DE
0x180021802  jmp     short loc_18002185E
0x180021804  lea     rdi, [rbx+0D8h]
0x18002180b  mov     rcx, rdi; lpCriticalSection
0x18002180e  call    cs:__imp_EnterCriticalSection
0x180021814  mov     ebx, [rbx]
0x180021816  mov     rcx, rdi; lpCriticalSection
0x180021819  call    cs:__imp_LeaveCriticalSection
0x18002181f  test    ebx, ebx
0x180021821  jz      short loc_18002185E
0x180021823  lea     rdx, [rbp+arg_0]
0x180021827  lea     rcx, [rbp+arg_10]
0x18002182b  call    ?HrMoveToList@Iterator@?$CUList@VCSsdpCacheEntry@@@@QEAAJAEAV2@@Z; CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(CUList<CSsdpCacheEntry> &)
0x180021830  dec     dword ptr [rsi+30h]
0x180021833  mov     rcx, cs:WPP_GLOBAL_Control
0x18002183a  cmp     rcx, r12
0x18002183d  jz      short loc_18002185E
0x18002183f  test    byte ptr [rcx+1Ch], 8
0x180021843  jz      short loc_18002185E
0x180021845  mov     r9d, [rsi+30h]
0x180021849  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180021850  mov     rcx, [rcx+10h]
0x180021854  mov     edx, 40h ; '@'
0x180021859  call    WPP_SF_d
0x18002185e  mov     rcx, rsi; lpCriticalSection
0x180021861  call    cs:__imp_LeaveCriticalSection
0x180021867  lea     rax, [rbp+arg_0]
0x18002186b  mov     [rbp+arg_18], rax
0x18002186f  cmp     [rbp+arg_0], r14
0x180021873  jz      short loc_1800218D5
0x180021875  mov     [rbp+arg_10], r14
0x180021879  lea     rdx, [rbp+arg_10]
0x18002187d  lea     rcx, [rbp+arg_18]
0x180021881  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x180021886  test    eax, eax
0x180021888  jnz     short loc_1800218A6
0x18002188a  mov     rcx, [rbp+arg_10]; this
0x18002188e  lea     edx, [rax+1]; int
0x180021891  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x180021896  lea     rcx, [rbp+arg_18]
0x18002189a  mov     r14d, eax
0x18002189d  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x1800218a2  test    eax, eax
0x1800218a4  jz      short loc_180021879
0x1800218a6  test    r14d, r14d
0x1800218a9  jz      short loc_1800218D5
0x1800218ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218b2  cmp     rcx, r12
0x1800218b5  jz      short loc_1800218D5
0x1800218b7  test    byte ptr [rcx+1Ch], 1
0x1800218bb  jz      short loc_1800218D5
0x1800218bd  mov     rcx, [rcx+10h]
0x1800218c1  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x1800218c8  mov     edx, 41h ; 'A'
0x1800218cd  mov     r9d, r14d
0x1800218d0  call    WPP_SF_d
0x1800218d5  mov     rcx, [rbp+arg_0]; void *
0x1800218d9  test    rcx, rcx
0x1800218dc  jz      short loc_1800218E3
0x1800218de  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x1800218e3  mov     rbx, [rsp+20h+arg_8]
0x1800218e8  mov     eax, r14d
0x1800218eb  add     rsp, 20h
0x1800218ef  pop     r14
0x1800218f1  pop     r12
0x1800218f3  pop     rdi
0x1800218f4  pop     rsi
0x1800218f5  pop     rbp
0x1800218f6  retn
```
