# GetIsKFMEnrolled(bool &)

- ea: `0x180019288`
- end: `0x1800194a2`
- name: `?GetIsKFMEnrolled@@YAJAEA_N@Z`
- size: `538`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018ea0`

## callees

- `0x1800050f0`
- `0x18000eb18`
- `0x1800152d4`
- `0x18001707c`
- `0x18001719c`
- `0x180017af4`
- `0x180019288`
- `0x180019674`
- `0x18001ef0c`
- `0x18001f108`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001940f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001940f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001943e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001943e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800193b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800193b8`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180019370`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180019393`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180019370`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180019393`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetIsKFMEnrolled(bool *a1)
{
  int ODSyncRootPaths; // ebx
  __int64 v3; // rdx
  wchar_t **v5; // rdi
  __int64 v6; // rsi
  __int64 v7; // r15
  __int64 v8; // rax
  const wchar_t *v9; // rax
  wchar_t *v10; // rbx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-69h]
  __int64 v12; // [rsp+30h] [rbp-59h] BYREF
  __int64 v13; // [rsp+38h] [rbp-51h]
  __int64 v14; // [rsp+40h] [rbp-49h]
  PWSTR Str; // [rsp+48h] [rbp-41h] BYREF
  PWSTR ppszPath; // [rsp+50h] [rbp-39h] BYREF
  __int128 v17; // [rsp+58h] [rbp-31h] BYREF
  __int64 v18; // [rsp+68h] [rbp-21h]
  __int64 v19; // [rsp+70h] [rbp-19h]
  _BYTE rfid[28]; // [rsp+80h] [rbp-9h] BYREF
  char v21; // [rsp+9Ch] [rbp+13h]
  __int16 v22; // [rsp+9Dh] [rbp+14h]
  char v23; // [rsp+9Fh] [rbp+16h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *a1 = 0;
  std::vector<unsigned short const *>::vector<unsigned short const *>(&v12);
  ODSyncRootPaths = GetODSyncRootPaths(&v12);
  if ( ODSyncRootPaths < 0 )
  {
    v3 = 2355;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
      (const char *)(unsigned int)ODSyncRootPaths,
      bIgnoreCase);
    if ( v12 )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v12, v13);
      std::_Deallocate<16>(v12, (v14 - v12) & 0xFFFFFFFFFFFFFFE0uLL);
    }
    return (unsigned int)ODSyncRootPaths;
  }
  if ( v13 == v12 )
  {
    ODSyncRootPaths = -2147467259;
    v3 = 2356;
    goto LABEL_3;
  }
  v5 = &KnownFolderScanConfigTable;
  do
  {
    *(_OWORD *)rfid = *(_OWORD *)v5;
    *(_OWORD *)&rfid[12] = *(_OWORD *)((char *)v5 + 12);
    v21 = *((_BYTE *)v5 + 28);
    v22 = *(_WORD *)((char *)v5 + 29);
    v23 = *((_BYTE *)v5 + 31);
    if ( v21 )
    {
      ppszPath = 0;
      if ( SHGetKnownFolderPath((const KNOWNFOLDERID *const)&rfid[8], 0x400u, 0, &ppszPath) >= 0 )
      {
        Str = 0;
        if ( SHGetKnownFolderPath((const KNOWNFOLDERID *const)&rfid[8], 0, 0, &Str) >= 0
          && CompareStringOrdinal(ppszPath, -1, Str, -1, 1) != 2 )
        {
          v6 = v12;
          v7 = v13;
          while ( v6 != v7 )
          {
            v17 = 0;
            v18 = 0;
            v19 = 0;
            v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
            std::wstring::_Construct<2,unsigned short const *>(&v17, v8, *(_QWORD *)(v6 + 16));
            v9 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v17);
            v10 = wcsstr(Str, v9);
            std::wstring::_Tidy_deallocate(&v17);
            if ( v10 )
            {
              *a1 = 1;
              break;
            }
            v6 += 32;
          }
        }
        CoTaskMemFree(Str);
      }
      CoTaskMemFree(ppszPath);
      if ( *a1 )
        break;
    }
    v5 += 4;
  }
  while ( v5 != &RegScanConfigTable );
  if ( v12 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v12, v13);
    std::_Deallocate<16>(v12, (v14 - v12) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return 0;
}

```

## disassembly

```asm
0x180019288  push    rbp
0x18001928a  push    rbx
0x18001928b  push    rsi
0x18001928c  push    rdi
0x18001928d  push    r14
0x18001928f  push    r15
0x180019291  lea     rbp, [rsp-2Fh]
0x180019296  sub     rsp, 0B8h
0x18001929d  mov     rax, cs:__security_cookie
0x1800192a4  xor     rax, rsp
0x1800192a7  mov     [rbp+57h+var_40], rax
0x1800192ab  mov     r14, rcx
0x1800192ae  mov     byte ptr [rcx], 0
0x1800192b1  lea     rcx, [rbp+57h+var_B0]
0x1800192b5  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x1800192ba  nop
0x1800192bb  lea     rcx, [rbp+57h+var_B0]
0x1800192bf  call    ?GetODSyncRootPaths@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetODSyncRootPaths(std::vector<std::wstring> &)
0x1800192c4  mov     ebx, eax
0x1800192c6  test    eax, eax
0x1800192c8  jns     short loc_180019310
0x1800192ca  mov     edx, 933h; void *
0x1800192cf  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800192d6  mov     r9d, ebx; char *
0x1800192d9  mov     rcx, [rbp+5Fh]; this
0x1800192dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800192e2  nop
0x1800192e3  mov     rcx, [rbp+57h+var_B0]
0x1800192e7  test    rcx, rcx
0x1800192ea  jz      short loc_180019309
0x1800192ec  mov     rdx, [rbp+57h+var_A8]
0x1800192f0  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800192f5  mov     rcx, [rbp+57h+var_B0]
0x1800192f9  mov     rdx, [rbp+57h+var_A0]
0x1800192fd  sub     rdx, rcx
0x180019300  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180019304  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180019309  mov     eax, ebx
0x18001930b  jmp     loc_180019486
0x180019310  mov     rax, [rbp+57h+var_A8]
0x180019314  cmp     rax, [rbp+57h+var_B0]
0x180019318  jnz     short loc_180019326
0x18001931a  mov     ebx, 80004005h
0x18001931f  mov     edx, 934h
0x180019324  jmp     short loc_1800192CF
0x180019326  lea     rdi, ?KnownFolderScanConfigTable@@3V?$array@UKNOWN_FOLDER_SCAN_CONFIG@@$06@std@@A; std::array<KNOWN_FOLDER_SCAN_CONFIG,7> KnownFolderScanConfigTable
0x18001932d  movups  xmm0, xmmword ptr [rdi]
0x180019330  movups  xmmword ptr [rbp+57h+rfid], xmm0
0x180019334  movups  xmm1, xmmword ptr [rdi+0Ch]
0x180019338  movups  xmmword ptr [rbp+57h+rfid+0Ch], xmm1
0x18001933c  mov     cl, [rdi+1Ch]
0x18001933f  mov     [rbp+57h+var_44], cl
0x180019342  movzx   eax, word ptr [rdi+1Dh]
0x180019346  mov     [rbp+57h+var_43], ax
0x18001934a  mov     al, [rdi+1Fh]
0x18001934d  mov     [rbp+57h+var_41], al
0x180019350  test    cl, cl
0x180019352  jz      loc_18001944A
0x180019358  mov     [rbp+57h+ppszPath], 0
0x180019360  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x180019364  xor     r8d, r8d; hToken
0x180019367  mov     edx, 400h; dwFlags
0x18001936c  lea     rcx, [rbp+57h+rfid+8]; rfid
0x180019370  call    cs:__imp_SHGetKnownFolderPath
0x180019376  test    eax, eax
0x180019378  js      loc_18001943A
0x18001937e  mov     [rbp+57h+Str], 0
0x180019386  lea     r9, [rbp+57h+Str]; ppszPath
0x18001938a  xor     r8d, r8d; hToken
0x18001938d  xor     edx, edx; dwFlags
0x18001938f  lea     rcx, [rbp+57h+rfid+8]; rfid
0x180019393  call    cs:__imp_SHGetKnownFolderPath
0x180019399  test    eax, eax
0x18001939b  js      loc_180019430
0x1800193a1  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x1800193a9  or      r9d, 0FFFFFFFFh; cchCount2
0x1800193ad  mov     r8, [rbp+57h+Str]; lpString2
0x1800193b1  or      edx, r9d; cchCount1
0x1800193b4  mov     rcx, [rbp+57h+ppszPath]; lpString1
0x1800193b8  call    cs:__imp_CompareStringOrdinal
0x1800193be  cmp     eax, 2
0x1800193c1  jz      short loc_180019430
0x1800193c3  mov     rsi, [rbp+57h+var_B0]
0x1800193c7  mov     r15, [rbp+57h+var_A8]
0x1800193cb  cmp     rsi, r15
0x1800193ce  jz      short loc_180019430
0x1800193d0  xorps   xmm0, xmm0
0x1800193d3  movups  [rbp+57h+var_88], xmm0
0x1800193d7  mov     [rbp+57h+var_78], 0
0x1800193df  mov     [rbp+57h+var_70], 0
0x1800193e7  mov     rcx, rsi
0x1800193ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800193ef  mov     r8, [rsi+10h]
0x1800193f3  mov     rdx, rax
0x1800193f6  lea     rcx, [rbp+57h+var_88]
0x1800193fa  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800193ff  lea     rcx, [rbp+57h+var_88]
0x180019403  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019408  mov     rdx, rax; SubStr
0x18001940b  mov     rcx, [rbp+57h+Str]; Str
0x18001940f  call    cs:__imp_wcsstr
0x180019415  mov     rbx, rax
0x180019418  lea     rcx, [rbp+57h+var_88]
0x18001941c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019421  test    rbx, rbx
0x180019424  jnz     short loc_18001942C
0x180019426  add     rsi, 20h ; ' '
0x18001942a  jmp     short loc_1800193CB
0x18001942c  mov     byte ptr [r14], 1
0x180019430  mov     rcx, [rbp+57h+Str]; pv
0x180019434  call    cs:__imp_CoTaskMemFree
0x18001943a  mov     rcx, [rbp+57h+ppszPath]; pv
0x18001943e  call    cs:__imp_CoTaskMemFree
0x180019444  cmp     byte ptr [r14], 1
0x180019448  jz      short loc_18001945E
0x18001944a  add     rdi, 20h ; ' '
0x18001944e  lea     rax, ?RegScanConfigTable@@3V?$array@UREG_SCAN_CONFIG@@$05@std@@A; std::array<REG_SCAN_CONFIG,6> RegScanConfigTable
0x180019455  cmp     rdi, rax
0x180019458  jnz     loc_18001932D
0x18001945e  mov     rcx, [rbp+57h+var_B0]
0x180019462  test    rcx, rcx
0x180019465  jz      short loc_180019484
0x180019467  mov     rdx, [rbp+57h+var_A8]
0x18001946b  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180019470  mov     rcx, [rbp+57h+var_B0]
0x180019474  mov     rdx, [rbp+57h+var_A0]
0x180019478  sub     rdx, rcx
0x18001947b  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001947f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180019484  xor     eax, eax
0x180019486  mov     rcx, [rbp+57h+var_40]
0x18001948a  xor     rcx, rsp; StackCookie
0x18001948d  call    __security_check_cookie
0x180019492  add     rsp, 0B8h
0x180019499  pop     r15
0x18001949b  pop     r14
0x18001949d  pop     rdi
0x18001949e  pop     rsi
0x18001949f  pop     rbx
0x1800194a0  pop     rbp
0x1800194a1  retn
```
