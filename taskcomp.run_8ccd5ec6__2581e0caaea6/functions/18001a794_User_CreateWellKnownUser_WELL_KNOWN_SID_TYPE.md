# User::CreateWellKnownUser(WELL_KNOWN_SID_TYPE)

- ea: `0x18001a794`
- end: `0x18001a8ed`
- name: `?CreateWellKnownUser@User@@CA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `345`
- prototype: `static struct User __high(enum WELL_KNOWN_SID_TYPE)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b124`
- `0x18001b46c`
- `0x18001b68c`

## callees

- `0x1800050d0`
- `0x180008c4c`
- `0x18000cf80`
- `0x180019f10`
- `0x18001a794`
- `0x18001bf80`
- `0x180030700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001a7e7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001a7e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a810`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  if ( !(unsigned int)User::LookupUserSid((struct _bstr_t *)&v6, (struct _bstr_t *)v8, &v5, pSid) )
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
    v11 = byte_180052608;
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
0x18001a794  mov     [rsp-8+arg_10], rbx
0x18001a799  push    rbp
0x18001a79a  lea     rbp, [rsp-57h]
0x18001a79f  sub     rsp, 0F0h
0x18001a7a6  mov     rax, cs:__security_cookie
0x18001a7ad  xor     rax, rsp
0x18001a7b0  mov     [rbp+57h+var_10], rax
0x18001a7b4  mov     eax, edx
0x18001a7b6  mov     rbx, rcx
0x18001a7b9  mov     [rbp+57h+var_B8], rcx
0x18001a7bd  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18001a7c4  mov     [rbp+57h+var_C0], 8
0x18001a7cb  mov     [rbp+57h+var_B8], 0
0x18001a7d3  mov     [rbp+57h+var_A8], 0
0x18001a7db  lea     r9, [rbp+57h+cbSid]; cbSid
0x18001a7df  lea     r8, [rbp+57h+pSid]; pSid
0x18001a7e3  xor     edx, edx; DomainSid
0x18001a7e5  mov     ecx, eax; WellKnownSidType
0x18001a7e7  call    cs:__imp_CreateWellKnownSid
0x18001a7ee  nop     dword ptr [rax+rax+00h]
0x18001a7f3  lea     r9, [rbp+57h+pSid]; void *
0x18001a7f7  lea     r8, [rbp+57h+var_C0]; enum _SID_NAME_USE *
0x18001a7fb  lea     rdx, [rbp+57h+var_A8]; struct _bstr_t *
0x18001a7ff  lea     rcx, [rbp+57h+var_B8]; struct _bstr_t *
0x18001a803  call    ?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z; User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)
0x18001a808  test    eax, eax
0x18001a80a  jnz     loc_18001A89B
0x18001a810  call    cs:__imp_GetLastError
0x18001a817  nop     dword ptr [rax+rax+00h]
0x18001a81c  mov     ebx, eax
0x18001a81e  lea     rax, WPP_GLOBAL_Control
0x18001a825  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a82c  cmp     rcx, rax
0x18001a82f  jz      short loc_18001A855
0x18001a831  test    byte ptr [rcx+1Ch], 80h
0x18001a835  jz      short loc_18001A855
0x18001a837  cmp     byte ptr [rcx+19h], 2
0x18001a83b  jb      short loc_18001A855
0x18001a83d  mov     edx, 0Bh
0x18001a842  mov     r9d, ebx
0x18001a845  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001a84c  mov     rcx, [rcx+10h]
0x18001a850  call    WPP_SF_d
0x18001a855  mov     [rbp+57h+var_90], 0
0x18001a859  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001a860  mov     [rbp+57h+pExceptionObject], rax
0x18001a864  lea     rax, byte_180052608
0x18001a86b  mov     [rbp+57h+var_88], rax
0x18001a86f  mov     [rbp+57h+var_80], 0
0x18001a877  mov     [rbp+57h+var_78], 0
0x18001a87f  mov     [rbp+57h+var_70], ebx
0x18001a882  mov     [rbp+57h+var_6C], 0FFFFFFFFFFFFFFFFh
0x18001a88a  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001a891  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001a895  call    _CxxThrowException_0
0x18001a89b  lea     rax, [rbp+57h+pSid]
0x18001a89f  mov     [rsp+0F0h+var_D0], rax
0x18001a8a4  mov     r9d, [rbp+57h+var_C0]
0x18001a8a8  lea     r8, [rbp+57h+var_B8]
0x18001a8ac  lea     rdx, [rbp+57h+var_A8]
0x18001a8b0  mov     rcx, rbx
0x18001a8b3  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18001a8b8  nop
0x18001a8b9  lea     rcx, [rbp+57h+var_A8]; this
0x18001a8bd  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a8c2  nop
0x18001a8c3  lea     rcx, [rbp+57h+var_B8]; this
0x18001a8c7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a8cc  mov     rax, rbx
0x18001a8cf  mov     rcx, [rbp+57h+var_10]
0x18001a8d3  xor     rcx, rsp; StackCookie
0x18001a8d6  call    __security_check_cookie
0x18001a8db  mov     rbx, [rsp+0F0h+arg_10]
0x18001a8e3  add     rsp, 0F0h
0x18001a8ea  pop     rbp
0x18001a8eb  retn
```
