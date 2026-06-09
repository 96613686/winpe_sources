# CAccountManager::PurgeBioTimestamps(_WINBIO_IDENTITY *)

- ea: `0x180077fcc`
- end: `0x1800781d9`
- name: `?PurgeBioTimestamps@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(struct _WINBIO_IDENTITY *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053ff0`

## callees

- `0x180011d90`
- `0x180014110`
- `0x1800142e0`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x180028af0`
- `0x18002b2f8`
- `0x18002b7c0`
- `0x180033378`
- `0x18005388c`
- `0x180058458`
- `0x180068f60`
- `0x18007762c`
- `0x180077fcc`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800780df`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007815c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800780df`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007815c`

## string_xrefs

- `0x180078008`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180078065`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x1800780f0`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x18007816d`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAccountManager::PurgeBioTimestamps(struct _WINBIO_IDENTITY *a1, __int64 a2, bool a3)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // ebx
  int WinBioRegistryLocation; // eax
  __int64 v10; // rdx
  struct CAccountManager *v11; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rax
  const WCHAR *v16; // rax
  unsigned int v17; // eax
  unsigned int v19; // [rsp+20h] [rbp-69h] BYREF
  __int64 v20; // [rsp+28h] [rbp-61h]
  _BYTE v21[32]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v23[32]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v24[32]; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v25[32]; // [rsp+B0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = winbio::ValidateIdentity((winbio *)a1, 0, a3);
  v8 = v4;
  if ( v4 >= 0 )
  {
    std::wstring::wstring(v21, v5, v6, v7);
    WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v21);
    v8 = WinBioRegistryLocation;
    if ( WinBioRegistryLocation >= 0 )
    {
      std::wstring::append(v21, L"AccountInfo\\");
      WinBioRegistryLocation = IdentityToRegPath(a1, v21);
      v8 = WinBioRegistryLocation;
      if ( WinBioRegistryLocation >= 0 )
      {
        v11 = CAccountManager::Instance();
        winbio::lockable_object::lock_exclusive(v11, &v19);
        v20 = 0;
        v12 = std::operator+<unsigned short>(v24, v21, L"\\");
        std::operator+<unsigned short>(v22, v12, L"BioEnrolledTime");
        std::wstring::_Tidy_deallocate(v24);
        v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
        v14 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v13);
        if ( v14 )
        {
          v8 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x581,
                 (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
                 (const char *)v14,
                 v19);
        }
        else
        {
          v15 = std::operator+<unsigned short>(v25, v21, L"\\");
          std::operator+<unsigned short>(v23, v15, L"LastBioUseTime");
          std::wstring::_Tidy_deallocate(v25);
          v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
          v17 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v16);
          if ( !v17 )
          {
            std::wstring::_Tidy_deallocate(v23);
            std::wstring::_Tidy_deallocate(v22);
            Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v19);
            v8 = 0;
            goto LABEL_14;
          }
          v8 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x584,
                 (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
                 (const char *)v17,
                 v19);
          std::wstring::_Tidy_deallocate(v23);
        }
        std::wstring::_Tidy_deallocate(v22);
        Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v19);
LABEL_14:
        std::wstring::_Tidy_deallocate(v21);
        return v8;
      }
      v10 = 1403;
    }
    else
    {
      v10 = 1400;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      v19);
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x575,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
    (const char *)(unsigned int)v4,
    v19);
  return v8;
}

```

## disassembly

```asm
0x180077fcc  mov     [rsp-8+arg_8], rbx
0x180077fd1  mov     [rsp-8+arg_10], rdi
0x180077fd6  push    rbp
0x180077fd7  lea     rbp, [rsp-57h]
0x180077fdc  sub     rsp, 0E0h
0x180077fe3  mov     rax, cs:__security_cookie
0x180077fea  xor     rax, rsp
0x180077fed  mov     [rbp+57h+var_10], rax
0x180077ff1  mov     rdi, rcx
0x180077ff4  xor     edx, edx; struct _WINBIO_IDENTITY *
0x180077ff6  call    ?ValidateIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@_N@Z; winbio::ValidateIdentity(_WINBIO_IDENTITY *,bool)
0x180077ffb  mov     ebx, eax
0x180077ffd  test    eax, eax
0x180077fff  jns     short loc_18007801E
0x180078001  mov     rcx, [rbp+5Fh]; this
0x180078005  mov     r9d, eax; char *
0x180078008  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x18007800f  mov     edx, 575h; void *
0x180078014  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078019  jmp     loc_1800781B6
0x18007801e  lea     rcx, [rbp+57h+var_B0]
0x180078022  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180078027  nop
0x180078028  lea     rcx, [rbp+57h+var_B0]
0x18007802c  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180078031  mov     ebx, eax
0x180078033  test    eax, eax
0x180078035  jns     short loc_18007803E
0x180078037  mov     edx, 578h
0x18007803c  jmp     short loc_180078065
0x18007803e  lea     rdx, aAccountinfo; "AccountInfo\\"
0x180078045  lea     rcx, [rbp+57h+var_B0]
0x180078049  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18007804e  lea     rdx, [rbp+57h+var_B0]
0x180078052  mov     rcx, rdi
0x180078055  call    IdentityToRegPath
0x18007805a  mov     ebx, eax
0x18007805c  test    eax, eax
0x18007805e  jns     short loc_18007807D
0x180078060  mov     edx, 57Bh; void *
0x180078065  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x18007806c  mov     r9d, eax; char *
0x18007806f  mov     rcx, [rbp+5Fh]; this
0x180078073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078078  jmp     loc_1800781AD
0x18007807d  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x180078082  lea     rdx, [rbp+57h+var_C0]
0x180078086  mov     rcx, rax
0x180078089  call    ?lock_exclusive@lockable_object@winbio@@QEBA?AVSyncLockExclusive@Details@Wrappers@WRL@Microsoft@@XZ; winbio::lockable_object::lock_exclusive(void)
0x18007808e  nop
0x18007808f  mov     [rbp+57h+var_B8], 0
0x180078097  lea     r8, asc_1800DC1E4; "\\"
0x18007809e  lea     rdx, [rbp+57h+var_B0]
0x1800780a2  lea     rcx, [rbp+57h+var_50]
0x1800780a6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800780ab  nop
0x1800780ac  lea     r8, aBioenrolledtim; "BioEnrolledTime"
0x1800780b3  mov     rdx, rax
0x1800780b6  lea     rcx, [rbp+57h+var_90]
0x1800780ba  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800780bf  nop
0x1800780c0  lea     rcx, [rbp+57h+var_50]
0x1800780c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800780c9  lea     rcx, [rbp+57h+var_90]
0x1800780cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800780d2  mov     rdx, rax; lpSubKey
0x1800780d5  mov     rbx, 0FFFFFFFF80000002h
0x1800780dc  mov     rcx, rbx; hKey
0x1800780df  call    cs:__imp_RegDeleteKeyW
0x1800780e5  test    eax, eax
0x1800780e7  jz      short loc_18007811B
0x1800780e9  mov     rcx, [rbp+5Fh]; this
0x1800780ed  mov     r9d, eax; char *
0x1800780f0  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x1800780f7  mov     edx, 581h; void *
0x1800780fc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180078101  mov     ebx, eax
0x180078103  lea     rcx, [rbp+57h+var_90]
0x180078107  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007810c  nop
0x18007810d  lea     rcx, [rbp+57h+var_C0]; this
0x180078111  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180078116  jmp     loc_1800781AD
0x18007811b  lea     r8, asc_1800DC1E4; "\\"
0x180078122  lea     rdx, [rbp+57h+var_B0]
0x180078126  lea     rcx, [rbp+57h+var_30]
0x18007812a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18007812f  nop
0x180078130  lea     r8, aLastbiousetime; "LastBioUseTime"
0x180078137  mov     rdx, rax
0x18007813a  lea     rcx, [rbp+57h+var_70]
0x18007813e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180078143  nop
0x180078144  lea     rcx, [rbp+57h+var_30]
0x180078148  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007814d  lea     rcx, [rbp+57h+var_70]
0x180078151  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078156  mov     rdx, rax; lpSubKey
0x180078159  mov     rcx, rbx; hKey
0x18007815c  call    cs:__imp_RegDeleteKeyW
0x180078162  test    eax, eax
0x180078164  jz      short loc_18007818E
0x180078166  mov     rcx, [rbp+5Fh]; this
0x18007816a  mov     r9d, eax; char *
0x18007816d  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180078174  mov     edx, 584h; void *
0x180078179  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007817e  mov     ebx, eax
0x180078180  lea     rcx, [rbp+57h+var_70]
0x180078184  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078189  jmp     loc_180078103
0x18007818e  lea     rcx, [rbp+57h+var_70]
0x180078192  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078197  nop
0x180078198  lea     rcx, [rbp+57h+var_90]
0x18007819c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800781a1  nop
0x1800781a2  lea     rcx, [rbp+57h+var_C0]; this
0x1800781a6  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800781ab  xor     ebx, ebx
0x1800781ad  lea     rcx, [rbp+57h+var_B0]
0x1800781b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800781b6  mov     eax, ebx
0x1800781b8  mov     rcx, [rbp+57h+var_10]
0x1800781bc  xor     rcx, rsp; StackCookie
0x1800781bf  call    __security_check_cookie
0x1800781c4  lea     r11, [rsp+0E0h+var_s0]
0x1800781cc  mov     rbx, [r11+18h]
0x1800781d0  mov     rdi, [r11+20h]
0x1800781d4  mov     rsp, r11
0x1800781d7  pop     rbp
0x1800781d8  retn
```
