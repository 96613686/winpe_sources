# IsTokenMember(void *,WELL_KNOWN_SID_TYPE,int *)

- ea: `0x180098d68`
- end: `0x180098fc6`
- name: `?IsTokenMember@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@PEAH@Z`
- size: `606`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, WELL_KNOWN_SID_TYPE WellKnownSidType, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800991f4`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x180098d68`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180098ebf`
- `KERNEL32!CloseHandle` at `0x180098f8e`
- `KERNEL32!CloseHandle` at `0x180098ebf`
- `KERNEL32!CloseHandle` at `0x180098f8e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098f1f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098f4f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098f1f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098f4f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180098ee5`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180098ee5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098e13`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098e13`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098e5f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098e5f`

## string_xrefs

- `0x180098d92`: `IsTokenMember`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v19, "IsTokenMember", 282, 1);
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
0x180098d68  mov     [rsp-8+arg_18], rbx
0x180098d6d  push    rbp
0x180098d6e  push    rsi
0x180098d6f  push    rdi
0x180098d70  lea     rbp, [rsp-47h]
0x180098d75  sub     rsp, 0F0h
0x180098d7c  mov     rax, cs:__security_cookie
0x180098d83  xor     rax, rsp
0x180098d86  mov     [rbp+57h+var_20], rax
0x180098d8a  mov     rsi, r8
0x180098d8d  mov     edi, edx
0x180098d8f  mov     rbx, rcx
0x180098d92  lea     rdx, aIstokenmember; "IsTokenMember"
0x180098d99  mov     r8d, 11Ah; unsigned __int16
0x180098d9f  lea     rcx, [rbp+57h+var_B8]; this
0x180098da3  mov     r9d, 1; unsigned __int16
0x180098da9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180098dae  xor     edx, edx; Val
0x180098db0  mov     [rbp+57h+IsMember], 0
0x180098db7  lea     rcx, [rbp+57h+pSid]; void *
0x180098dbb  lea     r8d, [rdx+48h]; Size
0x180098dbf  call    memset_0
0x180098dc4  mov     [rbp+57h+cbSid], 48h ; 'H'
0x180098dcb  mov     eax, 123h
0x180098dd0  mov     [rbp+57h+hObject], 0
0x180098dd8  mov     [rbp+57h+TokenInformation], 1
0x180098ddf  mov     [rbp+57h+var_C0], 0
0x180098de6  test    rbx, rbx
0x180098de9  jnz     short loc_180098DFC
0x180098deb  mov     ebx, 80070057h
0x180098df0  mov     [rbp+57h+var_B2], ax
0x180098df4  mov     [rbp+57h+var_B8], ebx
0x180098df7  jmp     loc_180098F9C
0x180098dfc  lea     r9, [rbp+57h+cbSid]; cbSid
0x180098e00  mov     [rbp+57h+var_B8], 0
0x180098e07  lea     r8, [rbp+57h+pSid]; pSid
0x180098e0b  mov     [rbp+57h+var_B4], ax
0x180098e0f  xor     edx, edx; DomainSid
0x180098e11  mov     ecx, edi; WellKnownSidType
0x180098e13  call    cs:__imp_CreateWellKnownSid
0x180098e19  test    eax, eax
0x180098e1b  jnz     short loc_180098E35
0x180098e1d  call    GetLastFailureAsHRESULT
0x180098e22  mov     ebx, eax
0x180098e24  mov     [rbp+57h+var_B8], eax
0x180098e27  mov     eax, 125h
0x180098e2c  mov     [rbp+57h+var_B2], ax
0x180098e30  jmp     loc_180098F80
0x180098e35  mov     r9d, 4; TokenInformationLength
0x180098e3b  mov     [rbp+57h+var_B8], 0
0x180098e42  mov     eax, 125h
0x180098e47  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180098e4b  mov     [rbp+57h+var_B4], ax
0x180098e4f  mov     rcx, rbx; TokenHandle
0x180098e52  lea     rax, [rbp+57h+var_C0]
0x180098e56  lea     edx, [r9+4]; TokenInformationClass
0x180098e5a  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180098e5f  call    cs:__imp_GetTokenInformation
0x180098e65  test    eax, eax
0x180098e67  jnz     short loc_180098E7A
0x180098e69  call    GetLastFailureAsHRESULT
0x180098e6e  mov     ebx, eax
0x180098e70  mov     [rbp+57h+var_B8], eax
0x180098e73  mov     eax, 126h
0x180098e78  jmp     short loc_180098E2C
0x180098e7a  cmp     [rbp+57h+var_C0], 4
0x180098e7e  mov     eax, 126h
0x180098e83  mov     [rbp+57h+var_B4], ax
0x180098e87  mov     eax, 127h
0x180098e8c  jz      short loc_180098E98
0x180098e8e  mov     ebx, 80004005h
0x180098e93  mov     [rbp+57h+var_B8], ebx
0x180098e96  jmp     short loc_180098E2C
0x180098e98  mov     edi, 2
0x180098e9d  mov     [rbp+57h+var_B8], 0
0x180098ea4  mov     [rbp+57h+var_B4], ax
0x180098ea8  cmp     [rbp+57h+TokenInformation], edi
0x180098eab  jz      loc_180098F44
0x180098eb1  mov     rcx, [rbp+57h+hObject]; hObject
0x180098eb5  lea     rax, [rcx-1]
0x180098eb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180098ebd  ja      short loc_180098ECD
0x180098ebf  call    cs:__imp_CloseHandle
0x180098ec5  mov     [rbp+57h+hObject], 0
0x180098ecd  lea     rax, [rbp+57h+hObject]
0x180098ed1  mov     r9d, edi; ImpersonationLevel
0x180098ed4  mov     [rsp+100h+phNewToken], rax; phNewToken
0x180098ed9  xor     r8d, r8d; lpTokenAttributes
0x180098edc  xor     edx, edx; dwDesiredAccess
0x180098ede  mov     dword ptr [rsp+100h+ReturnLength], edi; TokenType
0x180098ee2  mov     rcx, rbx; hExistingToken
0x180098ee5  call    cs:__imp_DuplicateTokenEx
0x180098eeb  test    eax, eax
0x180098eed  jnz     short loc_180098F03
0x180098eef  call    GetLastFailureAsHRESULT
0x180098ef4  mov     ebx, eax
0x180098ef6  mov     [rbp+57h+var_B8], eax
0x180098ef9  mov     eax, 12Ah
0x180098efe  jmp     loc_180098E2C
0x180098f03  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x180098f07  lea     r8, [rbp+57h+IsMember]; IsMember
0x180098f0b  mov     eax, 12Ah
0x180098f10  mov     [rbp+57h+var_B8], 0
0x180098f17  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180098f1b  mov     [rbp+57h+var_B4], ax
0x180098f1f  call    cs:__imp_CheckTokenMembership
0x180098f25  test    eax, eax
0x180098f27  jnz     short loc_180098F3D
0x180098f29  call    GetLastFailureAsHRESULT
0x180098f2e  mov     ebx, eax
0x180098f30  mov     [rbp+57h+var_B8], eax
0x180098f33  mov     eax, 12Bh
0x180098f38  jmp     loc_180098E2C
0x180098f3d  mov     eax, 12Bh
0x180098f42  jmp     short loc_180098F72
0x180098f44  lea     r8, [rbp+57h+IsMember]; IsMember
0x180098f48  mov     rcx, rbx; TokenHandle
0x180098f4b  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180098f4f  call    cs:__imp_CheckTokenMembership
0x180098f55  test    eax, eax
0x180098f57  jnz     short loc_180098F6D
0x180098f59  call    GetLastFailureAsHRESULT
0x180098f5e  mov     ebx, eax
0x180098f60  mov     [rbp+57h+var_B8], eax
0x180098f63  mov     eax, 12Fh
0x180098f68  jmp     loc_180098E2C
0x180098f6d  mov     eax, 12Fh
0x180098f72  xor     ebx, ebx
0x180098f74  mov     [rbp+57h+var_B4], ax
0x180098f78  mov     eax, [rbp+57h+IsMember]
0x180098f7b  mov     [rbp+57h+var_B8], ebx
0x180098f7e  mov     [rsi], eax
0x180098f80  mov     rcx, [rbp+57h+hObject]; hObject
0x180098f84  lea     rdx, [rcx-1]
0x180098f88  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180098f8c  ja      short loc_180098F9C
0x180098f8e  call    cs:__imp_CloseHandle
0x180098f94  mov     [rbp+57h+hObject], 0
0x180098f9c  lea     rcx, [rbp+57h+var_B8]; this
0x180098fa0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180098fa5  mov     eax, ebx
0x180098fa7  mov     rcx, [rbp+57h+var_20]
0x180098fab  xor     rcx, rsp; StackCookie
0x180098fae  call    __security_check_cookie
0x180098fb3  mov     rbx, [rsp+100h+arg_18]
0x180098fbb  add     rsp, 0F0h
0x180098fc2  pop     rdi
0x180098fc3  pop     rsi
0x180098fc4  pop     rbp
0x180098fc5  retn
```
