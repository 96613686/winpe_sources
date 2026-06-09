# GetUserProfileDirectoryWInternal(void *,ushort *,ulong *)

- ea: `0x180004ae0`
- end: `0x180004ea2`
- name: `?GetUserProfileDirectoryWInternal@@YAHPEAXPEAGPEAK@Z`
- size: `962`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006690`

## callees

- `0x180004ae0`
- `0x180004fc0`
- `0x1800051f0`
- `0x1800053f0`
- `0x18000d9b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c7e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004dd2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004dd2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004bef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004bef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e29`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004bba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004bba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e5d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004bd2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004bd2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004c0b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004c0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d09`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004c55`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004c55`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004cb7`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004d76`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004cb7`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004d76`

## pseudocode

```c
__int64 __fastcall GetUserProfileDirectoryWInternal(HANDLE TokenHandle, unsigned __int16 *a2, unsigned int *a3)
{
  HANDLE ProcessHeap; // rax
  PSID *v8; // rsi
  unsigned int v9; // r13d
  void *v10; // rbp
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v13; // rax
  void *v14; // rax
  void *v15; // r14
  HANDLE v16; // rax
  int v17; // edi
  LPWSTR v18; // rsi
  HANDLE v19; // rax
  __int64 v20; // rbp
  int BasicProfileFolderPath; // edi
  __int64 v22; // rcx
  DWORD v23; // edi
  HANDLE v24; // rax
  PSID *v25; // rax
  _WORD *v26; // rax
  BOOL TokenInformation; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-268h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-260h] BYREF
  _BYTE v30[528]; // [rsp+40h] [rbp-258h] BYREF

  if ( TokenHandle )
  {
    if ( !a3 )
    {
      SetLastError(0x57u);
      return 0;
    }
    TokenInformationLength = 200;
    ProcessHeap = GetProcessHeap();
    v8 = (PSID *)HeapAlloc(ProcessHeap, 8u, 0xC8u);
    if ( !v8 )
      goto LABEL_34;
    v9 = 1;
    v10 = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error == -2147024774 )
      {
        v23 = TokenInformationLength;
        v24 = GetProcessHeap();
        v25 = (PSID *)HeapReAlloc(v24, 8u, v8, v23);
        if ( v25 )
        {
          v8 = v25;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
            goto LABEL_12;
        }
        TokenInformation = GetTokenInformation(
                             TokenHandle,
                             TokenUser,
                             v8,
                             TokenInformationLength,
                             &TokenInformationLength);
        Error = ResultFromWin32Bool(TokenInformation);
      }
    }
    if ( Error < 0 )
      goto LABEL_12;
    LengthSid = GetLengthSid(*v8);
    TokenInformationLength = LengthSid;
    v13 = GetProcessHeap();
    v14 = HeapAlloc(v13, 8u, LengthSid);
    v15 = v14;
    if ( v14 )
    {
      if ( CopySid(TokenInformationLength, v14, *v8) )
      {
        Error = 0;
LABEL_11:
        v10 = v15;
        goto LABEL_12;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_11;
      ResultFromHeapFree(v15);
    }
    else
    {
      Error = -2147024882;
    }
LABEL_12:
    v16 = GetProcessHeap();
    if ( !HeapFree(v16, 0, v8) )
      ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_34;
    StringSid = 0;
    if ( ConvertSidToStringSidW(v10, &StringSid) )
    {
      v17 = 0;
    }
    else
    {
      v18 = 0;
      v17 = ResultFromKnownLastError();
      if ( v17 < 0 )
        goto LABEL_18;
    }
    v18 = StringSid;
LABEL_18:
    if ( v10 )
    {
      v19 = GetProcessHeap();
      if ( !HeapFree(v19, 0, v10) )
        ResultFromKnownLastError();
    }
    if ( v17 >= 0 )
    {
      if ( a2 && *a3 )
      {
        v20 = 0x7FFFFFFF;
        BasicProfileFolderPath = GetBasicProfileFolderPath(5, v18, a2, *a3);
        if ( BasicProfileFolderPath >= 0 )
        {
          v22 = 0x7FFFFFFF;
          do
          {
            if ( !*a2 )
              break;
            ++a2;
            --v22;
          }
          while ( v22 );
          BasicProfileFolderPath = -2147024809;
          if ( v22 )
          {
            BasicProfileFolderPath = 0;
            *a3 = 0x80000000 - v22;
          }
        }
        if ( BasicProfileFolderPath != -2147024774 )
        {
          if ( BasicProfileFolderPath >= 0 )
          {
LABEL_32:
            LocalFree(v18);
            return v9;
          }
LABEL_37:
          SetLastError((unsigned __int16)BasicProfileFolderPath);
          v9 = 0;
          goto LABEL_32;
        }
        if ( *a3 >= 0x104 )
          goto LABEL_37;
      }
      else
      {
        LOWORD(BasicProfileFolderPath) = 122;
        *a3 = 0;
        v20 = 0x7FFFFFFF;
      }
      if ( (int)GetBasicProfileFolderPath(5, v18, v30, 260) >= 0 )
      {
        v26 = v30;
        while ( *v26 )
        {
          ++v26;
          if ( !--v20 )
            goto LABEL_37;
        }
        *a3 = 0x80000000 - v20;
      }
      goto LABEL_37;
    }
LABEL_34:
    v9 = 0;
    SetLastError(6u);
    return v9;
  }
  SetLastError(6u);
  return 0;
}

```

## disassembly

```asm
0x180004ae0  push    rbx
0x180004ae2  push    r12
0x180004ae4  push    r14
0x180004ae6  sub     rsp, 280h
0x180004aed  mov     rax, cs:__security_cookie
0x180004af4  xor     rax, rsp
0x180004af7  mov     [rsp+298h+var_48], rax
0x180004aff  mov     r12, r8
0x180004b02  mov     rbx, rdx
0x180004b05  mov     r14, rcx
0x180004b08  test    rcx, rcx
0x180004b0b  jz      loc_180004E24
0x180004b11  test    r8, r8
0x180004b14  jnz     short loc_180004B40
0x180004b16  mov     ecx, 57h ; 'W'; dwErrCode
0x180004b1b  call    cs:__imp_SetLastError
0x180004b21  xor     eax, eax
0x180004b23  mov     rcx, [rsp+298h+var_48]
0x180004b2b  xor     rcx, rsp; StackCookie
0x180004b2e  call    __security_check_cookie
0x180004b33  add     rsp, 280h
0x180004b3a  pop     r14
0x180004b3c  pop     r12
0x180004b3e  pop     rbx
0x180004b3f  retn
0x180004b40  mov     [rsp+298h+arg_18], rbp
0x180004b48  mov     [rsp+298h+var_20], rsi
0x180004b50  mov     [rsp+298h+var_28], rdi
0x180004b58  mov     [rsp+298h+var_30], r13
0x180004b60  mov     [rsp+298h+var_38], r15
0x180004b68  mov     [rsp+298h+TokenInformationLength], 0C8h
0x180004b70  call    cs:__imp_GetProcessHeap
0x180004b76  mov     edx, 8; dwFlags
0x180004b7b  mov     r8d, 0C8h; dwBytes
0x180004b81  mov     rcx, rax; hHeap
0x180004b84  call    cs:__imp_HeapAlloc
0x180004b8a  xor     r15d, r15d
0x180004b8d  mov     rsi, rax
0x180004b90  test    rax, rax
0x180004b93  jz      loc_180004D3F
0x180004b99  mov     r9d, [rsp+298h+TokenInformationLength]; TokenInformationLength
0x180004b9e  lea     rax, [rsp+298h+TokenInformationLength]
0x180004ba3  mov     r13d, 1
0x180004ba9  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x180004bae  mov     edx, r13d; TokenInformationClass
0x180004bb1  mov     r8, rsi; TokenInformation
0x180004bb4  mov     rcx, r14; TokenHandle
0x180004bb7  mov     ebp, r15d
0x180004bba  call    cs:__imp_GetTokenInformation
0x180004bc0  test    eax, eax
0x180004bc2  jz      loc_180004DA8
0x180004bc8  mov     edi, r15d
0x180004bcb  test    edi, edi
0x180004bcd  js      short loc_180004C24
0x180004bcf  mov     rcx, [rsi]; pSid
0x180004bd2  call    cs:__imp_GetLengthSid
0x180004bd8  mov     edi, eax
0x180004bda  mov     [rsp+298h+TokenInformationLength], edi
0x180004bde  call    cs:__imp_GetProcessHeap
0x180004be4  mov     r8d, edi; dwBytes
0x180004be7  mov     edx, 8; dwFlags
0x180004bec  mov     rcx, rax; hHeap
0x180004bef  call    cs:__imp_HeapAlloc
0x180004bf5  mov     r14, rax
0x180004bf8  test    rax, rax
0x180004bfb  jz      loc_180004E71
0x180004c01  mov     r8, [rsi]; pSourceSid
0x180004c04  mov     rdx, rax; pDestinationSid
0x180004c07  mov     ecx, [rsp+298h+TokenInformationLength]; nDestinationSidLength
0x180004c0b  call    cs:__imp_CopySid
0x180004c11  test    eax, eax
0x180004c13  jz      loc_180004DE2
0x180004c19  mov     edi, r15d
0x180004c1c  mov     rbp, r14
0x180004c1f  test    rsi, rsi
0x180004c22  jz      short loc_180004C40
0x180004c24  call    cs:__imp_GetProcessHeap
0x180004c2a  mov     r8, rsi; lpMem
0x180004c2d  xor     edx, edx; dwFlags
0x180004c2f  mov     rcx, rax; hHeap
0x180004c32  call    cs:__imp_HeapFree
0x180004c38  test    eax, eax
0x180004c3a  jz      loc_180004E7B
0x180004c40  test    edi, edi
0x180004c42  js      loc_180004D3F
0x180004c48  lea     rdx, [rsp+298h+StringSid]; StringSid
0x180004c4d  mov     [rsp+298h+StringSid], r15
0x180004c52  mov     rcx, rbp; Sid
0x180004c55  call    cs:__imp_ConvertSidToStringSidW
0x180004c5b  test    eax, eax
0x180004c5d  jz      loc_180004D91
0x180004c63  mov     edi, r15d
0x180004c66  mov     rsi, [rsp+298h+StringSid]
0x180004c6b  test    rbp, rbp
0x180004c6e  jz      short loc_180004C8C
0x180004c70  call    cs:__imp_GetProcessHeap
0x180004c76  mov     r8, rbp; lpMem
0x180004c79  xor     edx, edx; dwFlags
0x180004c7b  mov     rcx, rax; hHeap
0x180004c7e  call    cs:__imp_HeapFree
0x180004c84  test    eax, eax
0x180004c86  jz      loc_180004E85
0x180004c8c  test    edi, edi
0x180004c8e  js      loc_180004D3F
0x180004c94  test    rbx, rbx
0x180004c97  jz      loc_180004D4F
0x180004c9d  mov     eax, [r12]
0x180004ca1  test    eax, eax
0x180004ca3  jz      loc_180004D4F
0x180004ca9  mov     r9d, eax
0x180004cac  mov     r8, rbx
0x180004caf  mov     rdx, rsi
0x180004cb2  mov     ecx, 5
0x180004cb7  call    cs:__imp_GetBasicProfileFolderPath
0x180004cbd  mov     ebp, 7FFFFFFFh
0x180004cc2  mov     r14d, 80000000h
0x180004cc8  mov     edi, eax
0x180004cca  test    eax, eax
0x180004ccc  js      short loc_180004CF6
0x180004cce  mov     ecx, ebp
0x180004cd0  cmp     [rbx], r15w
0x180004cd4  jz      short loc_180004CDF
0x180004cd6  add     rbx, 2
0x180004cda  sub     rcx, r13
0x180004cdd  jnz     short loc_180004CD0
0x180004cdf  test    rcx, rcx
0x180004ce2  mov     edi, 80070057h
0x180004ce7  cmovnz  edi, r15d
0x180004ceb  jz      short loc_180004CF6
0x180004ced  mov     eax, r14d
0x180004cf0  sub     eax, ecx
0x180004cf2  mov     [r12], eax
0x180004cf6  cmp     edi, 8007007Ah
0x180004cfc  jz      loc_180004E8F
0x180004d02  test    edi, edi
0x180004d04  js      short loc_180004D80
0x180004d06  mov     rcx, rsi; hMem
0x180004d09  call    cs:__imp_LocalFree
0x180004d0f  mov     r15, [rsp+298h+var_38]
0x180004d17  mov     eax, r13d
0x180004d1a  mov     r13, [rsp+298h+var_30]
0x180004d22  mov     rdi, [rsp+298h+var_28]
0x180004d2a  mov     rsi, [rsp+298h+var_20]
0x180004d32  mov     rbp, [rsp+298h+arg_18]
0x180004d3a  jmp     loc_180004B23
0x180004d3f  mov     ecx, 6; dwErrCode
0x180004d44  mov     r13d, r15d
0x180004d47  call    cs:__imp_SetLastError
0x180004d4d  jmp     short loc_180004D0F
0x180004d4f  mov     edi, 8007007Ah
0x180004d54  mov     [r12], r15d
0x180004d58  mov     ebp, 7FFFFFFFh
0x180004d5d  mov     r14d, 80000000h
0x180004d63  mov     r9d, 104h
0x180004d69  lea     r8, [rsp+298h+var_258]
0x180004d6e  mov     rdx, rsi
0x180004d71  mov     ecx, 5
0x180004d76  call    cs:__imp_GetBasicProfileFolderPath
0x180004d7c  test    eax, eax
0x180004d7e  jns     short loc_180004DFE
0x180004d80  movzx   ecx, di; dwErrCode
0x180004d83  call    cs:__imp_SetLastError
0x180004d89  mov     r13d, r15d
0x180004d8c  jmp     loc_180004D06
0x180004d91  mov     rsi, r15
0x180004d94  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004d99  mov     edi, eax
0x180004d9b  test    eax, eax
0x180004d9d  jns     loc_180004C66
0x180004da3  jmp     loc_180004C6B
0x180004da8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004dad  mov     edi, eax
0x180004daf  cmp     eax, 8007007Ah
0x180004db4  jnz     loc_180004BCB
0x180004dba  mov     edi, [rsp+298h+TokenInformationLength]
0x180004dbe  call    cs:__imp_GetProcessHeap
0x180004dc4  mov     r9d, edi; dwBytes
0x180004dc7  mov     r8, rsi; lpMem
0x180004dca  mov     rcx, rax; hHeap
0x180004dcd  mov     edx, 8; dwFlags
0x180004dd2  call    cs:__imp_HeapReAlloc
0x180004dd8  test    rax, rax
0x180004ddb  jz      short loc_180004E36
0x180004ddd  mov     rsi, rax
0x180004de0  jmp     short loc_180004E45
0x180004de2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004de7  mov     edi, eax
0x180004de9  test    eax, eax
0x180004deb  jns     loc_180004C1C
0x180004df1  mov     rcx, r14; lpMem
0x180004df4  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180004df9  jmp     loc_180004C1F
0x180004dfe  lea     rax, [rsp+298h+var_258]
0x180004e03  cmp     [rax], r15w
0x180004e07  jz      short loc_180004E18
0x180004e09  add     rax, 2
0x180004e0d  sub     rbp, 1
0x180004e11  jnz     short loc_180004E03
0x180004e13  jmp     loc_180004D80
0x180004e18  sub     r14d, ebp
0x180004e1b  mov     [r12], r14d
0x180004e1f  jmp     loc_180004D80
0x180004e24  mov     ecx, 6; dwErrCode
0x180004e29  call    cs:__imp_SetLastError
0x180004e2f  xor     eax, eax
0x180004e31  jmp     loc_180004B23
0x180004e36  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004e3b  mov     edi, eax
0x180004e3d  test    eax, eax
0x180004e3f  js      loc_180004C24
0x180004e45  mov     r9d, [rsp+298h+TokenInformationLength]; TokenInformationLength
0x180004e4a  lea     rax, [rsp+298h+TokenInformationLength]
0x180004e4f  mov     r8, rsi; TokenInformation
0x180004e52  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x180004e57  mov     edx, r13d; TokenInformationClass
0x180004e5a  mov     rcx, r14; TokenHandle
0x180004e5d  call    cs:__imp_GetTokenInformation
0x180004e63  mov     ecx, eax; int
0x180004e65  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180004e6a  mov     edi, eax
0x180004e6c  jmp     loc_180004BCB
0x180004e71  mov     edi, 8007000Eh
0x180004e76  jmp     loc_180004C1F
0x180004e7b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004e80  jmp     loc_180004C40
0x180004e85  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004e8a  jmp     loc_180004C8C
0x180004e8f  cmp     dword ptr [r12], 104h
0x180004e97  jnb     loc_180004D80
0x180004e9d  jmp     loc_180004D63
```
