# ExtractSymbolicLink

- ea: `0x180066210`
- end: `0x180066444`
- name: `ExtractSymbolicLink`
- size: `564`
- prototype: `char *__fastcall(char *, struct archive_entry *, __int64, char)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180064cec`

## callees

- `0x180020cbc`
- `0x180024a7c`
- `0x18002abd0`
- `0x180034fbc`
- `0x1800350cc`
- `0x18003534c`
- `0x180036f50`
- `0x180055790`
- `0x180062684`
- `0x180066210`
- `0x180068cf8`
- `0x180068e80`
- `0x180068f88`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x1800662af`
- `SHLWAPI!PathIsRelativeW` at `0x1800662af`
- `archiveint!archive_entry_symlink_w` at `0x180066249`
- `archiveint!archive_entry_symlink_w` at `0x180066249`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180066375`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180066375`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x180066338`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x180066338`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall ExtractSymbolicLink(char *a1, struct archive_entry *a2, __int64 a3, char a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // r8
  const WCHAR *v11; // rax
  const WCHAR *v12; // rax
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // r15d
  const WCHAR *v16; // rax
  LPCWSTR v17; // r9
  const WCHAR *v18; // rax
  char *FileW; // rax
  __int64 v20; // rax
  char v22[8]; // [rsp+40h] [rbp-39h] BYREF
  char *v23; // [rsp+48h] [rbp-31h] BYREF
  int v24; // [rsp+58h] [rbp-21h] BYREF
  char v25; // [rsp+5Ch] [rbp-1Dh]
  _QWORD v26[2]; // [rsp+60h] [rbp-19h] BYREF
  __m128i si128; // [rsp+70h] [rbp-9h]
  _BYTE v28[16]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 v29; // [rsp+90h] [rbp+17h]

  v23 = a1;
  v8 = archive_entry_symlink_w(a2);
  if ( v8 )
  {
    std::wstring::wstring(v28, v8);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    replace_invalid_path_chars(v11, v29, 1);
    if ( (a4 & 4) != 0
      || (v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28), PathIsRelativeW(v12)) )
    {
      v15 = -((unsigned int)DeduceSymlinkType(a2) != 2);
      v22[0] = 0;
      while ( 1 )
      {
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
        v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
        if ( CreateSymbolicLinkW(v17, v16, v15 + 3) )
          break;
        TryHandleCreationFailure((__int64)&v24, a3, a4, v22);
        if ( v24 < 0 )
        {
          *(_DWORD *)a1 = v24;
          a1[4] = v25;
          *((_QWORD *)a1 + 1) = v26[0];
          *((_QWORD *)a1 + 2) = v26[1];
          *(__m128i *)(a1 + 24) = si128;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v26[0]) = 0;
          std::wstring::_Tidy_deallocate(v26);
          goto LABEL_13;
        }
        std::wstring::_Tidy_deallocate(v26);
      }
      v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      FileW = (char *)CreateFileW(v18, 0x100u, 7u, 0, 3u, 0x2200000u, 0);
      v23 = FileW;
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        TryRestoreFileTimes_0(FileW, a2);
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      TryRestoreAttributes_0(v20, a2);
      *(_OWORD *)a1 = 0;
      *((_OWORD *)a1 + 1) = 0;
      *(_DWORD *)a1 = 0;
      a1[4] = 0;
      *(_OWORD *)(a1 + 8) = 0;
      *((_QWORD *)a1 + 3) = 0;
      *((_QWORD *)a1 + 4) = 7;
      *((_WORD *)a1 + 4) = 0;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    }
    else
    {
      v13 = std::wstring::wstring(&v24, a3);
      LOBYTE(v14) = 9;
      ExtractResult::ExtractResult(a1, 2147943864LL, v14, v13);
    }
LABEL_13:
    std::wstring::_Tidy_deallocate(v28);
  }
  else
  {
    v9 = std::wstring::wstring(&v24, a3);
    LOBYTE(v10) = 2;
    ExtractResult::ExtractResult(a1, 2147942561LL, v10, v9);
  }
  return a1;
}

```

## disassembly

```asm
0x180066210  mov     [rsp-8+arg_18], rbx
0x180066215  push    rbp
0x180066216  push    rsi
0x180066217  push    rdi
0x180066218  push    r14
0x18006621a  push    r15
0x18006621c  lea     rbp, [rsp-37h]
0x180066221  sub     rsp, 0B0h
0x180066228  mov     rax, cs:__security_cookie
0x18006622f  xor     rax, rsp
0x180066232  mov     [rbp+57h+var_30], rax
0x180066236  mov     r14b, r9b
0x180066239  mov     rdi, r8
0x18006623c  mov     rsi, rdx
0x18006623f  mov     rbx, rcx
0x180066242  mov     [rbp+57h+var_88], rcx
0x180066246  mov     rcx, rdx
0x180066249  call    cs:__imp_archive_entry_symlink_w
0x18006624f  test    rax, rax
0x180066252  jnz     short loc_180066278
0x180066254  mov     rdx, rdi
0x180066257  lea     rcx, [rbp+57h+var_78]
0x18006625b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180066260  mov     r9, rax
0x180066263  mov     r8b, 2
0x180066266  mov     edx, 800700A1h
0x18006626b  mov     rcx, rbx
0x18006626e  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x180066273  jmp     loc_1800663DB
0x180066278  mov     rdx, rax
0x18006627b  lea     rcx, [rbp+57h+var_50]
0x18006627f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066284  nop
0x180066285  lea     rcx, [rbp+57h+var_50]
0x180066289  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006628e  mov     rcx, rax; pszPath
0x180066291  mov     r8b, 1; bool
0x180066294  mov     rdx, [rbp+57h+var_40]; unsigned __int64
0x180066298  call    ?replace_invalid_path_chars@@YA_NPEAG_K_N@Z; replace_invalid_path_chars(ushort *,unsigned __int64,bool)
0x18006629d  test    r14b, 4
0x1800662a1  jnz     short loc_1800662DD
0x1800662a3  lea     rcx, [rbp+57h+var_50]
0x1800662a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800662ac  mov     rcx, rax; pszPath
0x1800662af  call    cs:__imp_PathIsRelativeW
0x1800662b5  test    eax, eax
0x1800662b7  jnz     short loc_1800662DD
0x1800662b9  mov     rdx, rdi
0x1800662bc  lea     rcx, [rbp+57h+var_78]
0x1800662c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800662c5  mov     r9, rax
0x1800662c8  mov     r8b, 9
0x1800662cb  mov     edx, 800705B8h
0x1800662d0  mov     rcx, rbx
0x1800662d3  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x1800662d8  jmp     loc_1800663D2
0x1800662dd  mov     rcx, rsi; struct archive_entry *
0x1800662e0  call    ?DeduceSymlinkType@@YAHPEAUarchive_entry@@@Z; DeduceSymlinkType(archive_entry *)
0x1800662e5  sub     eax, 2
0x1800662e8  neg     eax
0x1800662ea  sbb     r15d, r15d
0x1800662ed  mov     [rbp+57h+var_90], 0
0x1800662f1  jmp     short loc_18006631A
0x1800662f3  lea     r9, [rbp+57h+var_90]
0x1800662f7  mov     r8b, r14b
0x1800662fa  mov     rdx, rdi
0x1800662fd  lea     rcx, [rbp+57h+var_78]
0x180066301  call    TryHandleCreationFailure
0x180066306  mov     eax, [rbp+57h+var_78]
0x180066309  lea     rcx, [rbp+57h+var_70]
0x18006630d  test    eax, eax
0x18006630f  js      loc_180066401
0x180066315  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006631a  mov     rcx, rdi
0x18006631d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180066322  mov     r9, rax
0x180066325  lea     rcx, [rbp+57h+var_50]
0x180066329  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006632e  lea     r8d, [r15+3]; dwFlags
0x180066332  mov     rdx, rax; lpTargetFileName
0x180066335  mov     rcx, r9; lpSymlinkFileName
0x180066338  call    cs:__imp_CreateSymbolicLinkW
0x18006633e  test    al, al
0x180066340  jz      short loc_1800662F3
0x180066342  mov     rcx, rdi
0x180066345  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006634a  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x180066353  mov     [rsp+0D0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18006635b  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180066363  xor     r9d, r9d; lpSecurityAttributes
0x180066366  lea     r14d, [r9+7]
0x18006636a  mov     r8d, r14d; dwShareMode
0x18006636d  mov     edx, 100h; dwDesiredAccess
0x180066372  mov     rcx, rax; lpFileName
0x180066375  call    cs:__imp_CreateFileW
0x18006637b  mov     [rbp+57h+var_88], rax
0x18006637f  lea     rcx, [rax-1]
0x180066383  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180066387  ja      short loc_180066394
0x180066389  mov     rdx, rsi
0x18006638c  mov     rcx, rax
0x18006638f  call    TryRestoreFileTimes_0
0x180066394  mov     rcx, rdi
0x180066397  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006639c  mov     rdx, rsi
0x18006639f  mov     rcx, rax
0x1800663a2  call    TryRestoreAttributes_0
0x1800663a7  xorps   xmm0, xmm0
0x1800663aa  xor     eax, eax
0x1800663ac  movups  xmmword ptr [rbx], xmm0
0x1800663af  movups  xmmword ptr [rbx+10h], xmm0
0x1800663b3  mov     [rbx], eax
0x1800663b5  mov     [rbx+4], al
0x1800663b8  movups  xmmword ptr [rbx+8], xmm0
0x1800663bc  mov     [rbx+18h], rax
0x1800663c0  mov     [rbx+20h], r14
0x1800663c4  mov     [rbx+8], ax
0x1800663c8  lea     rcx, [rbp+57h+var_88]
0x1800663cc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800663d1  nop
0x1800663d2  lea     rcx, [rbp+57h+var_50]
0x1800663d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800663db  mov     rax, rbx
0x1800663de  mov     rcx, [rbp+57h+var_30]
0x1800663e2  xor     rcx, rsp; StackCookie
0x1800663e5  call    __security_check_cookie
0x1800663ea  mov     rbx, [rsp+0D0h+arg_18]
0x1800663f2  add     rsp, 0B0h
0x1800663f9  pop     r15
0x1800663fb  pop     r14
0x1800663fd  pop     rdi
0x1800663fe  pop     rsi
0x1800663ff  pop     rbp
0x180066400  retn
0x180066401  mov     [rbx], eax
0x180066403  mov     al, [rbp+57h+var_74]
0x180066406  mov     [rbx+4], al
0x180066409  mov     rax, [rbp+57h+var_70]
0x18006640d  mov     [rbx+8], rax
0x180066411  mov     rax, [rbp+57h+var_68]
0x180066415  mov     [rbx+10h], rax
0x180066419  mov     rax, qword ptr [rbp+57h+var_60]
0x18006641d  mov     [rbx+18h], rax
0x180066421  mov     rax, qword ptr [rbp+57h+var_60+8]
0x180066425  mov     [rbx+20h], rax
0x180066429  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180066431  movdqu  [rbp+57h+var_60], xmm0
0x180066436  xor     eax, eax
0x180066438  mov     word ptr [rbp+57h+var_70], ax
0x18006643c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066441  jmp     short loc_1800663D2
```
