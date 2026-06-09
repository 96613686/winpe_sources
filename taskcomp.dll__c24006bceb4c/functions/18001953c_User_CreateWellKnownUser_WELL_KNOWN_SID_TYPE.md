# User::CreateWellKnownUser(WELL_KNOWN_SID_TYPE)

- ea: `0x18001953c`
- end: `0x180019688`
- name: `?CreateWellKnownUser@User@@CA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `332`
- prototype: `__int64 __fastcall(__int64, WELL_KNOWN_SID_TYPE)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019e44`
- `0x18001a154`
- `0x18001a334`

## callees

- `0x180004e50`
- `0x18000878c`
- `0x18000c760`
- `0x180018d00`
- `0x18001953c`
- `0x18001abac`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001958f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001958f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195b2`

## pseudocode

```c
__int64 __fastcall User::CreateWellKnownUser(__int64 a1, WELL_KNOWN_SID_TYPE a2)
{
  DWORD LastError; // ebx
  enum _SID_NAME_USE v5; // [rsp+30h] [rbp-69h] BYREF
  __int64 v6; // [rsp+38h] [rbp-61h] BYREF
  DWORD cbSid; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v8[2]; // [rsp+48h] [rbp-51h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-41h] BYREF
  char v10; // [rsp+60h] [rbp-39h]
  char *v11; // [rsp+68h] [rbp-31h]
  __int64 v12; // [rsp+70h] [rbp-29h]
  __int64 v13; // [rsp+78h] [rbp-21h]
  DWORD v14; // [rsp+80h] [rbp-19h]
  __int64 v15; // [rsp+84h] [rbp-15h]
  _BYTE pSid[80]; // [rsp+90h] [rbp-9h] BYREF

  cbSid = 68;
  v5 = SidTypeUnknown;
  v6 = 0;
  v8[0] = 0;
  CreateWellKnownSid(a2, 0, pSid, &cbSid);
  if ( !User::LookupUserSid((struct _bstr_t *)&v6, (struct _bstr_t *)v8, &v5, pSid) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids, LastError);
    }
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = byte_1800505F8;
    v12 = 0;
    v13 = 0;
    v14 = LastError;
    v15 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  User::CreateUser(a1, (const struct _bstr_t *)v8, (const struct _bstr_t *)&v6, v5, pSid);
  _bstr_t::~_bstr_t((_bstr_t *)v8);
  _bstr_t::~_bstr_t((_bstr_t *)&v6);
  return a1;
}

```

## disassembly

```asm
0x18001953c  mov     [rsp-8+arg_10], rbx
0x180019541  push    rbp
0x180019542  lea     rbp, [rsp-57h]
0x180019547  sub     rsp, 0F0h
0x18001954e  mov     rax, cs:__security_cookie
0x180019555  xor     rax, rsp
0x180019558  mov     [rbp+57h+var_10], rax
0x18001955c  mov     eax, edx
0x18001955e  mov     rbx, rcx
0x180019561  mov     [rbp+57h+var_B8], rcx
0x180019565  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18001956c  mov     [rbp+57h+var_C0], 8
0x180019573  mov     [rbp+57h+var_B8], 0
0x18001957b  mov     [rbp+57h+var_A8], 0
0x180019583  lea     r9, [rbp+57h+cbSid]; cbSid
0x180019587  lea     r8, [rbp+57h+pSid]; pSid
0x18001958b  xor     edx, edx; DomainSid
0x18001958d  mov     ecx, eax; WellKnownSidType
0x18001958f  call    cs:__imp_CreateWellKnownSid
0x180019595  lea     r9, [rbp+57h+pSid]; void *
0x180019599  lea     r8, [rbp+57h+var_C0]; enum _SID_NAME_USE *
0x18001959d  lea     rdx, [rbp+57h+var_A8]; struct _bstr_t *
0x1800195a1  lea     rcx, [rbp+57h+var_B8]; struct _bstr_t *
0x1800195a5  call    ?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z; User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)
0x1800195aa  test    eax, eax
0x1800195ac  jnz     loc_180019637
0x1800195b2  call    cs:__imp_GetLastError
0x1800195b8  mov     ebx, eax
0x1800195ba  lea     rax, WPP_GLOBAL_Control
0x1800195c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195c8  cmp     rcx, rax
0x1800195cb  jz      short loc_1800195F1
0x1800195cd  test    byte ptr [rcx+1Ch], 80h
0x1800195d1  jz      short loc_1800195F1
0x1800195d3  cmp     byte ptr [rcx+19h], 2
0x1800195d7  jb      short loc_1800195F1
0x1800195d9  mov     edx, 0Bh
0x1800195de  mov     r9d, ebx
0x1800195e1  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x1800195e8  mov     rcx, [rcx+10h]
0x1800195ec  call    WPP_SF_d
0x1800195f1  mov     [rbp+57h+var_90], 0
0x1800195f5  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800195fc  mov     [rbp+57h+pExceptionObject], rax
0x180019600  lea     rax, byte_1800505F8
0x180019607  mov     [rbp+57h+var_88], rax
0x18001960b  mov     [rbp+57h+var_80], 0
0x180019613  mov     [rbp+57h+var_78], 0
0x18001961b  mov     [rbp+57h+var_70], ebx
0x18001961e  mov     [rbp+57h+var_6C], 0FFFFFFFFFFFFFFFFh
0x180019626  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001962d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019631  call    _CxxThrowException_0
0x180019637  lea     rax, [rbp+57h+pSid]
0x18001963b  mov     [rsp+0F0h+var_D0], rax
0x180019640  mov     r9d, [rbp+57h+var_C0]
0x180019644  lea     r8, [rbp+57h+var_B8]
0x180019648  lea     rdx, [rbp+57h+var_A8]
0x18001964c  mov     rcx, rbx
0x18001964f  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x180019654  nop
0x180019655  lea     rcx, [rbp+57h+var_A8]; this
0x180019659  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001965e  nop
0x18001965f  lea     rcx, [rbp+57h+var_B8]; this
0x180019663  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019668  mov     rax, rbx
0x18001966b  mov     rcx, [rbp+57h+var_10]
0x18001966f  xor     rcx, rsp; StackCookie
0x180019672  call    __security_check_cookie
0x180019677  mov     rbx, [rsp+0F0h+arg_10]
0x18001967f  add     rsp, 0F0h
0x180019686  pop     rbp
0x180019687  retn
```
