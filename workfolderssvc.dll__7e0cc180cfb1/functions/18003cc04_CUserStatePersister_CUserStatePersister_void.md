# CUserStatePersister::CUserStatePersister(void)

- ea: `0x18003cc04`
- end: `0x18003cf3d`
- name: `??0CUserStatePersister@@QEAA@XZ`
- size: `825`
- prototype: `CUserStatePersister *__fastcall(CUserStatePersister *__hidden this)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180024e18`
- `0x1800251b0`
- `0x1800360ac`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180006fa0`
- `0x180007b9c`
- `0x180007e10`
- `0x1800083b4`
- `0x180009384`
- `0x180009424`
- `0x180010ee0`
- `0x1800110fc`
- `0x180011314`
- `0x180029094`
- `0x18003cc04`
- `0x180060bc4`
- `0x180060fc8`
- `0x1800b1a5c`
- `0x1800b1a88`
- `0x1800b1e44`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003ce3c`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003cdfb`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003cdfb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003cc36`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003cc36`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
CUserStatePersister *__fastcall CUserStatePersister::CUserStatePersister(CUserStatePersister *this)
{
  _BYTE *v2; // rax
  char v3; // cl
  HKEY *v4; // rax
  HKEY *v5; // rax
  __int64 v6; // rdx
  char v7; // r8
  __int64 v8; // rax
  int v9; // eax
  HKEY *v10; // rax
  HKEY *v11; // rax
  __int64 pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+4Ch] [rbp-B4h]
  char v16; // [rsp+50h] [rbp-B0h]
  const char *v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+60h] [rbp-A0h]
  ULONG SecurityDescriptorSize; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h] BYREF
  HKEY v22; // [rsp+80h] [rbp-80h] BYREF
  HKEY v23; // [rsp+88h] [rbp-78h] BYREF
  HKEY v24; // [rsp+90h] [rbp-70h] BYREF
  struct _SECURITY_ATTRIBUTES v25; // [rsp+98h] [rbp-68h] BYREF
  CUserStatePersister *v26; // [rsp+B0h] [rbp-50h]
  _BYTE v27[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v28[40]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR StringSecurityDescriptor; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v30[1022]; // [rsp+F2h] [rbp-Eh] BYREF

  v26 = this;
  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_1a37b1bd89e233d7b5afa2994537b710_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( (v2[68] & 8) == 0 || (v3 = 1, v2[65] < 6u) )
    v3 = 0;
  LastFailureAsHRESULT = 0;
  v15 = 9;
  v16 = v3;
  v17 = "CUserStatePersister::CUserStatePersister";
  v18 = 0;
  v4 = CEcsRegKey::CurrentUserKeyForService((HKEY *)&pExceptionObject);
  CEcsRegKey::Get(
    &v22,
    v4,
    L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\WorkFolders\\UserState",
    983103,
    0,
    0,
    0,
    0);
  CEcsRegKey::Close((CEcsRegKey *)&pExceptionObject);
  if ( !v22 )
  {
    v5 = CEcsRegKey::CurrentUserKeyForService((HKEY *)&pExceptionObject);
    CEcsRegKey::Get(
      &v24,
      v5,
      L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion",
      983103,
      1,
      0,
      0,
      0);
    CEcsRegKey::Close((CEcsRegKey *)&pExceptionObject);
    pExceptionObject = CTokenHelper::GetCurrentToken(8u, v6, v7);
    v21 = 0;
    EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&v21, &pExceptionObject);
    CTokenHelper::StringSidFromToken(v28, v21);
    StringSecurityDescriptor = 0;
    memset_0(v30, 0, sizeof(v30));
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    v9 = StringCchPrintfW(
           &StringSecurityDescriptor,
           0x200u,
           L"O:%sG:SYD:P(D;CI;FA;;;S-1-15-2-1)(A;CI;GA;;;%s)(A;CI;GA;;;SY)(A;CI;GA;;;BA)",
           v8,
           v8);
    LastFailureAsHRESULT = v9;
    if ( v9 < 0 )
    {
      HIWORD(v15) = 40;
      LODWORD(pExceptionObject) = v9;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v15) = 40;
    SecurityDescriptor = 0;
    SecurityDescriptorSize = 0;
    LastFailureAsHRESULT = v9;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            &StringSecurityDescriptor,
            1u,
            &SecurityDescriptor,
            &SecurityDescriptorSize) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v15) = 47;
      LODWORD(pExceptionObject) = LastFailureAsHRESULT;
      throw (long *)&pExceptionObject;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v15) = 47;
    pExceptionObject = (__int64)LocalFree;
    std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(
      v27,
      SecurityDescriptor,
      &pExceptionObject);
    *(_QWORD *)&v25.nLength = 24;
    v25.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&v25.bInheritHandle = 0;
    v10 = CEcsRegKey::CurrentUserKeyForService(&v23);
    v11 = CEcsRegKey::Get(
            (HKEY *)&pExceptionObject,
            v10,
            L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\WorkFolders\\UserState",
            983103,
            1,
            &v25,
            0,
            0);
    CEcsRegKey::operator=(&v22, v11);
    CEcsRegKey::Close((CEcsRegKey *)&pExceptionObject);
    CEcsRegKey::Close((CEcsRegKey *)&v23);
    std::unique_ptr<_WTSINFOW,void (*)(void *)>::~unique_ptr<_WTSINFOW,void (*)(void *)>(v27);
    std::wstring::~wstring(v28);
    v23 = 0;
    EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&v21, &v23);
    CEcsRegKey::Close((CEcsRegKey *)&v24);
  }
  CEcsRegKey::Close((CEcsRegKey *)&v22);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return this;
}

```

## disassembly

```asm
0x18003cc04  mov     [rsp-8+arg_8], rbx
0x18003cc09  mov     [rsp-8+arg_10], rdi
0x18003cc0e  push    rbp
0x18003cc0f  lea     rbp, [rsp-400h]
0x18003cc17  sub     rsp, 500h
0x18003cc1e  mov     rax, cs:__security_cookie
0x18003cc25  xor     rax, rsp
0x18003cc28  mov     [rbp+400h+var_10], rax
0x18003cc2f  mov     rbx, rcx
0x18003cc32  mov     [rbp+400h+var_450], rcx
0x18003cc36  call    cs:__imp_InitializeCriticalSection
0x18003cc3c  nop
0x18003cc3d  lea     rcx, WPP_GLOBAL_Control
0x18003cc44  mov     rax, cs:WPP_GLOBAL_Control
0x18003cc4b  cmp     rax, rcx
0x18003cc4e  jz      short loc_18003CC78
0x18003cc50  test    byte ptr [rax+44h], 8
0x18003cc54  jz      short loc_18003CC78
0x18003cc56  cmp     byte ptr [rax+41h], 6
0x18003cc5a  jb      short loc_18003CC78
0x18003cc5c  mov     edx, 0Ah
0x18003cc61  lea     r8, WPP_1a37b1bd89e233d7b5afa2994537b710_Traceguids
0x18003cc68  mov     rcx, [rax+38h]
0x18003cc6c  call    WPP_SF_
0x18003cc71  mov     rax, cs:WPP_GLOBAL_Control
0x18003cc78  xor     edi, edi
0x18003cc7a  test    byte ptr [rax+44h], 8
0x18003cc7e  jz      short loc_18003CC88
0x18003cc80  cmp     byte ptr [rax+41h], 6
0x18003cc84  mov     cl, 1
0x18003cc86  jnb     short loc_18003CC8B
0x18003cc88  mov     cl, dil
0x18003cc8b  mov     [rsp+500h+var_4B8], edi
0x18003cc8f  mov     [rsp+500h+var_4B4], 9
0x18003cc97  mov     [rsp+500h+var_4B0], cl
0x18003cc9b  lea     rax, aCuserstatepers_7; "CUserStatePersister::CUserStatePersiste"...
0x18003cca2  mov     [rsp+500h+var_4A8], rax
0x18003cca7  mov     [rsp+500h+var_4A0], rdi
0x18003ccac  lea     rcx, [rsp+500h+pExceptionObject]
0x18003ccb1  call    ?CurrentUserKeyForService@CEcsRegKey@@SA?AV1@XZ; CEcsRegKey::CurrentUserKeyForService(void)
0x18003ccb6  nop
0x18003ccb7  mov     [rsp+500h+var_4C8], dil
0x18003ccbc  mov     [rsp+500h+var_4D0], rdi
0x18003ccc1  mov     [rsp+500h+var_4D8], rdi
0x18003ccc6  mov     byte ptr [rsp+500h+var_4E0], dil
0x18003cccb  mov     r9d, 0F003Fh
0x18003ccd1  lea     r8, aSoftwareClasse_1; "Software\\Classes\\Local Settings\\Soft"...
0x18003ccd8  mov     rdx, rax
0x18003ccdb  lea     rcx, [rbp+400h+var_480]
0x18003ccdf  call    ?Get@CEcsRegKey@@SA?AV1@AEBV1@PEBGK_NPEAU_SECURITY_ATTRIBUTES@@PEA_N2@Z; CEcsRegKey::Get(CEcsRegKey const &,ushort const *,ulong,bool,_SECURITY_ATTRIBUTES *,bool *,bool)
0x18003cce4  nop
0x18003cce5  lea     rcx, [rsp+500h+pExceptionObject]; this
0x18003ccea  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18003ccef  cmp     [rbp+400h+var_480], rdi
0x18003ccf3  jnz     loc_18003CF01
0x18003ccf9  lea     rcx, [rsp+500h+pExceptionObject]
0x18003ccfe  call    ?CurrentUserKeyForService@CEcsRegKey@@SA?AV1@XZ; CEcsRegKey::CurrentUserKeyForService(void)
0x18003cd03  nop
0x18003cd04  mov     [rsp+500h+var_4C8], dil
0x18003cd09  mov     [rsp+500h+var_4D0], rdi
0x18003cd0e  mov     [rsp+500h+var_4D8], rdi
0x18003cd13  mov     byte ptr [rsp+500h+var_4E0], 1
0x18003cd18  mov     r9d, 0F003Fh
0x18003cd1e  lea     r8, aSoftwareClasse; "Software\\Classes\\Local Settings\\Soft"...
0x18003cd25  mov     rdx, rax
0x18003cd28  lea     rcx, [rbp+400h+var_470]
0x18003cd2c  call    ?Get@CEcsRegKey@@SA?AV1@AEBV1@PEBGK_NPEAU_SECURITY_ATTRIBUTES@@PEA_N2@Z; CEcsRegKey::Get(CEcsRegKey const &,ushort const *,ulong,bool,_SECURITY_ATTRIBUTES *,bool *,bool)
0x18003cd31  nop
0x18003cd32  lea     rcx, [rsp+500h+pExceptionObject]; this
0x18003cd37  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18003cd3c  mov     ecx, 8; DesiredAccess
0x18003cd41  call    ?GetCurrentToken@CTokenHelper@@SAPEAXK_N0@Z; CTokenHelper::GetCurrentToken(ulong,bool,bool)
0x18003cd46  mov     [rsp+500h+pExceptionObject], rax
0x18003cd4b  mov     [rsp+500h+var_488], rdi
0x18003cd50  lea     rdx, [rsp+500h+pExceptionObject]
0x18003cd55  lea     rcx, [rsp+500h+var_488]
0x18003cd5a  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x18003cd5f  nop
0x18003cd60  mov     rdx, [rsp+500h+var_488]
0x18003cd65  lea     rcx, [rbp+400h+var_438]
0x18003cd69  call    ?StringSidFromToken@CTokenHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; CTokenHelper::StringSidFromToken(void *)
0x18003cd6e  nop
0x18003cd6f  mov     [rbp+400h+StringSecurityDescriptor], di
0x18003cd73  xor     edx, edx; Val
0x18003cd75  mov     r8d, 3FEh; Size
0x18003cd7b  lea     rcx, [rbp+400h+var_40E]; void *
0x18003cd7f  call    memset_0
0x18003cd84  lea     rcx, [rbp+400h+var_438]
0x18003cd88  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003cd8d  mov     [rsp+500h+var_4E0], rax
0x18003cd92  mov     r9, rax
0x18003cd95  lea     r8, aOSgSydPDCiFaS1; "O:%sG:SYD:P(D;CI;FA;;;S-1-15-2-1)(A;CI;"...
0x18003cd9c  mov     edx, 200h; unsigned __int64
0x18003cda1  lea     rcx, [rbp+400h+StringSecurityDescriptor]; unsigned __int16 *
0x18003cda5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003cdaa  mov     [rsp+500h+var_4B8], eax
0x18003cdae  mov     [rsp+500h+var_4B8], eax
0x18003cdb2  mov     ecx, 28h ; '('
0x18003cdb7  test    eax, eax
0x18003cdb9  jns     short loc_18003CDD6
0x18003cdbb  mov     word ptr [rsp+500h+var_4B4+2], cx
0x18003cdc0  mov     dword ptr [rsp+500h+pExceptionObject], eax
0x18003cdc4  lea     rdx, _TI1J; pThrowInfo
0x18003cdcb  lea     rcx, [rsp+500h+pExceptionObject]; pExceptionObject
0x18003cdd0  call    _CxxThrowException_0
0x18003cdd6  mov     word ptr [rsp+500h+var_4B4], cx
0x18003cddb  mov     [rsp+500h+SecurityDescriptor], rdi
0x18003cde0  mov     [rsp+500h+SecurityDescriptorSize], edi
0x18003cde4  mov     [rsp+500h+var_4B8], eax
0x18003cde8  lea     r9, [rsp+500h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18003cded  lea     r8, [rsp+500h+SecurityDescriptor]; SecurityDescriptor
0x18003cdf2  mov     edx, 1; StringSDRevision
0x18003cdf7  lea     rcx, [rbp+400h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18003cdfb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003ce01  test    eax, eax
0x18003ce03  jnz     short loc_18003CE2E
0x18003ce05  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18003ce0a  mov     [rsp+500h+var_4B8], eax
0x18003ce0e  mov     ecx, 2Fh ; '/'
0x18003ce13  mov     word ptr [rsp+500h+var_4B4+2], cx
0x18003ce18  mov     dword ptr [rsp+500h+pExceptionObject], eax
0x18003ce1c  lea     rdx, _TI1J; pThrowInfo
0x18003ce23  lea     rcx, [rsp+500h+pExceptionObject]; pExceptionObject
0x18003ce28  call    _CxxThrowException_0
0x18003ce2e  mov     [rsp+500h+var_4B8], edi
0x18003ce32  mov     ecx, 2Fh ; '/'
0x18003ce37  mov     word ptr [rsp+500h+var_4B4], cx
0x18003ce3c  mov     rax, cs:__imp_LocalFree
0x18003ce43  mov     [rsp+500h+pExceptionObject], rax
0x18003ce48  lea     r8, [rsp+500h+pExceptionObject]
0x18003ce4d  mov     rdx, [rsp+500h+SecurityDescriptor]
0x18003ce52  lea     rcx, [rbp+400h+var_448]
0x18003ce56  call    ??$?0P6AXPEAX@Z$0A@@?$unique_ptr@U_WTSINFOW@@P6AXPEAX@Z@std@@QEAA@PEAU_WTSINFOW@@$$QEAP6AXPEAX@Z@Z; std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(_WTSINFOW *,void (*&&)(void *))
0x18003ce5b  nop
0x18003ce5c  mov     [rbp+400h+var_468], 18h
0x18003ce64  mov     rax, [rsp+500h+SecurityDescriptor]
0x18003ce69  mov     [rbp+400h+var_460], rax
0x18003ce6d  mov     [rbp+400h+var_458], rdi
0x18003ce71  lea     rcx, [rbp+400h+var_478]
0x18003ce75  call    ?CurrentUserKeyForService@CEcsRegKey@@SA?AV1@XZ; CEcsRegKey::CurrentUserKeyForService(void)
0x18003ce7a  nop
0x18003ce7b  mov     [rsp+500h+var_4C8], dil
0x18003ce80  mov     [rsp+500h+var_4D0], rdi
0x18003ce85  lea     rcx, [rbp+400h+var_468]
0x18003ce89  mov     [rsp+500h+var_4D8], rcx
0x18003ce8e  mov     byte ptr [rsp+500h+var_4E0], 1
0x18003ce93  mov     r9d, 0F003Fh
0x18003ce99  lea     r8, aSoftwareClasse_1; "Software\\Classes\\Local Settings\\Soft"...
0x18003cea0  mov     rdx, rax
0x18003cea3  lea     rcx, [rsp+500h+pExceptionObject]
0x18003cea8  call    ?Get@CEcsRegKey@@SA?AV1@AEBV1@PEBGK_NPEAU_SECURITY_ATTRIBUTES@@PEA_N2@Z; CEcsRegKey::Get(CEcsRegKey const &,ushort const *,ulong,bool,_SECURITY_ATTRIBUTES *,bool *,bool)
0x18003cead  nop
0x18003ceae  mov     rdx, rax
0x18003ceb1  lea     rcx, [rbp+400h+var_480]
0x18003ceb5  call    ??4CEcsRegKey@@QEAAAEAV0@$$QEAV0@@Z; CEcsRegKey::operator=(CEcsRegKey &&)
0x18003ceba  nop
0x18003cebb  lea     rcx, [rsp+500h+pExceptionObject]; this
0x18003cec0  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18003cec5  nop
0x18003cec6  lea     rcx, [rbp+400h+var_478]; this
0x18003ceca  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18003cecf  nop
0x18003ced0  lea     rcx, [rbp+400h+var_448]
0x18003ced4  call    ??1?$unique_ptr@U_WTSINFOW@@P6AXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<_WTSINFOW,void (*)(void *)>::~unique_ptr<_WTSINFOW,void (*)(void *)>(void)
0x18003ced9  nop
0x18003ceda  lea     rcx, [rbp+400h+var_438]
0x18003cede  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cee3  nop
0x18003cee4  mov     [rbp+400h+var_478], rdi
0x18003cee8  lea     rdx, [rbp+400h+var_478]
0x18003ceec  lea     rcx, [rsp+500h+var_488]
0x18003cef1  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x18003cef6  nop
0x18003cef7  lea     rcx, [rbp+400h+var_470]; this
0x18003cefb  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18003cf00  nop
0x18003cf01  lea     rcx, [rbp+400h+var_480]; this
0x18003cf05  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18003cf0a  nop
0x18003cf0b  lea     rcx, [rsp+500h+var_4B8]; this
0x18003cf10  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18003cf15  nop
0x18003cf16  mov     rax, rbx
0x18003cf19  mov     rcx, [rbp+400h+var_10]
0x18003cf20  xor     rcx, rsp; StackCookie
0x18003cf23  call    __security_check_cookie
0x18003cf28  lea     r11, [rsp+500h+var_s0]
0x18003cf30  mov     rbx, [r11+18h]
0x18003cf34  mov     rdi, [r11+20h]
0x18003cf38  mov     rsp, r11
0x18003cf3b  pop     rbp
0x18003cf3c  retn
```
