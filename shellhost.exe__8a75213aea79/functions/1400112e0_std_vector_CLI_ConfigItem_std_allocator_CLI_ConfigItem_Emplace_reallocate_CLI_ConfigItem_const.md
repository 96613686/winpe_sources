# std::vector<CLI::ConfigItem,std::allocator<CLI::ConfigItem>>::_Emplace_reallocate<>(CLI::ConfigItem * const)

- ea: `0x1400112e0`
- end: `0x1400114dc`
- name: `??$_Emplace_reallocate@$$V@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAPEAUConfigItem@CLI@@QEAU23@@Z`
- size: `508`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140029950`
- `0x14002df60`

## callees

- `0x14000f804`
- `0x1400112e0`
- `0x140013ac0`
- `0x14001a980`
- `0x14001f2e0`
- `0x140020300`
- `0x14004a9e0`

## pseudocode

```c
char *__fastcall std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(_QWORD *a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 v5; // r8
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  __int64 v8; // rbp
  unsigned __int64 v9; // rdi
  size_t v10; // rcx
  _QWORD *v11; // rbx
  void *v12; // rax
  _QWORD *v13; // r9
  char *v14; // r14
  _QWORD *v15; // r15
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v19; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+28h] [rbp-50h]
  unsigned __int64 v21; // [rsp+30h] [rbp-48h]
  _QWORD *v22; // [rsp+38h] [rbp-40h]
  char *v23; // [rsp+40h] [rbp-38h]

  v2 = *a1;
  v5 = (a1[1] - *a1) / 80LL;
  if ( v5 == 0x333333333333333LL )
    std::vector<std::shared_ptr<CLI::App>>::_Xlength(a1);
  v6 = (a1[2] - v2) / 80;
  v7 = v6 >> 1;
  if ( v6 > 0x333333333333333LL - (v6 >> 1) )
    goto LABEL_19;
  v8 = v5 + 1;
  v9 = v5 + 1;
  if ( v6 + v7 >= v5 + 1 )
    v9 = v6 + v7;
  if ( v9 > 0x333333333333333LL )
    goto LABEL_19;
  v10 = 80 * v9;
  if ( !(80 * v9) )
  {
    v11 = 0;
    goto LABEL_14;
  }
  if ( v10 < 0x1000 )
  {
    v11 = operator new(v10);
    goto LABEL_14;
  }
  if ( v10 + 39 < v10 )
LABEL_19:
    std::_Throw_bad_array_new_length();
  v12 = operator new(v10 + 39);
  if ( !v12 )
    __fastfail(5u);
  v11 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v11 - 1) = v12;
LABEL_14:
  v19 = a1;
  v21 = v9;
  v13 = a1;
  v14 = (char *)&v11[10 * ((a2 - v2) / 80)];
  v22 = v14;
  *(_QWORD *)v14 = 0;
  v15 = v14 + 80;
  *((_QWORD *)v14 + 1) = 0;
  *((_QWORD *)v14 + 2) = 0;
  *(_OWORD *)(v14 + 24) = 0;
  *((_QWORD *)v14 + 5) = 0;
  *((_QWORD *)v14 + 6) = 15;
  v14[24] = 0;
  *((_QWORD *)v14 + 7) = 0;
  *((_QWORD *)v14 + 8) = 0;
  *((_QWORD *)v14 + 9) = 0;
  v16 = a1[1];
  v17 = *a1;
  v23 = v14 + 80;
  if ( a2 == v16 )
  {
    v15 = v11;
  }
  else
  {
    std::_Uninitialized_move<CLI::ConfigItem *>(v17, a2, v11, a1, v19, v20, v21, v22, v23);
    v16 = a1[1];
    v17 = a2;
    v13 = a1;
    v22 = v11;
  }
  std::_Uninitialized_move<CLI::ConfigItem *>(v17, v16, v15, v13, v19, v20, v21, v22, v23);
  v20 = 0;
  std::vector<CLI::ConfigItem>::_Change_array(a1, v11, v8, v9);
  std::vector<CLI::ConfigItem>::_Reallocation_guard::~_Reallocation_guard(&v19);
  return v14;
}

```

## disassembly

```asm
0x1400112e0  mov     r11, rsp
0x1400112e3  push    rsi
0x1400112e4  push    r12
0x1400112e6  push    r14
0x1400112e8  push    r15
0x1400112ea  sub     rsp, 58h
0x1400112ee  mov     r14, [rcx]
0x1400112f1  mov     r15, 6666666666666667h
0x1400112fb  mov     r8, [rcx+8]
0x1400112ff  mov     rax, r15
0x140011302  sub     r8, r14
0x140011305  mov     r12, rdx
0x140011308  imul    r8
0x14001130b  mov     r9, 333333333333333h
0x140011315  mov     rsi, rcx
0x140011318  mov     r8, rdx
0x14001131b  sar     r8, 5
0x14001131f  mov     rax, r8
0x140011322  shr     rax, 3Fh
0x140011326  add     r8, rax
0x140011329  cmp     r8, r9
0x14001132c  jz      loc_1400114D0
0x140011332  mov     rcx, [rcx+10h]
0x140011336  mov     rax, r15
0x140011339  sub     rcx, r14
0x14001133c  mov     [r11+8], rbx
0x140011340  imul    rcx
0x140011343  mov     [r11+10h], rbp
0x140011347  sar     rdx, 5
0x14001134b  mov     rax, rdx
0x14001134e  mov     [r11+18h], rdi
0x140011352  shr     rax, 3Fh
0x140011356  add     rdx, rax
0x140011359  mov     [r11-28h], r13
0x14001135d  mov     rcx, rdx
0x140011360  mov     rax, r9
0x140011363  shr     rcx, 1
0x140011366  sub     rax, rcx
0x140011369  cmp     rdx, rax
0x14001136c  ja      loc_1400114D6
0x140011372  lea     rbp, [r8+1]
0x140011376  lea     rax, [rdx+rcx]
0x14001137a  mov     rdi, rbp
0x14001137d  cmp     rax, rbp
0x140011380  cmovnb  rdi, rax
0x140011384  cmp     rdi, r9
0x140011387  ja      loc_1400114D6
0x14001138d  lea     rcx, [rdi+rdi*4]
0x140011391  xor     r13d, r13d
0x140011394  shl     rcx, 4; Size
0x140011398  test    rcx, rcx
0x14001139b  jnz     short loc_1400113A2
0x14001139d  mov     ebx, r13d
0x1400113a0  jmp     short loc_1400113E2
0x1400113a2  cmp     rcx, 1000h
0x1400113a9  jb      short loc_1400113DA
0x1400113ab  lea     rax, [rcx+27h]
0x1400113af  cmp     rax, rcx
0x1400113b2  jbe     loc_1400114D6
0x1400113b8  mov     rcx, rax; Size
0x1400113bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400113c0  test    rax, rax
0x1400113c3  jnz     short loc_1400113CC
0x1400113c5  mov     ecx, 5
0x1400113ca  int     29h; Win8: RtlFailFast(ecx)
0x1400113cc  lea     rbx, [rax+27h]
0x1400113d0  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1400113d4  mov     [rbx-8], rax
0x1400113d8  jmp     short loc_1400113E2
0x1400113da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400113df  mov     rbx, rax
0x1400113e2  mov     rax, r15
0x1400113e5  mov     [rsp+78h+var_58], rsi
0x1400113ea  mov     rcx, r12
0x1400113ed  mov     [rsp+78h+var_48], rdi
0x1400113f2  sub     rcx, r14
0x1400113f5  xorps   xmm0, xmm0
0x1400113f8  imul    rcx
0x1400113fb  mov     r9, rsi
0x1400113fe  sar     rdx, 5
0x140011402  mov     rcx, rdx
0x140011405  shr     rcx, 3Fh
0x140011409  add     rdx, rcx
0x14001140c  lea     r14, [rdx+rdx*4]
0x140011410  shl     r14, 4
0x140011414  add     r14, rbx
0x140011417  mov     [rsp+78h+var_40], r14
0x14001141c  mov     [r14], r13
0x14001141f  lea     r15, [r14+50h]
0x140011423  mov     [r14+8], r13
0x140011427  mov     [r14+10h], r13
0x14001142b  movups  xmmword ptr [r14+18h], xmm0
0x140011430  mov     [r14+28h], r13
0x140011434  mov     qword ptr [r14+30h], 0Fh
0x14001143c  mov     [r14+18h], r13b
0x140011440  mov     [r14+38h], r13
0x140011444  mov     [r14+40h], r13
0x140011448  mov     [r14+48h], r13
0x14001144c  mov     rdx, [rsi+8]
0x140011450  mov     rcx, [rsi]
0x140011453  mov     [rsp+78h+var_38], r15
0x140011458  cmp     r12, rdx
0x14001145b  jnz     short loc_140011462
0x14001145d  mov     r15, rbx
0x140011460  jmp     short loc_14001147C
0x140011462  mov     r8, rbx
0x140011465  mov     rdx, r12
0x140011468  call    ??$_Uninitialized_move@PEAUConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@YAPEAUConfigItem@CLI@@QEAU12@0PEAU12@AEAV?$allocator@UConfigItem@CLI@@@0@@Z; std::_Uninitialized_move<CLI::ConfigItem *>(CLI::ConfigItem * const,CLI::ConfigItem * const,CLI::ConfigItem *,std::allocator<CLI::ConfigItem> &)
0x14001146d  mov     rdx, [rsi+8]
0x140011471  mov     rcx, r12
0x140011474  mov     r9, rsi
0x140011477  mov     [rsp+78h+var_40], rbx
0x14001147c  mov     r8, r15
0x14001147f  call    ??$_Uninitialized_move@PEAUConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@YAPEAUConfigItem@CLI@@QEAU12@0PEAU12@AEAV?$allocator@UConfigItem@CLI@@@0@@Z; std::_Uninitialized_move<CLI::ConfigItem *>(CLI::ConfigItem * const,CLI::ConfigItem * const,CLI::ConfigItem *,std::allocator<CLI::ConfigItem> &)
0x140011484  mov     r9, rdi
0x140011487  mov     [rsp+78h+var_50], r13
0x14001148c  mov     r8, rbp
0x14001148f  mov     rdx, rbx
0x140011492  mov     rcx, rsi
0x140011495  call    ?_Change_array@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAXQEAUConfigItem@CLI@@_K1@Z; std::vector<CLI::ConfigItem>::_Change_array(CLI::ConfigItem * const,unsigned __int64,unsigned __int64)
0x14001149a  lea     rcx, [rsp+78h+var_58]
0x14001149f  call    ??1_Reallocation_guard@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@QEAA@XZ; std::vector<CLI::ConfigItem>::_Reallocation_guard::~_Reallocation_guard(void)
0x1400114a4  mov     rdi, [rsp+78h+arg_10]
0x1400114ac  mov     rax, r14
0x1400114af  mov     rbp, [rsp+78h+arg_8]
0x1400114b7  mov     rbx, [rsp+78h+arg_0]
0x1400114bf  mov     r13, [rsp+78h+var_28]
0x1400114c4  add     rsp, 58h
0x1400114c8  pop     r15
0x1400114ca  pop     r14
0x1400114cc  pop     r12
0x1400114ce  pop     rsi
0x1400114cf  retn
0x1400114d0  call    ?_Xlength@?$vector@V?$shared_ptr@VApp@CLI@@@std@@V?$allocator@V?$shared_ptr@VApp@CLI@@@std@@@2@@std@@CAXXZ; std::vector<std::shared_ptr<CLI::App>>::_Xlength(void)
0x1400114d6  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
