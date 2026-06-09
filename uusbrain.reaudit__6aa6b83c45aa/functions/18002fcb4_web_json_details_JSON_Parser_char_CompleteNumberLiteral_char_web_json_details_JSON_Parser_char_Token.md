# web::json::details::JSON_Parser<char>::CompleteNumberLiteral(char,web::json::details::JSON_Parser<char>::Token &)

- ea: `0x18002fcb4`
- end: `0x180030083`
- name: `?CompleteNumberLiteral@?$JSON_Parser@D@details@json@web@@AEAA_NDAEAUToken@1234@@Z`
- size: `975`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e6b0`

## callees

- `0x18000f724`
- `0x18000f7a0`
- `0x18002fcb4`
- `0x180030e0c`
- `0x180030f00`
- `0x180031a8c`
- `0x180031b14`
- `0x1800425d4`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall web::json::details::JSON_Parser<char>::CompleteNumberLiteral(__int64 a1, char a2, __int64 a3)
{
  char v4; // bl
  char v6; // r12
  char v7; // di
  int v8; // eax
  unsigned __int64 v9; // r14
  int v10; // eax
  __int64 v11; // rbx
  char v12; // bl
  int v13; // eax
  int v14; // r13d
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  char *v18; // rdi
  char *v19; // rbx
  __crt_locale_pointers *Locale; // rax
  int v21; // eax
  char v22; // bl
  int v23; // eax
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  const char *v27; // rbx
  __crt_locale_pointers *v28; // rax
  double v29; // xmm0_8
  char i; // [rsp+30h] [rbp-20h] BYREF
  char v31; // [rsp+31h] [rbp-1Fh]
  char *Buffer[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v33; // [rsp+48h] [rbp-8h]

  v4 = a2;
  v6 = 0;
  if ( a2 == 45 )
  {
    v7 = 1;
    v31 = 1;
    v4 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
  }
  else
  {
    v7 = 0;
    v31 = 0;
  }
  if ( (unsigned __int8)(v4 - 48) > 9u )
    return 0;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( v4 == 48 && v8 == 48 )
    return 0;
  v9 = v4 - 48;
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( v10 >= 48 )
  {
    while ( (unsigned int)v10 <= 0x39 )
    {
      v11 = (unsigned int)(v10 - 48);
      if ( v9 > 0x1999999999999999LL || v9 == 0x1999999999999999LL && (unsigned int)v11 > 5 )
      {
        v12 = 0;
        goto LABEL_14;
      }
      (**(void (__fastcall ***)(__int64))a1)(a1);
      v9 = v11 + 10 * v9;
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      if ( v10 < 48 )
        break;
    }
  }
  v12 = 1;
LABEL_14:
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v14 = v13;
  if ( !v12
    || (v15 = (unsigned int)(v13 - 46), (unsigned int)v15 <= 0x37) && (v16 = 0x80000000800001LL, _bittest64(&v16, v15)) )
  {
    *(_OWORD *)Buffer = 0;
    v33 = 0;
    std::vector<char>::vector<char>(Buffer, 24);
    v18 = Buffer[0];
    v19 = Buffer[1];
    Locale = utility::details::scoped_c_thread_locale::c_locale();
    v21 = snprintf_s_l(v18, v19 - v18, 0xFFFFFFFFFFFFFFFFuLL, "%I64u", Locale, v9);
    std::vector<char>::resize(Buffer, v21);
    v22 = 0;
    while ( v14 != -1 )
    {
      if ( (unsigned int)(v14 - 48) > 9 )
      {
        if ( v14 != 46 )
        {
          if ( ((v14 - 69) & 0xFFFFFFDF) != 0 )
            break;
          i = v14;
          std::vector<char>::push_back(Buffer, &i);
          (**(void (__fastcall ***)(__int64))a1)(a1);
          v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
          v25 = v24;
          if ( v24 == 43 )
          {
            i = 43;
            goto LABEL_39;
          }
          if ( v24 == 45 )
          {
            i = 45;
LABEL_39:
            std::vector<char>::push_back(Buffer, &i);
            (**(void (__fastcall ***)(__int64))a1)(a1);
            v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
          }
          if ( (unsigned int)(v25 - 48) > 9 )
            goto LABEL_48;
          for ( i = v25; ; i = v26 )
          {
            std::vector<char>::push_back(Buffer, &i);
            (**(void (__fastcall ***)(__int64))a1)(a1);
            v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
            if ( v26 < 48 || (unsigned int)v26 > 0x39 )
              break;
          }
          break;
        }
        if ( v22 )
          goto LABEL_48;
        v22 = 1;
        i = 46;
        std::vector<char>::push_back(Buffer, &i);
        (**(void (__fastcall ***)(__int64))a1)(a1);
        v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
        if ( (unsigned int)(v23 - 48) > 9 )
          goto LABEL_48;
        i = v23;
      }
      else
      {
        i = v14;
      }
      std::vector<char>::push_back(Buffer, &i);
      (**(void (__fastcall ***)(__int64))a1)(a1);
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    }
    i = 0;
    std::vector<char>::push_back(Buffer, &i);
    v27 = Buffer[0];
    v28 = utility::details::scoped_c_thread_locale::c_locale();
    v29 = strtod_l(v27, 0, v28);
    *(double *)(a3 + 56) = v29;
    if ( v31 )
      *(_QWORD *)(a3 + 56) = *(_QWORD *)&v29 ^ _xmm;
    *(_DWORD *)a3 = 8;
    v6 = 1;
LABEL_48:
    std::vector<char>::~vector<char>(Buffer);
    return v6;
  }
  else
  {
    if ( v7 )
    {
      *(_BYTE *)(a3 + 64) = 1;
      if ( v9 <= 0x8000000000000000uLL )
      {
        *(_QWORD *)(a3 + 56) = -(__int64)v9;
        *(_DWORD *)a3 = 9;
      }
      else
      {
        *(double *)(a3 + 56) = 0.0 - ((double)(int)(v9 & 1 | (v9 >> 1)) + (double)(int)(v9 & 1 | (v9 >> 1)));
        *(_DWORD *)a3 = 8;
      }
    }
    else
    {
      *(_QWORD *)(a3 + 56) = v9;
      *(_DWORD *)a3 = 9;
      *(_BYTE *)(a3 + 64) = 0;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18002fcb4  mov     [rsp-38h+arg_18], rbx
0x18002fcb9  push    rbp
0x18002fcba  push    rsi
0x18002fcbb  push    rdi
0x18002fcbc  push    r12
0x18002fcbe  push    r13
0x18002fcc0  push    r14
0x18002fcc2  push    r15
0x18002fcc4  mov     rbp, rsp
0x18002fcc7  sub     rsp, 50h
0x18002fccb  mov     r15, r8
0x18002fcce  mov     bl, dl
0x18002fcd0  mov     rsi, rcx
0x18002fcd3  xor     r12b, r12b
0x18002fcd6  cmp     dl, 2Dh ; '-'
0x18002fcd9  jnz     short loc_18002FCF1
0x18002fcdb  mov     dil, 1
0x18002fcde  mov     [rbp+var_1F], dil
0x18002fce2  mov     rax, [rcx]
0x18002fce5  mov     rax, [rax]
0x18002fce8  call    _guard_dispatch_icall
0x18002fced  mov     ebx, eax
0x18002fcef  jmp     short loc_18002FCF8
0x18002fcf1  mov     dil, r12b
0x18002fcf4  mov     [rbp+var_1F], r12b
0x18002fcf8  mov     al, bl
0x18002fcfa  mov     r13d, 30h ; '0'
0x18002fd00  sub     al, r13b
0x18002fd03  cmp     al, 9
0x18002fd05  ja      loc_180030069
0x18002fd0b  mov     rax, [rsi]
0x18002fd0e  mov     rcx, rsi
0x18002fd11  mov     rax, [rax+8]
0x18002fd15  call    _guard_dispatch_icall
0x18002fd1a  cmp     bl, r13b
0x18002fd1d  jnz     short loc_18002FD28
0x18002fd1f  cmp     eax, r13d
0x18002fd22  jz      loc_180030069
0x18002fd28  movsx   eax, bl
0x18002fd2b  sub     eax, r13d
0x18002fd2e  movsxd  r14, eax
0x18002fd31  mov     rax, [rsi]
0x18002fd34  mov     rcx, rsi
0x18002fd37  mov     rax, [rax+8]
0x18002fd3b  call    _guard_dispatch_icall
0x18002fd40  cmp     eax, r13d
0x18002fd43  jl      short loc_18002FD9F
0x18002fd45  mov     rcx, 1999999999999999h
0x18002fd4f  cmp     eax, 39h ; '9'
0x18002fd52  ja      short loc_18002FD9F
0x18002fd54  lea     ebx, [rax-30h]
0x18002fd57  cmp     r14, rcx
0x18002fd5a  ja      loc_18002FDFB
0x18002fd60  jnz     short loc_18002FD6B
0x18002fd62  cmp     ebx, 5
0x18002fd65  ja      loc_18002FDFB
0x18002fd6b  mov     rax, [rsi]
0x18002fd6e  mov     rcx, rsi
0x18002fd71  mov     rax, [rax]
0x18002fd74  call    _guard_dispatch_icall
0x18002fd79  lea     rcx, [r14+r14*4]
0x18002fd7d  lea     r14, [rbx+rcx*2]
0x18002fd81  mov     rax, [rsi]
0x18002fd84  mov     rcx, rsi
0x18002fd87  mov     rax, [rax+8]
0x18002fd8b  call    _guard_dispatch_icall
0x18002fd90  cmp     eax, r13d
0x18002fd93  mov     rcx, 1999999999999999h
0x18002fd9d  jge     short loc_18002FD4F
0x18002fd9f  mov     bl, 1
0x18002fda1  mov     rax, [rsi]
0x18002fda4  mov     rcx, rsi
0x18002fda7  mov     rax, [rax+8]
0x18002fdab  call    _guard_dispatch_icall
0x18002fdb0  mov     r13d, eax
0x18002fdb3  test    bl, bl
0x18002fdb5  jz      loc_18002FE52
0x18002fdbb  add     eax, 0FFFFFFD2h
0x18002fdbe  cmp     eax, 37h ; '7'
0x18002fdc1  ja      short loc_18002FDD3
0x18002fdc3  mov     rcx, 80000000800001h
0x18002fdcd  bt      rcx, rax
0x18002fdd1  jb      short loc_18002FE52
0x18002fdd3  test    dil, dil
0x18002fdd6  jz      short loc_18002FE41
0x18002fdd8  mov     byte ptr [r15+40h], 1
0x18002fddd  mov     rax, 8000000000000000h
0x18002fde7  cmp     r14, rax
0x18002fdea  jbe     short loc_18002FE31
0x18002fdec  xorps   xmm1, xmm1
0x18002fdef  test    r14, r14
0x18002fdf2  js      short loc_18002FE00
0x18002fdf4  cvtsi2sd xmm1, r14
0x18002fdf9  jmp     short loc_18002FE16
0x18002fdfb  mov     bl, r12b
0x18002fdfe  jmp     short loc_18002FDA1
0x18002fe00  mov     rcx, r14
0x18002fe03  shr     rcx, 1
0x18002fe06  and     r14d, 1
0x18002fe0a  or      rcx, r14
0x18002fe0d  cvtsi2sd xmm1, rcx
0x18002fe12  addsd   xmm1, xmm1
0x18002fe16  xorps   xmm0, xmm0
0x18002fe19  subsd   xmm0, xmm1
0x18002fe1d  movsd   qword ptr [r15+38h], xmm0
0x18002fe23  mov     dword ptr [r15], 8
0x18002fe2a  mov     al, 1
0x18002fe2c  jmp     loc_18003006B
0x18002fe31  neg     r14
0x18002fe34  mov     [r15+38h], r14
0x18002fe38  mov     dword ptr [r15], 9
0x18002fe3f  jmp     short loc_18002FE2A
0x18002fe41  mov     [r15+38h], r14
0x18002fe45  mov     dword ptr [r15], 9
0x18002fe4c  mov     [r15+40h], r12b
0x18002fe50  jmp     short loc_18002FE2A
0x18002fe52  xorps   xmm0, xmm0
0x18002fe55  xor     eax, eax
0x18002fe57  movups  xmmword ptr [rbp+Buffer], xmm0
0x18002fe5b  mov     [rbp+var_8], rax
0x18002fe5f  lea     edx, [rax+18h]
0x18002fe62  lea     rcx, [rbp+Buffer]
0x18002fe66  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x18002fe6b  nop
0x18002fe6c  mov     rdi, [rbp+Buffer]
0x18002fe70  mov     rbx, [rbp+Buffer+8]
0x18002fe74  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x18002fe79  sub     rbx, rdi
0x18002fe7c  mov     [rsp+50h+var_28], r14
0x18002fe81  mov     [rsp+50h+Locale], rax; Locale
0x18002fe86  lea     r9, aI64u; "%I64u"
0x18002fe8d  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18002fe91  mov     rdx, rbx; BufferCount
0x18002fe94  mov     rcx, rdi; Buffer
0x18002fe97  call    _snprintf_s_l
0x18002fe9c  movsxd  rdx, eax
0x18002fe9f  lea     rcx, [rbp+Buffer]
0x18002fea3  call    ?resize@?$vector@DV?$allocator@D@std@@@std@@QEAAX_K@Z; std::vector<char>::resize(unsigned __int64)
0x18002fea8  mov     bl, r12b
0x18002feab  jmp     loc_18002FF3D
0x18002feb0  lea     eax, [r13-30h]
0x18002feb4  cmp     eax, 9
0x18002feb7  ja      short loc_18002FEBF
0x18002feb9  mov     [rbp+var_20], r13b
0x18002febd  jmp     short loc_18002FF10
0x18002febf  cmp     r13d, 2Eh ; '.'
0x18002fec3  jnz     loc_18002FF4C
0x18002fec9  test    bl, bl
0x18002fecb  jnz     loc_18003005B
0x18002fed1  mov     bl, 1
0x18002fed3  mov     [rbp+var_20], r13b
0x18002fed7  lea     rdx, [rbp+var_20]
0x18002fedb  lea     rcx, [rbp+Buffer]
0x18002fedf  call    ?push_back@?$vector@DV?$allocator@D@std@@@std@@QEAAX$$QEAD@Z; std::vector<char>::push_back(char &&)
0x18002fee4  mov     rax, [rsi]
0x18002fee7  mov     rcx, rsi
0x18002feea  mov     rax, [rax]
0x18002feed  call    _guard_dispatch_icall
0x18002fef2  mov     rax, [rsi]
0x18002fef5  mov     rcx, rsi
0x18002fef8  mov     rax, [rax+8]
0x18002fefc  call    _guard_dispatch_icall
0x18002ff01  lea     ecx, [rax-30h]
0x18002ff04  cmp     ecx, 9
0x18002ff07  ja      loc_18003005B
0x18002ff0d  mov     [rbp+var_20], al
0x18002ff10  lea     rdx, [rbp+var_20]
0x18002ff14  lea     rcx, [rbp+Buffer]
0x18002ff18  call    ?push_back@?$vector@DV?$allocator@D@std@@@std@@QEAAX$$QEAD@Z; std::vector<char>::push_back(char &&)
0x18002ff1d  mov     rax, [rsi]
0x18002ff20  mov     rcx, rsi
0x18002ff23  mov     rax, [rax]
0x18002ff26  call    _guard_dispatch_icall
0x18002ff2b  mov     rax, [rsi]
0x18002ff2e  mov     rcx, rsi
0x18002ff31  mov     rax, [rax+8]
0x18002ff35  call    _guard_dispatch_icall
0x18002ff3a  mov     r13d, eax
0x18002ff3d  cmp     r13d, 0FFFFFFFFh
0x18002ff41  jnz     loc_18002FEB0
0x18002ff47  jmp     loc_180030011
0x18002ff4c  lea     eax, [r13-45h]
0x18002ff50  test    eax, 0FFFFFFDFh
0x18002ff55  jnz     loc_180030011
0x18002ff5b  mov     [rbp+var_20], r13b
0x18002ff5f  lea     rdx, [rbp+var_20]
0x18002ff63  lea     rcx, [rbp+Buffer]
0x18002ff67  call    ?push_back@?$vector@DV?$allocator@D@std@@@std@@QEAAX$$QEAD@Z; std::vector<char>::push_back(char &&)
0x18002ff6c  mov     rax, [rsi]
0x18002ff6f  mov     rcx, rsi
0x18002ff72  mov     rax, [rax]
0x18002ff75  call    _guard_dispatch_icall
0x18002ff7a  mov     rax, [rsi]
0x18002ff7d  mov     rcx, rsi
0x18002ff80  mov     rax, [rax+8]
0x18002ff84  call    _guard_dispatch_icall
0x18002ff89  mov     ecx, eax
0x18002ff8b  cmp     eax, 2Bh ; '+'
0x18002ff8e  jnz     short loc_18002FF95
0x18002ff90  mov     [rbp+var_20], al
0x18002ff93  jmp     short loc_18002FF9D
0x18002ff95  cmp     eax, 2Dh ; '-'
0x18002ff98  jnz     short loc_18002FFC9
0x18002ff9a  mov     [rbp+var_20], al
0x18002ff9d  lea     rdx, [rbp+var_20]
0x18002ffa1  lea     rcx, [rbp+Buffer]
0x18002ffa5  call    ?push_back@?$vector@DV?$allocator@D@std@@@std@@QEAAX$$QEAD@Z; std::vector<char>::push_back(char &&)
0x18002ffaa  mov     rax, [rsi]
0x18002ffad  mov     rcx, rsi
0x18002ffb0  mov     rax, [rax]
0x18002ffb3  call    _guard_dispatch_icall
0x18002ffb8  mov     rax, [rsi]
0x18002ffbb  mov     rcx, rsi
0x18002ffbe  mov     rax, [rax+8]
0x18002ffc2  call    _guard_dispatch_icall
0x18002ffc7  mov     ecx, eax
0x18002ffc9  lea     eax, [rcx-30h]
0x18002ffcc  cmp     eax, 9
0x18002ffcf  ja      loc_18003005B
0x18002ffd5  mov     [rbp+var_20], cl
0x18002ffd8  jmp     short loc_18002FFE2
0x18002ffda  cmp     eax, 39h ; '9'
0x18002ffdd  ja      short loc_180030011
0x18002ffdf  mov     [rbp+var_20], al
0x18002ffe2  lea     rdx, [rbp+var_20]
0x18002ffe6  lea     rcx, [rbp+Buffer]
0x18002ffea  call    ?push_back@?$vector@DV?$allocator@D@std@@@std@@QEAAX$$QEAD@Z; std::vector<char>::push_back(char &&)
0x18002ffef  mov     rax, [rsi]
0x18002fff2  mov     rcx, rsi
0x18002fff5  mov     rax, [rax]
0x18002fff8  call    _guard_dispatch_icall
0x18002fffd  mov     rax, [rsi]
0x180030000  mov     rcx, rsi
0x180030003  mov     rax, [rax+8]
0x180030007  call    _guard_dispatch_icall
0x18003000c  cmp     eax, 30h ; '0'
0x18003000f  jge     short loc_18002FFDA
0x180030011  mov     [rbp+var_20], r12b
0x180030015  lea     rdx, [rbp+var_20]
0x180030019  lea     rcx, [rbp+Buffer]
0x18003001d  call    ?push_back@?$vector@DV?$allocator@D@std@@@std@@QEAAX$$QEAD@Z; std::vector<char>::push_back(char &&)
0x180030022  mov     rbx, [rbp+Buffer]
0x180030026  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x18003002b  mov     r8, rax; Locale
0x18003002e  xor     edx, edx; EndPtr
0x180030030  mov     rcx, rbx; String
0x180030033  call    _strtod_l
0x180030038  movsd   qword ptr [r15+38h], xmm0
0x18003003e  cmp     [rbp+var_1F], r12b
0x180030042  jz      short loc_180030051
0x180030044  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x18003004b  movsd   qword ptr [r15+38h], xmm0
0x180030051  mov     dword ptr [r15], 8
0x180030058  mov     r12b, 1
0x18003005b  lea     rcx, [rbp+Buffer]
0x18003005f  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180030064  mov     al, r12b
0x180030067  jmp     short loc_18003006B
0x180030069  xor     al, al
0x18003006b  mov     rbx, [rsp+50h+arg_18]
0x180030073  add     rsp, 50h
0x180030077  pop     r15
0x180030079  pop     r14
0x18003007b  pop     r13
0x18003007d  pop     r12
0x18003007f  pop     rdi
0x180030080  pop     rsi
0x180030081  pop     rbp
0x180030082  retn
```
