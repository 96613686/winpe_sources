# prepare_archive_reader(archive *,ushort const *)

- ea: `0x18005634c`
- end: `0x18005647f`
- name: `?prepare_archive_reader@@YAXPEAUarchive@@PEBG@Z`
- size: `307`
- prototype: `void __fastcall(struct archive *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180054c60`
- `0x180061088`
- `0x1800613a0`
- `0x1800618e4`
- `0x180061bfc`
- `0x18006a4a8`

## callees

- `0x180034760`
- `0x180034e5c`
- `0x180036f50`
- `0x18004d03c`
- `0x18005634c`

## import_xrefs

- `archiveint!archive_read_support_filter_all` at `0x180056428`
- `archiveint!archive_read_support_filter_all` at `0x180056428`
- `archiveint!archive_read_support_format_raw` at `0x18005641f`
- `archiveint!archive_read_support_format_raw` at `0x18005641f`
- `archiveint!archive_read_support_format_all` at `0x180056416`
- `archiveint!archive_read_support_format_all` at `0x180056416`
- `archiveint!archive_read_set_format_option` at `0x180056446`
- `archiveint!archive_read_set_format_option` at `0x180056464`
- `archiveint!archive_read_set_format_option` at `0x180056446`
- `archiveint!archive_read_set_format_option` at `0x180056464`

## pseudocode

```c
void __fastcall prepare_archive_reader(struct archive *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int128 v5; // [rsp+20h] [rbp-48h] BYREF
  __int128 v6; // [rsp+30h] [rbp-38h] BYREF
  __int128 v7; // [rsp+40h] [rbp-28h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SHINE_2602_Bugs>::__private_IsEnabled() )
    goto LABEL_8;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  *(_QWORD *)&v5 = a2;
  *((_QWORD *)&v5 + 1) = v4;
  split_extension(&v6, &v5);
  if ( !*((_QWORD *)&v7 + 1)
    || (v5 = v7,
        !(unsigned __int8)matches_name<std::basic_string_view<unsigned short> const *>(
                            &v5,
                            &supported_archive_filter_formats,
                            &supported_archive_formats_inside_containers))
    || (v5 = v6, split_extension(&v6, &v5), *((_QWORD *)&v7 + 1))
    && (v5 = v7,
        (unsigned __int8)matches_name<std::basic_string_view<unsigned short> const *>(
                           &v5,
                           &supported_archive_formats_inside_containers,
                           &off_1800761E0)) )
  {
LABEL_8:
    archive_read_support_format_all(a1);
  }
  archive_read_support_format_raw(a1);
  archive_read_support_filter_all(a1);
  archive_read_set_format_option(a1, "tar", "hdrcharset", "UTF-8");
  archive_read_set_format_option(a1, "rar", "hdrcharset", "UTF-8");
}

```

## disassembly

```asm
0x18005634c  push    rbp
0x18005634e  push    rbx
0x18005634f  push    rsi
0x180056350  push    rdi
0x180056351  mov     rbp, rsp
0x180056354  sub     rsp, 68h
0x180056358  mov     rax, cs:__security_cookie
0x18005635f  xor     rax, rsp
0x180056362  mov     [rbp+var_18], rax
0x180056366  mov     rdi, rdx
0x180056369  mov     rbx, rcx
0x18005636c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SHINE_2602_Bugs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SHINE_2602_Bugs>::__private_IsEnabled(void)
0x180056371  xor     esi, esi
0x180056373  test    al, al
0x180056375  jz      loc_180056413
0x18005637b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005637f  inc     rax
0x180056382  cmp     [rdi+rax*2], si
0x180056386  jnz     short loc_18005637F
0x180056388  lea     rdx, [rbp+var_48]
0x18005638c  mov     qword ptr [rbp+var_48], rdi
0x180056390  lea     rcx, [rbp+var_38]
0x180056394  mov     qword ptr [rbp+var_48+8], rax
0x180056398  call    ?split_extension@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_extension(std::basic_string_view<ushort>)
0x18005639d  mov     rcx, qword ptr [rbp+var_28+8]
0x1800563a1  test    rcx, rcx
0x1800563a4  jz      short loc_180056413
0x1800563a6  mov     rax, qword ptr [rbp+var_28]
0x1800563aa  lea     r8, ?supported_archive_formats_inside_containers@@3QBV?$basic_string_view@GU?$char_traits@G@std@@@std@@B; std::basic_string_view<ushort> const near * const supported_archive_formats_inside_containers
0x1800563b1  mov     qword ptr [rbp+var_48+8], rcx
0x1800563b5  lea     rdx, ?supported_archive_filter_formats@@3QBV?$basic_string_view@GU?$char_traits@G@std@@@std@@B; std::basic_string_view<ushort> const near * const supported_archive_filter_formats
0x1800563bc  lea     rcx, [rbp+var_48]
0x1800563c0  mov     qword ptr [rbp+var_48], rax
0x1800563c4  call    ??$matches_name@PEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@@YA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEBV01@1@Z; matches_name<std::basic_string_view<ushort> const *>(std::basic_string_view<ushort>,std::basic_string_view<ushort> const *,std::basic_string_view<ushort> const *)
0x1800563c9  test    al, al
0x1800563cb  jz      short loc_180056413
0x1800563cd  movups  xmm0, [rbp+var_38]
0x1800563d1  lea     rdx, [rbp+var_48]
0x1800563d5  lea     rcx, [rbp+var_38]
0x1800563d9  movdqu  [rbp+var_48], xmm0
0x1800563de  call    ?split_extension@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_extension(std::basic_string_view<ushort>)
0x1800563e3  mov     rcx, qword ptr [rbp+var_28+8]
0x1800563e7  test    rcx, rcx
0x1800563ea  jz      short loc_18005641C
0x1800563ec  mov     rax, qword ptr [rbp+var_28]
0x1800563f0  lea     r8, off_1800761E0; "copy"
0x1800563f7  mov     qword ptr [rbp+var_48+8], rcx
0x1800563fb  lea     rdx, ?supported_archive_formats_inside_containers@@3QBV?$basic_string_view@GU?$char_traits@G@std@@@std@@B; std::basic_string_view<ushort> const near * const supported_archive_formats_inside_containers
0x180056402  lea     rcx, [rbp+var_48]
0x180056406  mov     qword ptr [rbp+var_48], rax
0x18005640a  call    ??$matches_name@PEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@@YA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEBV01@1@Z; matches_name<std::basic_string_view<ushort> const *>(std::basic_string_view<ushort>,std::basic_string_view<ushort> const *,std::basic_string_view<ushort> const *)
0x18005640f  test    al, al
0x180056411  jz      short loc_18005641C
0x180056413  mov     rcx, rbx
0x180056416  call    cs:__imp_archive_read_support_format_all
0x18005641c  mov     rcx, rbx
0x18005641f  call    cs:__imp_archive_read_support_format_raw
0x180056425  mov     rcx, rbx
0x180056428  call    cs:__imp_archive_read_support_filter_all
0x18005642e  lea     r9, aUtf8; "UTF-8"
0x180056435  mov     rcx, rbx
0x180056438  lea     r8, aHdrcharset; "hdrcharset"
0x18005643f  lea     rdx, aTar_0; "tar"
0x180056446  call    cs:__imp_archive_read_set_format_option
0x18005644c  lea     r9, aUtf8; "UTF-8"
0x180056453  mov     rcx, rbx
0x180056456  lea     r8, aHdrcharset; "hdrcharset"
0x18005645d  lea     rdx, aRar; "rar"
0x180056464  call    cs:__imp_archive_read_set_format_option
0x18005646a  mov     rcx, [rbp+var_18]
0x18005646e  xor     rcx, rsp; StackCookie
0x180056471  call    __security_check_cookie
0x180056476  add     rsp, 68h
0x18005647a  pop     rdi
0x18005647b  pop     rsi
0x18005647c  pop     rbx
0x18005647d  pop     rbp
0x18005647e  retn
```
