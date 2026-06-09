# std::filesystem::_Remove_all_dir(std::filesystem::path const &,std::error_code &,unsigned __int64 &)

- ea: `0x1800641c4`
- end: `0x1800644fc`
- name: `?_Remove_all_dir@filesystem@std@@YAXAEBVpath@12@AEAVerror_code@2@AEA_K@Z`
- size: `824`
- prototype: `void(std::filesystem *__hidden this, const struct std::filesystem::path *, struct std::error_code *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180039da4`
- `0x1800641c4`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x1800640a4`
- `0x1800641c4`
- `0x1800648e4`
- `0x180065084`
- `0x180065408`
- `0x18007a150`
- `0x18008fc40`
- `0x18008fe00`
- `0x180095af0`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800642d2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800642d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall std::filesystem::_Remove_all_dir(
        std::filesystem *this,
        const struct std::filesystem::path *a2,
        struct std::error_code *a3,
        unsigned __int64 *a4)
{
  int v7; // edi
  int v8; // esi
  char v9; // al
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // r15
  int v12; // edx
  _QWORD *v13; // rbx
  unsigned __int64 *v14; // r9
  __int64 v15; // rax
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  std::filesystem *v21; // rcx
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rax
  __int128 v24; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v26; // [rsp+40h] [rbp-C0h]
  __int128 v27; // [rsp+50h] [rbp-B0h]
  _BYTE v28[32]; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hFindFile; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[593]; // [rsp+88h] [rbp-78h] BYREF
  __int16 v31; // [rsp+2D9h] [rbp+1D9h]
  char v32; // [rsp+2DBh] [rbp+1DBh]
  int v33; // [rsp+2DCh] [rbp+1DCh]

  v7 = 0;
  v24 = 0;
  std::wstring::wstring((__int64)v28, (__int64)this);
  hFindFile = (HANDLE)-1LL;
  v8 = std::filesystem::_Dir_enum_impl::_Open_dir(v28, 0, &hFindFile, v30);
  if ( !v8 )
  {
    v9 = 1;
LABEL_3:
    v8 = 0;
    v33 = 0;
    goto LABEL_6;
  }
  v9 = 0;
  if ( v8 == 18 )
    goto LABEL_3;
  v33 = v8;
LABEL_6:
  v30[592] = v9;
  v31 = 0;
  v32 = 0;
  if ( v9 )
  {
    v10 = (volatile signed __int32 *)operator new(0x58u);
    *(_QWORD *)&v25 = v10;
    *(_OWORD *)v10 = 0;
    *((_DWORD *)v10 + 2) = 1;
    *((_DWORD *)v10 + 3) = 1;
    *(_QWORD *)v10 = &std::_Ref_count_obj2<std::filesystem::_Dir_enum_impl>::`vftable';
    v11 = v10 + 4;
    std::filesystem::_Dir_enum_impl::_Dir_enum_impl((std::filesystem::_Dir_enum_impl *)(v10 + 4), (__int64)v28);
    *(_QWORD *)&v24 = v10 + 4;
    *((_QWORD *)&v24 + 1) = v10;
    v8 = v33;
  }
  else
  {
    v10 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    v11 = (volatile signed __int32 *)v24;
  }
  if ( hFindFile != (HANDLE)-1LL && !FindClose(hFindFile) )
    abort();
  std::wstring::~wstring((__int64)v28);
  LODWORD(v25) = v8;
  *((_QWORD *)&v25 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  *(_OWORD *)a2 = v25;
  v12 = *(_DWORD *)a2;
  if ( !*(_DWORD *)a2 )
  {
    while ( v11 )
    {
      v13 = v11 + 8;
      std::filesystem::directory_entry::_Get_any_status(v11, &v25, 6);
      LODWORD(v27) = DWORD2(v25);
      *((_QWORD *)&v27 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
      *(_OWORD *)a2 = v27;
      if ( *(_DWORD *)a2 )
        goto LABEL_40;
      if ( (_DWORD)v25 == 3 )
      {
        std::filesystem::_Remove_all_dir((std::filesystem *)(v11 + 8), a2, a3, v14);
      }
      else
      {
        if ( *((_QWORD *)v11 + 7) > 7u )
          v13 = (_QWORD *)*v13;
        v15 = _std_fs_remove((__int64)v13);
        LODWORD(v26) = HIDWORD(v15);
        *((_QWORD *)&v26 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        *(_OWORD *)a2 = v26;
        *(_QWORD *)a3 += (unsigned __int8)v15;
      }
      if ( *(_DWORD *)a2 )
      {
LABEL_40:
        v10 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
        goto LABEL_41;
      }
      std::filesystem::directory_iterator::increment((std::filesystem::directory_iterator *)&v24, a2);
      v12 = *(_DWORD *)a2;
      if ( *(_DWORD *)a2 )
      {
        v10 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
        goto LABEL_23;
      }
      v11 = (volatile signed __int32 *)v24;
    }
    v10 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    goto LABEL_30;
  }
LABEL_23:
  if ( *(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL) == qword_1801824F0 )
  {
    v16 = v12 - 2;
    if ( !v16
      || (v17 = v16 - 1) == 0
      || (v18 = v17 - 50) == 0
      || (v19 = v18 - 11) == 0
      || (v20 = v19 - 59) == 0
      || v20 == 144 )
    {
LABEL_30:
      if ( v10 )
      {
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      do
      {
        v21 = this;
        if ( *((_QWORD *)this + 3) > 7u )
          v21 = *(std::filesystem **)this;
        v22 = _std_fs_remove((__int64)v21);
        *(_QWORD *)a3 += (unsigned __int8)v22;
        v23 = HIDWORD(v22);
        LODWORD(v26) = v23;
        *((_QWORD *)&v26 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        *(_OWORD *)a2 = v26;
        if ( (_DWORD)v23 != 145 && (_DWORD)v23 != 5 )
          break;
        ++v7;
      }
      while ( v7 < 10 );
      return;
    }
  }
LABEL_41:
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
}

```

## disassembly

```asm
0x1800641c4  mov     [rsp-8+arg_18], rbx
0x1800641c9  push    rbp
0x1800641ca  push    rsi
0x1800641cb  push    rdi
0x1800641cc  push    r12
0x1800641ce  push    r13
0x1800641d0  push    r14
0x1800641d2  push    r15
0x1800641d4  lea     rbp, [rsp-1F0h]
0x1800641dc  sub     rsp, 2F0h
0x1800641e3  mov     rax, cs:__security_cookie
0x1800641ea  xor     rax, rsp
0x1800641ed  mov     [rbp+220h+var_40], rax
0x1800641f4  mov     r12, r8
0x1800641f7  mov     r14, rdx
0x1800641fa  mov     r13, rcx
0x1800641fd  xor     edi, edi
0x1800641ff  xorps   xmm1, xmm1
0x180064202  movdqu  [rsp+320h+var_300], xmm1
0x180064208  mov     rdx, rcx
0x18006420b  lea     rcx, [rsp+320h+var_2C0]
0x180064210  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180064215  nop
0x180064216  mov     [rbp+220h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18006421e  lea     r9, [rbp+220h+var_298]
0x180064222  lea     r8, [rbp+220h+hFindFile]
0x180064226  xor     edx, edx
0x180064228  lea     rcx, [rsp+320h+var_2C0]
0x18006422d  call    ?_Open_dir@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAVpath@23@W4directory_options@23@AEAU_Find_file_handle@23@AEAU__std_fs_find_data@@@Z; std::filesystem::_Dir_enum_impl::_Open_dir(std::filesystem::path &,std::filesystem::directory_options,std::filesystem::_Find_file_handle &,__std_fs_find_data &)
0x180064232  mov     esi, eax
0x180064234  lea     r15d, [rdi+1]
0x180064238  test    eax, eax
0x18006423a  jnz     short loc_180064249
0x18006423c  mov     al, r15b
0x18006423f  mov     esi, edi
0x180064241  mov     [rbp+220h+var_44], edi
0x180064247  jmp     short loc_180064257
0x180064249  mov     al, dil
0x18006424c  cmp     esi, 12h
0x18006424f  jz      short loc_18006423F
0x180064251  mov     [rbp+220h+var_44], esi
0x180064257  xor     ecx, ecx
0x180064259  mov     [rbp+220h+var_48], al
0x18006425f  mov     [rbp+220h+var_47], cx
0x180064266  mov     [rbp+220h+var_45], cl
0x18006426c  test    al, al
0x18006426e  jz      short loc_1800642BE
0x180064270  mov     ecx, 58h ; 'X'; Size
0x180064275  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006427a  mov     rbx, rax
0x18006427d  mov     qword ptr [rsp+320h+var_2F0], rax
0x180064282  xorps   xmm0, xmm0
0x180064285  movups  xmmword ptr [rax], xmm0
0x180064288  mov     [rax+8], r15d
0x18006428c  mov     [rax+0Ch], r15d
0x180064290  lea     rax, ??_7?$_Ref_count_obj2@U_Dir_enum_impl@filesystem@std@@@std@@6B@; const std::_Ref_count_obj2<std::filesystem::_Dir_enum_impl>::`vftable'
0x180064297  mov     [rbx], rax
0x18006429a  lea     r15, [rbx+10h]
0x18006429e  lea     rdx, [rsp+320h+var_2C0]
0x1800642a3  mov     rcx, r15; this
0x1800642a6  call    ??0_Dir_enum_impl@filesystem@std@@QEAA@$$QEAU_Creator@012@W4directory_options@12@@Z; std::filesystem::_Dir_enum_impl::_Dir_enum_impl(std::filesystem::_Dir_enum_impl::_Creator &&,std::filesystem::directory_options)
0x1800642ab  nop
0x1800642ac  mov     qword ptr [rsp+320h+var_300], r15
0x1800642b1  mov     qword ptr [rsp+320h+var_300+8], rbx
0x1800642b6  mov     esi, [rbp+220h+var_44]
0x1800642bc  jmp     short loc_1800642C8
0x1800642be  mov     rbx, qword ptr [rsp+320h+var_300+8]
0x1800642c3  mov     r15, qword ptr [rsp+320h+var_300]
0x1800642c8  mov     rcx, [rbp+220h+hFindFile]; hFindFile
0x1800642cc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800642d0  jz      short loc_1800642E0
0x1800642d2  call    cs:__imp_FindClose
0x1800642d8  test    eax, eax
0x1800642da  jz      loc_1800644F6
0x1800642e0  lea     rcx, [rsp+320h+var_2C0]
0x1800642e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800642ea  mov     dword ptr [rsp+320h+var_2F0], esi
0x1800642ee  lea     rsi, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800642f5  mov     qword ptr [rsp+320h+var_2F0+8], rsi
0x1800642fa  movups  xmm0, [rsp+320h+var_2F0]
0x1800642ff  movdqu  xmmword ptr [r14], xmm0
0x180064304  mov     edx, [r14]
0x180064307  test    edx, edx
0x180064309  jnz     loc_1800643C5
0x18006430f  test    r15, r15
0x180064312  jz      loc_1800644EC
0x180064318  lea     rbx, [r15+20h]
0x18006431c  mov     r8d, 6
0x180064322  lea     rdx, [rsp+320h+var_2F0]
0x180064327  mov     rcx, r15
0x18006432a  call    ?_Get_any_status@directory_entry@filesystem@std@@AEBA?AU_File_status_and_error@23@W4__std_fs_stats_flags@@@Z; std::filesystem::directory_entry::_Get_any_status(__std_fs_stats_flags)
0x18006432f  mov     eax, dword ptr [rsp+320h+var_2F0+8]
0x180064333  mov     dword ptr [rsp+320h+var_2D0], eax
0x180064337  mov     qword ptr [rsp+320h+var_2D0+8], rsi
0x18006433c  movups  xmm0, [rsp+320h+var_2D0]
0x180064341  movdqu  xmmword ptr [r14], xmm0
0x180064346  cmp     [r14], edi
0x180064349  jnz     loc_180064481
0x18006434f  cmp     dword ptr [rsp+320h+var_2F0], 3
0x180064354  jnz     short loc_180064366
0x180064356  mov     r8, r12; struct std::error_code *
0x180064359  mov     rdx, r14; struct std::filesystem::path *
0x18006435c  mov     rcx, rbx; this
0x18006435f  call    ?_Remove_all_dir@filesystem@std@@YAXAEBVpath@12@AEAVerror_code@2@AEA_K@Z; std::filesystem::_Remove_all_dir(std::filesystem::path const &,std::error_code &,unsigned __int64 &)
0x180064364  jmp     short loc_180064399
0x180064366  cmp     qword ptr [rbx+18h], 7
0x18006436b  jbe     short loc_180064370
0x18006436d  mov     rbx, [rbx]
0x180064370  mov     rcx, rbx
0x180064373  call    __std_fs_remove
0x180064378  mov     rcx, rax
0x18006437b  shr     rcx, 20h
0x18006437f  mov     dword ptr [rsp+320h+var_2E0], ecx
0x180064383  mov     qword ptr [rsp+320h+var_2E0+8], rsi
0x180064388  movups  xmm0, [rsp+320h+var_2E0]
0x18006438d  movdqu  xmmword ptr [r14], xmm0
0x180064392  movzx   ecx, al
0x180064395  add     [r12], rcx
0x180064399  cmp     [r14], edi
0x18006439c  jnz     loc_180064481
0x1800643a2  mov     rdx, r14; struct std::error_code *
0x1800643a5  lea     rcx, [rsp+320h+var_300]; this
0x1800643aa  call    ?increment@directory_iterator@filesystem@std@@QEAAAEAV123@AEAVerror_code@3@@Z; std::filesystem::directory_iterator::increment(std::error_code &)
0x1800643af  mov     edx, [r14]
0x1800643b2  test    edx, edx
0x1800643b4  jnz     short loc_1800643C0
0x1800643b6  mov     r15, qword ptr [rsp+320h+var_300]
0x1800643bb  jmp     loc_18006430F
0x1800643c0  mov     rbx, qword ptr [rsp+320h+var_300+8]
0x1800643c5  mov     rcx, [r14+8]
0x1800643c9  mov     rax, cs:qword_1801824F0
0x1800643d0  cmp     [rcx+8], rax
0x1800643d4  jnz     loc_180064486
0x1800643da  sub     edx, 2
0x1800643dd  jz      short loc_1800643FF
0x1800643df  sub     edx, 1
0x1800643e2  jz      short loc_1800643FF
0x1800643e4  sub     edx, 32h ; '2'
0x1800643e7  jz      short loc_1800643FF
0x1800643e9  sub     edx, 0Bh
0x1800643ec  jz      short loc_1800643FF
0x1800643ee  sub     edx, 3Bh ; ';'
0x1800643f1  jz      short loc_1800643FF
0x1800643f3  cmp     edx, 90h
0x1800643f9  jnz     loc_180064486
0x1800643ff  test    rbx, rbx
0x180064402  jz      short loc_18006443B
0x180064404  or      eax, 0FFFFFFFFh
0x180064407  lock xadd [rbx+8], eax
0x18006440c  cmp     eax, 1
0x18006440f  jnz     short loc_18006443B
0x180064411  mov     rax, [rbx]
0x180064414  mov     rcx, rbx
0x180064417  mov     rax, [rax]
0x18006441a  call    _guard_dispatch_icall
0x18006441f  or      eax, 0FFFFFFFFh
0x180064422  lock xadd [rbx+0Ch], eax
0x180064427  cmp     eax, 1
0x18006442a  jnz     short loc_18006443B
0x18006442c  mov     rax, [rbx]
0x18006442f  mov     rcx, rbx
0x180064432  mov     rax, [rax+8]
0x180064436  call    _guard_dispatch_icall
0x18006443b  mov     rcx, r13
0x18006443e  cmp     qword ptr [r13+18h], 7
0x180064443  jbe     short loc_180064449
0x180064445  mov     rcx, [r13+0]
0x180064449  call    __std_fs_remove
0x18006444e  movzx   ecx, al
0x180064451  add     [r12], rcx
0x180064455  shr     rax, 20h
0x180064459  mov     dword ptr [rsp+320h+var_2E0], eax
0x18006445d  mov     qword ptr [rsp+320h+var_2E0+8], rsi
0x180064462  movups  xmm0, [rsp+320h+var_2E0]
0x180064467  movdqu  xmmword ptr [r14], xmm0
0x18006446c  cmp     eax, 91h
0x180064471  jz      short loc_180064478
0x180064473  cmp     eax, 5
0x180064476  jnz     short loc_1800644C2
0x180064478  inc     edi
0x18006447a  cmp     edi, 0Ah
0x18006447d  jl      short loc_18006443B
0x18006447f  jmp     short loc_1800644C2
0x180064481  mov     rbx, qword ptr [rsp+320h+var_300+8]
0x180064486  test    rbx, rbx
0x180064489  jz      short loc_1800644C2
0x18006448b  or      eax, 0FFFFFFFFh
0x18006448e  lock xadd [rbx+8], eax
0x180064493  cmp     eax, 1
0x180064496  jnz     short loc_1800644C2
0x180064498  mov     rax, [rbx]
0x18006449b  mov     rcx, rbx
0x18006449e  mov     rax, [rax]
0x1800644a1  call    _guard_dispatch_icall
0x1800644a6  or      eax, 0FFFFFFFFh
0x1800644a9  lock xadd [rbx+0Ch], eax
0x1800644ae  cmp     eax, 1
0x1800644b1  jnz     short loc_1800644C2
0x1800644b3  mov     rax, [rbx]
0x1800644b6  mov     rcx, rbx
0x1800644b9  mov     rax, [rax+8]
0x1800644bd  call    _guard_dispatch_icall
0x1800644c2  mov     rcx, [rbp+220h+var_40]
0x1800644c9  xor     rcx, rsp; StackCookie
0x1800644cc  call    __security_check_cookie
0x1800644d1  mov     rbx, [rsp+320h+arg_18]
0x1800644d9  add     rsp, 2F0h
0x1800644e0  pop     r15
0x1800644e2  pop     r14
0x1800644e4  pop     r13
0x1800644e6  pop     r12
0x1800644e8  pop     rdi
0x1800644e9  pop     rsi
0x1800644ea  pop     rbp
0x1800644eb  retn
0x1800644ec  mov     rbx, qword ptr [rsp+320h+var_300+8]
0x1800644f1  jmp     loc_1800643FF
0x1800644f6  call    abort
```
