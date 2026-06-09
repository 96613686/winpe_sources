# IsTokenMember(void *,WELL_KNOWN_SID_TYPE,int *)

- ea: `0x18009d2c4`
- end: `0x18009d54d`
- name: `?IsTokenMember@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@PEAH@Z`
- size: `649`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, WELL_KNOWN_SID_TYPE WellKnownSidType, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009d7b8`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009d2c4`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18009d427`
- `KERNEL32!CloseHandle` at `0x18009d50e`
- `KERNEL32!CloseHandle` at `0x18009d427`
- `KERNEL32!CloseHandle` at `0x18009d50e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d493`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d4c9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d493`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d4c9`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009d453`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009d453`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009d36f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009d36f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009d3c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009d3c1`

## string_xrefs

- `0x18009d2ee`: `IsTokenMember`

## pseudocode

```c
__int64 __fastcall IsTokenMember(HANDLE TokenHandle, WELL_KNOWN_SID_TYPE WellKnownSidType, int *a3)
{
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v7; // rcx
  __int16 v8; // ax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rcx
  WINBOOL IsMember; // [rsp+30h] [rbp-79h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-71h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-69h] BYREF
  int TokenInformation; // [rsp+44h] [rbp-65h] BYREF
  int v19; // [rsp+48h] [rbp-61h] BYREF
  __int16 v20; // [rsp+4Ch] [rbp-5Dh]
  __int16 v21; // [rsp+4Eh] [rbp-5Bh]
  DWORD cbSid[4]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE pSid[80]; // [rsp+90h] [rbp-19h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v19, "IsTokenMember", 0x11Au, 1u);
  IsMember = 0;
  memset_0(pSid, 0, 0x48u);
  cbSid[0] = 72;
  hObject = 0;
  TokenInformation = 1;
  ReturnLength = 0;
  if ( !TokenHandle )
  {
    LastFailureAsHRESULT = -2147024809;
    v21 = 291;
    v19 = -2147024809;
    goto LABEL_24;
  }
  v19 = 0;
  v20 = 291;
  if ( !CreateWellKnownSid(WellKnownSidType, 0, pSid, cbSid) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v19 = LastFailureAsHRESULT;
    v8 = 293;
LABEL_5:
    v21 = v8;
    goto LABEL_22;
  }
  v19 = 0;
  v20 = 293;
  if ( !GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, &ReturnLength) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v19 = LastFailureAsHRESULT;
    v8 = 294;
    goto LABEL_5;
  }
  v20 = 294;
  v8 = 295;
  if ( ReturnLength != 4 )
  {
    LastFailureAsHRESULT = -2147467259;
    v19 = -2147467259;
    goto LABEL_5;
  }
  v19 = 0;
  v20 = 295;
  if ( TokenInformation == 2 )
  {
    if ( !CheckTokenMembership(TokenHandle, pSid, &IsMember) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
      v19 = LastFailureAsHRESULT;
      v8 = 303;
      goto LABEL_5;
    }
    v12 = 303;
  }
  else
  {
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( !DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
      v19 = LastFailureAsHRESULT;
      v8 = 298;
      goto LABEL_5;
    }
    v19 = 0;
    v20 = 298;
    if ( !CheckTokenMembership(hObject, pSid, &IsMember) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
      v19 = LastFailureAsHRESULT;
      v8 = 299;
      goto LABEL_5;
    }
    v12 = 299;
  }
  LastFailureAsHRESULT = 0;
  v20 = v12;
  v19 = 0;
  *a3 = IsMember;
LABEL_22:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
LABEL_24:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v19);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18009d2c4  mov     [rsp-8+arg_18], rbx
0x18009d2c9  push    rbp
0x18009d2ca  push    rsi
0x18009d2cb  push    rdi
0x18009d2cc  lea     rbp, [rsp-47h]
0x18009d2d1  sub     rsp, 0F0h
0x18009d2d8  mov     rax, cs:__security_cookie
0x18009d2df  xor     rax, rsp
0x18009d2e2  mov     [rbp+57h+var_20], rax
0x18009d2e6  mov     rsi, r8
0x18009d2e9  mov     edi, edx
0x18009d2eb  mov     rbx, rcx
0x18009d2ee  lea     rdx, aIstokenmember; "IsTokenMember"
0x18009d2f5  mov     r8d, 11Ah; unsigned __int16
0x18009d2fb  lea     rcx, [rbp+57h+var_B8]; this
0x18009d2ff  mov     r9d, 1; unsigned __int16
0x18009d305  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18009d30a  xor     edx, edx; Val
0x18009d30c  mov     [rbp+57h+IsMember], 0
0x18009d313  lea     rcx, [rbp+57h+pSid]; void *
0x18009d317  lea     r8d, [rdx+48h]; Size
0x18009d31b  call    memset_0
0x18009d320  mov     [rbp+57h+cbSid], 48h ; 'H'
0x18009d327  mov     eax, 123h
0x18009d32c  mov     [rbp+57h+hObject], 0
0x18009d334  mov     [rbp+57h+TokenInformation], 1
0x18009d33b  mov     [rbp+57h+var_C0], 0
0x18009d342  test    rbx, rbx
0x18009d345  jnz     short loc_18009D358
0x18009d347  mov     ebx, 80070057h
0x18009d34c  mov     [rbp+57h+var_B2], ax
0x18009d350  mov     [rbp+57h+var_B8], ebx
0x18009d353  jmp     loc_18009D522
0x18009d358  lea     r9, [rbp+57h+cbSid]; cbSid
0x18009d35c  mov     [rbp+57h+var_B8], 0
0x18009d363  lea     r8, [rbp+57h+pSid]; pSid
0x18009d367  mov     [rbp+57h+var_B4], ax
0x18009d36b  xor     edx, edx; DomainSid
0x18009d36d  mov     ecx, edi; WellKnownSidType
0x18009d36f  call    cs:__imp_CreateWellKnownSid
0x18009d376  nop     dword ptr [rax+rax+00h]
0x18009d37b  test    eax, eax
0x18009d37d  jnz     short loc_18009D397
0x18009d37f  call    GetLastFailureAsHRESULT
0x18009d384  mov     ebx, eax
0x18009d386  mov     [rbp+57h+var_B8], eax
0x18009d389  mov     eax, 125h
0x18009d38e  mov     [rbp+57h+var_B2], ax
0x18009d392  jmp     loc_18009D500
0x18009d397  mov     r9d, 4; TokenInformationLength
0x18009d39d  mov     [rbp+57h+var_B8], 0
0x18009d3a4  mov     eax, 125h
0x18009d3a9  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18009d3ad  mov     [rbp+57h+var_B4], ax
0x18009d3b1  mov     rcx, rbx; TokenHandle
0x18009d3b4  lea     rax, [rbp+57h+var_C0]
0x18009d3b8  lea     edx, [r9+4]; TokenInformationClass
0x18009d3bc  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18009d3c1  call    cs:__imp_GetTokenInformation
0x18009d3c8  nop     dword ptr [rax+rax+00h]
0x18009d3cd  test    eax, eax
0x18009d3cf  jnz     short loc_18009D3E2
0x18009d3d1  call    GetLastFailureAsHRESULT
0x18009d3d6  mov     ebx, eax
0x18009d3d8  mov     [rbp+57h+var_B8], eax
0x18009d3db  mov     eax, 126h
0x18009d3e0  jmp     short loc_18009D38E
0x18009d3e2  cmp     [rbp+57h+var_C0], 4
0x18009d3e6  mov     eax, 126h
0x18009d3eb  mov     [rbp+57h+var_B4], ax
0x18009d3ef  mov     eax, 127h
0x18009d3f4  jz      short loc_18009D400
0x18009d3f6  mov     ebx, 80004005h
0x18009d3fb  mov     [rbp+57h+var_B8], ebx
0x18009d3fe  jmp     short loc_18009D38E
0x18009d400  mov     edi, 2
0x18009d405  mov     [rbp+57h+var_B8], 0
0x18009d40c  mov     [rbp+57h+var_B4], ax
0x18009d410  cmp     [rbp+57h+TokenInformation], edi
0x18009d413  jz      loc_18009D4BE
0x18009d419  mov     rcx, [rbp+57h+hObject]; hObject
0x18009d41d  lea     rax, [rcx-1]
0x18009d421  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009d425  ja      short loc_18009D43B
0x18009d427  call    cs:__imp_CloseHandle
0x18009d42e  nop     dword ptr [rax+rax+00h]
0x18009d433  mov     [rbp+57h+hObject], 0
0x18009d43b  lea     rax, [rbp+57h+hObject]
0x18009d43f  mov     r9d, edi; ImpersonationLevel
0x18009d442  mov     [rsp+100h+phNewToken], rax; phNewToken
0x18009d447  xor     r8d, r8d; lpTokenAttributes
0x18009d44a  xor     edx, edx; dwDesiredAccess
0x18009d44c  mov     dword ptr [rsp+100h+ReturnLength], edi; TokenType
0x18009d450  mov     rcx, rbx; hExistingToken
0x18009d453  call    cs:__imp_DuplicateTokenEx
0x18009d45a  nop     dword ptr [rax+rax+00h]
0x18009d45f  test    eax, eax
0x18009d461  jnz     short loc_18009D477
0x18009d463  call    GetLastFailureAsHRESULT
0x18009d468  mov     ebx, eax
0x18009d46a  mov     [rbp+57h+var_B8], eax
0x18009d46d  mov     eax, 12Ah
0x18009d472  jmp     loc_18009D38E
0x18009d477  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x18009d47b  lea     r8, [rbp+57h+IsMember]; IsMember
0x18009d47f  mov     eax, 12Ah
0x18009d484  mov     [rbp+57h+var_B8], 0
0x18009d48b  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18009d48f  mov     [rbp+57h+var_B4], ax
0x18009d493  call    cs:__imp_CheckTokenMembership
0x18009d49a  nop     dword ptr [rax+rax+00h]
0x18009d49f  test    eax, eax
0x18009d4a1  jnz     short loc_18009D4B7
0x18009d4a3  call    GetLastFailureAsHRESULT
0x18009d4a8  mov     ebx, eax
0x18009d4aa  mov     [rbp+57h+var_B8], eax
0x18009d4ad  mov     eax, 12Bh
0x18009d4b2  jmp     loc_18009D38E
0x18009d4b7  mov     eax, 12Bh
0x18009d4bc  jmp     short loc_18009D4F2
0x18009d4be  lea     r8, [rbp+57h+IsMember]; IsMember
0x18009d4c2  mov     rcx, rbx; TokenHandle
0x18009d4c5  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18009d4c9  call    cs:__imp_CheckTokenMembership
0x18009d4d0  nop     dword ptr [rax+rax+00h]
0x18009d4d5  test    eax, eax
0x18009d4d7  jnz     short loc_18009D4ED
0x18009d4d9  call    GetLastFailureAsHRESULT
0x18009d4de  mov     ebx, eax
0x18009d4e0  mov     [rbp+57h+var_B8], eax
0x18009d4e3  mov     eax, 12Fh
0x18009d4e8  jmp     loc_18009D38E
0x18009d4ed  mov     eax, 12Fh
0x18009d4f2  xor     ebx, ebx
0x18009d4f4  mov     [rbp+57h+var_B4], ax
0x18009d4f8  mov     eax, [rbp+57h+IsMember]
0x18009d4fb  mov     [rbp+57h+var_B8], ebx
0x18009d4fe  mov     [rsi], eax
0x18009d500  mov     rcx, [rbp+57h+hObject]; hObject
0x18009d504  lea     rdx, [rcx-1]
0x18009d508  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18009d50c  ja      short loc_18009D522
0x18009d50e  call    cs:__imp_CloseHandle
0x18009d515  nop     dword ptr [rax+rax+00h]
0x18009d51a  mov     [rbp+57h+hObject], 0
0x18009d522  lea     rcx, [rbp+57h+var_B8]; this
0x18009d526  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18009d52b  mov     eax, ebx
0x18009d52d  mov     rcx, [rbp+57h+var_20]
0x18009d531  xor     rcx, rsp; StackCookie
0x18009d534  call    __security_check_cookie
0x18009d539  mov     rbx, [rsp+100h+arg_18]
0x18009d541  add     rsp, 0F0h
0x18009d548  pop     rdi
0x18009d549  pop     rsi
0x18009d54a  pop     rbp
0x18009d54b  retn
```
