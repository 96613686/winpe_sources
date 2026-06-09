# p9fs::ShareList::Remove(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180027198`
- end: `0x18002735c`
- name: `?Remove@ShareList@p9fs@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x180027370`

## callees

- `0x180004534`
- `0x180004c5c`
- `0x18000c208`
- `0x18001c0c8`
- `0x180023b00`
- `0x180023e54`
- `0x180027198`
- `0x180027cb0`
- `0x180028804`
- `0x180028818`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800272eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800272eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800271b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800271b5`

## string_xrefs

- `0x18002734a`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall p9fs::ShareList::Remove(RTL_SRWLOCK *a1, size_t *a2)
{
  RTL_SRWLOCK *v4; // r14
  _QWORD *v5; // rbx
  _QWORD *v6; // rdx
  size_t v7; // rbp
  const void *v8; // rcx
  size_t v9; // r8
  int v10; // eax
  __int64 **v11; // rcx
  _QWORD *v12; // rdx
  __int64 i; // rax
  __int64 *j; // rcx
  _QWORD *v15; // rdi
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdx
  char *v19; // [rsp+28h] [rbp-70h]
  _QWORD v20[2]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v21[16]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v22; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = a1 + 1;
  AcquireSRWLockExclusive(a1 + 1);
  v20[1] = v4;
  std::_Tree<std::_Tmap_traits<std::string,std::shared_ptr<p9fs::Share>,std::less<void>,std::allocator<std::pair<std::string const,std::shared_ptr<p9fs::Share>>>,0>>::_Find_lower_bound<std::string>(
    &a1[2],
    v21,
    a2);
  v5 = (_QWORD *)v22;
  if ( *(_BYTE *)(v22 + 25) )
    goto LABEL_31;
  v6 = (_QWORD *)(v22 + 32);
  v7 = *(_QWORD *)(v22 + 48);
  if ( *(_QWORD *)(v22 + 56) > 0xFu )
    v6 = (_QWORD *)*v6;
  if ( a2[3] <= 0xF )
    v8 = a2;
  else
    v8 = (const void *)*a2;
  v9 = a2[2];
  if ( v7 < v9 )
    v9 = *(_QWORD *)(v22 + 48);
  v10 = memcmp_0(v8, v6, v9);
  if ( v10 )
  {
    if ( v10 < 0 )
      goto LABEL_31;
  }
  else if ( a2[2] < v7 )
  {
    goto LABEL_31;
  }
  if ( v5 == a1[2].Ptr )
  {
LABEL_31:
    v17 = std::string::data(a2);
    v20[0] = std::string::size(a2, v17);
    LODWORD(v19) = gsl::narrow_cast<int,unsigned __int64>(v20);
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x187,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
      (const char *)2,
      (unsigned int)"%.*hs",
      v19,
      v18);
  }
  if ( (*(_DWORD *)(v5[8] + 8LL) & 0x140) != 0 )
    --a1[4].Ptr;
  v11 = (__int64 **)v5[2];
  v12 = v5;
  if ( *((_BYTE *)v11 + 25) )
  {
    for ( i = v5[1]; !*(_BYTE *)(i + 25) && v5 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
      v5 = (_QWORD *)i;
  }
  else
  {
    for ( j = *v11; !*((_BYTE *)j + 25); j = (__int64 *)*j )
      ;
  }
  v15 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<p9fs::Fid>>>>::_Extract(
                    &a1[2],
                    v12);
  v16 = (volatile signed __int32 *)v15[9];
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  std::string::~string(v15 + 4);
  operator delete(v15, 0x50u);
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
}

```

## disassembly

```asm
0x180027198  mov     [rsp+arg_10], rbx
0x18002719d  push    rbp
0x18002719e  push    rsi
0x18002719f  push    rdi
0x1800271a0  push    r14
0x1800271a2  push    r15
0x1800271a4  sub     rsp, 70h
0x1800271a8  mov     rdi, rdx
0x1800271ab  mov     rsi, rcx
0x1800271ae  lea     r14, [rcx+8]
0x1800271b2  mov     rcx, r14; SRWLock
0x1800271b5  call    cs:__imp_AcquireSRWLockExclusive
0x1800271bb  mov     [rsp+98h+var_50], r14
0x1800271c0  lea     r15, [rsi+10h]
0x1800271c4  mov     r8, rdi
0x1800271c7  lea     rdx, [rsp+98h+var_48]
0x1800271cc  mov     rcx, r15
0x1800271cf  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,std::shared_ptr<p9fs::Share>,std::less<void>,std::allocator<std::pair<std::string const,std::shared_ptr<p9fs::Share>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x1800271d4  mov     rbx, [rsp+98h+var_38]
0x1800271d9  cmp     byte ptr [rbx+19h], 0
0x1800271dd  jnz     loc_180027305
0x1800271e3  lea     rdx, [rbx+20h]
0x1800271e7  mov     rbp, [rdx+10h]
0x1800271eb  cmp     qword ptr [rdx+18h], 0Fh
0x1800271f0  jbe     short loc_1800271F5
0x1800271f2  mov     rdx, [rdx]; Buf2
0x1800271f5  cmp     qword ptr [rdi+18h], 0Fh
0x1800271fa  jbe     short loc_180027201
0x1800271fc  mov     rcx, [rdi]
0x1800271ff  jmp     short loc_180027204
0x180027201  mov     rcx, rdi; Buf1
0x180027204  mov     r8, [rdi+10h]
0x180027208  cmp     rbp, r8
0x18002720b  cmovb   r8, rbp; Size
0x18002720f  call    memcmp_0
0x180027214  test    eax, eax
0x180027216  jz      short loc_180027220
0x180027218  js      loc_180027305
0x18002721e  jmp     short loc_18002722A
0x180027220  cmp     [rdi+10h], rbp
0x180027224  jb      loc_180027305
0x18002722a  cmp     rbx, [r15]
0x18002722d  jz      loc_180027305
0x180027233  mov     rax, [rbx+40h]
0x180027237  test    dword ptr [rax+8], 140h
0x18002723e  jz      short loc_180027244
0x180027240  dec     qword ptr [rsi+20h]
0x180027244  mov     rcx, [rbx+10h]
0x180027248  mov     rdx, rbx
0x18002724b  cmp     byte ptr [rcx+19h], 0
0x18002724f  jz      short loc_18002726C
0x180027251  mov     rax, [rbx+8]
0x180027255  jmp     short loc_180027264
0x180027257  cmp     rbx, [rax+10h]
0x18002725b  jnz     short loc_180027281
0x18002725d  mov     rbx, rax
0x180027260  mov     rax, [rax+8]
0x180027264  cmp     byte ptr [rax+19h], 0
0x180027268  jz      short loc_180027257
0x18002726a  jmp     short loc_180027281
0x18002726c  mov     rcx, [rcx]
0x18002726f  cmp     byte ptr [rcx+19h], 0
0x180027273  jnz     short loc_180027281
0x180027275  mov     rax, [rcx]
0x180027278  mov     rcx, rax
0x18002727b  cmp     byte ptr [rax+19h], 0
0x18002727f  jz      short loc_180027275
0x180027281  mov     rcx, r15
0x180027284  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<p9fs::Fid>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<p9fs::Fid>>>>,std::_Iterator_base0>)
0x180027289  mov     rdi, rax
0x18002728c  mov     rbx, [rax+48h]
0x180027290  test    rbx, rbx
0x180027293  jz      short loc_1800272CC
0x180027295  or      ecx, 0FFFFFFFFh
0x180027298  lock xadd [rbx+8], ecx
0x18002729d  cmp     ecx, 1
0x1800272a0  jnz     short loc_1800272CC
0x1800272a2  mov     rdx, [rbx]
0x1800272a5  mov     rcx, rbx
0x1800272a8  mov     rax, [rdx]
0x1800272ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272b0  or      eax, 0FFFFFFFFh
0x1800272b3  lock xadd [rbx+0Ch], eax
0x1800272b8  cmp     eax, 1
0x1800272bb  jnz     short loc_1800272CC
0x1800272bd  mov     rax, [rbx]
0x1800272c0  mov     rcx, rbx
0x1800272c3  mov     rax, [rax+8]
0x1800272c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272cc  lea     rcx, [rdi+20h]
0x1800272d0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800272d5  mov     edx, 50h ; 'P'; unsigned __int64
0x1800272da  mov     rcx, rdi; void *
0x1800272dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800272e2  nop
0x1800272e3  test    r14, r14
0x1800272e6  jz      short loc_1800272F1
0x1800272e8  mov     rcx, r14; SRWLock
0x1800272eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800272f1  mov     rbx, [rsp+98h+arg_10]
0x1800272f9  add     rsp, 70h
0x1800272fd  pop     r15
0x1800272ff  pop     r14
0x180027301  pop     rdi
0x180027302  pop     rsi
0x180027303  pop     rbp
0x180027304  retn
0x180027305  mov     rcx, rdi
0x180027308  call    ?data@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::data(void)
0x18002730d  mov     rdx, rax
0x180027310  mov     rcx, rdi
0x180027313  call    ?size@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KXZ; std::string::size(void)
0x180027318  mov     [rsp+98h+var_58], rax
0x18002731d  lea     rcx, [rsp+98h+var_58]
0x180027322  call    ??$narrow_cast@H_K@gsl@@YAH$$QEA_K@Z; gsl::narrow_cast<int,unsigned __int64>(unsigned __int64 &&)
0x180027327  mov     rcx, [rsp+98h]; this
0x18002732f  mov     [rsp+98h+var_68], rdx
0x180027334  mov     dword ptr [rsp+98h+var_70], eax; char *
0x180027338  lea     rax, aHs; "%.*hs"
0x18002733f  mov     qword ptr [rsp+98h+var_78], rax; unsigned int
0x180027344  mov     r9d, 2; char *
0x18002734a  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180027351  mov     edx, 187h; void *
0x180027356  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
