# GetUserProfileDirectoryW

- ea: `0x180004b30`
- end: `0x180004f42`
- name: `GetUserProfileDirectoryW`
- size: `1042`
- prototype: `BOOL __stdcall(HANDLE hToken, LPWSTR lpProfileDir, LPDWORD lpcchSize)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004b30`
- `0x180005690`
- `0x180005900`
- `0x180005b30`
- `0x18000e640`
- `0x18001408c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004bdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c63`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004bdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ca3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ca3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004deb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004deb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004c1d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004ead`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004c1d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004ead`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004c3a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004c3a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004c85`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004c85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004daf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004daf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004ce0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004ce0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004d53`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004e21`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004d53`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004e21`

## pseudocode

```c
BOOL __stdcall GetUserProfileDirectoryW(HANDLE hToken, LPWSTR lpProfileDir, LPDWORD lpcchSize)
{
  DWORD v6; // ecx
  HANDLE ProcessHeap; // rax
  LPWSTR v9; // rsi
  BOOL v10; // r13d
  void *v11; // r14
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v14; // rax
  void *v15; // rax
  void *v16; // r15
  HANDLE v17; // rax
  int v18; // edi
  LPWSTR v19; // rsi
  HANDLE v20; // rax
  __int64 v21; // r14
  int BasicProfileFolderPath; // edi
  __int64 v23; // rcx
  int v24; // eax
  BOOL TokenInformation; // eax
  _WORD *v26; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-268h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-260h] BYREF
  _BYTE v29[528]; // [rsp+40h] [rbp-258h] BYREF

  if ( !hToken )
  {
    v6 = 6;
    goto LABEL_4;
  }
  if ( !lpcchSize )
  {
    v6 = 87;
LABEL_4:
    SetLastError(v6);
    return 0;
  }
  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  StringSid = (LPWSTR)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v9 = StringSid;
  if ( !StringSid )
    goto LABEL_36;
  v10 = 1;
  v11 = 0;
  if ( GetTokenInformation(hToken, TokenUser, StringSid, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v24 = ResultFromHeapReAlloc(v9, TokenInformationLength, (void **)&StringSid);
      v9 = StringSid;
      Error = v24;
      if ( v24 < 0 )
        goto LABEL_13;
      TokenInformation = GetTokenInformation(
                           hToken,
                           TokenUser,
                           StringSid,
                           TokenInformationLength,
                           &TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v9);
    TokenInformationLength = LengthSid;
    v14 = GetProcessHeap();
    v15 = HeapAlloc(v14, 8u, LengthSid);
    v16 = v15;
    if ( !v15 )
    {
      Error = -2147024882;
      goto LABEL_13;
    }
    if ( CopySid(TokenInformationLength, v15, *(PSID *)v9) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v16);
        goto LABEL_13;
      }
    }
    v11 = v16;
  }
LABEL_13:
  if ( v9 )
  {
    v17 = GetProcessHeap();
    if ( !HeapFree(v17, 0, v9) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    goto LABEL_36;
  StringSid = 0;
  if ( ConvertSidToStringSidW(v11, &StringSid) )
  {
    v18 = 0;
  }
  else
  {
    v19 = 0;
    v18 = ResultFromKnownLastError();
    if ( v18 < 0 )
      goto LABEL_20;
  }
  v19 = StringSid;
LABEL_20:
  if ( v11 )
  {
    v20 = GetProcessHeap();
    if ( !HeapFree(v20, 0, v11) )
      ResultFromKnownLastError();
  }
  if ( v18 < 0 )
  {
LABEL_36:
    v10 = 0;
    SetLastError(6u);
    return v10;
  }
  if ( !lpProfileDir || !*lpcchSize )
  {
    LOWORD(BasicProfileFolderPath) = 122;
    *lpcchSize = 0;
    v21 = 0x7FFFFFFF;
    goto LABEL_38;
  }
  v21 = 0x7FFFFFFF;
  BasicProfileFolderPath = GetBasicProfileFolderPath(5, v19, lpProfileDir, *lpcchSize);
  if ( BasicProfileFolderPath >= 0 )
  {
    v23 = 0x7FFFFFFF;
    do
    {
      if ( !*lpProfileDir )
        break;
      ++lpProfileDir;
      --v23;
    }
    while ( v23 );
    BasicProfileFolderPath = -2147024809;
    if ( v23 )
    {
      BasicProfileFolderPath = 0;
      *lpcchSize = 0x80000000 - v23;
    }
  }
  if ( BasicProfileFolderPath == -2147024774 )
  {
    if ( *lpcchSize >= 0x104 )
      goto LABEL_39;
LABEL_38:
    if ( (int)GetBasicProfileFolderPath(5, v19, v29, 260) >= 0 )
    {
      v26 = v29;
      while ( *v26 )
      {
        ++v26;
        if ( !--v21 )
          goto LABEL_39;
      }
      *lpcchSize = 0x80000000 - v21;
    }
    goto LABEL_39;
  }
  if ( BasicProfileFolderPath < 0 )
  {
LABEL_39:
    SetLastError((unsigned __int16)BasicProfileFolderPath);
    v10 = 0;
  }
  LocalFree(v19);
  return v10;
}

```

## disassembly

```asm
0x180004b30  push    rbx
0x180004b32  push    rbp
0x180004b33  push    r12
0x180004b35  push    r15
0x180004b37  sub     rsp, 278h
0x180004b3e  mov     rax, cs:__security_cookie
0x180004b45  xor     rax, rsp
0x180004b48  mov     [rsp+298h+var_48], rax
0x180004b50  mov     r12, r8
0x180004b53  mov     rbx, rdx
0x180004b56  mov     r15, rcx
0x180004b59  test    rcx, rcx
0x180004b5c  jz      loc_180004F07
0x180004b62  test    r8, r8
0x180004b65  jnz     short loc_180004B9B
0x180004b67  mov     ecx, 57h ; 'W'; dwErrCode
0x180004b6c  call    cs:__imp_SetLastError
0x180004b73  nop     dword ptr [rax+rax+00h]
0x180004b78  xor     ebp, ebp
0x180004b7a  mov     eax, ebp
0x180004b7c  mov     rcx, [rsp+298h+var_48]
0x180004b84  xor     rcx, rsp; StackCookie
0x180004b87  call    __security_check_cookie
0x180004b8c  add     rsp, 278h
0x180004b93  pop     r15
0x180004b95  pop     r12
0x180004b97  pop     rbp
0x180004b98  pop     rbx
0x180004b99  retn
0x180004b9b  mov     [rsp+298h+arg_18], rsi
0x180004ba3  mov     [rsp+298h+var_28], rdi
0x180004bab  mov     [rsp+298h+var_30], r13
0x180004bb3  mov     [rsp+298h+var_38], r14
0x180004bbb  mov     [rsp+298h+TokenInformationLength], 0C8h
0x180004bc3  call    cs:__imp_GetProcessHeap
0x180004bca  nop     dword ptr [rax+rax+00h]
0x180004bcf  mov     edx, 8; dwFlags
0x180004bd4  mov     r8d, 0C8h; dwBytes
0x180004bda  mov     rcx, rax; hHeap
0x180004bdd  call    cs:__imp_HeapAlloc
0x180004be4  nop     dword ptr [rax+rax+00h]
0x180004be9  xor     ebp, ebp
0x180004beb  mov     [rsp+298h+StringSid], rax
0x180004bf0  mov     rsi, rax
0x180004bf3  test    rax, rax
0x180004bf6  jz      loc_180004DE3
0x180004bfc  mov     r9d, [rsp+298h+TokenInformationLength]; TokenInformationLength
0x180004c01  lea     rax, [rsp+298h+TokenInformationLength]
0x180004c06  mov     r13d, 1
0x180004c0c  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x180004c11  mov     edx, r13d; TokenInformationClass
0x180004c14  mov     r8, rsi; TokenInformation
0x180004c17  mov     rcx, r15; TokenHandle
0x180004c1a  mov     r14d, ebp
0x180004c1d  call    cs:__imp_GetTokenInformation
0x180004c24  nop     dword ptr [rax+rax+00h]
0x180004c29  test    eax, eax
0x180004c2b  jz      loc_180004E63
0x180004c31  mov     edi, ebp
0x180004c33  test    edi, edi
0x180004c35  js      short loc_180004C9E
0x180004c37  mov     rcx, [rsi]; pSid
0x180004c3a  call    cs:__imp_GetLengthSid
0x180004c41  nop     dword ptr [rax+rax+00h]
0x180004c46  mov     edi, eax
0x180004c48  mov     [rsp+298h+TokenInformationLength], edi
0x180004c4c  call    cs:__imp_GetProcessHeap
0x180004c53  nop     dword ptr [rax+rax+00h]
0x180004c58  mov     r8d, edi; dwBytes
0x180004c5b  mov     edx, 8; dwFlags
0x180004c60  mov     rcx, rax; hHeap
0x180004c63  call    cs:__imp_HeapAlloc
0x180004c6a  nop     dword ptr [rax+rax+00h]
0x180004c6f  mov     r15, rax
0x180004c72  test    rax, rax
0x180004c75  jz      loc_180004F11
0x180004c7b  mov     r8, [rsi]; pSourceSid
0x180004c7e  mov     rdx, rax; pDestinationSid
0x180004c81  mov     ecx, [rsp+298h+TokenInformationLength]; nDestinationSidLength
0x180004c85  call    cs:__imp_CopySid
0x180004c8c  nop     dword ptr [rax+rax+00h]
0x180004c91  test    eax, eax
0x180004c93  jz      loc_180004EC7
0x180004c99  mov     edi, ebp
0x180004c9b  mov     r14, r15
0x180004c9e  test    rsi, rsi
0x180004ca1  jz      short loc_180004CCB
0x180004ca3  call    cs:__imp_GetProcessHeap
0x180004caa  nop     dword ptr [rax+rax+00h]
0x180004caf  mov     r8, rsi; lpMem
0x180004cb2  xor     edx, edx; dwFlags
0x180004cb4  mov     rcx, rax; hHeap
0x180004cb7  call    cs:__imp_HeapFree
0x180004cbe  nop     dword ptr [rax+rax+00h]
0x180004cc3  test    eax, eax
0x180004cc5  jz      loc_180004F1B
0x180004ccb  test    edi, edi
0x180004ccd  js      loc_180004DE3
0x180004cd3  lea     rdx, [rsp+298h+StringSid]; StringSid
0x180004cd8  mov     [rsp+298h+StringSid], rbp
0x180004cdd  mov     rcx, r14; Sid
0x180004ce0  call    cs:__imp_ConvertSidToStringSidW
0x180004ce7  nop     dword ptr [rax+rax+00h]
0x180004cec  test    eax, eax
0x180004cee  jz      loc_180004E4C
0x180004cf4  mov     edi, ebp
0x180004cf6  mov     rsi, [rsp+298h+StringSid]
0x180004cfb  test    r14, r14
0x180004cfe  jz      short loc_180004D28
0x180004d00  call    cs:__imp_GetProcessHeap
0x180004d07  nop     dword ptr [rax+rax+00h]
0x180004d0c  mov     r8, r14; lpMem
0x180004d0f  xor     edx, edx; dwFlags
0x180004d11  mov     rcx, rax; hHeap
0x180004d14  call    cs:__imp_HeapFree
0x180004d1b  nop     dword ptr [rax+rax+00h]
0x180004d20  test    eax, eax
0x180004d22  jz      loc_180004F25
0x180004d28  test    edi, edi
0x180004d2a  js      loc_180004DE3
0x180004d30  test    rbx, rbx
0x180004d33  jz      loc_180004DF9
0x180004d39  mov     eax, [r12]
0x180004d3d  test    eax, eax
0x180004d3f  jz      loc_180004DF9
0x180004d45  mov     r9d, eax
0x180004d48  mov     r8, rbx
0x180004d4b  mov     rdx, rsi
0x180004d4e  mov     ecx, 5
0x180004d53  call    cs:__imp_GetBasicProfileFolderPath
0x180004d5a  nop     dword ptr [rax+rax+00h]
0x180004d5f  mov     r14d, 7FFFFFFFh
0x180004d65  mov     r15d, 80000000h
0x180004d6b  mov     edi, eax
0x180004d6d  test    eax, eax
0x180004d6f  js      short loc_180004D98
0x180004d71  mov     ecx, r14d
0x180004d74  cmp     [rbx], bp
0x180004d77  jz      short loc_180004D82
0x180004d79  add     rbx, 2
0x180004d7d  sub     rcx, r13
0x180004d80  jnz     short loc_180004D74
0x180004d82  test    rcx, rcx
0x180004d85  mov     edi, 80070057h
0x180004d8a  cmovnz  edi, ebp
0x180004d8d  jz      short loc_180004D98
0x180004d8f  mov     eax, r15d
0x180004d92  sub     eax, ecx
0x180004d94  mov     [r12], eax
0x180004d98  cmp     edi, 8007007Ah
0x180004d9e  jz      loc_180004F2F
0x180004da4  test    edi, edi
0x180004da6  js      loc_180004E35
0x180004dac  mov     rcx, rsi; hMem
0x180004daf  call    cs:__imp_LocalFree
0x180004db6  nop     dword ptr [rax+rax+00h]
0x180004dbb  mov     r14, [rsp+298h+var_38]
0x180004dc3  mov     eax, r13d
0x180004dc6  mov     r13, [rsp+298h+var_30]
0x180004dce  mov     rdi, [rsp+298h+var_28]
0x180004dd6  mov     rsi, [rsp+298h+arg_18]
0x180004dde  jmp     loc_180004B7C
0x180004de3  mov     ecx, 6; dwErrCode
0x180004de8  mov     r13d, ebp
0x180004deb  call    cs:__imp_SetLastError
0x180004df2  nop     dword ptr [rax+rax+00h]
0x180004df7  jmp     short loc_180004DBB
0x180004df9  mov     edi, 8007007Ah
0x180004dfe  mov     [r12], ebp
0x180004e02  mov     r14d, 7FFFFFFFh
0x180004e08  mov     r15d, 80000000h
0x180004e0e  mov     r9d, 104h
0x180004e14  lea     r8, [rsp+298h+var_258]
0x180004e19  mov     rdx, rsi
0x180004e1c  mov     ecx, 5
0x180004e21  call    cs:__imp_GetBasicProfileFolderPath
0x180004e28  nop     dword ptr [rax+rax+00h]
0x180004e2d  test    eax, eax
0x180004e2f  jns     loc_180004EE3
0x180004e35  movzx   ecx, di; dwErrCode
0x180004e38  call    cs:__imp_SetLastError
0x180004e3f  nop     dword ptr [rax+rax+00h]
0x180004e44  mov     r13d, ebp
0x180004e47  jmp     loc_180004DAC
0x180004e4c  mov     rsi, rbp
0x180004e4f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004e54  mov     edi, eax
0x180004e56  test    eax, eax
0x180004e58  jns     loc_180004CF6
0x180004e5e  jmp     loc_180004CFB
0x180004e63  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004e68  mov     edi, eax
0x180004e6a  cmp     eax, 8007007Ah
0x180004e6f  jnz     loc_180004C33
0x180004e75  mov     edx, [rsp+298h+TokenInformationLength]; dwBytes
0x180004e79  lea     r8, [rsp+298h+StringSid]; void **
0x180004e7e  mov     rcx, rsi; lpMem
0x180004e81  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180004e86  mov     rsi, [rsp+298h+StringSid]
0x180004e8b  mov     edi, eax
0x180004e8d  test    eax, eax
0x180004e8f  js      loc_180004C9E
0x180004e95  mov     r9d, [rsp+298h+TokenInformationLength]; TokenInformationLength
0x180004e9a  lea     rax, [rsp+298h+TokenInformationLength]
0x180004e9f  mov     r8, rsi; TokenInformation
0x180004ea2  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x180004ea7  mov     edx, r13d; TokenInformationClass
0x180004eaa  mov     rcx, r15; TokenHandle
0x180004ead  call    cs:__imp_GetTokenInformation
0x180004eb4  nop     dword ptr [rax+rax+00h]
0x180004eb9  mov     ecx, eax; int
0x180004ebb  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180004ec0  mov     edi, eax
0x180004ec2  jmp     loc_180004C33
0x180004ec7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004ecc  mov     edi, eax
0x180004ece  test    eax, eax
0x180004ed0  jns     loc_180004C9B
0x180004ed6  mov     rcx, r15; lpMem
0x180004ed9  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180004ede  jmp     loc_180004C9E
0x180004ee3  lea     rax, [rsp+298h+var_258]
0x180004ee8  cmp     [rax], bp
0x180004eeb  jz      short loc_180004EFB
0x180004eed  add     rax, 2
0x180004ef1  sub     r14, r13
0x180004ef4  jnz     short loc_180004EE8
0x180004ef6  jmp     loc_180004E35
0x180004efb  sub     r15d, r14d
0x180004efe  mov     [r12], r15d
0x180004f02  jmp     loc_180004E35
0x180004f07  mov     ecx, 6
0x180004f0c  jmp     loc_180004B6C
0x180004f11  mov     edi, 8007000Eh
0x180004f16  jmp     loc_180004C9E
0x180004f1b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004f20  jmp     loc_180004CCB
0x180004f25  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004f2a  jmp     loc_180004D28
0x180004f2f  cmp     dword ptr [r12], 104h
0x180004f37  jnb     loc_180004E35
0x180004f3d  jmp     loc_180004E0E
```
