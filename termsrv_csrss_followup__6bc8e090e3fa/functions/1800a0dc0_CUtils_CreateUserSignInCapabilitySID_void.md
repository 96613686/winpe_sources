# CUtils::CreateUserSignInCapabilitySID(void * *)

- ea: `0x1800a0dc0`
- end: `0x1800a0f85`
- name: `?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z`
- size: `453`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005f8a0`
- `0x1800bfa4c`

## callees

- `0x180009940`
- `0x180034494`
- `0x1800a0dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ea6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f6d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a0e96`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a0e96`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a0e72`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a0e72`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x1800a0e37`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x1800a0e37`

## string_xrefs

- `0x1800a0ebb`: `CopySid failed: 0x%x in %s`
- `0x1800a0df2`: `CUtils::CreateUserSignInCapabilitySID`
- `0x1800a0ed3`: `CUtils::CreateUserSignInCapabilitySID`
- `0x1800a0df9`: `ppUserSignInCapabilitySid`
- `0x1800a0ec9`: `Too many sids??? failed: 0x%x in %s`
- `0x1800a0e5c`: `CreateUserSignInCapabilitySID - DeriveCapabilitySidsFromName failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::CreateUserSignInCapabilitySID(void **a1)
{
  unsigned int v2; // edi
  signed int v3; // eax
  size_t LengthSid; // rbx
  void *v5; // rax
  PSID *v6; // r8
  signed int LastError; // eax
  HLOCAL *v8; // rcx
  __int64 i; // rsi
  HLOCAL *v10; // rcx
  __int64 j; // rsi
  unsigned int v13; // [rsp+60h] [rbp+28h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+30h] BYREF
  HLOCAL v15; // [rsp+70h] [rbp+38h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+40h] BYREF

  hMem = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  if ( a1 )
  {
    v2 = 0;
    if ( (unsigned int)DeriveCapabilitySidsFromName(L"UserSignInSupport", &hMem, &v13, &v15, &v14)
      || (v3 = GetLastError(), v2 = v3, v3 >= 0) )
    {
      if ( v14 == 1 )
      {
        LengthSid = GetLengthSid(*(PSID *)v15);
        v5 = operator new(LengthSid);
        v6 = (PSID *)v15;
        *a1 = v5;
        if ( !CopySid(LengthSid, v5, *v6) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError < 0 )
            _DbgPrintMessage(
              8,
              "CopySid failed: 0x%x in %s",
              (unsigned int)LastError,
              "CUtils::CreateUserSignInCapabilitySID");
        }
      }
      else
      {
        v2 = -2147467259;
        _DbgPrintMessage(
          8,
          "Too many sids??? failed: 0x%x in %s",
          2147500037LL,
          "CUtils::CreateUserSignInCapabilitySID");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CreateUserSignInCapabilitySID - DeriveCapabilitySidsFromName failed: 0x%x in %s",
        (unsigned int)v3,
        "CUtils::CreateUserSignInCapabilitySID");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "Missing paramter %s in %s",
      "ppUserSignInCapabilitySid",
      "CUtils::CreateUserSignInCapabilitySID");
    v2 = -2147024809;
  }
  v8 = (HLOCAL *)hMem;
  if ( hMem )
  {
    for ( i = 0; (unsigned int)i < v13; v8 = (HLOCAL *)hMem )
    {
      LocalFree(v8[i]);
      *((_QWORD *)hMem + i) = 0;
      i = (unsigned int)(i + 1);
    }
    LocalFree(v8);
    hMem = 0;
    v13 = 0;
  }
  v10 = (HLOCAL *)v15;
  if ( v15 )
  {
    for ( j = 0; (unsigned int)j < v14; v10 = (HLOCAL *)v15 )
    {
      LocalFree(v10[j]);
      *((_QWORD *)v15 + j) = 0;
      j = (unsigned int)(j + 1);
    }
    LocalFree(v10);
  }
  return v2;
}

```

## disassembly

```asm
0x1800a0dc0  push    rbp
0x1800a0dc2  push    rbx
0x1800a0dc3  push    rsi
0x1800a0dc4  push    rdi
0x1800a0dc5  mov     rbp, rsp
0x1800a0dc8  sub     rsp, 38h
0x1800a0dcc  mov     [rbp+hMem], 0
0x1800a0dd4  mov     rsi, rcx
0x1800a0dd7  mov     [rbp+arg_0], 0
0x1800a0dde  mov     [rbp+arg_10], 0
0x1800a0de6  mov     [rbp+arg_8], 0
0x1800a0ded  test    rcx, rcx
0x1800a0df0  jnz     short loc_1800A0E19
0x1800a0df2  lea     r9, aCutilsCreateus; "CUtils::CreateUserSignInCapabilitySID"
0x1800a0df9  lea     r8, aPpusersigninca; "ppUserSignInCapabilitySid"
0x1800a0e00  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x1800a0e07  lea     ecx, [rsi+8]; int
0x1800a0e0a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a0e0f  mov     edi, 80070057h
0x1800a0e14  jmp     loc_1800A0EE4
0x1800a0e19  lea     rax, [rbp+arg_8]
0x1800a0e1d  xor     edi, edi
0x1800a0e1f  lea     r9, [rbp+arg_10]
0x1800a0e23  mov     [rsp+38h+var_18], rax
0x1800a0e28  lea     r8, [rbp+arg_0]
0x1800a0e2c  lea     rdx, [rbp+hMem]
0x1800a0e30  lea     rcx, aUsersigninsupp; "UserSignInSupport"
0x1800a0e37  call    cs:__imp_DeriveCapabilitySidsFromName
0x1800a0e3e  nop     dword ptr [rax+rax+00h]
0x1800a0e43  test    eax, eax
0x1800a0e45  jnz     short loc_1800A0E65
0x1800a0e47  call    cs:__imp_GetLastError
0x1800a0e4e  nop     dword ptr [rax+rax+00h]
0x1800a0e53  mov     edi, eax
0x1800a0e55  test    eax, eax
0x1800a0e57  jns     short loc_1800A0E65
0x1800a0e59  mov     r8d, eax
0x1800a0e5c  lea     rdx, aCreateusersign; "CreateUserSignInCapabilitySID - DeriveC"...
0x1800a0e63  jmp     short loc_1800A0ED3
0x1800a0e65  cmp     [rbp+arg_8], 1
0x1800a0e69  jnz     short loc_1800A0EC4
0x1800a0e6b  mov     rcx, [rbp+arg_10]
0x1800a0e6f  mov     rcx, [rcx]; pSid
0x1800a0e72  call    cs:__imp_GetLengthSid
0x1800a0e79  nop     dword ptr [rax+rax+00h]
0x1800a0e7e  mov     ecx, eax; Size
0x1800a0e80  mov     ebx, eax
0x1800a0e82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a0e87  mov     r8, [rbp+arg_10]
0x1800a0e8b  mov     rdx, rax; pDestinationSid
0x1800a0e8e  mov     [rsi], rax
0x1800a0e91  mov     ecx, ebx; nDestinationSidLength
0x1800a0e93  mov     r8, [r8]; pSourceSid
0x1800a0e96  call    cs:__imp_CopySid
0x1800a0e9d  nop     dword ptr [rax+rax+00h]
0x1800a0ea2  test    eax, eax
0x1800a0ea4  jnz     short loc_1800A0EE4
0x1800a0ea6  call    cs:__imp_GetLastError
0x1800a0ead  nop     dword ptr [rax+rax+00h]
0x1800a0eb2  mov     edi, eax
0x1800a0eb4  test    eax, eax
0x1800a0eb6  jns     short loc_1800A0EE4
0x1800a0eb8  mov     r8d, eax
0x1800a0ebb  lea     rdx, aCopysidFailed0; "CopySid failed: 0x%x in %s"
0x1800a0ec2  jmp     short loc_1800A0ED3
0x1800a0ec4  mov     edi, 80004005h
0x1800a0ec9  lea     rdx, aTooManySidsFai; "Too many sids??? failed: 0x%x in %s"
0x1800a0ed0  mov     r8d, edi
0x1800a0ed3  lea     r9, aCutilsCreateus; "CUtils::CreateUserSignInCapabilitySID"
0x1800a0eda  mov     ecx, 8; int
0x1800a0edf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a0ee4  mov     rcx, [rbp+hMem]
0x1800a0ee8  test    rcx, rcx
0x1800a0eeb  jz      short loc_1800A0F36
0x1800a0eed  xor     esi, esi
0x1800a0eef  cmp     [rbp+arg_0], esi
0x1800a0ef2  jbe     short loc_1800A0F1B
0x1800a0ef4  mov     rcx, [rcx+rsi*8]; hMem
0x1800a0ef8  call    cs:__imp_LocalFree
0x1800a0eff  nop     dword ptr [rax+rax+00h]
0x1800a0f04  mov     rax, [rbp+hMem]
0x1800a0f08  mov     qword ptr [rax+rsi*8], 0
0x1800a0f10  inc     esi
0x1800a0f12  mov     rcx, [rbp+hMem]; hMem
0x1800a0f16  cmp     esi, [rbp+arg_0]
0x1800a0f19  jb      short loc_1800A0EF4
0x1800a0f1b  call    cs:__imp_LocalFree
0x1800a0f22  nop     dword ptr [rax+rax+00h]
0x1800a0f27  mov     [rbp+hMem], 0
0x1800a0f2f  mov     [rbp+arg_0], 0
0x1800a0f36  mov     rcx, [rbp+arg_10]
0x1800a0f3a  test    rcx, rcx
0x1800a0f3d  jz      short loc_1800A0F79
0x1800a0f3f  xor     esi, esi
0x1800a0f41  cmp     [rbp+arg_8], esi
0x1800a0f44  jbe     short loc_1800A0F6D
0x1800a0f46  mov     rcx, [rcx+rsi*8]; hMem
0x1800a0f4a  call    cs:__imp_LocalFree
0x1800a0f51  nop     dword ptr [rax+rax+00h]
0x1800a0f56  mov     rax, [rbp+arg_10]
0x1800a0f5a  mov     qword ptr [rax+rsi*8], 0
0x1800a0f62  inc     esi
0x1800a0f64  mov     rcx, [rbp+arg_10]; hMem
0x1800a0f68  cmp     esi, [rbp+arg_8]
0x1800a0f6b  jb      short loc_1800A0F46
0x1800a0f6d  call    cs:__imp_LocalFree
0x1800a0f74  nop     dword ptr [rax+rax+00h]
0x1800a0f79  mov     eax, edi
0x1800a0f7b  add     rsp, 38h
0x1800a0f7f  pop     rdi
0x1800a0f80  pop     rsi
0x1800a0f81  pop     rbx
0x1800a0f82  pop     rbp
0x1800a0f83  retn
```
