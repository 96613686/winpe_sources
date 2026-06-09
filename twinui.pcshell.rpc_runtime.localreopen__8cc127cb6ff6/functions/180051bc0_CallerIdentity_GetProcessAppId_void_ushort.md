# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x180051bc0`
- end: `0x1800521dc`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `1564`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180051450`
- `0x1800519e0`
- `0x1802609a0`
- `0x1802cb150`
- `0x18034cc48`
- `0x18045dd6c`

## callees

- `0x1800237c8`
- `0x180051bc0`
- `0x1800521f0`
- `0x18005235c`
- `0x1802c56a0`
- `0x180356edc`
- `0x18035b7f1`
- `0x18038fec8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180051dc8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180052037`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180051dc8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180052037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051df5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051e3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051f80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005207a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051df5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051e3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051f80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005207a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180051be9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180051be9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180051c04`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180051c04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051d3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051d3b`
- `ntdll!NtQueryInformationToken` at `0x180051c3d`
- `ntdll!NtQueryInformationToken` at `0x180051caa`
- `ntdll!NtQueryInformationToken` at `0x180051c3d`
- `ntdll!NtQueryInformationToken` at `0x180051caa`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180052145`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1806edea2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180052145`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1806edea2`
- `ntdll!RtlInitUnicodeString` at `0x180051cd0`
- `ntdll!RtlInitUnicodeString` at `0x180051cd0`
- `ntdll!RtlCompareUnicodeString` at `0x180051cfe`
- `ntdll!RtlCompareUnicodeString` at `0x180051cfe`
- `ntdll!RtlFreeHeap` at `0x180051d22`
- `ntdll!RtlFreeHeap` at `0x180051d22`
- `ntdll!RtlAllocateHeap` at `0x180051c72`
- `ntdll!RtlAllocateHeap` at `0x180051c72`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, wchar_t **a2, unsigned __int16 **a3)
{
  void *v5; // rdx
  signed int LastError; // ebx
  __int64 v7; // rbx
  NTSTATUS InformationToken; // eax
  unsigned __int128 v9; // rax
  ARI *v10; // r14
  int v11; // eax
  unsigned int v12; // ebx
  ARI *v13; // rdi
  void *v14; // rdx
  ARI *v16; // r13
  unsigned __int16 *v17; // rdi
  __int64 v18; // rax
  int v19; // esi
  const wchar_t *v20; // rcx
  wchar_t *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdi
  int v24; // r12d
  __int64 v25; // r12
  unsigned __int64 v26; // rsi
  unsigned int v27; // edi
  void *v28; // rdx
  wchar_t *v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rbx
  _WORD *v34; // rbx
  _WORD *v35; // rdi
  void *v36; // rdx
  unsigned __int16 *v37; // rsi
  __int64 v38; // rax
  int v39; // r13d
  const wchar_t *v40; // rcx
  wchar_t *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rsi
  size_t v44; // rdi
  wchar_t *v45; // r8
  char *v46; // rax
  __int64 v47; // rcx
  ARI *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  _WORD *v51; // rsi
  __int64 v52; // rdi
  void *v53; // rdx
  unsigned int ReturnLength; // [rsp+20h] [rbp-48h]
  ARI *v55[2]; // [rsp+30h] [rbp-38h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  __int128 v57; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  __int64 TokenInformationLength; // [rsp+A0h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+A8h] [rbp+40h] BYREF

  *a2 = 0;
  *(_OWORD *)v55 = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    v7 = -4;
    TokenHandle = (void *)-4LL;
  }
  else
  {
    if ( !OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v10 = v55[0];
        goto LABEL_18;
      }
    }
    v7 = (__int64)TokenHandle;
  }
  LODWORD(TokenInformationLength) = 0;
  InformationToken = NtQueryInformationToken((HANDLE)v7, TokenSecurityAttributes, 0, 0, (PULONG)&TokenInformationLength);
  if ( InformationToken == -1073741789 )
  {
    v9 = (unsigned int)TokenInformationLength * (unsigned __int128)0x10uLL;
    if ( is_mul_ok((unsigned int)TokenInformationLength, 0x10u) )
    {
      *(_QWORD *)&v9 = RtlAllocateHeap(
                         NtCurrentPeb()->ProcessHeap,
                         DWORD2(v9),
                         16LL * (unsigned int)TokenInformationLength);
      v10 = (ARI *)v9;
      if ( (_QWORD)v9 )
      {
        memset_0((void *)v9, 0, (unsigned int)TokenInformationLength);
        v11 = NtQueryInformationToken(
                (HANDLE)v7,
                TokenSecurityAttributes,
                v10,
                TokenInformationLength,
                (PULONG)&TokenInformationLength);
        if ( v11 < 0 )
        {
          LastError = RtlNtStatusToDosErrorNoTeb(v11);
          ARI::Free(v10, v53);
        }
        else
        {
          if ( *((_DWORD *)v10 + 1) )
          {
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
            v12 = 0;
            v57 = 0;
            while ( v12 < *((_DWORD *)v10 + 1) )
            {
              v13 = (ARI *)(*((_QWORD *)v10 + 1) + 40LL * v12);
              if ( !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)v13, 1u) )
              {
                v55[1] = v13;
                v55[0] = v10;
                ARI::Free(0, v14);
                LastError = 0;
                goto LABEL_16;
              }
              ++v12;
            }
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
          LastError = 1168;
        }
        goto LABEL_15;
      }
    }
    else
    {
      v10 = 0;
    }
    ARI::Free(v10, *((void **)&v9 + 1));
    LastError = 8;
  }
  else if ( InformationToken )
  {
    LastError = RtlNtStatusToDosErrorNoTeb(InformationToken);
  }
  else
  {
    LastError = 1359;
  }
LABEL_15:
  v10 = v55[0];
LABEL_16:
  if ( TokenHandle != (void *)-4LL )
    CloseHandle(TokenHandle);
LABEL_18:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023728 || LastError == -2147024891 )
  {
    if ( v10 )
LABEL_50:
      ARI::Free(v10, v5);
    return (unsigned int)LastError;
  }
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)LastError,
      ReturnLength);
    if ( v10 )
      goto LABEL_50;
    return (unsigned int)LastError;
  }
  v16 = v55[1];
  v17 = (unsigned __int16 *)*((_QWORD *)v55[1] + 4);
  v18 = v17[8] >> 1;
  v19 = v18 + 1;
  if ( (_DWORD)v18 == -1 )
  {
    v34 = (_WORD *)(2 * v18);
    memcpy_0(0, *((const void **)v17 + 3), 2 * v18);
    *v34 = 0;
    goto LABEL_43;
  }
  v20 = (const wchar_t *)*((_QWORD *)v17 + 1);
  LODWORD(TokenInformationLength) = *v17 >> 1;
  v21 = wcschr(v20, 0x5Fu);
  TokenHandle = (void *)*((_QWORD *)v17 + 1);
  v22 = ((char *)(v21 + 1) - (_BYTE *)TokenHandle) >> 1;
  v23 = (unsigned int)(v22 + 13);
  v24 = v22 + 14;
  if ( (_DWORD)v22 == -14 )
  {
    memcpy_0(0, TokenHandle, 0x1FFFFFFE4uLL);
    v30 = (unsigned int)(TokenInformationLength - 13);
    MEMORY[0x1FFFFFFE4] = *(_OWORD *)((char *)TokenHandle + 2 * v30);
    MEMORY[0x1FFFFFFEE] = *(_OWORD *)((char *)TokenHandle + 2 * v30 + 10);
    *(_WORD *)(2 * v23) = 0;
    v25 = (unsigned int)(v19 + v24);
    if ( (_DWORD)v25 )
      goto LABEL_30;
    *(_WORD *)(2 * v23) = 33;
    v31 = *((_QWORD *)v16 + 4);
    v32 = *(unsigned __int16 *)(v31 + 16) >> 1;
    if ( ~(_DWORD)v23 >= (unsigned int)(v32 + 1) )
    {
      v33 = 2 * v32;
      memcpy_0((void *)(2LL * (unsigned int)v23 + 2), *(const void **)(v31 + 24), 2 * v32);
      *(_WORD *)(v33 + 2LL * (unsigned int)v23 + 2) = 0;
    }
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLength);
    ARI::ProcessToken::AutoSysAppId::~AutoSysAppId((ARI::ProcessToken::AutoSysAppId *)v55);
    return 2147549183LL;
  }
  v25 = (unsigned int)(v19 + v24);
LABEL_30:
  CoTaskMemFree(0);
  v26 = v25 + 1;
  if ( v25 + 1 < (unsigned __int64)(unsigned int)v25 || (TokenInformationLength = 0, !is_mul_ok(v26, 2u)) )
  {
    v27 = -2147024362;
    goto LABEL_33;
  }
  v29 = (wchar_t *)CoTaskMemAlloc(2 * v26);
  if ( !v29 )
  {
    v27 = -2147024882;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)v27,
      ReturnLength);
    CoTaskMemFree(0);
    if ( v10 )
    {
      ARI::Free(v10, v28);
      return v27;
    }
    return v27;
  }
  if ( v26 <= 0x7FFFFFFF )
  {
    if ( (unsigned int)v25 >= 0x7FFFFFFF )
    {
      *v29 = 0;
    }
    else
    {
      *v29 = 0;
      if ( v26 > 1 )
        StringExHandleFillBehindNullW(v29, 2 * v26, 0x300u);
    }
  }
  else
  {
    *v29 = 0;
  }
  v37 = (unsigned __int16 *)*((_QWORD *)v16 + 4);
  v38 = v37[8] >> 1;
  v39 = v38 + 1;
  if ( (_DWORD)v38 == -1 )
  {
    v35 = (_WORD *)(2 * v38);
    memcpy_0(0, *((const void **)v37 + 3), 2 * v38);
    *v35 = 0;
  }
  else
  {
    v40 = (const wchar_t *)*((_QWORD *)v37 + 1);
    LODWORD(TokenInformationLength) = *v37 >> 1;
    v41 = wcschr(v40, 0x5Fu);
    TokenHandle = (void *)*((_QWORD *)v37 + 1);
    v42 = ((char *)(v41 + 1) - (_BYTE *)TokenHandle) >> 1;
    v43 = (unsigned int)(v42 + 13);
    if ( (unsigned int)v25 < (int)v42 + 14 )
      goto LABEL_53;
    v44 = (unsigned int)v42;
    memcpy_0(v29, TokenHandle, v44 * 2);
    v45 = &v29[v43];
    v46 = (char *)TokenHandle;
    v47 = (unsigned int)(TokenInformationLength - 13);
    *(_OWORD *)&v29[v44] = *(_OWORD *)((char *)TokenHandle + 2 * v47);
    *(_OWORD *)&v29[v44 + 5] = *(_OWORD *)&v46[2 * v47 + 10];
    *v45 = 0;
    if ( (unsigned int)v25 < (int)v43 + v39 + 1 )
    {
LABEL_53:
      v27 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xAC,
              (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
              (const char *)0x7A,
              ReturnLength);
      CoTaskMemFree(v29);
      ARI::ProcessToken::AutoSysAppId::~AutoSysAppId((ARI::ProcessToken::AutoSysAppId *)v55);
      return v27;
    }
    v48 = v55[1];
    *v45 = 33;
    v49 = *((_QWORD *)v48 + 4);
    v50 = *(unsigned __int16 *)(v49 + 16) >> 1;
    if ( (int)v25 - (int)v43 - 1 >= (unsigned int)(v50 + 1) )
    {
      v51 = v45 + 1;
      v52 = v50;
      memcpy_0(v45 + 1, *(const void **)(v49 + 24), 2 * v50);
      v51[v52] = 0;
    }
  }
  *a2 = v29;
  CoTaskMemFree(0);
  if ( v10 )
    ARI::Free(v10, v36);
  return 0;
}

```

## disassembly

```asm
0x180051bc0  push    rbp
0x180051bc2  push    rbx
0x180051bc3  push    rdi
0x180051bc4  push    r12
0x180051bc6  push    r14
0x180051bc8  push    r15
0x180051bca  mov     rbp, rsp
0x180051bcd  sub     rsp, 68h
0x180051bd1  xor     r12d, r12d
0x180051bd4  xorps   xmm0, xmm0
0x180051bd7  mov     [rdx], r12
0x180051bda  mov     r15, rdx
0x180051bdd  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180051be2  mov     [rbp+TokenHandle], r12
0x180051be6  mov     rbx, rcx
0x180051be9  call    cs:__imp_GetCurrentProcess
0x180051bef  cmp     rbx, rax
0x180051bf2  jz      loc_1800521B0
0x180051bf8  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180051bfc  mov     edx, 8; DesiredAccess
0x180051c01  mov     rcx, rbx; ProcessHandle
0x180051c04  call    cs:__imp_OpenProcessToken
0x180051c0a  test    eax, eax
0x180051c0c  jnz     short loc_180051C1E
0x180051c0e  call    cs:__imp_GetLastError
0x180051c14  mov     ebx, eax
0x180051c16  test    eax, eax
0x180051c18  jnz     loc_1800521A7
0x180051c1e  mov     rbx, [rbp+TokenHandle]
0x180051c22  lea     rax, [rbp+TokenInformationLength]
0x180051c26  mov     dword ptr [rbp+TokenInformationLength], r12d
0x180051c2a  xor     r9d, r9d; TokenInformationLength
0x180051c2d  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x180051c32  xor     r8d, r8d; TokenInformation
0x180051c35  mov     edx, 27h ; '''; TokenInformationClass
0x180051c3a  mov     rcx, rbx; TokenHandle
0x180051c3d  call    cs:__imp_NtQueryInformationToken
0x180051c43  cmp     eax, 0C0000023h
0x180051c48  jnz     loc_1800521C0
0x180051c4e  mov     ecx, dword ptr [rbp+TokenInformationLength]
0x180051c51  mov     eax, 10h
0x180051c56  mul     rcx
0x180051c59  test    rdx, rdx
0x180051c5c  jnz     loc_180051D6F
0x180051c62  mov     rcx, gs:60h
0x180051c6b  mov     r8, rax; Size
0x180051c6e  mov     rcx, [rcx+30h]; HeapHandle
0x180051c72  call    cs:__imp_RtlAllocateHeap
0x180051c78  mov     r14, rax
0x180051c7b  test    rax, rax
0x180051c7e  jz      loc_180051D72
0x180051c84  mov     r8d, dword ptr [rbp+TokenInformationLength]; Size
0x180051c88  xor     edx, edx; Val
0x180051c8a  mov     rcx, rax; void *
0x180051c8d  call    memset_0
0x180051c92  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x180051c96  lea     rax, [rbp+TokenInformationLength]
0x180051c9a  mov     r8, r14; TokenInformation
0x180051c9d  mov     qword ptr [rsp+68h+ReturnLength], rax; unsigned int
0x180051ca2  mov     edx, 27h ; '''; TokenInformationClass
0x180051ca7  mov     rcx, rbx; TokenHandle
0x180051caa  call    cs:__imp_NtQueryInformationToken
0x180051cb0  test    eax, eax
0x180051cb2  js      loc_180052143
0x180051cb8  cmp     [r14+4], r12d
0x180051cbc  jbe     short loc_180051D10
0x180051cbe  xorps   xmm0, xmm0
0x180051cc1  lea     rdx, SourceString; "WIN://SYSAPPID"
0x180051cc8  lea     rcx, [rbp+DestinationString]; DestinationString
0x180051ccc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180051cd0  call    cs:__imp_RtlInitUnicodeString
0x180051cd6  xorps   xmm0, xmm0
0x180051cd9  mov     ebx, r12d
0x180051cdc  movups  [rbp+var_18], xmm0
0x180051ce0  cmp     ebx, [r14+4]
0x180051ce4  jnb     short loc_180051D10
0x180051ce6  mov     eax, ebx
0x180051ce8  mov     r8b, 1; CaseInsensitive
0x180051ceb  lea     rcx, [rax+rax*4]
0x180051cef  mov     rax, [r14+8]
0x180051cf3  lea     rdi, [rax+rcx*8]
0x180051cf7  mov     rdx, rdi; String2
0x180051cfa  lea     rcx, [rbp+DestinationString]; String1
0x180051cfe  call    cs:__imp_RtlCompareUnicodeString
0x180051d04  test    eax, eax
0x180051d06  jz      loc_180051F9F
0x180051d0c  inc     ebx
0x180051d0e  jmp     short loc_180051CE0
0x180051d10  mov     rcx, gs:60h
0x180051d19  mov     r8, r14; P
0x180051d1c  xor     edx, edx; Flags
0x180051d1e  mov     rcx, [rcx+30h]; HeapHandle
0x180051d22  call    cs:__imp_RtlFreeHeap
0x180051d28  mov     ebx, 490h
0x180051d2d  mov     r14, [rbp+var_38]
0x180051d31  mov     rcx, [rbp+TokenHandle]; hObject
0x180051d35  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x180051d39  jz      short loc_180051D41
0x180051d3b  call    cs:__imp_CloseHandle
0x180051d41  test    ebx, ebx
0x180051d43  jle     short loc_180051D4E
0x180051d45  movzx   ebx, bx
0x180051d48  or      ebx, 80070000h
0x180051d4e  cmp     ebx, 80070490h
0x180051d54  jnz     short loc_180051D81
0x180051d56  test    r14, r14
0x180051d59  jnz     loc_180051FD7
0x180051d5f  mov     eax, ebx
0x180051d61  add     rsp, 68h
0x180051d65  pop     r15
0x180051d67  pop     r14
0x180051d69  pop     r12
0x180051d6b  pop     rdi
0x180051d6c  pop     rbx
0x180051d6d  pop     rbp
0x180051d6e  retn
0x180051d6f  mov     r14, r12
0x180051d72  mov     rcx, r14; this
0x180051d75  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180051d7a  mov     ebx, 8
0x180051d7f  jmp     short loc_180051D2D
0x180051d81  cmp     ebx, 80070005h
0x180051d87  jz      short loc_180051D56
0x180051d89  test    ebx, ebx
0x180051d8b  js      loc_180051FB6
0x180051d91  mov     [rsp+68h+arg_18], rsi
0x180051d99  mov     [rsp+68h+var_8], r13
0x180051d9e  mov     r13, [rbp+var_38+8]
0x180051da2  mov     rdi, [r13+20h]
0x180051da6  movzx   eax, word ptr [rdi+10h]
0x180051daa  shr     eax, 1
0x180051dac  lea     esi, [rax+1]
0x180051daf  test    esi, esi
0x180051db1  jz      loc_180051F13
0x180051db7  movzx   eax, word ptr [rdi]
0x180051dba  mov     edx, 5Fh ; '_'; Ch
0x180051dbf  mov     rcx, [rdi+8]; Str
0x180051dc3  shr     eax, 1
0x180051dc5  mov     dword ptr [rbp+TokenInformationLength], eax
0x180051dc8  call    cs:__imp_wcschr
0x180051dce  mov     rcx, [rdi+8]
0x180051dd2  add     rax, 2
0x180051dd6  sub     rax, rcx
0x180051dd9  mov     [rbp+TokenHandle], rcx
0x180051ddd  sar     rax, 1
0x180051de0  lea     edi, [rax+0Dh]
0x180051de3  lea     r12d, [rdi+1]
0x180051de7  test    r12d, r12d
0x180051dea  jz      loc_180051E8F
0x180051df0  add     r12d, esi
0x180051df3  xor     ecx, ecx; pv
0x180051df5  call    cs:__imp_CoTaskMemFree
0x180051dfb  mov     eax, r12d
0x180051dfe  lea     rsi, [r12+1]
0x180051e03  cmp     rsi, rax
0x180051e06  jb      short loc_180051E1D
0x180051e08  mov     eax, 2
0x180051e0d  mov     [rbp+TokenInformationLength], 0
0x180051e15  mul     rsi
0x180051e18  test    rdx, rdx
0x180051e1b  jz      short loc_180051E5D
0x180051e1d  mov     edi, 80070216h
0x180051e22  xor     ebx, ebx
0x180051e24  mov     rcx, [rbp+30h]; this
0x180051e28  lea     r8, aOnecoreShellLi_2; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180051e2f  mov     r9d, edi; char *
0x180051e32  mov     edx, 0ABh; void *
0x180051e37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051e3c  mov     rcx, rbx; pv
0x180051e3f  call    cs:__imp_CoTaskMemFree
0x180051e45  test    r14, r14
0x180051e48  jz      loc_180052089
0x180051e4e  mov     rcx, r14; this
0x180051e51  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180051e56  mov     eax, edi
0x180051e58  jmp     loc_180051F8D
0x180051e5d  mov     rcx, rax; cb
0x180051e60  call    cs:__imp_CoTaskMemAlloc
0x180051e66  mov     rbx, rax
0x180051e69  xor     edi, edi
0x180051e6b  test    rbx, rbx
0x180051e6e  mov     eax, 8007000Eh
0x180051e73  cmovz   edi, eax
0x180051e76  jz      short loc_180051E24
0x180051e78  cmp     rsi, 7FFFFFFFh
0x180051e7f  jbe     loc_18005215A
0x180051e85  xor     eax, eax
0x180051e87  mov     [rbx], ax
0x180051e8a  jmp     loc_18005200F
0x180051e8f  mov     eax, eax
0x180051e91  mov     rdx, rcx; Src
0x180051e94  xor     ecx, ecx; void *
0x180051e96  lea     rbx, [rax+rax]
0x180051e9a  mov     r8, rbx; Size
0x180051e9d  call    memcpy_0
0x180051ea2  mov     rcx, [rbp+TokenInformationLength]
0x180051ea6  mov     rax, [rbp+TokenHandle]
0x180051eaa  add     ecx, 0FFFFFFF3h
0x180051ead  mov     r8d, edi
0x180051eb0  movups  xmm0, xmmword ptr [rax+rcx*2]
0x180051eb4  movups  xmmword ptr [rbx], xmm0
0x180051eb7  movups  xmm1, xmmword ptr [rax+rcx*2+0Ah]
0x180051ebc  xor     eax, eax
0x180051ebe  movups  xmmword ptr [rbx+0Ah], xmm1
0x180051ec2  mov     ds:0[rdi*2], ax
0x180051eca  add     r12d, esi
0x180051ecd  jnz     loc_180051DF3
0x180051ed3  mov     word ptr ds:0[rdi*2], 21h ; '!'
0x180051edd  not     edi
0x180051edf  mov     rdx, [r13+20h]
0x180051ee3  movzx   ecx, word ptr [rdx+10h]
0x180051ee7  shr     ecx, 1
0x180051ee9  lea     eax, [rcx+1]
0x180051eec  cmp     edi, eax
0x180051eee  jb      short loc_180051F29
0x180051ef0  mov     rdx, [rdx+18h]; Src
0x180051ef4  lea     rdi, ds:2[r8*2]
0x180051efc  lea     rbx, [rcx+rcx]
0x180051f00  mov     rcx, rdi; void *
0x180051f03  mov     r8, rbx; Size
0x180051f06  call    memcpy_0
0x180051f0b  xor     eax, eax
0x180051f0d  mov     [rbx+rdi], ax
0x180051f11  jmp     short loc_180051F29
0x180051f13  mov     rdx, [rdi+18h]; Src
0x180051f17  lea     rbx, [rax+rax]
0x180051f1b  mov     r8, rbx; Size
0x180051f1e  xor     ecx, ecx; void *
0x180051f20  call    memcpy_0
0x180051f25  mov     [rbx], r12w
0x180051f29  mov     rcx, [rbp+30h]; this
0x180051f2d  lea     r8, aOnecoreShellLi_2; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180051f34  mov     r9d, 8000FFFFh; char *
0x180051f3a  mov     edx, 0A8h; void *
0x180051f3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051f44  lea     rcx, [rbp+var_38]; this
0x180051f48  call    ??1AutoSysAppId@ProcessToken@ARI@@QEAA@XZ; ARI::ProcessToken::AutoSysAppId::~AutoSysAppId(void)
0x180051f4d  mov     rsi, [rsp+68h+arg_18]
0x180051f55  mov     eax, 8000FFFFh
0x180051f5a  mov     r13, [rsp+68h+var_8]
0x180051f5f  jmp     loc_180051D61
0x180051f64  mov     rdx, [rsi+18h]; Src
0x180051f68  lea     rdi, [rax+rax]
0x180051f6c  mov     r8, rdi; Size
0x180051f6f  xor     ecx, ecx; void *
0x180051f71  call    memcpy_0
0x180051f76  xor     eax, eax
0x180051f78  mov     [rdi], ax
0x180051f7b  xor     ecx, ecx; pv
0x180051f7d  mov     [r15], rbx
0x180051f80  call    cs:__imp_CoTaskMemFree
0x180051f86  test    r14, r14
0x180051f89  jnz     short loc_180051FE4
0x180051f8b  xor     eax, eax
0x180051f8d  mov     rsi, [rsp+68h+arg_18]
0x180051f95  mov     r13, [rsp+68h+var_8]
0x180051f9a  jmp     loc_180051D61
0x180051f9f  xor     ecx, ecx; this
0x180051fa1  mov     [rbp+var_38+8], rdi
0x180051fa5  mov     [rbp+var_38], r14
0x180051fa9  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180051fae  mov     ebx, r12d
0x180051fb1  jmp     loc_180051D31
0x180051fb6  mov     rcx, [rbp+30h]; this
0x180051fba  lea     r8, aOnecoreShellLi_2; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180051fc1  mov     r9d, ebx; char *
0x180051fc4  mov     edx, 0A5h; void *
0x180051fc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051fce  test    r14, r14
0x180051fd1  jz      loc_180051D5F
0x180051fd7  mov     rcx, r14; this
0x180051fda  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180051fdf  jmp     loc_180051D5F
0x180051fe4  mov     rcx, r14; this
0x180051fe7  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180051fec  jmp     short loc_180051F8B
0x180051fee  test    r8, r8
0x180051ff1  lea     rcx, [r9-2]
0x180051ff5  lea     r11, [r10-1]
0x180051ff9  cmovnz  rcx, r9
0x180051ffd  cmovnz  r11, r10
0x180052001  xor     eax, eax
0x180052003  mov     [rcx], ax
0x180052006  test    r8, r8
0x180052009  jnz     loc_18005211E
0x18005200f  mov     rsi, [r13+20h]
0x180052013  movzx   eax, word ptr [rsi+10h]
0x180052017  shr     eax, 1
0x180052019  lea     r13d, [rax+1]
0x18005201d  test    r13d, r13d
0x180052020  jz      loc_180051F64
0x180052026  movzx   eax, word ptr [rsi]
0x180052029  mov     edx, 5Fh ; '_'; Ch
0x18005202e  mov     rcx, [rsi+8]; Str
0x180052032  shr     eax, 1
0x180052034  mov     dword ptr [rbp+TokenInformationLength], eax
0x180052037  call    cs:__imp_wcschr
0x18005203d  mov     rcx, [rsi+8]
0x180052041  add     rax, 2
0x180052045  sub     rax, rcx
  ... truncated ...
```
