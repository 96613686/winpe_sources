# p9fs::ShareList::Add(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,Schema::VirtualMachines::Resources::Storage::Plan9ShareFlags)

- ea: `0x180024af0`
- end: `0x180024dab`
- name: `?Add@ShareList@p9fs@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@W4Plan9ShareFlags@Storage@Resources@VirtualMachines@Schema@@@Z`
- size: `699`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x180024e50`
- `0x180024f90`

## callees

- `0x180004120`
- `0x180004144`
- `0x180004c5c`
- `0x18001c52c`
- `0x18001c77c`
- `0x180023b00`
- `0x180023e54`
- `0x180023e60`
- `0x1800243b0`
- `0x180024af0`
- `0x180027cb0`
- `0x180028804`
- `0x180028818`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024cdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024cdf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024bd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024bd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024bb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ba9`

## string_xrefs

- `0x180024d99`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall p9fs::ShareList::Add(RTL_SRWLOCK *a1, size_t *a2, __int64 *a3, int a4)
{
  int v4; // ebx
  _DWORD *v8; // rax
  char *v9; // rdi
  __int64 v10; // r12
  void *v11; // rsi
  DWORD LastError; // ebx
  _QWORD *v13; // rdx
  size_t v14; // rbx
  const void *v15; // rcx
  size_t v16; // r8
  int v17; // eax
  PVOID Ptr; // rdi
  _OWORD *v19; // rsi
  volatile signed __int32 *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  char *v23; // [rsp+28h] [rbp-51h]
  _QWORD v25[3]; // [rsp+48h] [rbp-31h] BYREF
  __int128 v26; // [rsp+60h] [rbp-19h] BYREF
  __int128 v27; // [rsp+70h] [rbp-9h] BYREF
  __int64 v28; // [rsp+80h] [rbp+7h]
  __int128 v29; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = a4;
  v8 = operator new(0x40u);
  v25[0] = v8;
  *(_OWORD *)v8 = 0;
  v8[2] = 1;
  v8[3] = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<p9fs::Share>::`vftable';
  v9 = (char *)(v8 + 4);
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)v8 + 2) = -1;
  *((_QWORD *)v8 + 4) = 0;
  *((_QWORD *)v8 + 5) = 0;
  *((_QWORD *)v8 + 6) = 0;
  *((_QWORD *)v8 + 7) = 0;
  *(_QWORD *)&v29 = v8 + 4;
  *((_QWORD *)&v29 + 1) = v8;
  if ( v8 + 4 != (_DWORD *)a3 )
  {
    v10 = *a3;
    v11 = *(void **)v9;
    if ( (unsigned __int64)(*(_QWORD *)v9 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v11);
      SetLastError(LastError);
      v4 = a4;
    }
    *(_QWORD *)v9 = v10;
    *a3 = -1;
    v9 = (char *)v29;
  }
  *((_DWORD *)v9 + 2) = v4;
  AcquireSRWLockExclusive(a1 + 1);
  *(_QWORD *)&v26 = a1 + 1;
  std::_Tree<std::_Tmap_traits<std::string,std::shared_ptr<p9fs::Share>,std::less<void>,std::allocator<std::pair<std::string const,std::shared_ptr<p9fs::Share>>>,0>>::_Find_lower_bound<std::string>(
    &a1[2],
    &v27,
    a2);
  if ( !*(_BYTE *)(v28 + 25) )
  {
    v13 = (_QWORD *)(v28 + 32);
    v14 = *(_QWORD *)(v28 + 48);
    if ( *(_QWORD *)(v28 + 56) > 0xFu )
      v13 = (_QWORD *)*v13;
    if ( a2[3] <= 0xF )
      v15 = a2;
    else
      v15 = (const void *)*a2;
    v16 = a2[2];
    if ( v14 < v16 )
      v16 = *(_QWORD *)(v28 + 48);
    v17 = memcmp_0(v15, v13, v16);
    if ( !v17 )
    {
      if ( a2[2] < v14 )
        goto LABEL_15;
LABEL_28:
      v21 = std::string::data(a2);
      v25[0] = std::string::size(a2, v21);
      LODWORD(v23) = gsl::narrow_cast<int,unsigned __int64>(v25);
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x178,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
        (const char *)0xB7,
        (unsigned int)"%.*hs",
        v23,
        v22);
    }
    if ( v17 >= 0 )
      goto LABEL_28;
  }
LABEL_15:
  if ( a1[3].Ptr == (PVOID)0x333333333333333LL )
    std::_Throw_tree_length_error();
  Ptr = a1[2].Ptr;
  v25[0] = a1 + 2;
  v19 = operator new(0x50u);
  std::string::string(v19 + 2, a2);
  v19[4] = v29;
  v29 = 0;
  *(_QWORD *)v19 = Ptr;
  *((_QWORD *)v19 + 1) = Ptr;
  *((_QWORD *)v19 + 2) = Ptr;
  *((_WORD *)v19 + 12) = 0;
  v25[1] = 0;
  std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<p9fs::Share>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<p9fs::Share>>,void *>>>(v25);
  v26 = v27;
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<p9fs::Fid>>>>::_Insert_node(
    &a1[2],
    &v26,
    v19);
  if ( (a4 & 0x140) != 0 )
    ++a1[4].Ptr;
  if ( a1 != (RTL_SRWLOCK *)-8LL )
    ReleaseSRWLockExclusive(a1 + 1);
  v20 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
  if ( *((_QWORD *)&v29 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
    if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
  }
}

```

## disassembly

```asm
0x180024af0  mov     [rsp-8+arg_18], rbx
0x180024af5  push    rbp
0x180024af6  push    rsi
0x180024af7  push    rdi
0x180024af8  push    r12
0x180024afa  push    r13
0x180024afc  push    r14
0x180024afe  push    r15
0x180024b00  lea     rbp, [rsp-27h]
0x180024b05  sub     rsp, 0A0h
0x180024b0c  mov     rax, cs:__security_cookie
0x180024b13  xor     rax, rsp
0x180024b16  mov     [rbp+57h+var_38], rax
0x180024b1a  mov     ebx, r9d
0x180024b1d  mov     [rbp+57h+var_90], ebx
0x180024b20  mov     r15, r8
0x180024b23  mov     r14, rdx
0x180024b26  mov     r13, rcx
0x180024b29  xor     esi, esi
0x180024b2b  xorps   xmm0, xmm0
0x180024b2e  movups  [rbp+57h+var_48], xmm0
0x180024b32  lea     ecx, [rsi+40h]; Size
0x180024b35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024b3a  mov     [rbp+57h+var_88], rax
0x180024b3e  xorps   xmm0, xmm0
0x180024b41  movups  xmmword ptr [rax], xmm0
0x180024b44  mov     dword ptr [rax+8], 1
0x180024b4b  mov     dword ptr [rax+0Ch], 1
0x180024b52  lea     rcx, ??_7?$_Ref_count_obj2@UShare@p9fs@@@std@@6B@; const std::_Ref_count_obj2<p9fs::Share>::`vftable'
0x180024b59  mov     [rax], rcx
0x180024b5c  lea     rdi, [rax+10h]
0x180024b60  mov     [rdi+8], rsi
0x180024b64  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180024b6b  xor     ecx, ecx
0x180024b6d  mov     [rdi+10h], rcx
0x180024b71  mov     [rdi+18h], rsi
0x180024b75  mov     [rdi+20h], rsi
0x180024b79  mov     [rdi+28h], rsi
0x180024b7d  movups  [rbp+57h+var_48], xmm0
0x180024b81  mov     qword ptr [rbp+57h+var_48], rdi
0x180024b85  mov     qword ptr [rbp+57h+var_48+8], rax
0x180024b89  cmp     rdi, r15
0x180024b8c  jz      short loc_180024BCA
0x180024b8e  mov     r12, [r15]
0x180024b91  mov     rsi, [rdi]
0x180024b94  lea     rax, [rsi-1]
0x180024b98  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024b9c  ja      short loc_180024BBA
0x180024b9e  call    cs:__imp_GetLastError
0x180024ba4  mov     ebx, eax
0x180024ba6  mov     rcx, rsi; hObject
0x180024ba9  call    cs:__imp_CloseHandle
0x180024baf  mov     ecx, ebx; dwErrCode
0x180024bb1  call    cs:__imp_SetLastError
0x180024bb7  mov     ebx, [rbp+57h+var_90]
0x180024bba  mov     [rdi], r12
0x180024bbd  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180024bc4  mov     rdi, qword ptr [rbp+57h+var_48]
0x180024bc8  xor     esi, esi
0x180024bca  mov     [rdi+8], ebx
0x180024bcd  lea     r15, [r13+8]
0x180024bd1  mov     rcx, r15; SRWLock
0x180024bd4  call    cs:__imp_AcquireSRWLockExclusive
0x180024bda  mov     qword ptr [rbp+57h+var_70], r15
0x180024bde  lea     r12, [r13+10h]
0x180024be2  mov     r8, r14
0x180024be5  lea     rdx, [rbp+57h+var_60]
0x180024be9  mov     rcx, r12
0x180024bec  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,std::shared_ptr<p9fs::Share>,std::less<void>,std::allocator<std::pair<std::string const,std::shared_ptr<p9fs::Share>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x180024bf1  mov     rdx, [rbp+57h+var_50]
0x180024bf5  cmp     [rdx+19h], sil
0x180024bf9  jnz     short loc_180024C3E
0x180024bfb  add     rdx, 20h ; ' '
0x180024bff  mov     rbx, [rdx+10h]
0x180024c03  cmp     qword ptr [rdx+18h], 0Fh
0x180024c08  jbe     short loc_180024C0D
0x180024c0a  mov     rdx, [rdx]; Buf2
0x180024c0d  cmp     qword ptr [r14+18h], 0Fh
0x180024c12  jbe     short loc_180024C19
0x180024c14  mov     rcx, [r14]
0x180024c17  jmp     short loc_180024C1C
0x180024c19  mov     rcx, r14; Buf1
0x180024c1c  mov     r8, [r14+10h]
0x180024c20  cmp     rbx, r8
0x180024c23  cmovb   r8, rbx; Size
0x180024c27  call    memcmp_0
0x180024c2c  test    eax, eax
0x180024c2e  jnz     loc_180024D4D
0x180024c34  cmp     [r14+10h], rbx
0x180024c38  jnb     loc_180024D5A
0x180024c3e  mov     rax, 333333333333333h
0x180024c48  cmp     [r12+8], rax
0x180024c4d  jz      loc_180024D54
0x180024c53  mov     rdi, [r12]
0x180024c57  mov     [rbp+57h+var_88], r12
0x180024c5b  mov     [rbp+57h+var_80], rsi
0x180024c5f  mov     ecx, 50h ; 'P'; Size
0x180024c64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024c69  mov     rsi, rax
0x180024c6c  mov     [rbp+57h+var_80], rax
0x180024c70  mov     rdx, r14
0x180024c73  lea     rcx, [rax+20h]
0x180024c77  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180024c7c  mov     rcx, qword ptr [rbp+57h+var_48]
0x180024c80  mov     [rsi+40h], rcx
0x180024c84  mov     rcx, qword ptr [rbp+57h+var_48+8]
0x180024c88  mov     [rsi+48h], rcx
0x180024c8c  xorps   xmm0, xmm0
0x180024c8f  movdqu  [rbp+57h+var_48], xmm0
0x180024c94  mov     [rsi], rdi
0x180024c97  mov     [rsi+8], rdi
0x180024c9b  mov     [rsi+10h], rdi
0x180024c9f  xor     edi, edi
0x180024ca1  mov     [rsi+18h], di
0x180024ca5  mov     [rbp+57h+var_80], rdi
0x180024ca9  lea     rcx, [rbp+57h+var_88]
0x180024cad  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<p9fs::Share>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<p9fs::Share>>,void *>>>(void)
0x180024cb2  movups  xmm0, [rbp+57h+var_60]
0x180024cb6  movdqu  [rbp+57h+var_70], xmm0
0x180024cbb  mov     r8, rsi
0x180024cbe  lea     rdx, [rbp+57h+var_70]
0x180024cc2  mov     rcx, r12
0x180024cc5  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<p9fs::Fid>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<uint const,std::shared_ptr<p9fs::Fid>>,void *> *>,std::_Tree_node<std::pair<uint const,std::shared_ptr<p9fs::Fid>>,void *> * const)
0x180024cca  test    [rbp+57h+var_90], 140h
0x180024cd1  jz      short loc_180024CD7
0x180024cd3  inc     qword ptr [r13+20h]
0x180024cd7  test    r15, r15
0x180024cda  jz      short loc_180024CE6
0x180024cdc  mov     rcx, r15; SRWLock
0x180024cdf  call    cs:__imp_ReleaseSRWLockExclusive
0x180024ce5  nop
0x180024ce6  mov     rbx, qword ptr [rbp+57h+var_48+8]
0x180024cea  test    rbx, rbx
0x180024ced  jz      short loc_180024D26
0x180024cef  or      eax, 0FFFFFFFFh
0x180024cf2  lock xadd [rbx+8], eax
0x180024cf7  cmp     eax, 1
0x180024cfa  jnz     short loc_180024D26
0x180024cfc  mov     rax, [rbx]
0x180024cff  mov     rcx, rbx
0x180024d02  mov     rax, [rax]
0x180024d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d0a  or      eax, 0FFFFFFFFh
0x180024d0d  lock xadd [rbx+0Ch], eax
0x180024d12  cmp     eax, 1
0x180024d15  jnz     short loc_180024D26
0x180024d17  mov     rax, [rbx]
0x180024d1a  mov     rcx, rbx
0x180024d1d  mov     rax, [rax+8]
0x180024d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d26  mov     rcx, [rbp+57h+var_38]
0x180024d2a  xor     rcx, rsp; StackCookie
0x180024d2d  call    __security_check_cookie
0x180024d32  mov     rbx, [rsp+0D0h+arg_18]
0x180024d3a  add     rsp, 0A0h
0x180024d41  pop     r15
0x180024d43  pop     r14
0x180024d45  pop     r13
0x180024d47  pop     r12
0x180024d49  pop     rdi
0x180024d4a  pop     rsi
0x180024d4b  pop     rbp
0x180024d4c  retn
0x180024d4d  jns     short loc_180024D5A
0x180024d4f  jmp     loc_180024C3E
0x180024d54  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x180024d5a  mov     rcx, r14
0x180024d5d  call    ?data@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::data(void)
0x180024d62  mov     rdx, rax
0x180024d65  mov     rcx, r14
0x180024d68  call    ?size@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KXZ; std::string::size(void)
0x180024d6d  mov     [rbp+57h+var_88], rax
0x180024d71  lea     rcx, [rbp+57h+var_88]
0x180024d75  call    ??$narrow_cast@H_K@gsl@@YAH$$QEA_K@Z; gsl::narrow_cast<int,unsigned __int64>(unsigned __int64 &&)
0x180024d7a  mov     rcx, [rbp+5Fh]; this
0x180024d7e  mov     [rsp+0D0h+var_A0], rdx
0x180024d83  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x180024d87  lea     rax, aHs; "%.*hs"
0x180024d8e  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x180024d93  mov     r9d, 0B7h; char *
0x180024d99  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180024da0  mov     edx, 178h; void *
0x180024da5  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
