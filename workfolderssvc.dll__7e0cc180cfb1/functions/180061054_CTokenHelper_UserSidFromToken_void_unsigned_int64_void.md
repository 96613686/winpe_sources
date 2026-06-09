# CTokenHelper::UserSidFromToken(void *,unsigned __int64,void *)

- ea: `0x180061054`
- end: `0x1800611e6`
- name: `?UserSidFromToken@CTokenHelper@@SAXPEAX_K0@Z`
- size: `402`
- prototype: `void __fastcall(HANDLE TokenHandle, unsigned __int64, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180060fc8`
- `0x1800c7390`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180004319`
- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x180061054`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x180061126`
- `ADVAPI32!GetTokenInformation` at `0x180061126`
- `ADVAPI32!GetLengthSid` at `0x180061169`
- `ADVAPI32!GetLengthSid` at `0x180061169`

## string_xrefs

- `0x1800610dd`: `CTokenHelper::UserSidFromToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTokenHelper::UserSidFromToken(HANDLE TokenHandle, unsigned __int64 a2, void *a3)
{
  _BYTE *v6; // rax
  char v7; // cl
  DWORD LengthSid; // eax
  int pExceptionObject; // [rsp+30h] [rbp-59h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-55h] BYREF
  int LastFailureAsHRESULT; // [rsp+38h] [rbp-51h] BYREF
  int v12; // [rsp+3Ch] [rbp-4Dh]
  char v13; // [rsp+40h] [rbp-49h]
  const char *v14; // [rsp+48h] [rbp-41h]
  __int64 v15; // [rsp+50h] [rbp-39h]
  const void *TokenInformation[12]; // [rsp+60h] [rbp-29h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_4342751f50db37403eb675fae9cba500_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 2) != 0 && v6[65] >= 6u )
  {
    v7 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v7 = 0;
LABEL_9:
  LastFailureAsHRESULT = 0;
  v12 = 180;
  v13 = v7;
  v14 = "CTokenHelper::UserSidFromToken";
  v15 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v12) = 194;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v12) = 194;
  LengthSid = GetLengthSid((PSID)TokenInformation[0]);
  ReturnLength = LengthSid;
  if ( a2 < LengthSid )
  {
    LastFailureAsHRESULT = -2147024774;
    HIWORD(v12) = 199;
    pExceptionObject = -2147024774;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v12) = 199;
  memcpy_0(a3, TokenInformation[0], LengthSid);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x180061054  mov     [rsp-8+arg_8], rbx
0x180061059  push    rbp
0x18006105a  push    rsi
0x18006105b  push    rdi
0x18006105c  lea     rbp, [rsp-47h]
0x180061061  sub     rsp, 0D0h
0x180061068  mov     rax, cs:__security_cookie
0x18006106f  xor     rax, rsp
0x180061072  mov     [rbp+57h+var_20], rax
0x180061076  mov     rdi, r8
0x180061079  mov     rbx, rdx
0x18006107c  mov     rsi, rcx
0x18006107f  lea     rcx, WPP_GLOBAL_Control
0x180061086  mov     rax, cs:WPP_GLOBAL_Control
0x18006108d  cmp     rax, rcx
0x180061090  jz      short loc_1800610BA
0x180061092  test    byte ptr [rax+44h], 2
0x180061096  jz      short loc_1800610CA
0x180061098  cmp     byte ptr [rax+41h], 6
0x18006109c  jb      short loc_1800610BA
0x18006109e  mov     edx, 0Dh
0x1800610a3  lea     r8, WPP_4342751f50db37403eb675fae9cba500_Traceguids
0x1800610aa  mov     rcx, [rax+38h]
0x1800610ae  call    WPP_SF_
0x1800610b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800610ba  test    byte ptr [rax+44h], 2
0x1800610be  jz      short loc_1800610CA
0x1800610c0  cmp     byte ptr [rax+41h], 6
0x1800610c4  jb      short loc_1800610CA
0x1800610c6  mov     cl, 1
0x1800610c8  jmp     short loc_1800610CC
0x1800610ca  xor     cl, cl
0x1800610cc  mov     [rbp+57h+var_A8], 0
0x1800610d3  mov     [rbp+57h+var_A4], 0B4h
0x1800610da  mov     [rbp+57h+var_A0], cl
0x1800610dd  lea     rax, aCtokenhelperUs; "CTokenHelper::UserSidFromToken"
0x1800610e4  mov     [rbp+57h+var_98], rax
0x1800610e8  mov     [rbp+57h+var_90], 0
0x1800610f0  xor     edx, edx; Val
0x1800610f2  lea     r8d, [rdx+58h]; Size
0x1800610f6  lea     rcx, [rbp+57h+TokenInformation]; void *
0x1800610fa  call    memset_0
0x1800610ff  mov     [rbp+57h+var_AC], 0
0x180061106  mov     eax, [rbp+57h+var_A8]
0x180061109  mov     [rbp+57h+var_A8], eax
0x18006110c  lea     rax, [rbp+57h+var_AC]
0x180061110  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180061115  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18006111b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18006111f  lea     edx, [r9-57h]; TokenInformationClass
0x180061123  mov     rcx, rsi; TokenHandle
0x180061126  call    cs:__imp_GetTokenInformation
0x18006112c  test    eax, eax
0x18006112e  jnz     short loc_180061155
0x180061130  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180061135  mov     [rbp+57h+var_A8], eax
0x180061138  mov     ecx, 0C2h
0x18006113d  mov     word ptr [rbp+57h+var_A4+2], cx
0x180061141  mov     [rbp+57h+pExceptionObject], eax
0x180061144  lea     rdx, _TI1J; pThrowInfo
0x18006114b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006114f  call    _CxxThrowException_0
0x180061155  mov     [rbp+57h+var_A8], 0
0x18006115c  mov     ecx, 0C2h
0x180061161  mov     word ptr [rbp+57h+var_A4], cx
0x180061165  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x180061169  call    cs:__imp_GetLengthSid
0x18006116f  mov     r8d, eax; Size
0x180061172  mov     [rbp+57h+var_AC], r8d
0x180061176  mov     eax, [rbp+57h+var_A8]
0x180061179  mov     [rbp+57h+var_A8], eax
0x18006117c  mov     eax, 0C7h
0x180061181  cmp     rbx, r8
0x180061184  jnb     short loc_1800611A6
0x180061186  mov     ecx, 8007007Ah
0x18006118b  mov     [rbp+57h+var_A8], ecx
0x18006118e  mov     word ptr [rbp+57h+var_A4+2], ax
0x180061192  mov     [rbp+57h+pExceptionObject], ecx
0x180061195  lea     rdx, _TI1J; pThrowInfo
0x18006119c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800611a0  call    _CxxThrowException_0
0x1800611a6  mov     [rbp+57h+var_A8], 0
0x1800611ad  mov     word ptr [rbp+57h+var_A4], ax
0x1800611b1  mov     rdx, [rbp+57h+TokenInformation]; Src
0x1800611b5  mov     rcx, rdi; void *
0x1800611b8  call    memcpy_0
0x1800611bd  nop
0x1800611be  lea     rcx, [rbp+57h+var_A8]; this
0x1800611c2  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800611c7  mov     rcx, [rbp+57h+var_20]
0x1800611cb  xor     rcx, rsp; StackCookie
0x1800611ce  call    __security_check_cookie
0x1800611d3  mov     rbx, [rsp+0E0h+arg_8]
0x1800611db  add     rsp, 0D0h
0x1800611e2  pop     rdi
0x1800611e3  pop     rsi
0x1800611e4  pop     rbp
0x1800611e5  retn
```
