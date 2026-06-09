# std::vector<std::unique_ptr<KEYWORD_ENTRY,std::default_delete<KEYWORD_ENTRY>>,std::allocator<std::unique_ptr<KEYWORD_ENTRY,std::default_delete<KEYWORD_ENTRY>>>>::_Emplace_reallocate<std::unique_ptr<KEYWORD_ENTRY,std::default_delete<KEYWORD_ENTRY>>>(std::unique_ptr<KEYWORD_ENTRY,std::default_delete<KEYWORD_ENTRY>> * const,std::unique_ptr<KEYWORD_ENTRY,std::default_delete<KEYWORD_ENTRY>> &&)

- ea: `0x18002e66c`
- end: `0x18002e7aa`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `318`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18001bdb8`
- `0x180033f84`
- `0x180038228`
- `0x180038498`

## callees

- `0x180001084`
- `0x18000320c`
- `0x18002cd3c`
- `0x18002e66c`
- `0x18002f220`
- `0x180030b64`
- `0x180033bac`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e6a7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e6a7`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<KEYWORD_ENTRY>>::_Emplace_reallocate<std::unique_ptr<KEYWORD_ENTRY>>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  __int64 size_of; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rsi
  _QWORD *v17; // r8
  _QWORD *v18; // r15
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-60h]
  _QWORD *v25; // [rsp+40h] [rbp-58h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v5 + 1;
  v9 = a2 - *a1;
  v10 = (a1[2] - *a1) >> 3;
  v11 = v9 >> 3;
  v12 = v10 >> 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v3);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = *a3;
  v16 = v14;
  *a3 = 0;
  v17 = (_QWORD *)v14;
  v23[0] = a1;
  v18 = (_QWORD *)(v14 + 8 * v11);
  v23[2] = v3;
  *v18 = v15;
  v19 = a1[1];
  v20 = *a1;
  v25 = v18 + 1;
  v24 = v18;
  if ( a2 != v19 )
  {
    std::_Uninitialized_move<std::unique_ptr<KEYWORD_ENTRY> *,std::allocator<std::unique_ptr<KEYWORD_ENTRY>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<KEYWORD_ENTRY> *,std::allocator<std::unique_ptr<KEYWORD_ENTRY>>>(
    v20,
    v19,
    v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<LEVEL_ENTRY>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<LEVEL_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002e66c  push    rbx
0x18002e66e  push    rbp
0x18002e66f  push    rsi
0x18002e670  push    rdi
0x18002e671  push    r12
0x18002e673  push    r13
0x18002e675  push    r14
0x18002e677  push    r15
0x18002e679  sub     rsp, 58h
0x18002e67d  mov     rax, [rcx+8]
0x18002e681  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002e68b  sub     rax, [rcx]
0x18002e68e  mov     r13, r8
0x18002e691  sar     rax, 3
0x18002e695  mov     rbp, rdx
0x18002e698  mov     rbx, rcx
0x18002e69b  cmp     rax, rdi
0x18002e69e  jnz     short loc_18002E6AE
0x18002e6a0  lea     rcx, aVectorTooLong; "vector too long"
0x18002e6a7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002e6ae  lea     r14, [rax+1]
0x18002e6b2  mov     r15, rbp
0x18002e6b5  sub     r15, [rcx]
0x18002e6b8  mov     rax, rdi
0x18002e6bb  mov     rcx, [rcx+10h]
0x18002e6bf  sub     rcx, [rbx]
0x18002e6c2  sar     rcx, 3
0x18002e6c6  mov     rdx, rcx
0x18002e6c9  sar     r15, 3
0x18002e6cd  shr     rdx, 1
0x18002e6d0  sub     rax, rdx
0x18002e6d3  cmp     rcx, rax
0x18002e6d6  ja      short loc_18002E6E3
0x18002e6d8  lea     rdi, [rdx+rcx]
0x18002e6dc  cmp     rdi, r14
0x18002e6df  cmovb   rdi, r14
0x18002e6e3  mov     rcx, rdi
0x18002e6e6  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002e6eb  mov     rcx, rax
0x18002e6ee  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002e6f3  mov     rcx, [r13+0]
0x18002e6f7  mov     rsi, rax
0x18002e6fa  mov     qword ptr [r13+0], 0
0x18002e702  mov     r8, rax
0x18002e705  mov     [rsp+98h+var_78], rbx
0x18002e70a  lea     r15, [rax+r15*8]
0x18002e70e  mov     [rsp+98h+var_68], rdi
0x18002e713  mov     [r15], rcx
0x18002e716  lea     r12, [r15+8]
0x18002e71a  mov     rdx, [rbx+8]
0x18002e71e  mov     rcx, [rbx]
0x18002e721  mov     [rsp+98h+var_58], r12
0x18002e726  mov     [rsp+98h+var_60], r15
0x18002e72b  cmp     rbp, rdx
0x18002e72e  jz      short loc_18002E747
0x18002e730  mov     rdx, rbp
0x18002e733  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<KEYWORD_ENTRY> *,std::allocator<std::unique_ptr<KEYWORD_ENTRY>>>(std::unique_ptr<KEYWORD_ENTRY> * const,std::unique_ptr<KEYWORD_ENTRY> * const,std::unique_ptr<KEYWORD_ENTRY> *,std::allocator<std::unique_ptr<KEYWORD_ENTRY>> &)
0x18002e738  mov     rdx, [rbx+8]
0x18002e73c  mov     r8, r12
0x18002e73f  mov     rcx, rbp
0x18002e742  mov     [rsp+98h+var_60], rsi
0x18002e747  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<KEYWORD_ENTRY> *,std::allocator<std::unique_ptr<KEYWORD_ENTRY>>>(std::unique_ptr<KEYWORD_ENTRY> * const,std::unique_ptr<KEYWORD_ENTRY> * const,std::unique_ptr<KEYWORD_ENTRY> *,std::allocator<std::unique_ptr<KEYWORD_ENTRY>> &)
0x18002e74c  mov     rcx, [rbx]
0x18002e74f  mov     [rsp+98h+var_70], 0
0x18002e758  test    rcx, rcx
0x18002e75b  jz      short loc_18002E779
0x18002e75d  mov     rdx, [rbx+8]
0x18002e761  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<LEVEL_ENTRY>>>(std::unique_ptr<LEVEL_ENTRY> *,std::unique_ptr<LEVEL_ENTRY> * const,std::allocator<std::unique_ptr<LEVEL_ENTRY>> &)
0x18002e766  mov     rdx, [rbx+10h]
0x18002e76a  sub     rdx, [rbx]
0x18002e76d  mov     rcx, [rbx]
0x18002e770  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002e774  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e779  mov     [rbx], rsi
0x18002e77c  lea     rcx, [rsi+r14*8]
0x18002e780  mov     [rbx+8], rcx
0x18002e784  lea     rcx, [rsi+rdi*8]
0x18002e788  mov     [rbx+10h], rcx
0x18002e78c  lea     rcx, [rsp+98h+var_78]
0x18002e791  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<LEVEL_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002e796  mov     rax, r15
0x18002e799  add     rsp, 58h
0x18002e79d  pop     r15
0x18002e79f  pop     r14
0x18002e7a1  pop     r13
0x18002e7a3  pop     r12
0x18002e7a5  pop     rdi
0x18002e7a6  pop     rsi
0x18002e7a7  pop     rbp
0x18002e7a8  pop     rbx
0x18002e7a9  retn
```
