# std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)

- ea: `0x180064504`
- end: `0x18006476c`
- name: `?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z`
- size: `616`
- prototype: `bool __fastcall(std::filesystem *__hidden this, const struct std::filesystem::path *, struct std::error_code *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180039bd4`
- `0x180039e64`

## callees

- `0x180018c00`
- `0x180018eec`
- `0x18001adcc`
- `0x180064504`
- `0x180065d10`
- `0x18007a3e8`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800646a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800646a6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180064693`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180064693`

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
    std::wstring::~wstring((__int64)lpPathName);
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
0x180064504  mov     [rsp-38h+arg_10], rbx
0x180064509  push    rbp
0x18006450a  push    rsi
0x18006450b  push    rdi
0x18006450c  push    r12
0x18006450e  push    r13
0x180064510  push    r14
0x180064512  push    r15
0x180064514  mov     rbp, rsp
0x180064517  sub     rsp, 80h
0x18006451e  mov     rax, cs:__security_cookie
0x180064525  xor     rax, rsp
0x180064528  mov     [rbp+var_8], rax
0x18006452c  mov     r12, rdx
0x18006452f  mov     qword ptr [rbp+var_58], rdx
0x180064533  mov     rdi, rcx
0x180064536  xor     r13d, r13d
0x180064539  lea     r15, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180064540  cmp     [rcx+10h], r13
0x180064544  jnz     short loc_180064560
0x180064546  mov     dword ptr [rbp+var_58], 3
0x18006454d  mov     qword ptr [rbp+var_58+8], r15
0x180064551  movups  xmm0, [rbp+var_58]
0x180064555  movdqu  xmmword ptr [rdx], xmm0
0x180064559  xor     al, al
0x18006455b  jmp     loc_180064745
0x180064560  mov     [rdx], r13d
0x180064563  mov     [rdx+8], r15
0x180064567  xorps   xmm0, xmm0
0x18006456a  movups  xmmword ptr [rbp+lpPathName], xmm0
0x18006456e  mov     [rbp+var_18], r13
0x180064572  mov     [rbp+var_10], 7
0x18006457a  mov     word ptr [rbp+lpPathName], r13w
0x18006457f  mov     rax, [rcx+10h]
0x180064583  cmp     rax, 7
0x180064587  jbe     short loc_18006459D
0x180064589  mov     rdx, rax
0x18006458c  lea     rcx, [rbp+lpPathName]; Src
0x180064590  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180064595  mov     [rbp+var_18], r13
0x180064599  mov     rax, [rdi+10h]
0x18006459d  cmp     qword ptr [rdi+18h], 7
0x1800645a2  jbe     short loc_1800645AC
0x1800645a4  mov     rcx, [rdi]
0x1800645a7  mov     rdi, rcx
0x1800645aa  jmp     short loc_1800645AF
0x1800645ac  mov     rcx, rdi
0x1800645af  lea     rsi, [rcx+rax*2]
0x1800645b3  mov     rdx, rsi; wchar_t *
0x1800645b6  mov     rcx, rdi; this
0x1800645b9  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x1800645be  mov     rbx, rax
0x1800645c1  cmp     rax, rsi
0x1800645c4  jz      short loc_1800645DB
0x1800645c6  cmp     word ptr [rbx], 5Ch ; '\'
0x1800645ca  jz      short loc_1800645D2
0x1800645cc  cmp     word ptr [rbx], 2Fh ; '/'
0x1800645d0  jnz     short loc_1800645DB
0x1800645d2  add     rbx, 2
0x1800645d6  cmp     rbx, rsi
0x1800645d9  jnz     short loc_1800645C6
0x1800645db  cmp     rbx, rdi
0x1800645de  jz      short loc_180064612
0x1800645e0  mov     rax, rsi
0x1800645e3  sub     rax, rbx
0x1800645e6  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800645ea  cmp     rax, 6
0x1800645ee  jl      short loc_180064612
0x1800645f0  mov     eax, [rbx]
0x1800645f2  and     eax, 0FFFFFFDFh
0x1800645f5  sub     eax, 3A0041h
0x1800645fa  cmp     eax, 1Ah
0x1800645fd  jnb     short loc_180064612
0x1800645ff  lea     rax, [rbx+4]
0x180064603  cmp     word ptr [rax], 5Ch ; '\'
0x180064607  jz      short loc_18006460F
0x180064609  cmp     word ptr [rax], 2Fh ; '/'
0x18006460d  jnz     short loc_180064612
0x18006460f  mov     rbx, rax
0x180064612  mov     r8, rbx
0x180064615  sub     r8, rdi
0x180064618  sar     r8, 1
0x18006461b  mov     rdx, rdi
0x18006461e  lea     rcx, [rbp+lpPathName]; Src
0x180064622  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180064627  mov     r14b, r13b
0x18006462a  mov     eax, r13d
0x18006462d  cmp     rbx, rsi
0x180064630  jz      loc_180064728
0x180064636  mov     r12d, 0B7h
0x18006463c  mov     rdi, rbx
0x18006463f  cmp     word ptr [rdi], 5Ch ; '\'
0x180064643  jz      short loc_18006464B
0x180064645  cmp     word ptr [rdi], 2Fh ; '/'
0x180064649  jnz     short loc_180064666
0x18006464b  add     rdi, 2
0x18006464f  cmp     rdi, rsi
0x180064652  jnz     short loc_18006463F
0x180064654  jmp     short loc_180064666
0x180064656  cmp     word ptr [rdi], 5Ch ; '\'
0x18006465a  jz      short loc_18006466B
0x18006465c  cmp     word ptr [rdi], 2Fh ; '/'
0x180064660  jz      short loc_18006466B
0x180064662  add     rdi, 2
0x180064666  cmp     rdi, rsi
0x180064669  jnz     short loc_180064656
0x18006466b  mov     r8, rdi
0x18006466e  sub     r8, rbx
0x180064671  sar     r8, 1
0x180064674  mov     rdx, rbx
0x180064677  lea     rcx, [rbp+lpPathName]; Src
0x18006467b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180064680  lea     rbx, [rbp+lpPathName]
0x180064684  cmp     [rbp+var_10], 7
0x180064689  cmova   rbx, [rbp+lpPathName]
0x18006468e  xor     edx, edx; lpSecurityAttributes
0x180064690  mov     rcx, rbx; lpPathName
0x180064693  call    cs:__imp_CreateDirectoryW
0x180064699  test    eax, eax
0x18006469b  jz      short loc_1800646A6
0x18006469d  mov     r14b, 1
0x1800646a0  xor     eax, eax
0x1800646a2  xor     ecx, ecx
0x1800646a4  jmp     short loc_18006470D
0x1800646a6  call    cs:__imp_GetLastError
0x1800646ac  cmp     eax, r12d
0x1800646af  jnz     short loc_1800646DE
0x1800646b1  xorps   xmm0, xmm0
0x1800646b4  movups  [rbp+var_48], xmm0
0x1800646b8  movups  [rbp+var_38], xmm0
0x1800646bc  or      r9d, 0FFFFFFFFh
0x1800646c0  mov     r8d, 3
0x1800646c6  lea     rdx, [rbp+var_48]
0x1800646ca  mov     rcx, rbx; lpFileName
0x1800646cd  call    __std_fs_get_stats
0x1800646d2  test    eax, eax
0x1800646d4  jnz     short loc_1800646DE
0x1800646d6  test    byte ptr [rbp+var_38], 10h
0x1800646da  cmovz   eax, r12d
0x1800646de  xor     r14b, r14b
0x1800646e1  mov     ecx, eax
0x1800646e3  test    eax, eax
0x1800646e5  jz      short loc_18006470D
0x1800646e7  sub     ecx, 2
0x1800646ea  jz      short loc_18006470B
0x1800646ec  sub     ecx, 1
0x1800646ef  jz      short loc_18006470B
0x1800646f1  sub     ecx, 32h ; '2'
0x1800646f4  jz      short loc_18006470B
0x1800646f6  sub     ecx, 0Bh
0x1800646f9  jz      short loc_18006470B
0x1800646fb  sub     ecx, 3Bh ; ';'
0x1800646fe  jz      short loc_18006470B
0x180064700  cmp     ecx, 90h
0x180064706  jz      short loc_18006470B
0x180064708  mov     r13d, eax
0x18006470b  mov     ecx, eax
0x18006470d  mov     rbx, rdi
0x180064710  cmp     rdi, rsi
0x180064713  jnz     loc_18006463C
0x180064719  test    ecx, ecx
0x18006471b  mov     r12, qword ptr [rbp+var_58]
0x18006471f  jz      short loc_180064728
0x180064721  test    r13d, r13d
0x180064724  cmovnz  eax, r13d
0x180064728  mov     dword ptr [rbp+var_58], eax
0x18006472b  mov     qword ptr [rbp+var_58+8], r15
0x18006472f  movups  xmm0, [rbp+var_58]
0x180064733  movdqu  xmmword ptr [r12], xmm0
0x180064739  lea     rcx, [rbp+lpPathName]
0x18006473d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180064742  mov     al, r14b
0x180064745  mov     rcx, [rbp+var_8]
0x180064749  xor     rcx, rsp; StackCookie
0x18006474c  call    __security_check_cookie
0x180064751  mov     rbx, [rsp+80h+arg_10]
0x180064759  add     rsp, 80h
0x180064760  pop     r15
0x180064762  pop     r14
0x180064764  pop     r13
0x180064766  pop     r12
0x180064768  pop     rdi
0x180064769  pop     rsi
0x18006476a  pop     rbp
0x18006476b  retn
```
