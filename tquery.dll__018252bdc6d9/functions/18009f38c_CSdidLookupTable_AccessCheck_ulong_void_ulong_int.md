# CSdidLookupTable::AccessCheck(ulong,void *,ulong,int &)

- ea: `0x18009f38c`
- end: `0x18009f6d3`
- name: `?AccessCheck@CSdidLookupTable@@QEAAHKPEAXKAEAH@Z`
- size: `839`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int, HANDLE ClientToken, DWORD DesiredAccess, LPBOOL)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009f2e0`

## callees

- `0x180038f08`
- `0x18008c14c`
- `0x180098390`
- `0x18009ef88`
- `0x18009f11c`
- `0x18009f38c`
- `0x1800fe8d4`
- `0x180101020`
- `0x180104608`
- `0x18010ed30`
- `0x18013e868`
- `0x18015aa68`
- `0x1801781b0`
- `0x180188d90`
- `0x1801ae5e4`
- `0x1801fbf10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f401`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f401`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f429`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f434`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f429`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f54d`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18009f53c`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18009f53c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f5b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f5b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f674`
- `ntdll!RtlNtStatusToDosError` at `0x18009f69c`
- `ntdll!RtlNtStatusToDosError` at `0x18009f69c`

## string_xrefs

- `0x18009f556`: `[Query] CSdidLookupTable::AccessCheck failed, GetLastError is %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSdidLookupTable::AccessCheck(
        LPCRITICAL_SECTION lpCriticalSection,
        int a2,
        HANDLE ClientToken,
        DWORD DesiredAccess,
        LPBOOL AccessStatus)
{
  DWORD v10; // r8d
  PSECURITY_DESCRIPTOR v11; // r15
  __int64 v12; // r8
  unsigned int v13; // r13d
  DWORD LastError; // eax
  __int64 v15; // rdi
  __int64 v16; // r14
  __int64 v17; // rax
  NTSTATUS v18; // eax
  void *v19; // rcx
  PSECURITY_DESCRIPTOR v20; // rcx
  signed int v21; // eax
  const char *v22; // r9
  int PrivilegeSet; // [rsp+20h] [rbp-118h]
  _BYTE v24[4]; // [rsp+40h] [rbp-F8h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-F4h] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-F0h] BYREF
  __int128 v27; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-D8h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp-D0h] BYREF
  __int128 v30; // [rsp+70h] [rbp-C8h] BYREF
  _BYTE v31[24]; // [rsp+80h] [rbp-B8h] BYREF
  _BYTE v32[16]; // [rsp+98h] [rbp-A0h] BYREF
  _BYTE v33[32]; // [rsp+A8h] [rbp-90h] BYREF
  __int128 v34; // [rsp+C8h] [rbp-70h] BYREF
  __int64 v35; // [rsp+D8h] [rbp-60h]
  struct _PRIVILEGE_SET v36; // [rsp+E0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  std::string::string(v33);
  v34 = 0;
  v35 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix35701600>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix35701600>::GetImpl'::`2'::impl) )
  {
    if ( SQLiteSecurityDescriptorTable::TryRead(
           (SQLiteSecurityDescriptorTable *)&lpCriticalSection[1].OwningThread,
           a2,
           (struct security_descriptor_table_entry *)v33) )
    {
      goto LABEL_8;
    }
LABEL_6:
    security_descriptor_table_entry::~security_descriptor_table_entry((security_descriptor_table_entry *)v33);
    return 0;
  }
  *(_QWORD *)&v30 = lpCriticalSection;
  EnterCriticalSection(lpCriticalSection);
  if ( LOBYTE(lpCriticalSection[1].LockCount)
    || !SQLiteSecurityDescriptorTable::TryRead(
          (SQLiteSecurityDescriptorTable *)&lpCriticalSection[1].OwningThread,
          a2,
          (struct security_descriptor_table_entry *)v33) )
  {
    LeaveCriticalSection(lpCriticalSection);
    goto LABEL_6;
  }
  LeaveCriticalSection(lpCriticalSection);
LABEL_8:
  v30 = *(_OWORD *)std::string::operator std::string_view(v33, v32);
  convert_text_to_security_descriptor(&pSecurityDescriptor, &v30);
  from_utf8_list(v31, &v34);
  to_unicode_string_list(&v27, v31);
  *AccessStatus = 0;
  memset(&v36, 0, sizeof(v36));
  PrivilegeSetLength = 20;
  GrantedAccess = 0;
  v10 = DesiredAccess;
  v11 = pSecurityDescriptor;
  v13 = AccessCheck(
          pSecurityDescriptor,
          ClientToken,
          v10,
          &gmFile,
          &v36,
          &PrivilegeSetLength,
          &GrantedAccess,
          AccessStatus);
  if ( v13 )
  {
    if ( *AccessStatus )
    {
      v16 = *((_QWORD *)&v27 + 1);
      v15 = v27;
      if ( (__int64)(*((_QWORD *)&v27 + 1) - v27) >> 4 )
      {
        *AccessStatus = 0;
        while ( v15 != v16 )
        {
          v24[0] = 0;
          v17 = -6;
          if ( ClientToken )
            v17 = (__int64)ClientToken;
          *(_QWORD *)&v30 = v17;
          v18 = IsEnterpriseAllowed(&v30, v15, v12, v24);
          if ( v18 < 0 )
          {
            v21 = RtlNtStatusToDosError(v18);
            if ( v21 > 0 )
              v21 = (unsigned __int16)v21 | 0x80070000;
            v22 = (const char *)(unsigned int)wil::verify_hresult<long>((unsigned int)v21);
            try
            {
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x157,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\ntciutil\\secstore.cxx",
                v22,
                PrivilegeSet);
            }
            catch ( ... )
            {
              v19 = (void *)v27;
              if ( (_QWORD)v27 )
              {
                std::_Deallocate<16>(v19, (v28 - (_QWORD)v19) & 0xFFFFFFFFFFFFFFF0uLL);
                v27 = 0;
                v28 = 0;
              }
              std::vector<std::wstring>::_Tidy(v31);
              v20 = pSecurityDescriptor;
              if ( pSecurityDescriptor )
                LocalFree(v20);
              goto LABEL_6;
            }
          }
          if ( v24[0] )
          {
            *AccessStatus = 1;
            break;
          }
          v15 += 16;
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\ntciutil\\secstore.cxx",
      (const wchar_t *)0x144,
      (unsigned int)L"[Query] CSdidLookupTable::AccessCheck failed, GetLastError is %d\n",
      (const wchar_t *)LastError);
  }
  if ( (_QWORD)v27 )
  {
    std::_Deallocate<16>((void *)v27, (v28 - v27) & 0xFFFFFFFFFFFFFFF0uLL);
    v27 = 0;
    v28 = 0;
  }
  std::vector<std::wstring>::_Tidy(v31);
  if ( v11 )
    LocalFree(v11);
  security_descriptor_table_entry::~security_descriptor_table_entry((security_descriptor_table_entry *)v33);
  return v13;
}

```

## disassembly

```asm
0x18009f38c  push    rsi
0x18009f38e  push    rdi
0x18009f38f  push    r12
0x18009f391  push    r13
0x18009f393  push    r14
0x18009f395  push    r15
0x18009f397  sub     rsp, 108h
0x18009f39e  mov     rax, cs:__security_cookie
0x18009f3a5  xor     rax, rsp
0x18009f3a8  mov     [rsp+138h+var_40], rax
0x18009f3b0  mov     r15d, r9d
0x18009f3b3  mov     r12, r8
0x18009f3b6  mov     r14d, edx
0x18009f3b9  mov     rdi, rcx
0x18009f3bc  mov     rsi, [rsp+138h+arg_20]
0x18009f3c4  lea     rcx, [rsp+138h+var_90]
0x18009f3cc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18009f3d1  xorps   xmm1, xmm1
0x18009f3d4  movdqu  [rsp+138h+var_70], xmm1
0x18009f3dd  mov     [rsp+138h+var_60], 0
0x18009f3e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix35701600@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix35701600@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix35701600> `wil::Feature<__WilFeatureTraits_Feature_BugFix35701600>::GetImpl(void)'::`2'::impl
0x18009f3f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix35701600@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix35701600>::__private_IsEnabled(void)
0x18009f3f5  test    al, al
0x18009f3f7  jz      short loc_18009F46C
0x18009f3f9  mov     qword ptr [rsp+138h+var_C8], rdi
0x18009f3fe  mov     rcx, rdi; lpCriticalSection
0x18009f401  call    cs:__imp_EnterCriticalSection
0x18009f407  nop
0x18009f408  cmp     byte ptr [rdi+30h], 0
0x18009f40c  jnz     short loc_18009F431
0x18009f40e  lea     rcx, [rdi+38h]; this
0x18009f412  lea     r8, [rsp+138h+var_90]; struct security_descriptor_table_entry *
0x18009f41a  mov     edx, r14d; int
0x18009f41d  call    ?TryRead@SQLiteSecurityDescriptorTable@@QEAA_NHAEAUsecurity_descriptor_table_entry@@@Z; SQLiteSecurityDescriptorTable::TryRead(int,security_descriptor_table_entry &)
0x18009f422  test    al, al
0x18009f424  jz      short loc_18009F431
0x18009f426  mov     rcx, rdi; lpCriticalSection
0x18009f429  call    cs:__imp_LeaveCriticalSection
0x18009f42f  jmp     short loc_18009F484
0x18009f431  mov     rcx, rdi; lpCriticalSection
0x18009f434  call    cs:__imp_LeaveCriticalSection
0x18009f43a  nop
0x18009f43b  lea     rcx, [rsp+138h+var_90]; this
0x18009f443  call    ??1security_descriptor_table_entry@@QEAA@XZ; security_descriptor_table_entry::~security_descriptor_table_entry(void)
0x18009f448  xor     eax, eax
0x18009f44a  mov     rcx, [rsp+138h+var_40]
0x18009f452  xor     rcx, rsp; StackCookie
0x18009f455  call    __security_check_cookie
0x18009f45a  add     rsp, 108h
0x18009f461  pop     r15
0x18009f463  pop     r14
0x18009f465  pop     r13
0x18009f467  pop     r12
0x18009f469  pop     rdi
0x18009f46a  pop     rsi
0x18009f46b  retn
0x18009f46c  lea     rcx, [rdi+38h]; this
0x18009f470  lea     r8, [rsp+138h+var_90]; struct security_descriptor_table_entry *
0x18009f478  mov     edx, r14d; int
0x18009f47b  call    ?TryRead@SQLiteSecurityDescriptorTable@@QEAA_NHAEAUsecurity_descriptor_table_entry@@@Z; SQLiteSecurityDescriptorTable::TryRead(int,security_descriptor_table_entry &)
0x18009f480  test    al, al
0x18009f482  jz      short loc_18009F43B
0x18009f484  lea     rdx, [rsp+138h+var_A0]
0x18009f48c  lea     rcx, [rsp+138h+var_90]
0x18009f494  call    ??B?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string_view@DU?$char_traits@D@std@@@1@XZ; std::string::operator std::string_view(void)
0x18009f499  movups  xmm0, xmmword ptr [rax]
0x18009f49c  movdqu  [rsp+138h+var_C8], xmm0
0x18009f4a2  lea     rdx, [rsp+138h+var_C8]
0x18009f4a7  lea     rcx, [rsp+138h+pSecurityDescriptor]
0x18009f4ac  call    ?convert_text_to_security_descriptor@@YA?AV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; convert_text_to_security_descriptor(std::string_view)
0x18009f4b1  nop
0x18009f4b2  lea     rdx, [rsp+138h+var_70]
0x18009f4ba  lea     rcx, [rsp+138h+var_B8]
0x18009f4c2  call    ?from_utf8_list@@YA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@@Z; from_utf8_list(std::vector<std::string> const &)
0x18009f4c7  nop
0x18009f4c8  lea     rdx, [rsp+138h+var_B8]
0x18009f4d0  lea     rcx, [rsp+138h+var_E8]
0x18009f4d5  call    ?to_unicode_string_list@@YA?AV?$vector@U_UNICODE_STRING@@V?$allocator@U_UNICODE_STRING@@@std@@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@Z; to_unicode_string_list(std::vector<std::wstring> &)
0x18009f4da  nop
0x18009f4db  mov     dword ptr [rsi], 0
0x18009f4e1  xorps   xmm0, xmm0
0x18009f4e4  xor     eax, eax
0x18009f4e6  movups  xmmword ptr [rsp+138h+var_58.PrivilegeCount], xmm0
0x18009f4ee  mov     [rsp+138h+var_58.Privilege.Attributes], eax
0x18009f4f5  mov     [rsp+138h+var_F0], 14h
0x18009f4fd  mov     [rsp+138h+var_F4], eax
0x18009f501  mov     [rsp+138h+AccessStatus], rsi; AccessStatus
0x18009f506  lea     rax, [rsp+138h+var_F4]
0x18009f50b  mov     [rsp+138h+GrantedAccess], rax; GrantedAccess
0x18009f510  lea     rax, [rsp+138h+var_F0]
0x18009f515  mov     [rsp+138h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18009f51a  lea     rax, [rsp+138h+var_58]
0x18009f522  mov     [rsp+138h+PrivilegeSet], rax; int
0x18009f527  lea     r9, ?gmFile@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18009f52e  mov     r8d, r15d; DesiredAccess
0x18009f531  mov     rdx, r12; ClientToken
0x18009f534  mov     r15, [rsp+138h+pSecurityDescriptor]
0x18009f539  mov     rcx, r15; pSecurityDescriptor
0x18009f53c  call    cs:__imp_AccessCheck
0x18009f542  mov     r13d, eax
0x18009f545  test    eax, eax
0x18009f547  jnz     loc_18009F5CE
0x18009f54d  call    cs:__imp_GetLastError
0x18009f553  mov     r9d, eax; wchar_t *
0x18009f556  lea     r8, aQueryCsdidlook; "[Query] CSdidLookupTable::AccessCheck f"...
0x18009f55d  mov     edx, 144h; wchar_t *
0x18009f562  lea     rcx, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18009f569  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18009f56e  nop
0x18009f56f  mov     rcx, qword ptr [rsp+138h+var_E8]
0x18009f574  test    rcx, rcx
0x18009f577  jz      short loc_18009F59C
0x18009f579  mov     rdx, [rsp+138h+var_D8]
0x18009f57e  sub     rdx, rcx
0x18009f581  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18009f585  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009f58a  xorps   xmm0, xmm0
0x18009f58d  movdqu  [rsp+138h+var_E8], xmm0
0x18009f593  mov     [rsp+138h+var_D8], 0
0x18009f59c  lea     rcx, [rsp+138h+var_B8]
0x18009f5a4  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18009f5a9  nop
0x18009f5aa  test    r15, r15
0x18009f5ad  jz      short loc_18009F5B9
0x18009f5af  mov     rcx, r15; hMem
0x18009f5b2  call    cs:__imp_LocalFree
0x18009f5b8  nop
0x18009f5b9  lea     rcx, [rsp+138h+var_90]; this
0x18009f5c1  call    ??1security_descriptor_table_entry@@QEAA@XZ; security_descriptor_table_entry::~security_descriptor_table_entry(void)
0x18009f5c6  mov     eax, r13d
0x18009f5c9  jmp     loc_18009F44A
0x18009f5ce  cmp     dword ptr [rsi], 0
0x18009f5d1  jz      short loc_18009F56F
0x18009f5d3  mov     rdi, qword ptr [rsp+138h+var_E8]
0x18009f5d8  mov     r14, qword ptr [rsp+138h+var_E8+8]
0x18009f5dd  mov     rax, r14
0x18009f5e0  sub     rax, rdi
0x18009f5e3  sar     rax, 4
0x18009f5e7  test    rax, rax
0x18009f5ea  jz      short loc_18009F56F
0x18009f5ec  mov     dword ptr [rsi], 0
0x18009f5f2  cmp     rdi, r14
0x18009f5f5  jz      loc_18009F56F
0x18009f5fb  mov     [rsp+138h+var_F8], 0
0x18009f600  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18009f607  test    r12, r12
0x18009f60a  cmovnz  rax, r12
0x18009f60e  mov     qword ptr [rsp+138h+var_C8], rax
0x18009f613  lea     r9, [rsp+138h+var_F8]
0x18009f618  mov     rdx, rdi
0x18009f61b  lea     rcx, [rsp+138h+var_C8]
0x18009f620  call    IsEnterpriseAllowed
0x18009f625  test    eax, eax
0x18009f627  js      short loc_18009F69A
0x18009f629  jmp     short loc_18009F67F
0x18009f62b  mov     rcx, qword ptr [rsp+138h+var_E8]
0x18009f630  test    rcx, rcx
0x18009f633  jz      short loc_18009F658
0x18009f635  mov     rdx, [rsp+138h+var_D8]
0x18009f63a  sub     rdx, rcx
0x18009f63d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18009f641  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009f646  xorps   xmm0, xmm0
0x18009f649  movdqu  [rsp+138h+var_E8], xmm0
0x18009f64f  mov     [rsp+138h+var_D8], 0
0x18009f658  lea     rcx, [rsp+138h+var_B8]
0x18009f660  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18009f665  nop
0x18009f666  mov     rcx, [rsp+138h+pSecurityDescriptor]; hMem
0x18009f66b  test    rcx, rcx
0x18009f66e  jz      loc_18009F43B
0x18009f674  call    cs:__imp_LocalFree
0x18009f67a  jmp     loc_18009F43B
0x18009f67f  cmp     [rsp+138h+var_F8], 0
0x18009f684  jz      short loc_18009F691
0x18009f686  mov     dword ptr [rsi], 1
0x18009f68c  jmp     loc_18009F56F
0x18009f691  add     rdi, 10h
0x18009f695  jmp     loc_18009F5F2
0x18009f69a  mov     ecx, eax; Status
0x18009f69c  call    cs:__imp_RtlNtStatusToDosError
0x18009f6a2  test    eax, eax
0x18009f6a4  jle     short loc_18009F6AE
0x18009f6a6  movzx   eax, ax
0x18009f6a9  or      eax, 80070000h
0x18009f6ae  mov     ecx, eax
0x18009f6b0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18009f6b5  mov     r9d, eax; char *
0x18009f6b8  mov     rcx, [rsp+138h]; this
0x18009f6c0  lea     r8, aOnecoreuapBase_51; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18009f6c7  mov     edx, 157h; void *
0x18009f6cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
