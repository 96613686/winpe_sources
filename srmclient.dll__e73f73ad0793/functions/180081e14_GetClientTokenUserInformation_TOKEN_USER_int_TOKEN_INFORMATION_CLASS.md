# GetClientTokenUserInformation<_TOKEN_USER>(int,_TOKEN_INFORMATION_CLASS)

- ea: `0x180081e14`
- end: `0x1800820b6`
- name: `??$GetClientTokenUserInformation@U_TOKEN_USER@@@@YAPEAU_TOKEN_USER@@HW4_TOKEN_INFORMATION_CLASS@@@Z`
- size: `674`
- prototype: `LPVOID __fastcall(int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180083640`
- `0x1800a9e40`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180081e14`
- `0x1800824c4`
- `0x180082f80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180081fdf`
- `KERNEL32!CloseHandle` at `0x180081fdf`
- `KERNEL32!GetLastError` at `0x180081f13`
- `KERNEL32!GetLastError` at `0x180081f13`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180081eff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180081f96`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180081eff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180081f96`

## string_xrefs

- `0x180081e59`: `GetClientTokenUserInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LPVOID __fastcall GetClientTokenUserInformation<_TOKEN_USER>(int a1)
{
  unsigned int v2; // edx
  BOOL v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  LPVOID v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  char v10; // al
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  int v13; // eax
  char v14; // al
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  void **v16; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID TokenInformation; // [rsp+40h] [rbp-C0h]
  DWORD ReturnLength; // [rsp+48h] [rbp-B8h] BYREF
  void **v19; // [rsp+50h] [rbp-B0h]
  HANDLE TokenHandle[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v21[3]; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+80h] [rbp-80h]
  int v23; // [rsp+84h] [rbp-7Ch]
  int v24; // [rsp+88h] [rbp-78h]
  _BYTE v25[96]; // [rsp+90h] [rbp-70h] BYREF
  int v26; // [rsp+F0h] [rbp-10h]
  void **v27; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v28; // [rsp+108h] [rbp+8h]

  TokenHandle[1] = v21;
  v21[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmsec.h";
  v21[1] = L"GetClientTokenUserInformation";
  v21[2] = L"INCSECH";
  v22 = 165;
  v23 = 17;
  v24 = 255;
  v26 = 0x1000000;
  memset_0(v25, 0, sizeof(v25));
  CSrmFunctionTracer::CSrmFunctionTracer(&v27, v21, 0);
  v19 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  TokenHandle[0] = (HANDLE)-1LL;
  GetCurrentAccessToken(a1, v2, TokenHandle);
  TokenInformationLength = 0;
  v3 = GetTokenInformation(TokenHandle[0], TokenUser, 0, 0, &TokenInformationLength);
  v5 = v28;
  if ( v3 || GetLastError() != 122 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v5, v4);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v27, LastFailureAsHRESULT);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v27);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v27, 0xB5u, Hr, 0);
  }
  v28 = 0;
  TokenInformation = 0;
  v16 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
  CSrmAutoLocalPtr_Storage<_TOKEN_USER *>::AllocateBytes(&v16, TokenInformationLength);
  ReturnLength = 0;
  v6 = TokenInformation;
  if ( !GetTokenInformation(TokenHandle[0], TokenUser, TokenInformation, TokenInformationLength, &ReturnLength) )
  {
    v13 = GetLastFailureAsHRESULT(v8, v7);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v27, v13);
    v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v27);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v27, 0xC4u, v14, 0);
  }
  v28 = 0;
  if ( ReturnLength != TokenInformationLength )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v27, -2147200234);
    v10 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v27);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v27, 0xC6u, v10, 0);
  }
  v28 = 0;
  v16 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  TokenInformation = 0;
  v19 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( TokenHandle[0] != (HANDLE)-1LL )
    CloseHandle(TokenHandle[0]);
  v19 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
  TokenHandle[0] = (HANDLE)-1LL;
  v27 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v27);
  return v6;
}

```

## disassembly

```asm
0x180081e14  push    rbp
0x180081e16  push    rbx
0x180081e17  push    rsi
0x180081e18  push    rdi
0x180081e19  push    r12
0x180081e1b  push    r13
0x180081e1d  push    r14
0x180081e1f  push    r15
0x180081e21  lea     rbp, [rsp-0C8h]
0x180081e29  sub     rsp, 1C8h
0x180081e30  mov     rax, cs:__security_cookie
0x180081e37  xor     rax, rsp
0x180081e3a  mov     [rbp+100h+var_50], rax
0x180081e41  mov     ebx, ecx
0x180081e43  lea     rax, [rsp+200h+var_198]
0x180081e48  mov     [rsp+200h+var_1A0], rax
0x180081e4d  lea     rax, aBaseFsFsrmUtil_5; "base\\fs\\fsrm\\utilities\\inc\\srmsec."...
0x180081e54  mov     [rsp+200h+var_198], rax
0x180081e59  lea     rax, aGetclienttoken; "GetClientTokenUserInformation"
0x180081e60  mov     [rsp+200h+var_190], rax
0x180081e65  lea     rax, aIncsech; "INCSECH"
0x180081e6c  mov     [rsp+200h+var_188], rax
0x180081e71  mov     [rbp+100h+var_180], 0A5h
0x180081e78  mov     [rbp+100h+var_17C], 11h
0x180081e7f  mov     [rbp+100h+var_178], 0FFh
0x180081e86  xor     edi, edi
0x180081e88  mov     [rbp+100h+var_110], 1000000h
0x180081e8f  xor     edx, edx; Val
0x180081e91  lea     r8d, [rdi+60h]; Size
0x180081e95  lea     rcx, [rbp+100h+var_170]; void *
0x180081e99  call    memset_0
0x180081e9e  nop
0x180081e9f  xor     r8d, r8d
0x180081ea2  lea     rdx, [rsp+200h+var_198]
0x180081ea7  lea     rcx, [rbp+100h+var_100]
0x180081eab  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180081eb0  nop
0x180081eb1  lea     r12, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x180081eb8  mov     [rsp+200h+var_1B0], r12
0x180081ebd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180081ec1  mov     [rsp+200h+TokenHandle], rsi
0x180081ec6  lea     r13, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x180081ecd  mov     [rsp+200h+var_1B0], r13
0x180081ed2  mov     [rsp+200h+TokenHandle], rsi
0x180081ed7  lea     r8, [rsp+200h+TokenHandle]; void **
0x180081edc  mov     ecx, ebx; int
0x180081ede  call    ?GetCurrentAccessToken@@YA_NHKPEAPEAX@Z; GetCurrentAccessToken(int,ulong,void * *)
0x180081ee3  mov     [rsp+200h+TokenInformationLength], edi
0x180081ee7  lea     rax, [rsp+200h+TokenInformationLength]
0x180081eec  mov     [rsp+200h+ReturnLength], rax; ReturnLength
0x180081ef1  xor     r9d, r9d; TokenInformationLength
0x180081ef4  xor     r8d, r8d; TokenInformation
0x180081ef7  lea     edx, [rdi+1]; TokenInformationClass
0x180081efa  mov     rcx, [rsp+200h+TokenHandle]; TokenHandle
0x180081eff  call    cs:__imp_GetTokenInformation
0x180081f05  mov     ecx, [rbp+100h+var_F8]
0x180081f08  mov     [rbp+100h+var_F8], ecx
0x180081f0b  test    eax, eax
0x180081f0d  jnz     loc_18008205A
0x180081f13  call    cs:__imp_GetLastError
0x180081f19  cmp     eax, 7Ah ; 'z'
0x180081f1c  jnz     loc_18008205A
0x180081f22  mov     [rbp+100h+var_F8], edi
0x180081f25  lea     r14, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x180081f2c  mov     [rsp+200h+var_1C8], r14
0x180081f31  mov     [rsp+200h+TokenInformation], rdi
0x180081f36  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x180081f3d  mov     [rsp+200h+var_1C8], rax
0x180081f42  lea     r15, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x180081f49  mov     [rsp+200h+var_1C8], r15
0x180081f4e  mov     [rsp+200h+TokenInformation], rdi
0x180081f53  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x180081f5a  mov     [rsp+200h+var_1C8], rax
0x180081f5f  mov     edx, [rsp+200h+TokenInformationLength]
0x180081f63  lea     rcx, [rsp+200h+var_1C8]
0x180081f68  call    ?AllocateBytes@?$CSrmAutoLocalPtr_Storage@PEAU_TOKEN_USER@@@@QEAAX_K@Z; CSrmAutoLocalPtr_Storage<_TOKEN_USER *>::AllocateBytes(unsigned __int64)
0x180081f6d  mov     [rsp+200h+var_1B8], edi
0x180081f71  mov     eax, [rbp+100h+var_F8]
0x180081f74  mov     [rbp+100h+var_F8], eax
0x180081f77  mov     rbx, [rsp+200h+TokenInformation]
0x180081f7c  lea     rax, [rsp+200h+var_1B8]
0x180081f81  mov     [rsp+200h+ReturnLength], rax; ReturnLength
0x180081f86  mov     r9d, [rsp+200h+TokenInformationLength]; TokenInformationLength
0x180081f8b  mov     r8, rbx; TokenInformation
0x180081f8e  lea     edx, [rdi+1]; TokenInformationClass
0x180081f91  mov     rcx, [rsp+200h+TokenHandle]; TokenHandle
0x180081f96  call    cs:__imp_GetTokenInformation
0x180081f9c  test    eax, eax
0x180081f9e  jz      loc_180082088
0x180081fa4  mov     [rbp+100h+var_F8], edi
0x180081fa7  mov     [rbp+100h+var_F8], edi
0x180081faa  mov     eax, [rsp+200h+TokenInformationLength]
0x180081fae  cmp     [rsp+200h+var_1B8], eax
0x180081fb2  jnz     short loc_18008202E
0x180081fb4  mov     [rbp+100h+var_F8], edi
0x180081fb7  mov     [rsp+200h+TokenInformation], rdi
0x180081fbc  mov     [rsp+200h+var_1C8], r15
0x180081fc1  mov     [rsp+200h+TokenInformation], rdi
0x180081fc6  mov     [rsp+200h+var_1C8], r14
0x180081fcb  mov     [rsp+200h+TokenInformation], rdi
0x180081fd0  mov     [rsp+200h+var_1B0], r13
0x180081fd5  mov     rcx, [rsp+200h+TokenHandle]; hObject
0x180081fda  cmp     rcx, rsi
0x180081fdd  jz      short loc_180081FE5
0x180081fdf  call    cs:__imp_CloseHandle
0x180081fe5  mov     [rsp+200h+TokenHandle], rsi
0x180081fea  mov     [rsp+200h+var_1B0], r12
0x180081fef  mov     [rsp+200h+TokenHandle], rsi
0x180081ff4  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180081ffb  mov     [rbp+100h+var_100], rax
0x180081fff  lea     rcx, [rbp+100h+var_100]; this
0x180082003  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180082008  mov     rax, rbx
0x18008200b  mov     rcx, [rbp+100h+var_50]
0x180082012  xor     rcx, rsp; StackCookie
0x180082015  call    __security_check_cookie
0x18008201a  add     rsp, 1C8h
0x180082021  pop     r15
0x180082023  pop     r14
0x180082025  pop     r13
0x180082027  pop     r12
0x180082029  pop     rdi
0x18008202a  pop     rsi
0x18008202b  pop     rbx
0x18008202c  pop     rbp
0x18008202d  retn
0x18008202e  mov     edx, 80045316h; int
0x180082033  lea     rcx, [rbp+100h+var_100]; this
0x180082037  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18008203c  lea     rcx, [rbp+100h+var_100]; this
0x180082040  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180082045  mov     r8d, eax; char
0x180082048  xor     r9d, r9d; unsigned __int16 *
0x18008204b  mov     edx, 0C6h; unsigned int
0x180082050  lea     rcx, [rbp+100h+var_100]; this
0x180082054  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18008205a  call    GetLastFailureAsHRESULT
0x18008205f  mov     edx, eax; int
0x180082061  lea     rcx, [rbp+100h+var_100]; this
0x180082065  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18008206a  lea     rcx, [rbp+100h+var_100]; this
0x18008206e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180082073  mov     r8d, eax; char
0x180082076  xor     r9d, r9d; unsigned __int16 *
0x180082079  mov     edx, 0B5h; unsigned int
0x18008207e  lea     rcx, [rbp+100h+var_100]; this
0x180082082  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180082088  call    GetLastFailureAsHRESULT
0x18008208d  mov     edx, eax; int
0x18008208f  lea     rcx, [rbp+100h+var_100]; this
0x180082093  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180082098  lea     rcx, [rbp+100h+var_100]; this
0x18008209c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800820a1  mov     r8d, eax; char
0x1800820a4  xor     r9d, r9d; unsigned __int16 *
0x1800820a7  mov     edx, 0C4h; unsigned int
0x1800820ac  lea     rcx, [rbp+100h+var_100]; this
0x1800820b0  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
