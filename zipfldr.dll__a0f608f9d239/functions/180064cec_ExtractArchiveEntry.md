# ExtractArchiveEntry

- ea: `0x180064cec`
- end: `0x1800651d6`
- name: `ExtractArchiveEntry`
- size: `1258`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, installer_update`

## callers

- `0x180062d2c`
- `0x180063e64`
- `0x18006408c`
- `0x18006442c`

## callees

- `0x1800207f8`
- `0x180020cbc`
- `0x18002abd0`
- `0x18002f294`
- `0x180034fbc`
- `0x18003534c`
- `0x180036f50`
- `0x18005ff70`
- `0x180062648`
- `0x180062684`
- `0x180064cec`
- `0x180065834`
- `0x180065a94`
- `0x180066210`
- `0x180068b80`
- `0x180068c20`
- `0x180068e80`
- `0x180068f88`

## import_xrefs

- `archiveint!archive_entry_hardlink_w` at `0x18006515b`
- `archiveint!archive_entry_hardlink_w` at `0x18006515b`
- `archiveint!archive_entry_filetype` at `0x180064d57`
- `archiveint!archive_entry_filetype` at `0x180064d57`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064f50`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064f50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ExtractArchiveEntry(
        __int64 a1,
        __int64 a2,
        struct archive_entry *a3,
        __int64 a4,
        __int128 *a5,
        char a6,
        __int64 a7,
        const void *a8,
        __int64 a9)
{
  __int16 v13; // bx
  const WCHAR *v14; // rdx
  char v16; // bl
  __int64 v17; // rcx
  const WCHAR *v18; // rax
  char *FileW; // rax
  const WCHAR *v20; // rax
  const WCHAR *v21; // rax
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25[2]; // [rsp+40h] [rbp-108h] BYREF
  __int128 v26; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-E8h]
  LPCVOID v28; // [rsp+70h] [rbp-D8h]
  __int64 v29; // [rsp+78h] [rbp-D0h]
  __int64 v30; // [rsp+88h] [rbp-C0h]
  _BYTE v31[33]; // [rsp+90h] [rbp-B8h] BYREF
  __int16 v32; // [rsp+B1h] [rbp-97h]
  char v33; // [rsp+B3h] [rbp-95h]
  __int128 v34; // [rsp+B4h] [rbp-94h]
  __int64 v35; // [rsp+C4h] [rbp-84h]
  __int64 v36; // [rsp+CCh] [rbp-7Ch]
  int v37; // [rsp+D4h] [rbp-74h]
  int v38; // [rsp+E0h] [rbp-68h] BYREF
  char v39; // [rsp+E4h] [rbp-64h]
  __int64 v40; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v41; // [rsp+F0h] [rbp-58h]
  __m128i si128; // [rsp+F8h] [rbp-50h]

  v29 = a1;
  v30 = a4;
  v28 = a8;
  v25[0] = a9;
  v13 = archive_entry_filetype(a3);
  if ( v13 == 0x4000 )
  {
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    v26 = *a5;
    EnsureDirectory((__int64)&v38, v14, *(_QWORD *)(a4 + 16), &v26, a6);
    if ( v38 < 0 )
    {
LABEL_3:
      *(_DWORD *)a1 = v38;
      *(_BYTE *)(a1 + 4) = v39;
      *(_QWORD *)(a1 + 8) = v40;
      *(_QWORD *)(a1 + 16) = v41;
      *(__m128i *)(a1 + 24) = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v40) = 0;
      std::wstring::_Tidy_deallocate(&v40);
      return a1;
    }
    if ( a7 )
    {
      v26 = 0u;
      v27 = 0;
      v16 = (unsigned __int8)TryGetFileTimes(a3, &v26) != 0;
      v25[0] = 0;
      if ( (unsigned __int8)TryGetAttributes(a3, v25) )
        v16 |= 2u;
      if ( v16 )
      {
        std::wstring::wstring(v31, a4);
        v31[32] = v16;
        v32 = 0;
        v33 = 0;
        v34 = v26;
        v35 = v27;
        v36 = v25[0];
        v37 = 0;
        v17 = *(_QWORD *)(a7 + 8);
        if ( v17 == *(_QWORD *)(a7 + 16) )
        {
          std::vector<DeferredPropertyUpdates>::_Emplace_reallocate<DeferredPropertyUpdates>(
            a7,
            *(_QWORD *)(a7 + 8),
            v31);
        }
        else
        {
          DeferredPropertyUpdates::DeferredPropertyUpdates(v17, v31);
          *(_QWORD *)(a7 + 8) += 72LL;
        }
        std::wstring::_Tidy_deallocate(v31);
      }
    }
    else
    {
      v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      FileW = (char *)CreateFileW(v18, 0x100u, 7u, 0, 3u, 0x2000000u, 0);
      v25[0] = (__int64)FileW;
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        TryRestoreFileTimes_0(FileW);
      v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      TryRestoreAttributes_0(v20);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v25);
    }
    *(_DWORD *)a1 = v38;
    *(_BYTE *)(a1 + 4) = v39;
    *(_QWORD *)(a1 + 8) = v40;
    *(_QWORD *)(a1 + 16) = v41;
    *(__m128i *)(a1 + 24) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v40) = 0;
    std::wstring::_Tidy_deallocate(&v40);
    return a1;
  }
  else
  {
    *(_QWORD *)&v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    *((_QWORD *)&v26 + 1) = *(_QWORD *)(a4 + 16);
    split_filename(&v38, &v26);
    v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    v26 = *a5;
    EnsureDirectory((__int64)&v38, v21, v40, &v26, a6);
    if ( v38 < 0 )
      goto LABEL_3;
    std::wstring::_Tidy_deallocate(&v40);
    if ( ((v13 - 4096) & 0xAFFF) == 0 && v13 != 20480 )
      goto LABEL_22;
    if ( v13 != (__int16)0x8000 )
    {
      if ( v13 == -24576 )
      {
        ExtractSymbolicLink((char *)a1, a3, a4, a6);
        return a1;
      }
      if ( v13 == -16384 )
      {
LABEL_22:
        v22 = std::wstring::wstring(&v38, a4);
        LOBYTE(v23) = 8;
        ExtractResult::ExtractResult(a1, 2147942622LL, v23, v22);
        return a1;
      }
    }
    v24 = archive_entry_hardlink_w(a3);
    if ( v24 )
      ExtractHardLink(a1, (__int64)a3, a4, a6, v24);
    else
      ExtractRegularFile(a1, a2, (__int64)a3, a4, a6, v28, (ArchiveExtractProgress *)v25[0]);
    return a1;
  }
}

```

## disassembly

```asm
0x180064cec  push    rbx
0x180064cee  push    rsi
0x180064cef  push    rdi
0x180064cf0  push    r12
0x180064cf2  push    r13
0x180064cf4  push    r14
0x180064cf6  push    r15
0x180064cf8  sub     rsp, 110h
0x180064cff  mov     rax, cs:__security_cookie
0x180064d06  xor     rax, rsp
0x180064d09  mov     [rsp+148h+var_40], rax
0x180064d11  mov     rsi, r9
0x180064d14  mov     r14, r8
0x180064d17  mov     r13, rdx
0x180064d1a  mov     rdi, rcx
0x180064d1d  mov     [rsp+148h+var_D0], rcx
0x180064d22  mov     [rsp+148h+var_C0], r9
0x180064d2a  mov     r12, [rsp+148h+arg_20]
0x180064d32  mov     r15, [rsp+148h+arg_30]
0x180064d3a  mov     rax, [rsp+148h+arg_38]
0x180064d42  mov     [rsp+148h+var_D8], rax
0x180064d47  mov     rax, [rsp+148h+arg_40]
0x180064d4f  mov     [rsp+148h+var_108], rax
0x180064d54  mov     rcx, r8
0x180064d57  call    cs:__imp_archive_entry_filetype
0x180064d5d  movzx   ebx, ax
0x180064d60  mov     eax, 4000h
0x180064d65  mov     rcx, rsi
0x180064d68  cmp     bx, ax
0x180064d6b  jnz     loc_180064FFF
0x180064d71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180064d76  mov     rdx, rax
0x180064d79  movaps  xmm0, xmmword ptr [r12]
0x180064d7e  movdqa  [rsp+148h+var_F8], xmm0
0x180064d84  mov     al, [rsp+148h+arg_28]
0x180064d8b  mov     byte ptr [rsp+148h+dwCreationDisposition], al
0x180064d8f  lea     r9, [rsp+148h+var_F8]
0x180064d94  mov     r8, [rsi+10h]
0x180064d98  lea     rcx, [rsp+148h+var_68]
0x180064da0  call    EnsureDirectory
0x180064da5  nop
0x180064da6  mov     eax, [rsp+148h+var_68]
0x180064dad  xor     r12d, r12d
0x180064db0  test    eax, eax
0x180064db2  jns     short loc_180064E1F
0x180064db4  mov     [rdi], eax
0x180064db6  mov     al, [rsp+148h+var_64]
0x180064dbd  mov     [rdi+4], al
0x180064dc0  mov     rax, [rsp+148h+var_60]
0x180064dc8  mov     [rdi+8], rax
0x180064dcc  mov     rcx, [rsp+148h+var_58]
0x180064dd4  mov     [rdi+10h], rcx
0x180064dd8  mov     rcx, qword ptr [rsp+148h+var_50]
0x180064de0  mov     [rdi+18h], rcx
0x180064de4  mov     rcx, qword ptr [rsp+148h+var_50+8]
0x180064dec  mov     [rdi+20h], rcx
0x180064df0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180064df8  movdqu  [rsp+148h+var_50], xmm0
0x180064e01  mov     word ptr [rsp+148h+var_60], r12w
0x180064e0a  lea     rcx, [rsp+148h+var_60]
0x180064e12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064e17  mov     rax, rdi
0x180064e1a  jmp     loc_1800651B2
0x180064e1f  test    r15, r15
0x180064e22  jz      loc_180064F24
0x180064e28  movzx   ebx, r12b
0x180064e2c  xor     eax, eax
0x180064e2e  mov     qword ptr [rsp+148h+var_F8], rax
0x180064e33  mov     qword ptr [rsp+148h+var_F8+8], rax
0x180064e38  mov     [rsp+148h+var_E8], rax
0x180064e3d  lea     rdx, [rsp+148h+var_F8]
0x180064e42  mov     rcx, r14
0x180064e45  call    TryGetFileTimes
0x180064e4a  mov     ecx, 1
0x180064e4f  test    al, al
0x180064e51  cmovnz  ebx, ecx
0x180064e54  mov     [rsp+148h+var_108], r12
0x180064e59  lea     rdx, [rsp+148h+var_108]
0x180064e5e  mov     rcx, r14
0x180064e61  call    TryGetAttributes
0x180064e66  test    al, al
0x180064e68  jz      short loc_180064E6D
0x180064e6a  or      bl, 2
0x180064e6d  test    bl, bl
0x180064e6f  jz      loc_180064F8D
0x180064e75  mov     rdx, rsi
0x180064e78  lea     rcx, [rsp+148h+var_B8]
0x180064e80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180064e85  mov     [rsp+148h+var_98], bl
0x180064e8c  xor     eax, eax
0x180064e8e  mov     [rsp+148h+var_97], ax
0x180064e96  mov     [rsp+148h+var_95], al
0x180064e9d  mov     rax, qword ptr [rsp+148h+var_F8]
0x180064ea2  mov     qword ptr [rsp+148h+var_94], rax
0x180064eaa  mov     rax, qword ptr [rsp+148h+var_F8+8]
0x180064eaf  mov     qword ptr [rsp+148h+var_94+8], rax
0x180064eb7  mov     rax, [rsp+148h+var_E8]
0x180064ebc  mov     [rsp+148h+var_84], rax
0x180064ec4  mov     eax, dword ptr [rsp+148h+var_108]
0x180064ec8  mov     dword ptr [rsp+148h+var_7C], eax
0x180064ecf  mov     eax, dword ptr [rsp+148h+var_108+4]
0x180064ed3  mov     dword ptr [rsp+148h+var_7C+4], eax
0x180064eda  xor     eax, eax
0x180064edc  mov     [rsp+148h+var_74], eax
0x180064ee3  mov     rcx, [r15+8]
0x180064ee7  cmp     rcx, [r15+10h]
0x180064eeb  jz      short loc_180064F01
0x180064eed  lea     rdx, [rsp+148h+var_B8]
0x180064ef5  call    ??0DeferredPropertyUpdates@@QEAA@$$QEAU0@@Z; DeferredPropertyUpdates::DeferredPropertyUpdates(DeferredPropertyUpdates &&)
0x180064efa  add     qword ptr [r15+8], 48h ; 'H'
0x180064eff  jmp     short loc_180064F15
0x180064f01  lea     r8, [rsp+148h+var_B8]
0x180064f09  mov     rdx, rcx
0x180064f0c  mov     rcx, r15
0x180064f0f  call    ??$_Emplace_reallocate@UDeferredPropertyUpdates@@@?$vector@UDeferredPropertyUpdates@@V?$allocator@UDeferredPropertyUpdates@@@std@@@std@@AEAAPEAUDeferredPropertyUpdates@@QEAU2@$$QEAU2@@Z; std::vector<DeferredPropertyUpdates>::_Emplace_reallocate<DeferredPropertyUpdates>(DeferredPropertyUpdates * const,DeferredPropertyUpdates &&)
0x180064f14  nop
0x180064f15  lea     rcx, [rsp+148h+var_B8]
0x180064f1d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064f22  jmp     short loc_180064F8D
0x180064f24  mov     rcx, rsi
0x180064f27  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180064f2c  mov     [rsp+148h+hTemplateFile], r12; hTemplateFile
0x180064f31  mov     [rsp+148h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180064f39  mov     [rsp+148h+dwCreationDisposition], 3; dwCreationDisposition
0x180064f41  xor     r9d, r9d; lpSecurityAttributes
0x180064f44  mov     edx, 100h; dwDesiredAccess
0x180064f49  lea     r8d, [r9+7]; dwShareMode
0x180064f4d  mov     rcx, rax; lpFileName
0x180064f50  call    cs:__imp_CreateFileW
0x180064f56  mov     [rsp+148h+var_108], rax
0x180064f5b  lea     rcx, [rax-1]
0x180064f5f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180064f63  ja      short loc_180064F70
0x180064f65  mov     rdx, r14
0x180064f68  mov     rcx, rax; hFile
0x180064f6b  call    TryRestoreFileTimes_0
0x180064f70  mov     rcx, rsi
0x180064f73  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180064f78  mov     rdx, r14
0x180064f7b  mov     rcx, rax; lpFileName
0x180064f7e  call    TryRestoreAttributes_0
0x180064f83  lea     rcx, [rsp+148h+var_108]
0x180064f88  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180064f8d  mov     eax, [rsp+148h+var_68]
0x180064f94  mov     [rdi], eax
0x180064f96  mov     al, [rsp+148h+var_64]
0x180064f9d  mov     [rdi+4], al
0x180064fa0  mov     rax, [rsp+148h+var_60]
0x180064fa8  mov     [rdi+8], rax
0x180064fac  mov     rax, [rsp+148h+var_58]
0x180064fb4  mov     [rdi+10h], rax
0x180064fb8  mov     rax, qword ptr [rsp+148h+var_50]
0x180064fc0  mov     [rdi+18h], rax
0x180064fc4  mov     rax, qword ptr [rsp+148h+var_50+8]
0x180064fcc  mov     [rdi+20h], rax
0x180064fd0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180064fd8  movdqu  [rsp+148h+var_50], xmm0
0x180064fe1  mov     word ptr [rsp+148h+var_60], r12w
0x180064fea  lea     rcx, [rsp+148h+var_60]
0x180064ff2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064ff7  mov     rax, rdi
0x180064ffa  jmp     loc_1800651B2
0x180064fff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065004  mov     qword ptr [rsp+148h+var_F8], rax
0x180065009  mov     rax, [rsi+10h]
0x18006500d  mov     qword ptr [rsp+148h+var_F8+8], rax
0x180065012  lea     rdx, [rsp+148h+var_F8]
0x180065017  lea     rcx, [rsp+148h+var_68]
0x18006501f  call    ?split_filename@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_filename(std::basic_string_view<ushort>)
0x180065024  mov     rcx, rsi
0x180065027  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006502c  movaps  xmm0, xmmword ptr [r12]
0x180065031  movdqa  [rsp+148h+var_F8], xmm0
0x180065037  mov     r15b, [rsp+148h+arg_28]
0x18006503f  mov     byte ptr [rsp+148h+dwCreationDisposition], r15b
0x180065044  lea     r9, [rsp+148h+var_F8]
0x180065049  mov     r8, [rsp+148h+var_60]
0x180065051  mov     rdx, rax
0x180065054  lea     rcx, [rsp+148h+var_68]
0x18006505c  call    EnsureDirectory
0x180065061  mov     eax, [rsp+148h+var_68]
0x180065068  lea     rcx, [rsp+148h+var_60]
0x180065070  test    eax, eax
0x180065072  jns     short loc_1800650D8
0x180065074  mov     [rdi], eax
0x180065076  mov     al, [rsp+148h+var_64]
0x18006507d  mov     [rdi+4], al
0x180065080  mov     rax, [rsp+148h+var_60]
0x180065088  mov     [rdi+8], rax
0x18006508c  mov     rax, [rsp+148h+var_58]
0x180065094  mov     [rdi+10h], rax
0x180065098  mov     rax, qword ptr [rsp+148h+var_50]
0x1800650a0  mov     [rdi+18h], rax
0x1800650a4  mov     rax, qword ptr [rsp+148h+var_50+8]
0x1800650ac  mov     [rdi+20h], rax
0x1800650b0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800650b8  movdqu  [rsp+148h+var_50], xmm0
0x1800650c1  xor     eax, eax
0x1800650c3  mov     word ptr [rsp+148h+var_60], ax
0x1800650cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800650d0  mov     rax, rdi
0x1800650d3  jmp     loc_1800651B2
0x1800650d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800650dd  mov     ecx, 1000h
0x1800650e2  movzx   eax, bx
0x1800650e5  sub     ax, cx
0x1800650e8  mov     ecx, 0AFFFh
0x1800650ed  test    cx, ax
0x1800650f0  jnz     short loc_1800650FC
0x1800650f2  mov     eax, 5000h
0x1800650f7  cmp     bx, ax
0x1800650fa  jnz     short loc_18006511A
0x1800650fc  mov     eax, 8000h
0x180065101  cmp     bx, ax
0x180065104  jz      short loc_180065158
0x180065106  mov     eax, 0A000h
0x18006510b  cmp     bx, ax
0x18006510e  jz      short loc_180065142
0x180065110  mov     eax, 0C000h
0x180065115  cmp     bx, ax
0x180065118  jnz     short loc_180065158
0x18006511a  mov     rdx, rsi
0x18006511d  lea     rcx, [rsp+148h+var_68]
0x180065125  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006512a  mov     r9, rax
0x18006512d  mov     r8b, 8
0x180065130  mov     edx, 800700DEh
0x180065135  mov     rcx, rdi
0x180065138  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x18006513d  mov     rax, rdi
0x180065140  jmp     short loc_1800651B2
0x180065142  mov     r9b, r15b
0x180065145  mov     r8, rsi
0x180065148  mov     rdx, r14
0x18006514b  mov     rcx, rdi
0x18006514e  call    ExtractSymbolicLink
0x180065153  mov     rax, rdi
0x180065156  jmp     short loc_1800651B2
0x180065158  mov     rcx, r14
0x18006515b  call    cs:__imp_archive_entry_hardlink_w
0x180065161  mov     rcx, rdi; int
0x180065164  test    rax, rax
0x180065167  jz      short loc_180065181
0x180065169  mov     qword ptr [rsp+148h+dwCreationDisposition], rax
0x18006516e  mov     r9b, r15b
0x180065171  mov     r8, rsi
0x180065174  mov     rdx, r14
0x180065177  call    ExtractHardLink
0x18006517c  mov     rax, rdi
0x18006517f  jmp     short loc_1800651B2
0x180065181  mov     rax, [rsp+148h+var_108]
0x180065186  mov     [rsp+148h+hTemplateFile], rax; __int64
0x18006518b  mov     rax, [rsp+148h+var_D8]
0x180065190  mov     qword ptr [rsp+148h+dwFlagsAndAttributes], rax; LPCVOID
0x180065195  mov     byte ptr [rsp+148h+dwCreationDisposition], r15b; char
0x18006519a  mov     r9, rsi; int
0x18006519d  mov     r8, r14; int
0x1800651a0  mov     rdx, r13; int
0x1800651a3  call    ExtractRegularFile
0x1800651a8  mov     rax, rdi
0x1800651ab  jmp     short loc_1800651B2
0x1800651ad  mov     rax, [rsp+148h+var_D0]
0x1800651b2  mov     rcx, [rsp+148h+var_40]
0x1800651ba  xor     rcx, rsp; StackCookie
0x1800651bd  call    __security_check_cookie
0x1800651c2  add     rsp, 110h
0x1800651c9  pop     r15
0x1800651cb  pop     r14
0x1800651cd  pop     r13
0x1800651cf  pop     r12
0x1800651d1  pop     rdi
0x1800651d2  pop     rsi
0x1800651d3  pop     rbx
0x1800651d4  retn
```
