# SectionCache::GetSection(wchar_t const *)

- ea: `0x180037a04`
- end: `0x180037c3b`
- name: `?GetSection@SectionCache@@QEAA?AV?$unique_ptr@VRecordCache@@U?$default_delete@VRecordCache@@@utl@@@utl@@PEB_W@Z`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180036688`

## callees

- `0x180007180`
- `0x18000c374`
- `0x18002265c`
- `0x180023548`
- `0x180035f48`
- `0x1800369b0`
- `0x180037a04`
- `0x180037cac`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037c09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037c09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037c1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037c1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
RecordCache **__fastcall SectionCache::GetSection(__int64 a1, RecordCache **a2, __int64 a3)
{
  __int64 v5; // rdi
  __int64 v6; // rbx
  RecordCache *v7; // rax
  RecordCache *v8; // rbx
  __int64 v9; // rax
  RecordCache *v10; // rbx
  RTL_SRWLOCK *v11; // rdi
  unsigned __int64 v12; // rdx
  bool v13; // r8
  _QWORD v15[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+50h] [rbp-20h]
  int v18; // [rsp+58h] [rbp-18h]
  int v19; // [rsp+5Ch] [rbp-14h]
  int v20; // [rsp+60h] [rbp-10h]
  __int64 v21; // [rsp+A0h] [rbp+30h] BYREF

  v21 = a3;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 87);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = 87;
    v19 = -1;
    v20 = 549;
    throw (EvtException *)&pExceptionObject;
  }
  v5 = a1 + 1088;
  v6 = utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_FindImpl<wchar_t const *>(
         a1 + 1088,
         &v21);
  if ( v5 == v6 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1168);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = 1168;
    v19 = -1;
    v20 = 556;
    throw (EvtException *)&pExceptionObject;
  }
  v7 = (RecordCache *)MIDL_user_allocate(0x438u);
  v21 = (__int64)v7;
  if ( v7 )
    v8 = RecordCache::RecordCache(v7, *(_QWORD *)(v6 + 64), *(_QWORD *)(v6 + 72));
  else
    v8 = 0;
  *a2 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = 14;
    v19 = -1;
    v20 = 564;
    throw (EvtException *)&pExceptionObject;
  }
  v15[0] = *(_QWORD *)(a1 + 24);
  v15[1] = (__int64)(*(_QWORD *)(a1 + 32) - v15[0]) >> 1;
  v9 = MakeOrThrowOOM(&pExceptionObject, v15);
  RecordCache::OpenFile(v8, v9);
  v10 = *a2;
  v11 = (RTL_SRWLOCK *)((char *)*a2 + 64);
  v21 = (__int64)v11;
  AcquireSRWLockExclusive(v11);
  RecordCache::InternalSyncFileHeader(v10, v12, v13);
  ReleaseSRWLockExclusive(v11);
  return a2;
}

```

## disassembly

```asm
0x180037a04  mov     rax, rsp
0x180037a07  mov     [rax+8], rbx
0x180037a0b  mov     [rax+20h], rsi
0x180037a0f  mov     [rax+18h], r8
0x180037a13  mov     [rax+10h], rdx
0x180037a17  push    rbp
0x180037a18  push    rdi
0x180037a19  push    r14
0x180037a1b  mov     rbp, rsp
0x180037a1e  sub     rsp, 70h
0x180037a22  mov     rsi, rdx
0x180037a25  mov     r14, rcx
0x180037a28  mov     [rbp+var_50], 0
0x180037a2f  test    r8, r8
0x180037a32  jnz     short loc_180037A9F
0x180037a34  lea     rax, WPP_GLOBAL_Control
0x180037a3b  lea     ebx, [r8+57h]
0x180037a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a46  cmp     rcx, rax
0x180037a49  jz      short loc_180037A6D
0x180037a4b  test    byte ptr [rcx+1Ch], 1
0x180037a4f  jz      short loc_180037A6D
0x180037a51  cmp     byte ptr [rcx+19h], 2
0x180037a55  jb      short loc_180037A6D
0x180037a57  lea     edx, [rbx-3Dh]
0x180037a5a  mov     r9d, ebx
0x180037a5d  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037a64  mov     rcx, [rcx+10h]
0x180037a68  call    WPP_SF_D
0x180037a6d  xorps   xmm0, xmm0
0x180037a70  movdqu  [rbp+pExceptionObject], xmm0
0x180037a75  mov     [rbp+var_20], 0
0x180037a7d  mov     [rbp+var_18], ebx
0x180037a80  mov     [rbp+var_14], 0FFFFFFFFh
0x180037a87  mov     [rbp+var_10], 225h
0x180037a8e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037a95  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037a99  call    _CxxThrowException_0
0x180037a9f  lea     rdi, [rcx+440h]
0x180037aa6  lea     rdx, [rbp+arg_10]
0x180037aaa  mov     rcx, rdi
0x180037aad  call    ??$_FindImpl@PEB_W@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@AEBQEB_W@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_FindImpl<wchar_t const *>(wchar_t const * const &)
0x180037ab2  mov     rbx, rax
0x180037ab5  cmp     rdi, rax
0x180037ab8  jnz     short loc_180037B28
0x180037aba  lea     rax, WPP_GLOBAL_Control
0x180037ac1  mov     ebx, 490h
0x180037ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x180037acd  cmp     rcx, rax
0x180037ad0  jz      short loc_180037AF6
0x180037ad2  test    byte ptr [rcx+1Ch], 1
0x180037ad6  jz      short loc_180037AF6
0x180037ad8  cmp     byte ptr [rcx+19h], 2
0x180037adc  jb      short loc_180037AF6
0x180037ade  mov     edx, 1Bh
0x180037ae3  mov     r9d, ebx
0x180037ae6  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037aed  mov     rcx, [rcx+10h]
0x180037af1  call    WPP_SF_D
0x180037af6  xorps   xmm0, xmm0
0x180037af9  movdqu  [rbp+pExceptionObject], xmm0
0x180037afe  mov     [rbp+var_20], 0
0x180037b06  mov     [rbp+var_18], ebx
0x180037b09  mov     [rbp+var_14], 0FFFFFFFFh
0x180037b10  mov     [rbp+var_10], 22Ch
0x180037b17  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037b1e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037b22  call    _CxxThrowException_0
0x180037b28  mov     ecx, 438h; size
0x180037b2d  call    MIDL_user_allocate
0x180037b32  mov     [rbp+arg_10], rax
0x180037b36  test    rax, rax
0x180037b39  jz      short loc_180037B50
0x180037b3b  mov     r8, [rbx+48h]; unsigned __int64
0x180037b3f  mov     rdx, [rbx+40h]; unsigned __int64
0x180037b43  mov     rcx, rax; this
0x180037b46  call    ??0RecordCache@@QEAA@_K0@Z; RecordCache::RecordCache(unsigned __int64,unsigned __int64)
0x180037b4b  mov     rbx, rax
0x180037b4e  jmp     short loc_180037B52
0x180037b50  xor     ebx, ebx
0x180037b52  mov     [rsi], rbx
0x180037b55  mov     [rbp+var_50], 3
0x180037b5c  test    rbx, rbx
0x180037b5f  jnz     short loc_180037BCD
0x180037b61  lea     rax, WPP_GLOBAL_Control
0x180037b68  mov     ebx, 0Eh
0x180037b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b74  cmp     rcx, rax
0x180037b77  jz      short loc_180037B9B
0x180037b79  test    byte ptr [rcx+1Ch], 1
0x180037b7d  jz      short loc_180037B9B
0x180037b7f  cmp     byte ptr [rcx+19h], 2
0x180037b83  jb      short loc_180037B9B
0x180037b85  lea     edx, [rbx+0Eh]
0x180037b88  mov     r9d, ebx
0x180037b8b  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037b92  mov     rcx, [rcx+10h]
0x180037b96  call    WPP_SF_D
0x180037b9b  xorps   xmm0, xmm0
0x180037b9e  movdqu  [rbp+pExceptionObject], xmm0
0x180037ba3  mov     [rbp+var_20], 0
0x180037bab  mov     [rbp+var_18], ebx
0x180037bae  mov     [rbp+var_14], 0FFFFFFFFh
0x180037bb5  mov     [rbp+var_10], 234h
0x180037bbc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037bc3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037bc7  call    _CxxThrowException_0
0x180037bcd  mov     rax, [r14+18h]
0x180037bd1  mov     [rbp+var_40], rax
0x180037bd5  mov     rcx, [r14+20h]
0x180037bd9  sub     rcx, rax
0x180037bdc  sar     rcx, 1
0x180037bdf  mov     [rbp+var_38], rcx
0x180037be3  lea     rdx, [rbp+var_40]
0x180037be7  lea     rcx, [rbp+pExceptionObject]
0x180037beb  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180037bf0  mov     rdx, rax
0x180037bf3  mov     rcx, rbx; this
0x180037bf6  call    ?OpenFile@RecordCache@@QEAAXV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N1@Z; RecordCache::OpenFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,bool,bool)
0x180037bfb  mov     rbx, [rsi]
0x180037bfe  lea     rdi, [rbx+40h]
0x180037c02  mov     [rbp+arg_10], rdi
0x180037c06  mov     rcx, rdi; SRWLock
0x180037c09  call    cs:__imp_AcquireSRWLockExclusive
0x180037c0f  nop
0x180037c10  mov     rcx, rbx; this
0x180037c13  call    ?InternalSyncFileHeader@RecordCache@@AEAAX_K_N@Z; RecordCache::InternalSyncFileHeader(unsigned __int64,bool)
0x180037c18  nop
0x180037c19  mov     rcx, rdi; SRWLock
0x180037c1c  call    cs:__imp_ReleaseSRWLockExclusive
0x180037c22  mov     rax, rsi
0x180037c25  lea     r11, [rsp+70h+var_s0]
0x180037c2a  mov     rbx, [r11+20h]
0x180037c2e  mov     rsi, [r11+38h]
0x180037c32  mov     rsp, r11
0x180037c35  pop     r14
0x180037c37  pop     rdi
0x180037c38  pop     rbp
0x180037c39  retn
```
