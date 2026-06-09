# CPicturePasswordEnrollmentHandler::ClearEnrollment(void)

- ea: `0x180006480`
- end: `0x18000653b`
- name: `?ClearEnrollment@CPicturePasswordEnrollmentHandler@@UEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(CPicturePasswordEnrollmentHandler *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005a10`
- `0x180005a2c`
- `0x180006480`
- `0x180006d54`
- `0x1800092b8`
- `0x180018dac`
- `0x1800197cc`
- `0x1800198d4`
- `0x180019968`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800064b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800064b8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006510`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006510`

## pseudocode

```c
__int64 __fastcall CPicturePasswordEnrollmentHandler::ClearEnrollment(CPicturePasswordEnrollmentHandler *this)
{
  int CallerSID; // edi
  unsigned __int16 *v2; // rbx
  const unsigned __int16 *v3; // r8
  _QWORD v5[6]; // [rsp+20h] [rbp-30h] BYREF
  PSID Sid; // [rsp+78h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int16 *v8; // [rsp+88h] [rbp+38h] BYREF

  Sid = 0;
  CallerSID = CImpersonateCaller::GetCallerSID(&Sid);
  if ( CallerSID >= 0 )
  {
    v2 = 0;
    v8 = 0;
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) || (int)ResultFromKnownLastError() >= 0 )
    {
      CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(
        (CConvenienceLogonEnrollmentData *)v5,
        StringSid,
        v3);
      v5[0] = &CPicturePasswordUserData::`vftable';
      CPicturePasswordUserData::GetImagePath((CPicturePasswordUserData *)v5, &v8);
      CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData((CConvenienceLogonEnrollmentData *)v5);
      v2 = v8;
    }
    CallerSID = CPicturePasswordVault::ClearEnrollment(Sid);
    if ( v2 )
      DeleteFileW(v2);
    CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&StringSid);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v8);
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&Sid);
  return (unsigned int)CallerSID;
}

```

## disassembly

```asm
0x180006480  push    rbp
0x180006482  push    rbx
0x180006483  push    rdi
0x180006484  mov     rbp, rsp
0x180006487  sub     rsp, 50h
0x18000648b  lea     rcx, [rbp+Sid]; void **
0x18000648f  mov     [rbp+Sid], 0
0x180006497  call    ?GetCallerSID@CImpersonateCaller@@SAJPEAPEAX@Z; CImpersonateCaller::GetCallerSID(void * *)
0x18000649c  mov     edi, eax
0x18000649e  test    eax, eax
0x1800064a0  js      loc_180006528
0x1800064a6  mov     rcx, [rbp+Sid]; Sid
0x1800064aa  lea     rdx, [rbp+StringSid]; StringSid
0x1800064ae  xor     ebx, ebx
0x1800064b0  mov     [rbp+arg_18], rbx
0x1800064b4  mov     [rbp+StringSid], rbx
0x1800064b8  call    cs:__imp_ConvertSidToStringSidW
0x1800064be  test    eax, eax
0x1800064c0  jnz     short loc_1800064CB
0x1800064c2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800064c7  test    eax, eax
0x1800064c9  js      short loc_1800064FD
0x1800064cb  mov     rdx, [rbp+StringSid]; unsigned __int16 *
0x1800064cf  lea     rcx, [rbp+var_30]; this
0x1800064d3  call    ??0CConvenienceLogonEnrollmentData@@QEAA@PEBG0@Z; CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(ushort const *,ushort const *)
0x1800064d8  lea     rax, ??_7CPicturePasswordUserData@@6B@; const CPicturePasswordUserData::`vftable'
0x1800064df  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x1800064e3  mov     [rbp+var_30], rax
0x1800064e7  lea     rcx, [rbp+var_30]; this
0x1800064eb  call    ?GetImagePath@CPicturePasswordUserData@@QEBAJPEAPEAG@Z; CPicturePasswordUserData::GetImagePath(ushort * *)
0x1800064f0  lea     rcx, [rbp+var_30]; this
0x1800064f4  call    ??1CConvenienceLogonEnrollmentData@@UEAA@XZ; CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData(void)
0x1800064f9  mov     rbx, [rbp+arg_18]
0x1800064fd  mov     rcx, [rbp+Sid]; pSid
0x180006501  call    ?ClearEnrollment@CPicturePasswordVault@@SAJPEAX@Z; CPicturePasswordVault::ClearEnrollment(void *)
0x180006506  mov     edi, eax
0x180006508  test    rbx, rbx
0x18000650b  jz      short loc_180006516
0x18000650d  mov     rcx, rbx; lpFileName
0x180006510  call    cs:__imp_DeleteFileW
0x180006516  lea     rcx, [rbp+StringSid]
0x18000651a  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18000651f  lea     rcx, [rbp+arg_18]
0x180006523  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180006528  lea     rcx, [rbp+Sid]
0x18000652c  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180006531  mov     eax, edi
0x180006533  add     rsp, 50h
0x180006537  pop     rdi
0x180006538  pop     rbx
0x180006539  pop     rbp
0x18000653a  retn
```
