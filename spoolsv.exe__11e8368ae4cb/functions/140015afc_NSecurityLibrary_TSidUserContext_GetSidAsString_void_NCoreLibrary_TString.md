# NSecurityLibrary::TSidUserContext::GetSidAsString(void *,NCoreLibrary::TString &)

- ea: `0x140015afc`
- end: `0x140015c09`
- name: `?GetSidAsString@TSidUserContext@NSecurityLibrary@@SAJPEAXAEAVTString@NCoreLibrary@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct NCoreLibrary::TString *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006a910`

## callees

- `0x14001128c`
- `0x140014e14`
- `0x140015afc`
- `0x14002a870`
- `0x14002bbd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015b34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015be7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015be7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140015b2a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140015b91`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140015b2a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140015b91`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140015bbe`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140015bbe`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::TSidUserContext::GetSidAsString(
        HANDLE TokenHandle,
        struct NCoreLibrary::TString *this)
{
  PSID *v2; // rdi
  signed int LastError; // eax
  signed int LastErrorAsFailHRNoBreak; // ebx
  NCoreLibrary *v7; // rcx
  NCoreLibrary *v8; // rcx
  LPWSTR StringSid; // [rsp+30h] [rbp-28h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  ReturnLength = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastErrorAsFailHRNoBreak = -2147467259;
  }
  else
  {
    LastError = GetLastError();
    LastErrorAsFailHRNoBreak = LastError;
    if ( LastError == 122 )
    {
      v2 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)NCoreLibrary::nothrow);
      LastErrorAsFailHRNoBreak = v2 == 0 ? 0x8007000E : 0;
    }
    else if ( LastError > 0 )
    {
      LastErrorAsFailHRNoBreak = (unsigned __int16)LastError | 0x80070000;
    }
    if ( LastErrorAsFailHRNoBreak >= 0
      && !GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &ReturnLength) )
    {
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v7);
    }
  }
  StringSid = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    if ( ConvertSidToStringSidW(*v2, &StringSid)
      || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v8), LastErrorAsFailHRNoBreak >= 0) )
    {
      LastErrorAsFailHRNoBreak = NCoreLibrary::TString::Update(this, StringSid);
    }
  }
  LocalFree(StringSid);
  operator delete(v2, 0x10u);
  return (unsigned int)LastErrorAsFailHRNoBreak;
}

```

## disassembly

```asm
0x140015afc  mov     rax, rsp
0x140015aff  mov     [rax+8], rbx
0x140015b03  push    rbp
0x140015b04  push    rsi
0x140015b05  push    rdi
0x140015b06  sub     rsp, 40h
0x140015b0a  xor     edi, edi
0x140015b0c  mov     rbp, rdx
0x140015b0f  mov     [rax+20h], edi
0x140015b12  xor     r9d, r9d; TokenInformationLength
0x140015b15  mov     [rax+18h], edi
0x140015b18  lea     rax, [rax+18h]
0x140015b1c  xor     r8d, r8d; TokenInformation
0x140015b1f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140015b24  lea     edx, [rdi+1]; TokenInformationClass
0x140015b27  mov     rsi, rcx
0x140015b2a  call    cs:__imp_GetTokenInformation
0x140015b30  test    eax, eax
0x140015b32  jnz     short loc_140015BA4
0x140015b34  call    cs:__imp_GetLastError
0x140015b3a  mov     ebx, eax
0x140015b3c  cmp     eax, 7Ah ; 'z'
0x140015b3f  jnz     short loc_140015B66
0x140015b41  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x140015b45  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x140015b4c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140015b51  mov     rcx, rax
0x140015b54  mov     rdi, rax
0x140015b57  neg     rcx
0x140015b5a  sbb     ebx, ebx
0x140015b5c  not     ebx
0x140015b5e  and     ebx, 8007000Eh
0x140015b64  jmp     short loc_140015B73
0x140015b66  test    eax, eax
0x140015b68  jle     short loc_140015B73
0x140015b6a  movzx   ebx, ax
0x140015b6d  or      ebx, 80070000h
0x140015b73  test    ebx, ebx
0x140015b75  js      short loc_140015BA9
0x140015b77  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x140015b7c  lea     rax, [rsp+58h+arg_18]
0x140015b81  mov     r8, rdi; TokenInformation
0x140015b84  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140015b89  mov     edx, 1; TokenInformationClass
0x140015b8e  mov     rcx, rsi; TokenHandle
0x140015b91  call    cs:__imp_GetTokenInformation
0x140015b97  test    eax, eax
0x140015b99  jnz     short loc_140015BA9
0x140015b9b  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140015ba0  mov     ebx, eax
0x140015ba2  jmp     short loc_140015BA9
0x140015ba4  mov     ebx, 80004005h
0x140015ba9  mov     [rsp+58h+StringSid], 0
0x140015bb2  test    ebx, ebx
0x140015bb4  js      short loc_140015BE2
0x140015bb6  mov     rcx, [rdi]; Sid
0x140015bb9  lea     rdx, [rsp+58h+StringSid]; StringSid
0x140015bbe  call    cs:__imp_ConvertSidToStringSidW
0x140015bc4  test    eax, eax
0x140015bc6  jnz     short loc_140015BD3
0x140015bc8  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140015bcd  mov     ebx, eax
0x140015bcf  test    eax, eax
0x140015bd1  js      short loc_140015BE2
0x140015bd3  mov     rdx, [rsp+58h+StringSid]; unsigned __int16 *
0x140015bd8  mov     rcx, rbp; this
0x140015bdb  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x140015be0  mov     ebx, eax
0x140015be2  mov     rcx, [rsp+58h+StringSid]; hMem
0x140015be7  call    cs:__imp_LocalFree
0x140015bed  mov     edx, 10h; unsigned __int64
0x140015bf2  mov     rcx, rdi; void *
0x140015bf5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140015bfa  mov     eax, ebx
0x140015bfc  mov     rbx, [rsp+58h+arg_0]
0x140015c01  add     rsp, 40h
0x140015c05  pop     rdi
0x140015c06  pop     rsi
0x140015c07  pop     rbp
0x140015c08  retn
```
