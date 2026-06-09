# IsInGroup(ulong,bool)

- ea: `0x18003d78c`
- end: `0x18003da6e`
- name: `?IsInGroup@@YA_NK_N@Z`
- size: `738`
- prototype: `char __fastcall()`
- caller_count: `34`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006cb0`
- `0x180007b80`
- `0x18000de70`
- `0x18000e900`
- `0x18000f910`
- `0x18000ffe0`
- `0x180010a20`
- `0x1800122a0`
- `0x180012740`
- `0x180012bd0`
- `0x180012e50`
- `0x180013080`
- `0x1800138c0`
- `0x180013de0`
- `0x1800144a0`
- `0x180014a00`
- `0x180015890`
- `0x180015ff0`
- `0x180016550`
- `0x180017b30`
- `0x180023d70`
- `0x1800260e0`
- `0x1800267e0`
- `0x180026da0`
- `0x180027ad0`
- `0x180028aa0`
- `0x1800294e0`
- `0x180029e60`
- `0x18002a950`
- `0x18002b490`
- `0x18002c080`
- `0x18002c830`
- `0x18002d1f0`
- `0x18002e010`

## callees

- `0x180001580`
- `0x18000212c`
- `0x18000dc10`
- `0x18000f8e0`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x18003609c`
- `0x180036f10`
- `0x18003cb5c`
- `0x18003d78c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d8a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d96a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d8a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d96a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d95c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d95c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003da0a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003da0a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003d897`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003d897`

## string_xrefs

- `0x18003d7af`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003d911`: `AllocateAndInitializeSid`
- `0x18003d9d6`: `CheckTokenMembership`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IsInGroup()
{
  signed int LastError; // eax
  unsigned int v1; // edi
  __int64 v2; // rdx
  __int64 v3; // rcx
  void *v4; // rcx
  signed int v5; // eax
  unsigned int v6; // edi
  char v7; // bl
  WINBOOL IsMember; // [rsp+60h] [rbp-198h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-190h] BYREF
  void **v11; // [rsp+70h] [rbp-188h] BYREF
  void *v12; // [rsp+78h] [rbp-180h] BYREF
  unsigned int v13; // [rsp+80h] [rbp-178h] BYREF
  const unsigned __int16 *v14; // [rsp+90h] [rbp-168h] BYREF
  const unsigned __int16 *v15; // [rsp+98h] [rbp-160h]
  const unsigned __int16 *v16; // [rsp+A0h] [rbp-158h]
  int v17; // [rsp+A8h] [rbp-150h]
  int v18; // [rsp+ACh] [rbp-14Ch]
  int v19; // [rsp+B0h] [rbp-148h]
  _BYTE v20[120]; // [rsp+B8h] [rbp-140h] BYREF
  int v21; // [rsp+130h] [rbp-C8h]
  LPVOID v22; // [rsp+140h] [rbp-B8h] BYREF
  int v23; // [rsp+148h] [rbp-B0h]
  unsigned int v24; // [rsp+164h] [rbp-94h]
  _com_error *v25; // [rsp+1B0h] [rbp-48h] BYREF
  const std::exception *v26; // [rsp+1B8h] [rbp-40h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+1C0h] [rbp-38h] BYREF

  v14 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v15 = L"IsInGroup";
  v16 = L"SECSECRC";
  v17 = 221;
  v18 = 11;
  v19 = 255;
  v21 = 0x1000000;
  memset_0(v20, 0, sizeof(v20));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v22, (__int64)&v14, 0);
  v12 = (void *)-1LL;
  v11 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  SidToCheck = 0;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v14 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v15 = L"IsInGroup";
    v16 = L"SECSECRC";
    v17 = 249;
    v18 = 11;
    v19 = 255;
    v21 = 0x1000000;
    memset_0(v20, 0, sizeof(v20));
    CVssFunctionTracer::TranslateError(&v22, &v14, v1, L"AllocateAndInitializeSid");
  }
  CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&v11);
  try
  {
    if ( GetCurrentAccessToken(v3, v2, &v12) )
      v4 = v12;
    else
      v4 = 0;
    if ( !CheckTokenMembership(v4, SidToCheck, &IsMember) )
    {
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      v14 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v15 = L"IsInGroup";
      v16 = L"SECSECRC";
      v17 = 281;
      v18 = 11;
      v19 = 255;
      v21 = 0x1000000;
      memset_0(v20, 0, sizeof(v20));
      CVssFunctionTracer::TranslateError(&v22, &v14, v6, L"CheckTokenMembership");
    }
  }
  catch ( long v13 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v22,
      v13,
      L"base\\stor\\vss\\modules\\sec\\security.cxx",
      L"SECSECRC",
      L"IsInGroup",
      0x11Eu,
      v24);
  }
  catch ( _com_error *v25 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v22,
      v25,
      L"base\\stor\\vss\\modules\\sec\\security.cxx",
      L"SECSECRC",
      L"IsInGroup",
      0x11Eu,
      v24);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v22,
      L"base\\stor\\vss\\modules\\sec\\security.cxx",
      L"SECSECRC",
      L"IsInGroup",
      0x11Eu,
      v24);
  }
  catch ( const std::exception *v26 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v22,
      v26,
      L"base\\stor\\vss\\modules\\sec\\security.cxx",
      L"SECSECRC",
      L"IsInGroup",
      0x11Eu,
      v24);
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( v23 < 0 )
    CVssFunctionTracer::ReThrow((CVssFunctionTracer *)&v22);
  v7 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v22, IsMember != 0);
  CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(&v11);
  CVssFunctionTracer::~CVssFunctionTracer(&v22);
  return v7;
}

```

## disassembly

```asm
0x18003d78c  mov     r11, rsp
0x18003d78f  push    rbx
0x18003d790  push    rsi
0x18003d791  push    rdi
0x18003d792  push    r14
0x18003d794  push    r15
0x18003d796  sub     rsp, 1D0h
0x18003d79d  mov     rax, cs:__security_cookie
0x18003d7a4  xor     rax, rsp
0x18003d7a7  mov     [rsp+1F8h+var_30], rax
0x18003d7af  lea     rsi, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003d7b6  mov     [r11-168h], rsi
0x18003d7bd  lea     r14, aIsingroup; "IsInGroup"
0x18003d7c4  mov     [r11-160h], r14
0x18003d7cb  lea     r15, aSecsecrc; "SECSECRC"
0x18003d7d2  mov     [r11-158h], r15
0x18003d7d9  mov     [rsp+1F8h+var_150], 0DDh
0x18003d7e4  mov     [rsp+1F8h+var_14C], 0Bh
0x18003d7ef  mov     [rsp+1F8h+var_148], 0FFh
0x18003d7fa  xor     ebx, ebx
0x18003d7fc  mov     [rsp+1F8h+var_C8], 1000000h
0x18003d807  xor     edx, edx; Val
0x18003d809  lea     r8d, [rbx+78h]; Size
0x18003d80d  lea     rcx, [r11-140h]; void *
0x18003d814  call    memset_0
0x18003d819  xor     r8d, r8d
0x18003d81c  lea     rdx, [rsp+1F8h+var_168]
0x18003d824  lea     rcx, [rsp+1F8h+var_B8]
0x18003d82c  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003d831  nop
0x18003d832  mov     [rsp+1F8h+var_180], 0FFFFFFFFFFFFFFFFh
0x18003d83b  lea     rax, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18003d842  mov     [rsp+1F8h+var_188], rax
0x18003d847  mov     [rsp+1F8h+SidToCheck], rbx
0x18003d84c  mov     [rsp+1F8h+IsMember], ebx
0x18003d850  mov     dword ptr [rsp+1F8h+pIdentifierAuthority.Value], ebx
0x18003d857  mov     word ptr [rsp+1F8h+pIdentifierAuthority.Value+4], 500h
0x18003d861  lea     rax, [rsp+1F8h+SidToCheck]
0x18003d866  mov     [rsp+1F8h+pSid], rax; pSid
0x18003d86b  mov     [rsp+1F8h+nSubAuthority7], ebx; nSubAuthority7
0x18003d86f  mov     [rsp+1F8h+nSubAuthority6], ebx; nSubAuthority6
0x18003d873  mov     [rsp+1F8h+nSubAuthority5], ebx; nSubAuthority5
0x18003d877  mov     [rsp+1F8h+nSubAuthority4], ebx; nSubAuthority4
0x18003d87b  mov     [rsp+1F8h+nSubAuthority3], ebx; nSubAuthority3
0x18003d87f  mov     [rsp+1F8h+nSubAuthority2], ebx; nSubAuthority2
0x18003d883  mov     r9d, 220h; nSubAuthority1
0x18003d889  lea     r8d, [rbx+20h]; nSubAuthority0
0x18003d88d  mov     dl, 2; nSubAuthorityCount
0x18003d88f  lea     rcx, [rsp+1F8h+pIdentifierAuthority]; pIdentifierAuthority
0x18003d897  call    cs:__imp_AllocateAndInitializeSid
0x18003d89d  test    eax, eax
0x18003d89f  jnz     loc_18003D931
0x18003d8a5  call    cs:__imp_GetLastError
0x18003d8ab  mov     edi, eax
0x18003d8ad  test    eax, eax
0x18003d8af  jle     short loc_18003D8BA
0x18003d8b1  movzx   edi, ax
0x18003d8b4  or      edi, 80070000h
0x18003d8ba  mov     [rsp+1F8h+var_168], rsi
0x18003d8c2  mov     [rsp+1F8h+var_160], r14
0x18003d8ca  mov     [rsp+1F8h+var_158], r15
0x18003d8d2  mov     [rsp+1F8h+var_150], 0F9h
0x18003d8dd  mov     [rsp+1F8h+var_14C], 0Bh
0x18003d8e8  mov     [rsp+1F8h+var_148], 0FFh
0x18003d8f3  mov     [rsp+1F8h+var_C8], 1000000h
0x18003d8fe  xor     edx, edx; Val
0x18003d900  lea     r8d, [rdx+78h]; Size
0x18003d904  lea     rcx, [rsp+1F8h+var_140]; void *
0x18003d90c  call    memset_0
0x18003d911  lea     r9, aAllocateandini; "AllocateAndInitializeSid"
0x18003d918  mov     r8d, edi
0x18003d91b  lea     rdx, [rsp+1F8h+var_168]
0x18003d923  lea     rcx, [rsp+1F8h+var_B8]
0x18003d92b  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x18003d931  lea     rcx, [rsp+1F8h+var_188]
0x18003d936  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x18003d93b  lea     r8, [rsp+1F8h+var_180]; void **
0x18003d940  call    ?GetCurrentAccessToken@@YA_N_N0PEAPEAX@Z; GetCurrentAccessToken(bool,bool,void * *)
0x18003d945  lea     r8, [rsp+1F8h+IsMember]; IsMember
0x18003d94a  mov     rdx, [rsp+1F8h+SidToCheck]; SidToCheck
0x18003d94f  test    al, al
0x18003d951  jz      short loc_18003D95A
0x18003d953  mov     rcx, [rsp+1F8h+var_180]
0x18003d958  jmp     short loc_18003D95C
0x18003d95a  xor     ecx, ecx; TokenHandle
0x18003d95c  call    cs:__imp_CheckTokenMembership
0x18003d962  test    eax, eax
0x18003d964  jnz     loc_18003D9F6
0x18003d96a  call    cs:__imp_GetLastError
0x18003d970  mov     edi, eax
0x18003d972  test    eax, eax
0x18003d974  jle     short loc_18003D97F
0x18003d976  movzx   edi, ax
0x18003d979  or      edi, 80070000h
0x18003d97f  mov     [rsp+1F8h+var_168], rsi
0x18003d987  mov     [rsp+1F8h+var_160], r14
0x18003d98f  mov     [rsp+1F8h+var_158], r15
0x18003d997  mov     [rsp+1F8h+var_150], 119h
0x18003d9a2  mov     [rsp+1F8h+var_14C], 0Bh
0x18003d9ad  mov     [rsp+1F8h+var_148], 0FFh
0x18003d9b8  mov     [rsp+1F8h+var_C8], 1000000h
0x18003d9c3  xor     edx, edx; Val
0x18003d9c5  lea     r8d, [rdx+78h]; Size
0x18003d9c9  lea     rcx, [rsp+1F8h+var_140]; void *
0x18003d9d1  call    memset_0
0x18003d9d6  lea     r9, aChecktokenmemb; "CheckTokenMembership"
0x18003d9dd  mov     r8d, edi
0x18003d9e0  lea     rdx, [rsp+1F8h+var_168]
0x18003d9e8  lea     rcx, [rsp+1F8h+var_B8]
0x18003d9f0  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x18003d9f6  jmp     short loc_18003DA00
0x18003d9f8  jmp     short loc_18003D9FE
0x18003d9fa  jmp     short loc_18003D9FE
0x18003d9fc  jmp     short $+2
0x18003d9fe  xor     ebx, ebx
0x18003da00  mov     rcx, [rsp+1F8h+SidToCheck]; pSid
0x18003da05  test    rcx, rcx
0x18003da08  jz      short loc_18003DA10
0x18003da0a  call    cs:__imp_FreeSid
0x18003da10  lea     rcx, [rsp+1F8h+var_B8]; this
0x18003da18  cmp     [rsp+1F8h+var_B0], ebx
0x18003da1f  jge     short loc_18003DA27
0x18003da21  call    ?ReThrow@CVssFunctionTracer@@QEAAXXZ; CVssFunctionTracer::ReThrow(void)
0x18003da27  cmp     [rsp+1F8h+IsMember], ebx
0x18003da2b  setnz   dl; bool
0x18003da2e  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x18003da33  mov     bl, al
0x18003da35  lea     rcx, [rsp+1F8h+var_188]
0x18003da3a  call    ??1?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x18003da3f  nop
0x18003da40  lea     rcx, [rsp+1F8h+var_B8]; this
0x18003da48  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003da4d  mov     al, bl
0x18003da4f  mov     rcx, [rsp+1F8h+var_30]
0x18003da57  xor     rcx, rsp; StackCookie
0x18003da5a  call    __security_check_cookie
0x18003da5f  add     rsp, 1D0h
0x18003da66  pop     r15
0x18003da68  pop     r14
0x18003da6a  pop     rdi
0x18003da6b  pop     rsi
0x18003da6c  pop     rbx
0x18003da6d  retn
```
