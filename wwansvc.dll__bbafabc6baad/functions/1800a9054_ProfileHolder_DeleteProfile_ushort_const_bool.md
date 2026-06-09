# ProfileHolder::DeleteProfile(ushort const *,bool)

- ea: `0x1800a9054`
- end: `0x1800a92f4`
- name: `?DeleteProfile@ProfileHolder@@QEAAKPEBG_N@Z`
- size: `672`
- prototype: `unsigned int __fastcall(ProfileHolder *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x1800a4478`
- `0x1800aa4d8`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x1800111ac`
- `0x180013288`
- `0x180013588`
- `0x180014154`
- `0x180014f1c`
- `0x180056e50`
- `0x18007b020`
- `0x1800a796c`
- `0x1800a9054`
- `0x1800a99a4`
- `0x1800a9c80`
- `0x1800aa800`
- `0x1800c8520`
- `0x1800c858c`

## import_xrefs

- `WwanPrfl!WwanProfileCleanup` at `0x1800a9269`
- `WwanPrfl!WwanProfileCleanup` at `0x1800a92b6`
- `WwanPrfl!WwanProfileCleanup` at `0x1800a9269`
- `WwanPrfl!WwanProfileCleanup` at `0x1800a92b6`
- `WwanPrfl!WwanProfileInit` at `0x1800a90bd`
- `WwanPrfl!WwanProfileInit` at `0x1800a90bd`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a917a`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a91d3`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a9260`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a917a`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a91d3`
- `WwanPrfl!WwanProfileCopyProfile` at `0x1800a9260`

## string_xrefs

- `0x1800a9160`: `ProfileHolder::DeleteProfile`
- `0x1800a91b9`: `ProfileHolder::DeleteProfile`
- `0x1800a9200`: `ProfileHolder::DeleteProfile`
- `0x1800a9247`: `ProfileHolder::DeleteProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProfileHolder::DeleteProfile(ProfileHolder *this, const unsigned __int16 *a2, char a3)
{
  unsigned int v6; // r12d
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // r14d
  __int64 v11; // rax
  __int64 v12; // rbx
  const wchar_t **v13; // rdi
  const wchar_t *i; // rbx
  char *v15; // rcx
  const wchar_t **v16; // rdi
  const wchar_t *v17; // rax
  _QWORD *v18; // rax
  __int64 *j; // rbx
  int CreationTypePriority; // [rsp+20h] [rbp-E0h]
  unsigned int v22; // [rsp+20h] [rbp-E0h]
  _BYTE v23[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v24[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[6320]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  std::wstring::wstring((__int64)v24, (__int64)a2);
  memset_0(v25, 0, sizeof(v25));
  WwanProfileInit(v25);
  if ( (byte_1801528C4 & 0x10) != 0 )
  {
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
    McTemplateU0zz_EventWriteTransfer(v9, PHDeleteProfile, v8, a2);
  }
  v10 = 0;
  v11 = *((_QWORD *)this + 4);
  do
  {
    v12 = *(_QWORD *)ProfileHolder::FindProfileInMapByName(v7, v23, v11 + 16LL * v10, a2);
    v11 = *((_QWORD *)this + 4);
    if ( v12 != *(_QWORD *)(v11 + 16LL * v10) )
    {
      v17 = L"manual";
      if ( *(_DWORD *)(v12 + 3236) )
        v17 = L"auto";
      v22 = v10;
      WwanLog::Info("ProfileHolder::DeleteProfile", 0, L" removing %s (pri %d, %s profile)", v12 + 40, v22, v17);
      if ( a3 )
        WwanProfileCopyProfile(v25, v12 + 40);
      WwanProfileCleanup(v12 + 40);
      v18 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,enum _WWAN_RADIO>>>::_Extract(
                        *((_QWORD *)this + 4) + 16LL * v10,
                        v12);
      std::_Deallocate<16>(v18, 0x18D8u);
      goto LABEL_27;
    }
    ++v10;
  }
  while ( v10 < 4 );
  v13 = (const wchar_t **)*((_QWORD *)this + 5);
  for ( i = *v13; i != (const wchar_t *)v13; i = *(const wchar_t **)i )
  {
    if ( !wcsncmp_0(a2, i + 8, 0x100u) )
    {
      CreationTypePriority = GetCreationTypePriority(*((unsigned int *)i + 773));
      WwanLog::Info(
        "ProfileHolder::DeleteProfile",
        0,
        L" removing %s (pri %d purchase profile)",
        a2,
        CreationTypePriority);
      if ( a3 )
        WwanProfileCopyProfile(v25, i + 8);
      v15 = (char *)this + 40;
      goto LABEL_20;
    }
  }
  v16 = (const wchar_t **)*((_QWORD *)this + 7);
  for ( i = *v16; ; i = *(const wchar_t **)i )
  {
    if ( i == (const wchar_t *)v16 )
    {
      WwanLog::Info("ProfileHolder::DeleteProfile", 0, L" the profile %s not found", a2);
      v6 = 1168;
      goto LABEL_27;
    }
    if ( !wcsncmp_0(a2, i + 8, 0x100u) )
      break;
  }
  WwanLog::Info("ProfileHolder::DeleteProfile", 0, L" removing %s (ModemOperatorProvisioned profile)", a2);
  if ( a3 )
    WwanProfileCopyProfile(v25, i + 8);
  v15 = (char *)this + 56;
LABEL_20:
  std::list<WWAN_PROFILE>::erase(v15, v23, i);
  v6 = 0;
LABEL_27:
  if ( a3 )
  {
    for ( j = (__int64 *)*((_QWORD *)this + 10);
          ;
          ProfileHandler::OnProfileDeleted((ProfileHandler *)j[4], (struct WWAN_PROFILE *)v25) )
    {
      j = (__int64 *)*j;
      if ( j == *((__int64 **)this + 10) )
        break;
    }
  }
  WwanProfileCleanup(v25);
  std::wstring::_Tidy_deallocate(v24);
  return v6;
}

```

## disassembly

```asm
0x1800a9054  mov     [rsp-8+arg_10], rbx
0x1800a9059  push    rbp
0x1800a905a  push    rsi
0x1800a905b  push    rdi
0x1800a905c  push    r12
0x1800a905e  push    r13
0x1800a9060  push    r14
0x1800a9062  push    r15
0x1800a9064  lea     rbp, [rsp-1820h]
0x1800a906c  mov     eax, 1920h
0x1800a9071  call    _alloca_probe
0x1800a9076  sub     rsp, rax
0x1800a9079  mov     rax, cs:__security_cookie
0x1800a9080  xor     rax, rsp
0x1800a9083  mov     [rbp+1850h+var_40], rax
0x1800a908a  mov     r13b, r8b
0x1800a908d  mov     r15, rdx
0x1800a9090  mov     rsi, rcx
0x1800a9093  xor     r12d, r12d
0x1800a9096  mov     [rsp+1950h+var_1920], r12d
0x1800a909b  lea     rcx, [rsp+1950h+var_1910]
0x1800a90a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a90a5  nop
0x1800a90a6  xor     edx, edx; Val
0x1800a90a8  mov     r8d, 18B0h; Size
0x1800a90ae  lea     rcx, [rsp+1950h+var_18F0]; void *
0x1800a90b3  call    memset_0
0x1800a90b8  lea     rcx, [rsp+1950h+var_18F0]
0x1800a90bd  call    cs:__imp_WwanProfileInit
0x1800a90c3  test    cs:byte_1801528C4, 10h
0x1800a90ca  jz      short loc_1800A90E6
0x1800a90cc  mov     rcx, rsi
0x1800a90cf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a90d4  mov     r9, r15
0x1800a90d7  mov     r8, rax
0x1800a90da  lea     rdx, PHDeleteProfile
0x1800a90e1  call    McTemplateU0zz_EventWriteTransfer
0x1800a90e6  xor     r14d, r14d
0x1800a90e9  mov     rax, [rsi+20h]
0x1800a90ed  mov     edi, r14d
0x1800a90f0  add     rdi, rdi
0x1800a90f3  lea     r8, [rax+rdi*8]
0x1800a90f7  mov     r9, r15
0x1800a90fa  lea     rdx, [rsp+1950h+var_1918]
0x1800a90ff  call    ?FindProfileInMapByName@ProfileHolder@@AEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUWWAN_PROFILE@@@std@@@std@@@std@@@std@@AEAV?$multimap@KUWWAN_PROFILE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUWWAN_PROFILE@@@std@@@3@@3@PEBG@Z; ProfileHolder::FindProfileInMapByName(std::multimap<ulong,WWAN_PROFILE> &,ushort const *)
0x1800a9104  mov     rbx, [rax]
0x1800a9107  mov     rax, [rsi+20h]
0x1800a910b  cmp     rbx, [rax+rdi*8]
0x1800a910f  jnz     loc_1800A9214
0x1800a9115  inc     r14d
0x1800a9118  cmp     r14d, 4
0x1800a911c  jb      short loc_1800A90ED
0x1800a911e  mov     rdi, [rsi+28h]
0x1800a9122  mov     rbx, [rdi]
0x1800a9125  cmp     rbx, rdi
0x1800a9128  jz      short loc_1800A9186
0x1800a912a  mov     r8d, 100h; MaxCount
0x1800a9130  lea     rdx, [rbx+10h]; String2
0x1800a9134  mov     rcx, r15; String1
0x1800a9137  call    wcsncmp_0
0x1800a913c  test    eax, eax
0x1800a913e  jz      short loc_1800A9145
0x1800a9140  mov     rbx, [rbx]
0x1800a9143  jmp     short loc_1800A9125
0x1800a9145  mov     ecx, [rbx+0C14h]
0x1800a914b  call    ?GetCreationTypePriority@@YAKW4WWAN_PROFILE_CREATION_TYPE@@@Z; GetCreationTypePriority(WWAN_PROFILE_CREATION_TYPE)
0x1800a9150  mov     [rsp+1950h+var_1930], eax
0x1800a9154  mov     r9, r15
0x1800a9157  lea     r8, aRemovingSPriDP; " removing %s (pri %d purchase profile)"
0x1800a915e  xor     edx, edx; struct _GUID *
0x1800a9160  lea     rcx, aProfileholderD; "ProfileHolder::DeleteProfile"
0x1800a9167  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a916c  test    r13b, r13b
0x1800a916f  jz      short loc_1800A9180
0x1800a9171  lea     rdx, [rbx+10h]
0x1800a9175  lea     rcx, [rsp+1950h+var_18F0]
0x1800a917a  call    cs:__imp_WwanProfileCopyProfile
0x1800a9180  lea     rcx, [rsi+28h]
0x1800a9184  jmp     short loc_1800A91DD
0x1800a9186  mov     rdi, [rsi+38h]
0x1800a918a  mov     rbx, [rdi]
0x1800a918d  cmp     rbx, rdi
0x1800a9190  jz      short loc_1800A91F4
0x1800a9192  mov     r8d, 100h; MaxCount
0x1800a9198  lea     rdx, [rbx+10h]; String2
0x1800a919c  mov     rcx, r15; String1
0x1800a919f  call    wcsncmp_0
0x1800a91a4  test    eax, eax
0x1800a91a6  jz      short loc_1800A91AD
0x1800a91a8  mov     rbx, [rbx]
0x1800a91ab  jmp     short loc_1800A918D
0x1800a91ad  mov     r9, r15
0x1800a91b0  lea     r8, aRemovingSModem; " removing %s (ModemOperatorProvisioned "...
0x1800a91b7  xor     edx, edx; struct _GUID *
0x1800a91b9  lea     rcx, aProfileholderD; "ProfileHolder::DeleteProfile"
0x1800a91c0  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a91c5  test    r13b, r13b
0x1800a91c8  jz      short loc_1800A91D9
0x1800a91ca  lea     rdx, [rbx+10h]
0x1800a91ce  lea     rcx, [rsp+1950h+var_18F0]
0x1800a91d3  call    cs:__imp_WwanProfileCopyProfile
0x1800a91d9  lea     rcx, [rsi+38h]
0x1800a91dd  lea     rdx, [rsp+1950h+var_1918]
0x1800a91e2  mov     r8, rbx
0x1800a91e5  call    ?erase@?$list@UWWAN_PROFILE@@V?$allocator@UWWAN_PROFILE@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@UWWAN_PROFILE@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UWWAN_PROFILE@@@std@@@std@@@2@@Z; std::list<WWAN_PROFILE>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<WWAN_PROFILE>>>)
0x1800a91ea  mov     r12d, [rsp+1950h+var_1920]
0x1800a91ef  jmp     loc_1800A928F
0x1800a91f4  mov     r9, r15
0x1800a91f7  lea     r8, aTheProfileSNot_0; " the profile %s not found"
0x1800a91fe  xor     edx, edx; struct _GUID *
0x1800a9200  lea     rcx, aProfileholderD; "ProfileHolder::DeleteProfile"
0x1800a9207  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a920c  mov     r12d, 490h
0x1800a9212  jmp     short loc_1800A928F
0x1800a9214  lea     rdi, [rbx+28h]
0x1800a9218  lea     rcx, aAuto_0; "auto"
0x1800a921f  lea     rax, aManual_0; "manual"
0x1800a9226  cmp     dword ptr [rdi+0C7Ch], 0
0x1800a922d  cmovnz  rax, rcx
0x1800a9231  mov     [rsp+1950h+var_1928], rax
0x1800a9236  mov     [rsp+1950h+var_1930], r14d
0x1800a923b  mov     r9, rdi
0x1800a923e  lea     r8, aRemovingSPriDS; " removing %s (pri %d, %s profile)"
0x1800a9245  xor     edx, edx; struct _GUID *
0x1800a9247  lea     rcx, aProfileholderD; "ProfileHolder::DeleteProfile"
0x1800a924e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a9253  test    r13b, r13b
0x1800a9256  jz      short loc_1800A9266
0x1800a9258  mov     rdx, rdi
0x1800a925b  lea     rcx, [rsp+1950h+var_18F0]
0x1800a9260  call    cs:__imp_WwanProfileCopyProfile
0x1800a9266  mov     rcx, rdi
0x1800a9269  call    cs:__imp_WwanProfileCleanup
0x1800a926f  mov     ecx, r14d
0x1800a9272  shl     rcx, 4
0x1800a9276  add     rcx, [rsi+20h]
0x1800a927a  mov     rdx, rbx
0x1800a927d  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@W4_WWAN_RADIO@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@W4_WWAN_RADIO@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@W4_WWAN_RADIO@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_WWAN_RADIO>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_WWAN_RADIO>>>,std::_Iterator_base0>)
0x1800a9282  mov     edx, 18D8h
0x1800a9287  mov     rcx, rax
0x1800a928a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a928f  test    r13b, r13b
0x1800a9292  jz      short loc_1800A92B1
0x1800a9294  mov     rbx, [rsi+50h]
0x1800a9298  mov     rbx, [rbx]
0x1800a929b  cmp     rbx, [rsi+50h]
0x1800a929f  jz      short loc_1800A92B1
0x1800a92a1  lea     rdx, [rsp+1950h+var_18F0]; struct WWAN_PROFILE *
0x1800a92a6  mov     rcx, [rbx+20h]; this
0x1800a92aa  call    ?OnProfileDeleted@ProfileHandler@@QEAAXAEAUWWAN_PROFILE@@@Z; ProfileHandler::OnProfileDeleted(WWAN_PROFILE &)
0x1800a92af  jmp     short loc_1800A9298
0x1800a92b1  lea     rcx, [rsp+1950h+var_18F0]
0x1800a92b6  call    cs:__imp_WwanProfileCleanup
0x1800a92bc  nop
0x1800a92bd  lea     rcx, [rsp+1950h+var_1910]
0x1800a92c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a92c7  mov     eax, r12d
0x1800a92ca  mov     rcx, [rbp+1850h+var_40]
0x1800a92d1  xor     rcx, rsp; StackCookie
0x1800a92d4  call    __security_check_cookie
0x1800a92d9  mov     rbx, [rsp+1950h+arg_10]
0x1800a92e1  add     rsp, 1920h
0x1800a92e8  pop     r15
0x1800a92ea  pop     r14
0x1800a92ec  pop     r13
0x1800a92ee  pop     r12
0x1800a92f0  pop     rdi
0x1800a92f1  pop     rsi
0x1800a92f2  pop     rbp
0x1800a92f3  retn
```
