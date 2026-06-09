# WfdInterfaceManagement::WfdInterfaceManager::SetSelectedWfdManagerAccessCheck(void *,void *)

- ea: `0x1800bf490`
- end: `0x1800bf65d`
- name: `?SetSelectedWfdManagerAccessCheck@WfdInterfaceManager@WfdInterfaceManagement@@IEBAXPEAX0@Z`
- size: `461`
- prototype: `void __fastcall(WfdInterfaceManagement::WfdInterfaceManager *__hidden this, HANDLE ClientToken, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d9c24`

## callees

- `0x1800bd620`
- `0x1800bee6c`
- `0x1800bf490`
- `0x180106340`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf53d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf5bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf53d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf5bd`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800bf5b3`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800bf5b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bf637`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bf637`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf533`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf533`

## string_xrefs

- `0x1800bf56f`: `WfdInterfaceManagement::WfdInterfaceManager::SetSelectedWfdManagerAccessCheck`
- `0x1800bf5ef`: `WfdInterfaceManagement::WfdInterfaceManager::SetSelectedWfdManagerAccessCheck`
- `0x1800bf61d`: `WfdInterfaceManagement::WfdInterfaceManager::SetSelectedWfdManagerAccessCheck`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WfdInterfaceManagement::WfdInterfaceManager::SetSelectedWfdManagerAccessCheck(
        WfdInterfaceManagement::WfdInterfaceManager *this,
        HANDLE ClientToken,
        void *a3)
{
  const WCHAR *v5; // rcx
  signed int LastError; // eax
  signed int v7; // eax
  WINBOOL AccessStatus; // [rsp+40h] [rbp-9h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+44h] [rbp-5h] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-1h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp+3h] BYREF
  void **v12; // [rsp+50h] [rbp+7h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+Fh] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp+17h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp+2Fh] BYREF

  GenericMapping = (_GENERIC_MAPPING)_mm_load_si128((const __m128i *)&_xmm);
  if ( a3 )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 16LL))(*((_QWORD *)this + 26)) )
      return;
    v5 = L"O:SYG:SYD:(A;;0x1;;;SY)(A;;0x1;;;BA)(A;;0x1;;;S-1-5-80-1495648203-2503502111-1597754693-3445174711-1316708627)";
  }
  else
  {
    v5 = L"O:SYG:SYD:(A;;0x1;;;SY)(A;;0x1;;;BA)";
  }
  v12 = &CAutoPtr<unsigned char,LocalFreeDeleter>::`vftable';
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  GrantedAccess = 0;
  AccessStatus = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v5, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WFDSvc::CWFDSvcException::Throw(
        LastError,
        "WfdInterfaceManagement::WfdInterfaceManager::SetSelectedWfdManagerAccessCheck",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfdinterfacemanager\\src\\wfdinterfacemanagerimpl.cpp",
        140,
        L"Function returned bad Win32 Error Code",
        this);
    }
  }
  if ( !AccessCheck(
          SecurityDescriptor,
          ClientToken,
          1u,
          &GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    v7 = GetLastError();
    if ( v7 )
    {
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      WFDSvc::CWFDSvcException::Throw(
        v7,
        "WfdInterfaceManagement::WfdInterfaceManager::SetSelectedWfdManagerAccessCheck",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfdinterfacemanager\\src\\wfdinterfacemanagerimpl.cpp",
        154,
        L"Function returned bad Win32 Error Code",
        this);
    }
  }
  if ( !AccessStatus )
    WFDSvc::CWFDSvcException::Throw(
      -2147024891,
      "WfdInterfaceManagement::WfdInterfaceManager::SetSelectedWfdManagerAccessCheck",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfdinterfacemanager\\src\\wfdinterfacemanagerimpl.cpp",
      0x19Fu,
      L"Caller does not have permission to set the selected WFDMgr");
  v12 = &CAutoPtr<unsigned char,LocalFreeDeleter>::`vftable';
  LocalFree(SecurityDescriptor);
}

```

## disassembly

```asm
0x1800bf490  mov     [rsp-8+arg_10], rbx
0x1800bf495  push    rbp
0x1800bf496  push    rdi
0x1800bf497  push    r14
0x1800bf499  lea     rbp, [rsp-47h]
0x1800bf49e  sub     rsp, 90h
0x1800bf4a5  mov     rax, cs:__security_cookie
0x1800bf4ac  xor     rax, rsp
0x1800bf4af  mov     [rbp+57h+var_18], rax
0x1800bf4b3  mov     rdi, rdx
0x1800bf4b6  mov     rbx, rcx
0x1800bf4b9  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x1800bf4c1  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x1800bf4c5  test    r8, r8
0x1800bf4c8  jnz     short loc_1800BF4D3
0x1800bf4ca  lea     rcx, aOSygSydA0x1SyA_0; "O:SYG:SYD:(A;;0x1;;;SY)(A;;0x1;;;BA)"
0x1800bf4d1  jmp     short loc_1800BF4F5
0x1800bf4d3  mov     rcx, [rcx+0D0h]
0x1800bf4da  mov     rax, [rcx]
0x1800bf4dd  mov     rax, [rax+10h]
0x1800bf4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf4e6  test    al, al
0x1800bf4e8  jz      loc_1800BF63D
0x1800bf4ee  lea     rcx, aOSygSydA0x1SyA; "O:SYG:SYD:(A;;0x1;;;SY)(A;;0x1;;;BA)(A;"...
0x1800bf4f5  lea     r14, ??_7?$CAutoPtr@EULocalFreeDeleter@@@@6B@; const CAutoPtr<uchar,LocalFreeDeleter>::`vftable'
0x1800bf4fc  mov     [rbp+57h+var_50], r14
0x1800bf500  mov     [rbp+57h+SecurityDescriptor], 0
0x1800bf508  mov     [rbp+57h+SecurityDescriptorSize], 0
0x1800bf50f  xorps   xmm0, xmm0
0x1800bf512  xor     eax, eax
0x1800bf514  movups  xmmword ptr [rbp+57h+var_40.PrivilegeCount], xmm0
0x1800bf518  mov     [rbp+57h+var_40.Privilege.Attributes], eax
0x1800bf51b  mov     [rbp+57h+var_54], 14h
0x1800bf522  mov     [rbp+57h+var_58], eax
0x1800bf525  mov     [rbp+57h+var_60], eax
0x1800bf528  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800bf52c  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800bf530  lea     edx, [rax+1]; StringSDRevision
0x1800bf533  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bf539  test    eax, eax
0x1800bf53b  jnz     short loc_1800BF57E
0x1800bf53d  call    cs:__imp_GetLastError
0x1800bf543  test    eax, eax
0x1800bf545  jz      short loc_1800BF57E
0x1800bf547  jle     short loc_1800BF551
0x1800bf549  movzx   eax, ax
0x1800bf54c  or      eax, 80070000h
0x1800bf551  mov     [rsp+0A0h+PrivilegeSetLength], rbx; void *
0x1800bf556  lea     rcx, aFunctionReturn_1; "Function returned bad Win32 Error Code"
0x1800bf55d  mov     [rsp+0A0h+PrivilegeSet], rcx; unsigned __int16 *
0x1800bf562  mov     r9d, 18Ch; char
0x1800bf568  lea     r8, aOnecoreuapNetW_54; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bf56f  lea     rdx, aWfdinterfacema_1; "WfdInterfaceManagement::WfdInterfaceMan"...
0x1800bf576  mov     ecx, eax; int
0x1800bf578  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800bf57e  lea     rax, [rbp+57h+var_60]
0x1800bf582  mov     [rsp+0A0h+AccessStatus], rax; AccessStatus
0x1800bf587  lea     rax, [rbp+57h+var_58]
0x1800bf58b  mov     [rsp+0A0h+GrantedAccess], rax; GrantedAccess
0x1800bf590  lea     rax, [rbp+57h+var_54]
0x1800bf594  mov     [rsp+0A0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800bf599  lea     rax, [rbp+57h+var_40]
0x1800bf59d  mov     [rsp+0A0h+PrivilegeSet], rax; PrivilegeSet
0x1800bf5a2  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800bf5a6  mov     r8d, 1; DesiredAccess
0x1800bf5ac  mov     rdx, rdi; ClientToken
0x1800bf5af  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800bf5b3  call    cs:__imp_AccessCheck
0x1800bf5b9  test    eax, eax
0x1800bf5bb  jnz     short loc_1800BF5FE
0x1800bf5bd  call    cs:__imp_GetLastError
0x1800bf5c3  test    eax, eax
0x1800bf5c5  jz      short loc_1800BF5FE
0x1800bf5c7  jle     short loc_1800BF5D1
0x1800bf5c9  movzx   eax, ax
0x1800bf5cc  or      eax, 80070000h
0x1800bf5d1  mov     [rsp+0A0h+PrivilegeSetLength], rbx; void *
0x1800bf5d6  lea     rcx, aFunctionReturn_1; "Function returned bad Win32 Error Code"
0x1800bf5dd  mov     [rsp+0A0h+PrivilegeSet], rcx; unsigned __int16 *
0x1800bf5e2  mov     r9d, 19Ah; char
0x1800bf5e8  lea     r8, aOnecoreuapNetW_54; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bf5ef  lea     rdx, aWfdinterfacema_1; "WfdInterfaceManagement::WfdInterfaceMan"...
0x1800bf5f6  mov     ecx, eax; int
0x1800bf5f8  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800bf5fe  cmp     [rbp+57h+var_60], 0
0x1800bf602  jnz     short loc_1800BF62F
0x1800bf604  lea     rax, aCallerDoesNotH; "Caller does not have permission to set "...
0x1800bf60b  mov     [rsp+0A0h+PrivilegeSet], rax; unsigned __int16 *
0x1800bf610  mov     r9d, 19Fh; unsigned int
0x1800bf616  lea     r8, aOnecoreuapNetW_54; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bf61d  lea     rdx, aWfdinterfacema_1; "WfdInterfaceManagement::WfdInterfaceMan"...
0x1800bf624  mov     ecx, 80070005h; int
0x1800bf629  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800bf62f  mov     [rbp+57h+var_50], r14
0x1800bf633  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800bf637  call    cs:__imp_LocalFree
0x1800bf63d  mov     rcx, [rbp+57h+var_18]
0x1800bf641  xor     rcx, rsp; StackCookie
0x1800bf644  call    __security_check_cookie
0x1800bf649  mov     rbx, [rsp+0A0h+arg_10]
0x1800bf651  add     rsp, 90h
0x1800bf658  pop     r14
0x1800bf65a  pop     rdi
0x1800bf65b  pop     rbp
0x1800bf65c  retn
```
