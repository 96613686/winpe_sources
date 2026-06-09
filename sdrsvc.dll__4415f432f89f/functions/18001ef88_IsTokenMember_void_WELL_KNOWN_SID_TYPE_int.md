# IsTokenMember(void *,WELL_KNOWN_SID_TYPE,int *)

- ea: `0x18001ef88`
- end: `0x18001f1e6`
- name: `?IsTokenMember@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@PEAH@Z`
- size: `606`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, WELL_KNOWN_SID_TYPE WellKnownSidType, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001f414`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18001ef88`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1ae`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001f033`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001f033`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f105`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f105`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001f13f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001f16f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001f13f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001f16f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f07f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f07f`

## string_xrefs

- `0x18001efb2`: `IsTokenMember`

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
0x18001ef88  mov     [rsp-8+arg_18], rbx
0x18001ef8d  push    rbp
0x18001ef8e  push    rsi
0x18001ef8f  push    rdi
0x18001ef90  lea     rbp, [rsp-47h]
0x18001ef95  sub     rsp, 0F0h
0x18001ef9c  mov     rax, cs:__security_cookie
0x18001efa3  xor     rax, rsp
0x18001efa6  mov     [rbp+57h+var_20], rax
0x18001efaa  mov     rsi, r8
0x18001efad  mov     edi, edx
0x18001efaf  mov     rbx, rcx
0x18001efb2  lea     rdx, aIstokenmember; "IsTokenMember"
0x18001efb9  mov     r8d, 11Ah; unsigned __int16
0x18001efbf  lea     rcx, [rbp+57h+var_B8]; this
0x18001efc3  mov     r9d, 1; unsigned __int16
0x18001efc9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001efce  xor     edx, edx; Val
0x18001efd0  mov     [rbp+57h+IsMember], 0
0x18001efd7  lea     rcx, [rbp+57h+pSid]; void *
0x18001efdb  lea     r8d, [rdx+48h]; Size
0x18001efdf  call    memset_0
0x18001efe4  mov     [rbp+57h+cbSid], 48h ; 'H'
0x18001efeb  mov     eax, 123h
0x18001eff0  mov     [rbp+57h+hObject], 0
0x18001eff8  mov     [rbp+57h+TokenInformation], 1
0x18001efff  mov     [rbp+57h+var_C0], 0
0x18001f006  test    rbx, rbx
0x18001f009  jnz     short loc_18001F01C
0x18001f00b  mov     ebx, 80070057h
0x18001f010  mov     [rbp+57h+var_B2], ax
0x18001f014  mov     [rbp+57h+var_B8], ebx
0x18001f017  jmp     loc_18001F1BC
0x18001f01c  lea     r9, [rbp+57h+cbSid]; cbSid
0x18001f020  mov     [rbp+57h+var_B8], 0
0x18001f027  lea     r8, [rbp+57h+pSid]; pSid
0x18001f02b  mov     [rbp+57h+var_B4], ax
0x18001f02f  xor     edx, edx; DomainSid
0x18001f031  mov     ecx, edi; WellKnownSidType
0x18001f033  call    cs:__imp_CreateWellKnownSid
0x18001f039  test    eax, eax
0x18001f03b  jnz     short loc_18001F055
0x18001f03d  call    GetLastFailureAsHRESULT
0x18001f042  mov     ebx, eax
0x18001f044  mov     [rbp+57h+var_B8], eax
0x18001f047  mov     eax, 125h
0x18001f04c  mov     [rbp+57h+var_B2], ax
0x18001f050  jmp     loc_18001F1A0
0x18001f055  mov     r9d, 4; TokenInformationLength
0x18001f05b  mov     [rbp+57h+var_B8], 0
0x18001f062  mov     eax, 125h
0x18001f067  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001f06b  mov     [rbp+57h+var_B4], ax
0x18001f06f  mov     rcx, rbx; TokenHandle
0x18001f072  lea     rax, [rbp+57h+var_C0]
0x18001f076  lea     edx, [r9+4]; TokenInformationClass
0x18001f07a  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18001f07f  call    cs:__imp_GetTokenInformation
0x18001f085  test    eax, eax
0x18001f087  jnz     short loc_18001F09A
0x18001f089  call    GetLastFailureAsHRESULT
0x18001f08e  mov     ebx, eax
0x18001f090  mov     [rbp+57h+var_B8], eax
0x18001f093  mov     eax, 126h
0x18001f098  jmp     short loc_18001F04C
0x18001f09a  cmp     [rbp+57h+var_C0], 4
0x18001f09e  mov     eax, 126h
0x18001f0a3  mov     [rbp+57h+var_B4], ax
0x18001f0a7  mov     eax, 127h
0x18001f0ac  jz      short loc_18001F0B8
0x18001f0ae  mov     ebx, 80004005h
0x18001f0b3  mov     [rbp+57h+var_B8], ebx
0x18001f0b6  jmp     short loc_18001F04C
0x18001f0b8  mov     edi, 2
0x18001f0bd  mov     [rbp+57h+var_B8], 0
0x18001f0c4  mov     [rbp+57h+var_B4], ax
0x18001f0c8  cmp     [rbp+57h+TokenInformation], edi
0x18001f0cb  jz      loc_18001F164
0x18001f0d1  mov     rcx, [rbp+57h+hObject]; hObject
0x18001f0d5  lea     rax, [rcx-1]
0x18001f0d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f0dd  ja      short loc_18001F0ED
0x18001f0df  call    cs:__imp_CloseHandle
0x18001f0e5  mov     [rbp+57h+hObject], 0
0x18001f0ed  lea     rax, [rbp+57h+hObject]
0x18001f0f1  mov     r9d, edi; ImpersonationLevel
0x18001f0f4  mov     [rsp+100h+phNewToken], rax; phNewToken
0x18001f0f9  xor     r8d, r8d; lpTokenAttributes
0x18001f0fc  xor     edx, edx; dwDesiredAccess
0x18001f0fe  mov     dword ptr [rsp+100h+ReturnLength], edi; TokenType
0x18001f102  mov     rcx, rbx; hExistingToken
0x18001f105  call    cs:__imp_DuplicateTokenEx
0x18001f10b  test    eax, eax
0x18001f10d  jnz     short loc_18001F123
0x18001f10f  call    GetLastFailureAsHRESULT
0x18001f114  mov     ebx, eax
0x18001f116  mov     [rbp+57h+var_B8], eax
0x18001f119  mov     eax, 12Ah
0x18001f11e  jmp     loc_18001F04C
0x18001f123  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x18001f127  lea     r8, [rbp+57h+IsMember]; IsMember
0x18001f12b  mov     eax, 12Ah
0x18001f130  mov     [rbp+57h+var_B8], 0
0x18001f137  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18001f13b  mov     [rbp+57h+var_B4], ax
0x18001f13f  call    cs:__imp_CheckTokenMembership
0x18001f145  test    eax, eax
0x18001f147  jnz     short loc_18001F15D
0x18001f149  call    GetLastFailureAsHRESULT
0x18001f14e  mov     ebx, eax
0x18001f150  mov     [rbp+57h+var_B8], eax
0x18001f153  mov     eax, 12Bh
0x18001f158  jmp     loc_18001F04C
0x18001f15d  mov     eax, 12Bh
0x18001f162  jmp     short loc_18001F192
0x18001f164  lea     r8, [rbp+57h+IsMember]; IsMember
0x18001f168  mov     rcx, rbx; TokenHandle
0x18001f16b  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18001f16f  call    cs:__imp_CheckTokenMembership
0x18001f175  test    eax, eax
0x18001f177  jnz     short loc_18001F18D
0x18001f179  call    GetLastFailureAsHRESULT
0x18001f17e  mov     ebx, eax
0x18001f180  mov     [rbp+57h+var_B8], eax
0x18001f183  mov     eax, 12Fh
0x18001f188  jmp     loc_18001F04C
0x18001f18d  mov     eax, 12Fh
0x18001f192  xor     ebx, ebx
0x18001f194  mov     [rbp+57h+var_B4], ax
0x18001f198  mov     eax, [rbp+57h+IsMember]
0x18001f19b  mov     [rbp+57h+var_B8], ebx
0x18001f19e  mov     [rsi], eax
0x18001f1a0  mov     rcx, [rbp+57h+hObject]; hObject
0x18001f1a4  lea     rdx, [rcx-1]
0x18001f1a8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001f1ac  ja      short loc_18001F1BC
0x18001f1ae  call    cs:__imp_CloseHandle
0x18001f1b4  mov     [rbp+57h+hObject], 0
0x18001f1bc  lea     rcx, [rbp+57h+var_B8]; this
0x18001f1c0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001f1c5  mov     eax, ebx
0x18001f1c7  mov     rcx, [rbp+57h+var_20]
0x18001f1cb  xor     rcx, rsp; StackCookie
0x18001f1ce  call    __security_check_cookie
0x18001f1d3  mov     rbx, [rsp+100h+arg_18]
0x18001f1db  add     rsp, 0F0h
0x18001f1e2  pop     rdi
0x18001f1e3  pop     rsi
0x18001f1e4  pop     rbp
0x18001f1e5  retn
```
