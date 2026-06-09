# GetUserTextualSidHKCU

- ea: `0x180014070`
- end: `0x180014480`
- name: `GetUserTextualSidHKCU`
- size: `1040`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014490`

## callees

- `0x180014070`
- `0x180014970`
- `0x180014bb8`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800141ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001437b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014473`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800141ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001437b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001442f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001442f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800140d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800140d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800140a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800140a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800140be`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800140be`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800140ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800140ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014173`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014444`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014173`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014444`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014373`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014373`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800141e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800141e7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014166`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014166`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001421d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001421d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001418a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001418a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014200`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014200`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180014211`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180014211`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001414b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800141be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001414b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800141be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180014306`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180014306`

## pseudocode

```c
__int64 __fastcall GetUserTextualSidHKCU(STRSAFE_LPWSTR pszDest, unsigned int *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v6; // r15
  unsigned int v7; // ebx
  PSID *v8; // rdi
  PSID *v9; // r14
  SIZE_T LengthSid; // r15
  HLOCAL v11; // rax
  void *v12; // rsi
  void *v13; // r14
  DWORD LastError; // edi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rbx
  DWORD v16; // edi
  unsigned int v17; // eax
  unsigned int v18; // ecx
  HRESULT v19; // eax
  DWORD i; // ebx
  int v21; // eax
  DWORD v22; // edi
  __int64 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+30h] [rbp-D0h]
  DWORD TokenInformationLength; // [rsp+60h] [rbp-A0h] BYREF
  size_t pcchRemaining; // [rsp+68h] [rbp-98h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+70h] [rbp-90h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  _BYTE TokenInformation[256]; // [rsp+80h] [rbp-80h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      return 0;
  }
  v6 = TokenHandle;
  TokenInformationLength = 256;
  v7 = GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, &TokenInformationLength);
  if ( v7 )
  {
    v8 = 0;
    v9 = (PSID *)TokenInformation;
  }
  else
  {
    v12 = 0;
    if ( GetLastError() != 122 )
      goto LABEL_13;
    v8 = (PSID *)LocalAlloc(0, TokenInformationLength);
    if ( !v8 )
      goto LABEL_13;
    v9 = v8;
    v7 = GetTokenInformation(v6, TokenUser, v8, TokenInformationLength, &TokenInformationLength);
    if ( !v7 )
    {
LABEL_12:
      freeWithSavedLastError(v8);
      goto LABEL_13;
    }
  }
  v7 = 0;
  LengthSid = GetLengthSid(*v9);
  v11 = LocalAlloc(0, LengthSid);
  v12 = v11;
  if ( v11 )
  {
    v7 = CopySid(LengthSid, v11, *v9);
    if ( !v7 )
    {
      freeWithSavedLastError(v12);
      v12 = 0;
    }
  }
  if ( v8 )
    goto LABEL_12;
LABEL_13:
  v13 = TokenHandle;
  if ( TokenHandle )
  {
    LastError = GetLastError();
    CloseHandle(v13);
    SetLastError(LastError);
  }
  if ( !v7 )
    goto LABEL_29;
  if ( !IsValidSid(v12) )
    goto LABEL_40;
  SidIdentifierAuthority = GetSidIdentifierAuthority(v12);
  v16 = *GetSidSubAuthorityCount(v12);
  v17 = *a2;
  v18 = 12 * v16 + 28;
  if ( *a2 < v18 || !pszDest )
  {
    *a2 = v18;
    SetLastError(0x7Au);
LABEL_40:
    v7 = 0;
    goto LABEL_29;
  }
  pcchRemaining = *a2;
  ppszDestEnd = pszDest;
  v19 = StringCchPrintfExW(pszDest, v17, &ppszDestEnd, &pcchRemaining, 0, L"S-%lu-", 1);
  if ( v19 >= 0 )
  {
    if ( *(_WORD *)SidIdentifierAuthority->Value )
    {
      LODWORD(v24) = SidIdentifierAuthority->Value[0];
      v19 = StringCchPrintfExW(
              ppszDestEnd,
              pcchRemaining,
              &ppszDestEnd,
              &pcchRemaining,
              0,
              L"0x%02hx%02hx%02hx%02hx%02hx%02hx",
              v24,
              SidIdentifierAuthority->Value[1],
              SidIdentifierAuthority->Value[2],
              SidIdentifierAuthority->Value[3],
              SidIdentifierAuthority->Value[4],
              SidIdentifierAuthority->Value[5]);
      if ( v19 >= 0 )
      {
LABEL_22:
        for ( i = 0; i < v16; ++i )
        {
          LODWORD(v25) = *GetSidSubAuthority(v12, i);
          v19 = StringCchPrintfExW(ppszDestEnd, pcchRemaining, &ppszDestEnd, &pcchRemaining, 0, L"-%lu", v25);
          if ( v19 < 0 )
            goto LABEL_32;
        }
        v21 = pcchRemaining;
        if ( pcchRemaining )
          v21 = pcchRemaining - 1;
        *a2 -= v21;
        v7 = 1;
        goto LABEL_29;
      }
    }
    else
    {
      LODWORD(v24) = SidIdentifierAuthority->Value[5]
                   + (SidIdentifierAuthority->Value[4] << 8)
                   + (SidIdentifierAuthority->Value[3] << 16)
                   + (SidIdentifierAuthority->Value[2] << 24);
      v19 = StringCchPrintfExW(ppszDestEnd, pcchRemaining, &ppszDestEnd, &pcchRemaining, 0, L"%lu", v24);
      if ( v19 >= 0 )
        goto LABEL_22;
    }
  }
LABEL_32:
  SetLastError(v19);
  v7 = 0;
LABEL_29:
  if ( v12 )
  {
    v22 = GetLastError();
    LocalFree(v12);
    SetLastError(v22);
  }
  return v7;
}

```

## disassembly

```asm
0x180014070  push    rbp
0x180014072  push    r12
0x180014074  push    r13
0x180014076  lea     rbp, [rsp-0B0h]
0x18001407e  sub     rsp, 1B0h
0x180014085  mov     rax, cs:__security_cookie
0x18001408c  xor     rax, rsp
0x18001408f  mov     [rbp+0C0h+var_40], rax
0x180014096  mov     r12, rdx
0x180014099  mov     [rsp+1C0h+TokenHandle], 0
0x1800140a2  mov     r13, rcx
0x1800140a5  call    cs:__imp_GetCurrentThread
0x1800140ab  lea     r9, [rsp+1C0h+TokenHandle]; TokenHandle
0x1800140b0  mov     edx, 8; DesiredAccess
0x1800140b5  mov     rcx, rax; ThreadHandle
0x1800140b8  mov     r8d, 1; OpenAsSelf
0x1800140be  call    cs:__imp_OpenThreadToken
0x1800140c4  test    eax, eax
0x1800140c6  jnz     short loc_1800140FA
0x1800140c8  call    cs:__imp_GetLastError
0x1800140ce  cmp     eax, 3F0h
0x1800140d3  jnz     loc_1800143C4
0x1800140d9  call    cs:__imp_GetCurrentProcess
0x1800140df  lea     r8, [rsp+1C0h+TokenHandle]; TokenHandle
0x1800140e4  mov     edx, 8; DesiredAccess
0x1800140e9  mov     rcx, rax; ProcessHandle
0x1800140ec  call    cs:__imp_OpenProcessToken
0x1800140f2  test    eax, eax
0x1800140f4  jz      loc_1800143C4
0x1800140fa  mov     [rsp+1C0h+arg_10], rbx
0x180014102  lea     rax, [rsp+1C0h+TokenInformationLength]
0x180014107  mov     [rsp+1C0h+var_18], rsi
0x18001410f  lea     r8, [rbp+0C0h+TokenInformation]; TokenInformation
0x180014113  mov     [rsp+1C0h+var_20], rdi
0x18001411b  mov     r9d, 100h; TokenInformationLength
0x180014121  mov     [rsp+1C0h+var_28], r14
0x180014129  mov     edx, 1; TokenInformationClass
0x18001412e  mov     [rsp+1C0h+var_30], r15
0x180014136  mov     r15, [rsp+1C0h+TokenHandle]
0x18001413b  mov     rcx, r15; TokenHandle
0x18001413e  mov     [rsp+1C0h+TokenInformationLength], 100h
0x180014146  mov     [rsp+1C0h+ReturnLength], rax; ReturnLength
0x18001414b  call    cs:__imp_GetTokenInformation
0x180014151  mov     ebx, eax
0x180014153  test    eax, eax
0x180014155  jz      loc_18001442D
0x18001415b  xor     edi, edi
0x18001415d  lea     r14, [rbp+0C0h+TokenInformation]
0x180014161  mov     rcx, [r14]; pSid
0x180014164  xor     ebx, ebx
0x180014166  call    cs:__imp_GetLengthSid
0x18001416c  mov     edx, eax; uBytes
0x18001416e  xor     ecx, ecx; uFlags
0x180014170  mov     r15d, eax
0x180014173  call    cs:__imp_LocalAlloc
0x180014179  mov     rsi, rax
0x18001417c  test    rax, rax
0x18001417f  jz      short loc_18001419A
0x180014181  mov     r8, [r14]; pSourceSid
0x180014184  mov     rdx, rax; pDestinationSid
0x180014187  mov     ecx, r15d; nDestinationSidLength
0x18001418a  call    cs:__imp_CopySid
0x180014190  mov     ebx, eax
0x180014192  test    eax, eax
0x180014194  jz      loc_18001445B
0x18001419a  test    rdi, rdi
0x18001419d  jnz     short loc_1800141CA
0x18001419f  jmp     short loc_1800141D2
0x1800141a1  mov     r9d, [rsp+1C0h+TokenInformationLength]; TokenInformationLength
0x1800141a6  lea     rax, [rsp+1C0h+TokenInformationLength]
0x1800141ab  mov     r8, rdi; TokenInformation
0x1800141ae  mov     [rsp+1C0h+ReturnLength], rax; ReturnLength
0x1800141b3  mov     edx, 1; TokenInformationClass
0x1800141b8  mov     rcx, r15; TokenHandle
0x1800141bb  mov     r14, rdi
0x1800141be  call    cs:__imp_GetTokenInformation
0x1800141c4  mov     ebx, eax
0x1800141c6  test    eax, eax
0x1800141c8  jnz     short loc_180014161
0x1800141ca  mov     rcx, rdi; hMem
0x1800141cd  call    freeWithSavedLastError
0x1800141d2  mov     r14, [rsp+1C0h+TokenHandle]
0x1800141d7  test    r14, r14
0x1800141da  jz      short loc_1800141F5
0x1800141dc  call    cs:__imp_GetLastError
0x1800141e2  mov     rcx, r14; hObject
0x1800141e5  mov     edi, eax
0x1800141e7  call    cs:__imp_CloseHandle
0x1800141ed  mov     ecx, edi; dwErrCode
0x1800141ef  call    cs:__imp_SetLastError
0x1800141f5  test    ebx, ebx
0x1800141f7  jz      loc_180014353
0x1800141fd  mov     rcx, rsi; pSid
0x180014200  call    cs:__imp_IsValidSid
0x180014206  test    eax, eax
0x180014208  jz      loc_180014479
0x18001420e  mov     rcx, rsi; pSid
0x180014211  call    cs:__imp_GetSidIdentifierAuthority
0x180014217  mov     rcx, rsi; pSid
0x18001421a  mov     rbx, rax
0x18001421d  call    cs:__imp_GetSidSubAuthorityCount
0x180014223  movzx   edi, byte ptr [rax]
0x180014226  mov     eax, [r12]
0x18001422a  lea     ecx, [rdi+rdi*2]
0x18001422d  lea     ecx, ds:1Ch[rcx*4]
0x180014234  cmp     eax, ecx
0x180014236  jb      loc_18001446A
0x18001423c  test    r13, r13
0x18001423f  jz      loc_18001446A
0x180014245  mov     edx, eax; cchDest
0x180014247  mov     [rsp+1C0h+pcchRemaining], rax
0x18001424c  lea     rax, aSLu; "S-%lu-"
0x180014253  mov     dword ptr [rsp+1C0h+var_190], 1
0x18001425b  mov     [rsp+1C0h+pszFormat], rax; pszFormat
0x180014260  lea     r9, [rsp+1C0h+pcchRemaining]; pcchRemaining
0x180014265  xor     r14d, r14d
0x180014268  mov     [rsp+1C0h+ppszDestEnd], r13
0x18001426d  lea     r8, [rsp+1C0h+ppszDestEnd]; ppszDestEnd
0x180014272  mov     [rsp+1C0h+ReturnLength], r14; dwFlags
0x180014277  mov     rcx, r13; pszDest
0x18001427a  call    StringCchPrintfExW
0x18001427f  test    eax, eax
0x180014281  js      loc_1800143B7
0x180014287  movzx   r10d, byte ptr [rbx]
0x18001428b  test    r10b, r10b
0x18001428e  jnz     loc_1800143C8
0x180014294  cmp     [rbx+1], r14b
0x180014298  jnz     loc_1800143C8
0x18001429e  movzx   ecx, byte ptr [rbx+2]
0x1800142a2  lea     r9, [rsp+1C0h+pcchRemaining]; pcchRemaining
0x1800142a7  movzx   eax, byte ptr [rbx+3]
0x1800142ab  lea     r8, [rsp+1C0h+ppszDestEnd]; ppszDestEnd
0x1800142b0  mov     rdx, [rsp+1C0h+pcchRemaining]; cchDest
0x1800142b5  shl     eax, 10h
0x1800142b8  shl     ecx, 18h
0x1800142bb  add     ecx, eax
0x1800142bd  movzx   eax, byte ptr [rbx+4]
0x1800142c1  shl     eax, 8
0x1800142c4  add     ecx, eax
0x1800142c6  movzx   eax, byte ptr [rbx+5]
0x1800142ca  add     ecx, eax
0x1800142cc  lea     rax, aLu_0; "%lu"
0x1800142d3  mov     dword ptr [rsp+1C0h+var_190], ecx
0x1800142d7  mov     rcx, [rsp+1C0h+ppszDestEnd]; pszDest
0x1800142dc  mov     [rsp+1C0h+pszFormat], rax; pszFormat
0x1800142e1  mov     [rsp+1C0h+ReturnLength], r14; dwFlags
0x1800142e6  call    StringCchPrintfExW
0x1800142eb  test    eax, eax
0x1800142ed  js      loc_1800143B7
0x1800142f3  mov     ebx, r14d
0x1800142f6  lea     r15, aLu; "-%lu"
0x1800142fd  cmp     ebx, edi
0x1800142ff  jnb     short loc_18001433D
0x180014301  mov     edx, ebx; nSubAuthority
0x180014303  mov     rcx, rsi; pSid
0x180014306  call    cs:__imp_GetSidSubAuthority
0x18001430c  mov     rdx, [rsp+1C0h+pcchRemaining]; cchDest
0x180014311  lea     r9, [rsp+1C0h+pcchRemaining]; pcchRemaining
0x180014316  lea     r8, [rsp+1C0h+ppszDestEnd]; ppszDestEnd
0x18001431b  mov     ecx, [rax]
0x18001431d  mov     dword ptr [rsp+1C0h+var_190], ecx
0x180014321  mov     rcx, [rsp+1C0h+ppszDestEnd]; pszDest
0x180014326  mov     [rsp+1C0h+pszFormat], r15; pszFormat
0x18001432b  mov     [rsp+1C0h+ReturnLength], r14; dwFlags
0x180014330  call    StringCchPrintfExW
0x180014335  test    eax, eax
0x180014337  js      short loc_1800143B7
0x180014339  inc     ebx
0x18001433b  jmp     short loc_1800142FD
0x18001433d  mov     rax, [rsp+1C0h+pcchRemaining]
0x180014342  test    rax, rax
0x180014345  jz      short loc_18001434A
0x180014347  dec     rax
0x18001434a  sub     [r12], eax
0x18001434e  mov     ebx, 1
0x180014353  mov     r15, [rsp+1C0h+var_30]
0x18001435b  mov     r14, [rsp+1C0h+var_28]
0x180014363  test    rsi, rsi
0x180014366  jz      short loc_180014381
0x180014368  call    cs:__imp_GetLastError
0x18001436e  mov     rcx, rsi; hMem
0x180014371  mov     edi, eax
0x180014373  call    cs:__imp_LocalFree
0x180014379  mov     ecx, edi; dwErrCode
0x18001437b  call    cs:__imp_SetLastError
0x180014381  mov     rdi, [rsp+1C0h+var_20]
0x180014389  mov     eax, ebx
0x18001438b  mov     rbx, [rsp+1C0h+arg_10]
0x180014393  mov     rsi, [rsp+1C0h+var_18]
0x18001439b  mov     rcx, [rbp+0C0h+var_40]
0x1800143a2  xor     rcx, rsp; StackCookie
0x1800143a5  call    __security_check_cookie
0x1800143aa  add     rsp, 1B0h
0x1800143b1  pop     r13
0x1800143b3  pop     r12
0x1800143b5  pop     rbp
0x1800143b6  retn
0x1800143b7  mov     ecx, eax; dwErrCode
0x1800143b9  call    cs:__imp_SetLastError
0x1800143bf  mov     ebx, r14d
0x1800143c2  jmp     short loc_180014353
0x1800143c4  xor     eax, eax
0x1800143c6  jmp     short loc_18001439B
0x1800143c8  movzx   eax, byte ptr [rbx+5]
0x1800143cc  movzx   ecx, byte ptr [rbx+4]
0x1800143d0  movzx   edx, byte ptr [rbx+3]
0x1800143d4  movzx   r8d, byte ptr [rbx+2]
0x1800143d9  movzx   r9d, byte ptr [rbx+1]
0x1800143de  mov     [rsp+1C0h+var_168], eax
0x1800143e2  lea     rax, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x1800143e9  mov     [rsp+1C0h+var_170], ecx
0x1800143ed  mov     rcx, [rsp+1C0h+ppszDestEnd]; pszDest
0x1800143f2  mov     [rsp+1C0h+var_178], edx
0x1800143f6  mov     rdx, [rsp+1C0h+pcchRemaining]; cchDest
0x1800143fb  mov     [rsp+1C0h+var_180], r8d
0x180014400  lea     r8, [rsp+1C0h+ppszDestEnd]; ppszDestEnd
0x180014405  mov     [rsp+1C0h+var_188], r9d
0x18001440a  lea     r9, [rsp+1C0h+pcchRemaining]; pcchRemaining
0x18001440f  mov     dword ptr [rsp+1C0h+var_190], r10d
0x180014414  mov     [rsp+1C0h+pszFormat], rax; pszFormat
0x180014419  mov     [rsp+1C0h+ReturnLength], r14; dwFlags
0x18001441e  call    StringCchPrintfExW
0x180014423  test    eax, eax
0x180014425  jns     loc_1800142F3
0x18001442b  jmp     short loc_1800143B7
0x18001442d  xor     esi, esi
0x18001442f  call    cs:__imp_GetLastError
0x180014435  cmp     eax, 7Ah ; 'z'
0x180014438  jnz     loc_1800141D2
0x18001443e  mov     edx, [rsp+1C0h+TokenInformationLength]; uBytes
0x180014442  xor     ecx, ecx; uFlags
0x180014444  call    cs:__imp_LocalAlloc
0x18001444a  mov     rdi, rax
0x18001444d  test    rax, rax
0x180014450  jz      loc_1800141D2
0x180014456  jmp     loc_1800141A1
0x18001445b  mov     rcx, rsi; hMem
0x18001445e  call    freeWithSavedLastError
0x180014463  xor     esi, esi
0x180014465  jmp     loc_18001419A
0x18001446a  mov     [r12], ecx
0x18001446e  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180014473  call    cs:__imp_SetLastError
0x180014479  xor     ebx, ebx
0x18001447b  jmp     loc_180014353
```
