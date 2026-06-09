# std::vector<std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>>,std::allocator<std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>>>>::_Emplace_reallocate<std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>>>(std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>> * const,std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>> &&)

- ea: `0x18002e15c`
- end: `0x18002e29a`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `318`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c440`
- `0x180034cbc`

## callees

- `0x180001084`
- `0x18000320c`
- `0x18002cc5c`
- `0x18002e15c`
- `0x18002f220`
- `0x180030a64`
- `0x180033abc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e197`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e197`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<CHANNEL_ENTRY>>::_Emplace_reallocate<std::unique_ptr<CHANNEL_ENTRY>>(
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
    std::_Uninitialized_move<std::unique_ptr<CHANNEL_ENTRY> *,std::allocator<std::unique_ptr<CHANNEL_ENTRY>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<CHANNEL_ENTRY> *,std::allocator<std::unique_ptr<CHANNEL_ENTRY>>>(
    v20,
    v19,
    v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<CHANNEL_ENTRY>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<CHANNEL_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002e15c  push    rbx
0x18002e15e  push    rbp
0x18002e15f  push    rsi
0x18002e160  push    rdi
0x18002e161  push    r12
0x18002e163  push    r13
0x18002e165  push    r14
0x18002e167  push    r15
0x18002e169  sub     rsp, 58h
0x18002e16d  mov     rax, [rcx+8]
0x18002e171  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002e17b  sub     rax, [rcx]
0x18002e17e  mov     r13, r8
0x18002e181  sar     rax, 3
0x18002e185  mov     rbp, rdx
0x18002e188  mov     rbx, rcx
0x18002e18b  cmp     rax, rdi
0x18002e18e  jnz     short loc_18002E19E
0x18002e190  lea     rcx, aVectorTooLong; "vector too long"
0x18002e197  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002e19e  lea     r14, [rax+1]
0x18002e1a2  mov     r15, rbp
0x18002e1a5  sub     r15, [rcx]
0x18002e1a8  mov     rax, rdi
0x18002e1ab  mov     rcx, [rcx+10h]
0x18002e1af  sub     rcx, [rbx]
0x18002e1b2  sar     rcx, 3
0x18002e1b6  mov     rdx, rcx
0x18002e1b9  sar     r15, 3
0x18002e1bd  shr     rdx, 1
0x18002e1c0  sub     rax, rdx
0x18002e1c3  cmp     rcx, rax
0x18002e1c6  ja      short loc_18002E1D3
0x18002e1c8  lea     rdi, [rdx+rcx]
0x18002e1cc  cmp     rdi, r14
0x18002e1cf  cmovb   rdi, r14
0x18002e1d3  mov     rcx, rdi
0x18002e1d6  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002e1db  mov     rcx, rax
0x18002e1de  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002e1e3  mov     rcx, [r13+0]
0x18002e1e7  mov     rsi, rax
0x18002e1ea  mov     qword ptr [r13+0], 0
0x18002e1f2  mov     r8, rax
0x18002e1f5  mov     [rsp+98h+var_78], rbx
0x18002e1fa  lea     r15, [rax+r15*8]
0x18002e1fe  mov     [rsp+98h+var_68], rdi
0x18002e203  mov     [r15], rcx
0x18002e206  lea     r12, [r15+8]
0x18002e20a  mov     rdx, [rbx+8]
0x18002e20e  mov     rcx, [rbx]
0x18002e211  mov     [rsp+98h+var_58], r12
0x18002e216  mov     [rsp+98h+var_60], r15
0x18002e21b  cmp     rbp, rdx
0x18002e21e  jz      short loc_18002E237
0x18002e220  mov     rdx, rbp
0x18002e223  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<CHANNEL_ENTRY> *,std::allocator<std::unique_ptr<CHANNEL_ENTRY>>>(std::unique_ptr<CHANNEL_ENTRY> * const,std::unique_ptr<CHANNEL_ENTRY> * const,std::unique_ptr<CHANNEL_ENTRY> *,std::allocator<std::unique_ptr<CHANNEL_ENTRY>> &)
0x18002e228  mov     rdx, [rbx+8]
0x18002e22c  mov     r8, r12
0x18002e22f  mov     rcx, rbp
0x18002e232  mov     [rsp+98h+var_60], rsi
0x18002e237  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<CHANNEL_ENTRY> *,std::allocator<std::unique_ptr<CHANNEL_ENTRY>>>(std::unique_ptr<CHANNEL_ENTRY> * const,std::unique_ptr<CHANNEL_ENTRY> * const,std::unique_ptr<CHANNEL_ENTRY> *,std::allocator<std::unique_ptr<CHANNEL_ENTRY>> &)
0x18002e23c  mov     rcx, [rbx]
0x18002e23f  mov     [rsp+98h+var_70], 0
0x18002e248  test    rcx, rcx
0x18002e24b  jz      short loc_18002E269
0x18002e24d  mov     rdx, [rbx+8]
0x18002e251  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<CHANNEL_ENTRY>>>(std::unique_ptr<CHANNEL_ENTRY> *,std::unique_ptr<CHANNEL_ENTRY> * const,std::allocator<std::unique_ptr<CHANNEL_ENTRY>> &)
0x18002e256  mov     rdx, [rbx+10h]
0x18002e25a  sub     rdx, [rbx]
0x18002e25d  mov     rcx, [rbx]
0x18002e260  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002e264  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e269  mov     [rbx], rsi
0x18002e26c  lea     rcx, [rsi+r14*8]
0x18002e270  mov     [rbx+8], rcx
0x18002e274  lea     rcx, [rsi+rdi*8]
0x18002e278  mov     [rbx+10h], rcx
0x18002e27c  lea     rcx, [rsp+98h+var_78]
0x18002e281  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<CHANNEL_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002e286  mov     rax, r15
0x18002e289  add     rsp, 58h
0x18002e28d  pop     r15
0x18002e28f  pop     r14
0x18002e291  pop     r13
0x18002e293  pop     r12
0x18002e295  pop     rdi
0x18002e296  pop     rsi
0x18002e297  pop     rbp
0x18002e298  pop     rbx
0x18002e299  retn
```
