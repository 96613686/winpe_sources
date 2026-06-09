# CEtwTraceManager::AddWprcInstancesFromRegistry(wchar_t const *)

- ea: `0x180031a48`
- end: `0x180031d0e`
- name: `?AddWprcInstancesFromRegistry@CEtwTraceManager@@QEAAJPEB_W@Z`
- size: `710`
- prototype: `__int64 __fastcall(CEtwTraceManager *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180018c5c`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180002a00`
- `0x180007cc8`
- `0x180011648`
- `0x1800314f0`
- `0x180031a48`
- `0x180032a20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031aab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031aab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031ce3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031ce3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031aec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031c35`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031aec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031c35`

## pseudocode

```c
__int64 __fastcall CEtwTraceManager::AddWprcInstancesFromRegistry(CEtwTraceManager *this, const wchar_t *a2)
{
  HKEY *phkResult; // rax
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  DWORD v6; // r15d
  char *v7; // rax
  void **v8; // rdi
  __int64 v9; // r8
  __int64 *v10; // rsi
  void ***v11; // rax
  void **v12; // r14
  __int64 v13; // r14
  char v14; // al
  __int64 v15; // rcx
  void ***v16; // r8
  __int64 v17; // rdx
  char *v18; // rcx
  char *v19; // rax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[1032]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  cchName = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\DynamicWprcSessions",
         0,
         0x20019u,
         phkResult) )
  {
    v4 = 1;
    goto LABEL_35;
  }
  cchName = 1025;
  v5 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
  v6 = 1;
  if ( v5 == 259 )
  {
LABEL_34:
    v4 = 0;
    goto LABEL_35;
  }
  while ( 1 )
  {
    if ( v5 == 234 )
      goto LABEL_21;
    if ( v5 )
    {
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      else
        v4 = v5;
      goto LABEL_35;
    }
    v7 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = (void **)v7;
    if ( !v7 )
      goto LABEL_30;
    *(_QWORD *)(v7 + 18) = 0;
    *(_DWORD *)(v7 + 26) = 0;
    v9 = -1;
    *((_WORD *)v7 + 15) = 0;
    *(_QWORD *)v7 = v7 + 16;
    *((_QWORD *)v7 + 1) = v7 + 16;
    v23[0] = v7;
    *((_WORD *)v7 + 8) = 0;
    do
      ++v9;
    while ( Name[v9] );
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v7,
                             Name) )
    {
      if ( *v8 != v8 + 2 )
        operator delete(*v8, (const struct std::nothrow_t *)&std::nothrow);
      operator delete(v8, (const struct std::nothrow_t *)0x20);
LABEL_30:
      v4 = -2147024882;
      goto LABEL_35;
    }
    v10 = (__int64 *)((char *)this + 24);
    v11 = (void ***)*((_QWORD *)this + 4);
    if ( v11 != *((void ****)this + 5) )
    {
      v12 = 0;
      *v11 = v8;
      goto LABEL_17;
    }
    v13 = *v10;
    v14 = utl::vector<utl::unique_ptr<CWprcInstance,utl::default_delete<CWprcInstance>>,utl::allocator<utl::unique_ptr<CWprcInstance,utl::default_delete<CWprcInstance>>>>::_Grow((char *)this + 24);
    v16 = (void ***)*((_QWORD *)this + 4);
    v17 = *v10;
    if ( !v14 )
      break;
    v18 = (char *)v23 - v13;
    if ( (char *)v23 - v13 >= (char *)v16 - v17 )
    {
      v19 = (char *)v23;
    }
    else
    {
      v19 = &v18[v17];
      v8 = *(void ***)&v18[v17];
    }
    *(_QWORD *)v19 = 0;
    v12 = (void **)v23[0];
    *v16 = v8;
LABEL_17:
    *((_QWORD *)this + 4) += 8LL;
    if ( v12 )
    {
      if ( *v12 != v12 + 2 )
        operator delete(*v12, (const struct std::nothrow_t *)&std::nothrow);
      operator delete(v12, (const struct std::nothrow_t *)0x20);
    }
LABEL_21:
    cchName = 1025;
    v5 = RegEnumKeyExW(hKey, v6, Name, &cchName, 0, 0, 0, 0);
    if ( v5 == 259 )
      goto LABEL_34;
    ++v6;
  }
  *((_QWORD *)this + 4) = v17;
  v4 = -2147024882;
  utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWprcInstance,utl::default_delete<CWprcInstance>>>>(
    v15,
    v17,
    ((__int64)v16 - v17) >> 3);
  if ( v8 )
  {
    if ( *v8 != v8 + 2 )
      operator delete(*v8, (const struct std::nothrow_t *)&std::nothrow);
    operator delete(v8, (const struct std::nothrow_t *)0x20);
  }
LABEL_35:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180031a48  push    rbp
0x180031a4a  push    rbx
0x180031a4b  push    rsi
0x180031a4c  push    rdi
0x180031a4d  push    r12
0x180031a4f  push    r13
0x180031a51  push    r14
0x180031a53  push    r15
0x180031a55  lea     rbp, [rsp-788h]
0x180031a5d  sub     rsp, 888h
0x180031a64  mov     rax, cs:__security_cookie
0x180031a6b  xor     rax, rsp
0x180031a6e  mov     [rbp+7C0h+var_50], rax
0x180031a75  mov     r13, rcx
0x180031a78  xor     r12d, r12d
0x180031a7b  lea     rcx, [rsp+8C0h+hKey]
0x180031a80  mov     [rsp+8C0h+hKey], r12
0x180031a85  mov     [rsp+8C0h+cchName], r12d
0x180031a8a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180031a8f  mov     r9d, 20019h; samDesired
0x180031a95  mov     [rsp+8C0h+phkResult], rax; phkResult
0x180031a9a  xor     r8d, r8d; ulOptions
0x180031a9d  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\Windows E"...
0x180031aa4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031aab  call    cs:__imp_RegOpenKeyExW
0x180031ab1  test    eax, eax
0x180031ab3  jz      short loc_180031ABF
0x180031ab5  lea     ebx, [r12+1]
0x180031aba  jmp     loc_180031CD9
0x180031abf  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180031ac4  lea     r9, [rsp+8C0h+cchName]; lpcchName
0x180031ac9  mov     [rsp+8C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180031ace  lea     r8, [rsp+8C0h+Name]; lpName
0x180031ad3  mov     [rsp+8C0h+lpcchClass], r12; lpcchClass
0x180031ad8  xor     edx, edx; dwIndex
0x180031ada  mov     [rsp+8C0h+lpClass], r12; lpClass
0x180031adf  mov     [rsp+8C0h+phkResult], r12; lpReserved
0x180031ae4  mov     [rsp+8C0h+cchName], 401h
0x180031aec  call    cs:__imp_RegEnumKeyExW
0x180031af2  mov     ebx, 1
0x180031af7  mov     r15d, ebx
0x180031afa  cmp     eax, 103h
0x180031aff  jz      loc_180031CD6
0x180031b05  cmp     eax, 0EAh
0x180031b0a  jz      loc_180031C07
0x180031b10  test    eax, eax
0x180031b12  jnz     loc_180031CBB
0x180031b18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031b1f  lea     ecx, [rax+20h]; unsigned __int64
0x180031b22  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031b27  mov     rdi, rax
0x180031b2a  test    rax, rax
0x180031b2d  jz      loc_180031CB4
0x180031b33  mov     [rax+12h], r12
0x180031b37  lea     rcx, [rax+10h]
0x180031b3b  mov     [rax+1Ah], r12d
0x180031b3f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031b43  mov     [rax+1Eh], r12w
0x180031b48  mov     [rax], rcx
0x180031b4b  mov     [rax+8], rcx
0x180031b4f  mov     [rsp+8C0h+var_870], rax
0x180031b54  lea     rax, [rsp+8C0h+Name]
0x180031b59  mov     [rcx], r12w
0x180031b5d  inc     r8
0x180031b60  cmp     [rax+r8*2], r12w
0x180031b65  jnz     short loc_180031B5D
0x180031b67  lea     rdx, [rsp+8C0h+Name]
0x180031b6c  mov     rcx, rdi
0x180031b6f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180031b74  test    al, al
0x180031b76  jz      loc_180031C8F
0x180031b7c  lea     rsi, [r13+18h]
0x180031b80  mov     rax, [rsi+8]
0x180031b84  cmp     rax, [rsi+10h]
0x180031b88  jz      short loc_180031B92
0x180031b8a  mov     r14, r12
0x180031b8d  mov     [rax], rdi
0x180031b90  jmp     short loc_180031BD8
0x180031b92  mov     r14, [rsi]
0x180031b95  mov     rcx, rsi
0x180031b98  call    ?_Grow@?$vector@V?$unique_ptr@VCWprcInstance@@U?$default_delete@VCWprcInstance@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCWprcInstance@@U?$default_delete@VCWprcInstance@@@utl@@@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::unique_ptr<CWprcInstance,utl::default_delete<CWprcInstance>>,utl::allocator<utl::unique_ptr<CWprcInstance,utl::default_delete<CWprcInstance>>>>::_Grow(void)
0x180031b9d  mov     r8, [rsi+8]
0x180031ba1  mov     rdx, [rsi]
0x180031ba4  test    al, al
0x180031ba6  jz      loc_180031C4E
0x180031bac  lea     rcx, [rsp+8C0h+var_870]
0x180031bb1  mov     rax, r8
0x180031bb4  sub     rcx, r14
0x180031bb7  sub     rax, rdx
0x180031bba  cmp     rcx, rax
0x180031bbd  jnb     short loc_180031BC8
0x180031bbf  lea     rax, [rcx+rdx]
0x180031bc3  mov     rdi, [rax]
0x180031bc6  jmp     short loc_180031BCD
0x180031bc8  lea     rax, [rsp+8C0h+var_870]
0x180031bcd  mov     [rax], r12
0x180031bd0  mov     r14, [rsp+8C0h+var_870]
0x180031bd5  mov     [r8], rdi
0x180031bd8  add     qword ptr [rsi+8], 8
0x180031bdd  test    r14, r14
0x180031be0  jz      short loc_180031C07
0x180031be2  lea     rax, [r14+10h]
0x180031be6  cmp     [r14], rax
0x180031be9  jz      short loc_180031BFA
0x180031beb  mov     rcx, [r14]; void *
0x180031bee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031bf5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031bfa  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180031bff  mov     rcx, r14; void *
0x180031c02  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031c07  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180031c0c  lea     r9, [rsp+8C0h+cchName]; lpcchName
0x180031c11  mov     [rsp+8C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180031c16  lea     r8, [rsp+8C0h+Name]; lpName
0x180031c1b  mov     [rsp+8C0h+lpcchClass], r12; lpcchClass
0x180031c20  mov     edx, r15d; dwIndex
0x180031c23  mov     [rsp+8C0h+lpClass], r12; lpClass
0x180031c28  mov     [rsp+8C0h+phkResult], r12; lpReserved
0x180031c2d  mov     [rsp+8C0h+cchName], 401h
0x180031c35  call    cs:__imp_RegEnumKeyExW
0x180031c3b  cmp     eax, 103h
0x180031c40  jz      loc_180031CD6
0x180031c46  add     r15d, ebx
0x180031c49  jmp     loc_180031B05
0x180031c4e  sub     r8, rdx
0x180031c51  mov     [rsi+8], rdx
0x180031c55  sar     r8, 3
0x180031c59  mov     ebx, 8007000Eh
0x180031c5e  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCWprcInstance@@U?$default_delete@VCWprcInstance@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCWprcInstance@@U?$default_delete@VCWprcInstance@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCWprcInstance@@U?$default_delete@VCWprcInstance@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWprcInstance,utl::default_delete<CWprcInstance>>>>(utl::allocator<utl::unique_ptr<CWprcInstance,utl::default_delete<CWprcInstance>>> &,utl::unique_ptr<CWprcInstance,utl::default_delete<CWprcInstance>> *,unsigned __int64)
0x180031c63  test    rdi, rdi
0x180031c66  jz      short loc_180031CD9
0x180031c68  lea     rax, [rdi+10h]
0x180031c6c  cmp     [rdi], rax
0x180031c6f  jz      short loc_180031C80
0x180031c71  mov     rcx, [rdi]; void *
0x180031c74  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031c7b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031c80  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180031c85  mov     rcx, rdi; void *
0x180031c88  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031c8d  jmp     short loc_180031CD9
0x180031c8f  lea     rax, [rdi+10h]
0x180031c93  cmp     [rdi], rax
0x180031c96  jz      short loc_180031CA7
0x180031c98  mov     rcx, [rdi]; void *
0x180031c9b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031ca2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031ca7  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180031cac  mov     rcx, rdi; void *
0x180031caf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031cb4  mov     ebx, 8007000Eh
0x180031cb9  jmp     short loc_180031CD9
0x180031cbb  jg      short loc_180031CC1
0x180031cbd  mov     ebx, eax
0x180031cbf  jmp     short loc_180031CCA
0x180031cc1  movzx   ebx, ax
0x180031cc4  or      ebx, 80070000h
0x180031cca  test    ebx, ebx
0x180031ccc  mov     eax, 80004005h
0x180031cd1  cmovns  ebx, eax
0x180031cd4  jmp     short loc_180031CD9
0x180031cd6  mov     ebx, r12d
0x180031cd9  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180031cde  test    rcx, rcx
0x180031ce1  jz      short loc_180031CE9
0x180031ce3  call    cs:__imp_RegCloseKey
0x180031ce9  mov     eax, ebx
0x180031ceb  mov     rcx, [rbp+7C0h+var_50]
0x180031cf2  xor     rcx, rsp; StackCookie
0x180031cf5  call    __security_check_cookie
0x180031cfa  add     rsp, 888h
0x180031d01  pop     r15
0x180031d03  pop     r14
0x180031d05  pop     r13
0x180031d07  pop     r12
0x180031d09  pop     rdi
0x180031d0a  pop     rsi
0x180031d0b  pop     rbx
0x180031d0c  pop     rbp
0x180031d0d  retn
```
