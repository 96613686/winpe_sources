# std::vector<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>,std::allocator<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>>(std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>> * const,std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>> &&)

- ea: `0x18002e8f4`
- end: `0x18002ea32`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `318`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18003410c`
- `0x1800342ec`
- `0x180038d38`
- `0x18003b6f8`

## callees

- `0x180001084`
- `0x18000320c`
- `0x18002cdac`
- `0x18002e8f4`
- `0x18002f220`
- `0x180030be4`
- `0x180033c24`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e92f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e92f`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<OPCODE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY>>(
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
    std::_Uninitialized_move<std::unique_ptr<TASK_ENTRY> *,std::allocator<std::unique_ptr<TASK_ENTRY>>>(v20, a2, v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<TASK_ENTRY> *,std::allocator<std::unique_ptr<TASK_ENTRY>>>(v20, v19, v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<OPCODE_ENTRY>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<TASK_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002e8f4  push    rbx
0x18002e8f6  push    rbp
0x18002e8f7  push    rsi
0x18002e8f8  push    rdi
0x18002e8f9  push    r12
0x18002e8fb  push    r13
0x18002e8fd  push    r14
0x18002e8ff  push    r15
0x18002e901  sub     rsp, 58h
0x18002e905  mov     rax, [rcx+8]
0x18002e909  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002e913  sub     rax, [rcx]
0x18002e916  mov     r13, r8
0x18002e919  sar     rax, 3
0x18002e91d  mov     rbp, rdx
0x18002e920  mov     rbx, rcx
0x18002e923  cmp     rax, rdi
0x18002e926  jnz     short loc_18002E936
0x18002e928  lea     rcx, aVectorTooLong; "vector too long"
0x18002e92f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002e936  lea     r14, [rax+1]
0x18002e93a  mov     r15, rbp
0x18002e93d  sub     r15, [rcx]
0x18002e940  mov     rax, rdi
0x18002e943  mov     rcx, [rcx+10h]
0x18002e947  sub     rcx, [rbx]
0x18002e94a  sar     rcx, 3
0x18002e94e  mov     rdx, rcx
0x18002e951  sar     r15, 3
0x18002e955  shr     rdx, 1
0x18002e958  sub     rax, rdx
0x18002e95b  cmp     rcx, rax
0x18002e95e  ja      short loc_18002E96B
0x18002e960  lea     rdi, [rdx+rcx]
0x18002e964  cmp     rdi, r14
0x18002e967  cmovb   rdi, r14
0x18002e96b  mov     rcx, rdi
0x18002e96e  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002e973  mov     rcx, rax
0x18002e976  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002e97b  mov     rcx, [r13+0]
0x18002e97f  mov     rsi, rax
0x18002e982  mov     qword ptr [r13+0], 0
0x18002e98a  mov     r8, rax
0x18002e98d  mov     [rsp+98h+var_78], rbx
0x18002e992  lea     r15, [rax+r15*8]
0x18002e996  mov     [rsp+98h+var_68], rdi
0x18002e99b  mov     [r15], rcx
0x18002e99e  lea     r12, [r15+8]
0x18002e9a2  mov     rdx, [rbx+8]
0x18002e9a6  mov     rcx, [rbx]
0x18002e9a9  mov     [rsp+98h+var_58], r12
0x18002e9ae  mov     [rsp+98h+var_60], r15
0x18002e9b3  cmp     rbp, rdx
0x18002e9b6  jz      short loc_18002E9CF
0x18002e9b8  mov     rdx, rbp
0x18002e9bb  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<TASK_ENTRY> *,std::allocator<std::unique_ptr<TASK_ENTRY>>>(std::unique_ptr<TASK_ENTRY> * const,std::unique_ptr<TASK_ENTRY> * const,std::unique_ptr<TASK_ENTRY> *,std::allocator<std::unique_ptr<TASK_ENTRY>> &)
0x18002e9c0  mov     rdx, [rbx+8]
0x18002e9c4  mov     r8, r12
0x18002e9c7  mov     rcx, rbp
0x18002e9ca  mov     [rsp+98h+var_60], rsi
0x18002e9cf  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<TASK_ENTRY> *,std::allocator<std::unique_ptr<TASK_ENTRY>>>(std::unique_ptr<TASK_ENTRY> * const,std::unique_ptr<TASK_ENTRY> * const,std::unique_ptr<TASK_ENTRY> *,std::allocator<std::unique_ptr<TASK_ENTRY>> &)
0x18002e9d4  mov     rcx, [rbx]
0x18002e9d7  mov     [rsp+98h+var_70], 0
0x18002e9e0  test    rcx, rcx
0x18002e9e3  jz      short loc_18002EA01
0x18002e9e5  mov     rdx, [rbx+8]
0x18002e9e9  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<OPCODE_ENTRY>>>(std::unique_ptr<OPCODE_ENTRY> *,std::unique_ptr<OPCODE_ENTRY> * const,std::allocator<std::unique_ptr<OPCODE_ENTRY>> &)
0x18002e9ee  mov     rdx, [rbx+10h]
0x18002e9f2  sub     rdx, [rbx]
0x18002e9f5  mov     rcx, [rbx]
0x18002e9f8  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002e9fc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002ea01  mov     [rbx], rsi
0x18002ea04  lea     rcx, [rsi+r14*8]
0x18002ea08  mov     [rbx+8], rcx
0x18002ea0c  lea     rcx, [rsi+rdi*8]
0x18002ea10  mov     [rbx+10h], rcx
0x18002ea14  lea     rcx, [rsp+98h+var_78]
0x18002ea19  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<TASK_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002ea1e  mov     rax, r15
0x18002ea21  add     rsp, 58h
0x18002ea25  pop     r15
0x18002ea27  pop     r14
0x18002ea29  pop     r13
0x18002ea2b  pop     r12
0x18002ea2d  pop     rdi
0x18002ea2e  pop     rsi
0x18002ea2f  pop     rbp
0x18002ea30  pop     rbx
0x18002ea31  retn
```
