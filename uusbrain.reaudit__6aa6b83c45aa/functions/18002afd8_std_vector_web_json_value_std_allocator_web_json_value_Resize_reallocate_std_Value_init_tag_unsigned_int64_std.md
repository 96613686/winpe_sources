# std::vector<web::json::value,std::allocator<web::json::value>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18002afd8`
- end: `0x18002b111`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002b170`

## callees

- `0x18001dc18`
- `0x1800293d4`
- `0x1800294f0`
- `0x1800296cc`
- `0x18002ae54`
- `0x18002af00`
- `0x18002afd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::vector<web::json::value>::_Resize_reallocate<std::_Value_init_tag>(
        __int64 **a1,
        unsigned __int64 a2)
{
  __int64 v4; // r13
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rbx
  __int64 v8; // r12
  web::json::value *v9; // rdi
  unsigned __int64 v10; // r15
  __int64 *v11; // r8
  _QWORD *v12; // rcx
  __int64 *i; // rdx
  __int64 v14; // rax
  web::json::value *v16; // [rsp+28h] [rbp-38h]
  _QWORD v17[4]; // [rsp+38h] [rbp-28h] BYREF
  web::json::value *v18; // [rsp+58h] [rbp-8h]

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<enum UusCapability>::_Xlength();
  v4 = a1[1] - *a1;
  v5 = a1[2] - *a1;
  v6 = v5 >> 1;
  if ( v5 <= 0x1FFFFFFFFFFFFFFFLL - (v5 >> 1) )
  {
    v7 = v6 + v5;
    if ( v6 + v5 >= a2 )
    {
      if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
        __scrt_throw_std_bad_array_new_length();
    }
    else
    {
      v7 = a2;
    }
  }
  else
  {
    v7 = 0x1FFFFFFFFFFFFFFFLL;
  }
  v8 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v7);
  v9 = (web::json::value *)(v8 + 8 * v4);
  v17[0] = a1;
  v17[1] = v8;
  v17[2] = v7;
  v17[3] = v9;
  v18 = v9;
  v16 = v9;
  v10 = a2 - v4;
  if ( a2 != v4 )
  {
    do
    {
      web::json::value::value(v9);
      v9 = (web::json::value *)((char *)v9 + 8);
      v16 = v9;
      --v10;
    }
    while ( v10 );
  }
  v18 = v9;
  v11 = a1[1];
  v12 = (_QWORD *)v8;
  for ( i = *a1; i != v11; ++i )
  {
    v14 = *i;
    *i = 0;
    *v12++ = v14;
  }
  std::vector<web::json::value>::_Change_array(a1, v8, a2, v7, v8 + 8 * v4, v16, a1, v17[0], 0);
  return std::vector<web::json::value>::_Reallocation_guard::~_Reallocation_guard(v17);
}

```

## disassembly

```asm
0x18002afd8  mov     [rsp-38h+arg_10], rbx
0x18002afdd  push    rbp
0x18002afde  push    rsi
0x18002afdf  push    rdi
0x18002afe0  push    r12
0x18002afe2  push    r13
0x18002afe4  push    r14
0x18002afe6  push    r15
0x18002afe8  mov     rbp, rsp
0x18002afeb  sub     rsp, 60h
0x18002afef  mov     rsi, rdx
0x18002aff2  mov     r14, rcx
0x18002aff5  mov     r8, 1FFFFFFFFFFFFFFFh
0x18002afff  cmp     rdx, r8
0x18002b002  ja      loc_18002B105
0x18002b008  mov     r13, [rcx+8]
0x18002b00c  sub     r13, [rcx]
0x18002b00f  sar     r13, 3
0x18002b013  mov     rcx, [rcx+10h]
0x18002b017  sub     rcx, [r14]
0x18002b01a  sar     rcx, 3
0x18002b01e  mov     rdx, rcx
0x18002b021  shr     rdx, 1
0x18002b024  mov     rax, r8
0x18002b027  sub     rax, rdx
0x18002b02a  cmp     rcx, rax
0x18002b02d  jbe     short loc_18002B09B
0x18002b02f  mov     rbx, r8
0x18002b032  lea     rcx, ds:0[rbx*8]
0x18002b03a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002b03f  mov     r12, rax
0x18002b042  lea     rdi, [rax+r13*8]
0x18002b046  mov     [rbp+var_28], r14
0x18002b04a  mov     [rbp+var_20], rax
0x18002b04e  mov     [rbp+var_18], rbx
0x18002b052  mov     [rbp+var_10], rdi
0x18002b056  mov     [rbp+var_8], rdi
0x18002b05a  mov     r15, rsi
0x18002b05d  xorps   xmm0, xmm0
0x18002b060  movups  [rbp+var_40], xmm0
0x18002b064  mov     qword ptr [rbp+var_40], rdi
0x18002b068  mov     qword ptr [rbp+var_40+8], rdi
0x18002b06c  mov     [rbp+var_30], r14
0x18002b070  sub     r15, r13
0x18002b073  jz      short loc_18002B08B
0x18002b075  mov     rcx, rdi; this
0x18002b078  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x18002b07d  add     rdi, 8
0x18002b081  mov     qword ptr [rbp+var_40+8], rdi
0x18002b085  sub     r15, 1
0x18002b089  jnz     short loc_18002B075
0x18002b08b  mov     [rbp+var_8], rdi
0x18002b08f  mov     r8, [r14+8]
0x18002b093  mov     rcx, r12
0x18002b096  mov     rdx, [r14]
0x18002b099  jmp     short loc_18002B0C5
0x18002b09b  lea     rbx, [rdx+rcx]
0x18002b09f  cmp     rbx, rsi
0x18002b0a2  jnb     short loc_18002B0A9
0x18002b0a4  mov     rbx, rsi
0x18002b0a7  jmp     short loc_18002B032
0x18002b0a9  cmp     rbx, r8
0x18002b0ac  ja      short loc_18002B10B
0x18002b0ae  jmp     short loc_18002B032
0x18002b0b0  mov     rax, [rdx]
0x18002b0b3  mov     qword ptr [rdx], 0
0x18002b0ba  mov     [rcx], rax
0x18002b0bd  lea     rcx, [rcx+8]
0x18002b0c1  add     rdx, 8
0x18002b0c5  cmp     rdx, r8
0x18002b0c8  jnz     short loc_18002B0B0
0x18002b0ca  mov     [rbp+var_20], 0
0x18002b0d2  mov     r9, rbx
0x18002b0d5  mov     r8, rsi
0x18002b0d8  mov     rdx, r12
0x18002b0db  mov     rcx, r14
0x18002b0de  call    ?_Change_array@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAXQEAVvalue@json@web@@_K1@Z; std::vector<web::json::value>::_Change_array(web::json::value * const,unsigned __int64,unsigned __int64)
0x18002b0e3  nop
0x18002b0e4  lea     rcx, [rbp+var_28]
0x18002b0e8  call    ??1_Reallocation_guard@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAA@XZ; std::vector<web::json::value>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002b0ed  mov     rbx, [rsp+60h+arg_10]
0x18002b0f5  add     rsp, 60h
0x18002b0f9  pop     r15
0x18002b0fb  pop     r14
0x18002b0fd  pop     r13
0x18002b0ff  pop     r12
0x18002b101  pop     rdi
0x18002b102  pop     rsi
0x18002b103  pop     rbp
0x18002b104  retn
0x18002b105  call    ?_Xlength@?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@CAXXZ; std::vector<UusCapability>::_Xlength(void)
0x18002b10b  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
