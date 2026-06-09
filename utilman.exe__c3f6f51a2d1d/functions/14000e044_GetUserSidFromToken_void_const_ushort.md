# GetUserSidFromToken(void * const,ushort * *)

- ea: `0x14000e044`
- end: `0x14000e260`
- name: `?GetUserSidFromToken@@YAJQEAXPEAPEAG@Z`
- size: `540`
- prototype: `__int64 __fastcall(void *const, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000e3cc`

## callees

- `0x140002fa0`
- `0x14000813c`
- `0x14000815c`
- `0x14000b19c`
- `0x14000b1d0`
- `0x14000c3dc`
- `0x14000cfe4`
- `0x14000e044`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14000e08c`
- `ADVAPI32!GetTokenInformation` at `0x14000e16e`
- `ADVAPI32!GetTokenInformation` at `0x14000e08c`
- `ADVAPI32!GetTokenInformation` at `0x14000e16e`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000e1c8`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000e1c8`
- `KERNEL32!GetLastError` at `0x14000e09c`
- `KERNEL32!GetLastError` at `0x14000e09c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUserSidFromToken(void *const a1, unsigned __int16 **a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  char *v7; // rdi
  char *v8; // rax
  size_t v9; // rbx
  const char *v10; // r9
  unsigned int v11; // ebx
  unsigned int v12; // r8d
  const char *v13; // r9
  const char *v14; // r9
  unsigned int v15; // ebx
  unsigned __int16 *v16; // rax
  __int64 v17; // [rsp+0h] [rbp-58h] BYREF
  PDWORD ReturnLength; // [rsp+20h] [rbp-38h]
  LPVOID TokenInformation; // [rsp+30h] [rbp-28h] BYREF
  void *v20; // [rsp+38h] [rbp-20h]
  __int64 v21; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+10h] BYREF

  TokenInformationLength = a1;
  *a2 = 0;
  std::vector<unsigned char>::vector<unsigned char>(&TokenInformation);
  LODWORD(TokenInformationLength) = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, (PDWORD)&TokenInformationLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12,
          (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
          (const char *)v5,
          (int)ReturnLength);
      if ( TokenInformation )
        std::_Deallocate<16>(TokenInformation, v21 - (_QWORD)TokenInformation);
      return v5;
    }
  }
  try
  {
    v7 = (char *)v20;
    if ( (unsigned int)TokenInformationLength >= (unsigned __int64)((_BYTE *)v20 - (_BYTE *)TokenInformation) )
    {
      if ( (unsigned int)TokenInformationLength <= (unsigned __int64)((_BYTE *)v20 - (_BYTE *)TokenInformation) )
        goto LABEL_17;
      if ( (unsigned int)TokenInformationLength > (unsigned __int64)(v21 - (_QWORD)TokenInformation) )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
          &TokenInformation,
          (unsigned int)TokenInformationLength);
        goto LABEL_17;
      }
      v9 = (unsigned int)TokenInformationLength - ((_BYTE *)v20 - (_BYTE *)TokenInformation);
      memset_0(v20, 0, v9);
      v8 = &v7[v9];
    }
    else
    {
      v8 = (char *)TokenInformation + (unsigned int)TokenInformationLength;
    }
    v20 = v8;
LABEL_17:
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenUser,
           TokenInformation,
           (DWORD)TokenInformationLength,
           (PDWORD)&TokenInformationLength) )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(*(PSID *)TokenInformation, &StringSid) )
      {
        v16 = StringSid;
        StringSid = 0;
        *a2 = v16;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        if ( TokenInformation )
          std::_Deallocate<16>(TokenInformation, v21 - (_QWORD)TokenInformation);
        result = 0;
      }
      else
      {
        v15 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1A,
                (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
                v14);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        if ( TokenInformation )
          std::_Deallocate<16>(TokenInformation, v21 - (_QWORD)TokenInformation);
        result = v15;
      }
    }
    else
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x16,
              (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
              v10);
      if ( TokenInformation )
        std::_Deallocate<16>(TokenInformation, v21 - (_QWORD)TokenInformation);
      result = v11;
    }
  }
  catch ( ... )
  {
    LODWORD(TokenInformationLength) = wil::details::in1diag3::Return_CaughtException(retaddr, &v17, v12, v13);
    return (unsigned int)TokenInformationLength;
  }
  return result;
}

```

## disassembly

```asm
0x14000e044  mov     rax, rsp
0x14000e047  mov     [rax+18h], rbx
0x14000e04b  mov     [rax+20h], rsi
0x14000e04f  mov     [rax+8], rcx
0x14000e053  push    rdi
0x14000e054  sub     rsp, 50h
0x14000e058  mov     rsi, rdx
0x14000e05b  mov     qword ptr [rdx], 0
0x14000e062  lea     rcx, [rax-28h]
0x14000e066  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x14000e06b  nop
0x14000e06c  mov     dword ptr [rsp+58h+TokenInformationLength], 0
0x14000e074  lea     rax, [rsp+58h+TokenInformationLength]
0x14000e079  mov     [rsp+58h+ReturnLength], rax; int
0x14000e07e  xor     r9d, r9d; TokenInformationLength
0x14000e081  xor     r8d, r8d; TokenInformation
0x14000e084  lea     edx, [r9+1]; TokenInformationClass
0x14000e088  lea     rcx, [r9-6]; TokenHandle
0x14000e08c  call    cs:__imp_GetTokenInformation
0x14000e093  nop     dword ptr [rax+rax+00h]
0x14000e098  test    eax, eax
0x14000e09a  jnz     short loc_14000E0F8
0x14000e09c  call    cs:__imp_GetLastError
0x14000e0a3  nop     dword ptr [rax+rax+00h]
0x14000e0a8  mov     ebx, eax
0x14000e0aa  cmp     eax, 7Ah ; 'z'
0x14000e0ad  jz      short loc_14000E0F8
0x14000e0af  test    eax, eax
0x14000e0b1  jle     short loc_14000E0BC
0x14000e0b3  movzx   ebx, ax
0x14000e0b6  or      ebx, 80070000h
0x14000e0bc  test    ebx, ebx
0x14000e0be  jns     short loc_14000E0DA
0x14000e0c0  mov     rcx, [rsp+58h]; this
0x14000e0c5  mov     r9d, ebx; char *
0x14000e0c8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\private"...
0x14000e0cf  mov     edx, 12h; void *
0x14000e0d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e0d9  nop
0x14000e0da  mov     rcx, [rsp+58h+TokenInformation]
0x14000e0df  test    rcx, rcx
0x14000e0e2  jz      short loc_14000E0F1
0x14000e0e4  mov     rdx, [rsp+58h+var_18]
0x14000e0e9  sub     rdx, rcx
0x14000e0ec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000e0f1  mov     eax, ebx
0x14000e0f3  jmp     loc_14000E24F
0x14000e0f8  mov     ebx, dword ptr [rsp+58h+TokenInformationLength]
0x14000e0fc  mov     rdx, [rsp+58h+TokenInformation]
0x14000e101  mov     rdi, [rsp+58h+var_20]
0x14000e106  mov     rcx, rdi
0x14000e109  sub     rcx, rdx
0x14000e10c  cmp     rbx, rcx
0x14000e10f  jnb     short loc_14000E117
0x14000e111  lea     rax, [rbx+rdx]
0x14000e115  jmp     short loc_14000E149
0x14000e117  jbe     short loc_14000E14E
0x14000e119  mov     rax, [rsp+58h+var_18]
0x14000e11e  sub     rax, rdx
0x14000e121  cmp     rbx, rax
0x14000e124  jbe     short loc_14000E135
0x14000e126  mov     rdx, rbx
0x14000e129  lea     rcx, [rsp+58h+TokenInformation]
0x14000e12e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x14000e133  jmp     short loc_14000E14E
0x14000e135  sub     rbx, rcx
0x14000e138  mov     r8, rbx; Size
0x14000e13b  xor     edx, edx; Val
0x14000e13d  mov     rcx, rdi; void *
0x14000e140  call    memset_0
0x14000e145  lea     rax, [rbx+rdi]
0x14000e149  mov     [rsp+58h+var_20], rax
0x14000e14e  lea     rax, [rsp+58h+TokenInformationLength]
0x14000e153  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x14000e158  mov     r9d, dword ptr [rsp+58h+TokenInformationLength]; TokenInformationLength
0x14000e15d  mov     r8, [rsp+58h+TokenInformation]; TokenInformation
0x14000e162  mov     edx, 1; TokenInformationClass
0x14000e167  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x14000e16e  call    cs:__imp_GetTokenInformation
0x14000e175  nop     dword ptr [rax+rax+00h]
0x14000e17a  test    eax, eax
0x14000e17c  jnz     short loc_14000E1B2
0x14000e17e  mov     rcx, [rsp+58h]; this
0x14000e183  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\private"...
0x14000e18a  lea     edx, [rax+16h]; void *
0x14000e18d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e192  mov     ebx, eax
0x14000e194  mov     rcx, [rsp+58h+TokenInformation]
0x14000e199  test    rcx, rcx
0x14000e19c  jz      short loc_14000E1AB
0x14000e19e  mov     rdx, [rsp+58h+var_18]
0x14000e1a3  sub     rdx, rcx
0x14000e1a6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000e1ab  mov     eax, ebx
0x14000e1ad  jmp     loc_14000E24F
0x14000e1b2  mov     [rsp+58h+StringSid], 0
0x14000e1bb  lea     rdx, [rsp+58h+StringSid]; StringSid
0x14000e1c0  mov     rcx, [rsp+58h+TokenInformation]
0x14000e1c5  mov     rcx, [rcx]; Sid
0x14000e1c8  call    cs:__imp_ConvertSidToStringSidW
0x14000e1cf  nop     dword ptr [rax+rax+00h]
0x14000e1d4  test    eax, eax
0x14000e1d6  jnz     short loc_14000E214
0x14000e1d8  mov     rcx, [rsp+58h]; this
0x14000e1dd  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\private"...
0x14000e1e4  lea     edx, [rax+1Ah]; void *
0x14000e1e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e1ec  mov     ebx, eax
0x14000e1ee  lea     rcx, [rsp+58h+StringSid]
0x14000e1f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000e1f8  nop
0x14000e1f9  mov     rcx, [rsp+58h+TokenInformation]
0x14000e1fe  test    rcx, rcx
0x14000e201  jz      short loc_14000E210
0x14000e203  mov     rdx, [rsp+58h+var_18]
0x14000e208  sub     rdx, rcx
0x14000e20b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000e210  mov     eax, ebx
0x14000e212  jmp     short loc_14000E24F
0x14000e214  mov     rax, [rsp+58h+StringSid]
0x14000e219  mov     [rsp+58h+StringSid], 0
0x14000e222  mov     [rsi], rax
0x14000e225  lea     rcx, [rsp+58h+StringSid]
0x14000e22a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000e22f  nop
0x14000e230  mov     rcx, [rsp+58h+TokenInformation]
0x14000e235  test    rcx, rcx
0x14000e238  jz      short loc_14000E247
0x14000e23a  mov     rdx, [rsp+58h+var_18]
0x14000e23f  sub     rdx, rcx
0x14000e242  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000e247  xor     eax, eax
0x14000e249  jmp     short loc_14000E24F
0x14000e24b  mov     eax, dword ptr [rsp+58h+TokenInformationLength]
0x14000e24f  mov     rbx, [rsp+58h+arg_10]
0x14000e254  mov     rsi, [rsp+58h+arg_18]
0x14000e259  add     rsp, 50h
0x14000e25d  pop     rdi
0x14000e25e  retn
```
