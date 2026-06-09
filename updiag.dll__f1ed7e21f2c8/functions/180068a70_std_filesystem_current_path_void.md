# std::filesystem::current_path(void)

- ea: `0x180068a70`
- end: `0x180068b40`
- name: `?current_path@filesystem@std@@YA?AVpath@12@XZ`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d73c`

## callees

- `0x180028b18`
- `0x180068a18`
- `0x180068a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068adf`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180068aca`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180068aca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::filesystem::current_path(__int64 a1)
{
  DWORD v2; // ebp
  WCHAR *v3; // rdx
  DWORD CurrentDirectoryW; // esi
  DWORD LastError; // edi
  std::filesystem *v6; // rcx
  const struct std::error_code *v7; // r8
  char v9[16]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+40h] [rbp-28h]

  v10 = a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  std::wstring::resize((void *)a1);
  do
  {
    v2 = *(_DWORD *)(a1 + 16);
    v3 = (WCHAR *)a1;
    if ( *(_QWORD *)(a1 + 24) > 7u )
      v3 = *(WCHAR **)a1;
    CurrentDirectoryW = GetCurrentDirectoryW(v2, v3);
    if ( CurrentDirectoryW && CurrentDirectoryW <= v2 )
      LastError = 0;
    else
      LastError = GetLastError();
    std::wstring::resize((void *)a1);
  }
  while ( CurrentDirectoryW >= v2 );
  *(_DWORD *)v9 = LastError;
  *(_QWORD *)&v9[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( LastError )
    std::filesystem::_Throw_fs_error(v6, v9, v7);
  return a1;
}

```

## disassembly

```asm
0x180068a70  mov     rax, rsp
0x180068a73  mov     [rax+10h], rbx
0x180068a77  mov     [rax+18h], rbp
0x180068a7b  push    rsi
0x180068a7c  push    rdi
0x180068a7d  push    r14
0x180068a7f  sub     rsp, 50h
0x180068a83  mov     rbx, rcx
0x180068a86  mov     [rax-28h], rcx
0x180068a8a  xor     r14d, r14d
0x180068a8d  mov     [rax-48h], r14d
0x180068a91  xorps   xmm0, xmm0
0x180068a94  movups  xmmword ptr [rcx], xmm0
0x180068a97  mov     [rcx+10h], r14
0x180068a9b  mov     qword ptr [rcx+18h], 7
0x180068aa3  mov     [rcx], r14w
0x180068aa7  mov     dword ptr [rax-48h], 2
0x180068aae  mov     edx, 104h
0x180068ab3  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180068ab8  mov     ebp, [rbx+10h]
0x180068abb  mov     rdx, rbx
0x180068abe  cmp     qword ptr [rbx+18h], 7
0x180068ac3  jbe     short loc_180068AC8
0x180068ac5  mov     rdx, [rbx]; lpBuffer
0x180068ac8  mov     ecx, ebp; nBufferLength
0x180068aca  call    cs:__imp_GetCurrentDirectoryW
0x180068ad0  mov     esi, eax
0x180068ad2  test    eax, eax
0x180068ad4  jz      short loc_180068ADF
0x180068ad6  cmp     esi, ebp
0x180068ad8  ja      short loc_180068ADF
0x180068ada  mov     edi, r14d
0x180068add  jmp     short loc_180068AE7
0x180068adf  call    cs:__imp_GetLastError
0x180068ae5  mov     edi, eax
0x180068ae7  mov     rdx, rsi
0x180068aea  mov     rcx, rbx; Src
0x180068aed  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180068af2  cmp     esi, ebp
0x180068af4  jnb     short loc_180068AB8
0x180068af6  mov     dword ptr [rsp+68h+var_38], edi
0x180068afa  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180068b01  mov     qword ptr [rsp+68h+var_38+8], rax
0x180068b06  movaps  xmm0, xmmword ptr [rsp+68h+var_38]
0x180068b0b  movdqa  xmmword ptr [rsp+68h+var_38], xmm0
0x180068b11  mov     [rsp+68h+var_48], 1
0x180068b19  test    edi, edi
0x180068b1b  jnz     short loc_180068B35
0x180068b1d  mov     rax, rbx
0x180068b20  lea     r11, [rsp+68h+var_18]
0x180068b25  mov     rbx, [r11+28h]
0x180068b29  mov     rbp, [r11+30h]
0x180068b2d  mov     rsp, r11
0x180068b30  pop     r14
0x180068b32  pop     rdi
0x180068b33  pop     rsi
0x180068b34  retn
0x180068b35  lea     rdx, [rsp+68h+var_38]; char *
0x180068b3a  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &)
```
