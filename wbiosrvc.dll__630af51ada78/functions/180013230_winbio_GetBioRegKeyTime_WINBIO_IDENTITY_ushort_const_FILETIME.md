# winbio::GetBioRegKeyTime(_WINBIO_IDENTITY *,ushort const *,_FILETIME *)

- ea: `0x180013230`
- end: `0x1800133e5`
- name: `?GetBioRegKeyTime@winbio@@YAJPEAU_WINBIO_IDENTITY@@PEBGPEAU_FILETIME@@@Z`
- size: `437`
- prototype: `int(winbio *__hidden this, struct _WINBIO_IDENTITY *, const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800283dc`
- `0x1800286b4`

## callees

- `0x180013230`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x1800148b4`
- `0x180014914`
- `0x18005388c`
- `0x180058504`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013349`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013349`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001327e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001327e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800132d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800132d3`

## string_xrefs

- `0x1800133d1`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winbio::GetBioRegKeyTime(winbio *this, const WCHAR *a2, unsigned __int16 *a3, struct _FILETIME *a4)
{
  char *v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  int WinBioRegistryLocation; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  const WCHAR *v16; // rax
  LSTATUS ValueW; // eax
  signed int LastError; // eax
  int pdwType; // [rsp+20h] [rbp-60h]
  DWORD pcbData; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-38h] BYREF
  __int64 pvData; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v24[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( a2 != L"BioEnrolledTime" && a2 != L"LastBioUseTime" )
    return 2147942487LL;
  if ( !this )
    return 2147500035LL;
  if ( *(_DWORD *)this != 3 )
    return 2147942487LL;
  v6 = (char *)this + 8;
  if ( !IsValidSid((char *)this + 8) )
    return 2147942487LL;
  std::wstring::wstring(v24, v7, v8, v9);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v24);
  v11 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      pdwType);
  }
  else
  {
    v12 = std::_WChar_traits<unsigned short>::length(L"AccountInfo\\");
    std::wstring::_Append<unsigned short>(v24, v13, v12);
    StringSid = 0;
    if ( ConvertSidToStringSidW(v6, &StringSid) )
    {
      v14 = std::_WChar_traits<unsigned short>::length(StringSid);
      std::wstring::_Append<unsigned short>(v24, v15, v14);
      LocalFree(StringSid);
      pvData = 0;
      pcbData = 8;
      v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v16, a2, 0x20000040u, 0, &pvData, &pcbData);
      if ( ValueW )
      {
        if ( ValueW <= 0 )
          v11 = ValueW;
        else
          v11 = (unsigned __int16)ValueW | 0x80070000;
      }
      else
      {
        *(_QWORD *)a3 = pvData;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = LastError;
    }
  }
  std::wstring::_Tidy_deallocate(v24);
  return v11;
}

```

## disassembly

```asm
0x180013230  push    rbp
0x180013232  push    rbx
0x180013233  push    rsi
0x180013234  push    rdi
0x180013235  push    r14
0x180013237  mov     rbp, rsp
0x18001323a  sub     rsp, 80h
0x180013241  mov     rax, cs:__security_cookie
0x180013248  xor     rax, rsp
0x18001324b  mov     [rbp+var_8], rax
0x18001324f  mov     r14, r8
0x180013252  mov     rdi, rdx
0x180013255  lea     rax, aBioenrolledtim; "BioEnrolledTime"
0x18001325c  cmp     rdx, rax
0x18001325f  jnz     loc_180013389
0x180013265  test    rcx, rcx
0x180013268  jz      loc_1800133C3
0x18001326e  cmp     dword ptr [rcx], 3
0x180013271  jnz     loc_180013399
0x180013277  lea     rsi, [rcx+8]
0x18001327b  mov     rcx, rsi; pSid
0x18001327e  call    cs:__imp_IsValidSid
0x180013284  test    eax, eax
0x180013286  jz      loc_180013399
0x18001328c  lea     rcx, [rbp+var_28]
0x180013290  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013295  nop
0x180013296  lea     rcx, [rbp+var_28]
0x18001329a  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x18001329f  mov     ebx, eax
0x1800132a1  test    eax, eax
0x1800132a3  js      loc_1800133CA
0x1800132a9  lea     rcx, aAccountinfo; "AccountInfo\\"
0x1800132b0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800132b5  mov     r8, rax
0x1800132b8  mov     rdx, rcx
0x1800132bb  lea     rcx, [rbp+var_28]
0x1800132bf  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800132c4  mov     [rbp+StringSid], 0
0x1800132cc  lea     rdx, [rbp+StringSid]; StringSid
0x1800132d0  mov     rcx, rsi; Sid
0x1800132d3  call    cs:__imp_ConvertSidToStringSidW
0x1800132d9  test    eax, eax
0x1800132db  jz      loc_1800133AD
0x1800132e1  mov     rcx, [rbp+StringSid]
0x1800132e5  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800132ea  mov     r8, rax
0x1800132ed  mov     rdx, rcx
0x1800132f0  lea     rcx, [rbp+var_28]
0x1800132f4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800132f9  mov     rcx, [rbp+StringSid]; hMem
0x1800132fd  call    cs:__imp_LocalFree
0x180013303  mov     [rbp+var_30], 0
0x18001330b  mov     [rbp+var_40], 8
0x180013312  lea     rcx, [rbp+var_28]
0x180013316  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001331b  mov     rdx, rax; lpSubKey
0x18001331e  lea     rax, [rbp+var_40]
0x180013322  mov     [rsp+80h+pcbData], rax; pcbData
0x180013327  lea     rax, [rbp+var_30]
0x18001332b  mov     [rsp+80h+pvData], rax; pvData
0x180013330  mov     [rsp+80h+pdwType], 0; pdwType
0x180013339  mov     r9d, 20000040h; dwFlags
0x18001333f  mov     r8, rdi; lpValue
0x180013342  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180013349  call    cs:__imp_RegGetValueW
0x18001334f  test    eax, eax
0x180013351  jz      short loc_1800133A0
0x180013353  jle     short loc_1800133A9
0x180013355  movzx   ebx, ax
0x180013358  or      ebx, 80070000h
0x18001335e  xor     eax, eax
0x180013360  test    ebx, ebx
0x180013362  jns     short loc_1800133A4
0x180013364  lea     rcx, [rbp+var_28]
0x180013368  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001336d  mov     eax, ebx
0x18001336f  mov     rcx, [rbp+var_8]
0x180013373  xor     rcx, rsp; StackCookie
0x180013376  call    __security_check_cookie
0x18001337b  add     rsp, 80h
0x180013382  pop     r14
0x180013384  pop     rdi
0x180013385  pop     rsi
0x180013386  pop     rbx
0x180013387  pop     rbp
0x180013388  retn
0x180013389  lea     rax, aLastbiousetime; "LastBioUseTime"
0x180013390  cmp     rdi, rax
0x180013393  jz      loc_180013265
0x180013399  mov     eax, 80070057h
0x18001339e  jmp     short loc_18001336F
0x1800133a0  mov     rax, [rbp+var_30]
0x1800133a4  mov     [r14], rax
0x1800133a7  jmp     short loc_180013364
0x1800133a9  mov     ebx, eax
0x1800133ab  jmp     short loc_18001335E
0x1800133ad  call    cs:__imp_GetLastError
0x1800133b3  test    eax, eax
0x1800133b5  jle     short loc_1800133BF
0x1800133b7  movzx   eax, ax
0x1800133ba  or      eax, 80070000h
0x1800133bf  mov     ebx, eax
0x1800133c1  jmp     short loc_180013364
0x1800133c3  mov     eax, 80004003h
0x1800133c8  jmp     short loc_18001336F
0x1800133ca  mov     rcx, [rbp+28h]; this
0x1800133ce  mov     r9d, eax; char *
0x1800133d1  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800133d8  mov     edx, 11Fh; void *
0x1800133dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800133e2  jmp     short loc_180013364
```
