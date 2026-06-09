# CVssSidCollection::IsClientValidRequestor(void)

- ea: `0x14001940c`
- end: `0x140019750`
- name: `?IsClientValidRequestor@CVssSidCollection@@QEAA_NXZ`
- size: `836`
- prototype: `bool __fastcall(PSECURITY_DESCRIPTOR *this)`
- caller_count: `10`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001d90`
- `0x140005050`
- `0x140018db0`
- `0x140019eb0`
- `0x14001d810`
- `0x1400844c0`
- `0x140085360`
- `0x14009e260`
- `0x14009ea80`
- `0x14009f9c0`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x1400138e0`
- `0x140013cb0`
- `0x14001940c`
- `0x140028b48`
- `0x140030e90`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019702`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019702`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x14001964c`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x14001964c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400194b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400194b8`
- `VssTrace!__imp_VssTraceMessage` at `0x14001958c`
- `VssTrace!__imp_VssTraceMessage` at `0x14001958c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140019504`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140019504`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400194f6`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400194f6`

## string_xrefs

- `0x14001943e`: `base\stor\vss\modules\sec\security.cxx`
- `0x140019449`: `CVssSidCollection::IsClientValidRequestor`
- `0x14001965a`: `CVssSidCollection::IsClientValidRequestor`
- `0x14001969e`: `AccessCheck`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall CVssSidCollection::IsClientValidRequestor(PSECURITY_DESCRIPTOR *this)
{
  int v2; // eax
  __int64 v3; // rcx
  int v4; // ebx
  bool v5; // bl
  const wchar_t *v6; // rax
  WINBOOL AccessStatus; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v9; // [rsp+58h] [rbp-A8h] BYREF
  DWORD GrantedAccess; // [rsp+60h] [rbp-A0h] BYREF
  DWORD PrivilegeSetLength; // [rsp+64h] [rbp-9Ch] BYREF
  void **v12; // [rsp+68h] [rbp-98h]
  HANDLE ClientToken; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v14[4]; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v15; // [rsp+90h] [rbp-70h]
  const unsigned __int16 *v16; // [rsp+98h] [rbp-68h]
  unsigned int v17; // [rsp+A0h] [rbp-60h]
  int v18; // [rsp+A4h] [rbp-5Ch]
  const wchar_t *v19; // [rsp+A8h] [rbp-58h]
  unsigned int v20; // [rsp+B0h] [rbp-50h]
  DWORD TickCount; // [rsp+B4h] [rbp-4Ch]
  int v22; // [rsp+B8h] [rbp-48h]
  __int128 v23; // [rsp+C0h] [rbp-40h]
  __int128 v24; // [rsp+D0h] [rbp-30h]
  __int64 v25; // [rsp+E0h] [rbp-20h]
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v27; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v28; // [rsp+100h] [rbp+0h]
  int v29; // [rsp+108h] [rbp+8h]
  int v30; // [rsp+10Ch] [rbp+Ch]
  int v31; // [rsp+110h] [rbp+10h]
  _BYTE v32[120]; // [rsp+118h] [rbp+18h] BYREF
  int v33; // [rsp+190h] [rbp+90h]
  _GENERIC_MAPPING GenericMapping; // [rsp+198h] [rbp+98h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+1A8h] [rbp+A8h] BYREF

  v26 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v27 = L"CVssSidCollection::IsClientValidRequestor";
  v28 = L"SECSECRC";
  v29 = 1733;
  v30 = 11;
  v31 = 255;
  v33 = 0x1000000;
  memset_0(v32, 0, sizeof(v32));
  v14[2] = 0;
  v19 = L"CVssSidCollection::IsClientValidRequestor";
  v15 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v16 = v28;
  v17 = v29;
  v18 = v30;
  TickCount = GetTickCount();
  v14[1] = -1;
  v22 = v31;
  v14[0] = 0;
  v25 = 0;
  v23 = 0;
  v24 = 0;
  v9 = 0;
  if ( (int)VssGetTracingContextPerThread(&v9) < 0 )
  {
    v3 = v25;
  }
  else
  {
    v2 = VssSetTracingContextPerThread(v14);
    v3 = v25;
    if ( v2 >= 0 )
      v3 = v9;
    v25 = v3;
  }
  if ( v3 )
    v20 = *(_DWORD *)(v3 + 48) + 1;
  else
    v20 = 0;
  v4 = 160;
  if ( v22 != 255 )
    v4 = v22;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v14) )
    VssTraceMessage(v15, v16, v17, v20, v18, v19, L"ENTER", v4, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v26);
  v12 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  GenericMapping = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  GrantedAccess = 0;
  AccessStatus = 0;
  ClientToken = (HANDLE)-1LL;
  GetCurrentAccessToken(1, 1, &ClientToken);
  GenericMapping.GenericRead = 0x20000;
  GenericMapping.GenericWrite = 0x20000;
  GenericMapping.GenericExecute = 0x20000;
  GenericMapping.GenericAll = 2031616;
  if ( !AccessCheck(
          this[5],
          ClientToken,
          1u,
          &GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    v26 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v27 = L"CVssSidCollection::IsClientValidRequestor";
    v28 = L"SECSECRC";
    v29 = 1756;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    CVssFunctionTracer::TranslateWin32Error(v14, &v26, L"AccessCheck");
  }
  v5 = AccessStatus != 0;
  v6 = L"TRUE";
  if ( !AccessStatus )
    v6 = L"FALSE";
  CVssFunctionTracer::TraceInternalWithFormat((CVssFunctionTracer *)v14, L"RETURN", 0xAAu, L"Returning BOOL: %s", v6);
  v12 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( ClientToken != (HANDLE)-1LL )
    CloseHandle(ClientToken);
  ClientToken = (HANDLE)-1LL;
  v12 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
  CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v14);
  return v5;
}

```

## disassembly

```asm
0x14001940c  mov     [rsp-8+arg_8], rbx
0x140019411  mov     [rsp-8+arg_10], rdi
0x140019416  push    rbp
0x140019417  push    r12
0x140019419  push    r13
0x14001941b  lea     rbp, [rsp-0D0h]
0x140019423  sub     rsp, 1D0h
0x14001942a  mov     rax, cs:__security_cookie
0x140019431  xor     rax, rsp
0x140019434  mov     [rbp+0E0h+var_20], rax
0x14001943b  mov     rdi, rcx
0x14001943e  lea     r13, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140019445  mov     [rbp+0E0h+var_F0], r13
0x140019449  lea     rax, aCvsssidcollect_2; "CVssSidCollection::IsClientValidRequest"...
0x140019450  mov     [rbp+0E0h+var_E8], rax
0x140019454  lea     rax, aSecsecrc; "SECSECRC"
0x14001945b  mov     [rbp+0E0h+var_E0], rax
0x14001945f  mov     [rbp+0E0h+var_D8], 6C5h
0x140019466  mov     [rbp+0E0h+var_D4], 0Bh
0x14001946d  mov     [rbp+0E0h+var_D0], 0FFh
0x140019474  mov     [rbp+0E0h+var_50], 1000000h
0x14001947e  xor     edx, edx; Val
0x140019480  lea     r8d, [rdx+78h]; Size
0x140019484  lea     rcx, [rbp+0E0h+var_C8]; void *
0x140019488  call    memset_0
0x14001948d  mov     [rbp+0E0h+var_158], 0
0x140019494  mov     rax, [rbp+0E0h+var_E8]
0x140019498  mov     [rbp+0E0h+var_138], rax
0x14001949c  mov     rax, [rbp+0E0h+var_F0]
0x1400194a0  mov     [rbp+0E0h+var_150], rax
0x1400194a4  mov     rax, [rbp+0E0h+var_E0]
0x1400194a8  mov     [rbp+0E0h+var_148], rax
0x1400194ac  mov     eax, [rbp+0E0h+var_D8]
0x1400194af  mov     [rbp+0E0h+var_140], eax
0x1400194b2  mov     eax, [rbp+0E0h+var_D4]
0x1400194b5  mov     [rbp+0E0h+var_13C], eax
0x1400194b8  call    cs:__imp_GetTickCount
0x1400194be  mov     [rbp+0E0h+var_12C], eax
0x1400194c1  mov     [rbp+0E0h+var_15C], 0FFFFFFFFh
0x1400194c8  mov     eax, [rbp+0E0h+var_D0]
0x1400194cb  mov     [rbp+0E0h+var_128], eax
0x1400194ce  mov     [rbp+0E0h+var_160], 0
0x1400194d5  mov     [rbp+0E0h+var_100], 0
0x1400194dd  xorps   xmm0, xmm0
0x1400194e0  movups  [rbp+0E0h+var_120], xmm0
0x1400194e4  movups  [rbp+0E0h+var_110], xmm0
0x1400194e8  mov     [rsp+1E0h+var_188], 0
0x1400194f1  lea     rcx, [rsp+1E0h+var_188]
0x1400194f6  call    cs:__imp_VssGetTracingContextPerThread
0x1400194fc  test    eax, eax
0x1400194fe  js      short loc_14001951C
0x140019500  lea     rcx, [rbp+0E0h+var_160]
0x140019504  call    cs:__imp_VssSetTracingContextPerThread
0x14001950a  mov     rcx, [rbp+0E0h+var_100]
0x14001950e  test    eax, eax
0x140019510  cmovns  rcx, [rsp+1E0h+var_188]
0x140019516  mov     [rbp+0E0h+var_100], rcx
0x14001951a  jmp     short loc_140019520
0x14001951c  mov     rcx, [rbp+0E0h+var_100]
0x140019520  test    rcx, rcx
0x140019523  jz      short loc_14001952F
0x140019525  mov     eax, [rcx+30h]
0x140019528  inc     eax
0x14001952a  mov     [rbp+0E0h+var_130], eax
0x14001952d  jmp     short loc_140019536
0x14001952f  mov     [rbp+0E0h+var_130], 0
0x140019536  mov     ebx, 0A0h
0x14001953b  cmp     [rbp+0E0h+var_128], 0FFh
0x140019542  cmovnz  ebx, [rbp+0E0h+var_128]
0x140019546  lea     rcx, [rbp+0E0h+var_160]; this
0x14001954a  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14001954f  test    eax, eax
0x140019551  jz      short loc_140019592
0x140019553  mov     [rsp+1E0h+var_1A0], 0
0x14001955c  mov     dword ptr [rsp+1E0h+AccessStatus], ebx
0x140019560  lea     rax, aEnter; "ENTER"
0x140019567  mov     [rsp+1E0h+GrantedAccess], rax
0x14001956c  mov     rax, [rbp+0E0h+var_138]
0x140019570  mov     [rsp+1E0h+PrivilegeSetLength], rax
0x140019575  mov     eax, [rbp+0E0h+var_13C]
0x140019578  mov     dword ptr [rsp+1E0h+PrivilegeSet], eax
0x14001957c  mov     r9d, [rbp+0E0h+var_130]
0x140019580  mov     r8d, [rbp+0E0h+var_140]
0x140019584  mov     rdx, [rbp+0E0h+var_148]
0x140019588  mov     rcx, [rbp+0E0h+var_150]
0x14001958c  call    cs:__imp_VssTraceMessage
0x140019592  lea     rcx, [rbp+0E0h+var_F0]; this
0x140019596  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14001959b  nop
0x14001959c  lea     r12, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x1400195a3  mov     [rsp+1E0h+var_178], r12
0x1400195a8  xorps   xmm0, xmm0
0x1400195ab  movups  xmmword ptr [rbp+0E0h+GenericMapping.GenericRead], xmm0
0x1400195b2  xorps   xmm1, xmm1
0x1400195b5  xor     eax, eax
0x1400195b7  movups  xmmword ptr [rbp+0E0h+var_38.PrivilegeCount], xmm1
0x1400195be  mov     [rbp+0E0h+var_38.Privilege.Attributes], eax
0x1400195c4  mov     [rsp+1E0h+var_17C], 14h
0x1400195cc  mov     [rsp+1E0h+var_180], eax
0x1400195d0  mov     [rsp+1E0h+var_190], eax
0x1400195d4  mov     [rsp+1E0h+ClientToken], 0FFFFFFFFFFFFFFFFh
0x1400195dd  lea     r8, [rsp+1E0h+ClientToken]; void **
0x1400195e2  mov     dl, 1; bool
0x1400195e4  mov     cl, dl; bool
0x1400195e6  call    ?GetCurrentAccessToken@@YA_N_N0PEAPEAX@Z; GetCurrentAccessToken(bool,bool,void * *)
0x1400195eb  mov     eax, 20000h
0x1400195f0  mov     [rbp+0E0h+GenericMapping.GenericRead], eax
0x1400195f6  mov     [rbp+0E0h+GenericMapping.GenericWrite], eax
0x1400195fc  mov     [rbp+0E0h+GenericMapping.GenericExecute], eax
0x140019602  mov     [rbp+0E0h+GenericMapping.GenericAll], 1F0000h
0x14001960c  lea     rax, [rsp+1E0h+var_190]
0x140019611  mov     [rsp+1E0h+AccessStatus], rax; AccessStatus
0x140019616  lea     rax, [rsp+1E0h+var_180]
0x14001961b  mov     [rsp+1E0h+GrantedAccess], rax; GrantedAccess
0x140019620  lea     rax, [rsp+1E0h+var_17C]
0x140019625  mov     [rsp+1E0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x14001962a  lea     rax, [rbp+0E0h+var_38]
0x140019631  mov     [rsp+1E0h+PrivilegeSet], rax; PrivilegeSet
0x140019636  lea     r9, [rbp+0E0h+GenericMapping]; GenericMapping
0x14001963d  mov     r8d, 1; DesiredAccess
0x140019643  mov     rdx, [rsp+1E0h+ClientToken]; ClientToken
0x140019648  mov     rcx, [rdi+28h]; pSecurityDescriptor
0x14001964c  call    cs:__imp_AccessCheck
0x140019652  test    eax, eax
0x140019654  jnz     short loc_1400196B3
0x140019656  mov     [rbp+0E0h+var_F0], r13
0x14001965a  lea     rax, aCvsssidcollect_2; "CVssSidCollection::IsClientValidRequest"...
0x140019661  mov     [rbp+0E0h+var_E8], rax
0x140019665  lea     rax, aSecsecrc; "SECSECRC"
0x14001966c  mov     [rbp+0E0h+var_E0], rax
0x140019670  mov     [rbp+0E0h+var_D8], 6DCh
0x140019677  mov     [rbp+0E0h+var_D4], 0Bh
0x14001967e  mov     [rbp+0E0h+var_D0], 0FFh
0x140019685  mov     [rbp+0E0h+var_50], 1000000h
0x14001968f  xor     edx, edx; Val
0x140019691  lea     r8d, [rdx+78h]; Size
0x140019695  lea     rcx, [rbp+0E0h+var_C8]; void *
0x140019699  call    memset_0
0x14001969e  lea     r8, aAccesscheck; "AccessCheck"
0x1400196a5  lea     rdx, [rbp+0E0h+var_F0]
0x1400196a9  lea     rcx, [rbp+0E0h+var_160]
0x1400196ad  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400196b3  cmp     [rsp+1E0h+var_190], 0
0x1400196b8  setnz   bl
0x1400196bb  lea     rcx, aFalse; "FALSE"
0x1400196c2  lea     rax, aTrue; "TRUE"
0x1400196c9  test    bl, bl
0x1400196cb  cmovz   rax, rcx
0x1400196cf  mov     [rsp+1E0h+PrivilegeSet], rax
0x1400196d4  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1400196db  mov     r8d, 0AAh; unsigned int
0x1400196e1  lea     rdx, aReturn; "RETURN"
0x1400196e8  lea     rcx, [rbp+0E0h+var_160]; this
0x1400196ec  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400196f1  nop
0x1400196f2  mov     [rsp+1E0h+var_178], r12
0x1400196f7  mov     rcx, [rsp+1E0h+ClientToken]; hObject
0x1400196fc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140019700  jz      short loc_140019708
0x140019702  call    cs:__imp_CloseHandle
0x140019708  mov     [rsp+1E0h+ClientToken], 0FFFFFFFFFFFFFFFFh
0x140019711  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x140019718  mov     [rsp+1E0h+var_178], rax
0x14001971d  lea     rcx, [rbp+0E0h+var_160]; this
0x140019721  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140019726  mov     al, bl
0x140019728  mov     rcx, [rbp+0E0h+var_20]
0x14001972f  xor     rcx, rsp; StackCookie
0x140019732  call    __security_check_cookie
0x140019737  lea     r11, [rsp+1E0h+var_10]
0x14001973f  mov     rbx, [r11+28h]
0x140019743  mov     rdi, [r11+30h]
0x140019747  mov     rsp, r11
0x14001974a  pop     r13
0x14001974c  pop     r12
0x14001974e  pop     rbp
0x14001974f  retn
```
