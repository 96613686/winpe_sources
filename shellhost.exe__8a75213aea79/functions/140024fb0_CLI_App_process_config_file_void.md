# CLI::App::_process_config_file(void)

- ea: `0x140024fb0`
- end: `0x1400252e8`
- name: `?_process_config_file@App@CLI@@IEAAXXZ`
- size: `824`
- prototype: `void __fastcall(CLI::App *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x140024be0`

## callees

- `0x1400083f0`
- `0x1400088d0`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x140010614`
- `0x140010668`
- `0x140013c50`
- `0x140018580`
- `0x140024db0`
- `0x140024fb0`
- `0x140028890`
- `0x140031680`
- `0x14003e830`
- `0x14004a9e0`
- `0x14004aaac`

## string_xrefs

- `0x1400252af`: `config file is required but none was given`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CLI::App::_process_config_file(CLI::App *this)
{
  __int64 v2; // rdx
  char v3; // r15
  unsigned __int64 v4; // rdi
  void **v5; // r12
  __int64 v6; // rbx
  size_t v7; // rax
  void *v8; // rax
  void *v9; // rcx
  size_t v10; // rcx
  _QWORD *v11; // rax
  unsigned __int64 v12; // rdx
  void *v13; // rcx
  void **v14; // rbx
  void **v15; // rdi
  void **v16; // rdi
  unsigned __int64 v17; // rdx
  char *v18; // rax
  unsigned __int64 v19; // rdx
  char *v20; // rcx
  unsigned __int64 v21; // rdx
  void **v22; // rcx
  __int64 v23; // rax
  void *v24; // [rsp+28h] [rbp-71h] BYREF
  void **v25; // [rsp+30h] [rbp-69h]
  __int64 v26; // [rsp+38h] [rbp-61h]
  void *Src[2]; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 v28; // [rsp+50h] [rbp-49h]
  unsigned __int64 v29; // [rsp+58h] [rbp-41h]
  __int128 pExceptionObject; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int64 v31; // [rsp+70h] [rbp-29h]
  __int64 v32; // [rsp+78h] [rbp-21h]

  v2 = *((_QWORD *)this + 113);
  if ( !v2 )
    return;
  v3 = *(_BYTE *)(v2 + 32);
  if ( !((__int64)(*(_QWORD *)(v2 + 576) - *(_QWORD *)(v2 + 568)) >> 5) && *(_QWORD *)(v2 + 184) )
  {
    CLI::detail::get_environment_value(Src, v2 + 168);
    v4 = v28;
    if ( !v28 )
      goto LABEL_25;
    pExceptionObject = 0;
    v31 = 0;
    v32 = 0;
    v5 = Src;
    if ( v29 > 0xF )
      v5 = (void **)Src[0];
    v6 = 0x7FFFFFFFFFFFFFFFLL;
    if ( v28 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlen_string();
    if ( v28 <= 0xF )
    {
      v31 = v28;
      v32 = 15;
      pExceptionObject = *(_OWORD *)v5;
LABEL_24:
      CLI::Option::add_result(*((_QWORD *)this + 113), &pExceptionObject);
LABEL_25:
      if ( v29 > 0xF )
      {
        v12 = v29 + 1;
        if ( v29 + 1 < 0x1000 )
        {
          v13 = Src[0];
        }
        else
        {
          v13 = (void *)*((_QWORD *)Src[0] - 1);
          if ( (unsigned __int64)((char *)Src[0] - (char *)v13 - 8) > 0x1F )
            goto LABEL_52;
          v12 = v29 + 40;
        }
        operator delete(v13, v12);
      }
      goto LABEL_31;
    }
    if ( (v28 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v7 = 0x8000000000000027uLL;
LABEL_12:
      v8 = operator new(v7);
      v9 = v8;
      if ( !v8 )
        __fastfail(5u);
      v11 = (_QWORD *)(((unsigned __int64)v8 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v11 - 1) = v9;
      goto LABEL_23;
    }
    v6 = v28 | 0xF;
    if ( (v28 | 0xF) < 0x16 )
      v6 = 22;
    v10 = v6 + 1;
    if ( v6 == -1 )
    {
      v11 = 0;
    }
    else
    {
      if ( v10 >= 0x1000 )
      {
        v7 = v6 + 40;
        if ( v6 + 40 < (unsigned __int64)(v6 + 1) )
          std::_Throw_bad_array_new_length();
        goto LABEL_12;
      }
      v11 = operator new(v10);
    }
LABEL_23:
    *(_QWORD *)&pExceptionObject = v11;
    v31 = v4;
    v32 = v6;
    memcpy_0(v11, v5, v4 + 1);
    goto LABEL_24;
  }
LABEL_31:
  CLI::Option::run_callback(*((CLI::Option **)this + 113));
  CLI::Option::as<std::vector<std::string>>(*((_QWORD *)this + 113), &v24);
  v14 = (void **)v24;
  v15 = v25;
  if ( v24 == v25 || !*((_QWORD *)v24 + 2) )
  {
    if ( v3 )
    {
      v23 = std::string::string(Src, "config file is required but none was given");
      CLI::FileError::FileError(&pExceptionObject, v23);
      throw (CLI::FileError *)&pExceptionObject;
    }
    if ( v24 )
    {
      if ( v24 != v25 )
      {
        do
        {
          v17 = (unsigned __int64)v14[3];
          if ( v17 > 0xF )
          {
            v18 = (char *)*v14;
            v19 = v17 + 1;
            if ( v19 < 0x1000 )
            {
              v20 = (char *)*v14;
            }
            else
            {
              v20 = (char *)*((_QWORD *)v18 - 1);
              if ( (unsigned __int64)(v18 - v20 - 8) > 0x1F )
                goto LABEL_52;
              v19 += 39LL;
            }
            operator delete(v20, v19);
          }
          v14[2] = 0;
          v14[3] = (void *)15;
          *(_BYTE *)v14 = 0;
          v14 += 4;
        }
        while ( v14 != v15 );
        goto LABEL_48;
      }
LABEL_49:
      v21 = (v26 - (_QWORD)v14) & 0xFFFFFFFFFFFFFFE0uLL;
      if ( v21 < 0x1000 )
      {
        v22 = v14;
        goto LABEL_54;
      }
      v22 = (void **)*(v14 - 1);
      if ( (unsigned __int64)((char *)v14 - (char *)v22 - 8) <= 0x1F )
      {
        v21 += 39LL;
LABEL_54:
        operator delete(v22, v21);
        return;
      }
LABEL_52:
      __fastfail(5u);
    }
  }
  else
  {
    do
    {
      CLI::App::_process_config_file(this);
      v14 += 4;
    }
    while ( v14 != v15 );
    v14 = (void **)v24;
    if ( v24 )
    {
      v16 = v25;
      if ( v24 != v25 )
      {
        do
        {
          std::string::_Tidy_deallocate(v14);
          v14 += 4;
        }
        while ( v14 != v16 );
LABEL_48:
        v14 = (void **)v24;
        goto LABEL_49;
      }
      goto LABEL_49;
    }
  }
}

```

## disassembly

```asm
0x140024fb0  push    rbp
0x140024fb2  push    rbx
0x140024fb3  push    rsi
0x140024fb4  push    rdi
0x140024fb5  push    r12
0x140024fb7  push    r13
0x140024fb9  push    r14
0x140024fbb  push    r15
0x140024fbd  lea     rbp, [rsp-1Fh]
0x140024fc2  sub     rsp, 0B8h
0x140024fc9  mov     rax, cs:__security_cookie
0x140024fd0  xor     rax, rsp
0x140024fd3  mov     [rbp+57h+var_50], rax
0x140024fd7  mov     r14, rcx
0x140024fda  xor     r13d, r13d
0x140024fdd  mov     rdx, [rcx+388h]
0x140024fe4  test    rdx, rdx
0x140024fe7  jz      loc_14002528F
0x140024fed  movzx   r15d, byte ptr [rdx+20h]
0x140024ff2  mov     rsi, [rdx+240h]
0x140024ff9  sub     rsi, [rdx+238h]
0x140025000  sar     rsi, 5
0x140025004  test    rsi, rsi
0x140025007  jnz     loc_140025166
0x14002500d  cmp     [rdx+0B8h], r13
0x140025014  jz      loc_140025166
0x14002501a  add     rdx, 0A8h
0x140025021  lea     rcx, [rbp+57h+Src]
0x140025025  call    ?get_environment_value@detail@CLI@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; CLI::detail::get_environment_value(std::string const &)
0x14002502a  nop
0x14002502b  mov     rdi, [rbp+57h+var_A0]
0x14002502f  test    rdi, rdi
0x140025032  jz      loc_140025129
0x140025038  xorps   xmm0, xmm0
0x14002503b  movups  [rbp+57h+pExceptionObject], xmm0
0x14002503f  mov     [rbp+57h+var_80], r13
0x140025043  mov     [rbp+57h+var_78], r13
0x140025047  lea     r12, [rbp+57h+Src]
0x14002504b  cmp     [rbp+57h+var_98], 0Fh
0x140025050  cmova   r12, [rbp+57h+Src]
0x140025055  mov     rbx, 7FFFFFFFFFFFFFFFh
0x14002505f  cmp     rdi, rbx
0x140025062  ja      loc_1400252E2
0x140025068  cmp     rdi, 0Fh
0x14002506c  ja      short loc_140025088
0x14002506e  mov     [rbp+57h+var_80], rdi
0x140025072  mov     [rbp+57h+var_78], 0Fh
0x14002507a  movups  xmm0, xmmword ptr [r12]
0x14002507f  movups  [rbp+57h+pExceptionObject], xmm0
0x140025083  jmp     loc_140025118
0x140025088  mov     rax, rdi
0x14002508b  or      rax, 0Fh
0x14002508f  cmp     rax, rbx
0x140025092  jbe     short loc_1400250B5
0x140025094  mov     rax, 8000000000000027h
0x14002509e  mov     rcx, rax; Size
0x1400250a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400250a6  mov     rcx, rax
0x1400250a9  test    rax, rax
0x1400250ac  jnz     short loc_1400250EA
0x1400250ae  mov     ecx, 5
0x1400250b3  int     29h; Win8: RtlFailFast(ecx)
0x1400250b5  mov     rbx, rax
0x1400250b8  mov     ecx, 16h
0x1400250bd  cmp     rax, rcx
0x1400250c0  cmovb   rbx, rcx
0x1400250c4  lea     rcx, [rbx+1]; Size
0x1400250c8  test    rcx, rcx
0x1400250cb  jnz     short loc_1400250D2
0x1400250cd  mov     rax, r13
0x1400250d0  jmp     short loc_1400250FD
0x1400250d2  cmp     rcx, 1000h
0x1400250d9  jb      short loc_1400250F8
0x1400250db  lea     rax, [rcx+27h]
0x1400250df  cmp     rax, rcx
0x1400250e2  jbe     loc_1400252DC
0x1400250e8  jmp     short loc_14002509E
0x1400250ea  add     rax, 27h ; '''
0x1400250ee  and     rax, 0FFFFFFFFFFFFFFE0h
0x1400250f2  mov     [rax-8], rcx
0x1400250f6  jmp     short loc_1400250FD
0x1400250f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400250fd  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x140025101  mov     [rbp+57h+var_80], rdi
0x140025105  mov     [rbp+57h+var_78], rbx
0x140025109  lea     r8, [rdi+1]; Size
0x14002510d  mov     rdx, r12; Src
0x140025110  mov     rcx, rax; void *
0x140025113  call    memcpy_0
0x140025118  lea     rdx, [rbp+57h+pExceptionObject]
0x14002511c  mov     rcx, [r14+388h]
0x140025123  call    ?add_result@Option@CLI@@QEAAPEAV12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::Option::add_result(std::string)
0x140025128  nop
0x140025129  mov     rdx, [rbp+57h+var_98]
0x14002512d  cmp     rdx, 0Fh
0x140025131  jbe     short loc_140025166
0x140025133  mov     rax, [rbp+57h+Src]
0x140025137  inc     rdx; unsigned __int64
0x14002513a  cmp     rdx, 1000h
0x140025141  jb      short loc_14002515E
0x140025143  mov     rcx, [rax-8]
0x140025147  sub     rax, rcx
0x14002514a  sub     rax, 8
0x14002514e  cmp     rax, 1Fh
0x140025152  ja      loc_140025280
0x140025158  add     rdx, 27h ; '''
0x14002515c  jmp     short loc_140025161
0x14002515e  mov     rcx, rax; void *
0x140025161  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140025166  mov     rcx, [r14+388h]; this
0x14002516d  call    ?run_callback@Option@CLI@@QEAAXXZ; CLI::Option::run_callback(void)
0x140025172  lea     rdx, [rbp+57h+var_C8]
0x140025176  mov     rcx, [r14+388h]
0x14002517d  call    ??$as@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Option@CLI@@QEBA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ; CLI::Option::as<std::vector<std::string>>(void)
0x140025182  nop
0x140025183  mov     rbx, [rbp+57h+var_C8]
0x140025187  mov     rdi, [rbp+57h+var_C0]
0x14002518b  cmp     rbx, rdi
0x14002518e  jz      short loc_1400251EA
0x140025190  cmp     qword ptr [rbx+10h], 0
0x140025195  jz      short loc_1400251EA
0x140025197  test    r15b, r15b
0x14002519a  jnz     short loc_1400251A6
0x14002519c  test    rsi, rsi
0x14002519f  jnz     short loc_1400251A6
0x1400251a1  xor     r8d, r8d
0x1400251a4  jmp     short loc_1400251A9
0x1400251a6  mov     r8b, 1
0x1400251a9  mov     rdx, rbx
0x1400251ac  mov     rcx, r14; this
0x1400251af  call    ?_process_config_file@App@CLI@@IEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; CLI::App::_process_config_file(std::string const &,bool)
0x1400251b4  add     rbx, 20h ; ' '
0x1400251b8  cmp     rbx, rdi
0x1400251bb  jnz     short loc_140025197
0x1400251bd  mov     rbx, [rbp+57h+var_C8]
0x1400251c1  test    rbx, rbx
0x1400251c4  jz      loc_14002528F
0x1400251ca  mov     rdi, [rbp+57h+var_C0]
0x1400251ce  cmp     rbx, rdi
0x1400251d1  jz      loc_140025255
0x1400251d7  mov     rcx, rbx; void *
0x1400251da  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400251df  add     rbx, 20h ; ' '
0x1400251e3  cmp     rbx, rdi
0x1400251e6  jnz     short loc_1400251D7
0x1400251e8  jmp     short loc_140025251
0x1400251ea  test    r15b, r15b
0x1400251ed  jnz     loc_1400252AF
0x1400251f3  test    rbx, rbx
0x1400251f6  jz      loc_14002528F
0x1400251fc  cmp     rbx, rdi
0x1400251ff  jz      short loc_140025255
0x140025201  mov     rdx, [rbx+18h]
0x140025205  cmp     rdx, 0Fh
0x140025209  jbe     short loc_140025239
0x14002520b  mov     rax, [rbx]
0x14002520e  inc     rdx; unsigned __int64
0x140025211  cmp     rdx, 1000h
0x140025218  jb      short loc_140025231
0x14002521a  mov     rcx, [rax-8]
0x14002521e  sub     rax, rcx
0x140025221  sub     rax, 8
0x140025225  cmp     rax, 1Fh
0x140025229  ja      short loc_140025280
0x14002522b  add     rdx, 27h ; '''
0x14002522f  jmp     short loc_140025234
0x140025231  mov     rcx, rax; void *
0x140025234  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140025239  mov     [rbx+10h], r13
0x14002523d  mov     qword ptr [rbx+18h], 0Fh
0x140025245  mov     byte ptr [rbx], 0
0x140025248  add     rbx, 20h ; ' '
0x14002524c  cmp     rbx, rdi
0x14002524f  jnz     short loc_140025201
0x140025251  mov     rbx, [rbp+57h+var_C8]
0x140025255  mov     rdx, [rbp+57h+var_B8]
0x140025259  sub     rdx, rbx
0x14002525c  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x140025260  cmp     rdx, 1000h
0x140025267  jb      short loc_140025287
0x140025269  mov     rcx, [rbx-8]
0x14002526d  sub     rbx, rcx
0x140025270  sub     rbx, 8
0x140025274  cmp     rbx, 1Fh
0x140025278  ja      short loc_140025280
0x14002527a  add     rdx, 27h ; '''
0x14002527e  jmp     short loc_14002528A
0x140025280  mov     ecx, 5
0x140025285  int     29h; Win8: RtlFailFast(ecx)
0x140025287  mov     rcx, rbx; void *
0x14002528a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002528f  mov     rcx, [rbp+57h+var_50]
0x140025293  xor     rcx, rsp; StackCookie
0x140025296  call    __security_check_cookie
0x14002529b  add     rsp, 0B8h
0x1400252a2  pop     r15
0x1400252a4  pop     r14
0x1400252a6  pop     r13
0x1400252a8  pop     r12
0x1400252aa  pop     rdi
0x1400252ab  pop     rsi
0x1400252ac  pop     rbx
0x1400252ad  pop     rbp
0x1400252ae  retn
0x1400252af  lea     rdx, aConfigFileIsRe; "config file is required but none was gi"...
0x1400252b6  lea     rcx, [rbp+57h+Src]
0x1400252ba  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400252bf  mov     rdx, rax
0x1400252c2  lea     rcx, [rbp+57h+pExceptionObject]
0x1400252c6  call    ??0FileError@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::FileError::FileError(std::string)
0x1400252cb  lea     rdx, _TI5?AVFileError@CLI@@; pThrowInfo
0x1400252d2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400252d6  call    _CxxThrowException_0
0x1400252dc  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x1400252e2  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
