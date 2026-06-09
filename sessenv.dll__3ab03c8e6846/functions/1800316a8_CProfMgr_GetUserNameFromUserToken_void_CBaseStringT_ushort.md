# CProfMgr::GetUserNameFromUserToken(void *,CBaseStringT<ushort> &)

- ea: `0x1800316a8`
- end: `0x1800318f1`
- name: `?GetUserNameFromUserToken@CProfMgr@@AEAAJPEAXAEAV?$CBaseStringT@G@@@Z`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031f00`

## callees

- `0x180003f30`
- `0x180004db0`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x1800316a8`
- `0x1800318f8`
- `0x180032754`
- `0x180032808`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031861`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800317dd`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180031857`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800317dd`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180031857`

## string_xrefs

- `0x18003171e`: `hTokenUser`
- `0x180031714`: `CProfMgr::GetUserNameFromUserToken`
- `0x1800318bc`: `CProfMgr::GetUserNameFromUserToken`
- `0x18003174d`: `GetUserSid() failed: 0x%x in %s`
- `0x180031883`: `LookupAccountSid() failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CProfMgr::GetUserNameFromUserToken(__int64 a1, void *a2, __int64 a3)
{
  unsigned int v4; // ebx
  int UserSid; // eax
  int v6; // eax
  int v7; // eax
  WCHAR *Buffer; // rax
  LPWSTR v9; // r10
  signed int LastError; // edi
  WCHAR *v11; // rax
  LPWSTR v12; // r10
  int v13; // eax
  int v14; // eax
  PSID Sid; // [rsp+30h] [rbp-30h] BYREF
  const int *v17; // [rsp+38h] [rbp-28h] BYREF
  int v18; // [rsp+40h] [rbp-20h]
  __int64 v19; // [rsp+44h] [rbp-1Ch]
  int v20; // [rsp+4Ch] [rbp-14h]
  __int64 v21; // [rsp+50h] [rbp-10h]
  int v22; // [rsp+58h] [rbp-8h]
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+30h] BYREF
  int v24; // [rsp+94h] [rbp+34h]
  DWORD cchName; // [rsp+98h] [rbp+38h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A8h] [rbp+48h] BYREF

  v24 = HIDWORD(a1);
  Sid = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  v17 = &CBaseStringT<unsigned short>::`vftable';
  v19 = 128;
  peUse = SidTypeUnknown;
  v21 = 0;
  v20 = 0;
  v22 = 0x8000000;
  v18 = 0;
  if ( !a2 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "hTokenUser", "CProfMgr::GetUserNameFromUserToken");
    v4 = -2147024809;
    goto LABEL_26;
  }
  UserSid = GetUserSid(a2, &Sid);
  v4 = UserSid;
  if ( UserSid < 0 )
  {
    _DbgPrintMessage(8, "GetUserSid() failed: 0x%x in %s", (unsigned int)UserSid, "CProfMgr::GetUserNameFromUserToken");
    goto LABEL_24;
  }
  v6 = CBaseStringT<unsigned short>::EnsureSpace(a3, 128);
  v4 = v6;
  if ( v6 < 0 )
    goto LABEL_6;
  cchName = CBaseStringT<unsigned short>::GetBufferLength(a3);
  v7 = CBaseStringT<unsigned short>::EnsureSpace(&v17, 128);
  v4 = v7;
  if ( v7 < 0 )
  {
LABEL_8:
    _DbgPrintMessage(
      8,
      "strUserDomain.EnsureBuffer() failed: 0x%x in %s",
      (unsigned int)v7,
      "CProfMgr::GetUserNameFromUserToken");
    goto LABEL_24;
  }
  cchReferencedDomainName = CBaseStringT<unsigned short>::GetBufferLength(&v17);
  CBaseStringT<unsigned short>::GetBuffer(&v17);
  Buffer = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(a3);
  if ( LookupAccountSidLocalW(Sid, Buffer, &cchName, v9, &cchReferencedDomainName, &peUse) )
    goto LABEL_20;
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v6 = CBaseStringT<unsigned short>::EnsureSpace(a3, cchName);
    v4 = v6;
    if ( v6 < 0 )
    {
LABEL_6:
      _DbgPrintMessage(
        8,
        "strUserName.EnsureBuffer() failed: 0x%x in %s",
        (unsigned int)v6,
        "CProfMgr::GetUserNameFromUserToken");
      goto LABEL_24;
    }
    v7 = CBaseStringT<unsigned short>::EnsureSpace(&v17, cchReferencedDomainName);
    v4 = v7;
    if ( v7 < 0 )
      goto LABEL_8;
    CBaseStringT<unsigned short>::GetBuffer(&v17);
    v11 = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(a3);
    if ( LookupAccountSidLocalW(Sid, v11, &cchName, v12, &cchReferencedDomainName, &peUse) )
      goto LABEL_18;
    LastError = GetLastError();
  }
  if ( !LastError )
  {
LABEL_20:
    v13 = CBaseStringT<unsigned short>::SetLength(a3);
    v4 = v13;
    if ( v13 >= 0 )
    {
      v14 = CBaseStringT<unsigned short>::SetLength(&v17);
      v4 = v14;
      if ( v14 < 0 )
        _DbgPrintMessage(
          8,
          "strUserDomain.SetLength() failed: 0x%x in %s",
          (unsigned int)v14,
          "CProfMgr::GetUserNameFromUserToken");
    }
    else
    {
      _DbgPrintMessage(
        8,
        "strUserName.SetLength() failed: 0x%x in %s",
        (unsigned int)v13,
        "CProfMgr::GetUserNameFromUserToken");
    }
    goto LABEL_24;
  }
  if ( LastError > 0 )
  {
LABEL_18:
    v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_19;
  }
  v4 = LastError;
LABEL_19:
  _DbgPrintMessage(8, "LookupAccountSid() failed: 0x%x in %s", v4, "CProfMgr::GetUserNameFromUserToken");
LABEL_24:
  if ( Sid )
    ResultFromHeapFree(Sid);
LABEL_26:
  CPathString::~CPathString((CPathString *)&v17);
  return v4;
}

```

## disassembly

```asm
0x1800316a8  mov     qword ptr [rsp-28h+arg_0], rcx
0x1800316ad  push    rbp
0x1800316ae  push    rbx
0x1800316af  push    rsi
0x1800316b0  push    rdi
0x1800316b1  push    r12
0x1800316b3  mov     rbp, rsp
0x1800316b6  sub     rsp, 60h
0x1800316ba  mov     [rbp+Sid], 0
0x1800316c2  mov     edi, 80h
0x1800316c7  mov     [rbp+cchName], 0
0x1800316ce  lea     rcx, ??_7?$CBaseStringT@G@@6B@; const CBaseStringT<ushort>::`vftable'
0x1800316d5  mov     [rbp+arg_0], 0
0x1800316dc  mov     rsi, r8
0x1800316df  mov     [rbp+var_28], rcx
0x1800316e3  mov     rax, rdx
0x1800316e6  mov     [rbp+var_1C], rdi
0x1800316ea  lea     r12d, [rdi-78h]
0x1800316ee  mov     [rbp+arg_18], r12d
0x1800316f2  mov     [rbp+var_10], 0
0x1800316fa  mov     [rbp+var_14], 0
0x180031701  mov     [rbp+var_8], 8000000h
0x180031708  mov     [rbp+var_20], 0
0x18003170f  test    rdx, rdx
0x180031712  jnz     short loc_18003173B
0x180031714  lea     r9, aCprofmgrGetuse; "CProfMgr::GetUserNameFromUserToken"
0x18003171b  mov     ecx, r12d; int
0x18003171e  lea     r8, aHtokenuser; "hTokenUser"
0x180031725  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18003172c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031731  mov     ebx, 80070057h
0x180031736  jmp     loc_1800318DB
0x18003173b  lea     rdx, [rbp+Sid]; void **
0x18003173f  mov     rcx, rax; TokenHandle
0x180031742  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180031747  mov     ebx, eax
0x180031749  test    eax, eax
0x18003174b  jns     short loc_180031759
0x18003174d  lea     rdx, aGetusersidFail_0; "GetUserSid() failed: 0x%x in %s"
0x180031754  jmp     loc_1800318B9
0x180031759  mov     edx, edi
0x18003175b  mov     rcx, rsi
0x18003175e  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180031763  mov     ebx, eax
0x180031765  test    eax, eax
0x180031767  jns     short loc_180031775
0x180031769  lea     rdx, aStrusernameEns; "strUserName.EnsureBuffer() failed: 0x%x"...
0x180031770  jmp     loc_1800318B9
0x180031775  mov     rcx, rsi
0x180031778  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x18003177d  mov     edx, edi
0x18003177f  mov     [rbp+cchName], eax
0x180031782  lea     rcx, [rbp+var_28]
0x180031786  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x18003178b  mov     ebx, eax
0x18003178d  test    eax, eax
0x18003178f  jns     short loc_18003179D
0x180031791  lea     rdx, aStruserdomainE; "strUserDomain.EnsureBuffer() failed: 0x"...
0x180031798  jmp     loc_1800318B9
0x18003179d  lea     rcx, [rbp+var_28]
0x1800317a1  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x1800317a6  lea     rcx, [rbp+var_28]
0x1800317aa  mov     [rbp+arg_0], eax
0x1800317ad  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x1800317b2  mov     rcx, rsi
0x1800317b5  mov     r10, rax
0x1800317b8  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x1800317bd  lea     rcx, [rbp+arg_18]
0x1800317c1  mov     r9, r10; ReferencedDomainName
0x1800317c4  mov     [rsp+60h+peUse], rcx; peUse
0x1800317c9  lea     r8, [rbp+cchName]; cchName
0x1800317cd  lea     rcx, [rbp+arg_0]
0x1800317d1  mov     rdx, rax; Name
0x1800317d4  mov     [rsp+60h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800317d9  mov     rcx, [rbp+Sid]; Sid
0x1800317dd  call    cs:__imp_LookupAccountSidLocalW
0x1800317e3  test    eax, eax
0x1800317e5  jnz     loc_18003188C
0x1800317eb  call    cs:__imp_GetLastError
0x1800317f1  mov     edi, eax
0x1800317f3  cmp     eax, 7Ah ; 'z'
0x1800317f6  jnz     short loc_180031869
0x1800317f8  mov     edx, [rbp+cchName]
0x1800317fb  mov     rcx, rsi
0x1800317fe  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180031803  mov     ebx, eax
0x180031805  test    eax, eax
0x180031807  js      loc_180031769
0x18003180d  mov     edx, [rbp+arg_0]
0x180031810  lea     rcx, [rbp+var_28]
0x180031814  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180031819  mov     ebx, eax
0x18003181b  test    eax, eax
0x18003181d  js      loc_180031791
0x180031823  lea     rcx, [rbp+var_28]
0x180031827  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x18003182c  mov     rcx, rsi
0x18003182f  mov     r10, rax
0x180031832  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180031837  lea     rcx, [rbp+arg_18]
0x18003183b  mov     r9, r10; ReferencedDomainName
0x18003183e  mov     [rsp+60h+peUse], rcx; peUse
0x180031843  lea     r8, [rbp+cchName]; cchName
0x180031847  lea     rcx, [rbp+arg_0]
0x18003184b  mov     rdx, rax; Name
0x18003184e  mov     [rsp+60h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180031853  mov     rcx, [rbp+Sid]; Sid
0x180031857  call    cs:__imp_LookupAccountSidLocalW
0x18003185d  test    eax, eax
0x18003185f  jnz     short loc_180031873
0x180031861  call    cs:__imp_GetLastError
0x180031867  mov     edi, eax
0x180031869  test    edi, edi
0x18003186b  jz      short loc_18003188C
0x18003186d  jg      short loc_180031873
0x18003186f  mov     ebx, edi
0x180031871  jmp     short loc_18003187C
0x180031873  movzx   ebx, di
0x180031876  or      ebx, 80070000h
0x18003187c  test    ebx, ebx
0x18003187e  jns     short loc_18003188C
0x180031880  mov     r8d, ebx
0x180031883  lea     rdx, aLookupaccounts_4; "LookupAccountSid() failed: 0x%x in %s"
0x18003188a  jmp     short loc_1800318BC
0x18003188c  mov     rcx, rsi
0x18003188f  call    ?SetLength@?$CBaseStringT@G@@QEAAJXZ; CBaseStringT<ushort>::SetLength(void)
0x180031894  mov     ebx, eax
0x180031896  test    eax, eax
0x180031898  jns     short loc_1800318A3
0x18003189a  lea     rdx, aStrusernameSet; "strUserName.SetLength() failed: 0x%x in"...
0x1800318a1  jmp     short loc_1800318B9
0x1800318a3  lea     rcx, [rbp+var_28]
0x1800318a7  call    ?SetLength@?$CBaseStringT@G@@QEAAJXZ; CBaseStringT<ushort>::SetLength(void)
0x1800318ac  mov     ebx, eax
0x1800318ae  test    eax, eax
0x1800318b0  jns     short loc_1800318CB
0x1800318b2  lea     rdx, aStruserdomainS; "strUserDomain.SetLength() failed: 0x%x "...
0x1800318b9  mov     r8d, eax
0x1800318bc  lea     r9, aCprofmgrGetuse; "CProfMgr::GetUserNameFromUserToken"
0x1800318c3  mov     ecx, r12d; int
0x1800318c6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800318cb  cmp     [rbp+Sid], 0
0x1800318d0  jz      short loc_1800318DB
0x1800318d2  mov     rcx, [rbp+Sid]; lpMem
0x1800318d6  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800318db  lea     rcx, [rbp+var_28]; this
0x1800318df  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800318e4  mov     eax, ebx
0x1800318e6  add     rsp, 60h
0x1800318ea  pop     r12
0x1800318ec  pop     rdi
0x1800318ed  pop     rsi
0x1800318ee  pop     rbx
0x1800318ef  pop     rbp
0x1800318f0  retn
```
