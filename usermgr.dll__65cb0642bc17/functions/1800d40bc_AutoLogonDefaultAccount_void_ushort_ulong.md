# AutoLogonDefaultAccount(void * *,ushort *,ulong *)

- ea: `0x1800d40bc`
- end: `0x1800d437e`
- name: `?AutoLogonDefaultAccount@@YAKPEAPEAXPEAGPEAK@Z`
- size: `706`
- prototype: `unsigned int(void **, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d4384`

## callees

- `0x180035938`
- `0x1800d3f5c`
- `0x1800d40bc`
- `0x1800d449c`
- `0x1800d4e98`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d419a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d41ed`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d419a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d41ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d41a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d41a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d4332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d4332`
- `ntdll!RtlNtStatusToDosError` at `0x1800d4160`
- `ntdll!RtlNtStatusToDosError` at `0x1800d4160`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800d4259`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800d4259`
- `SspiCli!LogonUserExExW` at `0x1800d42d6`
- `SspiCli!LogonUserExExW` at `0x1800d42d6`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800d4154`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800d4154`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800d417a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800d417a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800d4350`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800d4350`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800d41d1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800d4227`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800d41d1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800d4227`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800d4341`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800d4341`

## pseudocode

```c
__int64 __fastcall AutoLogonDefaultAccount(void **a1, unsigned __int16 *a2, unsigned int *a3)
{
  int SeparateNameSpaceForToken; // eax
  DWORD LastError; // eax
  unsigned int v8; // ebx
  unsigned int i; // edi
  DWORD cchReferencedDomainName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v12; // [rsp+64h] [rbp-9Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+68h] [rbp-98h] BYREF
  int v14; // [rsp+6Ch] [rbp-94h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbSid; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+7Ch] [rbp-84h] BYREF
  PVOID DomainInfo; // [rsp+80h] [rbp-80h] BYREF
  PVOID PolicyHandle; // [rsp+88h] [rbp-78h] BYREF
  WELL_KNOWN_SID_TYPE v20[2]; // [rsp+90h] [rbp-70h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  _BYTE pSid[80]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE Sid[80]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR Name[264]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+380h] [rbp+280h] BYREF

  cchReferencedDomainName = 260;
  *a1 = 0;
  PolicyHandle = 0;
  cchName = 260;
  hObject = 0;
  cbSid = 68;
  v12 = 68;
  DomainInfo = 0;
  peUse = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v14 = 0;
  v20[0] = WinAuthenticatedUserSid;
  v20[1] = WinInteractiveSid;
  SeparateNameSpaceForToken = LsaLookupOpenLocalPolicy(&ObjectAttributes, 0x801u, &PolicyHandle);
  if ( SeparateNameSpaceForToken < 0 )
    goto LABEL_2;
  SeparateNameSpaceForToken = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
  if ( SeparateNameSpaceForToken < 0 )
    goto LABEL_2;
  if ( !CreateWellKnownSid(
          WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
          *((PSID *)DomainInfo + 2),
          pSid,
          &cbSid) )
    goto LABEL_6;
  if ( !LookupAccountSidLocalW(pSid, a2, a3, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    goto LABEL_6;
  v12 = 68;
  if ( !CreateWellKnownSid(WinBuiltinUsersSid, 0, Sid, &v12) )
    goto LABEL_6;
  cchReferencedDomainName = 260;
  if ( !LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    goto LABEL_6;
  v8 = EnableDefaultAccountIfNecessary(a2, Name, pSid);
  if ( v8 )
    goto LABEL_22;
  RtlGetDeviceFamilyInfoEnum(0, &v14, 0);
  if ( v14 == 10 )
  {
    for ( i = 0; i < 2; ++i )
    {
      v8 = AddKnownGroupIfNecessary(v20[i], Name);
      if ( v8 )
        goto LABEL_22;
    }
  }
  SeparateNameSpaceForToken = SetNtlmThreadOptions(0, 1u);
  if ( SeparateNameSpaceForToken < 0 )
    goto LABEL_2;
  if ( !(unsigned int)LogonUserExExW(a2, 0, 0, 2, 0, 0, &hObject, 0, 0, 0, 0) )
  {
LABEL_6:
    LastError = GetLastError();
    goto LABEL_3;
  }
  SetNtlmThreadOptions(1, 1u);
  if ( DefaultAccountNameSpaceSeparation )
  {
    if ( InteractiveUserNameSpaceSeparation )
    {
      SeparateNameSpaceForToken = CreateSeparateNameSpaceForToken(hObject, &OpaqueHandles);
      if ( SeparateNameSpaceForToken < 0 )
      {
LABEL_2:
        LastError = RtlNtStatusToDosError(SeparateNameSpaceForToken);
LABEL_3:
        v8 = LastError;
        goto LABEL_22;
      }
    }
  }
  *a1 = hObject;
  hObject = 0;
LABEL_22:
  if ( hObject )
    CloseHandle(hObject);
  if ( DomainInfo )
    LsaLookupFreeMemory(DomainInfo);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  return v8;
}

```

## disassembly

```asm
0x1800d40bc  mov     [rsp-8+arg_18], rbx
0x1800d40c1  push    rbp
0x1800d40c2  push    rsi
0x1800d40c3  push    rdi
0x1800d40c4  push    r14
0x1800d40c6  push    r15
0x1800d40c8  lea     rbp, [rsp-4A0h]
0x1800d40d0  sub     rsp, 5A0h
0x1800d40d7  mov     rax, cs:__security_cookie
0x1800d40de  xor     rax, rsp
0x1800d40e1  mov     [rbp+4C0h+var_30], rax
0x1800d40e8  xor     r15d, r15d
0x1800d40eb  mov     [rsp+5C0h+var_560], 104h
0x1800d40f3  xorps   xmm0, xmm0
0x1800d40f6  mov     [rcx], r15
0x1800d40f9  mov     rbx, r8
0x1800d40fc  mov     [rbp+4C0h+PolicyHandle], r15
0x1800d4100  mov     rsi, rdx
0x1800d4103  mov     [rsp+5C0h+cchName], 104h
0x1800d410b  lea     edi, [r15+44h]
0x1800d410f  mov     [rsp+5C0h+hObject], r15
0x1800d4114  mov     r14, rcx
0x1800d4117  mov     [rsp+5C0h+cbSid], edi
0x1800d411b  lea     r8, [rbp+4C0h+PolicyHandle]; PolicyHandle
0x1800d411f  mov     [rsp+5C0h+var_55C], edi
0x1800d4123  mov     edx, 801h; AccessMask
0x1800d4128  mov     [rbp+4C0h+DomainInfo], r15
0x1800d412c  lea     rcx, [rbp+4C0h+ObjectAttributes]; ObjectAttributes
0x1800d4130  mov     [rsp+5C0h+var_558], r15d
0x1800d4135  movups  xmmword ptr [rbp+4C0h+ObjectAttributes.Length], xmm0
0x1800d4139  mov     [rsp+5C0h+var_554], r15d
0x1800d413e  movups  xmmword ptr [rbp+4C0h+ObjectAttributes.ObjectName], xmm0
0x1800d4142  mov     [rbp+4C0h+var_530], 11h
0x1800d4149  movups  xmmword ptr [rbp+4C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d414d  mov     [rbp+4C0h+var_52C], 0Bh
0x1800d4154  call    cs:__imp_LsaLookupOpenLocalPolicy
0x1800d415a  test    eax, eax
0x1800d415c  jns     short loc_1800D416D
0x1800d415e  mov     ecx, eax; Status
0x1800d4160  call    cs:__imp_RtlNtStatusToDosError
0x1800d4166  mov     ebx, eax
0x1800d4168  jmp     loc_1800D4328
0x1800d416d  mov     rcx, [rbp+4C0h+PolicyHandle]; PolicyHandle
0x1800d4171  lea     r8, [rbp+4C0h+DomainInfo]; DomainInfo
0x1800d4175  mov     edx, 5; DomainInfoClass
0x1800d417a  call    cs:__imp_LsaLookupGetDomainInfo
0x1800d4180  test    eax, eax
0x1800d4182  js      short loc_1800D415E
0x1800d4184  mov     rdx, [rbp+4C0h+DomainInfo]
0x1800d4188  lea     r9, [rsp+5C0h+cbSid]; cbSid
0x1800d418d  lea     r8, [rbp+4C0h+pSid]; pSid
0x1800d4191  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x1800d4196  mov     rdx, [rdx+10h]; DomainSid
0x1800d419a  call    cs:__imp_CreateWellKnownSid
0x1800d41a0  test    eax, eax
0x1800d41a2  jnz     short loc_1800D41AC
0x1800d41a4  call    cs:__imp_GetLastError
0x1800d41aa  jmp     short loc_1800D4166
0x1800d41ac  lea     rax, [rsp+5C0h+var_558]
0x1800d41b1  mov     r8, rbx; cchName
0x1800d41b4  mov     [rsp+5C0h+peUse], rax; peUse
0x1800d41b9  lea     r9, [rbp+4C0h+ReferencedDomainName]; ReferencedDomainName
0x1800d41c0  lea     rax, [rsp+5C0h+var_560]
0x1800d41c5  mov     rdx, rsi; Name
0x1800d41c8  lea     rcx, [rbp+4C0h+pSid]; Sid
0x1800d41cc  mov     [rsp+5C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800d41d1  call    cs:__imp_LookupAccountSidLocalW
0x1800d41d7  test    eax, eax
0x1800d41d9  jz      short loc_1800D41A4
0x1800d41db  xor     edx, edx; DomainSid
0x1800d41dd  mov     [rsp+5C0h+var_55C], edi
0x1800d41e1  lea     r9, [rsp+5C0h+var_55C]; cbSid
0x1800d41e6  lea     r8, [rbp+4C0h+Sid]; pSid
0x1800d41ea  lea     ecx, [rdx+1Bh]; WellKnownSidType
0x1800d41ed  call    cs:__imp_CreateWellKnownSid
0x1800d41f3  test    eax, eax
0x1800d41f5  jz      short loc_1800D41A4
0x1800d41f7  lea     rax, [rsp+5C0h+var_558]
0x1800d41fc  mov     [rsp+5C0h+var_560], 104h
0x1800d4204  mov     [rsp+5C0h+peUse], rax; peUse
0x1800d4209  lea     r9, [rbp+4C0h+ReferencedDomainName]; ReferencedDomainName
0x1800d4210  lea     rax, [rsp+5C0h+var_560]
0x1800d4215  lea     r8, [rsp+5C0h+cchName]; cchName
0x1800d421a  mov     [rsp+5C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800d421f  lea     rdx, [rbp+4C0h+Name]; Name
0x1800d4223  lea     rcx, [rbp+4C0h+Sid]; Sid
0x1800d4227  call    cs:__imp_LookupAccountSidLocalW
0x1800d422d  test    eax, eax
0x1800d422f  jz      loc_1800D41A4
0x1800d4235  lea     r8, [rbp+4C0h+pSid]; void *
0x1800d4239  mov     rcx, rsi; username
0x1800d423c  lea     rdx, [rbp+4C0h+Name]; groupname
0x1800d4240  call    ?EnableDefaultAccountIfNecessary@@YAKPEAG0PEAX@Z; EnableDefaultAccountIfNecessary(ushort *,ushort *,void *)
0x1800d4245  mov     ebx, eax
0x1800d4247  test    eax, eax
0x1800d4249  jnz     loc_1800D4328
0x1800d424f  xor     r8d, r8d
0x1800d4252  lea     rdx, [rsp+5C0h+var_554]
0x1800d4257  xor     ecx, ecx
0x1800d4259  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800d425f  cmp     [rsp+5C0h+var_554], 0Ah
0x1800d4264  jnz     short loc_1800D428C
0x1800d4266  mov     edi, r15d
0x1800d4269  cmp     edi, 2
0x1800d426c  jnb     short loc_1800D428C
0x1800d426e  movsxd  rcx, edi
0x1800d4271  lea     rdx, [rbp+4C0h+Name]; unsigned __int16 *
0x1800d4275  mov     ecx, [rbp+rcx*4+4C0h+var_530]; enum WELL_KNOWN_SID_TYPE
0x1800d4279  call    ?AddKnownGroupIfNecessary@@YAKW4WELL_KNOWN_SID_TYPE@@PEAG@Z; AddKnownGroupIfNecessary(WELL_KNOWN_SID_TYPE,ushort *)
0x1800d427e  mov     ebx, eax
0x1800d4280  test    eax, eax
0x1800d4282  jnz     loc_1800D4328
0x1800d4288  inc     edi
0x1800d428a  jmp     short loc_1800D4269
0x1800d428c  mov     edx, 1; unsigned int
0x1800d4291  xor     ecx, ecx; int
0x1800d4293  call    ?SetNtlmThreadOptions@@YAJHK@Z; SetNtlmThreadOptions(int,ulong)
0x1800d4298  test    eax, eax
0x1800d429a  js      loc_1800D415E
0x1800d42a0  mov     [rsp+5C0h+var_570], r15
0x1800d42a5  lea     rax, [rsp+5C0h+hObject]
0x1800d42aa  mov     [rsp+5C0h+var_578], r15
0x1800d42af  mov     r9d, 2
0x1800d42b5  mov     [rsp+5C0h+var_580], r15
0x1800d42ba  xor     r8d, r8d
0x1800d42bd  mov     [rsp+5C0h+var_588], r15
0x1800d42c2  xor     edx, edx
0x1800d42c4  mov     [rsp+5C0h+var_590], rax
0x1800d42c9  mov     rcx, rsi
0x1800d42cc  mov     [rsp+5C0h+peUse], r15
0x1800d42d1  mov     dword ptr [rsp+5C0h+cchReferencedDomainName], r15d
0x1800d42d6  call    cs:__imp_LogonUserExExW
0x1800d42dc  test    eax, eax
0x1800d42de  jz      loc_1800D41A4
0x1800d42e4  mov     edx, 1; unsigned int
0x1800d42e9  mov     ecx, edx; int
0x1800d42eb  call    ?SetNtlmThreadOptions@@YAJHK@Z; SetNtlmThreadOptions(int,ulong)
0x1800d42f0  cmp     cs:?DefaultAccountNameSpaceSeparation@@3KA, r15d; ulong DefaultAccountNameSpaceSeparation
0x1800d42f7  jz      short loc_1800D431B
0x1800d42f9  cmp     cs:?InteractiveUserNameSpaceSeparation@@3KA, r15d; ulong InteractiveUserNameSpaceSeparation
0x1800d4300  jz      short loc_1800D431B
0x1800d4302  mov     rcx, [rsp+5C0h+hObject]; TokenHandle
0x1800d4307  lea     rdx, ?OpaqueHandles@@3PA_KA; unsigned __int64 *
0x1800d430e  call    ?CreateSeparateNameSpaceForToken@@YAJPEAXPEA_K@Z; CreateSeparateNameSpaceForToken(void *,unsigned __int64 *)
0x1800d4313  test    eax, eax
0x1800d4315  js      loc_1800D415E
0x1800d431b  mov     rax, [rsp+5C0h+hObject]
0x1800d4320  mov     [r14], rax
0x1800d4323  mov     [rsp+5C0h+hObject], r15
0x1800d4328  mov     rcx, [rsp+5C0h+hObject]; hObject
0x1800d432d  test    rcx, rcx
0x1800d4330  jz      short loc_1800D4338
0x1800d4332  call    cs:__imp_CloseHandle
0x1800d4338  mov     rcx, [rbp+4C0h+DomainInfo]; Buffer
0x1800d433c  test    rcx, rcx
0x1800d433f  jz      short loc_1800D4347
0x1800d4341  call    cs:__imp_LsaLookupFreeMemory
0x1800d4347  mov     rcx, [rbp+4C0h+PolicyHandle]; ObjectHandle
0x1800d434b  test    rcx, rcx
0x1800d434e  jz      short loc_1800D4356
0x1800d4350  call    cs:__imp_LsaLookupClose
0x1800d4356  mov     eax, ebx
0x1800d4358  mov     rcx, [rbp+4C0h+var_30]
0x1800d435f  xor     rcx, rsp; StackCookie
0x1800d4362  call    __security_check_cookie
0x1800d4367  mov     rbx, [rsp+5C0h+arg_18]
0x1800d436f  add     rsp, 5A0h
0x1800d4376  pop     r15
0x1800d4378  pop     r14
0x1800d437a  pop     rdi
0x1800d437b  pop     rsi
0x1800d437c  pop     rbp
0x1800d437d  retn
```
