# CSsdpCacheEntryManager::HrRemoveOldCacheEntry(char *,ulong,_GUID,unsigned __int64)

- ea: `0x18000bdd4`
- end: `0x18000bf89`
- name: `?HrRemoveOldCacheEntry@CSsdpCacheEntryManager@@QEAAJPEADKU_GUID@@_K@Z`
- size: `437`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, char *Str1@<rdx>, unsigned int@<r8d>, struct _GUID *__struct_ptr@<r9>, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800168d0`

## callees

- `0x18000aef4`
- `0x18000bad0`
- `0x18000bbf0`
- `0x18000bd3c`
- `0x18000bdd4`
- `0x180019920`
- `0x18001a1b0`
- `0x18001c374`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000beb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000beb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bdff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bdff`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrRemoveOldCacheEntry(
        LPCRITICAL_SECTION lpCriticalSection,
        HashFn *Str1,
        unsigned int a3,
        struct _GUID *a4,
        unsigned __int64 a5)
{
  void *v5; // rdi
  unsigned int v9; // esi
  const char *v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // eax
  _QWORD *p_DebugInfo; // r10
  unsigned __int64 v14; // r15
  unsigned int v15; // r12d
  __int64 v16; // rax
  __int64 v17; // rbp
  _QWORD *v18; // rbx
  _QWORD *v19; // rax
  CSsdpCacheEntry *v20; // rsi
  int v21; // eax
  unsigned int v22; // eax
  _QWORD v24[2]; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v25; // [rsp+40h] [rbp-48h] BYREF
  LPCRITICAL_SECTION v26; // [rsp+90h] [rbp+8h] BYREF
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
    while ( p_DebugInfo )
    {
      v16 = *p_DebugInfo;
      if ( !*p_DebugInfo )
        break;
      v17 = v16 + 8;
      v25 = *a4;
      if ( (unsigned int)CSsdpCacheEntry::FIsSearchMatchHash(
                           (CSsdpCacheEntry *)(v16 + 8),
                           (const char *)Str1,
                           v27,
                           &v25,
                           v15)
        && *(_QWORD *)(v17 + 264) < v14 )
      {
        CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(&v26, v24);
        --lpCriticalSection[1].LockCount;
        v5 = (void *)v24[0];
        break;
      }
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext(&v26) )
        break;
      p_DebugInfo = &v26->DebugInfo;
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
0x18000bdd4  mov     [rsp+arg_8], rbx
0x18000bdd9  mov     [rsp+arg_10], r8d
0x18000bdde  push    rbp
0x18000bddf  push    rsi
0x18000bde0  push    rdi
0x18000bde1  push    r12
0x18000bde3  push    r13
0x18000bde5  push    r14
0x18000bde7  push    r15
0x18000bde9  sub     rsp, 50h
0x18000bded  xor     edi, edi
0x18000bdef  mov     r13, r9
0x18000bdf2  mov     [rsp+88h+var_58], rdi
0x18000bdf7  mov     r14, rdx
0x18000bdfa  mov     rbx, rcx
0x18000bdfd  xor     esi, esi
0x18000bdff  call    cs:__imp_EnterCriticalSection
0x18000be06  nop     dword ptr [rax+rax+00h]
0x18000be0b  lea     r10, [rbx+28h]
0x18000be0f  mov     [rsp+88h+arg_0], r10
0x18000be17  cmp     [r10], rsi
0x18000be1a  jz      loc_18000BEAE
0x18000be20  mov     rcx, r14; this
0x18000be23  call    ?HashString@HashFn@@YAKPEBDK@Z; HashFn::HashString(char const *,ulong)
0x18000be28  mov     r15, [rsp+88h+arg_20]
0x18000be30  mov     r12d, eax
0x18000be33  test    r10, r10
0x18000be36  jz      short loc_18000BEAE
0x18000be38  mov     rax, [r10]
0x18000be3b  test    rax, rax
0x18000be3e  jz      short loc_18000BEAE
0x18000be40  movaps  xmm0, xmmword ptr [r13+0]
0x18000be45  lea     rbp, [rax+8]
0x18000be49  mov     r8d, [rsp+88h+arg_10]; unsigned int
0x18000be51  lea     r9, [rsp+88h+var_48]; struct _GUID
0x18000be56  mov     rcx, rbp; this
0x18000be59  movdqa  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x18000be5f  mov     rdx, r14; Str1
0x18000be62  mov     [rsp+88h+var_68], r12d; unsigned int
0x18000be67  call    ?FIsSearchMatchHash@CSsdpCacheEntry@@QEAAHPEBDKU_GUID@@K@Z; CSsdpCacheEntry::FIsSearchMatchHash(char const *,ulong,_GUID,ulong)
0x18000be6c  test    eax, eax
0x18000be6e  jz      short loc_18000BE79
0x18000be70  cmp     [rbp+108h], r15
0x18000be77  jb      short loc_18000BE94
0x18000be79  lea     rcx, [rsp+88h+arg_0]
0x18000be81  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18000be86  test    eax, eax
0x18000be88  jnz     short loc_18000BEAE
0x18000be8a  mov     r10, [rsp+88h+arg_0]
0x18000be92  jmp     short loc_18000BE33
0x18000be94  lea     rdx, [rsp+88h+var_58]
0x18000be99  lea     rcx, [rsp+88h+arg_0]
0x18000bea1  call    ?HrMoveToList@Iterator@?$CUList@VCSsdpCacheEntry@@@@QEAAJAEAV2@@Z; CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(CUList<CSsdpCacheEntry> &)
0x18000bea6  dec     dword ptr [rbx+30h]
0x18000bea9  mov     rdi, [rsp+88h+var_58]
0x18000beae  mov     rcx, rbx; lpCriticalSection
0x18000beb1  call    cs:__imp_LeaveCriticalSection
0x18000beb8  nop     dword ptr [rax+rax+00h]
0x18000bebd  test    rdi, rdi
0x18000bec0  jz      loc_18000BF6E
0x18000bec6  lea     rbx, [rsp+88h+var_58]
0x18000becb  lea     rbp, WPP_GLOBAL_Control
0x18000bed2  test    rbx, rbx
0x18000bed5  jz      short loc_18000BF33
0x18000bed7  mov     rax, [rbx]
0x18000beda  test    rax, rax
0x18000bedd  jz      short loc_18000BF33
0x18000bedf  lea     rsi, [rax+8]
0x18000bee3  mov     rcx, rsi; this
0x18000bee6  call    ?NotifyByeByeForAllAddressFamily@CSsdpCacheEntry@@QEAAJXZ; CSsdpCacheEntry::NotifyByeByeForAllAddressFamily(void)
0x18000beeb  test    eax, eax
0x18000beed  jns     short loc_18000BF19
0x18000beef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bef6  cmp     rcx, rbp
0x18000bef9  jz      short loc_18000BF19
0x18000befb  test    byte ptr [rcx+1Ch], 1
0x18000beff  jz      short loc_18000BF19
0x18000bf01  mov     rcx, [rcx+10h]
0x18000bf05  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000bf0c  mov     edx, 4Bh ; 'K'
0x18000bf11  mov     r9d, eax
0x18000bf14  call    WPP_SF_d
0x18000bf19  xor     edx, edx; int
0x18000bf1b  mov     rcx, rsi; this
0x18000bf1e  call    ?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::HrShutdown(int)
0x18000bf23  mov     rbx, [rbx]
0x18000bf26  mov     esi, eax
0x18000bf28  test    rbx, rbx
0x18000bf2b  jz      short loc_18000BF33
0x18000bf2d  cmp     qword ptr [rbx], 0
0x18000bf31  jnz     short loc_18000BED2
0x18000bf33  test    esi, esi
0x18000bf35  jz      short loc_18000BF61
0x18000bf37  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf3e  cmp     rcx, rbp
0x18000bf41  jz      short loc_18000BF61
0x18000bf43  test    byte ptr [rcx+1Ch], 1
0x18000bf47  jz      short loc_18000BF61
0x18000bf49  mov     rcx, [rcx+10h]
0x18000bf4d  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000bf54  mov     edx, 4Ch ; 'L'
0x18000bf59  mov     r9d, esi
0x18000bf5c  call    WPP_SF_d
0x18000bf61  test    rdi, rdi
0x18000bf64  jz      short loc_18000BF6E
0x18000bf66  mov     rcx, rdi; void *
0x18000bf69  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x18000bf6e  mov     rbx, [rsp+88h+arg_8]
0x18000bf76  mov     eax, esi
0x18000bf78  add     rsp, 50h
0x18000bf7c  pop     r15
0x18000bf7e  pop     r14
0x18000bf80  pop     r13
0x18000bf82  pop     r12
0x18000bf84  pop     rdi
0x18000bf85  pop     rsi
0x18000bf86  pop     rbp
0x18000bf87  retn
```
