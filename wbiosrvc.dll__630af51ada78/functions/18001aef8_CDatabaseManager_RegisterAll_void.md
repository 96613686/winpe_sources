# CDatabaseManager::RegisterAll(void)

- ea: `0x18001aef8`
- end: `0x18001b2a6`
- name: `?RegisterAll@CDatabaseManager@@QEAAJXZ`
- size: `942`
- prototype: `__int64 __fastcall(CDatabaseManager *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x18001d378`
- `0x180041c14`
- `0x180045d10`

## callees

- `0x180014854`
- `0x180014894`
- `0x1800148b4`
- `0x180014938`
- `0x180014cb0`
- `0x180014f54`
- `0x18001aef8`
- `0x180031810`
- `0x180031b14`
- `0x18003828c`
- `0x18003ef5c`
- `0x180058504`
- `0x180068f60`
- `0x18006963c`
- `0x180069cc8`
- `0x18006b0a9`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001afe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b26a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001afe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b26a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001b062`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001b062`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001afd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b10d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001afd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b10d`

## string_xrefs

- `0x18001af6b`: `System\CurrentControlSet\Services\WbioSrvc\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDatabaseManager::RegisterAll(CDatabaseManager *this)
{
  CDatabaseManager *v1; // r15
  __int64 v2; // r8
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rcx
  const WCHAR *v6; // rax
  unsigned int v7; // r12d
  DWORD i; // esi
  const unsigned __int16 *v10; // rax
  __int64 *v11; // r13
  __int64 *v12; // rdi
  __int64 *v13; // r14
  int v14; // edi
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // r9
  CTemplateDatabase *v17; // r10
  CTemplateDatabase *v18; // rdi
  __int64 *v19; // rdx
  __int64 v20; // rcx
  WCHAR *p_Name; // rax
  __int64 v22; // [rsp+0h] [rbp-338h] BYREF
  DWORD cchName; // [rsp+40h] [rbp-2F8h] BYREF
  DWORD v24; // [rsp+44h] [rbp-2F4h]
  HKEY hKey; // [rsp+48h] [rbp-2F0h] BYREF
  CTemplateDatabase *v26; // [rsp+58h] [rbp-2E0h]
  HKEY phkResult; // [rsp+60h] [rbp-2D8h] BYREF
  CDatabaseManager *v28; // [rsp+68h] [rbp-2D0h]
  __int128 Buf2; // [rsp+70h] [rbp-2C8h] BYREF
  void *v30; // [rsp+80h] [rbp-2B8h]
  _BYTE v31[16]; // [rsp+88h] [rbp-2B0h] BYREF
  __int128 v32; // [rsp+98h] [rbp-2A0h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-290h]
  __int64 v34; // [rsp+B0h] [rbp-288h]
  __int128 v35; // [rsp+B8h] [rbp-280h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-270h]
  __int64 v37; // [rsp+D0h] [rbp-268h]
  __int128 v38; // [rsp+D8h] [rbp-260h] BYREF
  CTemplateDatabase *v39; // [rsp+E8h] [rbp-250h]
  WCHAR Name; // [rsp+F0h] [rbp-248h] BYREF
  _BYTE v41[72]; // [rsp+F2h] [rbp-246h] BYREF
  __int16 v42; // [rsp+13Ah] [rbp-1FEh]

  v1 = this;
  v28 = this;
  hKey = 0;
  memset_0(&Name, 0, 0x208u);
  cchName = 260;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v2 = std::_WChar_traits<unsigned short>::length(L"System\\CurrentControlSet\\Services\\WbioSrvc\\");
  std::wstring::_Construct<1,unsigned short const *>(&v35, v3, v2);
  v4 = std::_WChar_traits<unsigned short>::length(L"Databases");
  std::wstring::_Append<unsigned short>(&v35, v5, v4);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v35);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey) )
  {
    v7 = -2147467259;
  }
  else
  {
    v7 = 0;
    for ( i = 0; ; ++i )
    {
      v24 = i;
      if ( RegEnumKeyExW(hKey, i, &Name, &cchName, 0, 0, 0, 0) )
        break;
      if ( cchName == 38 && Name == 123 && v42 == 125 )
      {
        v32 = 0;
        v33 = 0;
        v34 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v32, v41, 36);
        v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v32);
        CWinBioUuid::Init((CWinBioUuid *)&Buf2, v10);
        phkResult = 0;
        if ( !RegOpenKeyExW(hKey, &Name, 0, 0x2000000u, &phkResult) )
        {
          v26 = 0;
          CSynchLock::Lock(v1);
          CSynchLock::Lock(v1);
          v11 = (__int64 *)*((_QWORD *)v1 + 6);
          v12 = (__int64 *)v11[1];
          HIDWORD(v38) = 0;
          v13 = v11;
          while ( !*((_BYTE *)v12 + 25) )
          {
            if ( memcmp_0(v12 + 4, &Buf2, 0x10u) >= 0 )
            {
              v13 = v12;
              v12 = (__int64 *)*v12;
            }
            else
            {
              v12 = (__int64 *)v12[2];
            }
          }
          if ( *((_BYTE *)v13 + 25) || memcmp_0(&Buf2, v13 + 4, 0x10u) < 0 || v13 == v11 )
          {
            v14 = -2146861035;
          }
          else
          {
            v14 = 0;
            if ( !v13[6] )
              v14 = -2147023537;
          }
          CSynchLock::Unlock(v1);
          if ( v14 < 0 )
          {
            if ( __eh34_try(-1, 0) )
            {
              __eh34_scope_strut(0);
              v30 = operator new(0xA8u);
              std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v1 + 64);
              v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v32);
              v18 = ((CTemplateDatabase *(__stdcall *)(CTemplateDatabase *, HKEY, const unsigned __int16 *, const unsigned __int16 *))CTemplateDatabase::CTemplateDatabase)(
                      v17,
                      phkResult,
                      v15,
                      v16);
              v26 = v18;
              v38 = Buf2;
              v39 = v18;
              std::_Tree<std::_Tmap_traits<CWinBioUuid,CTemplateDatabase *,std::less<CWinBioUuid>,std::allocator<std::pair<CWinBioUuid const,CTemplateDatabase *>>,0>>::_Emplace<std::pair<CWinBioUuid,CTemplateDatabase *>>(
                (char *)v1 + 48,
                v31,
                &v38);
              if ( v31[8] )
                v18 = 0;
              v26 = v18;
            }
            if ( __eh34_catch(0) )
            {
              if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
              {
                v19 = &v22;
                v7 = 0;
                i = v24;
                v18 = v26;
                v1 = v28;
                __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001B23D);
              }
            }
            if ( v18 )
              CTemplateDatabase::`scalar deleting destructor'(v18, (unsigned int)v19);
          }
          CSynchLock::Unlock(v1);
          RegCloseKey(phkResult);
        }
        std::wstring::_Tidy_deallocate(&v32);
      }
      cchName = 260;
      v20 = 520;
      p_Name = &Name;
      do
      {
        *(_BYTE *)p_Name = 0;
        p_Name = (WCHAR *)((char *)p_Name + 1);
        --v20;
      }
      while ( v20 );
    }
  }
  RegCloseKey(hKey);
  hKey = 0;
  std::wstring::_Tidy_deallocate(&v35);
  return v7;
}

```

## disassembly

```asm
0x18001aef8  mov     [rsp+arg_8], rbx
0x18001aefd  mov     [rsp+arg_10], rsi
0x18001af02  push    rdi
0x18001af03  push    r12
0x18001af05  push    r13
0x18001af07  push    r14
0x18001af09  push    r15
0x18001af0b  sub     rsp, 310h
0x18001af12  mov     rax, cs:__security_cookie
0x18001af19  xor     rax, rsp
0x18001af1c  mov     [rsp+338h+var_38], rax
0x18001af24  mov     r15, rcx
0x18001af27  mov     [rsp+338h+var_2D0], rcx
0x18001af2c  xor     ebx, ebx
0x18001af2e  mov     [rsp+338h+hKey], rbx
0x18001af33  xor     edx, edx; Val
0x18001af35  mov     r8d, 208h; Size
0x18001af3b  lea     rcx, [rsp+338h+Name]; void *
0x18001af43  call    memset_0
0x18001af48  mov     [rsp+338h+cchName], 104h
0x18001af50  xorps   xmm0, xmm0
0x18001af53  movups  [rsp+338h+var_280], xmm0
0x18001af5b  mov     [rsp+338h+var_270], rbx
0x18001af63  mov     [rsp+338h+var_268], rbx
0x18001af6b  lea     rcx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Wb"...
0x18001af72  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001af77  mov     r8, rax
0x18001af7a  mov     rdx, rcx
0x18001af7d  lea     rcx, [rsp+338h+var_280]
0x18001af85  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001af8a  nop
0x18001af8b  lea     rcx, aDatabases; "Databases"
0x18001af92  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001af97  mov     r8, rax
0x18001af9a  mov     rdx, rcx
0x18001af9d  lea     rcx, [rsp+338h+var_280]
0x18001afa5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001afaa  lea     rcx, [rsp+338h+var_280]
0x18001afb2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001afb7  mov     rdx, rax; lpSubKey
0x18001afba  lea     rax, [rsp+338h+hKey]
0x18001afbf  mov     [rsp+338h+phkResult], rax; phkResult
0x18001afc4  mov     r9d, 20019h; samDesired
0x18001afca  xor     r8d, r8d; ulOptions
0x18001afcd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001afd4  call    cs:__imp_RegOpenKeyExW
0x18001afda  test    eax, eax
0x18001afdc  jz      short loc_18001B031
0x18001afde  mov     r12d, 80004005h
0x18001afe4  mov     rcx, [rsp+338h+hKey]; hKey
0x18001afe9  call    cs:__imp_RegCloseKey
0x18001afef  mov     [rsp+338h+hKey], rbx
0x18001aff4  lea     rcx, [rsp+338h+var_280]
0x18001affc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b001  mov     eax, r12d
0x18001b004  mov     rcx, [rsp+338h+var_38]
0x18001b00c  xor     rcx, rsp; StackCookie
0x18001b00f  call    __security_check_cookie
0x18001b014  lea     r11, [rsp+338h+var_28]
0x18001b01c  mov     rbx, [r11+38h]
0x18001b020  mov     rsi, [r11+40h]
0x18001b024  mov     rsp, r11
0x18001b027  pop     r15
0x18001b029  pop     r14
0x18001b02b  pop     r13
0x18001b02d  pop     r12
0x18001b02f  pop     rdi
0x18001b030  retn
0x18001b031  mov     r12d, ebx
0x18001b034  mov     esi, ebx
0x18001b036  mov     [rsp+338h+var_2F4], esi
0x18001b03a  mov     [rsp+338h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18001b03f  mov     [rsp+338h+lpcchClass], rbx; lpcchClass
0x18001b044  mov     [rsp+338h+lpClass], rbx; lpClass
0x18001b049  mov     [rsp+338h+phkResult], rbx; lpReserved
0x18001b04e  lea     r9, [rsp+338h+cchName]; lpcchName
0x18001b053  lea     r8, [rsp+338h+Name]; lpName
0x18001b05b  mov     edx, esi; dwIndex
0x18001b05d  mov     rcx, [rsp+338h+hKey]; hKey
0x18001b062  call    cs:__imp_RegEnumKeyExW
0x18001b068  test    eax, eax
0x18001b06a  jnz     loc_18001AFE4
0x18001b070  cmp     [rsp+338h+cchName], 26h ; '&'
0x18001b075  jnz     loc_18001B27E
0x18001b07b  cmp     [rsp+338h+Name], 7Bh ; '{'
0x18001b084  jnz     loc_18001B27E
0x18001b08a  cmp     [rsp+338h+var_1FE], 7Dh ; '}'
0x18001b093  jnz     loc_18001B27E
0x18001b099  xorps   xmm0, xmm0
0x18001b09c  movups  [rsp+338h+var_2A0], xmm0
0x18001b0a4  mov     [rsp+338h+var_290], rbx
0x18001b0ac  mov     [rsp+338h+var_288], rbx
0x18001b0b4  lea     r8d, [rax+24h]
0x18001b0b8  lea     rdx, [rsp+338h+var_246]
0x18001b0c0  lea     rcx, [rsp+338h+var_2A0]
0x18001b0c8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b0cd  nop
0x18001b0ce  lea     rcx, [rsp+338h+var_2A0]
0x18001b0d6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b0db  mov     rdx, rax; unsigned __int16 *
0x18001b0de  lea     rcx, [rsp+338h+Buf2]; this
0x18001b0e3  call    ?Init@CWinBioUuid@@AEAAXPEBG@Z; CWinBioUuid::Init(ushort const *)
0x18001b0e8  mov     [rsp+338h+var_2D8], rbx
0x18001b0ed  lea     rax, [rsp+338h+var_2D8]
0x18001b0f2  mov     [rsp+338h+phkResult], rax; phkResult
0x18001b0f7  mov     r9d, 2000000h; samDesired
0x18001b0fd  xor     r8d, r8d; ulOptions
0x18001b100  lea     rdx, [rsp+338h+Name]; lpSubKey
0x18001b108  mov     rcx, [rsp+338h+hKey]; hKey
0x18001b10d  call    cs:__imp_RegOpenKeyExW
0x18001b113  test    eax, eax
0x18001b115  jnz     loc_18001B271
0x18001b11b  mov     [rsp+338h+var_2E0], rbx
0x18001b120  mov     rcx, r15; this
0x18001b123  call    ?Lock@CSynchLock@@QEAAXXZ; CSynchLock::Lock(void)
0x18001b128  mov     rcx, r15; this
0x18001b12b  call    ?Lock@CSynchLock@@QEAAXXZ; CSynchLock::Lock(void)
0x18001b130  mov     r13, [r15+30h]
0x18001b134  mov     rdi, [r13+8]
0x18001b138  xor     eax, eax
0x18001b13a  mov     dword ptr [rsp+338h+var_260+0Ch], eax
0x18001b141  mov     r14, r13
0x18001b144  jmp     short loc_18001B16A
0x18001b146  lea     rcx, [rdi+20h]; Buf1
0x18001b14a  mov     r8d, 10h; Size
0x18001b150  lea     rdx, [rsp+338h+Buf2]; Buf2
0x18001b155  call    memcmp_0
0x18001b15a  test    eax, eax
0x18001b15c  jns     short loc_18001B164
0x18001b15e  mov     rdi, [rdi+10h]
0x18001b162  jmp     short loc_18001B16A
0x18001b164  mov     r14, rdi
0x18001b167  mov     rdi, [rdi]
0x18001b16a  cmp     [rdi+19h], bl
0x18001b16d  jz      short loc_18001B146
0x18001b16f  cmp     [r14+19h], bl
0x18001b173  jnz     short loc_18001B1A1
0x18001b175  lea     rdx, [r14+20h]; Buf2
0x18001b179  mov     r8d, 10h; Size
0x18001b17f  lea     rcx, [rsp+338h+Buf2]; Buf1
0x18001b184  call    memcmp_0
0x18001b189  test    eax, eax
0x18001b18b  js      short loc_18001B1A1
0x18001b18d  cmp     r14, r13
0x18001b190  jz      short loc_18001B1A1
0x18001b192  mov     edi, ebx
0x18001b194  cmp     [r14+30h], rbx
0x18001b198  jnz     short loc_18001B1A6
0x18001b19a  mov     edi, 8007054Fh
0x18001b19f  jmp     short loc_18001B1A6
0x18001b1a1  mov     edi, 80098015h
0x18001b1a6  mov     rcx, r15; this
0x18001b1a9  call    ?Unlock@CSynchLock@@QEAAXXZ; CSynchLock::Unlock(void)
0x18001b1ae  test    edi, edi
0x18001b1b0  jns     loc_18001B25D
0x18001b1b6  mov     ecx, 0A8h; Size
0x18001b1bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b1c0  mov     r10, rax
0x18001b1c3  mov     [rsp+338h+var_2B8], rax
0x18001b1cb  lea     rcx, [r15+40h]
0x18001b1cf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b1d4  mov     r9, rax
0x18001b1d7  lea     rcx, [rsp+338h+var_2A0]
0x18001b1df  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b1e4  mov     r8, rax; unsigned __int16 *
0x18001b1e7  mov     rdx, [rsp+338h+var_2D8]; HKEY
0x18001b1ec  mov     rcx, r10; this
0x18001b1ef  call    ??0CTemplateDatabase@@QEAA@PEAUHKEY__@@PEBG1@Z; CTemplateDatabase::CTemplateDatabase(HKEY__ *,ushort const *,ushort const *)
0x18001b1f4  mov     rdi, rax
0x18001b1f7  mov     [rsp+338h+var_2E0], rax
0x18001b1fc  movups  xmm0, [rsp+338h+Buf2]
0x18001b201  movdqu  [rsp+338h+var_260], xmm0
0x18001b20a  mov     [rsp+338h+var_250], rax
0x18001b212  lea     r8, [rsp+338h+var_260]
0x18001b21a  lea     rdx, [rsp+338h+var_2B0]
0x18001b222  lea     rcx, [r15+30h]
0x18001b226  call    ??$_Emplace@U?$pair@VCWinBioUuid@@PEAVCTemplateDatabase@@@std@@@?$_Tree@V?$_Tmap_traits@VCWinBioUuid@@PEAVCTemplateDatabase@@U?$less@VCWinBioUuid@@@std@@V?$allocator@U?$pair@$$CBVCWinBioUuid@@PEAVCTemplateDatabase@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVCWinBioUuid@@PEAVCTemplateDatabase@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@VCWinBioUuid@@PEAVCTemplateDatabase@@@1@@Z; std::_Tree<std::_Tmap_traits<CWinBioUuid,CTemplateDatabase *,std::less<CWinBioUuid>,std::allocator<std::pair<CWinBioUuid const,CTemplateDatabase *>>,0>>::_Emplace<std::pair<CWinBioUuid,CTemplateDatabase *>>(std::pair<CWinBioUuid,CTemplateDatabase *> &&)
0x18001b22b  cmp     [rsp+338h+var_2A8], bl
0x18001b232  cmovnz  rdi, rbx
0x18001b236  mov     [rsp+338h+var_2E0], rdi
0x18001b23b  jmp     short loc_18001B250
0x18001b23d  xor     ebx, ebx
0x18001b23f  mov     r12d, ebx
0x18001b242  mov     esi, [rsp+338h+var_2F4]
0x18001b246  mov     rdi, [rsp+338h+var_2E0]
0x18001b24b  mov     r15, [rsp+338h+var_2D0]
0x18001b250  test    rdi, rdi
0x18001b253  jz      short loc_18001B25D
0x18001b255  mov     rcx, rdi; this
0x18001b258  call    ??_GCTemplateDatabase@@QEAAPEAXI@Z; CTemplateDatabase::`scalar deleting destructor'(uint)
0x18001b25d  mov     rcx, r15; this
0x18001b260  call    ?Unlock@CSynchLock@@QEAAXXZ; CSynchLock::Unlock(void)
0x18001b265  mov     rcx, [rsp+338h+var_2D8]; hKey
0x18001b26a  call    cs:__imp_RegCloseKey
0x18001b270  nop
0x18001b271  lea     rcx, [rsp+338h+var_2A0]
0x18001b279  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b27e  mov     [rsp+338h+cchName], 104h
0x18001b286  mov     ecx, 208h
0x18001b28b  lea     rax, [rsp+338h+Name]
0x18001b293  mov     [rax], bl
0x18001b295  inc     rax
0x18001b298  sub     rcx, 1
0x18001b29c  jnz     short loc_18001B293
0x18001b29e  inc     esi
0x18001b2a0  jmp     loc_18001B036
```
