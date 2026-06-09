# DllMain

- ea: `0x18000a98c`
- end: `0x18000ab6c`
- name: `DllMain`
- size: `480`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001724`

## callees

- `0x1800097dc`
- `0x18000a98c`
- `0x18000ebd4`
- `0x180010bc4`
- `0x18008cd30`
- `0x18008cda0`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x18000aa7d`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000aa7d`
- `KERNEL32!DeleteCriticalSection` at `0x18000ab3a`
- `KERNEL32!DeleteCriticalSection` at `0x18000ab3a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000aa01`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000aa01`

## string_xrefs

- `0x18000a9fa`: `%ProgramData%\Microsoft\FCI`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // r8
  void **v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 *v8; // rdi
  __int64 *v9; // rax
  WCHAR Dst; // [rsp+30h] [rbp-228h] BYREF
  _BYTE v12[526]; // [rsp+32h] [rbp-226h] BYREF

  if ( fdwReason == 1 )
  {
    qword_18011A300 = (__int64)hinstDLL;
    try
    {
      CSrmSharedLock::Initialize((CSrmSharedLock *)&g_LockDbGlobal);
      CSrmSharedLock::Initialize((CSrmSharedLock *)&g_LockConfigGlobal);
      Dst = 0;
      memset_0(v12, 0, 0x208u);
      ExpandEnvironmentStringsW(L"%ProgramData%\\Microsoft\\FCI", &Dst, 0x104u);
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)&v12[2 * v4 - 2] );
      std::wstring::assign(&CGlobalStoreManager::s_strStoreRootPath, &Dst);
      v5 = &CGlobalStoreManager::s_strStoreRootPath;
      if ( (unsigned __int64)qword_180119D10 >= 8 )
        v5 = (void **)CGlobalStoreManager::s_strStoreRootPath;
      if ( *((_WORD *)v5 + qword_180119D08 - 1) != 92 )
        std::wstring::append(&CGlobalStoreManager::s_strStoreRootPath, (void *)L"\\");
    }
    catch ( ... )
    {
      return 0;
    }
    DisableThreadLibraryCalls(hinstDLL);
  }
  else if ( !fdwReason )
  {
    v6 = qword_18011A408;
    if ( qword_18011A408 )
    {
      while ( *(_QWORD *)v6 )
      {
        v7 = *(_QWORD *)(v6 + 32);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        *(_QWORD *)(v6 + 32) = 0;
        (*(void (__fastcall **)(_QWORD))(v6 + 64))(0);
        v6 += 72;
      }
    }
    v8 = off_180119A00[0];
    v9 = off_180119A08;
    while ( v8 < v9 )
    {
      if ( *v8 )
      {
        (*(void (__fastcall **)(_QWORD))(*v8 + 64))(0);
        v9 = off_180119A08;
      }
      ++v8;
    }
    ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
    CSrmSharedLock::Uninitialize((CSrmSharedLock *)&g_LockConfigGlobal);
    CSrmSharedLock::Uninitialize((CSrmSharedLock *)&g_LockDbGlobal);
    if ( byte_18011A498 )
    {
      DeleteCriticalSection(&CClassManager::s_lockSharedPipeline);
      byte_18011A498 = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000a98c  mov     [rsp+arg_8], rbx
0x18000a991  push    rdi
0x18000a992  sub     rsp, 250h
0x18000a999  mov     rax, cs:__security_cookie
0x18000a9a0  xor     rax, rsp
0x18000a9a3  mov     [rsp+258h+var_18], rax
0x18000a9ab  mov     rdi, rcx
0x18000a9ae  cmp     edx, 1
0x18000a9b1  jnz     loc_18000AA8F
0x18000a9b7  mov     cs:qword_18011A300, rcx
0x18000a9be  lea     rcx, ?g_LockDbGlobal@@3VCSrmSharedLock@@A; this
0x18000a9c5  call    ?Initialize@CSrmSharedLock@@UEAAXXZ; CSrmSharedLock::Initialize(void)
0x18000a9ca  lea     rcx, ?g_LockConfigGlobal@@3VCSrmSharedLock@@A; this
0x18000a9d1  call    ?Initialize@CSrmSharedLock@@UEAAXXZ; CSrmSharedLock::Initialize(void)
0x18000a9d6  xor     ebx, ebx
0x18000a9d8  mov     [rsp+258h+Dst], bx
0x18000a9dd  xor     edx, edx; Val
0x18000a9df  mov     r8d, 208h; Size
0x18000a9e5  lea     rcx, [rsp+258h+var_226]; void *
0x18000a9ea  call    memset_0
0x18000a9ef  mov     r8d, 104h; nSize
0x18000a9f5  lea     rdx, [rsp+258h+Dst]; lpDst
0x18000a9fa  lea     rcx, Src; "%ProgramData%\\Microsoft\\FCI"
0x18000aa01  call    cs:__imp_ExpandEnvironmentStringsW
0x18000aa07  lea     rax, [rsp+258h+Dst]
0x18000aa0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000aa10  inc     r8
0x18000aa13  cmp     [rax+r8*2], bx
0x18000aa18  jnz     short loc_18000AA10
0x18000aa1a  lea     rdx, [rsp+258h+Dst]; Src
0x18000aa1f  lea     rbx, ?s_strStoreRootPath@CGlobalStoreManager@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CGlobalStoreManager::s_strStoreRootPath
0x18000aa26  mov     rcx, rbx; void *
0x18000aa29  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000aa2e  mov     rcx, rbx
0x18000aa31  cmp     cs:qword_180119D10, 8
0x18000aa39  cmovnb  rcx, cs:?s_strStoreRootPath@CGlobalStoreManager@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CGlobalStoreManager::s_strStoreRootPath
0x18000aa41  mov     rax, cs:qword_180119D08
0x18000aa48  lea     rax, [rcx+rax*2]
0x18000aa4c  mov     [rsp+258h+var_238], rax
0x18000aa51  mov     [rsp+258h+var_238], rax
0x18000aa56  mov     [rsp+258h+var_238], rax
0x18000aa5b  add     rax, 0FFFFFFFFFFFFFFFEh
0x18000aa5f  mov     [rsp+258h+var_238], rax
0x18000aa64  cmp     word ptr [rax], 5Ch ; '\'
0x18000aa68  jz      short loc_18000AA7A
0x18000aa6a  lea     rdx, psz; "\\"
0x18000aa71  mov     rcx, rbx; Src
0x18000aa74  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000aa79  nop
0x18000aa7a  mov     rcx, rdi; hLibModule
0x18000aa7d  call    cs:__imp_DisableThreadLibraryCalls
0x18000aa83  jmp     loc_18000AB46
0x18000aa88  xor     eax, eax
0x18000aa8a  jmp     loc_18000AB4B
0x18000aa8f  xor     ebx, ebx
0x18000aa91  test    edx, edx
0x18000aa93  jnz     loc_18000AB46
0x18000aa99  mov     rdi, cs:qword_18011A408
0x18000aaa0  test    rdi, rdi
0x18000aaa3  jz      short loc_18000AAD4
0x18000aaa5  jmp     short loc_18000AACF
0x18000aaa7  mov     rcx, [rdi+20h]
0x18000aaab  test    rcx, rcx
0x18000aaae  jz      short loc_18000AABC
0x18000aab0  mov     rax, [rcx]
0x18000aab3  mov     rax, [rax+10h]
0x18000aab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aabc  mov     [rdi+20h], rbx
0x18000aac0  xor     ecx, ecx
0x18000aac2  mov     rax, [rdi+40h]
0x18000aac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aacb  add     rdi, 48h ; 'H'
0x18000aacf  cmp     [rdi], rbx
0x18000aad2  jnz     short loc_18000AAA7
0x18000aad4  mov     rdi, cs:off_180119A00
0x18000aadb  mov     rax, cs:off_180119A08
0x18000aae2  jmp     short loc_18000AB02
0x18000aae4  mov     rdx, [rdi]
0x18000aae7  test    rdx, rdx
0x18000aaea  jz      short loc_18000AAFE
0x18000aaec  xor     ecx, ecx
0x18000aaee  mov     rax, [rdx+40h]
0x18000aaf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaf7  mov     rax, cs:off_180119A08
0x18000aafe  add     rdi, 8
0x18000ab02  cmp     rdi, rax
0x18000ab05  jb      short loc_18000AAE4
0x18000ab07  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000ab0e  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000ab13  lea     rcx, ?g_LockConfigGlobal@@3VCSrmSharedLock@@A; this
0x18000ab1a  call    ?Uninitialize@CSrmSharedLock@@UEAAXXZ; CSrmSharedLock::Uninitialize(void)
0x18000ab1f  lea     rcx, ?g_LockDbGlobal@@3VCSrmSharedLock@@A; this
0x18000ab26  call    ?Uninitialize@CSrmSharedLock@@UEAAXXZ; CSrmSharedLock::Uninitialize(void)
0x18000ab2b  cmp     cs:byte_18011A498, bl
0x18000ab31  jz      short loc_18000AB46
0x18000ab33  lea     rcx, ?s_lockSharedPipeline@CClassManager@@2VCSrmCriticalSection@@A; lpCriticalSection
0x18000ab3a  call    cs:__imp_DeleteCriticalSection
0x18000ab40  mov     cs:byte_18011A498, bl
0x18000ab46  mov     eax, 1
0x18000ab4b  mov     rcx, [rsp+258h+var_18]
0x18000ab53  xor     rcx, rsp; StackCookie
0x18000ab56  call    __security_check_cookie
0x18000ab5b  mov     rbx, [rsp+258h+arg_8]
0x18000ab63  add     rsp, 250h
0x18000ab6a  pop     rdi
0x18000ab6b  retn
```
