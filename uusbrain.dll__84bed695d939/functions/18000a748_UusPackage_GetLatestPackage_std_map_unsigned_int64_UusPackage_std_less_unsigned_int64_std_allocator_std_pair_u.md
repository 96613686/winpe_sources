# UusPackage::GetLatestPackage(std::map<unsigned __int64,UusPackage,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,UusPackage>>> *,std::function<void (std::filesystem::path const &,char const *)>)

- ea: `0x18000a748`
- end: `0x18000a8d3`
- name: `?GetLatestPackage@UusPackage@@SA?AV?$optional@VUusPackage@@@std@@PEAV?$map@_KVUusPackage@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KVUusPackage@@@std@@@3@@3@V?$function@$$A6AXAEBVpath@filesystem@std@@PEBD@Z@3@@Z`
- size: `395`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000c510`
- `0x180039904`

## callees

- `0x18000a748`
- `0x18000b024`
- `0x18000bc8c`
- `0x180014560`
- `0x180029644`
- `0x1800427d0`
- `0x180042bc4`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UusPackage::GetLatestPackage(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v6; // rdi
  char *v7; // r12
  char *v8; // rbx
  __int64 (__fastcall ***v9)(_QWORD, _BYTE *); // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD v13[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[56]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-58h]
  _QWORD v16[3]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v17[2]; // [rsp+C8h] [rbp-38h] BYREF
  char v18; // [rsp+D8h] [rbp-28h]
  _OWORD v19[2]; // [rsp+E0h] [rbp-20h] BYREF

  v16[0] = a2;
  v16[2] = a3;
  if ( a2 )
  {
    v6 = (_QWORD *)*a2;
    v7 = *(char **)(*a2 + 8LL);
    while ( !v7[25] )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,UusPackage>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,UusPackage>,void *>>>(
        a2,
        a2,
        *((_QWORD *)v7 + 2));
      v8 = v7;
      v7 = *(char **)v7;
      std::pair<unsigned __int64 const,UusPackage>::~pair<unsigned __int64 const,UusPackage>(v8 + 32);
      operator delete(v8, 0x80u);
    }
    v6[1] = v6;
    *v6 = v6;
    v6[2] = v6;
    a2[1] = 0;
  }
  v18 = 0;
  v19[0] = 0;
  v19[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19[0]) = 0;
  v15 = 0;
  v9 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a3 + 56);
  if ( v9 )
    v15 = (**v9)(v9, v14);
  v13[0] = &std::_Func_impl_no_alloc<_lambda_0cc5011d48c3d1c34535627d9051d611_,bool,UusPackage const &>::`vftable';
  v13[1] = v16;
  v13[2] = v17;
  v13[3] = v19;
  v13[7] = v13;
  UusPackage::FindBestPackage(a1, v13, v14);
  std::wstring::_Tidy_deallocate(v19);
  if ( v18 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))v17[0])(v17, 0);
  v11 = *(_QWORD *)(a3 + 56);
  if ( v11 )
  {
    LOBYTE(v10) = v11 != a3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 32LL))(v11, v10);
    *(_QWORD *)(a3 + 56) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000a748  mov     [rsp-8+arg_18], rbx
0x18000a74d  push    rbp
0x18000a74e  push    rsi
0x18000a74f  push    rdi
0x18000a750  push    r12
0x18000a752  push    r13
0x18000a754  push    r14
0x18000a756  push    r15
0x18000a758  lea     rbp, [rsp-10h]
0x18000a75d  sub     rsp, 110h
0x18000a764  mov     rax, cs:__security_cookie
0x18000a76b  xor     rax, rsp
0x18000a76e  mov     [rbp+40h+var_40], rax
0x18000a772  mov     rsi, r8
0x18000a775  mov     r14, rdx
0x18000a778  mov     r15, rcx
0x18000a77b  mov     [rbp+40h+var_90], rcx
0x18000a77f  mov     [rbp+40h+var_90], rdx
0x18000a783  mov     [rbp+40h+var_80], r8
0x18000a787  xor     r13d, r13d
0x18000a78a  test    rdx, rdx
0x18000a78d  jz      short loc_18000A7DB
0x18000a78f  mov     rdi, [rdx]
0x18000a792  mov     r12, [rdi+8]
0x18000a796  jmp     short loc_18000A7C5
0x18000a798  mov     r8, [r12+10h]
0x18000a79d  mov     rdx, r14
0x18000a7a0  mov     rcx, r14
0x18000a7a3  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KVUusPackage@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KVUusPackage@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KVUusPackage@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KVUusPackage@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,UusPackage>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,UusPackage>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,UusPackage>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,UusPackage>,void *> *)
0x18000a7a8  mov     rbx, r12
0x18000a7ab  mov     r12, [r12]
0x18000a7af  lea     rcx, [rbx+20h]
0x18000a7b3  call    ??1?$pair@$$CB_KVUusPackage@@@std@@QEAA@XZ; std::pair<unsigned __int64 const,UusPackage>::~pair<unsigned __int64 const,UusPackage>(void)
0x18000a7b8  mov     edx, 80h; unsigned __int64
0x18000a7bd  mov     rcx, rbx; void *
0x18000a7c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a7c5  cmp     [r12+19h], r13b
0x18000a7ca  jz      short loc_18000A798
0x18000a7cc  mov     [rdi+8], rdi
0x18000a7d0  mov     [rdi], rdi
0x18000a7d3  mov     [rdi+10h], rdi
0x18000a7d7  mov     [r14+8], r13
0x18000a7db  mov     [rbp+40h+var_68], r13b
0x18000a7df  xorps   xmm0, xmm0
0x18000a7e2  movups  [rbp+40h+var_60], xmm0
0x18000a7e6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000a7ee  movdqu  [rbp+40h+var_50], xmm1
0x18000a7f3  mov     word ptr [rbp+40h+var_60], r13w
0x18000a7f8  lea     rax, [rsp+140h+var_D0]
0x18000a7fd  mov     [rsp+140h+var_118], rax
0x18000a802  mov     [rbp+40h+var_98], r13
0x18000a806  mov     rcx, [rsi+38h]
0x18000a80a  test    rcx, rcx
0x18000a80d  jz      short loc_18000A823
0x18000a80f  mov     rax, [rcx]
0x18000a812  lea     rdx, [rsp+140h+var_D0]
0x18000a817  mov     rax, [rax]
0x18000a81a  call    _guard_dispatch_icall
0x18000a81f  mov     [rbp+40h+var_98], rax
0x18000a823  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_0cc5011d48c3d1c34535627d9051d611_@@_NAEBVUusPackage@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_0cc5011d48c3d1c34535627d9051d611_,bool,UusPackage const &>::`vftable'
0x18000a82a  mov     [rsp+140h+var_110], rax
0x18000a82f  lea     rax, [rbp+40h+var_90]
0x18000a833  mov     [rsp+140h+var_108], rax
0x18000a838  lea     rax, [rbp+40h+var_78]
0x18000a83c  mov     [rsp+140h+var_100], rax
0x18000a841  lea     rax, [rbp+40h+var_60]
0x18000a845  mov     [rsp+140h+var_F8], rax
0x18000a84a  lea     rax, [rsp+140h+var_110]
0x18000a84f  mov     [rsp+140h+var_D8], rax
0x18000a854  lea     r8, [rsp+140h+var_D0]
0x18000a859  lea     rdx, [rsp+140h+var_110]
0x18000a85e  mov     rcx, r15
0x18000a861  call    ?FindBestPackage@UusPackage@@CA?AV?$optional@VUusPackage@@@std@@V?$function@$$A6A_NAEBVUusPackage@@@Z@3@V?$function@$$A6AXAEBVpath@filesystem@std@@PEBD@Z@3@@Z; UusPackage::FindBestPackage(std::function<bool (UusPackage const &)>,std::function<void (std::filesystem::path const &,char const *)>)
0x18000a866  nop
0x18000a867  lea     rcx, [rbp+40h+var_60]
0x18000a86b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a870  nop
0x18000a871  cmp     [rbp+40h+var_68], r13b
0x18000a875  jz      short loc_18000A88A
0x18000a877  mov     rax, [rbp+40h+var_78]
0x18000a87b  xor     edx, edx
0x18000a87d  lea     rcx, [rbp+40h+var_78]
0x18000a881  mov     rax, [rax]
0x18000a884  call    _guard_dispatch_icall
0x18000a889  nop
0x18000a88a  mov     rcx, [rsi+38h]
0x18000a88e  test    rcx, rcx
0x18000a891  jz      short loc_18000A8A9
0x18000a893  cmp     rcx, rsi
0x18000a896  setnz   dl
0x18000a899  mov     r8, [rcx]
0x18000a89c  mov     rax, [r8+20h]
0x18000a8a0  call    _guard_dispatch_icall
0x18000a8a5  mov     [rsi+38h], r13
0x18000a8a9  mov     rax, r15
0x18000a8ac  mov     rcx, [rbp+40h+var_40]
0x18000a8b0  xor     rcx, rsp; StackCookie
0x18000a8b3  call    __security_check_cookie
0x18000a8b8  mov     rbx, [rsp+140h+arg_18]
0x18000a8c0  add     rsp, 110h
0x18000a8c7  pop     r15
0x18000a8c9  pop     r14
0x18000a8cb  pop     r13
0x18000a8cd  pop     r12
0x18000a8cf  pop     rdi
0x18000a8d0  pop     rsi
0x18000a8d1  pop     rbp
0x18000a8d2  retn
```
