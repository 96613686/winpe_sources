# cxl::SecurityDescriptor::SetObjectSecurity(wchar_t const *,_SE_OBJECT_TYPE,ulong,cxl::Sid *,cxl::Sid *,cxl::Acl *,cxl::Acl *)

- ea: `0x180016218`
- end: `0x1800162f8`
- name: `?SetObjectSecurity@SecurityDescriptor@cxl@@SAXPEB_WW4_SE_OBJECT_TYPE@@KPEAVSid@2@2PEAVAcl@2@3@Z`
- size: `224`
- prototype: `void __fastcall(const wchar_t *, enum _SE_OBJECT_TYPE, unsigned int, struct cxl::Sid *, struct cxl::Sid *, struct cxl::Acl *, struct cxl::Acl *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180060bc4`
- `0x180061f58`
- `0x1800629d4`
- `0x180062d98`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f0f4`
- `0x1800124ac`
- `0x180016218`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180016268`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180016268`

## string_xrefs

- `0x180016295`: `SetSecurityInfo failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::SecurityDescriptor::SetObjectSecurity(
        WCHAR *a1,
        enum _SE_OBJECT_TYPE a2,
        __int64 a3,
        struct cxl::Sid *a4,
        struct cxl::Sid *a5,
        struct cxl::Acl *a6)
{
  struct _ACL *pDacl; // rdx
  DWORD v7; // ebx
  _DWORD v8[2]; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v9[32]; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE v10[40]; // [rsp+68h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+90h] [rbp-88h] BYREF

  pDacl = 0;
  if ( a6 )
    pDacl = (struct _ACL *)*((_QWORD *)a6 + 2);
  v7 = SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
  if ( v7 )
  {
    std::wstring::wstring(v10);
    cxl::StringWriter::StringWriter(v9, v10);
    cxl::TextWriter::Write<23>(v9, "SetSecurityInfo failed");
    v8[0] = v7;
    v8[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v8, v10);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180016218  push    rbx
0x18001621a  sub     rsp, 110h
0x180016221  mov     rax, cs:__security_cookie
0x180016228  xor     rax, rsp
0x18001622b  mov     [rsp+118h+var_18], rax
0x180016233  mov     rax, [rsp+118h+arg_28]
0x18001623b  xor     edx, edx
0x18001623d  test    rax, rax
0x180016240  jz      short loc_180016246
0x180016242  mov     rdx, [rax+10h]
0x180016246  mov     [rsp+118h+pSacl], 0; pSacl
0x18001624f  mov     [rsp+118h+pDacl], rdx; pDacl
0x180016254  mov     [rsp+118h+psidGroup], 0; psidGroup
0x18001625d  xor     r9d, r9d; psidOwner
0x180016260  lea     edx, [r9+1]; ObjectType
0x180016264  lea     r8d, [r9+4]; SecurityInfo
0x180016268  call    cs:__imp_SetNamedSecurityInfoW
0x18001626f  nop     dword ptr [rax+rax+00h]
0x180016274  mov     ebx, eax
0x180016276  test    eax, eax
0x180016278  jz      short loc_1800162DE
0x18001627a  lea     rcx, [rsp+118h+var_B0]
0x18001627f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016284  nop
0x180016285  lea     rdx, [rsp+118h+var_B0]
0x18001628a  lea     rcx, [rsp+118h+var_D0]
0x18001628f  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180016294  nop
0x180016295  lea     rdx, aSetsecurityinf; "SetSecurityInfo failed"
0x18001629c  lea     rcx, [rsp+118h+var_D0]
0x1800162a1  call    ??$Write@$0BH@@TextWriter@cxl@@QEAAAEAV01@AEAY0BH@$$CBD@Z; cxl::TextWriter::Write<23>(char const (&)[23])
0x1800162a6  mov     [rsp+118h+var_D8], ebx
0x1800162aa  mov     [rsp+118h+var_D4], 0
0x1800162b2  lea     r8, [rsp+118h+var_B0]
0x1800162b7  lea     rdx, [rsp+118h+var_D8]
0x1800162bc  lea     rcx, [rsp+118h+pExceptionObject]
0x1800162c4  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800162c9  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800162d0  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800162d8  call    _CxxThrowException_0
0x1800162de  mov     rcx, [rsp+118h+var_18]
0x1800162e6  xor     rcx, rsp; StackCookie
0x1800162e9  call    __security_check_cookie
0x1800162ee  add     rsp, 110h
0x1800162f5  pop     rbx
0x1800162f6  retn
```
