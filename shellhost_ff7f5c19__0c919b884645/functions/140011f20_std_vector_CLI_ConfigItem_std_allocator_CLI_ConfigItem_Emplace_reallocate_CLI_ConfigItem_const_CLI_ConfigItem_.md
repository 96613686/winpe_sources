# std::vector<CLI::ConfigItem,std::allocator<CLI::ConfigItem>>::_Emplace_reallocate<CLI::ConfigItem const &>(CLI::ConfigItem * const,CLI::ConfigItem const &)

- ea: `0x140011f20`
- end: `0x140012106`
- name: `??$_Emplace_reallocate@AEBUConfigItem@CLI@@@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAPEAUConfigItem@CLI@@QEAU23@AEBU23@@Z`
- size: `486`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140029950`
- `0x14002df60`

## callees

- `0x140008a50`
- `0x14000f804`
- `0x140011f20`
- `0x140013ac0`
- `0x14001a980`
- `0x14001f2e0`
- `0x140020300`
- `0x14004a9e0`
- `0x140052264`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall std::vector<CLI::ConfigItem>::_Emplace_reallocate<CLI::ConfigItem const &>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r14
  __int64 v7; // r9
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  __int64 v10; // rbp
  unsigned __int64 v11; // rdi
  size_t v12; // rcx
  _QWORD *v13; // rbx
  void *v14; // rax
  char *v15; // r15
  _QWORD *v16; // r14
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // r9
  _QWORD *v21; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v22; // [rsp+28h] [rbp-70h]
  unsigned __int64 v23; // [rsp+30h] [rbp-68h]
  _QWORD *v24; // [rsp+38h] [rbp-60h]
  char *v25; // [rsp+40h] [rbp-58h]

  v6 = *a1;
  v7 = (a1[1] - *a1) / 80LL;
  if ( v7 == 0x333333333333333LL )
    std::vector<std::shared_ptr<CLI::App>>::_Xlength();
  v8 = (a1[2] - v6) / 80;
  v9 = v8 >> 1;
  if ( v8 > 0x333333333333333LL - (v8 >> 1) )
    goto LABEL_19;
  v10 = v7 + 1;
  v11 = v7 + 1;
  if ( v8 + v9 >= v7 + 1 )
    v11 = v8 + v9;
  if ( v11 > 0x333333333333333LL )
    goto LABEL_19;
  v12 = 80 * v11;
  if ( !(80 * v11) )
  {
    v13 = 0;
    goto LABEL_14;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(v12);
    goto LABEL_14;
  }
  if ( v12 + 39 < v12 )
LABEL_19:
    std::_Throw_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    __fastfail(5u);
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_14:
  v15 = (char *)&v13[10 * ((a2 - v6) / 80)];
  v16 = v15 + 80;
  v21 = a1;
  v22 = v13;
  v23 = v11;
  v25 = v15 + 80;
  std::vector<std::string>::vector<std::string>(v15, a3);
  std::string::string(v15 + 24, a3 + 24);
  std::vector<std::string>::vector<std::string>(v15 + 56, a3 + 56);
  v24 = v15;
  v17 = a1[1];
  v18 = *a1;
  v19 = a1;
  if ( a2 == v17 )
  {
    v16 = v13;
  }
  else
  {
    std::_Uninitialized_move<CLI::ConfigItem *>(v18, a2, v13, a1, v21, v22, v23, v24, v25);
    v24 = v13;
    v18 = a2;
    v17 = a1[1];
    v19 = a1;
  }
  std::_Uninitialized_move<CLI::ConfigItem *>(v18, v17, v16, v19, v21, v22, v23, v24, v25);
  v22 = 0;
  std::vector<CLI::ConfigItem>::_Change_array(a1, v13, v10, v11);
  std::vector<CLI::ConfigItem>::_Reallocation_guard::~_Reallocation_guard(&v21);
  return v15;
}

```

## disassembly

```asm
0x140011f20  push    rbx
0x140011f22  push    rbp
0x140011f23  push    rsi
0x140011f24  push    rdi
0x140011f25  push    r12
0x140011f27  push    r13
0x140011f29  push    r14
0x140011f2b  push    r15
0x140011f2d  sub     rsp, 58h
0x140011f31  mov     r13, r8
0x140011f34  mov     r12, rdx
0x140011f37  mov     rsi, rcx
0x140011f3a  mov     r14, [rcx]
0x140011f3d  mov     r9, [rcx+8]
0x140011f41  sub     r9, r14
0x140011f44  mov     r15, 6666666666666667h
0x140011f4e  mov     rax, r15
0x140011f51  imul    r9
0x140011f54  mov     r9, rdx
0x140011f57  sar     r9, 5
0x140011f5b  mov     rax, r9
0x140011f5e  shr     rax, 3Fh
0x140011f62  add     r9, rax
0x140011f65  mov     r8, 333333333333333h
0x140011f6f  cmp     r9, r8
0x140011f72  jz      loc_1400120FA
0x140011f78  mov     rcx, [rcx+10h]
0x140011f7c  sub     rcx, r14
0x140011f7f  mov     rax, r15
0x140011f82  imul    rcx
0x140011f85  sar     rdx, 5
0x140011f89  mov     rax, rdx
0x140011f8c  shr     rax, 3Fh
0x140011f90  add     rdx, rax
0x140011f93  mov     rcx, rdx
0x140011f96  shr     rcx, 1
0x140011f99  mov     rax, r8
0x140011f9c  sub     rax, rcx
0x140011f9f  cmp     rdx, rax
0x140011fa2  ja      loc_140012100
0x140011fa8  lea     rbp, [r9+1]
0x140011fac  lea     rax, [rdx+rcx]
0x140011fb0  mov     rdi, rbp
0x140011fb3  cmp     rax, rbp
0x140011fb6  cmovnb  rdi, rax
0x140011fba  cmp     rdi, r8
0x140011fbd  ja      loc_140012100
0x140011fc3  lea     rcx, [rdi+rdi*4]
0x140011fc7  shl     rcx, 4; Size
0x140011fcb  test    rcx, rcx
0x140011fce  jnz     short loc_140011FD4
0x140011fd0  xor     ebx, ebx
0x140011fd2  jmp     short loc_140012014
0x140011fd4  cmp     rcx, 1000h
0x140011fdb  jb      short loc_14001200C
0x140011fdd  lea     rax, [rcx+27h]
0x140011fe1  cmp     rax, rcx
0x140011fe4  jbe     loc_140012100
0x140011fea  mov     rcx, rax; Size
0x140011fed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140011ff2  test    rax, rax
0x140011ff5  jnz     short loc_140011FFE
0x140011ff7  mov     ecx, 5
0x140011ffc  int     29h; Win8: RtlFailFast(ecx)
0x140011ffe  lea     rbx, [rax+27h]
0x140012002  and     rbx, 0FFFFFFFFFFFFFFE0h
0x140012006  mov     [rbx-8], rax
0x14001200a  jmp     short loc_140012014
0x14001200c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012011  mov     rbx, rax
0x140012014  mov     rcx, r12
0x140012017  sub     rcx, r14
0x14001201a  mov     rax, r15
0x14001201d  imul    rcx
0x140012020  sar     rdx, 5
0x140012024  mov     rcx, rdx
0x140012027  shr     rcx, 3Fh
0x14001202b  add     rdx, rcx
0x14001202e  lea     r15, [rdx+rdx*4]
0x140012032  shl     r15, 4
0x140012036  add     r15, rbx
0x140012039  lea     r14, [r15+50h]
0x14001203d  mov     [rsp+98h+var_78], rsi
0x140012042  mov     [rsp+98h+var_70], rbx
0x140012047  mov     [rsp+98h+var_68], rdi
0x14001204c  mov     [rsp+98h+var_60], r14
0x140012051  mov     [rsp+98h+var_58], r14
0x140012056  mov     [rsp+98h+arg_0], r15
0x14001205e  mov     rdx, r13
0x140012061  mov     rcx, r15
0x140012064  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::string>::vector<std::string>(std::vector<std::string> const &)
0x140012069  nop
0x14001206a  lea     rdx, [r13+18h]
0x14001206e  lea     rcx, [r15+18h]
0x140012072  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140012077  nop
0x140012078  lea     rdx, [r13+38h]
0x14001207c  lea     rcx, [r15+38h]
0x140012080  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::string>::vector<std::string>(std::vector<std::string> const &)
0x140012085  nop
0x140012086  mov     [rsp+98h+var_60], r15
0x14001208b  mov     rdx, [rsi+8]
0x14001208f  mov     rcx, [rsi]
0x140012092  mov     r9, rsi
0x140012095  cmp     r12, rdx
0x140012098  jnz     short loc_14001209F
0x14001209a  mov     r14, rbx
0x14001209d  jmp     short loc_1400120B9
0x14001209f  mov     r8, rbx
0x1400120a2  mov     rdx, r12
0x1400120a5  call    ??$_Uninitialized_move@PEAUConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@YAPEAUConfigItem@CLI@@QEAU12@0PEAU12@AEAV?$allocator@UConfigItem@CLI@@@0@@Z; std::_Uninitialized_move<CLI::ConfigItem *>(CLI::ConfigItem * const,CLI::ConfigItem * const,CLI::ConfigItem *,std::allocator<CLI::ConfigItem> &)
0x1400120aa  mov     [rsp+98h+var_60], rbx
0x1400120af  mov     rcx, r12
0x1400120b2  mov     rdx, [rsi+8]
0x1400120b6  mov     r9, rsi
0x1400120b9  mov     r8, r14
0x1400120bc  call    ??$_Uninitialized_move@PEAUConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@YAPEAUConfigItem@CLI@@QEAU12@0PEAU12@AEAV?$allocator@UConfigItem@CLI@@@0@@Z; std::_Uninitialized_move<CLI::ConfigItem *>(CLI::ConfigItem * const,CLI::ConfigItem * const,CLI::ConfigItem *,std::allocator<CLI::ConfigItem> &)
0x1400120c1  mov     [rsp+98h+var_70], 0
0x1400120ca  mov     r9, rdi
0x1400120cd  mov     r8, rbp
0x1400120d0  mov     rdx, rbx
0x1400120d3  mov     rcx, rsi
0x1400120d6  call    ?_Change_array@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAXQEAUConfigItem@CLI@@_K1@Z; std::vector<CLI::ConfigItem>::_Change_array(CLI::ConfigItem * const,unsigned __int64,unsigned __int64)
0x1400120db  nop
0x1400120dc  lea     rcx, [rsp+98h+var_78]
0x1400120e1  call    ??1_Reallocation_guard@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@QEAA@XZ; std::vector<CLI::ConfigItem>::_Reallocation_guard::~_Reallocation_guard(void)
0x1400120e6  mov     rax, r15
0x1400120e9  add     rsp, 58h
0x1400120ed  pop     r15
0x1400120ef  pop     r14
0x1400120f1  pop     r13
0x1400120f3  pop     r12
0x1400120f5  pop     rdi
0x1400120f6  pop     rsi
0x1400120f7  pop     rbp
0x1400120f8  pop     rbx
0x1400120f9  retn
0x1400120fa  call    ?_Xlength@?$vector@V?$shared_ptr@VApp@CLI@@@std@@V?$allocator@V?$shared_ptr@VApp@CLI@@@std@@@2@@std@@CAXXZ; std::vector<std::shared_ptr<CLI::App>>::_Xlength(void)
0x140012100  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
