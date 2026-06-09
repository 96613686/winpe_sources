# ExtractHardLink

- ea: `0x180065834`
- end: `0x180065a8b`
- name: `ExtractHardLink`
- size: `599`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path`

## callers

- `0x180064cec`

## callees

- `0x1800208a8`
- `0x180020cbc`
- `0x180024a7c`
- `0x18002abd0`
- `0x18002ed2c`
- `0x180034fbc`
- `0x1800350cc`
- `0x180035764`
- `0x180036f50`
- `0x180058260`
- `0x180058688`
- `0x18005f9d0`
- `0x180062684`
- `0x180062ad8`
- `0x180065834`
- `0x180068cf8`
- `0x180069834`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x1800658a1`
- `SHLWAPI!PathIsRelativeW` at `0x1800658a1`
- `archiveint!archive_entry_pathname_w` at `0x1800658f1`
- `archiveint!archive_entry_pathname_w` at `0x1800658f1`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800659e8`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800659e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall ExtractHardLink(__int64 a1, __int64 a2, __int64 a3, char a4, __int64 a5)
{
  __int64 v9; // rdx
  __int64 v10; // r8
  WCHAR *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  const WCHAR *v14; // rax
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  struct std::filesystem::path *v19; // rax
  std::filesystem::path *v20; // rax
  struct std::filesystem::path *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  const WCHAR *v26; // rax
  LPCWSTR v27; // r9
  __int64 v28; // r8
  char v30[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v31; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v32[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v33[32]; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+78h] [rbp-88h] BYREF
  char v35; // [rsp+7Ch] [rbp-84h]
  _QWORD v36[2]; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  _BYTE v38[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v39[16]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v40; // [rsp+D0h] [rbp-30h]
  _BYTE v41[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v42[32]; // [rsp+100h] [rbp+0h] BYREF

  v31 = a1;
  std::wstring::wstring(v39, a5);
  v11 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39, v9, v10);
  replace_invalid_path_chars(v11, v40, 1);
  if ( (a4 & 4) != 0
    || (v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39, v12, v13),
        PathIsRelativeW(v14)) )
  {
    std::filesystem::path::path(v38, v39);
    if ( !std::filesystem::path::is_absolute((std::filesystem::path *)v38) )
    {
      v31 = archive_entry_pathname_w(a2);
      std::filesystem::path::path(v41, &v31);
      v19 = std::filesystem::path::remove_filename((std::filesystem::path *)v41);
      std::filesystem::path::lexically_relative(v38, v42, v19);
      v20 = (std::filesystem::path *)std::filesystem::path::path(&v34, a3);
      v21 = std::filesystem::path::remove_filename(v20);
      v22 = std::filesystem::operator/(v33, v21, v42);
      v23 = std::filesystem::path::lexically_normal(v22, v32);
      std::wstring::operator=(v38, v23);
      std::wstring::_Tidy_deallocate(v32);
      std::wstring::_Tidy_deallocate(v33);
      std::wstring::_Tidy_deallocate(&v34);
      std::wstring::_Tidy_deallocate(v42);
      std::wstring::_Tidy_deallocate(v41);
    }
    v30[0] = 0;
    while ( 1 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v17, v18);
      v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38, v24, v25);
      if ( CreateHardLinkW(v27, v26, 0) )
      {
        *(_OWORD *)a1 = 0;
        *(_OWORD *)(a1 + 16) = 0;
        *(_DWORD *)a1 = 0;
        *(_BYTE *)(a1 + 4) = 0;
        *(_OWORD *)(a1 + 8) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        *(_QWORD *)(a1 + 32) = 7;
        *(_WORD *)(a1 + 8) = 0;
        goto LABEL_11;
      }
      LOBYTE(v28) = a4;
      ((void (__fastcall *)(int *, __int64, __int64, char *))TryHandleCreationFailure)(&v34, a3, v28, v30);
      if ( v34 < 0 )
        break;
      std::wstring::_Tidy_deallocate(v36);
    }
    *(_DWORD *)a1 = v34;
    *(_BYTE *)(a1 + 4) = v35;
    *(_QWORD *)(a1 + 8) = v36[0];
    *(_QWORD *)(a1 + 16) = v36[1];
    *(__m128i *)(a1 + 24) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v36[0]) = 0;
    std::wstring::_Tidy_deallocate(v36);
LABEL_11:
    std::wstring::_Tidy_deallocate(v38);
  }
  else
  {
    v15 = std::wstring::wstring(v41, a3);
    LOBYTE(v16) = 9;
    ExtractResult::ExtractResult(a1, 2147943864LL, v16, v15);
  }
  std::wstring::_Tidy_deallocate(v39);
  return a1;
}

```

## disassembly

```asm
0x180065834  push    rbp
0x180065836  push    rbx
0x180065837  push    rsi
0x180065838  push    rdi
0x180065839  push    r14
0x18006583b  lea     rbp, [rsp-30h]
0x180065840  sub     rsp, 130h
0x180065847  mov     rax, cs:__security_cookie
0x18006584e  xor     rax, rsp
0x180065851  mov     [rbp+50h+var_30], rax
0x180065855  mov     sil, r9b
0x180065858  mov     rdi, r8
0x18006585b  mov     r14, rdx
0x18006585e  mov     rbx, rcx
0x180065861  mov     [rsp+150h+var_128], rcx
0x180065866  mov     rdx, [rbp+50h+arg_20]
0x18006586d  lea     rcx, [rbp+50h+var_90]
0x180065871  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180065876  nop
0x180065877  lea     rcx, [rbp+50h+var_90]
0x18006587b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065880  mov     rcx, rax; pszPath
0x180065883  mov     r8b, 1; bool
0x180065886  mov     rdx, [rbp+50h+var_80]; unsigned __int64
0x18006588a  call    ?replace_invalid_path_chars@@YA_NPEAG_K_N@Z; replace_invalid_path_chars(ushort *,unsigned __int64,bool)
0x18006588f  test    sil, 4
0x180065893  jnz     short loc_1800658CF
0x180065895  lea     rcx, [rbp+50h+var_90]
0x180065899  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006589e  mov     rcx, rax; pszPath
0x1800658a1  call    cs:__imp_PathIsRelativeW
0x1800658a7  test    eax, eax
0x1800658a9  jnz     short loc_1800658CF
0x1800658ab  mov     rdx, rdi
0x1800658ae  lea     rcx, [rbp+50h+var_70]
0x1800658b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800658b7  mov     r9, rax
0x1800658ba  mov     r8b, 9
0x1800658bd  mov     edx, 800705B8h
0x1800658c2  mov     rcx, rbx
0x1800658c5  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x1800658ca  jmp     loc_180065A21
0x1800658cf  lea     rdx, [rbp+50h+var_90]
0x1800658d3  lea     rcx, [rbp+50h+var_B0]
0x1800658d7  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x1800658dc  nop
0x1800658dd  lea     rcx, [rbp+50h+var_B0]; this
0x1800658e1  call    ?is_absolute@path@filesystem@std@@QEBA_NXZ; std::filesystem::path::is_absolute(void)
0x1800658e6  test    al, al
0x1800658e8  jnz     loc_18006599A
0x1800658ee  mov     rcx, r14
0x1800658f1  call    cs:__imp_archive_entry_pathname_w
0x1800658f7  mov     [rsp+150h+var_128], rax
0x1800658fc  lea     rdx, [rsp+150h+var_128]
0x180065901  lea     rcx, [rbp+50h+var_70]
0x180065905  call    ??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z; std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)
0x18006590a  nop
0x18006590b  lea     rcx, [rbp+50h+var_70]; this
0x18006590f  call    ?remove_filename@path@filesystem@std@@QEAAAEAV123@XZ; std::filesystem::path::remove_filename(void)
0x180065914  mov     r8, rax
0x180065917  lea     rdx, [rbp+50h+var_50]
0x18006591b  lea     rcx, [rbp+50h+var_B0]
0x18006591f  call    ?lexically_relative@path@filesystem@std@@QEBA?AV123@AEBV123@@Z; std::filesystem::path::lexically_relative(std::filesystem::path const &)
0x180065924  nop
0x180065925  mov     rdx, rdi
0x180065928  lea     rcx, [rsp+150h+var_D8]
0x18006592d  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x180065932  nop
0x180065933  mov     rcx, rax; this
0x180065936  call    ?remove_filename@path@filesystem@std@@QEAAAEAV123@XZ; std::filesystem::path::remove_filename(void)
0x18006593b  mov     rdx, rax
0x18006593e  lea     r8, [rbp+50h+var_50]
0x180065942  lea     rcx, [rsp+150h+var_F8]
0x180065947  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18006594c  nop
0x18006594d  lea     rdx, [rsp+150h+var_118]
0x180065952  mov     rcx, rax
0x180065955  call    ?lexically_normal@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::lexically_normal(void)
0x18006595a  mov     rdx, rax
0x18006595d  lea     rcx, [rbp+50h+var_B0]
0x180065961  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180065966  lea     rcx, [rsp+150h+var_118]
0x18006596b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065970  nop
0x180065971  lea     rcx, [rsp+150h+var_F8]
0x180065976  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006597b  nop
0x18006597c  lea     rcx, [rsp+150h+var_D8]
0x180065981  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065986  nop
0x180065987  lea     rcx, [rbp+50h+var_50]
0x18006598b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065990  nop
0x180065991  lea     rcx, [rbp+50h+var_70]
0x180065995  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006599a  mov     [rsp+150h+var_130], 0
0x18006599f  jmp     short loc_1800659CB
0x1800659a1  lea     r9, [rsp+150h+var_130]
0x1800659a6  mov     r8b, sil
0x1800659a9  mov     rdx, rdi
0x1800659ac  lea     rcx, [rsp+150h+var_D8]
0x1800659b1  call    TryHandleCreationFailure
0x1800659b6  mov     eax, [rsp+150h+var_D8]
0x1800659ba  lea     rcx, [rbp+50h+var_D0]
0x1800659be  test    eax, eax
0x1800659c0  js      loc_180065A47
0x1800659c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800659cb  mov     rcx, rdi
0x1800659ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800659d3  mov     r9, rax
0x1800659d6  lea     rcx, [rbp+50h+var_B0]
0x1800659da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800659df  xor     r8d, r8d; lpSecurityAttributes
0x1800659e2  mov     rdx, rax; lpExistingFileName
0x1800659e5  mov     rcx, r9; lpFileName
0x1800659e8  call    cs:__imp_CreateHardLinkW
0x1800659ee  test    eax, eax
0x1800659f0  jz      short loc_1800659A1
0x1800659f2  xorps   xmm0, xmm0
0x1800659f5  xor     eax, eax
0x1800659f7  movups  xmmword ptr [rbx], xmm0
0x1800659fa  movups  xmmword ptr [rbx+10h], xmm0
0x1800659fe  mov     [rbx], eax
0x180065a00  mov     [rbx+4], al
0x180065a03  movups  xmmword ptr [rbx+8], xmm0
0x180065a07  mov     [rbx+18h], rax
0x180065a0b  mov     qword ptr [rbx+20h], 7
0x180065a13  mov     [rbx+8], ax
0x180065a17  lea     rcx, [rbp+50h+var_B0]
0x180065a1b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065a20  nop
0x180065a21  lea     rcx, [rbp+50h+var_90]
0x180065a25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065a2a  mov     rax, rbx
0x180065a2d  mov     rcx, [rbp+50h+var_30]
0x180065a31  xor     rcx, rsp; StackCookie
0x180065a34  call    __security_check_cookie
0x180065a39  add     rsp, 130h
0x180065a40  pop     r14
0x180065a42  pop     rdi
0x180065a43  pop     rsi
0x180065a44  pop     rbx
0x180065a45  pop     rbp
0x180065a46  retn
0x180065a47  mov     [rbx], eax
0x180065a49  mov     al, [rsp+150h+var_D4]
0x180065a4d  mov     [rbx+4], al
0x180065a50  mov     rax, [rbp+50h+var_D0]
0x180065a54  mov     [rbx+8], rax
0x180065a58  mov     rax, [rbp+50h+var_C8]
0x180065a5c  mov     [rbx+10h], rax
0x180065a60  mov     rax, qword ptr [rbp+50h+var_C0]
0x180065a64  mov     [rbx+18h], rax
0x180065a68  mov     rax, qword ptr [rbp+50h+var_C0+8]
0x180065a6c  mov     [rbx+20h], rax
0x180065a70  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180065a78  movdqu  [rbp+50h+var_C0], xmm0
0x180065a7d  xor     eax, eax
0x180065a7f  mov     word ptr [rbp+50h+var_D0], ax
0x180065a83  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065a88  jmp     short loc_180065A17
```
