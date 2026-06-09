# PublisherManager::OnPublisherCacheTimerExpired(void)

- ea: `0x180005b94`
- end: `0x180005d97`
- name: `?OnPublisherCacheTimerExpired@PublisherManager@@AEAAXXZ`
- size: `515`
- prototype: `void __fastcall(PublisherManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004ac0`

## callees

- `0x18000347c`
- `0x18000556c`
- `0x180005b94`
- `0x180006174`
- `0x1800061ec`
- `0x1800067a0`
- `0x180006f78`
- `0x180087c90`
- `0x1800880c4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d31`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005bc1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005bc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PublisherManager::OnPublisherCacheTimerExpired(PublisherManager *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  unsigned __int64 v4; // rsi
  struct _FILETIME *i; // rdi
  const struct _GUID **v6; // r14
  const struct _GUID *v7; // rax
  struct _FILETIME v8; // r10
  struct _FILETIME *v9; // rax
  struct _FILETIME *v10; // r9
  __int64 v11; // r11
  __int64 v12; // r8
  struct _FILETIME *v13; // rcx
  char v14[16]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v15; // [rsp+30h] [rbp-40h] BYREF
  __int64 v16; // [rsp+40h] [rbp-30h]
  struct _FILETIME v17; // [rsp+48h] [rbp-28h] BYREF
  struct _FILETIME *v18; // [rsp+50h] [rbp-20h]
  struct _FILETIME *v19; // [rsp+58h] [rbp-18h]
  __int64 v20; // [rsp+60h] [rbp-10h]
  struct _FILETIME pftDueTime; // [rsp+A0h] [rbp+30h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp+38h] BYREF
  PublisherManager *v23; // [rsp+B0h] [rbp+40h]

  v15 = 0;
  v16 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v23 = this;
  AcquireSRWLockExclusive((PSRWLOCK)this);
  if ( !*((_BYTE *)this + 120) )
  {
    utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(&v17);
    v4 = (unsigned __int64)this + 24;
    for ( i = (struct _FILETIME *)*((_QWORD *)this + 5);
          i != (struct _FILETIME *)v4;
          i = (struct _FILETIME *)utl::_TreeNodeHeader<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>::_Traverse(
                                    i,
                                    v2) )
    {
      pftDueTime = i[5];
      if ( *(_QWORD *)&pftDueTime < *(unsigned __int64 *)&SystemTimeAsFileTime )
      {
        if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&pftDueTime < 0x1B7740u )
        {
          utl::_Tree<_GUID,utl::pair<_GUID const,PublisherManager::PublisherCacheNode>,GuidLess,utl::allocator<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>,0>::_InsertImpl<utl::pair<_GUID const,PublisherManager::PublisherCacheNode> const &>(
            (unsigned __int64)&v17,
            (__int64)v14,
            v3,
            (__int64)&i[3]);
        }
        else
        {
          v6 = (const struct _GUID **)&i[6];
          if ( *((_QWORD *)&v15 + 1) == v16 )
          {
            std::vector<wmi::AutoRef<Publisher>>::_Emplace_reallocate<wmi::AutoRef<Publisher> const &>(
              &v15,
              *((_QWORD *)&v15 + 1),
              &i[6]);
          }
          else
          {
            v7 = *v6;
            **((_QWORD **)&v15 + 1) = *v6;
            if ( v7 )
              _InterlockedIncrement((volatile signed __int32 *)v7->Data4);
            *((_QWORD *)&v15 + 1) += 8LL;
          }
          PublisherManager::RemoveMigratedPublisherFromLegacyCache(this, *v6 + 9);
        }
      }
      LOBYTE(v2) = 1;
    }
    v8 = v17;
    v9 = v18;
    v10 = v19;
    v11 = v20;
    if ( *((PublisherManager **)this + 5) == (PublisherManager *)((char *)this + 24) )
    {
      v17 = (struct _FILETIME)&v17;
      v13 = &v17;
      v18 = &v17;
      v20 = 0;
    }
    else
    {
      v12 = *((_QWORD *)this + 6);
      *(_QWORD *)(*(_QWORD *)v4 & 0xFFFFFFFFFFFFFFFEuLL) = (char *)&v17 + 1;
      v17 = *(struct _FILETIME *)v4;
      v18 = (struct _FILETIME *)*((_QWORD *)this + 4);
      v13 = (struct _FILETIME *)*((_QWORD *)this + 5);
      v20 = v12;
    }
    v19 = v13;
    if ( v10 == &v17 )
    {
      *(_QWORD *)v4 = v4;
      *((_QWORD *)this + 4) = (char *)this + 24;
      *((_QWORD *)this + 5) = (char *)this + 24;
      *((_QWORD *)this + 6) = 0;
    }
    else
    {
      *(_QWORD *)(*(_QWORD *)&v8 & 0xFFFFFFFFFFFFFFFEuLL) = v4 | 1;
      *(struct _FILETIME *)v4 = v8;
      *((_QWORD *)this + 4) = v9;
      *((_QWORD *)this + 5) = v10;
      *((_QWORD *)this + 6) = v11;
      if ( v11 )
      {
        pftDueTime = (struct _FILETIME)-18000000000LL;
        SetThreadpoolTimer(*((PTP_TIMER *)this + 2), &pftDueTime, 0, 0);
LABEL_20:
        utl::_Tree<_GUID,utl::pair<_GUID const,PublisherManager::PublisherCacheNode>,GuidLess,utl::allocator<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>,0>::clear(&v17);
        goto LABEL_21;
      }
    }
    *((_BYTE *)this + 121) = 0;
    goto LABEL_20;
  }
LABEL_21:
  ReleaseSRWLockExclusive((PSRWLOCK)this);
  if ( (_QWORD)v15 )
  {
    std::_Destroy_range<std::allocator<wmi::AutoRef<Publisher>>>(v15, *((_QWORD *)&v15 + 1));
    std::_Deallocate<16>(v15, (v16 - v15) & 0xFFFFFFFFFFFFFFF8uLL);
  }
}

```

## disassembly

```asm
0x180005b94  push    rbp
0x180005b96  push    rbx
0x180005b97  push    rsi
0x180005b98  push    rdi
0x180005b99  push    r14
0x180005b9b  mov     rbp, rsp
0x180005b9e  sub     rsp, 70h
0x180005ba2  mov     rbx, rcx
0x180005ba5  xorps   xmm0, xmm0
0x180005ba8  movdqu  [rbp+var_40], xmm0
0x180005bad  mov     [rbp+var_30], 0
0x180005bb5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180005bbd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005bc1  call    cs:__imp_GetSystemTimeAsFileTime
0x180005bc7  mov     [rbp+arg_10], rbx
0x180005bcb  mov     rcx, rbx; SRWLock
0x180005bce  call    cs:__imp_AcquireSRWLockExclusive
0x180005bd4  nop
0x180005bd5  cmp     byte ptr [rbx+78h], 0
0x180005bd9  jnz     loc_180005D42
0x180005bdf  lea     rcx, [rbp+var_28]
0x180005be3  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(void)
0x180005be8  nop
0x180005be9  lea     rsi, [rbx+18h]
0x180005bed  mov     rdi, [rsi+10h]
0x180005bf1  cmp     rdi, rsi
0x180005bf4  jz      short loc_180005C65
0x180005bf6  lea     r9, [rdi+18h]
0x180005bfa  mov     eax, [r9+14h]
0x180005bfe  mov     [rbp+pftDueTime.dwHighDateTime], eax
0x180005c01  mov     eax, [r9+10h]
0x180005c05  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x180005c08  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005c0c  cmp     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x180005c10  jnb     short loc_180005C56
0x180005c12  sub     rax, qword ptr [rbp+pftDueTime.dwLowDateTime]
0x180005c16  cmp     rax, 1B7740h
0x180005c1c  jb      loc_180005CB8
0x180005c22  mov     rdx, qword ptr [rbp+var_40+8]
0x180005c26  lea     r14, [r9+18h]
0x180005c2a  cmp     rdx, [rbp+var_30]
0x180005c2e  jz      short loc_180005CAA
0x180005c30  mov     rax, [r14]
0x180005c33  mov     [rdx], rax
0x180005c36  test    rax, rax
0x180005c39  jz      short loc_180005C3F
0x180005c3b  lock inc dword ptr [rax+8]
0x180005c3f  add     qword ptr [rbp+var_40+8], 8
0x180005c44  mov     rdx, [r14]
0x180005c47  add     rdx, 90h; struct _GUID *
0x180005c4e  mov     rcx, rbx; this
0x180005c51  call    ?RemoveMigratedPublisherFromLegacyCache@PublisherManager@@AEAAXAEBU_GUID@@@Z; PublisherManager::RemoveMigratedPublisherFromLegacyCache(_GUID const &)
0x180005c56  mov     dl, 1
0x180005c58  mov     rcx, rdi
0x180005c5b  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>::_Traverse(bool)
0x180005c60  mov     rdi, rax
0x180005c63  jmp     short loc_180005BF1
0x180005c65  mov     r10, [rbp+var_28]
0x180005c69  mov     rax, [rbp+var_20]
0x180005c6d  mov     r9, [rbp+var_18]
0x180005c71  mov     r11, [rbp+var_10]
0x180005c75  cmp     [rsi+10h], rsi
0x180005c79  jz      short loc_180005CC7
0x180005c7b  mov     r8, [rsi+18h]
0x180005c7f  lea     rdx, [rbp+var_28]
0x180005c83  or      rdx, 1
0x180005c87  mov     rcx, [rsi]
0x180005c8a  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180005c8e  mov     [rcx], rdx
0x180005c91  mov     rcx, [rsi]
0x180005c94  mov     [rbp+var_28], rcx
0x180005c98  mov     rcx, [rsi+8]
0x180005c9c  mov     [rbp+var_20], rcx
0x180005ca0  mov     rcx, [rsi+10h]
0x180005ca4  mov     [rbp+var_10], r8
0x180005ca8  jmp     short loc_180005CDF
0x180005caa  mov     r8, r14
0x180005cad  lea     rcx, [rbp+var_40]
0x180005cb1  call    ??$_Emplace_reallocate@AEBV?$AutoRef@VPublisher@@@wmi@@@?$vector@V?$AutoRef@VPublisher@@@wmi@@V?$allocator@V?$AutoRef@VPublisher@@@wmi@@@std@@@std@@AEAAPEAV?$AutoRef@VPublisher@@@wmi@@QEAV23@AEBV23@@Z; std::vector<wmi::AutoRef<Publisher>>::_Emplace_reallocate<wmi::AutoRef<Publisher> const &>(wmi::AutoRef<Publisher> * const,wmi::AutoRef<Publisher> const &)
0x180005cb6  jmp     short loc_180005C44
0x180005cb8  lea     rdx, [rbp+var_50]
0x180005cbc  lea     rcx, [rbp+var_28]
0x180005cc0  call    ??$_InsertImpl@AEBU?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@VGuidLess@@V?$allocator@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@@3@$0A@@utl@@AEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@@utl@@_N@1@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@@1@AEBU?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@1@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,PublisherManager::PublisherCacheNode>,GuidLess,utl::allocator<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>,0>::_InsertImpl<utl::pair<_GUID const,PublisherManager::PublisherCacheNode> const &>(utl::_TreeNode<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>> *,utl::pair<_GUID const,PublisherManager::PublisherCacheNode> const &)
0x180005cc5  jmp     short loc_180005C56
0x180005cc7  lea     rcx, [rbp+var_28]
0x180005ccb  mov     [rbp+var_28], rcx
0x180005ccf  lea     rcx, [rbp+var_28]
0x180005cd3  mov     [rbp+var_20], rcx
0x180005cd7  mov     [rbp+var_10], 0
0x180005cdf  mov     [rbp+var_18], rcx
0x180005ce3  lea     rcx, [rbp+var_28]
0x180005ce7  cmp     r9, rcx
0x180005cea  jz      loc_180005D7D
0x180005cf0  mov     rdx, rsi
0x180005cf3  or      rdx, 1
0x180005cf7  mov     rcx, r10
0x180005cfa  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180005cfe  mov     [rcx], rdx
0x180005d01  mov     [rsi], r10
0x180005d04  mov     [rsi+8], rax
0x180005d08  mov     [rsi+10h], r9
0x180005d0c  mov     [rsi+18h], r11
0x180005d10  test    r11, r11
0x180005d13  jz      short loc_180005D90
0x180005d15  mov     rax, 0FFFFFFFBCF1DCC00h
0x180005d1f  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x180005d23  xor     r9d, r9d; msWindowLength
0x180005d26  xor     r8d, r8d; msPeriod
0x180005d29  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x180005d2d  mov     rcx, [rbx+10h]; pti
0x180005d31  call    cs:__imp_SetThreadpoolTimer
0x180005d37  nop
0x180005d38  lea     rcx, [rbp+var_28]
0x180005d3c  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@VGuidLess@@V?$allocator@U?$pair@$$CBU_GUID@@UPublisherCacheNode@PublisherManager@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,PublisherManager::PublisherCacheNode>,GuidLess,utl::allocator<utl::pair<_GUID const,PublisherManager::PublisherCacheNode>>,0>::clear(void)
0x180005d41  nop
0x180005d42  mov     rcx, rbx; SRWLock
0x180005d45  call    cs:__imp_ReleaseSRWLockExclusive
0x180005d4b  nop
0x180005d4c  mov     rcx, qword ptr [rbp+var_40]
0x180005d50  test    rcx, rcx
0x180005d53  jz      short loc_180005D72
0x180005d55  mov     rdx, qword ptr [rbp+var_40+8]
0x180005d59  call    ??$_Destroy_range@V?$allocator@V?$AutoRef@VPublisher@@@wmi@@@std@@@std@@YAXPEAV?$AutoRef@VPublisher@@@wmi@@QEAV12@AEAV?$allocator@V?$AutoRef@VPublisher@@@wmi@@@0@@Z; std::_Destroy_range<std::allocator<wmi::AutoRef<Publisher>>>(wmi::AutoRef<Publisher> *,wmi::AutoRef<Publisher> * const,std::allocator<wmi::AutoRef<Publisher>> &)
0x180005d5e  mov     rcx, qword ptr [rbp+var_40]
0x180005d62  mov     rdx, [rbp+var_30]
0x180005d66  sub     rdx, rcx
0x180005d69  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180005d6d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180005d72  add     rsp, 70h
0x180005d76  pop     r14
0x180005d78  pop     rdi
0x180005d79  pop     rsi
0x180005d7a  pop     rbx
0x180005d7b  pop     rbp
0x180005d7c  retn
0x180005d7d  mov     [rsi], rsi
0x180005d80  mov     [rsi+8], rsi
0x180005d84  mov     [rsi+10h], rsi
0x180005d88  mov     qword ptr [rsi+18h], 0
0x180005d90  mov     byte ptr [rbx+79h], 0
0x180005d94  jmp     short loc_180005D38
```
