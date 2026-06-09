# CLI::App::_parse_subcommand(std::vector<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::allocator<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &)

- ea: `0x1400246d0`
- end: `0x140024bcd`
- name: `?_parse_subcommand@App@CLI@@IEAA_NAEAV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z`
- size: `1277`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140023880`

## callees

- `0x1400083f0`
- `0x140008910`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x140010620`
- `0x140010668`
- `0x140010db0`
- `0x140018770`
- `0x14001f090`
- `0x140020300`
- `0x140020fd0`
- `0x140021370`
- `0x140022fb0`
- `0x1400246d0`
- `0x140027480`
- `0x140029240`
- `0x14002cfa0`
- `0x1400312f0`
- `0x14003cc50`
- `0x14003cdc0`
- `0x140044efc`
- `0x14004a9e0`
- `0x14005385c`
- `0x14005d2f8`

## string_xrefs

- `0x140024b8c`: `Subcommand `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CLI::App::_parse_subcommand(const void **a1, _QWORD *a2)
{
  const void **v3; // rsi
  __int64 v4; // r10
  __int64 *v5; // rdx
  __int64 *v6; // r9
  __int64 v7; // rax
  int v8; // ecx
  __int64 v9; // r8
  __int64 subcommand; // rax
  __int64 v12; // rdx
  CLI::App *v13; // rdi
  unsigned __int64 first_of; // rax
  unsigned __int64 v15; // rbx
  _QWORD *v16; // rdx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // rdx
  void *v19; // rcx
  unsigned __int64 v20; // rbx
  _QWORD *v21; // rax
  unsigned __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned __int64 v25; // rdx
  void *v26; // rcx
  __int64 display_name; // rax
  void *v28; // rcx
  __int64 v29; // rbx
  const void **v30; // r14
  const void **v31; // rbx
  char *v32; // r15
  char *v33; // rcx
  __int64 v34; // rsi
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  unsigned __int64 v37; // r12
  size_t v38; // rcx
  char *v39; // rdi
  void *v40; // rax
  char *v41; // r8
  _BYTE *v42; // rdx
  char *v43; // rcx
  size_t v44; // r8
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  CLI::App *v48; // [rsp+20h] [rbp-89h] BYREF
  __int64 v49; // [rsp+28h] [rbp-81h]
  const void **v50; // [rsp+30h] [rbp-79h]
  void *v51[2]; // [rsp+38h] [rbp-71h] BYREF
  __int64 v52; // [rsp+48h] [rbp-61h]
  unsigned __int64 v53; // [rsp+50h] [rbp-59h]
  char v54[40]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+80h] [rbp-29h] BYREF

  v3 = a1;
  v50 = a1;
  v4 = 0;
  v5 = (__int64 *)a1[40];
  v6 = (__int64 *)a1[39];
  if ( v6 != v5 )
  {
    do
    {
      v7 = *v6;
      if ( *(_QWORD *)(*v6 + 152) )
      {
        if ( *(_BYTE *)(v7 + 32) )
        {
          v8 = *(_DWORD *)(v7 + 428) * *(_DWORD *)(v7 + 432);
          if ( v8 > 0 )
          {
            v9 = (__int64)(*(_QWORD *)(v7 + 576) - *(_QWORD *)(v7 + 568)) >> 5;
            if ( (int)v9 < v8 )
              v4 += v8 - v9;
          }
        }
      }
      ++v6;
    }
    while ( v6 != v5 );
    if ( v4 )
    {
      CLI::App::_parse_positional(v3, a2, 0);
      return 1;
    }
  }
  subcommand = CLI::App::_find_subcommand(v3, a2[1] - 32LL, 1);
  v13 = (CLI::App *)subcommand;
  v48 = (CLI::App *)subcommand;
  if ( subcommand )
  {
    v29 = subcommand;
    goto LABEL_44;
  }
  LOBYTE(v12) = 46;
  first_of = std::string::find_first_of(a2[1] - 32LL, v12, 0);
  v15 = first_of;
  if ( first_of != -1 )
  {
    v16 = (_QWORD *)(a2[1] - 32LL);
    *(_OWORD *)v51 = 0;
    v52 = 0;
    v53 = 0;
    v17 = first_of;
    if ( v16[2] < first_of )
      v17 = v16[2];
    if ( v16[3] > 0xFu )
      v16 = (_QWORD *)*v16;
    std::string::_Construct<1,char const *>(v51, v16, v17);
    v13 = (CLI::App *)CLI::App::_find_subcommand(v3, v51, 1);
    v48 = v13;
    if ( v53 > 0xF )
    {
      v18 = v53 + 1;
      if ( v53 + 1 < 0x1000 )
      {
        v19 = v51[0];
      }
      else
      {
        v19 = (void *)*((_QWORD *)v51[0] - 1);
        if ( (unsigned __int64)((char *)v51[0] - (char *)v19 - 8) > 0x1F )
          goto LABEL_68;
        v18 = v53 + 40;
      }
      operator delete(v19, v18);
    }
    if ( v13 )
    {
      v20 = v15 + 1;
      v21 = (_QWORD *)(a2[1] - 32LL);
      *(_OWORD *)v51 = 0;
      v52 = 0;
      v53 = 0;
      v22 = v21[2];
      if ( v22 < v20 )
        std::_String_val<std::_Simple_types<char>>::_Xran();
      v23 = v22 - v20;
      v24 = -1;
      if ( v23 != -1 )
        v24 = v23;
      if ( v21[3] > 0xFu )
        v21 = (_QWORD *)*v21;
      std::string::_Construct<1,char const *>(v51, (char *)v21 + v20, v24);
      std::string::operator=(a2[1] - 32LL, v51);
      if ( v53 > 0xF )
      {
        v25 = v53 + 1;
        if ( v53 + 1 < 0x1000 )
        {
          v26 = v51[0];
        }
        else
        {
          v26 = (void *)*((_QWORD *)v51[0] - 1);
          if ( (unsigned __int64)((char *)v51[0] - (char *)v26 - 8) > 0x1F )
            goto LABEL_68;
          v25 = v53 + 40;
        }
        operator delete(v26, v25);
      }
      display_name = CLI::App::get_display_name(v13, v51, 0);
      std::vector<std::string>::push_back(a2, display_name);
      if ( v53 > 0xF )
      {
        if ( v53 + 1 >= 0x1000 )
        {
          v28 = (void *)*((_QWORD *)v51[0] - 1);
          if ( (unsigned __int64)((char *)v51[0] - (char *)v28 - 8) <= 0x1F )
          {
            operator delete(v28, v53 + 40);
            v29 = (__int64)v13;
            goto LABEL_44;
          }
LABEL_68:
          __fastfail(5u);
        }
        operator delete(v51[0], v53 + 1);
      }
      v29 = (__int64)v13;
LABEL_44:
      v49 = v29;
      std::string::_Tidy_deallocate((void *)(a2[1] - 32LL));
      a2[1] -= 32LL;
      if ( !*(_BYTE *)(v29 + 801) )
        std::vector<CLI::Option *>::push_back(v3 + 85, &v48);
      CLI::App::_parse(v13);
      v30 = *(const void ***)(v29 + 840);
      if ( v30 != v3 )
      {
        while ( 1 )
        {
          CLI::App::_trigger_pre_parse((CLI::App *)v30, (__int64)(a2[1] - *a2) >> 5);
          if ( !*(_BYTE *)(v29 + 801) )
          {
            v31 = v30 + 85;
            v32 = (char *)v30[86];
            v33 = (char *)v30[87];
            if ( v32 == v33 )
            {
              v34 = (v32 - (_BYTE *)*v31) >> 3;
              if ( v34 == 0x1FFFFFFFFFFFFFFFLL )
                std::vector<std::shared_ptr<CLI::App>>::_Xlength();
              v35 = (v33 - (_BYTE *)*v31) >> 3;
              v36 = v35 >> 1;
              if ( v35 > 0x1FFFFFFFFFFFFFFFLL - (v35 >> 1) )
                goto LABEL_69;
              v37 = v34 + 1;
              if ( v35 + v36 >= v34 + 1 )
                v37 = v35 + v36;
              if ( v37 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_69:
                std::_Throw_bad_array_new_length();
              v38 = 8 * v37;
              if ( 8 * v37 )
              {
                if ( v38 < 0x1000 )
                {
                  v39 = (char *)operator new(v38);
                }
                else
                {
                  if ( v38 + 39 < v38 )
                    goto LABEL_69;
                  v40 = operator new(v38 + 39);
                  if ( !v40 )
                    goto LABEL_68;
                  v39 = (char *)(((unsigned __int64)v40 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                  *((_QWORD *)v39 - 1) = v40;
                }
              }
              else
              {
                v39 = 0;
              }
              *(_QWORD *)&v39[8 * v34] = v48;
              v41 = (char *)v30[86];
              v42 = *v31;
              v43 = v39;
              if ( v32 == v41 )
              {
                v44 = v41 - v42;
              }
              else
              {
                memmove_0(v39, v42, v32 - v42);
                v44 = (_BYTE *)v30[86] - v32;
                v43 = &v39[8 * v34 + 8];
                v42 = v32;
              }
              memmove_0(v43, v42, v44);
              std::vector<CLI::App *>::_Change_array(v30 + 85, v39, v34 + 1, v37);
              v13 = v48;
              v3 = v50;
              v29 = v49;
            }
            else
            {
              *(_QWORD *)v32 = v13;
              v30[86] = (char *)v30[86] + 8;
              v29 = (__int64)v13;
            }
          }
          v30 = (const void **)v30[105];
          if ( v30 == v3 )
            return 1;
        }
      }
      return 1;
    }
  }
  if ( !v3[105] )
  {
    v45 = std::vector<std::string>::back(a2);
    v46 = std::operator+<char>(v54, "Subcommand ", v45);
    v47 = std::operator+<char>(v51, v46, " missing");
    CLI::HorribleError::HorribleError(pExceptionObject, v47);
    throw (CLI::HorribleError *)pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x1400246d0  mov     [rsp-8+arg_10], rbx
0x1400246d5  push    rbp
0x1400246d6  push    rsi
0x1400246d7  push    rdi
0x1400246d8  push    r12
0x1400246da  push    r13
0x1400246dc  push    r14
0x1400246de  push    r15
0x1400246e0  lea     rbp, [rsp-27h]
0x1400246e5  sub     rsp, 0D0h
0x1400246ec  mov     rax, cs:__security_cookie
0x1400246f3  xor     rax, rsp
0x1400246f6  mov     [rbp+57h+var_40], rax
0x1400246fa  mov     r13, rdx
0x1400246fd  mov     rsi, rcx
0x140024700  mov     [rbp+57h+var_D0], rcx
0x140024704  xor     r14d, r14d
0x140024707  mov     r10d, r14d
0x14002470a  mov     rdx, [rcx+140h]
0x140024711  mov     r9, [rcx+138h]
0x140024718  cmp     r9, rdx
0x14002471b  jz      loc_1400247A9
0x140024721  mov     rax, [r9]
0x140024724  cmp     [rax+98h], r14
0x14002472b  jz      short loc_140024764
0x14002472d  cmp     [rax+20h], r14b
0x140024731  jz      short loc_140024764
0x140024733  mov     ecx, [rax+1B0h]
0x140024739  imul    ecx, [rax+1ACh]
0x140024740  test    ecx, ecx
0x140024742  jle     short loc_140024764
0x140024744  mov     r8, [rax+240h]
0x14002474b  sub     r8, [rax+238h]
0x140024752  sar     r8, 5
0x140024756  cmp     r8d, ecx
0x140024759  jge     short loc_140024764
0x14002475b  movsxd  rax, ecx
0x14002475e  sub     rax, r8
0x140024761  add     r10, rax
0x140024764  add     r9, 8
0x140024768  cmp     r9, rdx
0x14002476b  jnz     short loc_140024721
0x14002476d  test    r10, r10
0x140024770  jz      short loc_1400247A9
0x140024772  xor     r8d, r8d
0x140024775  mov     rdx, r13
0x140024778  mov     rcx, rsi
0x14002477b  call    ?_parse_positional@App@CLI@@IEAA_NAEAV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@_N@Z; CLI::App::_parse_positional(std::vector<std::string> &,bool)
0x140024780  mov     al, 1
0x140024782  mov     rcx, [rbp+57h+var_40]
0x140024786  xor     rcx, rsp; StackCookie
0x140024789  call    __security_check_cookie
0x14002478e  mov     rbx, [rsp+100h+arg_10]
0x140024796  add     rsp, 0D0h
0x14002479d  pop     r15
0x14002479f  pop     r14
0x1400247a1  pop     r13
0x1400247a3  pop     r12
0x1400247a5  pop     rdi
0x1400247a6  pop     rsi
0x1400247a7  pop     rbp
0x1400247a8  retn
0x1400247a9  mov     rdx, [r13+8]
0x1400247ad  sub     rdx, 20h ; ' '
0x1400247b1  mov     r9b, 1
0x1400247b4  movzx   r8d, r9b
0x1400247b8  mov     rcx, rsi
0x1400247bb  call    ?_find_subcommand@App@CLI@@IEBAPEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N1@Z; CLI::App::_find_subcommand(std::string const &,bool,bool)
0x1400247c0  mov     rdi, rax
0x1400247c3  mov     [rsp+100h+var_E0], rax
0x1400247c8  test    rax, rax
0x1400247cb  jnz     loc_14002499E
0x1400247d1  mov     rcx, [r13+8]
0x1400247d5  sub     rcx, 20h ; ' '
0x1400247d9  xor     r8d, r8d
0x1400247dc  mov     dl, 2Eh ; '.'
0x1400247de  call    ?find_first_of@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KD_K@Z; std::string::find_first_of(char,unsigned __int64)
0x1400247e3  mov     rbx, rax
0x1400247e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400247ea  jz      loc_14002498A
0x1400247f0  mov     rdx, [r13+8]
0x1400247f4  add     rdx, 0FFFFFFFFFFFFFFE0h
0x1400247f8  xorps   xmm0, xmm0
0x1400247fb  movups  xmmword ptr [rbp+57h+var_C8], xmm0
0x1400247ff  mov     [rbp+57h+var_B8], r14
0x140024803  mov     [rbp+57h+var_B0], r14
0x140024807  mov     r8, rax
0x14002480a  cmp     [rdx+10h], rax
0x14002480e  cmovb   r8, [rdx+10h]
0x140024813  cmp     qword ptr [rdx+18h], 0Fh
0x140024818  jbe     short loc_14002481D
0x14002481a  mov     rdx, [rdx]
0x14002481d  lea     rcx, [rbp+57h+var_C8]
0x140024821  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140024826  mov     r9b, 1
0x140024829  movzx   r8d, r9b
0x14002482d  lea     rdx, [rbp+57h+var_C8]
0x140024831  mov     rcx, rsi
0x140024834  call    ?_find_subcommand@App@CLI@@IEBAPEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N1@Z; CLI::App::_find_subcommand(std::string const &,bool,bool)
0x140024839  mov     rdi, rax
0x14002483c  mov     [rsp+100h+var_E0], rax
0x140024841  mov     rdx, [rbp+57h+var_B0]
0x140024845  cmp     rdx, 0Fh
0x140024849  jbe     short loc_14002487E
0x14002484b  mov     rax, [rbp+57h+var_C8]
0x14002484f  inc     rdx; unsigned __int64
0x140024852  cmp     rdx, 1000h
0x140024859  jb      short loc_140024876
0x14002485b  mov     rcx, [rax-8]
0x14002485f  sub     rax, rcx
0x140024862  sub     rax, 8
0x140024866  cmp     rax, 1Fh
0x14002486a  ja      loc_140024B68
0x140024870  add     rdx, 27h ; '''
0x140024874  jmp     short loc_140024879
0x140024876  mov     rcx, rax; void *
0x140024879  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002487e  test    rdi, rdi
0x140024881  jz      loc_14002498A
0x140024887  inc     rbx
0x14002488a  mov     rax, [r13+8]
0x14002488e  add     rax, 0FFFFFFFFFFFFFFE0h
0x140024892  xorps   xmm0, xmm0
0x140024895  movups  xmmword ptr [rbp+57h+var_C8], xmm0
0x140024899  mov     [rbp+57h+var_B8], r14
0x14002489d  mov     [rbp+57h+var_B0], r14
0x1400248a1  mov     rcx, [rax+10h]
0x1400248a5  cmp     rcx, rbx
0x1400248a8  jb      loc_140024B7B
0x1400248ae  sub     rcx, rbx
0x1400248b1  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1400248b8  cmp     rcx, r8
0x1400248bb  cmovb   r8, rcx
0x1400248bf  cmp     qword ptr [rax+18h], 0Fh
0x1400248c4  jbe     short loc_1400248C9
0x1400248c6  mov     rax, [rax]
0x1400248c9  lea     rdx, [rax+rbx]
0x1400248cd  lea     rcx, [rbp+57h+var_C8]
0x1400248d1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400248d6  mov     rcx, [r13+8]
0x1400248da  sub     rcx, 20h ; ' '
0x1400248de  lea     rdx, [rbp+57h+var_C8]
0x1400248e2  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1400248e7  mov     rdx, [rbp+57h+var_B0]
0x1400248eb  cmp     rdx, 0Fh
0x1400248ef  jbe     short loc_140024924
0x1400248f1  mov     rax, [rbp+57h+var_C8]
0x1400248f5  inc     rdx; unsigned __int64
0x1400248f8  cmp     rdx, 1000h
0x1400248ff  jb      short loc_14002491C
0x140024901  mov     rcx, [rax-8]
0x140024905  sub     rax, rcx
0x140024908  sub     rax, 8
0x14002490c  cmp     rax, 1Fh
0x140024910  ja      loc_140024B68
0x140024916  add     rdx, 27h ; '''
0x14002491a  jmp     short loc_14002491F
0x14002491c  mov     rcx, rax; void *
0x14002491f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140024924  xor     r8d, r8d
0x140024927  lea     rdx, [rbp+57h+var_C8]
0x14002492b  mov     rcx, rdi
0x14002492e  call    ?get_display_name@App@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; CLI::App::get_display_name(bool)
0x140024933  nop
0x140024934  mov     rdx, rax
0x140024937  mov     rcx, r13
0x14002493a  call    ?push_back@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::vector<std::string>::push_back(std::string &&)
0x14002493f  nop
0x140024940  mov     rdx, [rbp+57h+var_B0]
0x140024944  cmp     rdx, 0Fh
0x140024948  jbe     short loc_140024985
0x14002494a  mov     rax, [rbp+57h+var_C8]
0x14002494e  inc     rdx; unsigned __int64
0x140024951  cmp     rdx, 1000h
0x140024958  jb      short loc_14002497D
0x14002495a  mov     rcx, [rax-8]; void *
0x14002495e  sub     rax, rcx
0x140024961  sub     rax, 8
0x140024965  cmp     rax, 1Fh
0x140024969  ja      loc_140024B68
0x14002496f  add     rdx, 27h ; '''; unsigned __int64
0x140024973  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140024978  mov     rbx, rdi
0x14002497b  jmp     short loc_1400249A1
0x14002497d  mov     rcx, rax; void *
0x140024980  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140024985  mov     rbx, rdi
0x140024988  jmp     short loc_1400249A1
0x14002498a  cmp     [rsi+348h], r14
0x140024991  jz      loc_140024B81
0x140024997  xor     al, al
0x140024999  jmp     loc_140024782
0x14002499e  mov     rbx, rax
0x1400249a1  mov     [rsp+100h+var_D8], rbx
0x1400249a6  mov     rcx, [r13+8]
0x1400249aa  sub     rcx, 20h ; ' '; void *
0x1400249ae  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400249b3  add     qword ptr [r13+8], 0FFFFFFFFFFFFFFE0h
0x1400249b8  cmp     byte ptr [rbx+321h], 0
0x1400249bf  jnz     short loc_1400249D2
0x1400249c1  lea     rcx, [rsi+2A8h]
0x1400249c8  lea     rdx, [rsp+100h+var_E0]
0x1400249cd  call    ?push_back@?$vector@PEAVOption@CLI@@V?$allocator@PEAVOption@CLI@@@std@@@std@@QEAAX$$QEAPEAVOption@CLI@@@Z; std::vector<CLI::Option *>::push_back(CLI::Option * &&)
0x1400249d2  mov     rdx, r13
0x1400249d5  mov     rcx, rdi; this
0x1400249d8  call    ?_parse@App@CLI@@IEAAXAEAV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z; CLI::App::_parse(std::vector<std::string> &)
0x1400249dd  mov     r14, [rbx+348h]
0x1400249e4  cmp     r14, rsi
0x1400249e7  jz      loc_140024780
0x1400249ed  mov     r12, 1FFFFFFFFFFFFFFFh
0x1400249f7  nop     word ptr [rax+rax+00000000h]
0x140024a00  mov     rdx, [r13+8]
0x140024a04  sub     rdx, [r13+0]
0x140024a08  sar     rdx, 5; unsigned __int64
0x140024a0c  mov     rcx, r14; this
0x140024a0f  call    ?_trigger_pre_parse@App@CLI@@IEAAX_K@Z; CLI::App::_trigger_pre_parse(unsigned __int64)
0x140024a14  cmp     byte ptr [rbx+321h], 0
0x140024a1b  jnz     loc_140024B53
0x140024a21  lea     rbx, [r14+2A8h]
0x140024a28  mov     r15, [rbx+8]
0x140024a2c  mov     rcx, [rbx+10h]
0x140024a30  cmp     r15, rcx
0x140024a33  jz      short loc_140024A45
0x140024a35  mov     [r15], rdi
0x140024a38  add     qword ptr [rbx+8], 8
0x140024a3d  mov     rbx, rdi
0x140024a40  jmp     loc_140024B53
0x140024a45  mov     rax, [rbx]
0x140024a48  mov     rsi, r15
0x140024a4b  sub     rsi, rax
0x140024a4e  sar     rsi, 3
0x140024a52  cmp     rsi, r12
0x140024a55  jz      loc_140024B75
0x140024a5b  sub     rcx, rax
0x140024a5e  sar     rcx, 3
0x140024a62  mov     rdx, rcx
0x140024a65  shr     rdx, 1
0x140024a68  mov     rax, r12
0x140024a6b  sub     rax, rdx
0x140024a6e  cmp     rcx, rax
0x140024a71  ja      loc_140024B6F
0x140024a77  lea     r8, [rsi+1]
0x140024a7b  lea     rax, [rcx+rdx]
0x140024a7f  mov     r12, r8
0x140024a82  cmp     rax, r8
0x140024a85  cmovnb  r12, rax
0x140024a89  mov     rax, 1FFFFFFFFFFFFFFFh
0x140024a93  cmp     r12, rax
0x140024a96  ja      loc_140024B6F
0x140024a9c  lea     rcx, ds:0[r12*8]; Size
0x140024aa4  test    rcx, rcx
0x140024aa7  jnz     short loc_140024AAD
0x140024aa9  xor     edi, edi
0x140024aab  jmp     short loc_140024AEA
0x140024aad  cmp     rcx, 1000h
0x140024ab4  jb      short loc_140024AE2
0x140024ab6  lea     rax, [rcx+27h]
0x140024aba  cmp     rax, rcx
0x140024abd  jbe     loc_140024B6F
0x140024ac3  mov     rcx, rax; Size
0x140024ac6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140024acb  test    rax, rax
0x140024ace  jz      loc_140024B68
0x140024ad4  lea     rdi, [rax+27h]
0x140024ad8  and     rdi, 0FFFFFFFFFFFFFFE0h
0x140024adc  mov     [rdi-8], rax
0x140024ae0  jmp     short loc_140024AEA
0x140024ae2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140024ae7  mov     rdi, rax
0x140024aea  mov     rax, [rsp+100h+var_E0]
0x140024aef  mov     [rdi+rsi*8], rax
0x140024af3  mov     r8, [rbx+8]
0x140024af7  mov     rdx, [rbx]; Src
0x140024afa  mov     rcx, rdi; void *
0x140024afd  cmp     r15, r8
0x140024b00  jnz     short loc_140024B07
0x140024b02  sub     r8, rdx
0x140024b05  jmp     short loc_140024B24
0x140024b07  mov     r8, r15
0x140024b0a  sub     r8, rdx; Size
0x140024b0d  call    memmove_0
0x140024b12  mov     r8, [rbx+8]
0x140024b16  sub     r8, r15; Size
0x140024b19  lea     rcx, [rsi+1]
0x140024b1d  lea     rcx, [rdi+rcx*8]; void *
0x140024b21  mov     rdx, r15; Src
0x140024b24  call    memmove_0
0x140024b29  mov     r9, r12
0x140024b2c  lea     r8, [rsi+1]
0x140024b30  mov     rdx, rdi
0x140024b33  mov     rcx, rbx
0x140024b36  call    ?_Change_array@?$vector@PEAVApp@CLI@@V?$allocator@PEAVApp@CLI@@@std@@@std@@AEAAXQEAPEAVApp@CLI@@_K1@Z; std::vector<CLI::App *>::_Change_array(CLI::App * * const,unsigned __int64,unsigned __int64)
0x140024b3b  mov     rdi, [rsp+100h+var_E0]
0x140024b40  mov     rsi, [rbp+57h+var_D0]
0x140024b44  mov     rbx, [rsp+100h+var_D8]
0x140024b49  mov     r12, 1FFFFFFFFFFFFFFFh
0x140024b53  mov     r14, [r14+348h]
0x140024b5a  cmp     r14, rsi
0x140024b5d  jnz     loc_140024A00
0x140024b63  jmp     loc_140024780
  ... truncated ...
```
