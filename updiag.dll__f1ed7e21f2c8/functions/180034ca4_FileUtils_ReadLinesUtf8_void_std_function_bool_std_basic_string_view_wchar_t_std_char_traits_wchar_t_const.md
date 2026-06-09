# FileUtils::ReadLinesUtf8(void *,std::function<bool (std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)> const &)

- ea: `0x180034ca4`
- end: `0x1800352ea`
- name: `?ReadLinesUtf8@FileUtils@@SA_NPEAXAEBV?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@std@@@Z`
- size: `1606`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800349bc`

## callees

- `0x180016274`
- `0x18001639c`
- `0x180018eec`
- `0x180018f80`
- `0x180019080`
- `0x1800292f4`
- `0x180034ca4`
- `0x180046e60`
- `0x1800586bc`
- `0x180078da8`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180034d58`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800350c3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180034d58`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800350c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall FileUtils::ReadLinesUtf8(HANDLE hFile, __int64 a2)
{
  char v4; // di
  int v5; // esi
  char v6; // r12
  char v7; // bl
  __int64 v8; // r8
  DWORD i; // r14d
  char v10; // bl
  __int128 *p_Src; // rax
  __int128 *v12; // rax
  WCHAR *v13; // rax
  __int64 v14; // rcx
  char v15; // al
  __int128 *v16; // rax
  __int128 *v17; // rax
  WCHAR *v18; // rax
  __int64 v19; // rcx
  __int128 *v20; // rax
  __int128 *v21; // rax
  WCHAR *v22; // rax
  __int64 v23; // rcx
  __int128 *v24; // rax
  __int128 *v25; // rax
  WCHAR *v26; // rax
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  __int128 *v29; // rax
  const wchar_t *v30; // rax
  __int128 *v31; // rax
  WCHAR *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rcx
  const wchar_t *v35; // rax
  WCHAR *v36; // rax
  __int64 v37; // rcx
  const wchar_t *v39; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v40; // [rsp+38h] [rbp-C8h]
  _QWORD v41[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v42[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v43[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v44[4]; // [rsp+90h] [rbp-70h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR WideCharStr[8]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v47; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v48; // [rsp+D0h] [rbp-30h]
  __int128 Src; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v50; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v51; // [rsp+F0h] [rbp-10h]
  LPVOID lpBuffer[2]; // [rsp+F8h] [rbp-8h] BYREF
  char *v53; // [rsp+108h] [rbp+8h]

  v4 = 0;
  v5 = 0;
  NumberOfBytesRead = 0;
  *(_OWORD *)lpBuffer = 0;
  v53 = 0;
  lpBuffer[0] = std::_Allocate<16,std::_Default_allocate_traits>(0x2000u);
  v53 = (char *)lpBuffer[0] + 0x2000;
  memset(lpBuffer[0], 0, 0x2000u);
  lpBuffer[1] = (char *)lpBuffer[0] + 0x2000;
  v41[0] = 0;
  std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(v41);
  Src = 0;
  v50 = 0;
  v51 = 15;
  LOBYTE(Src) = 0;
  NumberOfBytesRead = 0;
  v6 = 0;
  v7 = 0;
  if ( !ReadFile(hFile, lpBuffer[0], 0x2000u, &NumberOfBytesRead, 0) )
    goto LABEL_80;
  while ( NumberOfBytesRead )
  {
    for ( i = 0; i < NumberOfBytesRead; ++i )
    {
      v10 = *((_BYTE *)lpBuffer[0] + i);
      if ( v6 )
      {
        v6 = 0;
        if ( v10 == 10 )
        {
          if ( v50 )
          {
            p_Src = &Src;
            if ( v51 > 0xF )
              p_Src = (__int128 *)Src;
            v41[0] = p_Src;
            v41[1] = v50;
            System::Convert::Utf8ToWideString(WideCharStr);
          }
          else
          {
            *(_OWORD *)WideCharStr = 0;
            v47 = 0;
            v48 = 0;
            std::wstring::_Construct<1,wchar_t const *>(WideCharStr, &psz, 0);
          }
          v5 |= 4u;
          v50 = 0;
          v12 = &Src;
          if ( v51 > 0xF )
            v12 = (__int128 *)Src;
          *(_BYTE *)v12 = 0;
          v7 = 1;
          v13 = WideCharStr;
          if ( v48 > 7 )
            v13 = *(WCHAR **)WideCharStr;
          v42[0] = v13;
          v42[1] = v47;
          v14 = *(_QWORD *)(a2 + 56);
          if ( !v14 )
            std::_Xbad_function_call();
          v15 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v14 + 16LL))(v14, v42);
          goto LABEL_17;
        }
        if ( v50 )
        {
          v16 = &Src;
          if ( v51 > 0xF )
            v16 = (__int128 *)Src;
          v42[2] = v16;
          v42[3] = v50;
          System::Convert::Utf8ToWideString(WideCharStr);
        }
        else
        {
          *(_OWORD *)WideCharStr = 0;
          v47 = 0;
          v48 = 0;
          std::wstring::_Construct<1,wchar_t const *>(WideCharStr, &psz, 0);
        }
        v5 |= 8u;
        v50 = 0;
        v17 = &Src;
        if ( v51 > 0xF )
          v17 = (__int128 *)Src;
        *(_BYTE *)v17 = 0;
        v18 = WideCharStr;
        if ( v48 > 7 )
          v18 = *(WCHAR **)WideCharStr;
        v43[0] = v18;
        v43[1] = v47;
        v19 = *(_QWORD *)(a2 + 56);
        if ( !v19 )
          std::_Xbad_function_call();
        if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v19 + 16LL))(v19, v43) )
        {
LABEL_69:
          std::wstring::~wstring((__int64)WideCharStr);
          goto LABEL_91;
        }
        std::wstring::~wstring((__int64)WideCharStr);
      }
      if ( v10 == 10 )
      {
        if ( v50 )
        {
          v20 = &Src;
          if ( v51 > 0xF )
            v20 = (__int128 *)Src;
          v43[2] = v20;
          v43[3] = v50;
          System::Convert::Utf8ToWideString(WideCharStr);
        }
        else
        {
          *(_OWORD *)WideCharStr = 0;
          v47 = 0;
          v48 = 0;
          std::wstring::_Construct<1,wchar_t const *>(WideCharStr, &psz, 0);
        }
        v5 |= 1u;
        v50 = 0;
        v21 = &Src;
        if ( v51 > 0xF )
          v21 = (__int128 *)Src;
        *(_BYTE *)v21 = 0;
        v7 = 1;
        v22 = WideCharStr;
        if ( v48 > 7 )
          v22 = *(WCHAR **)WideCharStr;
        v44[0] = v22;
        v44[1] = v47;
        v23 = *(_QWORD *)(a2 + 56);
        if ( !v23 )
          std::_Xbad_function_call();
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v23 + 16LL))(v23, v44);
      }
      else
      {
        if ( v10 != 13 )
        {
          v28 = v50;
          if ( v50 >= v51 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(
              &Src,
              (__int64)&psz,
              v8,
              v10);
          }
          else
          {
            ++v50;
            v29 = &Src;
            if ( v51 > 0xF )
              v29 = (__int128 *)Src;
            *((_BYTE *)v29 + v28) = v10;
            *((_BYTE *)v29 + v28 + 1) = 0;
          }
          v7 = 0;
          continue;
        }
        v7 = 0;
        if ( i + 1 >= NumberOfBytesRead )
        {
          v6 = 1;
          continue;
        }
        if ( *((_BYTE *)lpBuffer[0] + i + 1) == 10 )
          continue;
        if ( v50 )
        {
          v24 = &Src;
          if ( v51 > 0xF )
            v24 = (__int128 *)Src;
          v44[2] = v24;
          v44[3] = v50;
          System::Convert::Utf8ToWideString(WideCharStr);
        }
        else
        {
          *(_OWORD *)WideCharStr = 0;
          v47 = 0;
          v48 = 0;
          std::wstring::_Construct<1,wchar_t const *>(WideCharStr, &psz, 0);
        }
        v5 |= 0x20u;
        v50 = 0;
        v25 = &Src;
        if ( v51 > 0xF )
          v25 = (__int128 *)Src;
        *(_BYTE *)v25 = 0;
        v7 = 1;
        v26 = WideCharStr;
        if ( v48 > 7 )
          v26 = *(WCHAR **)WideCharStr;
        v39 = v26;
        v40 = v47;
        v27 = *(_QWORD *)(a2 + 56);
        if ( !v27 )
          std::_Xbad_function_call();
        v15 = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v27 + 16LL))(v27, &v39);
      }
LABEL_17:
      if ( !v15 )
        goto LABEL_69;
      std::wstring::~wstring((__int64)WideCharStr);
    }
    if ( ReadFile(hFile, lpBuffer[0], 0x2000u, &NumberOfBytesRead, 0) )
      continue;
    break;
  }
  if ( v6 )
  {
    if ( v50 )
    {
      v30 = (const wchar_t *)&Src;
      if ( v51 > 0xF )
        v30 = (const wchar_t *)Src;
      v39 = v30;
      v40 = v50;
      System::Convert::Utf8ToWideString(WideCharStr);
    }
    else
    {
      *(_OWORD *)WideCharStr = 0;
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(WideCharStr, &psz, 0);
    }
    v50 = 0;
    v31 = &Src;
    if ( v51 > 0xF )
      v31 = (__int128 *)Src;
    *(_BYTE *)v31 = 0;
    v32 = WideCharStr;
    if ( v48 > 7 )
      v32 = *(WCHAR **)WideCharStr;
    v39 = v32;
    v40 = v47;
    v33 = *(_QWORD *)(a2 + 56);
    if ( !v33 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v33 + 16LL))(v33, &v39);
    v39 = &psz;
    v40 = 0;
    v34 = *(_QWORD *)(a2 + 56);
    if ( !v34 )
      std::_Xbad_function_call();
    goto LABEL_86;
  }
LABEL_80:
  if ( v50 )
  {
    v35 = (const wchar_t *)&Src;
    if ( v51 > 0xF )
      v35 = (const wchar_t *)Src;
    v39 = v35;
    v40 = v50;
    System::Convert::Utf8ToWideString(WideCharStr);
    v36 = WideCharStr;
    if ( v48 > 7 )
      v36 = *(WCHAR **)WideCharStr;
    v39 = v36;
    v40 = v47;
    v34 = *(_QWORD *)(a2 + 56);
    if ( !v34 )
      std::_Xbad_function_call();
LABEL_86:
    (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v34 + 16LL))(v34, &v39);
    std::wstring::~wstring((__int64)WideCharStr);
  }
  else if ( v7 )
  {
    v39 = &psz;
    v40 = 0;
    v37 = *(_QWORD *)(a2 + 56);
    if ( !v37 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v37 + 16LL))(v37, &v39);
  }
  v4 = 1;
LABEL_91:
  std::string::~string((__int64)&Src);
  std::vector<char>::~vector<char>(lpBuffer);
  return v4;
}

```

## disassembly

```asm
0x180034ca4  mov     [rsp-8+arg_10], rbx
0x180034ca9  push    rbp
0x180034caa  push    rsi
0x180034cab  push    rdi
0x180034cac  push    r12
0x180034cae  push    r13
0x180034cb0  push    r14
0x180034cb2  push    r15
0x180034cb4  lea     rbp, [rsp-20h]
0x180034cb9  sub     rsp, 120h
0x180034cc0  mov     rax, cs:__security_cookie
0x180034cc7  xor     rax, rsp
0x180034cca  mov     [rbp+50h+var_40], rax
0x180034cce  mov     r15, rdx
0x180034cd1  mov     r13, rcx
0x180034cd4  xor     edi, edi
0x180034cd6  mov     esi, edi
0x180034cd8  mov     [rbp+50h+NumberOfBytesRead], edi
0x180034cdb  xorps   xmm1, xmm1
0x180034cde  movdqu  xmmword ptr [rbp+50h+lpBuffer], xmm1
0x180034ce3  mov     [rbp+50h+var_48], rdi
0x180034ce7  mov     r14d, 2000h
0x180034ced  mov     ecx, r14d
0x180034cf0  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180034cf5  mov     [rbp+50h+lpBuffer], rax
0x180034cf9  lea     rbx, [rax+2000h]
0x180034d00  mov     [rbp+50h+var_48], rbx
0x180034d04  mov     r8d, r14d; Size
0x180034d07  xor     edx, edx; Val
0x180034d09  mov     rcx, rax; void *
0x180034d0c  call    memset
0x180034d11  mov     [rbp+50h+lpBuffer+8], rbx
0x180034d15  mov     [rsp+150h+var_110], rdi
0x180034d1a  lea     rcx, [rsp+150h+var_110]
0x180034d1f  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180034d24  nop
0x180034d25  xorps   xmm0, xmm0
0x180034d28  movups  [rbp+50h+Src], xmm0
0x180034d2c  mov     [rbp+50h+var_68], rdi
0x180034d30  mov     [rbp+50h+var_60], 0Fh
0x180034d38  mov     byte ptr [rbp+50h+Src], dil
0x180034d3c  mov     [rbp+50h+NumberOfBytesRead], edi
0x180034d3f  mov     r12b, dil
0x180034d42  mov     bl, dil
0x180034d45  mov     [rsp+150h+lpOverlapped], rdi; lpOverlapped
0x180034d4a  lea     r9, [rbp+50h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180034d4e  mov     r8d, r14d; nNumberOfBytesToRead
0x180034d51  mov     rdx, [rbp+50h+lpBuffer]; lpBuffer
0x180034d55  mov     rcx, r13; hFile
0x180034d58  call    cs:__imp_ReadFile
0x180034d5e  lea     rdx, psz
0x180034d65  test    eax, eax
0x180034d67  jz      loc_1800351B5
0x180034d6d  cmp     [rbp+50h+NumberOfBytesRead], edi
0x180034d70  jbe     loc_1800350D8
0x180034d76  mov     r14d, edi
0x180034d79  mov     ecx, r14d
0x180034d7c  mov     rax, [rbp+50h+lpBuffer]
0x180034d80  mov     bl, [rcx+rax]
0x180034d83  test    r12b, r12b
0x180034d86  jz      loc_180034EF2
0x180034d8c  mov     r12b, dil
0x180034d8f  mov     r8, [rbp+50h+var_68]
0x180034d93  lea     rcx, [rbp+50h+WideCharStr]; lpWideCharStr
0x180034d97  cmp     bl, 0Ah
0x180034d9a  jnz     loc_180034E49
0x180034da0  test    r8, r8
0x180034da3  jnz     short loc_180034DBB
0x180034da5  xorps   xmm0, xmm0
0x180034da8  movups  xmmword ptr [rbp+50h+WideCharStr], xmm0
0x180034dac  mov     [rbp+50h+var_88], rdi
0x180034db0  mov     [rbp+50h+var_80], rdi
0x180034db4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180034db9  jmp     short loc_180034DDE
0x180034dbb  lea     rax, [rbp+50h+Src]
0x180034dbf  cmp     [rbp+50h+var_60], 0Fh
0x180034dc4  cmova   rax, qword ptr [rbp+50h+Src]
0x180034dc9  mov     [rsp+150h+var_110], rax
0x180034dce  mov     [rsp+150h+var_108], r8
0x180034dd3  lea     rdx, [rsp+150h+var_110]
0x180034dd8  call    ?Utf8ToWideString@Convert@System@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@4@H@Z; System::Convert::Utf8ToWideString(std::string_view,int)
0x180034ddd  nop
0x180034dde  or      esi, 4
0x180034de1  mov     [rbp+50h+var_68], rdi
0x180034de5  lea     rax, [rbp+50h+Src]
0x180034de9  cmp     [rbp+50h+var_60], 0Fh
0x180034dee  cmova   rax, qword ptr [rbp+50h+Src]
0x180034df3  mov     [rax], dil
0x180034df6  mov     bl, 1
0x180034df8  lea     rax, [rbp+50h+WideCharStr]
0x180034dfc  cmp     [rbp+50h+var_80], 7
0x180034e01  cmova   rax, qword ptr [rbp+50h+WideCharStr]
0x180034e06  mov     [rsp+150h+var_100], rax
0x180034e0b  mov     rax, [rbp+50h+var_88]
0x180034e0f  mov     [rsp+150h+var_F8], rax
0x180034e14  mov     rcx, [r15+38h]
0x180034e18  test    rcx, rcx
0x180034e1b  jz      loc_1800352C0
0x180034e21  mov     rax, [rcx]
0x180034e24  lea     rdx, [rsp+150h+var_100]
0x180034e29  mov     rax, [rax+10h]
0x180034e2d  call    _guard_dispatch_icall
0x180034e32  nop
0x180034e33  test    al, al
0x180034e35  lea     rcx, [rbp+50h+WideCharStr]
0x180034e39  jz      loc_180035104
0x180034e3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034e44  jmp     loc_180035099
0x180034e49  test    r8, r8
0x180034e4c  jnz     short loc_180034E64
0x180034e4e  xorps   xmm0, xmm0
0x180034e51  movups  xmmword ptr [rbp+50h+WideCharStr], xmm0
0x180034e55  mov     [rbp+50h+var_88], rdi
0x180034e59  mov     [rbp+50h+var_80], rdi
0x180034e5d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180034e62  jmp     short loc_180034E87
0x180034e64  lea     rax, [rbp+50h+Src]
0x180034e68  cmp     [rbp+50h+var_60], 0Fh
0x180034e6d  cmova   rax, qword ptr [rbp+50h+Src]
0x180034e72  mov     [rsp+150h+var_F0], rax
0x180034e77  mov     [rsp+150h+var_E8], r8
0x180034e7c  lea     rdx, [rsp+150h+var_F0]
0x180034e81  call    ?Utf8ToWideString@Convert@System@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@4@H@Z; System::Convert::Utf8ToWideString(std::string_view,int)
0x180034e86  nop
0x180034e87  or      esi, 8
0x180034e8a  mov     [rbp+50h+var_68], rdi
0x180034e8e  lea     rax, [rbp+50h+Src]
0x180034e92  cmp     [rbp+50h+var_60], 0Fh
0x180034e97  cmova   rax, qword ptr [rbp+50h+Src]
0x180034e9c  mov     [rax], dil
0x180034e9f  lea     rax, [rbp+50h+WideCharStr]
0x180034ea3  cmp     [rbp+50h+var_80], 7
0x180034ea8  cmova   rax, qword ptr [rbp+50h+WideCharStr]
0x180034ead  mov     [rsp+150h+var_E0], rax
0x180034eb2  mov     rax, [rbp+50h+var_88]
0x180034eb6  mov     [rsp+150h+var_D8], rax
0x180034ebb  mov     rcx, [r15+38h]
0x180034ebf  test    rcx, rcx
0x180034ec2  jz      loc_1800352C6
0x180034ec8  mov     rax, [rcx]
0x180034ecb  lea     rdx, [rsp+150h+var_E0]
0x180034ed0  mov     rax, [rax+10h]
0x180034ed4  call    _guard_dispatch_icall
0x180034ed9  nop
0x180034eda  lea     rcx, [rbp+50h+WideCharStr]
0x180034ede  test    al, al
0x180034ee0  jz      loc_180035104
0x180034ee6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034eeb  lea     rdx, psz
0x180034ef2  cmp     bl, 0Ah
0x180034ef5  jnz     loc_180034F95
0x180034efb  mov     r8, [rbp+50h+var_68]
0x180034eff  lea     rcx, [rbp+50h+WideCharStr]; lpWideCharStr
0x180034f03  test    r8, r8
0x180034f06  jnz     short loc_180034F1E
0x180034f08  xorps   xmm0, xmm0
0x180034f0b  movups  xmmword ptr [rbp+50h+WideCharStr], xmm0
0x180034f0f  mov     [rbp+50h+var_88], rdi
0x180034f13  mov     [rbp+50h+var_80], rdi
0x180034f17  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180034f1c  jmp     short loc_180034F3E
0x180034f1e  lea     rax, [rbp+50h+Src]
0x180034f22  cmp     [rbp+50h+var_60], 0Fh
0x180034f27  cmova   rax, qword ptr [rbp+50h+Src]
0x180034f2c  mov     [rbp+50h+var_D0], rax
0x180034f30  mov     [rbp+50h+var_C8], r8
0x180034f34  lea     rdx, [rbp+50h+var_D0]
0x180034f38  call    ?Utf8ToWideString@Convert@System@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@4@H@Z; System::Convert::Utf8ToWideString(std::string_view,int)
0x180034f3d  nop
0x180034f3e  or      esi, 1
0x180034f41  mov     [rbp+50h+var_68], rdi
0x180034f45  lea     rax, [rbp+50h+Src]
0x180034f49  cmp     [rbp+50h+var_60], 0Fh
0x180034f4e  cmova   rax, qword ptr [rbp+50h+Src]
0x180034f53  mov     [rax], dil
0x180034f56  mov     bl, 1
0x180034f58  lea     rax, [rbp+50h+WideCharStr]
0x180034f5c  cmp     [rbp+50h+var_80], 7
0x180034f61  cmova   rax, qword ptr [rbp+50h+WideCharStr]
0x180034f66  mov     [rbp+50h+var_C0], rax
0x180034f6a  mov     rax, [rbp+50h+var_88]
0x180034f6e  mov     [rbp+50h+var_B8], rax
0x180034f72  mov     rcx, [r15+38h]
0x180034f76  test    rcx, rcx
0x180034f79  jz      loc_1800352CC
0x180034f7f  mov     rax, [rcx]
0x180034f82  lea     rdx, [rbp+50h+var_C0]
0x180034f86  mov     rax, [rax+10h]
0x180034f8a  call    _guard_dispatch_icall
0x180034f8f  nop
0x180034f90  jmp     loc_180034E33
0x180034f95  cmp     bl, 0Dh
0x180034f98  jnz     loc_180035060
0x180034f9e  lea     eax, [r14+1]
0x180034fa2  mov     bl, dil
0x180034fa5  cmp     eax, [rbp+50h+NumberOfBytesRead]
0x180034fa8  jnb     loc_18003505B
0x180034fae  mov     ecx, eax
0x180034fb0  mov     rax, [rbp+50h+lpBuffer]
0x180034fb4  cmp     byte ptr [rcx+rax], 0Ah
0x180034fb8  jz      loc_180035099
0x180034fbe  mov     r8, [rbp+50h+var_68]
0x180034fc2  lea     rcx, [rbp+50h+WideCharStr]; lpWideCharStr
0x180034fc6  test    r8, r8
0x180034fc9  jnz     short loc_180034FE1
0x180034fcb  xorps   xmm0, xmm0
0x180034fce  movups  xmmword ptr [rbp+50h+WideCharStr], xmm0
0x180034fd2  mov     [rbp+50h+var_88], rdi
0x180034fd6  mov     [rbp+50h+var_80], rdi
0x180034fda  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180034fdf  jmp     short loc_180035001
0x180034fe1  lea     rax, [rbp+50h+Src]
0x180034fe5  cmp     [rbp+50h+var_60], 0Fh
0x180034fea  cmova   rax, qword ptr [rbp+50h+Src]
0x180034fef  mov     [rbp+50h+var_B0], rax
0x180034ff3  mov     [rbp+50h+var_A8], r8
0x180034ff7  lea     rdx, [rbp+50h+var_B0]
0x180034ffb  call    ?Utf8ToWideString@Convert@System@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@4@H@Z; System::Convert::Utf8ToWideString(std::string_view,int)
0x180035000  nop
0x180035001  or      esi, 20h
0x180035004  mov     [rbp+50h+var_68], rdi
0x180035008  lea     rax, [rbp+50h+Src]
0x18003500c  cmp     [rbp+50h+var_60], 0Fh
0x180035011  cmova   rax, qword ptr [rbp+50h+Src]
0x180035016  mov     [rax], dil
0x180035019  mov     bl, 1
0x18003501b  lea     rax, [rbp+50h+WideCharStr]
0x18003501f  cmp     [rbp+50h+var_80], 7
0x180035024  cmova   rax, qword ptr [rbp+50h+WideCharStr]
0x180035029  mov     [rsp+150h+var_120], rax
0x18003502e  mov     rax, [rbp+50h+var_88]
0x180035032  mov     [rsp+150h+var_118], rax
0x180035037  mov     rcx, [r15+38h]
0x18003503b  test    rcx, rcx
0x18003503e  jz      loc_1800352D2
0x180035044  mov     rax, [rcx]
0x180035047  lea     rdx, [rsp+150h+var_120]
0x18003504c  mov     rax, [rax+10h]
0x180035050  call    _guard_dispatch_icall
0x180035055  nop
0x180035056  jmp     loc_180034E33
0x18003505b  mov     r12b, 1
0x18003505e  jmp     short loc_180035099
0x180035060  mov     rcx, [rbp+50h+var_68]
0x180035064  cmp     rcx, [rbp+50h+var_60]
0x180035068  jnb     short loc_18003508A
0x18003506a  lea     rax, [rcx+1]
0x18003506e  mov     [rbp+50h+var_68], rax
0x180035072  lea     rax, [rbp+50h+Src]
0x180035076  cmp     [rbp+50h+var_60], 0Fh
0x18003507b  cmova   rax, qword ptr [rbp+50h+Src]
0x180035080  mov     [rax+rcx], bl
0x180035083  mov     [rax+rcx+1], dil
0x180035088  jmp     short loc_180035096
0x18003508a  mov     r9b, bl
0x18003508d  lea     rcx, [rbp+50h+Src]; Src
0x180035091  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180035096  mov     bl, dil
0x180035099  inc     r14d
0x18003509c  cmp     r14d, [rbp+50h+NumberOfBytesRead]
0x1800350a0  lea     rdx, psz
0x1800350a7  jb      loc_180034D79
0x1800350ad  mov     [rsp+150h+lpOverlapped], rdi; lpOverlapped
0x1800350b2  lea     r9, [rbp+50h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800350b6  mov     r8d, 2000h; nNumberOfBytesToRead
0x1800350bc  mov     rdx, [rbp+50h+lpBuffer]; lpBuffer
0x1800350c0  mov     rcx, r13; hFile
0x1800350c3  call    cs:__imp_ReadFile
0x1800350c9  lea     rdx, psz
0x1800350d0  test    eax, eax
0x1800350d2  jnz     loc_180034D6D
0x1800350d8  test    r12b, r12b
0x1800350db  jz      loc_1800351B5
0x1800350e1  mov     r8, [rbp+50h+var_68]
0x1800350e5  lea     rcx, [rbp+50h+WideCharStr]; lpWideCharStr
0x1800350e9  test    r8, r8
0x1800350ec  jnz     short loc_18003510E
0x1800350ee  xorps   xmm0, xmm0
0x1800350f1  movups  xmmword ptr [rbp+50h+WideCharStr], xmm0
0x1800350f5  mov     [rbp+50h+var_88], rdi
0x1800350f9  mov     [rbp+50h+var_80], rdi
0x1800350fd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180035102  jmp     short loc_180035131
0x180035104  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035109  jmp     loc_18003527D
0x18003510e  lea     rax, [rbp+50h+Src]
0x180035112  cmp     [rbp+50h+var_60], 0Fh
0x180035117  cmova   rax, qword ptr [rbp+50h+Src]
0x18003511c  mov     [rsp+150h+var_120], rax
0x180035121  mov     [rsp+150h+var_118], r8
0x180035126  lea     rdx, [rsp+150h+var_120]
0x18003512b  call    ?Utf8ToWideString@Convert@System@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@4@H@Z; System::Convert::Utf8ToWideString(std::string_view,int)
0x180035130  nop
0x180035131  mov     [rbp+50h+var_68], rdi
0x180035135  lea     rax, [rbp+50h+Src]
0x180035139  cmp     [rbp+50h+var_60], 0Fh
0x18003513e  cmova   rax, qword ptr [rbp+50h+Src]
0x180035143  mov     [rax], dil
0x180035146  lea     rax, [rbp+50h+WideCharStr]
0x18003514a  cmp     [rbp+50h+var_80], 7
  ... truncated ...
```
