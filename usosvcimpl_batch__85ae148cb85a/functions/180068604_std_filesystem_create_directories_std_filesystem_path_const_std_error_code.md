# std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)

- ea: `0x180068604`
- end: `0x18006886c`
- name: `?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z`
- size: `616`
- prototype: `bool __fastcall(std::filesystem *__hidden this, const struct std::filesystem::path *, struct std::error_code *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180066c88`

## callees

- `0x180011680`
- `0x18002c5bc`
- `0x18002e2d8`
- `0x18002e698`
- `0x180043328`
- `0x180068604`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800687a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800687a6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180068793`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180068793`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall std::filesystem::create_directories(
        std::filesystem *this,
        const struct std::filesystem::path *a2,
        const wchar_t *a3)
{
  const struct std::filesystem::path *v3; // r12
  std::filesystem *v4; // rdi
  DWORD v5; // r13d
  unsigned __int64 v7; // rax
  std::filesystem *v8; // rcx
  const wchar_t *v9; // rsi
  const wchar_t *i; // rbx
  char v11; // r14
  DWORD LastError; // eax
  const wchar_t *v13; // rdi
  const WCHAR *v14; // rbx
  DWORD v15; // ecx
  __int128 v16; // [rsp+28h] [rbp-58h]
  LPCWSTR lpPathName[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v18; // [rsp+68h] [rbp-18h]
  unsigned __int64 v19; // [rsp+70h] [rbp-10h]

  v3 = a2;
  *(_QWORD *)&v16 = a2;
  v4 = this;
  v5 = 0;
  if ( *((_QWORD *)this + 2) )
  {
    *(_DWORD *)a2 = 0;
    *((_QWORD *)a2 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)lpPathName = 0;
    v18 = 0;
    v19 = 7;
    LOWORD(lpPathName[0]) = 0;
    v7 = *((_QWORD *)this + 2);
    if ( v7 > 7 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(lpPathName);
      v18 = 0;
      v7 = *((_QWORD *)v4 + 2);
    }
    if ( *((_QWORD *)v4 + 3) <= 7u )
    {
      v8 = v4;
    }
    else
    {
      v8 = *(std::filesystem **)v4;
      v4 = *(std::filesystem **)v4;
    }
    v9 = (const wchar_t *)((char *)v8 + 2 * v7);
    for ( i = std::filesystem::_Find_root_name_end(v4, v9, a3); i != v9; ++i )
    {
      if ( *i != 92 && *i != 47 )
        break;
    }
    if ( i != (const wchar_t *)v4
      && (__int64)(((char *)v9 - (char *)i) & 0xFFFFFFFFFFFFFFFEuLL) >= 6
      && (*(_DWORD *)i & 0xFFFFFFDF) - 3801153 < 0x1A
      && (i[2] == 92 || i[2] == 47) )
    {
      i += 2;
    }
    std::wstring::append(lpPathName);
    v11 = 0;
    LastError = 0;
    if ( i != v9 )
    {
      do
      {
        v13 = i;
        do
        {
          if ( *v13 != 92 && *v13 != 47 )
            break;
          ++v13;
        }
        while ( v13 != v9 );
        while ( v13 != v9 && *v13 != 92 && *v13 != 47 )
          ++v13;
        std::wstring::append(lpPathName);
        v14 = (const WCHAR *)lpPathName;
        if ( v19 > 7 )
          v14 = lpPathName[0];
        if ( CreateDirectoryW(v14, 0) )
        {
          v11 = 1;
          LastError = 0;
          v15 = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError == 183 )
          {
            LastError = _std_fs_get_stats(v14);
            if ( !LastError )
              LastError = 183;
          }
          v11 = 0;
          v15 = LastError;
          if ( LastError )
          {
            if ( LastError != 2
              && LastError != 3
              && LastError != 53
              && LastError != 64
              && LastError != 123
              && LastError != 267 )
            {
              v5 = LastError;
            }
            v15 = LastError;
          }
        }
        i = v13;
      }
      while ( v13 != v9 );
      v3 = (const struct std::filesystem::path *)v16;
      if ( v15 )
      {
        if ( v5 )
          LastError = v5;
      }
    }
    LODWORD(v16) = LastError;
    *((_QWORD *)&v16 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)v3 = v16;
    std::wstring::~wstring(lpPathName);
    return v11;
  }
  else
  {
    LODWORD(v16) = 3;
    *((_QWORD *)&v16 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)a2 = v16;
    return 0;
  }
}

```

## disassembly

```asm
0x180068604  mov     [rsp-38h+arg_10], rbx
0x180068609  push    rbp
0x18006860a  push    rsi
0x18006860b  push    rdi
0x18006860c  push    r12
0x18006860e  push    r13
0x180068610  push    r14
0x180068612  push    r15
0x180068614  mov     rbp, rsp
0x180068617  sub     rsp, 80h
0x18006861e  mov     rax, cs:__security_cookie
0x180068625  xor     rax, rsp
0x180068628  mov     [rbp+var_8], rax
0x18006862c  mov     r12, rdx
0x18006862f  mov     qword ptr [rbp+var_58], rdx
0x180068633  mov     rdi, rcx
0x180068636  xor     r13d, r13d
0x180068639  lea     r15, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180068640  cmp     [rcx+10h], r13
0x180068644  jnz     short loc_180068660
0x180068646  mov     dword ptr [rbp+var_58], 3
0x18006864d  mov     qword ptr [rbp+var_58+8], r15
0x180068651  movups  xmm0, [rbp+var_58]
0x180068655  movdqu  xmmword ptr [rdx], xmm0
0x180068659  xor     al, al
0x18006865b  jmp     loc_180068845
0x180068660  mov     [rdx], r13d
0x180068663  mov     [rdx+8], r15
0x180068667  xorps   xmm0, xmm0
0x18006866a  movups  xmmword ptr [rbp+lpPathName], xmm0
0x18006866e  mov     [rbp+var_18], r13
0x180068672  mov     [rbp+var_10], 7
0x18006867a  mov     word ptr [rbp+lpPathName], r13w
0x18006867f  mov     rax, [rcx+10h]
0x180068683  cmp     rax, 7
0x180068687  jbe     short loc_18006869D
0x180068689  mov     rdx, rax
0x18006868c  lea     rcx, [rbp+lpPathName]; Src
0x180068690  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180068695  mov     [rbp+var_18], r13
0x180068699  mov     rax, [rdi+10h]
0x18006869d  cmp     qword ptr [rdi+18h], 7
0x1800686a2  jbe     short loc_1800686AC
0x1800686a4  mov     rcx, [rdi]
0x1800686a7  mov     rdi, rcx
0x1800686aa  jmp     short loc_1800686AF
0x1800686ac  mov     rcx, rdi
0x1800686af  lea     rsi, [rcx+rax*2]
0x1800686b3  mov     rdx, rsi; wchar_t *
0x1800686b6  mov     rcx, rdi; this
0x1800686b9  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x1800686be  mov     rbx, rax
0x1800686c1  cmp     rax, rsi
0x1800686c4  jz      short loc_1800686DB
0x1800686c6  cmp     word ptr [rbx], 5Ch ; '\'
0x1800686ca  jz      short loc_1800686D2
0x1800686cc  cmp     word ptr [rbx], 2Fh ; '/'
0x1800686d0  jnz     short loc_1800686DB
0x1800686d2  add     rbx, 2
0x1800686d6  cmp     rbx, rsi
0x1800686d9  jnz     short loc_1800686C6
0x1800686db  cmp     rbx, rdi
0x1800686de  jz      short loc_180068712
0x1800686e0  mov     rax, rsi
0x1800686e3  sub     rax, rbx
0x1800686e6  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800686ea  cmp     rax, 6
0x1800686ee  jl      short loc_180068712
0x1800686f0  mov     eax, [rbx]
0x1800686f2  and     eax, 0FFFFFFDFh
0x1800686f5  sub     eax, 3A0041h
0x1800686fa  cmp     eax, 1Ah
0x1800686fd  jnb     short loc_180068712
0x1800686ff  lea     rax, [rbx+4]
0x180068703  cmp     word ptr [rax], 5Ch ; '\'
0x180068707  jz      short loc_18006870F
0x180068709  cmp     word ptr [rax], 2Fh ; '/'
0x18006870d  jnz     short loc_180068712
0x18006870f  mov     rbx, rax
0x180068712  mov     r8, rbx
0x180068715  sub     r8, rdi
0x180068718  sar     r8, 1
0x18006871b  mov     rdx, rdi
0x18006871e  lea     rcx, [rbp+lpPathName]; Src
0x180068722  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180068727  mov     r14b, r13b
0x18006872a  mov     eax, r13d
0x18006872d  cmp     rbx, rsi
0x180068730  jz      loc_180068828
0x180068736  mov     r12d, 0B7h
0x18006873c  mov     rdi, rbx
0x18006873f  cmp     word ptr [rdi], 5Ch ; '\'
0x180068743  jz      short loc_18006874B
0x180068745  cmp     word ptr [rdi], 2Fh ; '/'
0x180068749  jnz     short loc_180068766
0x18006874b  add     rdi, 2
0x18006874f  cmp     rdi, rsi
0x180068752  jnz     short loc_18006873F
0x180068754  jmp     short loc_180068766
0x180068756  cmp     word ptr [rdi], 5Ch ; '\'
0x18006875a  jz      short loc_18006876B
0x18006875c  cmp     word ptr [rdi], 2Fh ; '/'
0x180068760  jz      short loc_18006876B
0x180068762  add     rdi, 2
0x180068766  cmp     rdi, rsi
0x180068769  jnz     short loc_180068756
0x18006876b  mov     r8, rdi
0x18006876e  sub     r8, rbx
0x180068771  sar     r8, 1
0x180068774  mov     rdx, rbx
0x180068777  lea     rcx, [rbp+lpPathName]; Src
0x18006877b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180068780  lea     rbx, [rbp+lpPathName]
0x180068784  cmp     [rbp+var_10], 7
0x180068789  cmova   rbx, [rbp+lpPathName]
0x18006878e  xor     edx, edx; lpSecurityAttributes
0x180068790  mov     rcx, rbx; lpPathName
0x180068793  call    cs:__imp_CreateDirectoryW
0x180068799  test    eax, eax
0x18006879b  jz      short loc_1800687A6
0x18006879d  mov     r14b, 1
0x1800687a0  xor     eax, eax
0x1800687a2  xor     ecx, ecx
0x1800687a4  jmp     short loc_18006880D
0x1800687a6  call    cs:__imp_GetLastError
0x1800687ac  cmp     eax, r12d
0x1800687af  jnz     short loc_1800687DE
0x1800687b1  xorps   xmm0, xmm0
0x1800687b4  movups  [rbp+var_48], xmm0
0x1800687b8  movups  [rbp+var_38], xmm0
0x1800687bc  or      r9d, 0FFFFFFFFh
0x1800687c0  mov     r8d, 3
0x1800687c6  lea     rdx, [rbp+var_48]
0x1800687ca  mov     rcx, rbx; lpFileName
0x1800687cd  call    __std_fs_get_stats
0x1800687d2  test    eax, eax
0x1800687d4  jnz     short loc_1800687DE
0x1800687d6  test    byte ptr [rbp+var_38], 10h
0x1800687da  cmovz   eax, r12d
0x1800687de  xor     r14b, r14b
0x1800687e1  mov     ecx, eax
0x1800687e3  test    eax, eax
0x1800687e5  jz      short loc_18006880D
0x1800687e7  sub     ecx, 2
0x1800687ea  jz      short loc_18006880B
0x1800687ec  sub     ecx, 1
0x1800687ef  jz      short loc_18006880B
0x1800687f1  sub     ecx, 32h ; '2'
0x1800687f4  jz      short loc_18006880B
0x1800687f6  sub     ecx, 0Bh
0x1800687f9  jz      short loc_18006880B
0x1800687fb  sub     ecx, 3Bh ; ';'
0x1800687fe  jz      short loc_18006880B
0x180068800  cmp     ecx, 90h
0x180068806  jz      short loc_18006880B
0x180068808  mov     r13d, eax
0x18006880b  mov     ecx, eax
0x18006880d  mov     rbx, rdi
0x180068810  cmp     rdi, rsi
0x180068813  jnz     loc_18006873C
0x180068819  test    ecx, ecx
0x18006881b  mov     r12, qword ptr [rbp+var_58]
0x18006881f  jz      short loc_180068828
0x180068821  test    r13d, r13d
0x180068824  cmovnz  eax, r13d
0x180068828  mov     dword ptr [rbp+var_58], eax
0x18006882b  mov     qword ptr [rbp+var_58+8], r15
0x18006882f  movups  xmm0, [rbp+var_58]
0x180068833  movdqu  xmmword ptr [r12], xmm0
0x180068839  lea     rcx, [rbp+lpPathName]; void *
0x18006883d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180068842  mov     al, r14b
0x180068845  mov     rcx, [rbp+var_8]
0x180068849  xor     rcx, rsp; StackCookie
0x18006884c  call    __security_check_cookie
0x180068851  mov     rbx, [rsp+80h+arg_10]
0x180068859  add     rsp, 80h
0x180068860  pop     r15
0x180068862  pop     r14
0x180068864  pop     r13
0x180068866  pop     r12
0x180068868  pop     rdi
0x180068869  pop     rsi
0x18006886a  pop     rbp
0x18006886b  retn
```
