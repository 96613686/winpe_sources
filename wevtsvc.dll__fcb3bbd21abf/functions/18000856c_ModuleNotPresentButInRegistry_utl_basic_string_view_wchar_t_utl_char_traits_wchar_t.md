# ModuleNotPresentButInRegistry(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x18000856c`
- end: `0x18000884c`
- name: `?ModuleNotPresentButInRegistry@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z`
- size: `736`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180008d64`

## callees

- `0x180006e60`
- `0x18000856c`
- `0x180008870`
- `0x180008a20`
- `0x180009314`
- `0x180014bd0`
- `0x18001722c`
- `0x180017b60`
- `0x180017b98`
- `0x18001c320`
- `0x18002d354`
- `0x18002d6dc`
- `0x18009aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008815`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008815`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800086d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800086d1`

## string_xrefs

- `0x1800085c8`: `SYSTEM\CurrentControlSet\Services\Eventlog`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ModuleNotPresentButInRegistry(_QWORD *a1)
{
  unsigned int v2; // eax
  HKEY *v3; // rsi
  HKEY v4; // rdi
  HKEY v5; // rbx
  _BYTE *v6; // rax
  _WORD *v7; // rcx
  _BYTE *v9; // rax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rdx
  char v12; // bl
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-D0h] BYREF
  _WORD *v14; // [rsp+38h] [rbp-C8h]
  _BYTE *v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[2]; // [rsp+4Eh] [rbp-B2h] BYREF
  HKEY phkResult[4]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v19; // [rsp+80h] [rbp-80h]
  HKEY v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+90h] [rbp-70h]
  int v22; // [rsp+94h] [rbp-6Ch]

  if ( (void **)utl::_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::unique_ptr<LOGMODULE,utl::default_delete<LOGMODULE>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::unique_ptr<LOGMODULE,utl::default_delete<LOGMODULE>>>>,0>::_FindImpl<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
                  a1,
                  a1) != &LogModules )
    return 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpSubKey);
  RegistryKeyEnumerator::RegistryKeyEnumerator(
    (RegistryKeyEnumerator *)hKey,
    HKEY_LOCAL_MACHINE,
    L"SYSTEM\\CurrentControlSet\\Services\\Eventlog",
    (void *)0xFFFFFFFFFFFFFFFFLL);
  v21 = v22;
  v2 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)hKey);
  v3 = (HKEY *)(a1 + 1);
  while ( 1 )
  {
    if ( v2 == 259 )
    {
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
      if ( lpSubKey != (LPCWSTR)&v15 )
        operator delete((void *)lpSubKey);
      return 0;
    }
    v4 = v19;
    v5 = v20;
    if ( (v20 != (HKEY)10
       || (unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(v19, L"Parameters"))
      && (v5 != (HKEY)5
       || (unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(v4, L"State")) )
    {
      break;
    }
LABEL_16:
    v2 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)hKey);
  }
  if ( *v3 == v5 && !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(*a1, v4) )
  {
    v12 = 1;
    goto LABEL_31;
  }
  phkResult[2] = v4;
  phkResult[3] = v5;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&lpSubKey) )
    goto LABEL_30;
  v6 = v16;
  if ( lpSubKey != (LPCWSTR)&v15 )
    v6 = v15;
  v7 = v14;
  if ( v14 == (_WORD *)v6 )
  {
    v9 = v16;
    if ( lpSubKey != (LPCWSTR)&v15 )
      v9 = v15;
    v10 = (v9 - (_BYTE *)lpSubKey) >> 1;
    if ( lpSubKey == (LPCWSTR)&v15 )
    {
      v11 = 15;
    }
    else
    {
      v11 = 2 * ((v15 - (_BYTE *)lpSubKey) >> 1) + 1;
      if ( v11 > 0x3FFFFFFFFFFFFFF7LL )
        v11 = 0x3FFFFFFFFFFFFFF7LL;
    }
    if ( v10 >= v11
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(&lpSubKey) )
    {
LABEL_30:
      v12 = 0;
LABEL_31:
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpSubKey);
      return v12;
    }
    v7 = v14;
  }
  *v7 = 92;
  *++v14 = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&lpSubKey) )
    goto LABEL_30;
  phkResult[0] = 0;
  if ( RegOpenKeyExW(hKey[0], lpSubKey, 0, 0x20019u, phkResult) )
  {
    if ( phkResult[0] )
      RegCloseKey(phkResult[0]);
    v3 = (HKEY *)(a1 + 1);
    goto LABEL_16;
  }
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
  if ( lpSubKey != (LPCWSTR)&v15 )
    operator delete((void *)lpSubKey);
  return 1;
}

```

## disassembly

```asm
0x18000856c  mov     [rsp-8+arg_8], rbx
0x180008571  mov     [rsp-8+arg_10], rsi
0x180008576  push    rbp
0x180008577  push    rdi
0x180008578  push    r12
0x18000857a  push    r14
0x18000857c  push    r15
0x18000857e  lea     rbp, [rsp-1B0h]
0x180008586  sub     rsp, 2B0h
0x18000858d  mov     rax, cs:__security_cookie
0x180008594  xor     rax, rsp
0x180008597  mov     [rbp+1D0h+var_30], rax
0x18000859e  mov     r14, rcx
0x1800085a1  mov     rdx, rcx
0x1800085a4  call    ??$_FindImpl@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@?$_Tree@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$unique_ptr@ULOGMODULE@@U?$default_delete@ULOGMODULE@@@utl@@@2@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$unique_ptr@ULOGMODULE@@U?$default_delete@ULOGMODULE@@@utl@@@2@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$unique_ptr@ULOGMODULE@@U?$default_delete@ULOGMODULE@@@utl@@@2@@utl@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z; utl::_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::unique_ptr<LOGMODULE,utl::default_delete<LOGMODULE>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::unique_ptr<LOGMODULE,utl::default_delete<LOGMODULE>>>>,0>::_FindImpl<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800085a9  lea     rcx, ?LogModules@@3V?$map@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$unique_ptr@ULOGMODULE@@U?$default_delete@ULOGMODULE@@@utl@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$unique_ptr@ULOGMODULE@@U?$default_delete@ULOGMODULE@@@utl@@@2@@utl@@@2@@utl@@A; utl::map<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::unique_ptr<LOGMODULE,utl::default_delete<LOGMODULE>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::unique_ptr<LOGMODULE,utl::default_delete<LOGMODULE>>>>> LogModules
0x1800085b0  cmp     rax, rcx
0x1800085b3  jnz     loc_18000875E
0x1800085b9  lea     rcx, [rsp+2D0h+lpSubKey]; void *
0x1800085be  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800085c3  nop
0x1800085c4  or      r9, 0FFFFFFFFFFFFFFFFh; void *
0x1800085c8  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x1800085cf  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800085d6  lea     rcx, [rsp+2D0h+hKey]; this
0x1800085db  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@PEB_WPEAX@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *,wchar_t const *,void *)
0x1800085e0  mov     eax, [rbp+1D0h+var_23C]
0x1800085e3  mov     [rbp+1D0h+var_240], eax
0x1800085e6  lea     rcx, [rsp+2D0h+hKey]; this
0x1800085eb  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x1800085f0  lea     rsi, [r14+8]
0x1800085f4  mov     r15, rsi
0x1800085f7  mov     r12, 3FFFFFFFFFFFFFF7h
0x180008601  cmp     eax, 103h
0x180008606  jz      loc_18000873F
0x18000860c  mov     rdi, [rbp+1D0h+var_250]
0x180008610  mov     rbx, [rbp+1D0h+var_248]
0x180008614  cmp     rbx, 0Ah
0x180008618  jz      loc_180008701
0x18000861e  cmp     rbx, 5
0x180008622  jz      loc_180008720
0x180008628  cmp     [rsi], rbx
0x18000862b  jz      loc_1800087F6
0x180008631  mov     [rsp+2D0h+var_270], rdi
0x180008636  mov     [rsp+2D0h+var_268], rbx
0x18000863b  lea     rdx, [rsp+2D0h+var_270]
0x180008640  lea     rcx, [rsp+2D0h+lpSubKey]
0x180008645  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18000864a  test    al, al
0x18000864c  jz      loc_1800087C4
0x180008652  lea     rax, [rsp+2D0h+var_282]
0x180008657  mov     rdx, [rsp+2D0h+var_290]
0x18000865c  lea     rcx, [rsp+2D0h+var_290]
0x180008661  mov     r8, [rsp+2D0h+lpSubKey]
0x180008666  cmp     r8, rcx
0x180008669  cmovnz  rax, rdx
0x18000866d  mov     rcx, [rsp+2D0h+var_298]
0x180008672  cmp     rcx, rax
0x180008675  jz      loc_18000878B
0x18000867b  mov     word ptr [rcx], 5Ch ; '\'
0x180008680  mov     rcx, [rsp+2D0h+var_298]
0x180008685  add     rcx, 2
0x180008689  mov     [rsp+2D0h+var_298], rcx
0x18000868e  xor     eax, eax
0x180008690  mov     [rcx], ax
0x180008693  mov     r8, [r15]
0x180008696  mov     rdx, [r14]
0x180008699  lea     rcx, [rsp+2D0h+lpSubKey]
0x18000869e  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800086a3  test    al, al
0x1800086a5  jz      loc_1800087C4
0x1800086ab  mov     [rsp+2D0h+var_280], 0
0x1800086b4  lea     rax, [rsp+2D0h+var_280]
0x1800086b9  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800086be  mov     r9d, 20019h; samDesired
0x1800086c4  xor     r8d, r8d; ulOptions
0x1800086c7  mov     rdx, [rsp+2D0h+lpSubKey]; lpSubKey
0x1800086cc  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800086d1  call    cs:__imp_RegOpenKeyExW
0x1800086d7  mov     rcx, [rsp+2D0h+var_280]; hKey
0x1800086dc  test    eax, eax
0x1800086de  jz      loc_180008810
0x1800086e4  test    rcx, rcx
0x1800086e7  jz      short loc_1800086EF
0x1800086e9  call    cs:__imp_RegCloseKey
0x1800086ef  mov     rsi, r15
0x1800086f2  lea     rcx, [rsp+2D0h+hKey]; this
0x1800086f7  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x1800086fc  jmp     loc_180008601
0x180008701  mov     r8d, 0Ah
0x180008707  lea     rdx, aParameters; "Parameters"
0x18000870e  mov     rcx, rdi
0x180008711  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x180008716  test    eax, eax
0x180008718  jnz     loc_18000861E
0x18000871e  jmp     short loc_1800086F2
0x180008720  mov     r8d, 5
0x180008726  lea     rdx, aState; "State"
0x18000872d  mov     rcx, rdi
0x180008730  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x180008735  test    eax, eax
0x180008737  jnz     loc_180008628
0x18000873d  jmp     short loc_1800086F2
0x18000873f  lea     rcx, [rsp+2D0h+hKey]
0x180008744  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180008749  nop
0x18000874a  lea     rax, [rsp+2D0h+var_290]
0x18000874f  mov     rcx, [rsp+2D0h+lpSubKey]; void *
0x180008754  cmp     rcx, rax
0x180008757  jz      short loc_18000875E
0x180008759  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000875e  xor     al, al
0x180008760  mov     rcx, [rbp+1D0h+var_30]
0x180008767  xor     rcx, rsp; StackCookie
0x18000876a  call    __security_check_cookie
0x18000876f  lea     r11, [rsp+2D0h+var_20]
0x180008777  mov     rbx, [r11+38h]
0x18000877b  mov     rsi, [r11+40h]
0x18000877f  mov     rsp, r11
0x180008782  pop     r15
0x180008784  pop     r14
0x180008786  pop     r12
0x180008788  pop     rdi
0x180008789  pop     rbp
0x18000878a  retn
0x18000878b  lea     rax, [rsp+2D0h+var_282]
0x180008790  lea     rcx, [rsp+2D0h+var_290]
0x180008795  cmp     r8, rcx
0x180008798  cmovnz  rax, rdx
0x18000879c  sub     rax, r8
0x18000879f  sar     rax, 1
0x1800087a2  lea     rcx, [rsp+2D0h+var_290]
0x1800087a7  cmp     r8, rcx
0x1800087aa  jnz     short loc_1800087DF
0x1800087ac  mov     edx, 0Fh
0x1800087b1  cmp     rax, rdx
0x1800087b4  jnb     short loc_1800087C4
0x1800087b6  lea     rcx, [rsp+2D0h+lpSubKey]
0x1800087bb  call    ?_GrowTo@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(unsigned __int64)
0x1800087c0  test    al, al
0x1800087c2  jnz     short loc_180008841
0x1800087c4  xor     ebx, ebx
0x1800087c6  lea     rcx, [rsp+2D0h+hKey]
0x1800087cb  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800087d0  nop
0x1800087d1  lea     rcx, [rsp+2D0h+lpSubKey]; void *
0x1800087d6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800087db  mov     al, bl
0x1800087dd  jmp     short loc_180008760
0x1800087df  sub     rdx, r8
0x1800087e2  sar     rdx, 1
0x1800087e5  lea     rdx, ds:1[rdx*2]
0x1800087ed  cmp     rdx, r12
0x1800087f0  cmova   rdx, r12
0x1800087f4  jmp     short loc_1800087B1
0x1800087f6  mov     r8, [rsi]
0x1800087f9  mov     rdx, rdi
0x1800087fc  mov     rcx, [r14]
0x1800087ff  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x180008804  test    eax, eax
0x180008806  jnz     loc_180008631
0x18000880c  mov     bl, 1
0x18000880e  jmp     short loc_1800087C6
0x180008810  test    rcx, rcx
0x180008813  jz      short loc_18000881B
0x180008815  call    cs:__imp_RegCloseKey
0x18000881b  lea     rcx, [rsp+2D0h+hKey]
0x180008820  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180008825  nop
0x180008826  lea     rax, [rsp+2D0h+var_290]
0x18000882b  mov     rcx, [rsp+2D0h+lpSubKey]; void *
0x180008830  cmp     rcx, rax
0x180008833  jz      short loc_18000883A
0x180008835  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000883a  mov     al, 1
0x18000883c  jmp     loc_180008760
0x180008841  mov     rcx, [rsp+2D0h+var_298]
0x180008846  jmp     loc_18000867B
```
