# CFileTypesManager::Save(void)

- ea: `0x1800106a4`
- end: `0x180010b43`
- name: `?Save@CFileTypesManager@@QEAAJXZ`
- size: `1183`
- prototype: `__int64 __fastcall(CFileTypesManager *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800118b4`

## callees

- `0x180004fdc`
- `0x180005cc0`
- `0x180006870`
- `0x18000687c`
- `0x18000e938`
- `0x18000f82c`
- `0x18000f860`
- `0x18000f898`
- `0x18000fa38`
- `0x18000fbb0`
- `0x18000fc9c`
- `0x1800106a4`
- `0x180012168`
- `0x18001fd00`
- `0x180020610`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010933`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010933`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800106f9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001075c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800106f9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001075c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFileTypesManager::Save(HWND *this)
{
  HWND *v1; // r15
  HWND *v2; // r13
  int v3; // r12d
  int i; // r14d
  CExtensionPersistentHandlers *v5; // rbx
  char v6; // di
  CMSSAdmin *v7; // rcx
  const unsigned __int16 *v8; // rdx
  int v9; // eax
  int v10; // eax
  _WORD *v11; // r9
  unsigned __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int128 *p_Src; // rbx
  __int64 v16; // rdx
  const char *v17; // r9
  HRESULT v18; // eax
  unsigned int v19; // ebx
  int v21; // eax
  unsigned __int64 j; // rbx
  __int64 v23; // rcx
  _QWORD *v24; // rdx
  int v25; // eax
  unsigned int v26; // edi
  int ppv; // [rsp+20h] [rbp-108h]
  LPVOID v28; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v29; // [rsp+38h] [rbp-F0h] BYREF
  __int128 v30; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-D8h]
  int v32; // [rsp+58h] [rbp-D0h]
  int v33; // [rsp+5Ch] [rbp-CCh]
  HWND *v34; // [rsp+60h] [rbp-C8h]
  LPARAM lParam; // [rsp+70h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+78h] [rbp-B0h]
  __int64 v37; // [rsp+80h] [rbp-A8h]
  _BYTE v38[16]; // [rsp+88h] [rbp-A0h] BYREF
  CExtensionPersistentHandlers *v39; // [rsp+98h] [rbp-90h]
  __int128 Src; // [rsp+D0h] [rbp-58h] BYREF
  __int128 v41; // [rsp+E0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v1 = this;
  v34 = this;
  v2 = this;
  v30 = 0;
  v31 = 0;
  v3 = SendMessageW(*this, 0x1004u, 0, 0);
  v33 = v3;
  for ( i = 0; ; ++i )
  {
    v32 = i;
    if ( i >= v3 )
      break;
    LODWORD(lParam) = 12;
    HIDWORD(lParam) = i;
    v36 = 0;
    v37 = 61440;
    memset_0(v38, 0, 0x40u);
    if ( (unsigned int)SendMessageW(*v1, 0x104Bu, 0, (LPARAM)&lParam) )
    {
      v5 = v39;
      if ( v39 )
      {
        if ( !(*(unsigned int (__fastcall **)(CExtensionPersistentHandlers *))(*(_QWORD *)v39 + 8LL))(v39) )
        {
          v6 = 0;
          if ( (*((_DWORD *)v5 + 20) == 0) == ((v36 & 0x200000000000LL) != 0)
            || ((v6 = 1,
                 v7 = (CMSSAdmin *)(v2 + 5),
                 v8 = (const unsigned __int16 *)(*((_QWORD *)v5 + 8) + 2LL),
                 (v36 & 0x200000000000LL) == 0)
              ? (v9 = CMSSAdmin::AddExtToExcludeList(v7, v8))
              : (v9 = CMSSAdmin::RemoveExtFromExcludeList(v7, v8)),
                v9 >= 0) )
          {
            v10 = CExtensionPersistentHandlers::SaveToRegistry(v5);
            if ( v6 || !v10 )
            {
              try
              {
                std::wstring::wstring(&Src, L"*");
                v11 = (_WORD *)*((_QWORD *)v5 + 8);
                v12 = -1;
                do
                  ++v12;
                while ( v11[v12] );
                v13 = v41;
                if ( v12 > *((_QWORD *)&v41 + 1) - (_QWORD)v41 )
                {
                  std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
                    &Src,
                    v12);
                }
                else
                {
                  v14 = v12 + v41;
                  *(_QWORD *)&v41 = v12 + v41;
                  p_Src = &Src;
                  if ( *((_QWORD *)&v41 + 1) > 7u )
                    p_Src = (__int128 *)Src;
                  memmove_0((char *)p_Src + 2 * v13, v11, 2 * v12);
                  *((_WORD *)p_Src + v14) = 0;
                }
                v16 = *((_QWORD *)&v30 + 1);
                if ( *((_QWORD *)&v30 + 1) == v31 )
                {
                  std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v30, *((_QWORD *)&v30 + 1), &Src);
                }
                else
                {
                  **((_OWORD **)&v30 + 1) = 0;
                  *(_QWORD *)(v16 + 16) = 0;
                  *(_QWORD *)(v16 + 24) = 0;
                  *(_OWORD *)v16 = Src;
                  *(_OWORD *)(v16 + 16) = v41;
                  *(_QWORD *)&v41 = 0;
                  *((_QWORD *)&v41 + 1) = 7;
                  LOWORD(Src) = 0;
                  *((_QWORD *)&v30 + 1) += 32LL;
                }
                std::wstring::~wstring(&Src);
              }
              catch ( ... )
              {
                wil::details::in1diag3::Log_CaughtException(
                  retaddr,
                  (void *)0x3F7,
                  (unsigned int)"shell\\cpls\\srchadmin\\cpl\\filetypes.cpp",
                  v17);
                v3 = v33;
                i = v32;
                v1 = v34;
                v2 = v34;
                continue;
              }
            }
          }
        }
      }
    }
  }
  v28 = 0;
  v18 = CoCreateInstance(&CLSID_CSearchManager, 0, 0x15u, &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69, &v28);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x406,
      (unsigned int)"shell\\cpls\\srchadmin\\cpl\\filetypes.cpp",
      (const char *)(unsigned int)v18,
      ppv);
LABEL_27:
    if ( v28 )
      winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(&v28);
    if ( (_QWORD)v30 )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v30, *((_QWORD *)&v30 + 1));
      std::_Deallocate<16>(v30, (v31 - v30) & 0xFFFFFFFFFFFFFFE0uLL);
    }
    return v19;
  }
  v29 = 0;
  v21 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *))(*(_QWORD *)v28 + 80LL))(
          v28,
          L"SystemIndex",
          &v29);
  v19 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x409,
      (unsigned int)"shell\\cpls\\srchadmin\\cpl\\filetypes.cpp",
      (const char *)(unsigned int)v21,
      ppv);
    if ( v29 )
      winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(&v29);
    goto LABEL_27;
  }
  for ( j = 0; ; ++j )
  {
    v23 = v30;
    if ( j >= (__int64)(*((_QWORD *)&v30 + 1) - v30) >> 5 )
      break;
    v24 = (_QWORD *)(v30 + 32 * j);
    if ( v24[3] > 7u )
      v24 = (_QWORD *)*v24;
    v25 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v29 + 72LL))(v29, v24);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40D,
        (unsigned int)"shell\\cpls\\srchadmin\\cpl\\filetypes.cpp",
        (const char *)(unsigned int)v25,
        ppv);
      if ( v29 )
        winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(&v29);
      if ( v28 )
        winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(&v28);
      if ( (_QWORD)v30 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v30, *((_QWORD *)&v30 + 1));
        std::_Deallocate<16>(v30, (v31 - v30) & 0xFFFFFFFFFFFFFFE0uLL);
      }
      return v26;
    }
  }
  if ( v29 )
  {
    winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(&v29);
    v23 = v30;
  }
  if ( v28 )
  {
    winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(&v28);
    v23 = v30;
  }
  if ( v23 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v23, *((_QWORD *)&v30 + 1));
    std::_Deallocate<16>(v30, (v31 - v30) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return 1;
}

```

## disassembly

```asm
0x1800106a4  mov     [rsp+arg_8], rbx
0x1800106a9  mov     [rsp+arg_10], rsi
0x1800106ae  push    rdi
0x1800106af  push    r12
0x1800106b1  push    r13
0x1800106b3  push    r14
0x1800106b5  push    r15
0x1800106b7  sub     rsp, 100h
0x1800106be  mov     rax, cs:__security_cookie
0x1800106c5  xor     rax, rsp
0x1800106c8  mov     [rsp+128h+var_38], rax
0x1800106d0  mov     r15, rcx
0x1800106d3  mov     [rsp+128h+var_C8], rcx
0x1800106d8  mov     r13, rcx
0x1800106db  xorps   xmm0, xmm0
0x1800106de  movdqu  [rsp+128h+var_E8], xmm0
0x1800106e4  xor     esi, esi
0x1800106e6  mov     [rsp+128h+var_D8], rsi
0x1800106eb  xor     r9d, r9d; lParam
0x1800106ee  xor     r8d, r8d; wParam
0x1800106f1  mov     edx, 1004h; Msg
0x1800106f6  mov     rcx, [rcx]; hWnd
0x1800106f9  call    cs:__imp_SendMessageW
0x1800106ff  mov     r12, rax
0x180010702  mov     [rsp+128h+var_CC], eax
0x180010706  mov     r14d, esi
0x180010709  mov     [rsp+128h+var_D0], r14d
0x18001070e  cmp     r14d, r12d
0x180010711  jge     loc_180010910
0x180010717  mov     dword ptr [rsp+128h+lParam], 0Ch
0x18001071f  mov     dword ptr [rsp+128h+lParam+4], r14d
0x180010724  mov     [rsp+128h+var_B0], 0
0x18001072d  mov     [rsp+128h+var_A8], 0F000h
0x180010739  xor     edx, edx; Val
0x18001073b  lea     r8d, [rdx+40h]; Size
0x18001073f  lea     rcx, [rsp+128h+var_A0]; void *
0x180010747  call    memset_0
0x18001074c  lea     r9, [rsp+128h+lParam]; lParam
0x180010751  xor     r8d, r8d; wParam
0x180010754  mov     edx, 104Bh; Msg
0x180010759  mov     rcx, [r15]; hWnd
0x18001075c  call    cs:__imp_SendMessageW
0x180010762  test    eax, eax
0x180010764  jz      loc_180010908
0x18001076a  mov     rbx, [rsp+128h+var_90]
0x180010772  test    rbx, rbx
0x180010775  jz      loc_180010908
0x18001077b  mov     rax, [rbx]
0x18001077e  mov     rcx, rbx
0x180010781  mov     rax, [rax+8]
0x180010785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001078a  test    eax, eax
0x18001078c  jnz     loc_180010908
0x180010792  mov     dil, sil
0x180010795  mov     r8d, dword ptr [rsp+128h+var_B0+4]
0x18001079a  mov     ecx, esi
0x18001079c  cmp     [rbx+50h], esi
0x18001079f  setz    cl
0x1800107a2  mov     eax, esi
0x1800107a4  and     r8d, 2000h
0x1800107ab  setnz   al
0x1800107ae  cmp     ecx, eax
0x1800107b0  jz      short loc_1800107DA
0x1800107b2  mov     dil, 1
0x1800107b5  lea     rcx, [r13+28h]; this
0x1800107b9  mov     rdx, [rbx+40h]
0x1800107bd  add     rdx, 2; unsigned __int16 *
0x1800107c1  test    r8d, r8d
0x1800107c4  jz      short loc_1800107CD
0x1800107c6  call    ?RemoveExtFromExcludeList@CMSSAdmin@@QEAAJPEBG@Z; CMSSAdmin::RemoveExtFromExcludeList(ushort const *)
0x1800107cb  jmp     short loc_1800107D2
0x1800107cd  call    ?AddExtToExcludeList@CMSSAdmin@@QEAAJPEBG@Z; CMSSAdmin::AddExtToExcludeList(ushort const *)
0x1800107d2  test    eax, eax
0x1800107d4  js      loc_180010908
0x1800107da  mov     rcx, rbx; this
0x1800107dd  call    ?SaveToRegistry@CExtensionPersistentHandlers@@QEAAJXZ; CExtensionPersistentHandlers::SaveToRegistry(void)
0x1800107e2  test    dil, dil
0x1800107e5  jnz     short loc_1800107EF
0x1800107e7  test    eax, eax
0x1800107e9  jnz     loc_180010908
0x1800107ef  lea     rdx, pszSrch; "*"
0x1800107f6  lea     rcx, [rsp+128h+Src]
0x1800107fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180010803  nop
0x180010804  mov     r9, [rbx+40h]
0x180010808  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001080c  inc     rdx
0x18001080f  cmp     [r9+rdx*2], si
0x180010814  jnz     short loc_18001080C
0x180010816  mov     rcx, qword ptr [rsp+128h+var_48]
0x18001081e  mov     rax, qword ptr [rsp+128h+var_48+8]
0x180010826  sub     rax, rcx
0x180010829  cmp     rdx, rax
0x18001082c  ja      short loc_18001086A
0x18001082e  lea     rdi, [rdx+rcx]
0x180010832  mov     qword ptr [rsp+128h+var_48], rdi
0x18001083a  lea     rbx, [rsp+128h+Src]
0x180010842  cmp     qword ptr [rsp+128h+var_48+8], 7
0x18001084b  cmova   rbx, qword ptr [rsp+128h+Src]
0x180010854  lea     r8, [rdx+rdx]; Size
0x180010858  lea     rcx, [rbx+rcx*2]; void *
0x18001085c  mov     rdx, r9; Src
0x18001085f  call    memmove_0
0x180010864  mov     [rbx+rdi*2], si
0x180010868  jmp     short loc_18001087C
0x18001086a  mov     qword ptr [rsp+128h+ppv], rdx; __int64
0x18001086f  lea     rcx, [rsp+128h+Src]; Src
0x180010877  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001087c  mov     rdx, qword ptr [rsp+128h+var_E8+8]
0x180010881  cmp     rdx, [rsp+128h+var_D8]
0x180010886  jz      short loc_1800108D1
0x180010888  xorps   xmm0, xmm0
0x18001088b  movups  xmmword ptr [rdx], xmm0
0x18001088e  mov     [rdx+10h], rsi
0x180010892  mov     [rdx+18h], rsi
0x180010896  movups  xmm0, [rsp+128h+Src]
0x18001089e  movups  xmmword ptr [rdx], xmm0
0x1800108a1  movups  xmm1, [rsp+128h+var_48]
0x1800108a9  movups  xmmword ptr [rdx+10h], xmm1
0x1800108ad  mov     qword ptr [rsp+128h+var_48], rsi
0x1800108b5  mov     qword ptr [rsp+128h+var_48+8], 7
0x1800108c1  mov     word ptr [rsp+128h+Src], si
0x1800108c9  add     qword ptr [rsp+128h+var_E8+8], 20h ; ' '
0x1800108cf  jmp     short loc_1800108E4
0x1800108d1  lea     r8, [rsp+128h+Src]
0x1800108d9  lea     rcx, [rsp+128h+var_E8]
0x1800108de  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800108e3  nop
0x1800108e4  lea     rcx, [rsp+128h+Src]
0x1800108ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800108f1  nop
0x1800108f2  jmp     short loc_180010908
0x1800108f4  xor     esi, esi
0x1800108f6  mov     r12d, [rsp+128h+var_CC]
0x1800108fb  mov     r14d, [rsp+128h+var_D0]
0x180010900  mov     r15, [rsp+128h+var_C8]
0x180010905  mov     r13, r15
0x180010908  inc     r14d
0x18001090b  jmp     loc_180010709
0x180010910  mov     [rsp+128h+var_F8], rsi
0x180010915  lea     rax, [rsp+128h+var_F8]
0x18001091a  mov     qword ptr [rsp+128h+ppv], rax; int
0x18001091f  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x180010926  xor     edx, edx; pUnkOuter
0x180010928  lea     r8d, [rdx+15h]; dwClsContext
0x18001092c  lea     rcx, CLSID_CSearchManager; rclsid
0x180010933  call    cs:__imp_CoCreateInstance
0x180010939  mov     ebx, eax
0x18001093b  test    eax, eax
0x18001093d  jns     short loc_18001099F
0x18001093f  mov     rcx, [rsp+128h]; this
0x180010947  mov     r9d, eax; char *
0x18001094a  lea     r8, aShellCplsSrcha_0; "shell\\cpls\\srchadmin\\cpl\\filetypes."...
0x180010951  mov     edx, 406h; void *
0x180010956  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001095b  nop
0x18001095c  cmp     [rsp+128h+var_F8], rsi
0x180010961  jz      short loc_18001096E
0x180010963  lea     rcx, [rsp+128h+var_F8]
0x180010968  call    ?unconditional_release_ref@?$com_ptr@UISearchCatalogManager@@@winrt@@AEAAXXZ; winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(void)
0x18001096d  nop
0x18001096e  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180010973  test    rcx, rcx
0x180010976  jz      short loc_180010998
0x180010978  mov     rdx, qword ptr [rsp+128h+var_E8+8]
0x18001097d  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180010982  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180010987  mov     rdx, [rsp+128h+var_D8]
0x18001098c  sub     rdx, rcx
0x18001098f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180010993  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010998  mov     eax, ebx
0x18001099a  jmp     loc_180010B16
0x18001099f  mov     [rsp+128h+var_F0], rsi
0x1800109a4  mov     rcx, [rsp+128h+var_F8]
0x1800109a9  mov     rax, [rcx]
0x1800109ac  lea     r8, [rsp+128h+var_F0]
0x1800109b1  lea     rdx, aSystemindex; "SystemIndex"
0x1800109b8  mov     rax, [rax+50h]
0x1800109bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109c1  mov     ebx, eax
0x1800109c3  test    eax, eax
0x1800109c5  jns     short loc_1800109FE
0x1800109c7  mov     rcx, [rsp+128h]; this
0x1800109cf  mov     r9d, eax; char *
0x1800109d2  lea     r8, aShellCplsSrcha_0; "shell\\cpls\\srchadmin\\cpl\\filetypes."...
0x1800109d9  mov     edx, 409h; void *
0x1800109de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109e3  nop
0x1800109e4  cmp     [rsp+128h+var_F0], rsi
0x1800109e9  jz      loc_18001095C
0x1800109ef  lea     rcx, [rsp+128h+var_F0]
0x1800109f4  call    ?unconditional_release_ref@?$com_ptr@UISearchCatalogManager@@@winrt@@AEAAXXZ; winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(void)
0x1800109f9  jmp     loc_18001095C
0x1800109fe  mov     rbx, rsi
0x180010a01  mov     rax, qword ptr [rsp+128h+var_E8+8]
0x180010a06  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180010a0b  sub     rax, rcx
0x180010a0e  sar     rax, 5
0x180010a12  cmp     rbx, rax
0x180010a15  jnb     loc_180010AC0
0x180010a1b  mov     r8, [rsp+128h+var_F0]
0x180010a20  mov     rax, [r8]
0x180010a23  mov     r9, [rax+48h]
0x180010a27  mov     rdx, rbx
0x180010a2a  shl     rdx, 5
0x180010a2e  add     rdx, rcx
0x180010a31  cmp     qword ptr [rdx+18h], 7
0x180010a36  jbe     short loc_180010A3B
0x180010a38  mov     rdx, [rdx]
0x180010a3b  mov     rcx, r8
0x180010a3e  mov     rax, r9
0x180010a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a46  mov     edi, eax
0x180010a48  test    eax, eax
0x180010a4a  js      short loc_180010A51
0x180010a4c  inc     rbx
0x180010a4f  jmp     short loc_180010A01
0x180010a51  mov     rcx, [rsp+128h]; this
0x180010a59  mov     r9d, edi; char *
0x180010a5c  lea     r8, aShellCplsSrcha_0; "shell\\cpls\\srchadmin\\cpl\\filetypes."...
0x180010a63  mov     edx, 40Dh; void *
0x180010a68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a6d  nop
0x180010a6e  cmp     [rsp+128h+var_F0], rsi
0x180010a73  jz      short loc_180010A80
0x180010a75  lea     rcx, [rsp+128h+var_F0]
0x180010a7a  call    ?unconditional_release_ref@?$com_ptr@UISearchCatalogManager@@@winrt@@AEAAXXZ; winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(void)
0x180010a7f  nop
0x180010a80  cmp     [rsp+128h+var_F8], rsi
0x180010a85  jz      short loc_180010A92
0x180010a87  lea     rcx, [rsp+128h+var_F8]
0x180010a8c  call    ?unconditional_release_ref@?$com_ptr@UISearchCatalogManager@@@winrt@@AEAAXXZ; winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(void)
0x180010a91  nop
0x180010a92  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180010a97  test    rcx, rcx
0x180010a9a  jz      short loc_180010ABC
0x180010a9c  mov     rdx, qword ptr [rsp+128h+var_E8+8]
0x180010aa1  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180010aa6  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180010aab  mov     rdx, [rsp+128h+var_D8]
0x180010ab0  sub     rdx, rcx
0x180010ab3  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180010ab7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010abc  mov     eax, edi
0x180010abe  jmp     short loc_180010B16
0x180010ac0  cmp     [rsp+128h+var_F0], rsi
0x180010ac5  jz      short loc_180010AD6
0x180010ac7  lea     rcx, [rsp+128h+var_F0]
0x180010acc  call    ?unconditional_release_ref@?$com_ptr@UISearchCatalogManager@@@winrt@@AEAAXXZ; winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(void)
0x180010ad1  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180010ad6  cmp     [rsp+128h+var_F8], rsi
0x180010adb  jz      short loc_180010AEC
0x180010add  lea     rcx, [rsp+128h+var_F8]
0x180010ae2  call    ?unconditional_release_ref@?$com_ptr@UISearchCatalogManager@@@winrt@@AEAAXXZ; winrt::com_ptr<ISearchCatalogManager>::unconditional_release_ref(void)
0x180010ae7  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180010aec  test    rcx, rcx
0x180010aef  jz      short loc_180010B11
0x180010af1  mov     rdx, qword ptr [rsp+128h+var_E8+8]
0x180010af6  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180010afb  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180010b00  mov     rdx, [rsp+128h+var_D8]
0x180010b05  sub     rdx, rcx
0x180010b08  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180010b0c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010b11  mov     eax, 1
0x180010b16  mov     rcx, [rsp+128h+var_38]
0x180010b1e  xor     rcx, rsp; StackCookie
0x180010b21  call    __security_check_cookie
0x180010b26  lea     r11, [rsp+128h+var_28]
0x180010b2e  mov     rbx, [r11+38h]
0x180010b32  mov     rsi, [r11+40h]
0x180010b36  mov     rsp, r11
0x180010b39  pop     r15
0x180010b3b  pop     r14
0x180010b3d  pop     r13
0x180010b3f  pop     r12
0x180010b41  pop     rdi
0x180010b42  retn
```
