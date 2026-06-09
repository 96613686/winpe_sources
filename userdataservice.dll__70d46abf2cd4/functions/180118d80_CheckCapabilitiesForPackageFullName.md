# CheckCapabilitiesForPackageFullName

- ea: `0x180118d80`
- end: `0x180119358`
- name: `CheckCapabilitiesForPackageFullName`
- size: `1496`
- prototype: `__int64 __fastcall(PCWSTR packageFullName)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180095d18`
- `0x180119360`

## callees

- `0x180004658`
- `0x180018c20`
- `0x1800303cc`
- `0x180042c58`
- `0x180042d18`
- `0x180064880`
- `0x180064904`
- `0x180065fb0`
- `0x1800977ac`
- `0x1800977b8`
- `0x180098534`
- `0x18009a274`
- `0x180118bd0`
- `0x180118c7c`
- `0x180118d80`
- `0x1801195e0`
- `0x1801197bc`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `ext-ms-win-security-chambers-l1-1-0!CreateTokenFromChamberSid` at `0x180118e73`
- `ext-ms-win-security-chambers-l1-1-0!CreateTokenFromChamberSid` at `0x180118e73`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118ea1`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118ece`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118ef9`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118f24`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118f56`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118f8a`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118ea1`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118ece`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118ef9`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118f24`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118f56`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180118f8a`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180118de7`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180118de7`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180119007`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180119007`

## string_xrefs

- `0x180119147`: `Windows.Internal.CapabilityAccess.CapabilityAccess`
- `0x180118f15`: `ID_CAP_SMS_COMPANION`
- `0x1801190a8`: `ID_CAP_SMS_COMPANION`

## pseudocode

```c
__int64 __fastcall CheckCapabilitiesForPackageFullName(PCWSTR packageFullName, _DWORD *a2)
{
  _DWORD *v3; // r15
  WCHAR *v4; // rax
  WCHAR *v5; // rbx
  LONG v7; // eax
  int PackageSidFromPackageFamilyName; // edi
  void **v9; // rax
  int v10; // edi
  int v11; // esi
  int v12; // r14d
  int v13; // r12d
  int v14; // esi
  unsigned int v15; // r12d
  int v16; // esi
  int v17; // eax
  int v18; // r13d
  int v19; // r12d
  unsigned int v20; // r12d
  int v21; // edi
  __int64 v22; // r15
  __int64 (__fastcall *v23)(__int64, PVOID, PVOID, PVOID, __int64 *); // r14
  PVOID Reserved1; // rsi
  HSTRING_HEADER *v25; // rax
  PVOID v26; // rdi
  HSTRING_HEADER *v27; // rax
  __int64 v28; // rdx
  _BYTE v29[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v30; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch] BYREF
  int v33; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v38[2]; // [rsp+88h] [rbp-78h] BYREF
  _WORD v39[8]; // [rsp+98h] [rbp-68h] BYREF
  const WCHAR *v40; // [rsp+A8h] [rbp-58h] BYREF
  __int64 *v41; // [rsp+B0h] [rbp-50h]
  _WORD v42[8]; // [rsp+B8h] [rbp-48h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+C8h] [rbp-38h] BYREF
  const WCHAR *v44; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD *v45; // [rsp+D8h] [rbp-28h]
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v47; // [rsp+F8h] [rbp-8h]
  HSTRING_HEADER v48; // [rsp+100h] [rbp+0h] BYREF
  HSTRING_HEADER v49; // [rsp+120h] [rbp+20h] BYREF

  v45 = a2;
  packageFamilyNameLength = 65;
  *a2 = 0;
  v3 = a2;
  v4 = (WCHAR *)operator new[](0x82u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v7 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, v4);
  PackageSidFromPackageFamilyName = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      PackageSidFromPackageFamilyName = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_43;
  }
  v39[0] = 0;
  v38[0] = v39;
  v38[1] = v39;
  PackageSidFromPackageFamilyName = GetPackageSidFromPackageFamilyName(v5, (__int64)v38);
  if ( PackageSidFromPackageFamilyName < 0 )
    goto LABEL_7;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( (unsigned __int8)IsCreateTokenFromChamberSidPresent() )
  {
    v30 = 0;
    v9 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&v30);
    PackageSidFromPackageFamilyName = CreateTokenFromChamberSid(v38[0], 1, v9);
    if ( PackageSidFromPackageFamilyName < 0 )
    {
LABEL_10:
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v30);
LABEL_7:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
LABEL_43:
      operator delete(v5);
      return (unsigned int)PackageSidFromPackageFamilyName;
    }
    v29[0] = 0;
    v10 = CapabilityCheck(v30, L"ID_CAP_SMS", v29);
    if ( v10 < 0 )
      goto LABEL_12;
    v11 = v29[0];
    v29[0] = 0;
    v10 = CapabilityCheck(v30, L"chat", v29);
    if ( v10 < 0 )
      goto LABEL_12;
    v12 = v29[0];
    v29[0] = 0;
    v10 = CapabilityCheck(v30, L"chatSystem", v29);
    if ( v10 < 0 )
      goto LABEL_12;
    v13 = v29[0];
    v29[0] = 0;
    v14 = v12 | v11;
    v10 = CapabilityCheck(v30, L"ID_CAP_SMS_COMPANION", v29);
    if ( v10 < 0
      || (v15 = v14 | v13,
          v16 = v29[0],
          v32 = v29[0],
          v29[0] = 0,
          v10 = CapabilityCheck(v30, L"blockedChatMessages", v29),
          v10 < 0) )
    {
LABEL_12:
      PackageSidFromPackageFamilyName = v10 | 0x10000000;
      goto LABEL_10;
    }
    v33 = v29[0];
    v29[0] = 0;
    v17 = CapabilityCheck(v30, L"smsSend", v29);
    if ( v17 < 0 )
    {
      PackageSidFromPackageFamilyName = v17 | 0x10000000;
      goto LABEL_10;
    }
    v18 = v29[0];
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v30);
  }
  else
  {
    if ( !(unsigned __int8)IsQueryApplicationCapabilitiesPresent() )
    {
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
      operator delete(v5);
      return 2147549183LL;
    }
    v40 = (const WCHAR *)&v31;
    v41 = &v37;
    v31 = 0;
    v37 = 0;
    LOBYTE(v42[0]) = 1;
    PackageSidFromPackageFamilyName = QueryApplicationCapabilities(packageFullName, &v37, &v31, 0, 0, 0, 0, 0, 0);
    if ( PackageSidFromPackageFamilyName < 0 )
      goto LABEL_22;
    LODWORD(v30) = 0;
    PackageSidFromPackageFamilyName = CheckAppSidsForCapability(v31, v37, L"ID_CAP_SMS", &v30);
    if ( PackageSidFromPackageFamilyName < 0 )
      goto LABEL_22;
    v19 = (int)v30;
    LODWORD(v30) = 0;
    PackageSidFromPackageFamilyName = CheckAppSidsForCapability(v31, v37, L"chat", &v30);
    if ( PackageSidFromPackageFamilyName < 0
      || (v20 = (unsigned int)v30 | v19,
          LODWORD(v30) = 0,
          PackageSidFromPackageFamilyName = CheckAppSidsForCapability(v31, v37, L"chatSystem", &v30),
          PackageSidFromPackageFamilyName < 0)
      || (PackageSidFromPackageFamilyName = CheckAppSidsForCapability(v31, v37, L"ID_CAP_SMS_COMPANION", &v32),
          PackageSidFromPackageFamilyName < 0)
      || (PackageSidFromPackageFamilyName = CheckAppSidsForCapability(v31, v37, L"blockedChatMessages", &v33),
          PackageSidFromPackageFamilyName < 0)
      || (PackageSidFromPackageFamilyName = CheckAppSidsForCapability(v31, v37, L"smsSend", &v34),
          PackageSidFromPackageFamilyName < 0) )
    {
LABEL_22:
      tlx::_UndoSolo__lambda_80d93ac43b4c1627ed8091444198c02d___::__UndoSolo__lambda_80d93ac43b4c1627ed8091444198c02d___(&v40);
      goto LABEL_7;
    }
    v15 = (unsigned int)v30 | v20;
    tlx::_UndoSolo__lambda_80d93ac43b4c1627ed8091444198c02d___::__UndoSolo__lambda_80d93ac43b4c1627ed8091444198c02d___(&v40);
    v16 = v32;
    v18 = v34;
  }
  if ( v15 || v16 || (v21 = 0, v18) )
  {
    v36 = 0;
    v47 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.CapabilityAccess.CapabilityAccess",
      0x33u,
      0x32u);
    PackageSidFromPackageFamilyName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
                                        v47,
                                        (__int64)&v36);
    if ( PackageSidFromPackageFamilyName < 0 )
    {
LABEL_34:
      Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v36);
      goto LABEL_7;
    }
    v42[0] = 0;
    v40 = v42;
    v41 = (__int64 *)v42;
    PackageSidFromPackageFamilyName = GetCurrentUserSidString((__int64)&v40);
    if ( PackageSidFromPackageFamilyName < 0 )
    {
LABEL_36:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v40);
      goto LABEL_34;
    }
    v22 = v36;
    v35 = 0;
    v23 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, PVOID, __int64 *))(*(_QWORD *)v36 + 48LL);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v35);
    v44 = v5;
    Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v44)[1].Reserved.Reserved1;
    v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v48, (const WCHAR **)&c_szCapabilityChat);
    v44 = v40;
    v26 = v25[1].Reserved.Reserved1;
    v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v49, &v44);
    PackageSidFromPackageFamilyName = v23(v22, v27[1].Reserved.Reserved1, v26, Reserved1, &v35);
    if ( PackageSidFromPackageFamilyName < 0
      || (LOBYTE(v28) = 1,
          v34 = 0,
          PackageSidFromPackageFamilyName = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 88LL))(
                                              v35,
                                              v28),
          PackageSidFromPackageFamilyName < 0)
      || (PackageSidFromPackageFamilyName = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 152LL))(
                                              v35,
                                              &v34),
          PackageSidFromPackageFamilyName < 0) )
    {
      Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v35);
      goto LABEL_36;
    }
    if ( v34 != 3 )
    {
      Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v35);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v40);
      Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v36);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
      PackageSidFromPackageFamilyName = -2147024891;
      goto LABEL_43;
    }
    v21 = v15 != 0;
    if ( v32 )
      v21 |= 2u;
    if ( v18 )
      v21 |= 8u;
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v35);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v40);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v36);
    v3 = v45;
  }
  if ( v33 )
    v21 |= 4u;
  *v3 = v21;
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
  operator delete(v5);
  return 0;
}

```

## disassembly

```asm
0x180118d80  mov     [rsp-8+arg_10], rbx
0x180118d85  push    rbp
0x180118d86  push    rsi
0x180118d87  push    rdi
0x180118d88  push    r12
0x180118d8a  push    r13
0x180118d8c  push    r14
0x180118d8e  push    r15
0x180118d90  lea     rbp, [rsp-50h]
0x180118d95  sub     rsp, 150h
0x180118d9c  mov     rax, cs:__security_cookie
0x180118da3  xor     rax, rsp
0x180118da6  mov     [rbp+80h+var_40], rax
0x180118daa  mov     rsi, rcx
0x180118dad  mov     [rbp+80h+var_A8], rdx
0x180118db1  xor     r14d, r14d
0x180118db4  mov     [rbp+80h+packageFamilyNameLength], 41h ; 'A'
0x180118dbb  mov     ecx, 82h; unsigned __int64
0x180118dc0  mov     [rdx], r14d
0x180118dc3  mov     r15, rdx
0x180118dc6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180118dcb  mov     rbx, rax
0x180118dce  test    rax, rax
0x180118dd1  jnz     short loc_180118DDD
0x180118dd3  mov     eax, 8007000Eh
0x180118dd8  jmp     loc_180119331
0x180118ddd  mov     r8, rbx; packageFamilyName
0x180118de0  lea     rdx, [rbp+80h+packageFamilyNameLength]; packageFamilyNameLength
0x180118de4  mov     rcx, rsi; packageFullName
0x180118de7  call    cs:__imp_PackageFamilyNameFromFullName
0x180118ded  mov     edi, eax
0x180118def  test    eax, eax
0x180118df1  jz      short loc_180118E07
0x180118df3  jle     loc_1801192B0
0x180118df9  movzx   edi, ax
0x180118dfc  or      edi, 80070000h
0x180118e02  jmp     loc_1801192B0
0x180118e07  lea     rax, [rbp+80h+var_E8]
0x180118e0b  mov     [rbp+80h+var_E8], r14w
0x180118e10  mov     [rbp+80h+var_F8], rax
0x180118e14  lea     rdx, [rbp+80h+var_F8]
0x180118e18  lea     rax, [rbp+80h+var_E8]
0x180118e1c  mov     rcx, rbx
0x180118e1f  mov     [rbp+80h+var_F0], rax
0x180118e23  call    GetPackageSidFromPackageFamilyName
0x180118e28  mov     edi, eax
0x180118e2a  test    eax, eax
0x180118e2c  jns     short loc_180118E3C
0x180118e2e  lea     rcx, [rbp+80h+var_F8]; void *
0x180118e32  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180118e37  jmp     loc_1801192B0
0x180118e3c  mov     [rsp+180h+var_11C], r14d
0x180118e41  mov     [rsp+180h+var_118], r14d
0x180118e46  mov     [rsp+180h+var_114], r14d
0x180118e4b  call    IsCreateTokenFromChamberSidPresent
0x180118e50  test    al, al
0x180118e52  jz      loc_180118FB4
0x180118e58  lea     rcx, [rsp+180h+var_128]
0x180118e5d  mov     [rsp+180h+var_128], r14
0x180118e62  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x180118e67  mov     rcx, [rbp+80h+var_F8]
0x180118e6b  mov     r8, rax
0x180118e6e  mov     edx, 1
0x180118e73  call    cs:__imp_CreateTokenFromChamberSid
0x180118e79  mov     edi, eax
0x180118e7b  test    eax, eax
0x180118e7d  jns     short loc_180118E8B
0x180118e7f  lea     rcx, [rsp+180h+var_128]
0x180118e84  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180118e89  jmp     short loc_180118E2E
0x180118e8b  mov     rcx, [rsp+180h+var_128]
0x180118e90  lea     r8, [rsp+180h+var_130]
0x180118e95  lea     rdx, aIdCapSms; "ID_CAP_SMS"
0x180118e9c  mov     [rsp+180h+var_130], r14b
0x180118ea1  call    cs:__imp_CapabilityCheck
0x180118ea7  mov     edi, eax
0x180118ea9  test    eax, eax
0x180118eab  jns     short loc_180118EB3
0x180118ead  bts     edi, 1Ch
0x180118eb1  jmp     short loc_180118E7F
0x180118eb3  movzx   esi, [rsp+180h+var_130]
0x180118eb8  lea     r8, [rsp+180h+var_130]
0x180118ebd  mov     rcx, [rsp+180h+var_128]
0x180118ec2  lea     rdx, aChat; "chat"
0x180118ec9  mov     [rsp+180h+var_130], r14b
0x180118ece  call    cs:__imp_CapabilityCheck
0x180118ed4  mov     edi, eax
0x180118ed6  test    eax, eax
0x180118ed8  js      short loc_180118EAD
0x180118eda  movzx   r14d, [rsp+180h+var_130]
0x180118ee0  lea     r8, [rsp+180h+var_130]
0x180118ee5  mov     rcx, [rsp+180h+var_128]
0x180118eea  lea     rdx, aChatsystem; "chatSystem"
0x180118ef1  xor     r13d, r13d
0x180118ef4  mov     [rsp+180h+var_130], r13b
0x180118ef9  call    cs:__imp_CapabilityCheck
0x180118eff  mov     edi, eax
0x180118f01  test    eax, eax
0x180118f03  js      short loc_180118EAD
0x180118f05  movzx   r12d, [rsp+180h+var_130]
0x180118f0b  lea     r8, [rsp+180h+var_130]
0x180118f10  mov     rcx, [rsp+180h+var_128]
0x180118f15  lea     rdx, aIdCapSmsCompan; "ID_CAP_SMS_COMPANION"
0x180118f1c  mov     [rsp+180h+var_130], r13b
0x180118f21  or      esi, r14d
0x180118f24  call    cs:__imp_CapabilityCheck
0x180118f2a  mov     edi, eax
0x180118f2c  test    eax, eax
0x180118f2e  js      loc_180118EAD
0x180118f34  mov     rcx, [rsp+180h+var_128]
0x180118f39  lea     r8, [rsp+180h+var_130]
0x180118f3e  or      r12d, esi
0x180118f41  lea     rdx, aBlockedchatmes; "blockedChatMessages"
0x180118f48  movzx   esi, [rsp+180h+var_130]
0x180118f4d  mov     [rsp+180h+var_11C], esi
0x180118f51  mov     [rsp+180h+var_130], r13b
0x180118f56  call    cs:__imp_CapabilityCheck
0x180118f5c  mov     edi, eax
0x180118f5e  test    eax, eax
0x180118f60  js      loc_180118EAD
0x180118f66  movzx   r14d, [rsp+180h+var_130]
0x180118f6c  lea     r8, [rsp+180h+var_130]
0x180118f71  mov     rcx, [rsp+180h+var_128]
0x180118f76  lea     rdx, aSmssend; "smsSend"
0x180118f7d  mov     [rsp+180h+var_118], r14d
0x180118f82  xor     r14d, r14d
0x180118f85  mov     [rsp+180h+var_130], r14b
0x180118f8a  call    cs:__imp_CapabilityCheck
0x180118f90  lea     rcx, [rsp+180h+var_128]
0x180118f95  mov     edi, eax
0x180118f97  test    eax, eax
0x180118f99  jns     short loc_180118FA4
0x180118f9b  bts     edi, 1Ch
0x180118f9f  jmp     loc_180118E84
0x180118fa4  movzx   r13d, [rsp+180h+var_130]
0x180118faa  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180118faf  jmp     loc_180119127
0x180118fb4  call    IsQueryApplicationCapabilitiesPresent
0x180118fb9  test    al, al
0x180118fbb  jz      loc_18011931B
0x180118fc1  mov     [rsp+180h+var_140], r14
0x180118fc6  lea     rax, [rsp+180h+var_120]
0x180118fcb  mov     [rsp+180h+var_148], r14
0x180118fd0  lea     r8, [rsp+180h+var_120]
0x180118fd5  mov     [rbp+80h+var_D8], rax
0x180118fd9  lea     rdx, [rbp+80h+var_100]
0x180118fdd  lea     rax, [rbp+80h+var_100]
0x180118fe1  mov     [rsp+180h+var_150], r14
0x180118fe6  mov     [rsp+180h+var_158], r14
0x180118feb  xor     r9d, r9d
0x180118fee  mov     rcx, rsi
0x180118ff1  mov     [rbp+80h+var_D0], rax
0x180118ff5  mov     [rsp+180h+var_120], r14d
0x180118ffa  mov     [rbp+80h+var_100], r14
0x180118ffe  mov     byte ptr [rbp+80h+var_C8], 1
0x180119002  mov     [rsp+180h+var_160], r14
0x180119007  call    cs:__imp_QueryApplicationCapabilities
0x18011900d  mov     edi, eax
0x18011900f  test    eax, eax
0x180119011  jns     short loc_180119021
0x180119013  lea     rcx, [rbp+80h+var_D8]
0x180119017  call    tlx___UndoSolo__lambda_80d93ac43b4c1627ed8091444198c02d_______UndoSolo__lambda_80d93ac43b4c1627ed8091444198c02d___
0x18011901c  jmp     loc_180118E2E
0x180119021  mov     rdx, [rbp+80h+var_100]
0x180119025  lea     r9, [rsp+180h+var_128]
0x18011902a  mov     ecx, [rsp+180h+var_120]
0x18011902e  lea     r8, aIdCapSms; "ID_CAP_SMS"
0x180119035  mov     dword ptr [rsp+180h+var_128], r14d
0x18011903a  call    CheckAppSidsForCapability
0x18011903f  mov     edi, eax
0x180119041  test    eax, eax
0x180119043  js      short loc_180119013
0x180119045  mov     r12d, dword ptr [rsp+180h+var_128]
0x18011904a  lea     r9, [rsp+180h+var_128]
0x18011904f  mov     rdx, [rbp+80h+var_100]
0x180119053  lea     r8, aChat; "chat"
0x18011905a  mov     ecx, [rsp+180h+var_120]
0x18011905e  mov     dword ptr [rsp+180h+var_128], r14d
0x180119063  call    CheckAppSidsForCapability
0x180119068  mov     edi, eax
0x18011906a  test    eax, eax
0x18011906c  js      short loc_180119013
0x18011906e  or      r12d, dword ptr [rsp+180h+var_128]
0x180119073  lea     r9, [rsp+180h+var_128]
0x180119078  mov     rdx, [rbp+80h+var_100]
0x18011907c  lea     r8, aChatsystem; "chatSystem"
0x180119083  mov     ecx, [rsp+180h+var_120]
0x180119087  mov     dword ptr [rsp+180h+var_128], r14d
0x18011908c  call    CheckAppSidsForCapability
0x180119091  mov     edi, eax
0x180119093  test    eax, eax
0x180119095  js      loc_180119013
0x18011909b  mov     rdx, [rbp+80h+var_100]
0x18011909f  lea     r9, [rsp+180h+var_11C]
0x1801190a4  mov     ecx, [rsp+180h+var_120]
0x1801190a8  lea     r8, aIdCapSmsCompan; "ID_CAP_SMS_COMPANION"
0x1801190af  call    CheckAppSidsForCapability
0x1801190b4  mov     edi, eax
0x1801190b6  test    eax, eax
0x1801190b8  js      loc_180119013
0x1801190be  mov     rdx, [rbp+80h+var_100]
0x1801190c2  lea     r9, [rsp+180h+var_118]
0x1801190c7  mov     ecx, [rsp+180h+var_120]
0x1801190cb  lea     r8, aBlockedchatmes; "blockedChatMessages"
0x1801190d2  call    CheckAppSidsForCapability
0x1801190d7  mov     edi, eax
0x1801190d9  test    eax, eax
0x1801190db  js      loc_180119013
0x1801190e1  mov     rdx, [rbp+80h+var_100]
0x1801190e5  lea     r9, [rsp+180h+var_114]
0x1801190ea  mov     ecx, [rsp+180h+var_120]
0x1801190ee  lea     r8, aSmssend; "smsSend"
0x1801190f5  call    CheckAppSidsForCapability
0x1801190fa  lea     rcx, [rbp+80h+var_D8]
0x1801190fe  mov     edi, eax
0x180119100  test    eax, eax
0x180119102  js      loc_180119017
0x180119108  or      r12d, dword ptr [rsp+180h+var_128]
0x18011910d  call    tlx___UndoSolo__lambda_80d93ac43b4c1627ed8091444198c02d_______UndoSolo__lambda_80d93ac43b4c1627ed8091444198c02d___
0x180119112  mov     eax, [rsp+180h+var_118]
0x180119116  mov     esi, [rsp+180h+var_11C]
0x18011911a  mov     r13d, [rsp+180h+var_114]
0x18011911f  mov     [rsp+180h+var_118], eax
0x180119123  mov     [rsp+180h+var_11C], esi
0x180119127  test    r12d, r12d
0x18011912a  jnz     short loc_18011913C
0x18011912c  test    esi, esi
0x18011912e  jnz     short loc_18011913C
0x180119130  mov     edi, r14d
0x180119133  test    r13d, r13d
0x180119136  jz      loc_1801192F9
0x18011913c  mov     r9d, 32h ; '2'; unsigned int
0x180119142  mov     [rsp+180h+var_108], r14
0x180119147  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x18011914e  mov     [rbp+80h+var_88], r14
0x180119152  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x180119156  lea     r8d, [r9+1]; unsigned int
0x18011915a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18011915f  mov     rcx, [rbp+80h+var_88]
0x180119163  lea     rdx, [rsp+180h+var_108]
0x180119168  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x18011916d  mov     edi, eax
0x18011916f  test    eax, eax
0x180119171  jns     short loc_180119182
0x180119173  lea     rcx, [rsp+180h+var_108]
0x180119178  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18011917d  jmp     loc_180118E2E
0x180119182  lea     rax, [rbp+80h+var_C8]
0x180119186  mov     [rbp+80h+var_C8], r14w
0x18011918b  mov     [rbp+80h+var_D8], rax
0x18011918f  lea     rcx, [rbp+80h+var_D8]
0x180119193  lea     rax, [rbp+80h+var_C8]
0x180119197  mov     [rbp+80h+var_D0], rax
0x18011919b  call    GetCurrentUserSidString
0x1801191a0  mov     edi, eax
0x1801191a2  test    eax, eax
0x1801191a4  jns     short loc_1801191B1
0x1801191a6  lea     rcx, [rbp+80h+var_D8]; void *
0x1801191aa  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1801191af  jmp     short loc_180119173
0x1801191b1  mov     r15, [rsp+180h+var_108]
0x1801191b6  lea     rcx, [rsp+180h+var_110]
0x1801191bb  mov     [rsp+180h+var_110], r14
0x1801191c0  mov     rax, [r15]
0x1801191c3  mov     r14, [rax+30h]
0x1801191c7  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1801191cc  lea     rdx, [rbp+80h+var_B0]
0x1801191d0  mov     [rbp+80h+var_B0], rbx
0x1801191d4  lea     rcx, [rbp+80h+hstringHeader]
0x1801191d8  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1801191dd  lea     rdx, ?c_szCapabilityChat@@3QEBGEB; ushort const * const c_szCapabilityChat
0x1801191e4  lea     rcx, [rbp+80h+var_80]
0x1801191e8  mov     rsi, [rax+18h]
0x1801191ec  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801191f1  mov     rdx, [rbp+80h+var_D8]
0x1801191f5  lea     rcx, [rbp+80h+var_60]
0x1801191f9  mov     [rbp+80h+var_B0], rdx
0x1801191fd  lea     rdx, [rbp+80h+var_B0]
0x180119201  mov     rdi, [rax+18h]
0x180119205  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18011920a  lea     rcx, [rsp+180h+var_110]
0x18011920f  mov     r9, rsi
0x180119212  mov     [rsp+180h+var_160], rcx
0x180119217  mov     r8, rdi
0x18011921a  mov     rcx, r15
0x18011921d  mov     rdx, [rax+18h]
0x180119221  mov     rax, r14
0x180119224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119229  xor     r14d, r14d
0x18011922c  mov     edi, eax
0x18011922e  test    eax, eax
0x180119230  jns     short loc_180119241
0x180119232  lea     rcx, [rsp+180h+var_110]
0x180119237  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18011923c  jmp     loc_1801191A6
0x180119241  mov     rcx, [rsp+180h+var_110]
0x180119246  mov     dl, 1
0x180119248  mov     [rsp+180h+var_114], r14d
0x18011924d  mov     rax, [rcx]
0x180119250  mov     rax, [rax+58h]
  ... truncated ...
```
