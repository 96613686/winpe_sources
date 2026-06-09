# __stdio_common_vswprintf

- ea: `0x10042d618`
- end: `0x10042d871`
- name: `__stdio_common_vswprintf`
- size: `601`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x10041dcc0`

## callees

- `0x100426580`
- `0x10042c550`
- `0x10042c654`
- `0x10042d618`
- `0x10042e504`
- `0x10042e7dc`

## pseudocode

```c
int __cdecl _stdio_common_vswprintf(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  char v8; // r15
  __crt_locale_pointers v9; // xmm0
  size_t v10; // rdi
  int v11; // eax
  __int64 v12; // rax
  void *v13; // rcx
  int v14; // ebx
  int v15; // ebx
  _QWORD v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h]
  char v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+49h] [rbp-B7h]
  __int16 v21; // [rsp+4Dh] [rbp-B3h]
  char v22; // [rsp+4Fh] [rbp-B1h]
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+60h] [rbp-A0h]
  __crt_locale_pointers v25; // [rsp+68h] [rbp-98h]
  char v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+7Ch] [rbp-84h]
  char v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+84h] [rbp-7Ch]
  char v30; // [rsp+88h] [rbp-78h]
  _QWORD v31[4]; // [rsp+90h] [rbp-70h] BYREF
  int v32; // [rsp+B0h] [rbp-50h]
  char v33; // [rsp+B4h] [rbp-4Ch]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  int v35; // [rsp+C0h] [rbp-40h]
  char v36; // [rsp+C8h] [rbp-38h]
  __int16 v37; // [rsp+CAh] [rbp-36h]
  int v38; // [rsp+D8h] [rbp-28h]
  char v39; // [rsp+DCh] [rbp-24h]
  void *Block[2]; // [rsp+4E0h] [rbp+3E0h]
  _QWORD *v41; // [rsp+4F0h] [rbp+3F0h]
  int v42; // [rsp+4F8h] [rbp+3F8h]

  v23[0] = 0;
  v24 = 0;
  v26 = 0;
  v8 = Options;
  v28 = 0;
  v30 = 0;
  if ( Locale )
  {
    v9 = *Locale;
LABEL_5:
    v26 = 1;
    v25 = v9;
    goto LABEL_6;
  }
  if ( !_acrt_locale_changed_data )
  {
    v9 = *(__crt_locale_pointers *)&_acrt_initial_locale_pointers;
    goto LABEL_5;
  }
LABEL_6:
  if ( !Format || BufferCount && !Buffer )
  {
    v28 = 1;
    v27 = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v23);
LABEL_8:
    LODWORD(v10) = -1;
    goto LABEL_34;
  }
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v17[0] = Buffer;
  v17[1] = BufferCount;
  v18 = 0;
  if ( (Options & 2) != 0 || (v19 = 0, !Buffer) )
    v19 = 1;
  v32 = 0;
  v31[1] = v23;
  v33 = 0;
  v41 = v17;
  v31[3] = ArgList;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  *(_OWORD *)Block = 0;
  v31[0] = Options;
  v31[2] = Format;
  v42 = 0;
  v11 = __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(v31);
  v10 = v11;
  if ( !Buffer )
    goto LABEL_33;
  if ( (v8 & 1) != 0 )
  {
    if ( !BufferCount && v11 )
      goto LABEL_18;
    v12 = v18;
    if ( v18 == BufferCount )
    {
      if ( (v10 & 0x80000000) == 0LL && v10 > BufferCount )
        goto LABEL_18;
      goto LABEL_33;
    }
    goto LABEL_32;
  }
  if ( (v8 & 2) == 0 )
  {
    if ( !BufferCount )
    {
LABEL_18:
      free_base(Block[1]);
      goto LABEL_8;
    }
    v12 = v18;
    if ( v18 == BufferCount )
    {
      v13 = Block[1];
      Buffer[BufferCount - 1] = 0;
      free_base(v13);
      LODWORD(v10) = -2;
      goto LABEL_34;
    }
    goto LABEL_32;
  }
  if ( BufferCount )
  {
    if ( v11 < 0 )
    {
      *Buffer = 0;
      goto LABEL_33;
    }
    v12 = v18;
    if ( v18 == BufferCount )
    {
      Buffer[BufferCount - 1] = 0;
      goto LABEL_33;
    }
LABEL_32:
    Buffer[v12] = 0;
  }
LABEL_33:
  free_base(Block[1]);
LABEL_34:
  if ( v26 == 2 )
    *(_DWORD *)(v23[0] + 936LL) &= ~2u;
  if ( v28 )
  {
    v14 = v27;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v23) + 8) = v14;
  }
  if ( v30 )
  {
    v15 = v29;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v23) + 9) = v15;
  }
  return v10;
}

```

## disassembly

```asm
0x10042d618  push    rbp
0x10042d61a  push    rbx
0x10042d61b  push    rsi
0x10042d61c  push    rdi
0x10042d61d  push    r12
0x10042d61f  push    r14
0x10042d621  push    r15
0x10042d623  lea     rbp, [rsp-410h]
0x10042d62b  sub     rsp, 510h
0x10042d632  mov     rax, cs:__security_cookie
0x10042d639  xor     rax, rsp
0x10042d63c  mov     [rbp+440h+var_40], rax
0x10042d643  mov     rax, [rbp+440h+Locale]
0x10042d64a  xor     r12d, r12d
0x10042d64d  mov     [rsp+540h+var_4F0], r12
0x10042d652  mov     rbx, r8
0x10042d655  mov     [rsp+540h+var_4E0], r12b
0x10042d65a  mov     rsi, rdx
0x10042d65d  mov     [rsp+540h+var_4C8], r12b
0x10042d662  mov     r15, rcx
0x10042d665  mov     [rbp+440h+var_4C0], r12b
0x10042d669  mov     [rbp+440h+var_4B8], r12b
0x10042d66d  test    rax, rax
0x10042d670  jz      short loc_10042D677
0x10042d672  movups  xmm0, xmmword ptr [rax]
0x10042d675  jmp     short loc_10042D687
0x10042d677  cmp     cs:__acrt_locale_changed_data, r12d
0x10042d67e  jnz     short loc_10042D692
0x10042d680  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x10042d687  mov     [rsp+540h+var_4C8], 1
0x10042d68c  movdqu  [rsp+540h+var_4D8], xmm0
0x10042d692  test    r9, r9
0x10042d695  jnz     short loc_10042D6C9
0x10042d697  lea     rax, [rsp+540h+var_4F0]
0x10042d69c  mov     [rbp+440h+var_4C0], 1
0x10042d6a0  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x10042d6a5  xor     r9d, r9d; LineNo
0x10042d6a8  xor     r8d, r8d; FileName
0x10042d6ab  mov     [rsp+540h+var_520], r12; uintptr_t
0x10042d6b0  xor     edx, edx; FunctionName
0x10042d6b2  mov     [rsp+540h+var_4C4], 16h
0x10042d6ba  xor     ecx, ecx; Expression
0x10042d6bc  call    _invalid_parameter_internal
0x10042d6c1  or      edi, 0FFFFFFFFh
0x10042d6c4  jmp     loc_10042D80E
0x10042d6c9  test    rbx, rbx
0x10042d6cc  jz      short loc_10042D6D3
0x10042d6ce  test    rsi, rsi
0x10042d6d1  jz      short loc_10042D697
0x10042d6d3  mov     r14, r15
0x10042d6d6  mov     [rsp+540h+var_4F7], r12d
0x10042d6db  mov     [rsp+540h+var_4F3], r12w
0x10042d6e1  mov     [rsp+540h+var_4F1], r12b
0x10042d6e6  mov     [rsp+540h+var_510], rsi
0x10042d6eb  mov     [rsp+540h+var_508], rbx
0x10042d6f0  mov     [rsp+540h+var_500], r12
0x10042d6f5  and     r14d, 2
0x10042d6f9  jnz     short loc_10042D705
0x10042d6fb  mov     [rsp+540h+var_4F8], r12b
0x10042d700  test    rsi, rsi
0x10042d703  jnz     short loc_10042D70A
0x10042d705  mov     [rsp+540h+var_4F8], 1
0x10042d70a  lea     rax, [rsp+540h+var_4F0]
0x10042d70f  mov     [rbp+440h+var_490], r12d
0x10042d713  mov     [rbp+440h+var_4A8], rax
0x10042d717  lea     rcx, [rbp+440h+var_4B0]
0x10042d71b  lea     rax, [rsp+540h+var_510]
0x10042d720  mov     [rbp+440h+var_48C], r12b
0x10042d724  mov     [rbp+440h+var_50], rax
0x10042d72b  xorps   xmm0, xmm0
0x10042d72e  mov     rax, [rbp+440h+ArgList]
0x10042d735  mov     [rbp+440h+var_498], rax
0x10042d739  mov     [rbp+440h+var_488], r12
0x10042d73d  mov     [rbp+440h+var_480], r12d
0x10042d741  mov     [rbp+440h+var_478], r12b
0x10042d745  mov     [rbp+440h+var_476], r12w
0x10042d74a  mov     [rbp+440h+var_468], r12d
0x10042d74e  mov     [rbp+440h+var_464], r12b
0x10042d752  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x10042d75a  mov     [rbp+440h+var_4B0], r15
0x10042d75e  mov     [rbp+440h+var_4A0], r9
0x10042d762  mov     [rbp+440h+var_48], r12d
0x10042d769  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x10042d76e  movsxd  rdi, eax
0x10042d771  test    rsi, rsi
0x10042d774  jz      loc_10042D802
0x10042d77a  test    r15b, 1
0x10042d77e  jz      short loc_10042D7AF
0x10042d780  test    rbx, rbx
0x10042d783  jnz     short loc_10042D79A
0x10042d785  test    eax, eax
0x10042d787  jz      short loc_10042D79A
0x10042d789  mov     rcx, [rbp+440h+Block+8]; Block
0x10042d790  call    _free_base
0x10042d795  jmp     loc_10042D6C1
0x10042d79a  mov     rax, [rsp+540h+var_500]
0x10042d79f  cmp     rax, rbx
0x10042d7a2  jnz     short loc_10042D7FD
0x10042d7a4  test    edi, edi
0x10042d7a6  js      short loc_10042D802
0x10042d7a8  cmp     rdi, rbx
0x10042d7ab  jbe     short loc_10042D802
0x10042d7ad  jmp     short loc_10042D789
0x10042d7af  test    r14, r14
0x10042d7b2  jz      short loc_10042D7D5
0x10042d7b4  test    rbx, rbx
0x10042d7b7  jz      short loc_10042D802
0x10042d7b9  test    eax, eax
0x10042d7bb  jns     short loc_10042D7C3
0x10042d7bd  mov     [rsi], r12w
0x10042d7c1  jmp     short loc_10042D802
0x10042d7c3  mov     rax, [rsp+540h+var_500]
0x10042d7c8  cmp     rax, rbx
0x10042d7cb  jnz     short loc_10042D7FD
0x10042d7cd  mov     [rsi+rbx*2-2], r12w
0x10042d7d3  jmp     short loc_10042D802
0x10042d7d5  test    rbx, rbx
0x10042d7d8  jz      short loc_10042D789
0x10042d7da  mov     rax, [rsp+540h+var_500]
0x10042d7df  cmp     rax, rbx
0x10042d7e2  jnz     short loc_10042D7FD
0x10042d7e4  mov     rcx, [rbp+440h+Block+8]; Block
0x10042d7eb  mov     [rsi+rbx*2-2], r12w
0x10042d7f1  call    _free_base
0x10042d7f6  mov     edi, 0FFFFFFFEh
0x10042d7fb  jmp     short loc_10042D80E
0x10042d7fd  mov     [rsi+rax*2], r12w
0x10042d802  mov     rcx, [rbp+440h+Block+8]; Block
0x10042d809  call    _free_base
0x10042d80e  cmp     [rsp+540h+var_4C8], 2
0x10042d813  jnz     short loc_10042D821
0x10042d815  mov     rax, [rsp+540h+var_4F0]
0x10042d81a  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x10042d821  cmp     [rbp+440h+var_4C0], r12b
0x10042d825  jz      short loc_10042D838
0x10042d827  mov     ebx, [rsp+540h+var_4C4]
0x10042d82b  lea     rcx, [rsp+540h+var_4F0]; this
0x10042d830  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x10042d835  mov     [rax+20h], ebx
0x10042d838  cmp     [rbp+440h+var_4B8], r12b
0x10042d83c  jz      short loc_10042D84E
0x10042d83e  mov     ebx, [rbp+440h+var_4BC]
0x10042d841  lea     rcx, [rsp+540h+var_4F0]; this
0x10042d846  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x10042d84b  mov     [rax+24h], ebx
0x10042d84e  mov     eax, edi
0x10042d850  mov     rcx, [rbp+440h+var_40]
0x10042d857  xor     rcx, rsp; StackCookie
0x10042d85a  call    __security_check_cookie
0x10042d85f  add     rsp, 510h
0x10042d866  pop     r15
0x10042d868  pop     r14
0x10042d86a  pop     r12
0x10042d86c  pop     rdi
0x10042d86d  pop     rsi
0x10042d86e  pop     rbx
0x10042d86f  pop     rbp
0x10042d870  retn
```
