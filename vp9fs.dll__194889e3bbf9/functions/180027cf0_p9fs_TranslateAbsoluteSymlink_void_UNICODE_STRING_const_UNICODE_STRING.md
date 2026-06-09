# p9fs::TranslateAbsoluteSymlink(void *,_UNICODE_STRING const *,_UNICODE_STRING *)

- ea: `0x180027cf0`
- end: `0x18002837c`
- name: `?TranslateAbsoluteSymlink@p9fs@@YAJPEAXPEBU_UNICODE_STRING@@PEAU2@@Z`
- size: `1676`
- prototype: `__int64 __fastcall(p9fs *__hidden this, void *, const struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path`

## callees

- `0x180003d20`
- `0x180004120`
- `0x180004c68`
- `0x180004c74`
- `0x180004c98`
- `0x18001cd30`
- `0x18001ce4c`
- `0x18001d8b4`
- `0x18001d940`
- `0x18001dc10`
- `0x180022f2c`
- `0x180023460`
- `0x180023ba4`
- `0x180025bd8`
- `0x180027cf0`
- `0x1800286dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180027dfe`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180027dfe`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180027fb1`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180027fb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028037`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028037`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028048`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028048`
- `lxutil!LxUtilNtPathToLxPath` at `0x1800282c7`
- `lxutil!LxUtilNtPathToLxPath` at `0x1800282c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall p9fs::TranslateAbsoluteSymlink(
        p9fs *this,
        _QWORD *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rdi
  wchar_t **v8; // rdx
  wchar_t **v9; // rbx
  wchar_t **v10; // r14
  wchar_t **v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rsi
  unsigned __int64 v14; // r8
  wchar_t **v15; // rsi
  const wchar_t *v16; // rcx
  unsigned int v17; // ebx
  _QWORD *v18; // rdx
  wchar_t **v19; // rcx
  wchar_t **v20; // rdx
  SIZE_T v21; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v23; // rax
  PWSTR Buffer; // rdx
  _QWORD *v25; // rax
  __int64 v26; // r10
  unsigned __int64 v27; // rcx
  __int64 v28; // r9
  unsigned __int64 v29; // r8
  WCHAR v30; // r11
  __int64 v31; // r9
  unsigned __int64 v32; // rsi
  __int64 v33; // r10
  WCHAR *v34; // r11
  unsigned __int64 v35; // rcx
  WCHAR *v36; // rdi
  int v37; // eax
  WCHAR v38; // dx
  wchar_t **v39; // r11
  unsigned __int64 v40; // r10
  unsigned __int64 v41; // rdi
  unsigned __int64 v42; // r10
  WCHAR *v43; // rdx
  __int16 v44; // cx
  WCHAR v45; // ax
  int v47; // [rsp+20h] [rbp-89h]
  __int16 v48; // [rsp+30h] [rbp-79h] BYREF
  __int128 pExceptionObject; // [rsp+38h] [rbp-71h] BYREF
  __int128 v50; // [rsp+48h] [rbp-61h]
  WCHAR *v51; // [rsp+58h] [rbp-51h]
  struct _UNICODE_STRING v52; // [rsp+68h] [rbp-41h] BYREF
  wchar_t *S1[2]; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v54; // [rsp+88h] [rbp-21h]
  unsigned __int64 v55; // [rsp+90h] [rbp-19h]
  _QWORD v56[4]; // [rsp+98h] [rbp-11h] BYREF
  char v57; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( !*((_QWORD *)this + 18) )
    return 4294967291LL;
  *(_OWORD *)S1 = 0;
  v54 = 0;
  v55 = 0;
  std::wstring::_Construct<1,unsigned short const *>(S1, a2[1], (unsigned __int64)*(unsigned __int16 *)a2 >> 1);
  v6 = (const wchar_t *)S1;
  if ( v55 > 7 )
    v6 = S1[0];
  v7 = 4;
  if ( v54 < 4 || wmemcmp(v6, L"\\??\\", 4u) )
  {
LABEL_104:
    std::wstring::~wstring(S1);
    return 4294967291LL;
  }
  pExceptionObject = 0;
  v50 = 0;
  if ( v54 < 4 )
LABEL_106:
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
  v8 = S1;
  if ( v55 > 7 )
    v8 = (wchar_t **)S1[0];
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, v8 + 1, v54 - 4);
  std::wstring::operator=(S1, &pExceptionObject);
  std::wstring::~wstring(&pExceptionObject);
  v9 = S1;
  if ( v55 > 7 )
    v9 = (wchar_t **)S1[0];
  if ( v54 < 3
    || !(unsigned int)_o_iswalpha(*(unsigned __int16 *)v9)
    || *((_WORD *)v9 + 1) != 58
    || *((_WORD *)v9 + 2) != 92 )
  {
    v10 = S1;
    if ( v55 > 7 )
      v10 = (wchar_t **)S1[0];
    if ( v54 < 6 || (v11 = &v10[v54 / 4], v12 = _std_search_2(v10, v11, L"Volume"), (wchar_t **)v12 == v11) )
    {
      v13 = -1;
    }
    else
    {
      v13 = (v12 - (__int64)v10) >> 1;
      if ( !v13 )
      {
        v14 = v54;
        if ( v55 - v54 < 4 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,unsigned short const *,unsigned __int64>(
            S1,
            (void *)L"\\\\?\\",
            4);
        }
        else
        {
          v54 += 4LL;
          v15 = S1;
          if ( v55 > 7 )
            v15 = (wchar_t **)S1[0];
          if ( L"" > (const wchar_t *)v15 && L"\\\\?\\" <= (const wchar_t *)v15 + v14 )
          {
            if ( v15 > (wchar_t **)L"\\\\?\\" )
              v7 = ((char *)v15 - (char *)L"\\\\?\\") >> 1;
            else
              v7 = 0;
          }
          memmove_0(v15 + 1, v15, 2 * v14 + 2);
          memcpy_0(v15, L"\\\\?\\", 2 * v7);
          memcpy_0((char *)v15 + 2 * v7, &asc_180036F40[v7 + 4], 8 - 2 * v7);
        }
LABEL_36:
        p9fs::GetDriveForVolume((unsigned __int64)v56, (const WCHAR *)S1);
        if ( !v57 )
        {
          v17 = -5;
LABEL_103:
          std::wstring::~wstring(S1);
          return v17;
        }
        v18 = v56;
        if ( v56[3] > 7u )
          v18 = (_QWORD *)v56[0];
        std::wstring::_Assign<unsigned short>(S1, v18, v56[2]);
        if ( v57 )
          std::wstring::~wstring(v56);
        goto LABEL_42;
      }
    }
    v16 = (const wchar_t *)S1;
    if ( v55 > 7 )
      v16 = S1[0];
    if ( v54 < 4 || wmemcmp(v16, L"\\\\?\\", 4u) || v13 != 4 )
      goto LABEL_104;
    goto LABEL_36;
  }
LABEL_42:
  v19 = S1;
  if ( v55 > 7 )
    v19 = (wchar_t **)S1[0];
  v48 = _o_towlower(*(unsigned __int16 *)v19);
  pExceptionObject = 0;
  v50 = 0;
  if ( v54 < 2 )
    goto LABEL_106;
  v20 = S1;
  if ( v55 > 7 )
    v20 = (wchar_t **)S1[0];
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, (char *)v20 + 4, v54 - 2);
  std::wstring::operator=(S1, &pExceptionObject);
  std::wstring::~wstring(&pExceptionObject);
  v21 = 2 * (v54 + *((_QWORD *)this + 18)) + 4;
  if ( v21 > 0xFFFF )
    goto LABEL_104;
  ProcessHeap = GetProcessHeap();
  v23 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v21);
  Buffer = v23;
  v51 = v23;
  if ( !v23 )
  {
    v17 = -12;
    goto LABEL_103;
  }
  *(_DWORD *)(&v52.MaximumLength + 1) = 0;
  v52.Buffer = v23;
  v52.Length = 0;
  v52.MaximumLength = v21;
  v25 = (_QWORD *)((char *)this + 128);
  if ( *((_QWORD *)this + 19) > 7u )
    v25 = (_QWORD *)*v25;
  v26 = 0x7FFF;
  v27 = (unsigned __int64)(unsigned __int16)v21 >> 1;
  v28 = 0;
  LODWORD(v29) = 0;
  if ( v27 )
  {
    while ( v26 )
    {
      v30 = *(_WORD *)v25;
      if ( *(_WORD *)v25 )
      {
        v25 = (_QWORD *)((char *)v25 + 2);
        *Buffer++ = v30;
        --v26;
        LODWORD(v29) = v29 + 1;
        if ( --v27 )
          continue;
      }
      if ( !v27 && v26 )
      {
        Buffer = v52.Buffer;
        LOWORD(v21) = v52.MaximumLength;
        goto LABEL_58;
      }
      break;
    }
    Buffer = v52.Buffer;
    LOWORD(v21) = v52.MaximumLength;
  }
  else
  {
LABEL_58:
    if ( *(_WORD *)v25 )
      v28 = 2147483653LL;
  }
  LOWORD(v29) = 2 * v29;
  v52.Length = v29;
  if ( (int)v28 < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(retaddr, (void *)0xA4, v29, (const char *)v28, v47);
  v31 = 3221225485LL;
  if ( (v21 & 1) != 0
    || (unsigned __int16)v29 > (unsigned __int16)v21
    || (_WORD)v21 == 0xFFFF
    || !Buffer && ((_WORD)v29 || (_WORD)v21) )
  {
    v37 = -1073741811;
  }
  else
  {
    v32 = (unsigned __int64)(unsigned __int16)v29 >> 1;
    v33 = 1;
    v34 = (WCHAR *)&v48;
    v35 = ((unsigned __int64)(unsigned __int16)v21 >> 1) - v32;
    v36 = &Buffer[v32];
    v37 = 0;
    LODWORD(v29) = 0;
    if ( v35 )
    {
      while ( v33 )
      {
        v38 = *v34;
        if ( *v34 )
        {
          ++v34;
          *v36++ = v38;
          --v33;
          LODWORD(v29) = v29 + 1;
          if ( --v35 )
            continue;
        }
        if ( !v35 && v33 )
        {
          Buffer = v52.Buffer;
          LOWORD(v21) = v52.MaximumLength;
          goto LABEL_74;
        }
        break;
      }
      Buffer = v52.Buffer;
      LOWORD(v21) = v52.MaximumLength;
    }
    else
    {
LABEL_74:
      if ( *v34 )
        v37 = -2147483643;
    }
    LOWORD(v29) = 2 * (v32 + v29);
    v52.Length = v29;
  }
  if ( v37 < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(retaddr, (void *)0xA5, v29, (const char *)(unsigned int)v37, v47);
  v39 = S1;
  if ( v55 > 7 )
    v39 = (wchar_t **)S1[0];
  v40 = (unsigned __int16)(2 * v54);
  if ( v40 != 2 * v54 )
  {
    pExceptionObject = 0;
    *(_QWORD *)&v50 = 0;
    gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  if ( (v29 & 1) == 0
    && (v21 & 1) == 0
    && (unsigned __int16)v29 <= (unsigned __int16)v21
    && (_WORD)v21 != 0xFFFF
    && (Buffer || !(_WORD)v29 && !(_WORD)v21)
    && (_WORD)v40 != 0xFFFF
    && (v39 || !(_WORD)v40) )
  {
    v41 = (unsigned __int64)(unsigned __int16)v29 >> 1;
    v29 = v40 >> 1;
    v42 = ((unsigned __int64)(unsigned __int16)v21 >> 1) - v41;
    v43 = &Buffer[v41];
    v31 = 0;
    v44 = 0;
    if ( v42 )
    {
      while ( v29 )
      {
        v45 = *(_WORD *)v39;
        v39 = (wchar_t **)((char *)v39 + 2);
        *v43++ = v45;
        --v29;
        ++v44;
        if ( !--v42 )
          goto LABEL_97;
      }
    }
    else
    {
LABEL_97:
      if ( v29 )
        v31 = 2147483653LL;
    }
    v52.Length = 2 * (v41 + v44);
  }
  if ( (int)v31 < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(retaddr, (void *)0xA7, v29, (const char *)v31, v47);
  LxUtilNtPathToLxPath(&v52, *((unsigned __int16 *)this + 72));
  *a3 = v52;
  std::wstring::~wstring(S1);
  return 0;
}

```

## disassembly

```asm
0x180027cf0  mov     [rsp-8+arg_8], rbx
0x180027cf5  push    rbp
0x180027cf6  push    rsi
0x180027cf7  push    rdi
0x180027cf8  push    r12
0x180027cfa  push    r13
0x180027cfc  push    r14
0x180027cfe  push    r15
0x180027d00  lea     rbp, [rsp-27h]
0x180027d05  sub     rsp, 0D0h
0x180027d0c  mov     rax, cs:__security_cookie
0x180027d13  xor     rax, rsp
0x180027d16  mov     [rbp+57h+var_40], rax
0x180027d1a  mov     r12, r8
0x180027d1d  mov     r13, rcx
0x180027d20  xor     r14d, r14d
0x180027d23  cmp     [rcx+90h], r14
0x180027d2a  jz      loc_1800282FF
0x180027d30  xorps   xmm0, xmm0
0x180027d33  movups  xmmword ptr [rbp+57h+S1], xmm0
0x180027d37  mov     [rbp+57h+var_78], r14
0x180027d3b  mov     [rbp+57h+var_70], r14
0x180027d3f  movzx   r8d, word ptr [rdx]
0x180027d43  shr     r8, 1
0x180027d46  mov     rdx, [rdx+8]
0x180027d4a  lea     rcx, [rbp+57h+S1]
0x180027d4e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027d53  nop
0x180027d54  lea     rcx, [rbp+57h+S1]
0x180027d58  cmp     [rbp+57h+var_70], 7
0x180027d5d  cmova   rcx, [rbp+57h+S1]; S1
0x180027d62  lea     edi, [r14+4]
0x180027d66  cmp     [rbp+57h+var_78], rdi
0x180027d6a  jb      loc_1800282F6
0x180027d70  mov     r8d, edi; N
0x180027d73  mov     rdx, cs:off_180035708; S2
0x180027d7a  call    wmemcmp
0x180027d7f  test    eax, eax
0x180027d81  jnz     loc_1800282F6
0x180027d87  xorps   xmm0, xmm0
0x180027d8a  movups  [rbp+57h+pExceptionObject], xmm0
0x180027d8e  xorps   xmm1, xmm1
0x180027d91  movdqu  [rbp+57h+var_B8], xmm1
0x180027d96  mov     rax, [rbp+57h+var_78]
0x180027d9a  cmp     rax, rdi
0x180027d9d  jb      loc_18002832B
0x180027da3  add     rax, 0FFFFFFFFFFFFFFFCh
0x180027da7  or      r15, 0FFFFFFFFFFFFFFFFh
0x180027dab  mov     r8, r15
0x180027dae  cmp     rax, r15
0x180027db1  cmovb   r8, rax
0x180027db5  lea     rdx, [rbp+57h+S1]
0x180027db9  cmp     [rbp+57h+var_70], 7
0x180027dbe  cmova   rdx, [rbp+57h+S1]
0x180027dc3  add     rdx, 8
0x180027dc7  lea     rcx, [rbp+57h+pExceptionObject]
0x180027dcb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027dd0  lea     rdx, [rbp+57h+pExceptionObject]
0x180027dd4  lea     rcx, [rbp+57h+S1]
0x180027dd8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180027ddd  lea     rcx, [rbp+57h+pExceptionObject]
0x180027de1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027de6  lea     rbx, [rbp+57h+S1]
0x180027dea  cmp     [rbp+57h+var_70], 7
0x180027def  cmova   rbx, [rbp+57h+S1]
0x180027df4  cmp     [rbp+57h+var_78], 3
0x180027df9  jb      short loc_180027E1A
0x180027dfb  movzx   ecx, word ptr [rbx]
0x180027dfe  call    cs:__imp__o_iswalpha
0x180027e04  test    eax, eax
0x180027e06  jz      short loc_180027E1A
0x180027e08  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180027e0d  jnz     short loc_180027E1A
0x180027e0f  cmp     word ptr [rbx+4], 5Ch ; '\'
0x180027e14  jz      loc_180027FA0
0x180027e1a  mov     rax, [rbp+57h+var_78]
0x180027e1e  lea     r14, [rbp+57h+S1]
0x180027e22  cmp     [rbp+57h+var_70], 7
0x180027e27  cmova   r14, [rbp+57h+S1]
0x180027e2c  mov     r9d, 6
0x180027e32  cmp     rax, r9
0x180027e35  jb      loc_180027F19
0x180027e3b  lea     rbx, [r14+rax*2]
0x180027e3f  lea     r8, aVolume; "Volume"
0x180027e46  mov     rdx, rbx
0x180027e49  mov     rcx, r14
0x180027e4c  call    __std_search_2
0x180027e51  mov     rsi, rax
0x180027e54  cmp     rax, rbx
0x180027e57  jz      loc_180027F19
0x180027e5d  sub     rsi, r14
0x180027e60  sar     rsi, 1
0x180027e63  jnz     loc_180027F1C
0x180027e69  mov     r8, [rbp+57h+var_78]
0x180027e6d  mov     rax, [rbp+57h+var_70]
0x180027e71  sub     rax, r8
0x180027e74  lea     r14, asc_180036F40; "\\\\?\\"
0x180027e7b  cmp     rax, rdi
0x180027e7e  jb      short loc_180027EFE
0x180027e80  lea     rax, [r8+4]
0x180027e84  mov     [rbp+57h+var_78], rax
0x180027e88  lea     rsi, [rbp+57h+S1]
0x180027e8c  cmp     [rbp+57h+var_70], 7
0x180027e91  cmova   rsi, [rbp+57h+S1]
0x180027e96  lea     rax, asc_180036F40+8; ""
0x180027e9d  cmp     rax, rsi
0x180027ea0  jbe     short loc_180027EBD
0x180027ea2  lea     rax, [rsi+r8*2]
0x180027ea6  cmp     r14, rax
0x180027ea9  ja      short loc_180027EBD
0x180027eab  cmp     rsi, r14
0x180027eae  ja      short loc_180027EB4
0x180027eb0  xor     edi, edi
0x180027eb2  jmp     short loc_180027EBD
0x180027eb4  mov     rdi, rsi
0x180027eb7  sub     rdi, r14
0x180027eba  sar     rdi, 1
0x180027ebd  lea     r8, ds:2[r8*2]; Size
0x180027ec5  lea     rcx, [rsi+8]; void *
0x180027ec9  mov     rdx, rsi; Src
0x180027ecc  call    memmove_0
0x180027ed1  lea     rbx, [rdi+rdi]
0x180027ed5  mov     r8, rbx; Size
0x180027ed8  mov     rdx, r14; Src
0x180027edb  mov     rcx, rsi; void *
0x180027ede  call    memcpy_0
0x180027ee3  mov     r8d, 8
0x180027ee9  sub     r8, rbx; Size
0x180027eec  lea     rdx, [r14+8]
0x180027ef0  add     rdx, rbx; Src
0x180027ef3  lea     rcx, [rbx+rsi]; void *
0x180027ef7  call    memcpy_0
0x180027efc  jmp     short loc_180027F14
0x180027efe  mov     [rsp+100h+var_D8], rdi; __int64
0x180027f03  mov     [rsp+100h+var_E0], r14; void *
0x180027f08  mov     rdx, rdi
0x180027f0b  lea     rcx, [rbp+57h+S1]; Src
0x180027f0f  call    ??$_Reallocate_grow_by@V_lambda_c5c7986eab02a925bb28d3483355880c_@@_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c5c7986eab02a925bb28d3483355880c_@@_KPEBG2@Z; std::wstring::_Reallocate_grow_by<_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,ushort const *,unsigned __int64)
0x180027f14  xor     r14d, r14d
0x180027f17  jmp     short loc_180027F57
0x180027f19  mov     rsi, r15
0x180027f1c  lea     rcx, [rbp+57h+S1]
0x180027f20  cmp     [rbp+57h+var_70], 7
0x180027f25  cmova   rcx, [rbp+57h+S1]; S1
0x180027f2a  cmp     [rbp+57h+var_78], rdi
0x180027f2e  jb      loc_1800282F6
0x180027f34  mov     r8, rdi; N
0x180027f37  lea     rdx, asc_180036F40; "\\\\?\\"
0x180027f3e  call    wmemcmp
0x180027f43  xor     r14d, r14d
0x180027f46  test    eax, eax
0x180027f48  jnz     loc_1800282F6
0x180027f4e  cmp     rsi, rdi
0x180027f51  jnz     loc_1800282F6
0x180027f57  lea     rdx, [rbp+57h+S1]
0x180027f5b  lea     rcx, [rbp+57h+var_68]
0x180027f5f  call    ?GetDriveForVolume@p9fs@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; p9fs::GetDriveForVolume(std::wstring const &)
0x180027f64  nop
0x180027f65  cmp     [rbp+57h+var_48], r14b
0x180027f69  jnz     short loc_180027F75
0x180027f6b  mov     ebx, 0FFFFFFFBh
0x180027f70  jmp     loc_1800282E9
0x180027f75  lea     rdx, [rbp+57h+var_68]
0x180027f79  cmp     [rbp+57h+var_50], 7
0x180027f7e  cmova   rdx, [rbp+57h+var_68]
0x180027f83  mov     r8, [rbp+57h+var_58]
0x180027f87  lea     rcx, [rbp+57h+S1]
0x180027f8b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180027f90  nop
0x180027f91  cmp     [rbp+57h+var_48], r14b
0x180027f95  jz      short loc_180027FA0
0x180027f97  lea     rcx, [rbp+57h+var_68]
0x180027f9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027fa0  lea     rcx, [rbp+57h+S1]
0x180027fa4  cmp     [rbp+57h+var_70], 7
0x180027fa9  cmova   rcx, [rbp+57h+S1]
0x180027fae  movzx   ecx, word ptr [rcx]
0x180027fb1  call    cs:__imp__o_towlower
0x180027fb7  mov     [rbp+57h+var_D0], ax
0x180027fbb  xorps   xmm0, xmm0
0x180027fbe  movups  [rbp+57h+pExceptionObject], xmm0
0x180027fc2  xorps   xmm1, xmm1
0x180027fc5  movdqu  [rbp+57h+var_B8], xmm1
0x180027fca  mov     rax, [rbp+57h+var_78]
0x180027fce  cmp     rax, 2
0x180027fd2  jb      loc_18002832B
0x180027fd8  add     rax, 0FFFFFFFFFFFFFFFEh
0x180027fdc  cmp     rax, r15
0x180027fdf  cmovb   r15, rax
0x180027fe3  lea     rdx, [rbp+57h+S1]
0x180027fe7  cmp     [rbp+57h+var_70], 7
0x180027fec  cmova   rdx, [rbp+57h+S1]
0x180027ff1  add     rdx, 4
0x180027ff5  mov     r8, r15
0x180027ff8  lea     rcx, [rbp+57h+pExceptionObject]
0x180027ffc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028001  lea     rdx, [rbp+57h+pExceptionObject]
0x180028005  lea     rcx, [rbp+57h+S1]
0x180028009  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002800e  lea     rcx, [rbp+57h+pExceptionObject]
0x180028012  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028017  mov     rax, [r13+90h]
0x18002801e  add     rax, [rbp+57h+var_78]
0x180028022  lea     rbx, ds:4[rax*2]
0x18002802a  cmp     rbx, 0FFFFh
0x180028031  ja      loc_1800282F6
0x180028037  call    cs:__imp_GetProcessHeap
0x18002803d  mov     rcx, rax; hHeap
0x180028040  mov     r8, rbx; dwBytes
0x180028043  mov     edx, 8; dwFlags
0x180028048  call    cs:__imp_HeapAlloc
0x18002804e  mov     rdx, rax
0x180028051  mov     [rbp+57h+var_A8], rax
0x180028055  test    rax, rax
0x180028058  jz      loc_1800282E4
0x18002805e  mov     dword ptr [rbp+57h+var_98+4], r14d
0x180028062  mov     qword ptr [rbp+57h+var_98+8], rax
0x180028066  mov     word ptr [rbp+57h+var_98], r14w
0x18002806b  mov     word ptr [rbp+57h+var_98+2], bx
0x18002806f  lea     rax, [r13+80h]
0x180028076  cmp     qword ptr [rax+18h], 7
0x18002807b  jbe     short loc_180028080
0x18002807d  mov     rax, [rax]
0x180028080  mov     r10d, 7FFFh
0x180028086  movzx   ecx, bx
0x180028089  mov     esi, 80000005h
0x18002808e  mov     r15d, 1
0x180028094  shr     rcx, 1
0x180028097  mov     r9d, r14d
0x18002809a  mov     r8, r14
0x18002809d  jz      short loc_1800280E3
0x18002809f  test    r10, r10
0x1800280a2  jz      loc_1800281BE
0x1800280a8  movzx   r11d, word ptr [rax]
0x1800280ac  test    r11w, r11w
0x1800280b0  jz      short loc_1800280C9
0x1800280b2  add     rax, 2
0x1800280b6  mov     [rdx], r11w
0x1800280ba  add     rdx, 2
0x1800280be  sub     r10, r15
0x1800280c1  add     r8, r15
0x1800280c4  sub     rcx, r15
0x1800280c7  jnz     short loc_18002809F
0x1800280c9  test    rcx, rcx
0x1800280cc  jnz     loc_1800281BE
0x1800280d2  test    r10, r10
0x1800280d5  jz      loc_1800281BE
0x1800280db  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x1800280df  movzx   ebx, word ptr [rbp+57h+var_98+2]
0x1800280e3  cmp     [rax], r14w
0x1800280e7  cmovnz  r9d, esi; char *
0x1800280eb  add     r8w, r8w; unsigned int
0x1800280ef  mov     word ptr [rbp+57h+var_98], r8w
0x1800280f4  mov     rcx, [rbp+5Fh]; this
0x1800280f8  test    r9d, r9d
0x1800280fb  js      loc_180028331
0x180028101  mov     edi, 0FFFEh
0x180028106  mov     r9d, 0C000000Dh
0x18002810c  test    r15b, bl
0x18002810f  jnz     loc_1800281D5
0x180028115  cmp     r8w, bx
0x180028119  ja      loc_1800281D5
0x18002811f  cmp     bx, di
0x180028122  ja      loc_1800281D5
0x180028128  test    rdx, rdx
0x18002812b  jnz     short loc_180028140
0x18002812d  test    r8w, r8w
0x180028131  jnz     loc_1800281D5
0x180028137  test    bx, bx
0x18002813a  jnz     loc_1800281D5
0x180028140  movzx   esi, r8w
0x180028144  shr     rsi, 1
0x180028147  mov     r10, r15
0x18002814a  lea     r11, [rbp+57h+var_D0]
0x18002814e  movzx   ecx, bx
0x180028151  shr     rcx, 1
0x180028154  sub     rcx, rsi
0x180028157  lea     rdi, [rdx+rsi*2]
0x18002815b  mov     eax, r14d
0x18002815e  mov     r8, r14
0x180028161  jz      short loc_180028199
0x180028163  test    r10, r10
0x180028166  jz      short loc_1800281CB
0x180028168  movzx   edx, word ptr [r11]
0x18002816c  test    dx, dx
0x18002816f  jz      short loc_180028187
0x180028171  add     r11, 2
0x180028175  mov     [rdi], dx
0x180028178  add     rdi, 2
0x18002817c  sub     r10, r15
0x18002817f  add     r8, r15
0x180028182  sub     rcx, r15
0x180028185  jnz     short loc_180028163
0x180028187  test    rcx, rcx
0x18002818a  jnz     short loc_1800281CB
0x18002818c  test    r10, r10
0x18002818f  jz      short loc_1800281CB
0x180028191  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x180028195  movzx   ebx, word ptr [rbp+57h+var_98+2]
0x180028199  cmp     [r11], r14w
  ... truncated ...
```
