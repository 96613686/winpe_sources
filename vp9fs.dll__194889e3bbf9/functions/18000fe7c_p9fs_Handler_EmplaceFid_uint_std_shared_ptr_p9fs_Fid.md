# p9fs::Handler::EmplaceFid(uint,std::shared_ptr<p9fs::Fid>)

- ea: `0x18000fe7c`
- end: `0x180010017`
- name: `?EmplaceFid@Handler@p9fs@@AEAAXIV?$shared_ptr@VFid@p9fs@@@std@@@Z`
- size: `411`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001085c`
- `0x180014b78`
- `0x18001572c`
- `0x180016310`

## callees

- `0x1800030b0`
- `0x1800030d0`
- `0x180004144`
- `0x18000de60`
- `0x18000fe7c`
- `0x18001c52c`
- `0x18001c75c`
- `0x18001c77c`
- `0x180034010`

## string_xrefs

- `0x18000ffff`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall p9fs::Handler::EmplaceFid(__int64 a1, unsigned int a2, _QWORD *a3)
{
  _QWORD *v5; // r12
  _Smtx_t *v6; // rbx
  __int64 *v7; // r13
  __int64 *v8; // rax
  __int64 *v9; // rcx
  char v10; // si
  _DWORD *v11; // rdi
  __int64 v12; // rax
  volatile signed __int32 *v13; // rbx
  __int128 v14; // [rsp+20h] [rbp-40h] BYREF
  __int128 v15; // [rsp+30h] [rbp-30h]
  _QWORD *v16; // [rsp+48h] [rbp-18h]
  __int64 v17; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v5 = (_QWORD *)(a1 + 40);
  v16 = a3;
  v6 = (_Smtx_t *)(a1 + 32);
  v17 = a1 + 32;
  Smtx_lock_exclusive((_Smtx_t *)(a1 + 32));
  v7 = (__int64 *)*v5;
  v8 = *(__int64 **)(*v5 + 8LL);
  v15 = (unsigned __int64)v8;
  v9 = v7;
  v10 = 1;
  while ( !*((_BYTE *)v8 + 25) )
  {
    *(_QWORD *)&v15 = v8;
    if ( *((_DWORD *)v8 + 8) >= a2 )
    {
      DWORD2(v15) = 1;
      v9 = v8;
    }
    else
    {
      DWORD2(v15) = 0;
      v8 += 2;
    }
    v8 = (__int64 *)*v8;
  }
  if ( *((_BYTE *)v9 + 25) || a2 < *((_DWORD *)v9 + 8) )
  {
    if ( v5[1] == 0x492492492492492LL )
      std::_Throw_tree_length_error();
    v14 = (unsigned __int64)v5;
    v11 = operator new(0x38u);
    v11[8] = a2;
    *((_QWORD *)v11 + 5) = 0;
    *((_QWORD *)v11 + 6) = 0;
    v12 = a3[1];
    if ( v12 )
      _InterlockedAdd((volatile signed __int32 *)(v12 + 8), 1u);
    *((_QWORD *)v11 + 5) = *a3;
    *((_QWORD *)v11 + 6) = a3[1];
    *(_QWORD *)v11 = v7;
    *((_QWORD *)v11 + 1) = v7;
    *((_QWORD *)v11 + 2) = v7;
    *((_WORD *)v11 + 12) = 0;
    *((_QWORD *)&v14 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<p9fs::Fid>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<p9fs::Fid>>,void *>>>(&v14);
    v14 = v15;
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<p9fs::Fid>>>>::_Insert_node(
      v5,
      &v14,
      v11);
    v10 = 0;
  }
  if ( v10 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x57E,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
      (const char *)0x8007000DLL,
      v14);
  Smtx_unlock_exclusive(v6);
  v13 = (volatile signed __int32 *)a3[1];
  if ( v13 && _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
    if ( !_InterlockedDecrement(v13 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
  }
}

```

## disassembly

```asm
0x18000fe7c  mov     [rsp-38h+arg_8], rbx
0x18000fe81  mov     [rsp-38h+arg_10], r8
0x18000fe86  push    rbp
0x18000fe87  push    rsi
0x18000fe88  push    rdi
0x18000fe89  push    r12
0x18000fe8b  push    r13
0x18000fe8d  push    r14
0x18000fe8f  push    r15
0x18000fe91  mov     rbp, rsp
0x18000fe94  sub     rsp, 60h
0x18000fe98  mov     r14, r8
0x18000fe9b  mov     r15d, edx
0x18000fe9e  lea     r12, [rcx+28h]
0x18000fea2  mov     [rbp+var_18], r8
0x18000fea6  lea     rbx, [rcx+20h]
0x18000feaa  mov     [rbp+var_10], rbx
0x18000feae  mov     rcx, rbx; _Smtx_t *
0x18000feb1  call    _Smtx_lock_exclusive
0x18000feb6  nop
0x18000feb7  mov     r13, [r12]
0x18000febb  mov     rax, [r13+8]
0x18000febf  mov     qword ptr [rbp+var_30], rax
0x18000fec3  xor     edi, edi
0x18000fec5  mov     qword ptr [rbp+var_30+8], rdi
0x18000fec9  mov     rcx, r13
0x18000fecc  lea     esi, [rdi+1]
0x18000fecf  jmp     short loc_18000FEED
0x18000fed1  mov     qword ptr [rbp+var_30], rax
0x18000fed5  cmp     [rax+20h], r15d
0x18000fed9  jnb     short loc_18000FEE4
0x18000fedb  mov     dword ptr [rbp+var_30+8], edi
0x18000fede  add     rax, 10h
0x18000fee2  jmp     short loc_18000FEEA
0x18000fee4  mov     dword ptr [rbp+var_30+8], esi
0x18000fee7  mov     rcx, rax
0x18000feea  mov     rax, [rax]
0x18000feed  cmp     [rax+19h], dil
0x18000fef1  jz      short loc_18000FED1
0x18000fef3  cmp     [rcx+19h], dil
0x18000fef7  jnz     short loc_18000FF03
0x18000fef9  cmp     r15d, [rcx+20h]
0x18000fefd  jnb     loc_18000FF90
0x18000ff03  mov     rax, 492492492492492h
0x18000ff0d  cmp     [r12+8], rax
0x18000ff12  jz      loc_180010011
0x18000ff18  mov     qword ptr [rbp+var_40], r12
0x18000ff1c  mov     qword ptr [rbp+var_40+8], rdi
0x18000ff20  mov     ecx, 38h ; '8'; Size
0x18000ff25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ff2a  mov     rdi, rax
0x18000ff2d  mov     [rax+20h], r15d
0x18000ff31  xor     ecx, ecx
0x18000ff33  mov     [rax+28h], rcx
0x18000ff37  mov     [rax+30h], rcx
0x18000ff3b  mov     rax, [r14+8]
0x18000ff3f  test    rax, rax
0x18000ff42  jz      short loc_18000FF48
0x18000ff44  lock add [rax+8], esi
0x18000ff48  mov     rax, [r14]
0x18000ff4b  mov     [rdi+28h], rax
0x18000ff4f  mov     rax, [r14+8]
0x18000ff53  mov     [rdi+30h], rax
0x18000ff57  mov     [rdi], r13
0x18000ff5a  mov     [rdi+8], r13
0x18000ff5e  mov     [rdi+10h], r13
0x18000ff62  mov     [rdi+18h], cx
0x18000ff66  mov     qword ptr [rbp+var_40+8], rcx
0x18000ff6a  lea     rcx, [rbp+var_40]
0x18000ff6e  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<p9fs::Fid>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<p9fs::Fid>>,void *>>>(void)
0x18000ff73  movups  xmm0, [rbp+var_30]
0x18000ff77  movdqu  [rbp+var_40], xmm0
0x18000ff7c  mov     r8, rdi
0x18000ff7f  lea     rdx, [rbp+var_40]
0x18000ff83  mov     rcx, r12
0x18000ff86  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VFid@p9fs@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<p9fs::Fid>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<uint const,std::shared_ptr<p9fs::Fid>>,void *> *>,std::_Tree_node<std::pair<uint const,std::shared_ptr<p9fs::Fid>>,void *> * const)
0x18000ff8b  xor     edi, edi
0x18000ff8d  mov     sil, dil
0x18000ff90  mov     rcx, [rbp+38h]; this
0x18000ff94  test    sil, sil
0x18000ff97  jnz     short loc_18000FFF9
0x18000ff99  mov     rcx, rbx; _Smtx_t *
0x18000ff9c  call    _Smtx_unlock_exclusive
0x18000ffa1  nop
0x18000ffa2  mov     rbx, [r14+8]
0x18000ffa6  test    rbx, rbx
0x18000ffa9  jz      short loc_18000FFE1
0x18000ffab  or      edi, 0FFFFFFFFh
0x18000ffae  mov     eax, edi
0x18000ffb0  lock xadd [rbx+8], eax
0x18000ffb5  add     eax, edi
0x18000ffb7  jnz     short loc_18000FFE1
0x18000ffb9  mov     rax, [rbx]
0x18000ffbc  mov     rcx, rbx
0x18000ffbf  mov     rax, [rax]
0x18000ffc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffc7  mov     eax, edi
0x18000ffc9  lock xadd [rbx+0Ch], eax
0x18000ffce  add     eax, edi
0x18000ffd0  jnz     short loc_18000FFE1
0x18000ffd2  mov     rax, [rbx]
0x18000ffd5  mov     rcx, rbx
0x18000ffd8  mov     rax, [rax+8]
0x18000ffdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffe1  mov     rbx, [rsp+60h+arg_8]
0x18000ffe9  add     rsp, 60h
0x18000ffed  pop     r15
0x18000ffef  pop     r14
0x18000fff1  pop     r13
0x18000fff3  pop     r12
0x18000fff5  pop     rdi
0x18000fff6  pop     rsi
0x18000fff7  pop     rbp
0x18000fff8  retn
0x18000fff9  mov     r9d, 8007000Dh; char *
0x18000ffff  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180010006  mov     edx, 57Eh; void *
0x18001000b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010011  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
