# BrainUtils::ConvertHandleToPath(void *)

- ea: `0x18003460c`
- end: `0x18003476e`
- name: `?ConvertHandleToPath@BrainUtils@@SA?AVpath@filesystem@std@@PEAX@Z`
- size: `354`
- prototype: `static struct std::filesystem::path __high(void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x180034774`
- `0x18003a620`

## callees

- `0x1800258c4`
- `0x180026a00`
- `0x180029518`
- `0x180029644`
- `0x18003460c`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003464a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180034699`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003464a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180034699`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall BrainUtils::ConvertHandleToPath(_OWORD *a1, void *a2)
{
  DWORD FinalPathNameByHandleW; // ebx
  const char *v5; // r9
  WCHAR *v6; // rdx
  DWORD v7; // edx
  const char *v8; // r9
  char v9; // cl
  LPWSTR *v10; // rdx
  __int128 v12; // [rsp+28h] [rbp-58h] BYREF
  __m128i v13; // [rsp+38h] [rbp-48h]
  _OWORD *v14; // [rsp+48h] [rbp-38h]
  LPWSTR lpszFilePath[2]; // [rsp+50h] [rbp-30h] BYREF
  __m128i si128; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v14 = a1;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a2, 0, 0, 0);
  if ( !FinalPathNameByHandleW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6B,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainUtils.hpp",
      v5);
  *(_OWORD *)lpszFilePath = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpszFilePath[0]) = 0;
  std::wstring::resize(lpszFilePath);
  v6 = (WCHAR *)lpszFilePath;
  if ( si128.m128i_i64[1] > 7uLL )
    v6 = lpszFilePath[0];
  v7 = GetFinalPathNameByHandleW(a2, v6, FinalPathNameByHandleW, 0);
  if ( !v7 || (v9 = 0, v7 >= FinalPathNameByHandleW) )
    v9 = 1;
  if ( v9 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x70,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainUtils.hpp",
      v8);
  v12 = 0;
  v13 = 0;
  v10 = lpszFilePath;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = (LPWSTR *)lpszFilePath[0];
  std::wstring::_Construct<1,wchar_t const *>(&v12, v10);
  *a1 = v12;
  a1[1] = v13;
  v13 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v12) = 0;
  std::wstring::_Tidy_deallocate(&v12);
  std::wstring::_Tidy_deallocate(lpszFilePath);
  return a1;
}

```

## disassembly

```asm
0x18003460c  mov     [rsp-18h+arg_10], rbx
0x180034611  mov     [rsp-18h+arg_18], rsi
0x180034616  push    rbp
0x180034617  push    rdi
0x180034618  push    r14
0x18003461a  mov     rbp, rsp
0x18003461d  sub     rsp, 80h
0x180034624  mov     rax, cs:__security_cookie
0x18003462b  xor     rax, rsp
0x18003462e  mov     [rbp+var_10], rax
0x180034632  mov     rsi, rdx
0x180034635  mov     rdi, rcx
0x180034638  mov     [rbp+var_38], rcx
0x18003463c  xor     r14d, r14d
0x18003463f  xor     r9d, r9d; dwFlags
0x180034642  xor     r8d, r8d; cchFilePath
0x180034645  xor     edx, edx; lpszFilePath
0x180034647  mov     rcx, rsi; hFile
0x18003464a  call    cs:__imp_GetFinalPathNameByHandleW
0x180034650  mov     ebx, eax
0x180034652  mov     rcx, [rbp+18h]; this
0x180034656  test    eax, eax
0x180034658  jz      loc_18003475C
0x18003465e  xorps   xmm0, xmm0
0x180034661  movups  xmmword ptr [rbp+lpszFilePath], xmm0
0x180034665  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003466d  movdqu  [rbp+var_20], xmm1
0x180034672  mov     word ptr [rbp+lpszFilePath], r14w
0x180034677  mov     edx, ebx
0x180034679  lea     rcx, [rbp+lpszFilePath]; Src
0x18003467d  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180034682  lea     rdx, [rbp+lpszFilePath]
0x180034686  cmp     qword ptr [rbp+var_20+8], 7
0x18003468b  cmova   rdx, [rbp+lpszFilePath]; lpszFilePath
0x180034690  xor     r9d, r9d; dwFlags
0x180034693  mov     r8d, ebx; cchFilePath
0x180034696  mov     rcx, rsi; hFile
0x180034699  call    cs:__imp_GetFinalPathNameByHandleW
0x18003469f  mov     edx, eax
0x1800346a1  test    eax, eax
0x1800346a3  jz      short loc_1800346AC
0x1800346a5  cmp     edx, ebx
0x1800346a7  mov     cl, r14b
0x1800346aa  jb      short loc_1800346AE
0x1800346ac  mov     cl, 1
0x1800346ae  mov     rax, [rbp+18h]
0x1800346b2  test    cl, cl
0x1800346b4  jnz     loc_180034747
0x1800346ba  xorps   xmm0, xmm0
0x1800346bd  movups  [rbp+var_58], xmm0
0x1800346c1  xorps   xmm1, xmm1
0x1800346c4  movdqu  [rbp+var_48], xmm1
0x1800346c9  mov     r8, rdx
0x1800346cc  cmp     qword ptr [rbp+var_20], rdx
0x1800346d0  cmovb   r8, qword ptr [rbp+var_20]
0x1800346d5  lea     rdx, [rbp+lpszFilePath]
0x1800346d9  cmp     qword ptr [rbp+var_20+8], 7
0x1800346de  cmova   rdx, [rbp+lpszFilePath]
0x1800346e3  lea     rcx, [rbp+var_58]
0x1800346e7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800346ec  movups  xmm0, [rbp+var_58]
0x1800346f0  movups  xmmword ptr [rdi], xmm0
0x1800346f3  movups  xmm1, [rbp+var_48]
0x1800346f7  movups  xmmword ptr [rdi+10h], xmm1
0x1800346fb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180034703  movdqu  [rbp+var_48], xmm0
0x180034708  mov     word ptr [rbp+var_58], r14w
0x18003470d  lea     rcx, [rbp+var_58]
0x180034711  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034716  nop
0x180034717  lea     rcx, [rbp+lpszFilePath]
0x18003471b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034720  mov     rax, rdi
0x180034723  mov     rcx, [rbp+var_10]
0x180034727  xor     rcx, rsp; StackCookie
0x18003472a  call    __security_check_cookie
0x18003472f  lea     r11, [rsp+80h+var_s0]
0x180034737  mov     rbx, [r11+30h]
0x18003473b  mov     rsi, [r11+38h]
0x18003473f  mov     rsp, r11
0x180034742  pop     r14
0x180034744  pop     rdi
0x180034745  pop     rbp
0x180034746  retn
0x180034747  lea     r8, aCW1SSrcBrainLi_7; "C:\\__w\\1\\s\\src\\brain\\lib\\BrainUt"...
0x18003474e  mov     edx, 70h ; 'p'; void *
0x180034753  mov     rcx, rax; this
0x180034756  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003475c  lea     r8, aCW1SSrcBrainLi_7; "C:\\__w\\1\\s\\src\\brain\\lib\\BrainUt"...
0x180034763  mov     edx, 6Bh ; 'k'; void *
0x180034768  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
