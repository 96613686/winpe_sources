# ConsentCoordinationHelpers::EnsureACLOnRegistryKey(winrt::hstring)

- ea: `0x180024144`
- end: `0x180024600`
- name: `?EnsureACLOnRegistryKey@ConsentCoordinationHelpers@@YAXUhstring@winrt@@@Z`
- size: `1212`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029504`

## callees

- `0x180002810`
- `0x180002834`
- `0x180003210`
- `0x180003384`
- `0x1800034f7`
- `0x1800035ab`
- `0x18000ebfc`
- `0x18000f44c`
- `0x1800139fc`
- `0x18001dcd4`
- `0x18001e8d4`
- `0x180021cf4`
- `0x180022808`
- `0x180023180`
- `0x180024144`
- `0x18002d268`
- `0x18002d284`
- `0x18003060c`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180024550`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180024550`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180024546`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180024546`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024239`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800245b4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024239`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800245b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800244e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002450c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800244e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002450c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800244bb`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800244bb`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800242a2`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800242a2`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002446a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002446a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800243ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800243ca`
- `api-ms-win-security-trustee-l1-1-1!GetEffectiveRightsFromAclW` at `0x180024403`
- `api-ms-win-security-trustee-l1-1-1!GetEffectiveRightsFromAclW` at `0x180024403`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
int __fastcall ConsentCoordinationHelpers::EnsureACLOnRegistryKey(volatile signed __int32 **a1, unsigned int a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rsi
  void *v4; // rbx
  int v5; // eax
  HANDLE ProcessHeap; // rax
  __int64 v7; // rax
  const WCHAR *v8; // rdx
  __int64 v9; // rax
  DWORD NamedSecurityInfoW; // eax
  struct _EXPLICIT_ACCESS_W *v11; // rbx
  void *v12; // rsi
  unsigned __int64 v13; // rdx
  ULONG v14; // esi
  __int64 v15; // r15
  const WCHAR *v16; // rcx
  PSID *v17; // r13
  void *v18; // rdx
  unsigned int v19; // r8d
  const char *v20; // r9
  __int64 v21; // rax
  DWORD v22; // eax
  struct _ACL *v23; // rsi
  __int64 v24; // rax
  DWORD v25; // eax
  unsigned __int64 v26; // rdx
  int result; // eax
  volatile signed __int32 *v28; // rbx
  int v29; // r14d
  HANDLE v30; // rax
  unsigned int ppsidGroup; // [rsp+20h] [rbp-E0h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-E0h]
  DWORD pAccessRights[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h]
  PACL pacl; // [rsp+60h] [rbp-A0h] BYREF
  void *v37; // [rsp+68h] [rbp-98h]
  PSECURITY_DESCRIPTOR hMem; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h]
  volatile signed __int32 **v40; // [rsp+80h] [rbp-80h]
  struct _EXPLICIT_ACCESS_W *v41; // [rsp+88h] [rbp-78h]
  void *v42; // [rsp+90h] [rbp-70h]
  int v43; // [rsp+9Ch] [rbp-64h]
  _QWORD v44[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v45[8]; // [rsp+B0h] [rbp-50h] BYREF
  char v46[8]; // [rsp+B8h] [rbp-48h] BYREF
  char v47[120]; // [rsp+C0h] [rbp-40h] BYREF
  char v48[104]; // [rsp+138h] [rbp+38h] BYREF
  __m256i v49; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 pTrustee_16; // [rsp+1C0h] [rbp+C0h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v40 = a1;
  v34 = 0;
  v35 = 0;
  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x60, a2);
  memcpy_s(
    (char *)v3 + 28,
    0xC0u,
    L"S-1-15-3-1024-3167453650-624722384-889205278-321484983-714554697-3592933102-807660695-1632717421",
    0xC0u);
  *(_QWORD *)pAccessRights = v3;
  std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(&v34, 0, pAccessRights);
  v4 = *(void **)pAccessRights;
  if ( *(_QWORD *)pAccessRights )
  {
    v5 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)pAccessRights + 24LL));
    if ( v5 )
    {
      if ( v5 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v4);
    }
  }
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v44);
  v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, L"CURRENT_USER\\");
  if ( *a1 )
    v8 = (const WCHAR *)*((_QWORD *)*a1 + 2);
  else
    v8 = &Name;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, v8);
  pacl = 0;
  hMem = 0;
  v9 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
         v44,
         &v49);
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v9 = *(_QWORD *)v9;
  NamedSecurityInfoW = GetNamedSecurityInfoW((LPCWSTR)v9, SE_REGISTRY_KEY, 4u, 0, 0, &pacl, 0, &hMem);
  if ( NamedSecurityInfoW )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\inc\\ConsentCoordinationHelpers.h",
      (const char *)NamedSecurityInfoW,
      ppsidGroup);
  std::wstring::_Tidy_deallocate(&v49);
  v11 = (struct _EXPLICIT_ACCESS_W *)operator new[](0x480u);
  memset_0(v11, 0, 0x480u);
  v41 = v11;
  memset_0(v11, 0, 48 * ((__int64)(*((_QWORD *)&v34 + 1) - v34) >> 3));
  v12 = operator new[](0xC0u);
  v37 = v12;
  memset_0(v12, 0, 0xC0u);
  v42 = v12;
  memset_0(v12, 0, (*((_QWORD *)&v34 + 1) - v34) & 0xFFFFFFFFFFFFFFF8uLL);
  v14 = 0;
  v39 = *((_QWORD *)&v34 + 1);
  v15 = v34;
  if ( (_QWORD)v34 != *((_QWORD *)&v34 + 1) )
  {
    do
    {
      memset((char *)&v49.m256i_u64[1] + 4, 0, 20);
      pTrustee_16 = 2u;
      v49.m256i_i64[0] = 0x110000000LL;
      v49.m256i_i32[2] = 3;
      if ( *(_QWORD *)v15 )
        v16 = *(const WCHAR **)(*(_QWORD *)v15 + 16LL);
      else
        v16 = &Name;
      v17 = (PSID *)((char *)v37 + 8 * v14);
      if ( !ConvertStringSidToSidW(v16, v17) )
        wil::details::in1diag3::_Throw_GetLastError(retaddr, v18, v19, v20);
      *((_QWORD *)&pTrustee_16 + 1) = *v17;
      pAccessRights[0] = 0;
      GetEffectiveRightsFromAclW(pacl, (PTRUSTEE_W)&v49.m256i_u64[2], pAccessRights);
      if ( pAccessRights[0] != 983103 )
      {
        v21 = v14;
        *(__m256i *)&v11[v21].grfAccessPermissions = v49;
        *(_OWORD *)&v11[v21].Trustee.TrusteeType = pTrustee_16;
        ++v14;
      }
      v15 += 8;
    }
    while ( v15 != v39 );
    if ( v14 )
    {
      *(_QWORD *)pAccessRights = 0;
      v22 = SetEntriesInAclW(v14, v11, pacl, (PACL *)pAccessRights);
      if ( v22 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\inc\\ConsentCoordinationHelpers.h",
          (const char *)v22,
          ppsidGroup);
      v23 = *(struct _ACL **)pAccessRights;
      v24 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
              v44,
              &v49);
      if ( *(_QWORD *)(v24 + 24) > 7u )
        v24 = *(_QWORD *)v24;
      v25 = SetNamedSecurityInfoW((LPWSTR)v24, SE_REGISTRY_KEY, 4u, 0, 0, v23, 0);
      if ( v25 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x68,
          (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\inc\\ConsentCoordinationHelpers.h",
          (const char *)v25,
          ppsidGroupa);
      std::wstring::_Tidy_deallocate(&v49);
      if ( *(_QWORD *)pAccessRights )
        LocalFree(*(HLOCAL *)pAccessRights);
    }
  }
  operator delete(v37, v13);
  operator delete(v11, v26);
  if ( hMem )
    LocalFree(hMem);
  *(_QWORD *)((char *)v44 + *(int *)(v44[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(int *)((char *)&v43 + *(int *)(v44[0] + 4LL)) = *(_DWORD *)(v44[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v46);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v47);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v48);
  result = std::vector<winrt::hstring>::~vector<winrt::hstring>(&v34);
  v28 = *a1;
  if ( *a1 )
  {
    v29 = _InterlockedDecrement(v28 + 6);
    if ( v29 )
    {
      if ( v29 < 0 )
        abort();
    }
    else
    {
      v30 = WINRT_IMPL_GetProcessHeap();
      result = WINRT_IMPL_HeapFree(v30, 0, (LPVOID)v28);
    }
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180024144  push    rbp
0x180024146  push    rbx
0x180024147  push    rsi
0x180024148  push    rdi
0x180024149  push    r12
0x18002414b  push    r13
0x18002414d  push    r14
0x18002414f  push    r15
0x180024151  lea     rbp, [rsp-0E8h]
0x180024159  sub     rsp, 1E8h
0x180024160  mov     rax, cs:__security_cookie
0x180024167  xor     rax, rsp
0x18002416a  mov     [rbp+120h+var_50], rax
0x180024171  mov     rdi, rcx
0x180024174  mov     [rbp+120h+var_1A0], rcx
0x180024178  xor     r13d, r13d
0x18002417b  xorps   xmm0, xmm0
0x18002417e  movdqu  [rsp+220h+var_1D8], xmm0
0x180024184  mov     [rsp+220h+var_1C8], r13
0x180024189  lea     ecx, [r13+60h]; this
0x18002418d  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180024192  mov     rsi, rax
0x180024195  lea     rcx, [rax+1Ch]; Destination
0x180024199  mov     r15d, 0C0h
0x18002419f  mov     r9d, r15d; SourceSize
0x1800241a2  lea     r8, aS1153102431674; "S-1-15-3-1024-3167453650-624722384-8892"...
0x1800241a9  mov     edx, r15d; DestinationSize
0x1800241ac  call    memcpy_s
0x1800241b1  mov     qword ptr [rsp+220h+pAccessRights], rsi
0x1800241b6  mov     rdx, qword ptr [rsp+220h+var_1D8+8]
0x1800241bb  cmp     rdx, [rsp+220h+var_1C8]
0x1800241c0  jz      short loc_1800241D0
0x1800241c2  mov     ebx, r13d
0x1800241c5  mov     [rdx], rsi
0x1800241c8  add     qword ptr [rsp+220h+var_1D8+8], 8
0x1800241ce  jmp     short loc_1800241E4
0x1800241d0  lea     r8, [rsp+220h+pAccessRights]
0x1800241d5  lea     rcx, [rsp+220h+var_1D8]
0x1800241da  call    ??$_Emplace_reallocate@Uhstring@winrt@@@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAPEAUhstring@winrt@@QEAU23@$$QEAU23@@Z; std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(winrt::hstring * const,winrt::hstring &&)
0x1800241df  mov     rbx, qword ptr [rsp+220h+pAccessRights]
0x1800241e4  or      r14d, 0FFFFFFFFh
0x1800241e8  test    rbx, rbx
0x1800241eb  jz      short loc_18002420D
0x1800241ed  mov     eax, r14d
0x1800241f0  lock xadd [rbx+18h], eax
0x1800241f5  sub     eax, 1
0x1800241f8  jnz     short loc_180024235
0x1800241fa  nop
0x1800241fb  call    WINRT_IMPL_GetProcessHeap
0x180024200  mov     rcx, rax; hHeap
0x180024203  mov     r8, rbx; lpMem
0x180024206  xor     edx, edx; dwFlags
0x180024208  call    WINRT_IMPL_HeapFree
0x18002420d  lea     rcx, [rbp+120h+var_180]
0x180024211  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180024216  nop
0x180024217  lea     rdx, aCurrentUser; "CURRENT_USER\\"
0x18002421e  lea     rcx, [rbp+120h+var_170]
0x180024222  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180024227  mov     rdx, [rdi]
0x18002422a  test    rdx, rdx
0x18002422d  jz      short loc_180024240
0x18002422f  mov     rdx, [rdx+10h]
0x180024233  jmp     short loc_180024247
0x180024235  test    eax, eax
0x180024237  jns     short loc_18002420D
0x180024239  call    cs:__imp_abort
0x180024240  lea     rdx, Name
0x180024247  mov     rcx, rax
0x18002424a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002424f  nop
0x180024250  mov     [rsp+220h+pacl], r13
0x180024255  mov     [rsp+220h+hMem], r13
0x18002425a  lea     rdx, [rbp+120h+var_80]
0x180024261  lea     rcx, [rbp+120h+var_180]
0x180024265  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x18002426a  nop
0x18002426b  cmp     qword ptr [rax+18h], 7
0x180024270  jbe     short loc_180024275
0x180024272  mov     rax, [rax]
0x180024275  lea     rcx, [rsp+220h+hMem]
0x18002427a  mov     [rsp+220h+ppSecurityDescriptor], rcx; ppSecurityDescriptor
0x18002427f  mov     [rsp+220h+ppSacl], r13; ppSacl
0x180024284  lea     rcx, [rsp+220h+pacl]
0x180024289  mov     [rsp+220h+ppDacl], rcx; ppDacl
0x18002428e  mov     [rsp+220h+ppsidGroup], r13; unsigned int
0x180024293  xor     r9d, r9d; ppsidOwner
0x180024296  lea     ecx, [r9+4]
0x18002429a  mov     r8d, ecx; SecurityInfo
0x18002429d  mov     edx, ecx; ObjectType
0x18002429f  mov     rcx, rax; pObjectName
0x1800242a2  call    cs:__imp_GetNamedSecurityInfoW
0x1800242a8  mov     rcx, [rbp+128h]; this
0x1800242af  test    eax, eax
0x1800242b1  jnz     loc_1800245C1
0x1800242b7  lea     rcx, [rbp+120h+var_80]
0x1800242be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800242c3  mov     esi, 480h
0x1800242c8  mov     ecx, esi; unsigned __int64
0x1800242ca  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800242cf  mov     rbx, rax
0x1800242d2  mov     r8d, esi; Size
0x1800242d5  xor     edx, edx; Val
0x1800242d7  mov     rcx, rax; void *
0x1800242da  call    memset_0
0x1800242df  mov     [rbp+120h+var_198], rbx
0x1800242e3  mov     rcx, qword ptr [rsp+220h+var_1D8+8]
0x1800242e8  sub     rcx, qword ptr [rsp+220h+var_1D8]
0x1800242ed  sar     rcx, 3
0x1800242f1  lea     r8, [rcx+rcx*2]
0x1800242f5  shl     r8, 4; Size
0x1800242f9  xor     edx, edx; Val
0x1800242fb  mov     rcx, rbx; void *
0x1800242fe  call    memset_0
0x180024303  mov     rcx, r15; unsigned __int64
0x180024306  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002430b  mov     rsi, rax
0x18002430e  mov     [rsp+220h+var_1B8], rax
0x180024313  mov     r8, r15; Size
0x180024316  xor     edx, edx; Val
0x180024318  mov     rcx, rax; void *
0x18002431b  call    memset_0
0x180024320  mov     [rbp+120h+var_190], rsi
0x180024324  mov     r8, qword ptr [rsp+220h+var_1D8+8]
0x180024329  sub     r8, qword ptr [rsp+220h+var_1D8]
0x18002432e  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180024332  xor     edx, edx; Val
0x180024334  mov     rcx, rsi; void *
0x180024337  call    memset_0
0x18002433c  mov     esi, r13d
0x18002433f  mov     r15, qword ptr [rsp+220h+var_1D8]
0x180024344  mov     rax, qword ptr [rsp+220h+var_1D8+8]
0x180024349  mov     [rsp+220h+var_1A8], rax
0x18002434e  cmp     r15, rax
0x180024351  jz      loc_1800244EE
0x180024357  mov     qword ptr [rbp+120h+var_80+0Ch], r13
0x18002435e  mov     [rbp+120h+pTrustee.pMultipleTrustee+4], 0
0x180024369  mov     qword ptr [rbp+120h+pTrustee+14h], r13
0x180024370  mov     dword ptr [rbp+120h+pTrustee.ptstrName+4], r13d
0x180024377  mov     dword ptr [rbp+120h+var_80], 10000000h
0x180024381  mov     dword ptr [rbp+120h+var_80+4], 1
0x18002438b  mov     dword ptr [rbp+120h+var_80+8], 3
0x180024395  mov     [rbp+120h+pTrustee.TrusteeForm], r13d
0x18002439c  mov     [rbp+120h+pTrustee.TrusteeType], 2
0x1800243a6  mov     rax, [r15]
0x1800243a9  test    rax, rax
0x1800243ac  jz      short loc_1800243B4
0x1800243ae  mov     rcx, [rax+10h]
0x1800243b2  jmp     short loc_1800243BB
0x1800243b4  lea     rcx, Name; StringSid
0x1800243bb  mov     r12d, esi
0x1800243be  mov     rax, [rsp+220h+var_1B8]
0x1800243c3  lea     r13, [rax+r12*8]
0x1800243c7  mov     rdx, r13; Sid
0x1800243ca  call    cs:__imp_ConvertStringSidToSidW
0x1800243d0  mov     rcx, [rbp+128h]; this
0x1800243d7  test    eax, eax
0x1800243d9  jz      loc_1800245BB
0x1800243df  mov     rax, [r13+0]
0x1800243e3  mov     [rbp+120h+pTrustee.ptstrName], rax
0x1800243ea  xor     r13d, r13d
0x1800243ed  mov     [rsp+220h+pAccessRights], r13d
0x1800243f2  lea     r8, [rsp+220h+pAccessRights]; pAccessRights
0x1800243f7  lea     rdx, [rbp+120h+pTrustee]; pTrustee
0x1800243fe  mov     rcx, [rsp+220h+pacl]; pacl
0x180024403  call    cs:__imp_GetEffectiveRightsFromAclW
0x180024409  cmp     [rsp+220h+pAccessRights], 0F003Fh
0x180024411  jz      short loc_18002443F
0x180024413  lea     rax, [r12+r12*2]
0x180024417  add     rax, rax
0x18002441a  movups  xmm0, [rbp+120h+var_80]
0x180024421  movups  xmmword ptr [rbx+rax*8], xmm0
0x180024425  movups  xmm1, xmmword ptr [rbp+0B0h]
0x18002442c  movups  xmmword ptr [rbx+rax*8+10h], xmm1
0x180024431  movups  xmm0, xmmword ptr [rbp+120h+pTrustee.TrusteeType]
0x180024438  movups  xmmword ptr [rbx+rax*8+20h], xmm0
0x18002443d  inc     esi
0x18002443f  add     r15, 8
0x180024443  cmp     r15, [rsp+220h+var_1A8]
0x180024448  jnz     loc_180024357
0x18002444e  test    esi, esi
0x180024450  jz      loc_1800244EE
0x180024456  mov     qword ptr [rsp+220h+pAccessRights], r13
0x18002445b  lea     r9, [rsp+220h+pAccessRights]; NewAcl
0x180024460  mov     r8, [rsp+220h+pacl]; OldAcl
0x180024465  mov     rdx, rbx; pListOfExplicitEntries
0x180024468  mov     ecx, esi; cCountOfExplicitEntries
0x18002446a  call    cs:__imp_SetEntriesInAclW
0x180024470  mov     rcx, [rbp+128h]; this
0x180024477  test    eax, eax
0x180024479  jnz     loc_1800245D6
0x18002447f  mov     rsi, qword ptr [rsp+220h+pAccessRights]
0x180024484  lea     rdx, [rbp+120h+var_80]
0x18002448b  lea     rcx, [rbp+120h+var_180]
0x18002448f  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x180024494  nop
0x180024495  cmp     qword ptr [rax+18h], 7
0x18002449a  jbe     short loc_18002449F
0x18002449c  mov     rax, [rax]
0x18002449f  mov     [rsp+220h+ppSacl], r13; pSacl
0x1800244a4  mov     [rsp+220h+ppDacl], rsi; pDacl
0x1800244a9  mov     [rsp+220h+ppsidGroup], r13; unsigned int
0x1800244ae  xor     r9d, r9d; psidOwner
0x1800244b1  lea     edx, [r9+4]; ObjectType
0x1800244b5  mov     r8d, edx; SecurityInfo
0x1800244b8  mov     rcx, rax; pObjectName
0x1800244bb  call    cs:__imp_SetNamedSecurityInfoW
0x1800244c1  mov     rcx, [rbp+128h]; this
0x1800244c8  test    eax, eax
0x1800244ca  jnz     loc_1800245EB
0x1800244d0  lea     rcx, [rbp+120h+var_80]
0x1800244d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800244dc  nop
0x1800244dd  mov     rcx, qword ptr [rsp+220h+pAccessRights]; hMem
0x1800244e2  test    rcx, rcx
0x1800244e5  jz      short loc_1800244EE
0x1800244e7  call    cs:__imp_LocalFree
0x1800244ed  nop
0x1800244ee  mov     rcx, [rsp+220h+var_1B8]; void *
0x1800244f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800244f8  nop
0x1800244f9  mov     rcx, rbx; void *
0x1800244fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024501  nop
0x180024502  mov     rcx, [rsp+220h+hMem]; hMem
0x180024507  test    rcx, rcx
0x18002450a  jz      short loc_180024513
0x18002450c  call    cs:__imp_LocalFree
0x180024512  nop
0x180024513  mov     rax, [rbp+120h+var_180]
0x180024517  movsxd  rcx, dword ptr [rax+4]
0x18002451b  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x180024522  mov     [rbp+rcx+120h+var_180], rax
0x180024527  mov     rax, [rbp+120h+var_180]
0x18002452b  movsxd  rcx, dword ptr [rax+4]
0x18002452f  lea     edx, [rcx-98h]
0x180024535  mov     [rbp+rcx+120h+var_184], edx
0x180024539  lea     rcx, [rbp+120h+var_168]
0x18002453d  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x180024542  lea     rcx, [rbp+120h+var_160]
0x180024546  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x18002454c  lea     rcx, [rbp+120h+var_E8]
0x180024550  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180024556  nop
0x180024557  lea     rcx, [rsp+220h+var_1D8]
0x18002455c  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x180024561  nop
0x180024562  mov     rbx, [rdi]
0x180024565  test    rbx, rbx
0x180024568  jz      short loc_18002458C
0x18002456a  lock xadd [rbx+18h], r14d
0x180024570  sub     r14d, 1
0x180024574  jnz     short loc_1800245AF
0x180024576  nop
0x180024577  call    WINRT_IMPL_GetProcessHeap
0x18002457c  mov     rcx, rax; hHeap
0x18002457f  mov     r8, rbx; lpMem
0x180024582  xor     edx, edx; dwFlags
0x180024584  call    WINRT_IMPL_HeapFree
0x180024589  mov     [rdi], r13
0x18002458c  mov     rcx, [rbp+120h+var_50]
0x180024593  xor     rcx, rsp; StackCookie
0x180024596  call    __security_check_cookie
0x18002459b  add     rsp, 1E8h
0x1800245a2  pop     r15
0x1800245a4  pop     r14
0x1800245a6  pop     r13
0x1800245a8  pop     r12
0x1800245aa  pop     rdi
0x1800245ab  pop     rsi
0x1800245ac  pop     rbx
0x1800245ad  pop     rbp
0x1800245ae  retn
0x1800245af  test    r14d, r14d
0x1800245b2  jns     short loc_180024589
0x1800245b4  call    cs:__imp_abort
0x1800245bb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800245c1  mov     r9d, eax; char *
0x1800245c4  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\consentux\\unifiedco"...
0x1800245cb  mov     edx, 38h ; '8'; void *
0x1800245d0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800245d6  mov     r9d, eax; char *
0x1800245d9  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\consentux\\unifiedco"...
0x1800245e0  mov     edx, 5Fh ; '_'; void *
0x1800245e5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800245eb  mov     r9d, eax; char *
0x1800245ee  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\consentux\\unifiedco"...
0x1800245f5  mov     edx, 68h ; 'h'; void *
0x1800245fa  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
