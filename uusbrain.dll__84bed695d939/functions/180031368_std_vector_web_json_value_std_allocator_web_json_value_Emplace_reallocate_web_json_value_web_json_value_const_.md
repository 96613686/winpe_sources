# std::vector<web::json::value,std::allocator<web::json::value>>::_Emplace_reallocate<web::json::value>(web::json::value * const,web::json::value &&)

- ea: `0x180031368`
- end: `0x1800314be`
- name: `??$_Emplace_reallocate@Vvalue@json@web@@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAPEAVvalue@json@web@@QEAV234@$$QEAV234@@Z`
- size: `342`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180030674`
- `0x180030b24`

## callees

- `0x18001dc18`
- `0x1800293d4`
- `0x1800294f0`
- `0x18002ae54`
- `0x18002af00`
- `0x180031368`

## pseudocode

```c
_QWORD *__fastcall std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(
        _QWORD *a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 v4; // rbp
  __int64 *v5; // rbx
  __int64 v6; // rax
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdi
  _QWORD *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  _QWORD *v15; // r14
  _QWORD *v16; // r8
  __int64 *v17; // r9
  __int64 *v18; // rcx
  _QWORD *v19; // r8
  __int64 v20; // rax
  _QWORD *v21; // r9
  __int64 v22; // rax
  __int64 *v23; // rcx
  __int64 v24; // rax
  _QWORD *v26; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 v27; // [rsp+30h] [rbp-58h]
  _QWORD *v28; // [rsp+38h] [rbp-50h]
  _QWORD *v29; // [rsp+40h] [rbp-48h]

  v4 = ((__int64)a2 - *a1) >> 3;
  v5 = a2;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<enum UusCapability>::_Xlength();
  v8 = v6 + 1;
  v9 = (__int64)(a1[2] - *a1) >> 3;
  v10 = v9 >> 1;
  if ( v9 <= 0x1FFFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v11 = v6 + 1;
    if ( v10 + v9 >= v8 )
      v11 = v10 + v9;
    if ( v11 > 0x1FFFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v11 = 0x1FFFFFFFFFFFFFFFLL;
  }
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v11);
  v13 = *a3;
  *a3 = 0;
  v14 = v12;
  v26 = a1;
  v15 = &v12[v4];
  v27 = v11;
  *v15 = v13;
  v16 = v15 + 1;
  v17 = (__int64 *)a1[1];
  v18 = (__int64 *)*a1;
  v29 = v15 + 1;
  v28 = v15;
  if ( v5 == v17 )
  {
    v19 = v12;
    while ( v18 != v17 )
    {
      v20 = *v18;
      *v18++ = 0;
      *v19++ = v20;
    }
  }
  else
  {
    v21 = v12;
    while ( v18 != v5 )
    {
      v22 = *v18;
      *v18++ = 0;
      *v21++ = v22;
    }
    v23 = (__int64 *)a1[1];
    v28 = v14;
    while ( v5 != v23 )
    {
      v24 = *v5;
      *v5++ = 0;
      *v16++ = v24;
    }
  }
  std::vector<web::json::value>::_Change_array(a1, v14, v8, v11, v26, 0, v27, v28, v29);
  std::vector<web::json::value>::_Reallocation_guard::~_Reallocation_guard(&v26);
  return v15;
}

```

## disassembly

```asm
0x180031368  push    rbx
0x18003136a  push    rbp
0x18003136b  push    rsi
0x18003136c  push    rdi
0x18003136d  push    r12
0x18003136f  push    r14
0x180031371  push    r15
0x180031373  sub     rsp, 50h
0x180031377  mov     rax, [rcx+8]
0x18003137b  mov     rbp, rdx
0x18003137e  sub     rbp, [rcx]
0x180031381  mov     r12, r8
0x180031384  sub     rax, [rcx]
0x180031387  mov     r8, 1FFFFFFFFFFFFFFFh
0x180031391  sar     rbp, 3
0x180031395  mov     rbx, rdx
0x180031398  sar     rax, 3
0x18003139c  mov     rsi, rcx
0x18003139f  cmp     rax, r8
0x1800313a2  jz      loc_1800314B2
0x1800313a8  mov     rcx, [rcx+10h]
0x1800313ac  lea     r15, [rax+1]
0x1800313b0  sub     rcx, [rsi]
0x1800313b3  mov     rax, r8
0x1800313b6  sar     rcx, 3
0x1800313ba  mov     rdx, rcx
0x1800313bd  shr     rdx, 1
0x1800313c0  sub     rax, rdx
0x1800313c3  cmp     rcx, rax
0x1800313c6  jbe     short loc_180031416
0x1800313c8  mov     rdi, r8
0x1800313cb  lea     rcx, ds:0[rdi*8]
0x1800313d3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800313d8  mov     rcx, [r12]
0x1800313dc  xor     r10d, r10d
0x1800313df  mov     [r12], r10
0x1800313e3  mov     rdx, rax
0x1800313e6  mov     [rsp+88h+var_68], rsi
0x1800313eb  lea     r14, [rax+rbp*8]
0x1800313ef  mov     [rsp+88h+var_58], rdi
0x1800313f4  mov     [r14], rcx
0x1800313f7  lea     r8, [r14+8]
0x1800313fb  mov     r9, [rsi+8]
0x1800313ff  mov     rcx, [rsi]
0x180031402  mov     [rsp+88h+var_48], r8
0x180031407  mov     [rsp+88h+var_50], r14
0x18003140c  cmp     rbx, r9
0x18003140f  jnz     short loc_180031447
0x180031411  mov     r8, rax
0x180031414  jmp     short loc_180031440
0x180031416  lea     rax, [rdx+rcx]
0x18003141a  mov     rdi, r15
0x18003141d  cmp     rax, r15
0x180031420  cmovnb  rdi, rax
0x180031424  cmp     rdi, r8
0x180031427  ja      loc_1800314B8
0x18003142d  jmp     short loc_1800313CB
0x18003142f  mov     rax, [rcx]
0x180031432  mov     [rcx], r10
0x180031435  add     rcx, 8
0x180031439  mov     [r8], rax
0x18003143c  lea     r8, [r8+8]
0x180031440  cmp     rcx, r9
0x180031443  jnz     short loc_18003142F
0x180031445  jmp     short loc_180031483
0x180031447  mov     r9, rdx
0x18003144a  jmp     short loc_18003145D
0x18003144c  mov     rax, [rcx]
0x18003144f  mov     [rcx], r10
0x180031452  add     rcx, 8
0x180031456  mov     [r9], rax
0x180031459  lea     r9, [r9+8]
0x18003145d  cmp     rcx, rbx
0x180031460  jnz     short loc_18003144C
0x180031462  mov     rcx, [rsi+8]
0x180031466  mov     [rsp+88h+var_50], rdx
0x18003146b  jmp     short loc_18003147E
0x18003146d  mov     rax, [rbx]
0x180031470  mov     [rbx], r10
0x180031473  add     rbx, 8
0x180031477  mov     [r8], rax
0x18003147a  lea     r8, [r8+8]
0x18003147e  cmp     rbx, rcx
0x180031481  jnz     short loc_18003146D
0x180031483  mov     r9, rdi
0x180031486  mov     [rsp+88h+var_60], r10
0x18003148b  mov     r8, r15
0x18003148e  mov     rcx, rsi
0x180031491  call    ?_Change_array@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAXQEAVvalue@json@web@@_K1@Z; std::vector<web::json::value>::_Change_array(web::json::value * const,unsigned __int64,unsigned __int64)
0x180031496  lea     rcx, [rsp+88h+var_68]
0x18003149b  call    ??1_Reallocation_guard@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAA@XZ; std::vector<web::json::value>::_Reallocation_guard::~_Reallocation_guard(void)
0x1800314a0  mov     rax, r14
0x1800314a3  add     rsp, 50h
0x1800314a7  pop     r15
0x1800314a9  pop     r14
0x1800314ab  pop     r12
0x1800314ad  pop     rdi
0x1800314ae  pop     rsi
0x1800314af  pop     rbp
0x1800314b0  pop     rbx
0x1800314b1  retn
0x1800314b2  call    ?_Xlength@?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@CAXXZ; std::vector<UusCapability>::_Xlength(void)
0x1800314b8  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
