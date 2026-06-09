# std::filesystem::_Dir_enum_impl::_Creator::_Creator(std::filesystem::path const &,std::filesystem::directory_options)

- ea: `0x18002603c`
- end: `0x180026248`
- name: `??0_Creator@_Dir_enum_impl@filesystem@std@@QEAA@AEBVpath@23@W4directory_options@23@@Z`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800264ac`

## callees

- `0x18002603c`
- `0x180027228`
- `0x180028728`
- `0x180028ec4`
- `0x1800295e8`
- `0x180029644`
- `0x180042640`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261b0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180026133`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180026133`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002610e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002610e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800261a6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800261a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall std::filesystem::_Dir_enum_impl::_Creator::_Creator(__int64 *a1, __int64 a2, char a3)
{
  __int64 *v5; // rcx
  __int64 v6; // rax
  const WCHAR *v7; // rbx
  void *v8; // rcx
  HANDLE FirstFile; // rax
  DWORD v10; // eax
  struct std::error_code *v11; // r8
  DWORD LastError; // ebx
  void *v13; // r14
  _QWORD v15[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v16; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v18[32]; // [rsp+70h] [rbp+7h] BYREF

  v16 = a1;
  std::wstring::wstring(a1, a2);
  a1[4] = -1;
  v5 = a1;
  if ( (unsigned __int64)a1[3] > 7 )
    v5 = (__int64 *)*a1;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)v5 + v6) );
  if ( !v6 || v6 != a1[2] )
  {
    LastError = 2;
    goto LABEL_35;
  }
  std::wstring::wstring(v18, a1);
  v15[0] = L"*";
  v15[1] = 1;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v17, v15);
  std::filesystem::path::operator/=((std::filesystem *)a1, (std::filesystem *)v17);
  std::wstring::_Tidy_deallocate(v17);
  v7 = (const WCHAR *)a1;
  if ( (unsigned __int64)a1[3] > 7 )
    v7 = (const WCHAR *)*a1;
  v8 = (void *)a1[4];
  if ( v8 != (void *)-1LL && !FindClose(v8) )
    abort();
  FirstFile = FindFirstFileExW(v7, FindExInfoBasic, a1 + 5, FindExSearchNameMatch, 0, 0);
  a1[4] = (__int64)FirstFile;
  if ( FirstFile == (HANDLE)-1LL && (v10 = GetLastError(), (LastError = v10) != 0) )
  {
    if ( v10 == 5 )
    {
      if ( (a3 & 2) != 0 )
        LastError = 18;
    }
    else if ( v10 == 2
           && std::filesystem::exists((std::filesystem *)v18, (const struct std::filesystem::path *)&v16, v11) )
    {
      LastError = 18;
    }
  }
  else
  {
    v13 = (void *)a1[4];
    while ( *((_WORD *)a1 + 42) == 46 && (!*((_WORD *)a1 + 43) || *((_WORD *)a1 + 43) == 46 && !*((_WORD *)a1 + 44)) )
    {
      if ( !FindNextFileW(v13, (LPWIN32_FIND_DATAW)(a1 + 5)) )
      {
        LastError = GetLastError();
        if ( LastError )
          goto LABEL_29;
      }
    }
    LastError = 0;
  }
LABEL_29:
  std::wstring::_Tidy_deallocate(v18);
  if ( LastError )
  {
    if ( LastError == 18 )
    {
      LOBYTE(v15[0]) = 0;
      goto LABEL_33;
    }
LABEL_35:
    LOBYTE(v15[0]) = 0;
    *(_WORD *)((char *)v15 + 1) = 0;
    BYTE3(v15[0]) = 0;
    HIDWORD(v15[0]) = LastError;
    a1[79] = v15[0];
    return a1;
  }
  LOBYTE(v15[0]) = 1;
LABEL_33:
  *(_WORD *)((char *)v15 + 1) = 0;
  BYTE3(v15[0]) = 0;
  HIDWORD(v15[0]) = 0;
  a1[79] = LOBYTE(v15[0]);
  return a1;
}

```

## disassembly

```asm
0x18002603c  mov     [rsp-8+arg_10], rbx
0x180026041  mov     [rsp-8+arg_18], rsi
0x180026046  push    rbp
0x180026047  push    rdi
0x180026048  push    r12
0x18002604a  push    r14
0x18002604c  push    r15
0x18002604e  lea     rbp, [rsp-37h]
0x180026053  sub     rsp, 0A0h
0x18002605a  mov     rax, cs:__security_cookie
0x180026061  xor     rax, rsp
0x180026064  mov     [rbp+57h+var_30], rax
0x180026068  mov     r14d, r8d
0x18002606b  mov     rdi, rcx
0x18002606e  mov     [rbp+57h+var_80], rcx
0x180026072  xor     r15d, r15d
0x180026075  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002607a  nop
0x18002607b  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x180026083  mov     rcx, rdi
0x180026086  cmp     qword ptr [rdi+18h], 7
0x18002608b  jbe     short loc_180026090
0x18002608d  mov     rcx, [rdi]
0x180026090  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026094  inc     rax
0x180026097  cmp     [rcx+rax*2], r15w
0x18002609c  jnz     short loc_180026094
0x18002609e  test    rax, rax
0x1800260a1  jz      loc_1800261F7
0x1800260a7  cmp     rax, [rdi+10h]
0x1800260ab  jnz     loc_1800261F7
0x1800260b1  mov     rdx, rdi
0x1800260b4  lea     rcx, [rbp+57h+var_50]
0x1800260b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800260bd  nop
0x1800260be  lea     rax, asc_180051F28; "*"
0x1800260c5  mov     [rbp+57h+var_90], rax
0x1800260c9  mov     r12d, 1
0x1800260cf  mov     [rbp+57h+var_88], r12
0x1800260d3  lea     rdx, [rbp+57h+var_90]
0x1800260d7  lea     rcx, [rbp+57h+var_70]
0x1800260db  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1800260e0  nop
0x1800260e1  lea     rdx, [rbp+57h+var_70]; void *
0x1800260e5  mov     rcx, rdi; Src
0x1800260e8  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x1800260ed  nop
0x1800260ee  lea     rcx, [rbp+57h+var_70]
0x1800260f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800260f7  mov     rbx, rdi
0x1800260fa  cmp     qword ptr [rdi+18h], 7
0x1800260ff  jbe     short loc_180026104
0x180026101  mov     rbx, [rdi]
0x180026104  mov     rcx, [rdi+20h]; hFindFile
0x180026108  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002610c  jz      short loc_18002611C
0x18002610e  call    cs:__imp_FindClose
0x180026114  test    eax, eax
0x180026116  jz      loc_180026242
0x18002611c  mov     [rsp+0C0h+dwAdditionalFlags], r15d; dwAdditionalFlags
0x180026121  mov     [rsp+0C0h+lpSearchFilter], r15; lpSearchFilter
0x180026126  xor     r9d, r9d; fSearchOp
0x180026129  lea     r8, [rdi+28h]; lpFindFileData
0x18002612d  mov     edx, r12d; fInfoLevelId
0x180026130  mov     rcx, rbx; lpFileName
0x180026133  call    cs:__imp_FindFirstFileExW
0x180026139  mov     [rdi+20h], rax
0x18002613d  mov     r12d, 12h
0x180026143  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026147  jnz     short loc_18002617F
0x180026149  call    cs:__imp_GetLastError
0x18002614f  mov     ebx, eax
0x180026151  test    eax, eax
0x180026153  jz      short loc_18002617F
0x180026155  cmp     eax, 5
0x180026158  jnz     short loc_180026165
0x18002615a  test    r14b, 2
0x18002615e  jz      short loc_1800261C1
0x180026160  mov     ebx, r12d
0x180026163  jmp     short loc_1800261C1
0x180026165  cmp     ebx, 2
0x180026168  jnz     short loc_1800261C1
0x18002616a  lea     rdx, [rbp+57h+var_80]; struct std::filesystem::path *
0x18002616e  lea     rcx, [rbp+57h+var_50]; this
0x180026172  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x180026177  test    al, al
0x180026179  cmovnz  ebx, r12d
0x18002617d  jmp     short loc_1800261C1
0x18002617f  mov     r14, [rdi+20h]
0x180026183  cmp     word ptr [rdi+54h], 2Eh ; '.'
0x180026188  jnz     short loc_1800261BE
0x18002618a  cmp     [rdi+56h], r15w
0x18002618f  jz      short loc_18002619F
0x180026191  cmp     word ptr [rdi+56h], 2Eh ; '.'
0x180026196  jnz     short loc_1800261BE
0x180026198  cmp     [rdi+58h], r15w
0x18002619d  jnz     short loc_1800261BE
0x18002619f  lea     rdx, [rdi+28h]; lpFindFileData
0x1800261a3  mov     rcx, r14; hFindFile
0x1800261a6  call    cs:__imp_FindNextFileW
0x1800261ac  test    eax, eax
0x1800261ae  jnz     short loc_180026183
0x1800261b0  call    cs:__imp_GetLastError
0x1800261b6  mov     ebx, eax
0x1800261b8  test    eax, eax
0x1800261ba  jz      short loc_180026183
0x1800261bc  jmp     short loc_1800261C1
0x1800261be  mov     ebx, r15d
0x1800261c1  lea     rcx, [rbp+57h+var_50]
0x1800261c5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800261ca  test    ebx, ebx
0x1800261cc  jnz     short loc_1800261D4
0x1800261ce  mov     byte ptr [rbp+57h+var_90], 1
0x1800261d2  jmp     short loc_1800261DD
0x1800261d4  cmp     ebx, r12d
0x1800261d7  jnz     short loc_1800261FC
0x1800261d9  mov     byte ptr [rbp+57h+var_90], r15b
0x1800261dd  xor     eax, eax
0x1800261df  mov     word ptr [rbp+57h+var_90+1], ax
0x1800261e3  mov     byte ptr [rbp+57h+var_90+3], al
0x1800261e6  mov     dword ptr [rbp+57h+var_90+4], r15d
0x1800261ea  mov     rax, [rbp+57h+var_90]
0x1800261ee  mov     [rdi+278h], rax
0x1800261f5  jmp     short loc_180026217
0x1800261f7  mov     ebx, 2
0x1800261fc  mov     byte ptr [rbp+57h+var_90], r15b
0x180026200  xor     eax, eax
0x180026202  mov     word ptr [rbp+57h+var_90+1], ax
0x180026206  mov     byte ptr [rbp+57h+var_90+3], al
0x180026209  mov     dword ptr [rbp+57h+var_90+4], ebx
0x18002620c  mov     rcx, [rbp+57h+var_90]
0x180026210  mov     [rdi+278h], rcx
0x180026217  mov     rax, rdi
0x18002621a  mov     rcx, [rbp+57h+var_30]
0x18002621e  xor     rcx, rsp; StackCookie
0x180026221  call    __security_check_cookie
0x180026226  lea     r11, [rsp+0C0h+var_20]
0x18002622e  mov     rbx, [r11+40h]
0x180026232  mov     rsi, [r11+48h]
0x180026236  mov     rsp, r11
0x180026239  pop     r15
0x18002623b  pop     r14
0x18002623d  pop     r12
0x18002623f  pop     rdi
0x180026240  pop     rbp
0x180026241  retn
0x180026242  call    abort
```
