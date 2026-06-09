# std::vector<std::unique_ptr<TEMPLATE_ENTRY,std::default_delete<TEMPLATE_ENTRY>>,std::allocator<std::unique_ptr<TEMPLATE_ENTRY,std::default_delete<TEMPLATE_ENTRY>>>>::_Emplace_reallocate<std::unique_ptr<TEMPLATE_ENTRY,std::default_delete<TEMPLATE_ENTRY>>>(std::unique_ptr<TEMPLATE_ENTRY,std::default_delete<TEMPLATE_ENTRY>> * const,std::unique_ptr<TEMPLATE_ENTRY,std::default_delete<TEMPLATE_ENTRY>> &&)

- ea: `0x18002eb7c`
- end: `0x18002ecba`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `318`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003bae4`

## callees

- `0x180001084`
- `0x18000320c`
- `0x18002ce1c`
- `0x18002eb7c`
- `0x18002f220`
- `0x180030c64`
- `0x180033c9c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ebb7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ebb7`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<TEMPLATE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<TEMPLATE_ENTRY>>(
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
    std::_Uninitialized_move<std::unique_ptr<TEMPLATE_ENTRY> *,std::allocator<std::unique_ptr<TEMPLATE_ENTRY>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<TEMPLATE_ENTRY> *,std::allocator<std::unique_ptr<TEMPLATE_ENTRY>>>(
    v20,
    v19,
    v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<TEMPLATE_ENTRY>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<TEMPLATE_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002eb7c  push    rbx
0x18002eb7e  push    rbp
0x18002eb7f  push    rsi
0x18002eb80  push    rdi
0x18002eb81  push    r12
0x18002eb83  push    r13
0x18002eb85  push    r14
0x18002eb87  push    r15
0x18002eb89  sub     rsp, 58h
0x18002eb8d  mov     rax, [rcx+8]
0x18002eb91  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002eb9b  sub     rax, [rcx]
0x18002eb9e  mov     r13, r8
0x18002eba1  sar     rax, 3
0x18002eba5  mov     rbp, rdx
0x18002eba8  mov     rbx, rcx
0x18002ebab  cmp     rax, rdi
0x18002ebae  jnz     short loc_18002EBBE
0x18002ebb0  lea     rcx, aVectorTooLong; "vector too long"
0x18002ebb7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002ebbe  lea     r14, [rax+1]
0x18002ebc2  mov     r15, rbp
0x18002ebc5  sub     r15, [rcx]
0x18002ebc8  mov     rax, rdi
0x18002ebcb  mov     rcx, [rcx+10h]
0x18002ebcf  sub     rcx, [rbx]
0x18002ebd2  sar     rcx, 3
0x18002ebd6  mov     rdx, rcx
0x18002ebd9  sar     r15, 3
0x18002ebdd  shr     rdx, 1
0x18002ebe0  sub     rax, rdx
0x18002ebe3  cmp     rcx, rax
0x18002ebe6  ja      short loc_18002EBF3
0x18002ebe8  lea     rdi, [rdx+rcx]
0x18002ebec  cmp     rdi, r14
0x18002ebef  cmovb   rdi, r14
0x18002ebf3  mov     rcx, rdi
0x18002ebf6  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002ebfb  mov     rcx, rax
0x18002ebfe  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002ec03  mov     rcx, [r13+0]
0x18002ec07  mov     rsi, rax
0x18002ec0a  mov     qword ptr [r13+0], 0
0x18002ec12  mov     r8, rax
0x18002ec15  mov     [rsp+98h+var_78], rbx
0x18002ec1a  lea     r15, [rax+r15*8]
0x18002ec1e  mov     [rsp+98h+var_68], rdi
0x18002ec23  mov     [r15], rcx
0x18002ec26  lea     r12, [r15+8]
0x18002ec2a  mov     rdx, [rbx+8]
0x18002ec2e  mov     rcx, [rbx]
0x18002ec31  mov     [rsp+98h+var_58], r12
0x18002ec36  mov     [rsp+98h+var_60], r15
0x18002ec3b  cmp     rbp, rdx
0x18002ec3e  jz      short loc_18002EC57
0x18002ec40  mov     rdx, rbp
0x18002ec43  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<TEMPLATE_ENTRY> *,std::allocator<std::unique_ptr<TEMPLATE_ENTRY>>>(std::unique_ptr<TEMPLATE_ENTRY> * const,std::unique_ptr<TEMPLATE_ENTRY> * const,std::unique_ptr<TEMPLATE_ENTRY> *,std::allocator<std::unique_ptr<TEMPLATE_ENTRY>> &)
0x18002ec48  mov     rdx, [rbx+8]
0x18002ec4c  mov     r8, r12
0x18002ec4f  mov     rcx, rbp
0x18002ec52  mov     [rsp+98h+var_60], rsi
0x18002ec57  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<TEMPLATE_ENTRY> *,std::allocator<std::unique_ptr<TEMPLATE_ENTRY>>>(std::unique_ptr<TEMPLATE_ENTRY> * const,std::unique_ptr<TEMPLATE_ENTRY> * const,std::unique_ptr<TEMPLATE_ENTRY> *,std::allocator<std::unique_ptr<TEMPLATE_ENTRY>> &)
0x18002ec5c  mov     rcx, [rbx]
0x18002ec5f  mov     [rsp+98h+var_70], 0
0x18002ec68  test    rcx, rcx
0x18002ec6b  jz      short loc_18002EC89
0x18002ec6d  mov     rdx, [rbx+8]
0x18002ec71  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<TEMPLATE_ENTRY>>>(std::unique_ptr<TEMPLATE_ENTRY> *,std::unique_ptr<TEMPLATE_ENTRY> * const,std::allocator<std::unique_ptr<TEMPLATE_ENTRY>> &)
0x18002ec76  mov     rdx, [rbx+10h]
0x18002ec7a  sub     rdx, [rbx]
0x18002ec7d  mov     rcx, [rbx]
0x18002ec80  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002ec84  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002ec89  mov     [rbx], rsi
0x18002ec8c  lea     rcx, [rsi+r14*8]
0x18002ec90  mov     [rbx+8], rcx
0x18002ec94  lea     rcx, [rsi+rdi*8]
0x18002ec98  mov     [rbx+10h], rcx
0x18002ec9c  lea     rcx, [rsp+98h+var_78]
0x18002eca1  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTEMPLATE_ENTRY@@U?$default_delete@VTEMPLATE_ENTRY@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<TEMPLATE_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002eca6  mov     rax, r15
0x18002eca9  add     rsp, 58h
0x18002ecad  pop     r15
0x18002ecaf  pop     r14
0x18002ecb1  pop     r13
0x18002ecb3  pop     r12
0x18002ecb5  pop     rdi
0x18002ecb6  pop     rsi
0x18002ecb7  pop     rbp
0x18002ecb8  pop     rbx
0x18002ecb9  retn
```
