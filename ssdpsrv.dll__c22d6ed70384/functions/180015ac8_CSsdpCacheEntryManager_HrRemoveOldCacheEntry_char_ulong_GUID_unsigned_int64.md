# CSsdpCacheEntryManager::HrRemoveOldCacheEntry(char *,ulong,_GUID,unsigned __int64)

- ea: `0x180015ac8`
- end: `0x180015c70`
- name: `?HrRemoveOldCacheEntry@CSsdpCacheEntryManager@@QEAAJPEADKU_GUID@@_K@Z`
- size: `424`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, HashFn *Str1, unsigned int, struct _GUID *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001436c`

## callees

- `0x18000993c`
- `0x18000a3f0`
- `0x18000a590`
- `0x180015ac8`
- `0x180015d70`
- `0x1800186a0`
- `0x180018fe0`
- `0x18001b070`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015af3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015af3`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrRemoveOldCacheEntry(
        LPCRITICAL_SECTION lpCriticalSection,
        HashFn *Str1,
        unsigned int a3,
        struct _GUID *a4,
        unsigned __int64 a5)
{
  _QWORD **v5; // rdi
  unsigned int v9; // esi
  const char *v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // eax
  struct _RTL_CRITICAL_SECTION *v13; // r10
  unsigned __int64 v14; // r15
  unsigned int v15; // r12d
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  struct _RTL_CRITICAL_SECTION **p_CriticalSection; // rbp
  _QWORD *v18; // rbx
  _QWORD *v19; // rax
  CSsdpCacheEntry *v20; // rsi
  int v21; // eax
  unsigned int v22; // eax
  _QWORD v24[2]; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v25; // [rsp+40h] [rbp-48h] BYREF
  struct _RTL_CRITICAL_SECTION *v26; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v27; // [rsp+A0h] [rbp+18h]

  v27 = a3;
  v5 = 0;
  v24[0] = 0;
  v9 = 0;
  EnterCriticalSection(lpCriticalSection);
  v26 = lpCriticalSection + 1;
  if ( lpCriticalSection[1].DebugInfo )
  {
    v12 = HashFn::HashString(Str1, v10, v11);
    v14 = a5;
    v15 = v12;
    while ( v13 )
    {
      DebugInfo = v13->DebugInfo;
      if ( !v13->DebugInfo )
        break;
      p_CriticalSection = &DebugInfo->CriticalSection;
      v25 = *a4;
      if ( (unsigned int)CSsdpCacheEntry::FIsSearchMatchHash(
                           (CSsdpCacheEntry *)&DebugInfo->CriticalSection,
                           (const char *)Str1,
                           v27,
                           &v25,
                           v15)
        && (unsigned __int64)p_CriticalSection[33] < v14 )
      {
        CUList<CSsdpCacheEntry>::Iterator::HrMoveToList((_QWORD ***)&v26, v24);
        --lpCriticalSection[1].LockCount;
        v5 = (_QWORD **)v24[0];
        break;
      }
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v26) )
        break;
      v13 = v26;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( v5 )
  {
    v18 = v24;
    do
    {
      if ( !v18 )
        break;
      v19 = (_QWORD *)*v18;
      if ( !*v18 )
        break;
      v20 = (CSsdpCacheEntry *)(v19 + 1);
      v21 = CSsdpCacheEntry::NotifyByeByeForAllAddressFamily((CSsdpCacheEntry *)(v19 + 1));
      if ( v21 < 0 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          (unsigned int)v21);
      v22 = CSsdpCacheEntry::HrShutdown(v20, 0);
      v18 = (_QWORD *)*v18;
      v9 = v22;
      if ( !v18 )
        break;
    }
    while ( *v18 );
    if ( v9 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v9);
    CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(v5);
  }
  return v9;
}

```

## disassembly

```asm
0x180015ac8  mov     [rsp+arg_8], rbx
0x180015acd  mov     [rsp+arg_10], r8d
0x180015ad2  push    rbp
0x180015ad3  push    rsi
0x180015ad4  push    rdi
0x180015ad5  push    r12
0x180015ad7  push    r13
0x180015ad9  push    r14
0x180015adb  push    r15
0x180015add  sub     rsp, 50h
0x180015ae1  xor     edi, edi
0x180015ae3  mov     r13, r9
0x180015ae6  mov     [rsp+88h+var_58], rdi
0x180015aeb  mov     r14, rdx
0x180015aee  mov     rbx, rcx
0x180015af1  xor     esi, esi
0x180015af3  call    cs:__imp_EnterCriticalSection
0x180015af9  lea     r10, [rbx+28h]
0x180015afd  mov     [rsp+88h+arg_0], r10
0x180015b05  cmp     [r10], rsi
0x180015b08  jz      loc_180015B9C
0x180015b0e  mov     rcx, r14; this
0x180015b11  call    ?HashString@HashFn@@YAKPEBDK@Z; HashFn::HashString(char const *,ulong)
0x180015b16  mov     r15, [rsp+88h+arg_20]
0x180015b1e  mov     r12d, eax
0x180015b21  test    r10, r10
0x180015b24  jz      short loc_180015B9C
0x180015b26  mov     rax, [r10]
0x180015b29  test    rax, rax
0x180015b2c  jz      short loc_180015B9C
0x180015b2e  movaps  xmm0, xmmword ptr [r13+0]
0x180015b33  lea     rbp, [rax+8]
0x180015b37  mov     r8d, [rsp+88h+arg_10]; unsigned int
0x180015b3f  lea     r9, [rsp+88h+var_48]; struct _GUID
0x180015b44  mov     rcx, rbp; this
0x180015b47  movdqa  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180015b4d  mov     rdx, r14; Str1
0x180015b50  mov     [rsp+88h+var_68], r12d; unsigned int
0x180015b55  call    ?FIsSearchMatchHash@CSsdpCacheEntry@@QEAAHPEBDKU_GUID@@K@Z; CSsdpCacheEntry::FIsSearchMatchHash(char const *,ulong,_GUID,ulong)
0x180015b5a  test    eax, eax
0x180015b5c  jz      short loc_180015B67
0x180015b5e  cmp     [rbp+108h], r15
0x180015b65  jb      short loc_180015B82
0x180015b67  lea     rcx, [rsp+88h+arg_0]
0x180015b6f  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180015b74  test    eax, eax
0x180015b76  jnz     short loc_180015B9C
0x180015b78  mov     r10, [rsp+88h+arg_0]
0x180015b80  jmp     short loc_180015B21
0x180015b82  lea     rdx, [rsp+88h+var_58]
0x180015b87  lea     rcx, [rsp+88h+arg_0]
0x180015b8f  call    ?HrMoveToList@Iterator@?$CUList@VCSsdpCacheEntry@@@@QEAAJAEAV2@@Z; CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(CUList<CSsdpCacheEntry> &)
0x180015b94  dec     dword ptr [rbx+30h]
0x180015b97  mov     rdi, [rsp+88h+var_58]
0x180015b9c  mov     rcx, rbx; lpCriticalSection
0x180015b9f  call    cs:__imp_LeaveCriticalSection
0x180015ba5  test    rdi, rdi
0x180015ba8  jz      loc_180015C56
0x180015bae  lea     rbx, [rsp+88h+var_58]
0x180015bb3  lea     rbp, WPP_GLOBAL_Control
0x180015bba  test    rbx, rbx
0x180015bbd  jz      short loc_180015C1B
0x180015bbf  mov     rax, [rbx]
0x180015bc2  test    rax, rax
0x180015bc5  jz      short loc_180015C1B
0x180015bc7  lea     rsi, [rax+8]
0x180015bcb  mov     rcx, rsi; this
0x180015bce  call    ?NotifyByeByeForAllAddressFamily@CSsdpCacheEntry@@QEAAJXZ; CSsdpCacheEntry::NotifyByeByeForAllAddressFamily(void)
0x180015bd3  test    eax, eax
0x180015bd5  jns     short loc_180015C01
0x180015bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bde  cmp     rcx, rbp
0x180015be1  jz      short loc_180015C01
0x180015be3  test    byte ptr [rcx+1Ch], 1
0x180015be7  jz      short loc_180015C01
0x180015be9  mov     rcx, [rcx+10h]
0x180015bed  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180015bf4  mov     edx, 4Bh ; 'K'
0x180015bf9  mov     r9d, eax
0x180015bfc  call    WPP_SF_d
0x180015c01  xor     edx, edx; int
0x180015c03  mov     rcx, rsi; this
0x180015c06  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x180015c0b  mov     rbx, [rbx]
0x180015c0e  mov     esi, eax
0x180015c10  test    rbx, rbx
0x180015c13  jz      short loc_180015C1B
0x180015c15  cmp     qword ptr [rbx], 0
0x180015c19  jnz     short loc_180015BBA
0x180015c1b  test    esi, esi
0x180015c1d  jz      short loc_180015C49
0x180015c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c26  cmp     rcx, rbp
0x180015c29  jz      short loc_180015C49
0x180015c2b  test    byte ptr [rcx+1Ch], 1
0x180015c2f  jz      short loc_180015C49
0x180015c31  mov     rcx, [rcx+10h]
0x180015c35  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180015c3c  mov     edx, 4Ch ; 'L'
0x180015c41  mov     r9d, esi
0x180015c44  call    WPP_SF_d
0x180015c49  test    rdi, rdi
0x180015c4c  jz      short loc_180015C56
0x180015c4e  mov     rcx, rdi; void *
0x180015c51  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x180015c56  mov     rbx, [rsp+88h+arg_8]
0x180015c5e  mov     eax, esi
0x180015c60  add     rsp, 50h
0x180015c64  pop     r15
0x180015c66  pop     r14
0x180015c68  pop     r13
0x180015c6a  pop     r12
0x180015c6c  pop     rdi
0x180015c6d  pop     rsi
0x180015c6e  pop     rbp
0x180015c6f  retn
```
