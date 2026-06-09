# std::vector<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&,web::json::value &&)

- ea: `0x1800310f4`
- end: `0x180031362`
- name: `??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAVvalue@json@web@@@Z`
- size: `622`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int128 *, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180030358`
- `0x180030844`

## callees

- `0x18001dc18`
- `0x1800293d4`
- `0x1800294f0`
- `0x18002be9c`
- `0x18002bfa8`
- `0x1800310f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::wstring,web::json::value>(
        _QWORD *a1,
        _QWORD *a2,
        __int128 *a3,
        __int64 *a4)
{
  __int64 v8; // r14
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rbx
  _QWORD *v14; // r11
  _QWORD *v15; // r14
  _QWORD *v16; // r8
  __int128 v17; // xmm0
  __int64 v18; // rax
  _QWORD *v19; // r9
  __int64 v20; // rcx
  _QWORD *v21; // rdx
  __int64 v22; // rax
  _QWORD *v23; // rdx
  __int64 v24; // rax
  _QWORD *v25; // r9
  _QWORD *v26; // r10
  __int64 v27; // rax
  _QWORD *v29; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int64 v30; // [rsp+30h] [rbp-68h]
  _QWORD *v31; // [rsp+38h] [rbp-60h]
  _QWORD *v32; // [rsp+40h] [rbp-58h]

  v8 = ((__int64)a2 - *a1) / 40;
  v9 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[1] - *a1) >> 3);
  if ( v9 == 0x666666666666666LL )
    std::vector<enum UusCapability>::_Xlength();
  v10 = v9 + 1;
  v11 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[2] - *a1) >> 3);
  v12 = v11 >> 1;
  if ( v11 <= 0x666666666666666LL - (v11 >> 1) )
  {
    v13 = v10;
    if ( v12 - 0x3333333333333333LL * ((__int64)(a1[2] - *a1) >> 3) >= v10 )
      v13 = v12 - 0x3333333333333333LL * ((__int64)(a1[2] - *a1) >> 3);
    if ( v13 > 0x666666666666666LL )
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v13 = 0x666666666666666LL;
  }
  v29 = a1;
  v30 = v13;
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(40 * v13);
  v15 = &v14[5 * v8];
  *(_OWORD *)v15 = 0;
  v15[2] = 0;
  v15[3] = 0;
  v16 = v15 + 5;
  v17 = *a3;
  v32 = v15 + 5;
  v31 = v15;
  *(_OWORD *)v15 = v17;
  *((_OWORD *)v15 + 1) = a3[1];
  *((_QWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 3) = 7;
  *(_WORD *)a3 = 0;
  v18 = *a4;
  *a4 = 0;
  v15[4] = v18;
  v19 = (_QWORD *)a1[1];
  v20 = *a1;
  if ( a2 == v19 )
  {
    if ( (_QWORD *)v20 != v19 )
    {
      v21 = v14 + 3;
      do
      {
        *(_OWORD *)(v21 - 3) = 0;
        *(v21 - 1) = 0;
        *v21 = 0;
        v21 += 5;
        *((_OWORD *)v21 - 4) = *(_OWORD *)v20;
        *((_OWORD *)v21 - 3) = *(_OWORD *)(v20 + 16);
        *(_QWORD *)(v20 + 16) = 0;
        *(_QWORD *)(v20 + 24) = 7;
        *(_WORD *)v20 = 0;
        v22 = *(_QWORD *)(v20 + 32);
        *(_QWORD *)(v20 + 32) = 0;
        v20 += 40;
        *(v21 - 4) = v22;
      }
      while ( (_QWORD *)v20 != v19 );
    }
  }
  else
  {
    if ( (_QWORD *)v20 != a2 )
    {
      v23 = v14 + 3;
      do
      {
        *(_OWORD *)(v23 - 3) = 0;
        *(v23 - 1) = 0;
        *v23 = 0;
        v23 += 5;
        *((_OWORD *)v23 - 4) = *(_OWORD *)v20;
        *((_OWORD *)v23 - 3) = *(_OWORD *)(v20 + 16);
        *(_QWORD *)(v20 + 16) = 0;
        *(_QWORD *)(v20 + 24) = 7;
        *(_WORD *)v20 = 0;
        v24 = *(_QWORD *)(v20 + 32);
        *(_QWORD *)(v20 + 32) = 0;
        v20 += 40;
        *(v23 - 4) = v24;
      }
      while ( (_QWORD *)v20 != a2 );
    }
    v25 = (_QWORD *)a1[1];
    v31 = v14;
    if ( a2 != v25 )
    {
      v26 = a2 + 4;
      do
      {
        *(_OWORD *)v16 = 0;
        v16[2] = 0;
        v16[3] = 0;
        *(_OWORD *)v16 = *((_OWORD *)v26 - 2);
        v16 += 5;
        *(_OWORD *)(v16 - 3) = *((_OWORD *)v26 - 1);
        *(v26 - 2) = 0;
        *(v26 - 1) = 7;
        *((_WORD *)v26 - 16) = 0;
        v27 = *v26;
        *v26 = 0;
        v26 += 5;
        *(v16 - 1) = v27;
      }
      while ( v26 - 4 != v25 );
    }
  }
  std::vector<std::pair<std::wstring,web::json::value>>::_Change_array(a1, v14, v10, v13, v29, 0, v30, v31, v32);
  std::vector<std::pair<std::wstring,web::json::value>>::_Reallocation_guard::~_Reallocation_guard(&v29);
  return v15;
}

```

## disassembly

```asm
0x1800310f4  push    rbx
0x1800310f6  push    rbp
0x1800310f7  push    rsi
0x1800310f8  push    rdi
0x1800310f9  push    r12
0x1800310fb  push    r13
0x1800310fd  push    r14
0x1800310ff  push    r15
0x180031101  sub     rsp, 58h
0x180031105  mov     rsi, rcx
0x180031108  mov     rax, 6666666666666667h
0x180031112  mov     rcx, rdx
0x180031115  mov     rdi, rdx
0x180031118  mov     r15, r8
0x18003111b  mov     r12, r9
0x18003111e  mov     r8, 666666666666666h
0x180031128  sub     rcx, [rsi]
0x18003112b  mov     rbp, [rsi+8]
0x18003112f  sub     rbp, [rsi]
0x180031132  imul    rcx
0x180031135  sar     rbp, 3
0x180031139  mov     r14, rdx
0x18003113c  sar     r14, 4
0x180031140  mov     rax, r14
0x180031143  shr     rax, 3Fh
0x180031147  add     r14, rax
0x18003114a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180031154  imul    rbp, rax
0x180031158  cmp     rbp, r8
0x18003115b  jz      loc_180031356
0x180031161  mov     rcx, [rsi+10h]
0x180031165  inc     rbp
0x180031168  sub     rcx, [rsi]
0x18003116b  sar     rcx, 3
0x18003116f  imul    rcx, rax
0x180031173  mov     rax, r8
0x180031176  mov     rdx, rcx
0x180031179  shr     rdx, 1
0x18003117c  sub     rax, rdx
0x18003117f  cmp     rcx, rax
0x180031182  jbe     loc_18003125B
0x180031188  mov     rbx, r8
0x18003118b  lea     rcx, [rbx+rbx*4]
0x18003118f  shl     rcx, 3
0x180031193  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180031198  xor     r13d, r13d
0x18003119b  mov     [rsp+98h+var_78], rsi
0x1800311a0  lea     rcx, [r14+r14*4]
0x1800311a4  mov     [rsp+98h+var_68], rbx
0x1800311a9  xorps   xmm0, xmm0
0x1800311ac  mov     r11, rax
0x1800311af  lea     r14, [rax+rcx*8]
0x1800311b3  movups  xmmword ptr [r14], xmm0
0x1800311b7  mov     [r14+10h], r13
0x1800311bb  lea     r10d, [r13+7]
0x1800311bf  mov     [r14+18h], r13
0x1800311c3  lea     r8, [r14+28h]
0x1800311c7  movups  xmm0, xmmword ptr [r15]
0x1800311cb  mov     [rsp+98h+var_58], r8
0x1800311d0  mov     [rsp+98h+var_60], r14
0x1800311d5  movups  xmmword ptr [r14], xmm0
0x1800311d9  movups  xmm1, xmmword ptr [r15+10h]
0x1800311de  movups  xmmword ptr [r14+10h], xmm1
0x1800311e3  mov     [r15+10h], r13
0x1800311e7  mov     [r15+18h], r10
0x1800311eb  mov     [r15], r13w
0x1800311ef  mov     rax, [r12]
0x1800311f3  mov     [r12], r13
0x1800311f7  mov     [r14+20h], rax
0x1800311fb  mov     r9, [rsi+8]
0x1800311ff  mov     rcx, [rsi]
0x180031202  cmp     rdi, r9
0x180031205  jnz     short loc_180031277
0x180031207  cmp     rcx, r9
0x18003120a  jz      loc_180031322
0x180031210  lea     rdx, [r11+18h]
0x180031214  xorps   xmm0, xmm0
0x180031217  movups  xmmword ptr [rdx-18h], xmm0
0x18003121b  mov     [rdx-8], r13
0x18003121f  mov     [rdx], r13
0x180031222  lea     rdx, [rdx+28h]
0x180031226  movups  xmm0, xmmword ptr [rcx]
0x180031229  movups  xmmword ptr [rdx-40h], xmm0
0x18003122d  movups  xmm1, xmmword ptr [rcx+10h]
0x180031231  movups  xmmword ptr [rdx-30h], xmm1
0x180031235  mov     [rcx+10h], r13
0x180031239  mov     [rcx+18h], r10
0x18003123d  mov     [rcx], r13w
0x180031241  mov     rax, [rcx+20h]
0x180031245  mov     [rcx+20h], r13
0x180031249  add     rcx, 28h ; '('
0x18003124d  mov     [rdx-20h], rax
0x180031251  cmp     rcx, r9
0x180031254  jnz     short loc_180031214
0x180031256  jmp     loc_180031322
0x18003125b  lea     rax, [rdx+rcx]
0x18003125f  mov     rbx, rbp
0x180031262  cmp     rax, rbp
0x180031265  cmovnb  rbx, rax
0x180031269  cmp     rbx, r8
0x18003126c  ja      loc_18003135C
0x180031272  jmp     loc_18003118B
0x180031277  cmp     rcx, rdi
0x18003127a  jz      short loc_1800312C2
0x18003127c  lea     rdx, [r11+18h]
0x180031280  xorps   xmm0, xmm0
0x180031283  movups  xmmword ptr [rdx-18h], xmm0
0x180031287  mov     [rdx-8], r13
0x18003128b  mov     [rdx], r13
0x18003128e  lea     rdx, [rdx+28h]
0x180031292  movups  xmm0, xmmword ptr [rcx]
0x180031295  movups  xmmword ptr [rdx-40h], xmm0
0x180031299  movups  xmm1, xmmword ptr [rcx+10h]
0x18003129d  movups  xmmword ptr [rdx-30h], xmm1
0x1800312a1  mov     [rcx+10h], r13
0x1800312a5  mov     [rcx+18h], r10
0x1800312a9  mov     [rcx], r13w
0x1800312ad  mov     rax, [rcx+20h]
0x1800312b1  mov     [rcx+20h], r13
0x1800312b5  add     rcx, 28h ; '('
0x1800312b9  mov     [rdx-20h], rax
0x1800312bd  cmp     rcx, rdi
0x1800312c0  jnz     short loc_180031280
0x1800312c2  mov     r9, [rsi+8]
0x1800312c6  mov     [rsp+98h+var_60], r11
0x1800312cb  cmp     rdi, r9
0x1800312ce  jz      short loc_180031322
0x1800312d0  lea     r10, [rdi+20h]
0x1800312d4  xorps   xmm0, xmm0
0x1800312d7  movups  xmmword ptr [r8], xmm0
0x1800312db  mov     [r8+10h], r13
0x1800312df  mov     [r8+18h], r13
0x1800312e3  movups  xmm0, xmmword ptr [r10-20h]
0x1800312e8  movups  xmmword ptr [r8], xmm0
0x1800312ec  lea     r8, [r8+28h]
0x1800312f0  movups  xmm1, xmmword ptr [r10-10h]
0x1800312f5  movups  xmmword ptr [r8-18h], xmm1
0x1800312fa  mov     [r10-10h], r13
0x1800312fe  mov     qword ptr [r10-8], 7
0x180031306  mov     [r10-20h], r13w
0x18003130b  mov     rax, [r10]
0x18003130e  mov     [r10], r13
0x180031311  lea     r10, [r10+28h]
0x180031315  lea     rdx, [r10-20h]
0x180031319  mov     [r8-8], rax
0x18003131d  cmp     rdx, r9
0x180031320  jnz     short loc_1800312D4
0x180031322  mov     r9, rbx
0x180031325  mov     [rsp+98h+var_70], r13
0x18003132a  mov     r8, rbp
0x18003132d  mov     rdx, r11
0x180031330  mov     rcx, rsi
0x180031333  call    ?_Change_array@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAXQEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@2@_K1@Z; std::vector<std::pair<std::wstring,web::json::value>>::_Change_array(std::pair<std::wstring,web::json::value> * const,unsigned __int64,unsigned __int64)
0x180031338  lea     rcx, [rsp+98h+var_78]
0x18003133d  call    ??1_Reallocation_guard@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,web::json::value>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180031342  mov     rax, r14
0x180031345  add     rsp, 58h
0x180031349  pop     r15
0x18003134b  pop     r14
0x18003134d  pop     r13
0x18003134f  pop     r12
0x180031351  pop     rdi
0x180031352  pop     rsi
0x180031353  pop     rbp
0x180031354  pop     rbx
0x180031355  retn
0x180031356  call    ?_Xlength@?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@CAXXZ; std::vector<UusCapability>::_Xlength(void)
0x18003135c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
