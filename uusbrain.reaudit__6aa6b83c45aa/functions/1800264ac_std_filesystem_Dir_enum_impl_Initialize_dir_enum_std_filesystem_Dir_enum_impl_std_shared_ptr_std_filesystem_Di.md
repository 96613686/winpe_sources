# std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(std::shared_ptr<std::filesystem::_Dir_enum_impl> &,std::filesystem::path const &,std::filesystem::directory_options)

- ea: `0x1800264ac`
- end: `0x180026640`
- name: `??$_Initialize_dir_enum@U_Dir_enum_impl@filesystem@std@@@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@2@AEBVpath@12@W4directory_options@12@@Z`
- size: `404`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18000b024`
- `0x18000cf18`
- `0x18000ecdc`
- `0x1800250d0`

## callees

- `0x18002603c`
- `0x180026408`
- `0x1800264ac`
- `0x180029644`
- `0x180042640`
- `0x1800427d0`
- `0x180042bfc`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800265fe`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800265fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(
        std::filesystem::_Dir_enum_impl **a1,
        __int64 a2)
{
  char *v3; // r14
  std::filesystem::_Dir_enum_impl *v4; // rsi
  _OWORD *v5; // rbx
  HANDLE v6; // rax
  volatile signed __int32 *v7; // rbx
  unsigned int v8; // ebx
  __int128 v10; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+40h] [rbp-C0h]
  HANDLE hFindFile; // [rsp+50h] [rbp-B0h]
  _BYTE v13[596]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v14; // [rsp+2ACh] [rbp+1ACh]

  std::filesystem::_Dir_enum_impl::_Creator::_Creator(&v10, a2, 0);
  if ( v13[592] )
  {
    v3 = (char *)operator new(0x58u);
    *(_OWORD *)v3 = 0;
    *((_DWORD *)v3 + 2) = 1;
    *((_DWORD *)v3 + 3) = 1;
    *(_QWORD *)v3 = &std::_Ref_count_obj2<std::filesystem::_Dir_enum_impl>::`vftable';
    v4 = (std::filesystem::_Dir_enum_impl *)(v3 + 16);
    *((_OWORD *)v3 + 1) = 0;
    *((_OWORD *)v3 + 2) = 0;
    v5 = v3 + 48;
    *((_OWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 9) = 7;
    *((_WORD *)v3 + 24) = 0;
    v6 = hFindFile;
    hFindFile = (HANDLE)-1LL;
    *((_QWORD *)v3 + 10) = v6;
    if ( v3 + 48 != (char *)&v10 )
    {
      std::wstring::_Tidy_deallocate(v5);
      *v5 = v10;
      *((_OWORD *)v3 + 4) = v11;
      *(_QWORD *)&v11 = 0;
      *((_QWORD *)&v11 + 1) = 7;
      LOWORD(v10) = 0;
    }
    std::filesystem::_Dir_enum_impl::_Refresh(v4, (const struct __std_fs_find_data *)v13);
    *a1 = v4;
    v7 = (volatile signed __int32 *)a1[1];
    a1[1] = (std::filesystem::_Dir_enum_impl *)v3;
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
  }
  v8 = v14;
  if ( hFindFile != (HANDLE)-1LL && !FindClose(hFindFile) )
    abort();
  std::wstring::_Tidy_deallocate(&v10);
  return v8;
}

```

## disassembly

```asm
0x1800264ac  mov     [rsp-8+arg_10], rbx
0x1800264b1  push    rbp
0x1800264b2  push    rsi
0x1800264b3  push    rdi
0x1800264b4  push    r12
0x1800264b6  push    r14
0x1800264b8  lea     rbp, [rsp-1C0h]
0x1800264c0  sub     rsp, 2C0h
0x1800264c7  mov     rax, cs:__security_cookie
0x1800264ce  xor     rax, rsp
0x1800264d1  mov     [rbp+1E0h+var_30], rax
0x1800264d8  mov     rdi, rcx
0x1800264db  xor     r12d, r12d
0x1800264de  xor     r8d, r8d
0x1800264e1  lea     rcx, [rsp+2E0h+var_2B0]
0x1800264e6  call    ??0_Creator@_Dir_enum_impl@filesystem@std@@QEAA@AEBVpath@23@W4directory_options@23@@Z; std::filesystem::_Dir_enum_impl::_Creator::_Creator(std::filesystem::path const &,std::filesystem::directory_options)
0x1800264eb  nop
0x1800264ec  cmp     [rbp+1E0h+var_38], r12b
0x1800264f3  jz      loc_1800265ED
0x1800264f9  lea     ecx, [r12+58h]; Size
0x1800264fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026503  mov     r14, rax
0x180026506  mov     [rsp+2E0h+var_2C0], rax
0x18002650b  xorps   xmm0, xmm0
0x18002650e  movups  xmmword ptr [rax], xmm0
0x180026511  lea     eax, [r12+1]
0x180026516  mov     [r14+8], eax
0x18002651a  mov     [r14+0Ch], eax
0x18002651e  lea     rax, ??_7?$_Ref_count_obj2@U_Dir_enum_impl@filesystem@std@@@std@@6B@; const std::_Ref_count_obj2<std::filesystem::_Dir_enum_impl>::`vftable'
0x180026525  mov     [r14], rax
0x180026528  lea     rsi, [r14+10h]
0x18002652c  mov     [rsp+2E0h+var_2B8], rsi
0x180026531  movups  xmmword ptr [rsi], xmm0
0x180026534  movups  xmmword ptr [rsi+10h], xmm0
0x180026538  lea     rbx, [rsi+20h]
0x18002653c  movups  xmmword ptr [rbx], xmm0
0x18002653f  mov     [rbx+10h], r12
0x180026543  mov     qword ptr [rbx+18h], 7
0x18002654b  mov     [rbx], r12w
0x18002654f  mov     rax, [rsp+2E0h+hFindFile]
0x180026554  mov     [rsp+2E0h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18002655d  mov     [rsi+40h], rax
0x180026561  lea     rax, [rsp+2E0h+var_2B0]
0x180026566  cmp     rbx, rax
0x180026569  jz      short loc_180026598
0x18002656b  mov     rcx, rbx
0x18002656e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026573  movaps  xmm0, [rsp+2E0h+var_2B0]
0x180026578  movups  xmmword ptr [rbx], xmm0
0x18002657b  movaps  xmm1, [rsp+2E0h+var_2A0]
0x180026580  movups  xmmword ptr [rbx+10h], xmm1
0x180026584  mov     qword ptr [rsp+2E0h+var_2A0], r12
0x180026589  mov     qword ptr [rsp+2E0h+var_2A0+8], 7
0x180026592  mov     word ptr [rsp+2E0h+var_2B0], r12w
0x180026598  lea     rdx, [rsp+2E0h+var_288]; struct __std_fs_find_data *
0x18002659d  mov     rcx, rsi; this
0x1800265a0  call    ?_Refresh@_Dir_enum_impl@filesystem@std@@QEAAXAEBU__std_fs_find_data@@@Z; std::filesystem::_Dir_enum_impl::_Refresh(__std_fs_find_data const &)
0x1800265a5  nop
0x1800265a6  mov     [rdi], rsi
0x1800265a9  mov     rbx, [rdi+8]
0x1800265ad  mov     [rdi+8], r14
0x1800265b1  test    rbx, rbx
0x1800265b4  jz      short loc_1800265ED
0x1800265b6  or      eax, 0FFFFFFFFh
0x1800265b9  lock xadd [rbx+8], eax
0x1800265be  cmp     eax, 1
0x1800265c1  jnz     short loc_1800265ED
0x1800265c3  mov     rax, [rbx]
0x1800265c6  mov     rcx, rbx
0x1800265c9  mov     rax, [rax]
0x1800265cc  call    _guard_dispatch_icall
0x1800265d1  or      eax, 0FFFFFFFFh
0x1800265d4  lock xadd [rbx+0Ch], eax
0x1800265d9  cmp     eax, 1
0x1800265dc  jnz     short loc_1800265ED
0x1800265de  mov     rax, [rbx]
0x1800265e1  mov     rcx, rbx
0x1800265e4  mov     rax, [rax+8]
0x1800265e8  call    _guard_dispatch_icall
0x1800265ed  mov     ebx, [rbp+1E0h+var_34]
0x1800265f3  mov     rcx, [rsp+2E0h+hFindFile]; hFindFile
0x1800265f8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800265fc  jz      short loc_180026608
0x1800265fe  call    cs:__imp_FindClose
0x180026604  test    eax, eax
0x180026606  jz      short loc_18002663A
0x180026608  lea     rcx, [rsp+2E0h+var_2B0]
0x18002660d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026612  mov     eax, ebx
0x180026614  mov     rcx, [rbp+1E0h+var_30]
0x18002661b  xor     rcx, rsp; StackCookie
0x18002661e  call    __security_check_cookie
0x180026623  mov     rbx, [rsp+2E0h+arg_10]
0x18002662b  add     rsp, 2C0h
0x180026632  pop     r14
0x180026634  pop     r12
0x180026636  pop     rdi
0x180026637  pop     rsi
0x180026638  pop     rbp
0x180026639  retn
0x18002663a  call    abort
```
