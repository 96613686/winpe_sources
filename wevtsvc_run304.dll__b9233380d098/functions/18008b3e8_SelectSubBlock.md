# SelectSubBlock

- ea: `0x18008b3e8`
- end: `0x18008b59c`
- name: `SelectSubBlock`
- size: `436`
- prototype: `__int64 __fastcall(LPCVOID pBlock)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002df68`

## callees

- `0x180014bd0`
- `0x180017b60`
- `0x18002d204`
- `0x18002de9c`
- `0x18003d2f8`
- `0x18008b3e8`
- `0x180091dc8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18008b405`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18008b405`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b42a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b4ab`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b508`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b540`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b56a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b42a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b4ab`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b508`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b540`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008b56a`

## pseudocode

```c
char __fastcall SelectSubBlock(LPCVOID pBlock, _QWORD *a2)
{
  LANGID ThreadUILanguage; // ax
  unsigned int v5; // esi
  LANGID v6; // r13
  unsigned __int16 *v7; // r12
  char v8; // r15
  unsigned int v9; // edi
  __int64 v10; // rax
  const wchar_t *v12; // rdx
  LPVOID lpBuffer; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR lpSubBlock[5]; // [rsp+28h] [rbp-28h] BYREF
  unsigned int puLen; // [rsp+A0h] [rbp+50h] BYREF
  LPVOID v16; // [rsp+A8h] [rbp+58h] BYREF

  ThreadUILanguage = GetThreadUILanguage();
  v5 = 0;
  lpBuffer = 0;
  puLen = 0;
  v6 = ThreadUILanguage;
  if ( VerQueryValueW(pBlock, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
  {
    v16 = 0;
    if ( puLen >= 4 )
    {
      v7 = (unsigned __int16 *)lpBuffer;
      v8 = 1;
      v9 = puLen >> 2;
      if ( puLen >> 2 )
      {
        do
        {
          if ( *((_WORD *)lpBuffer + 2 * v5) == v6 )
            break;
          ++v5;
        }
        while ( v5 < v9 );
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubBlock);
      v10 = v5 < v9 ? v5 : 0;
      if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  lpSubBlock,
                  L"\\StringFileInfo\\%04x%04x\\FileVersion",
                  v7[2 * v10],
                  v7[2 * v10 + 1]) < 0 )
      {
        v8 = 0;
LABEL_11:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubBlock);
        return v8;
      }
      if ( VerQueryValueW(pBlock, lpSubBlock[0], &v16, &puLen) && puLen )
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, lpSubBlock);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
          a2,
          ((__int64)(a2[1] - *a2) >> 1) - 11);
        goto LABEL_11;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubBlock);
    }
    if ( VerQueryValueW(pBlock, L"\\StringFileInfo\\040904B0\\FileVersion", &v16, &puLen) && puLen )
    {
      v12 = L"\\StringFileInfo\\040904B0\\";
      return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, v12);
    }
    if ( VerQueryValueW(pBlock, L"\\StringFileInfo\\040904E4\\FileVersion", &v16, &puLen) && puLen )
    {
      v12 = L"\\StringFileInfo\\040904E4\\";
      return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, v12);
    }
    if ( VerQueryValueW(pBlock, L"\\StringFileInfo\\04090000\\FileVersion", &v16, &puLen) && puLen )
    {
      v12 = L"\\StringFileInfo\\04090000\\";
      return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18008b3e8  mov     [rsp-38h+arg_0], rbx
0x18008b3ed  push    rbp
0x18008b3ee  push    rsi
0x18008b3ef  push    rdi
0x18008b3f0  push    r12
0x18008b3f2  push    r13
0x18008b3f4  push    r14
0x18008b3f6  push    r15
0x18008b3f8  mov     rbp, rsp
0x18008b3fb  sub     rsp, 50h
0x18008b3ff  mov     rbx, rdx
0x18008b402  mov     r14, rcx
0x18008b405  call    cs:__imp_GetThreadUILanguage
0x18008b40b  xor     esi, esi
0x18008b40d  lea     r9, [rbp+puLen]; puLen
0x18008b411  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18008b415  mov     [rbp+lpBuffer], rsi
0x18008b419  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x18008b420  mov     [rbp+puLen], esi
0x18008b423  mov     rcx, r14; pBlock
0x18008b426  movzx   r13d, ax
0x18008b42a  call    cs:__imp_VerQueryValueW
0x18008b430  test    eax, eax
0x18008b432  jz      loc_18008B582
0x18008b438  mov     edi, [rbp+puLen]
0x18008b43b  mov     [rbp+arg_18], rsi
0x18008b43f  cmp     edi, 4
0x18008b442  jb      loc_18008B4F6
0x18008b448  mov     r12, [rbp+lpBuffer]
0x18008b44c  lea     r15d, [rsi+1]
0x18008b450  shr     edi, 2
0x18008b453  test    edi, edi
0x18008b455  jz      short loc_18008B467
0x18008b457  mov     eax, esi
0x18008b459  cmp     [r12+rax*4], r13w
0x18008b45e  jz      short loc_18008B467
0x18008b460  add     esi, r15d
0x18008b463  cmp     esi, edi
0x18008b465  jb      short loc_18008B457
0x18008b467  lea     rcx, [rbp+lpSubBlock]; void *
0x18008b46b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b470  cmp     esi, edi
0x18008b472  lea     rdx, aStringfileinfo_0; "\\StringFileInfo\\%04x%04x\\FileVersion"
0x18008b479  lea     rcx, [rbp+lpSubBlock]
0x18008b47d  sbb     eax, eax
0x18008b47f  and     eax, esi
0x18008b481  movzx   r9d, word ptr [r12+rax*4+2]
0x18008b487  movzx   r8d, word ptr [r12+rax*4]
0x18008b48c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008b491  xor     esi, esi
0x18008b493  test    eax, eax
0x18008b495  jns     short loc_18008B49C
0x18008b497  mov     r15b, sil
0x18008b49a  jmp     short loc_18008B4DC
0x18008b49c  mov     rdx, [rbp+lpSubBlock]; lpSubBlock
0x18008b4a0  lea     r9, [rbp+puLen]; puLen
0x18008b4a4  lea     r8, [rbp+arg_18]; lplpBuffer
0x18008b4a8  mov     rcx, r14; pBlock
0x18008b4ab  call    cs:__imp_VerQueryValueW
0x18008b4b1  test    eax, eax
0x18008b4b3  jz      short loc_18008B4ED
0x18008b4b5  cmp     [rbp+puLen], esi
0x18008b4b8  jbe     short loc_18008B4ED
0x18008b4ba  lea     rdx, [rbp+lpSubBlock]
0x18008b4be  mov     rcx, rbx
0x18008b4c1  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18008b4c6  mov     rdx, [rbx+8]
0x18008b4ca  mov     rcx, rbx
0x18008b4cd  sub     rdx, [rbx]
0x18008b4d0  sar     rdx, 1
0x18008b4d3  sub     rdx, 0Bh
0x18008b4d7  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18008b4dc  lea     rcx, [rbp+lpSubBlock]; void *
0x18008b4e0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008b4e5  mov     al, r15b
0x18008b4e8  jmp     loc_18008B584
0x18008b4ed  lea     rcx, [rbp+lpSubBlock]; void *
0x18008b4f1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008b4f6  lea     r9, [rbp+puLen]; puLen
0x18008b4fa  mov     rcx, r14; pBlock
0x18008b4fd  lea     r8, [rbp+arg_18]; lplpBuffer
0x18008b501  lea     rdx, aStringfileinfo_5; "\\StringFileInfo\\040904B0\\FileVersion"
0x18008b508  call    cs:__imp_VerQueryValueW
0x18008b50e  test    eax, eax
0x18008b510  jz      short loc_18008B52E
0x18008b512  cmp     [rbp+puLen], esi
0x18008b515  jbe     short loc_18008B52E
0x18008b517  lea     rdx, aStringfileinfo_3; "\\StringFileInfo\\040904B0\\"
0x18008b51e  mov     r8d, 19h
0x18008b524  mov     rcx, rbx
0x18008b527  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18008b52c  jmp     short loc_18008B584
0x18008b52e  lea     r9, [rbp+puLen]; puLen
0x18008b532  mov     rcx, r14; pBlock
0x18008b535  lea     r8, [rbp+arg_18]; lplpBuffer
0x18008b539  lea     rdx, aStringfileinfo_4; "\\StringFileInfo\\040904E4\\FileVersion"
0x18008b540  call    cs:__imp_VerQueryValueW
0x18008b546  test    eax, eax
0x18008b548  jz      short loc_18008B558
0x18008b54a  cmp     [rbp+puLen], esi
0x18008b54d  jbe     short loc_18008B558
0x18008b54f  lea     rdx, aStringfileinfo_2; "\\StringFileInfo\\040904E4\\"
0x18008b556  jmp     short loc_18008B51E
0x18008b558  lea     r9, [rbp+puLen]; puLen
0x18008b55c  mov     rcx, r14; pBlock
0x18008b55f  lea     r8, [rbp+arg_18]; lplpBuffer
0x18008b563  lea     rdx, aStringfileinfo_6; "\\StringFileInfo\\04090000\\FileVersion"
0x18008b56a  call    cs:__imp_VerQueryValueW
0x18008b570  test    eax, eax
0x18008b572  jz      short loc_18008B582
0x18008b574  cmp     [rbp+puLen], esi
0x18008b577  jbe     short loc_18008B582
0x18008b579  lea     rdx, aStringfileinfo_1; "\\StringFileInfo\\04090000\\"
0x18008b580  jmp     short loc_18008B51E
0x18008b582  xor     al, al
0x18008b584  mov     rbx, [rsp+50h+arg_0]
0x18008b58c  add     rsp, 50h
0x18008b590  pop     r15
0x18008b592  pop     r14
0x18008b594  pop     r13
0x18008b596  pop     r12
0x18008b598  pop     rdi
0x18008b599  pop     rsi
0x18008b59a  pop     rbp
0x18008b59b  retn
```
