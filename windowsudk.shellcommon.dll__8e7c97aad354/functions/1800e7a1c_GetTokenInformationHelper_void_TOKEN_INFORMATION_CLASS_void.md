# GetTokenInformationHelper(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x1800e7a1c`
- end: `0x1800e7b52`
- name: `?GetTokenInformationHelper@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e7960`

## callees

- `0x1800a8430`
- `0x1800e2988`
- `0x1800e34bc`
- `0x1800e3660`
- `0x1800e7a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7a5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e7a4f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e7abd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e7a4f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e7abd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e7a72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e7a72`

## string_xrefs

- `0x1800e7a8a`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800e7acc`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800e7b0c`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800e7b27`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
__int64 __fastcall GetTokenInformationHelper(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS a2, void **a3)
{
  DWORD LastError; // eax
  void *v6; // rbx
  unsigned int v7; // ebx
  const char *v8; // r9
  unsigned int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T uBytes; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v13; // [rsp+58h] [rbp+20h] BYREF

  LODWORD(uBytes) = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&uBytes) )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
      (const char *)0x8000FFFFLL,
      ReturnLength);
    return v7;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x19,
               (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
               (const char *)LastError,
               ReturnLength);
    return 0;
  }
  v13 = LocalAlloc(0, (unsigned int)uBytes);
  v6 = v13;
  if ( v13 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, v13, uBytes, (PDWORD)&uBytes) )
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x13,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             v8);
      goto LABEL_7;
    }
    v13 = 0;
    *a3 = v6;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v13);
    return 0;
  }
  v7 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11,
    (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
    (const char *)0x8007000ELL,
    ReturnLength);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v13);
  return v7;
}

```

## disassembly

```asm
0x1800e7a1c  mov     rax, rsp
0x1800e7a1f  mov     [rax+8], rbx
0x1800e7a23  mov     [rax+18h], rsi
0x1800e7a27  mov     [rax+10h], edx
0x1800e7a2a  push    rdi
0x1800e7a2b  sub     rsp, 30h
0x1800e7a2f  xor     r9d, r9d; TokenInformationLength
0x1800e7a32  mov     dword ptr [rax+10h], 0
0x1800e7a39  mov     rdi, r8
0x1800e7a3c  lea     rax, [rax+10h]
0x1800e7a40  xor     r8d, r8d; TokenInformation
0x1800e7a43  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800e7a48  mov     rsi, rcx
0x1800e7a4b  lea     edx, [r9+1]; TokenInformationClass
0x1800e7a4f  call    cs:__imp_GetTokenInformation
0x1800e7a55  test    eax, eax
0x1800e7a57  jnz     loc_1800E7B22
0x1800e7a5d  call    cs:__imp_GetLastError
0x1800e7a63  cmp     eax, 7Ah ; 'z'
0x1800e7a66  jnz     loc_1800E7B03
0x1800e7a6c  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x1800e7a70  xor     ecx, ecx; uFlags
0x1800e7a72  call    cs:__imp_LocalAlloc
0x1800e7a78  mov     [rsp+38h+arg_18], rax
0x1800e7a7d  mov     rbx, rax
0x1800e7a80  test    rax, rax
0x1800e7a83  jnz     short loc_1800E7AA3
0x1800e7a85  mov     rcx, [rsp+38h]; this
0x1800e7a8a  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800e7a91  mov     ebx, 8007000Eh
0x1800e7a96  lea     edx, [rax+11h]; void *
0x1800e7a99  mov     r9d, ebx; char *
0x1800e7a9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7aa1  jmp     short loc_1800E7ADD
0x1800e7aa3  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x1800e7aa8  lea     rax, [rsp+38h+uBytes]
0x1800e7aad  mov     r8, rbx; TokenInformation
0x1800e7ab0  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800e7ab5  mov     edx, 1; TokenInformationClass
0x1800e7aba  mov     rcx, rsi; TokenHandle
0x1800e7abd  call    cs:__imp_GetTokenInformation
0x1800e7ac3  test    eax, eax
0x1800e7ac5  jnz     short loc_1800E7AE9
0x1800e7ac7  mov     rcx, [rsp+38h]; this
0x1800e7acc  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800e7ad3  lea     edx, [rax+13h]; void *
0x1800e7ad6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e7adb  mov     ebx, eax
0x1800e7add  lea     rcx, [rsp+38h+arg_18]
0x1800e7ae2  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1800e7ae7  jmp     short loc_1800E7B40
0x1800e7ae9  lea     rcx, [rsp+38h+arg_18]
0x1800e7aee  mov     [rsp+38h+arg_18], 0
0x1800e7af7  mov     [rdi], rbx
0x1800e7afa  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1800e7aff  xor     eax, eax
0x1800e7b01  jmp     short loc_1800E7B42
0x1800e7b03  test    eax, eax
0x1800e7b05  jz      short loc_1800E7AFF
0x1800e7b07  mov     rcx, [rsp+38h]; this
0x1800e7b0c  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800e7b13  mov     r9d, eax; char *
0x1800e7b16  mov     edx, 19h; void *
0x1800e7b1b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e7b20  jmp     short loc_1800E7B42
0x1800e7b22  mov     rcx, [rsp+38h]; this
0x1800e7b27  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800e7b2e  mov     ebx, 8000FFFFh
0x1800e7b33  mov     edx, 1Eh; void *
0x1800e7b38  mov     r9d, ebx; char *
0x1800e7b3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7b40  mov     eax, ebx
0x1800e7b42  mov     rbx, [rsp+38h+arg_0]
0x1800e7b47  mov     rsi, [rsp+38h+arg_10]
0x1800e7b4c  add     rsp, 30h
0x1800e7b50  pop     rdi
0x1800e7b51  retn
```
