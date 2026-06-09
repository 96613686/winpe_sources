# std::vector<std::unique_ptr<PROPERTY_ENTRY,std::default_delete<PROPERTY_ENTRY>>,std::allocator<std::unique_ptr<PROPERTY_ENTRY,std::default_delete<PROPERTY_ENTRY>>>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY,std::default_delete<PROPERTY_ENTRY>>>(std::unique_ptr<PROPERTY_ENTRY,std::default_delete<PROPERTY_ENTRY>> * const,std::unique_ptr<PROPERTY_ENTRY,std::default_delete<PROPERTY_ENTRY>> &&)

- ea: `0x18002ea38`
- end: `0x18002eb76`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `318`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001d810`
- `0x18003b4dc`

## callees

- `0x180001084`
- `0x18000320c`
- `0x18002cde4`
- `0x18002ea38`
- `0x18002f220`
- `0x180030c24`
- `0x180033c60`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ea73`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ea73`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Emplace_reallocate<std::unique_ptr<PROPERTY_ENTRY>>(
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
    std::_Uninitialized_move<std::unique_ptr<PROPERTY_ENTRY> *,std::allocator<std::unique_ptr<PROPERTY_ENTRY>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<PROPERTY_ENTRY> *,std::allocator<std::unique_ptr<PROPERTY_ENTRY>>>(
    v20,
    v19,
    v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<PROPERTY_ENTRY>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002ea38  push    rbx
0x18002ea3a  push    rbp
0x18002ea3b  push    rsi
0x18002ea3c  push    rdi
0x18002ea3d  push    r12
0x18002ea3f  push    r13
0x18002ea41  push    r14
0x18002ea43  push    r15
0x18002ea45  sub     rsp, 58h
0x18002ea49  mov     rax, [rcx+8]
0x18002ea4d  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002ea57  sub     rax, [rcx]
0x18002ea5a  mov     r13, r8
0x18002ea5d  sar     rax, 3
0x18002ea61  mov     rbp, rdx
0x18002ea64  mov     rbx, rcx
0x18002ea67  cmp     rax, rdi
0x18002ea6a  jnz     short loc_18002EA7A
0x18002ea6c  lea     rcx, aVectorTooLong; "vector too long"
0x18002ea73  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002ea7a  lea     r14, [rax+1]
0x18002ea7e  mov     r15, rbp
0x18002ea81  sub     r15, [rcx]
0x18002ea84  mov     rax, rdi
0x18002ea87  mov     rcx, [rcx+10h]
0x18002ea8b  sub     rcx, [rbx]
0x18002ea8e  sar     rcx, 3
0x18002ea92  mov     rdx, rcx
0x18002ea95  sar     r15, 3
0x18002ea99  shr     rdx, 1
0x18002ea9c  sub     rax, rdx
0x18002ea9f  cmp     rcx, rax
0x18002eaa2  ja      short loc_18002EAAF
0x18002eaa4  lea     rdi, [rdx+rcx]
0x18002eaa8  cmp     rdi, r14
0x18002eaab  cmovb   rdi, r14
0x18002eaaf  mov     rcx, rdi
0x18002eab2  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002eab7  mov     rcx, rax
0x18002eaba  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002eabf  mov     rcx, [r13+0]
0x18002eac3  mov     rsi, rax
0x18002eac6  mov     qword ptr [r13+0], 0
0x18002eace  mov     r8, rax
0x18002ead1  mov     [rsp+98h+var_78], rbx
0x18002ead6  lea     r15, [rax+r15*8]
0x18002eada  mov     [rsp+98h+var_68], rdi
0x18002eadf  mov     [r15], rcx
0x18002eae2  lea     r12, [r15+8]
0x18002eae6  mov     rdx, [rbx+8]
0x18002eaea  mov     rcx, [rbx]
0x18002eaed  mov     [rsp+98h+var_58], r12
0x18002eaf2  mov     [rsp+98h+var_60], r15
0x18002eaf7  cmp     rbp, rdx
0x18002eafa  jz      short loc_18002EB13
0x18002eafc  mov     rdx, rbp
0x18002eaff  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<PROPERTY_ENTRY> *,std::allocator<std::unique_ptr<PROPERTY_ENTRY>>>(std::unique_ptr<PROPERTY_ENTRY> * const,std::unique_ptr<PROPERTY_ENTRY> * const,std::unique_ptr<PROPERTY_ENTRY> *,std::allocator<std::unique_ptr<PROPERTY_ENTRY>> &)
0x18002eb04  mov     rdx, [rbx+8]
0x18002eb08  mov     r8, r12
0x18002eb0b  mov     rcx, rbp
0x18002eb0e  mov     [rsp+98h+var_60], rsi
0x18002eb13  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<PROPERTY_ENTRY> *,std::allocator<std::unique_ptr<PROPERTY_ENTRY>>>(std::unique_ptr<PROPERTY_ENTRY> * const,std::unique_ptr<PROPERTY_ENTRY> * const,std::unique_ptr<PROPERTY_ENTRY> *,std::allocator<std::unique_ptr<PROPERTY_ENTRY>> &)
0x18002eb18  mov     rcx, [rbx]
0x18002eb1b  mov     [rsp+98h+var_70], 0
0x18002eb24  test    rcx, rcx
0x18002eb27  jz      short loc_18002EB45
0x18002eb29  mov     rdx, [rbx+8]
0x18002eb2d  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<PROPERTY_ENTRY>>>(std::unique_ptr<PROPERTY_ENTRY> *,std::unique_ptr<PROPERTY_ENTRY> * const,std::allocator<std::unique_ptr<PROPERTY_ENTRY>> &)
0x18002eb32  mov     rdx, [rbx+10h]
0x18002eb36  sub     rdx, [rbx]
0x18002eb39  mov     rcx, [rbx]
0x18002eb3c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002eb40  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002eb45  mov     [rbx], rsi
0x18002eb48  lea     rcx, [rsi+r14*8]
0x18002eb4c  mov     [rbx+8], rcx
0x18002eb50  lea     rcx, [rsi+rdi*8]
0x18002eb54  mov     [rbx+10h], rcx
0x18002eb58  lea     rcx, [rsp+98h+var_78]
0x18002eb5d  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VPROPERTY_ENTRY@@U?$default_delete@VPROPERTY_ENTRY@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<PROPERTY_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002eb62  mov     rax, r15
0x18002eb65  add     rsp, 58h
0x18002eb69  pop     r15
0x18002eb6b  pop     r14
0x18002eb6d  pop     r13
0x18002eb6f  pop     r12
0x18002eb71  pop     rdi
0x18002eb72  pop     rsi
0x18002eb73  pop     rbp
0x18002eb74  pop     rbx
0x18002eb75  retn
```
