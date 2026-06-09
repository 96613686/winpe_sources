# IsInGroup(ulong,bool)

- ea: `0x140030230`
- end: `0x14003077c`
- name: `?IsInGroup@@YA_NK_N@Z`
- size: `1356`
- prototype: `_BOOL8 __fastcall(DWORD nSubAuthority1)`
- caller_count: `14`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140001d54`
- `0x140001d90`
- `0x140002270`
- `0x140004690`
- `0x140005050`
- `0x14002eb20`
- `0x1400475f0`
- `0x140047f80`
- `0x140060460`
- `0x14006a3e0`
- `0x14006f180`
- `0x14009bf40`
- `0x14009cfa0`
- `0x1400a7280`

## callees

- `0x1400137c0`
- `0x1400138e0`
- `0x140013c60`
- `0x140030230`
- `0x140030e90`
- `0x140031730`
- `0x140070fcc`
- `0x140091560`
- `0x1400921dc`
- `0x1400cdbd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400305e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003066f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400305e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003066f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030537`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030537`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400304b0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400304b0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400304c8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400304c8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14003046d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14003046d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003031d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003031d`
- `VssTrace!__imp_VssTraceMessage` at `0x14003074a`
- `VssTrace!__imp_VssTraceMessage` at `0x14003074a`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400305ad`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400305ad`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140030375`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140030375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030592`

## string_xrefs

- `0x14003025f`: `base\stor\vss\modules\sec\security.cxx`
- `0x14003064f`: `AllocateAndInitializeSid`
- `0x1400306dd`: `CheckTokenMembership`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall IsInGroup(DWORD nSubAuthority1)
{
  __int64 v2; // rax
  int v3; // ebx
  __int64 i; // rbx
  void *v5; // rcx
  HANDLE v6; // rcx
  bool v7; // bl
  const wchar_t *v8; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  signed int v12; // eax
  unsigned int v13; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-198h] BYREF
  __int64 v15; // [rsp+68h] [rbp-190h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp-188h] BYREF
  void **v17; // [rsp+78h] [rbp-180h] BYREF
  HANDLE TokenHandle; // [rsp+80h] [rbp-178h] BYREF
  _DWORD v19[2]; // [rsp+90h] [rbp-168h] BYREF
  int v20; // [rsp+98h] [rbp-160h]
  const unsigned __int16 *v21; // [rsp+A0h] [rbp-158h]
  const unsigned __int16 *v22; // [rsp+A8h] [rbp-150h]
  unsigned int v23; // [rsp+B0h] [rbp-148h]
  unsigned int v24; // [rsp+B4h] [rbp-144h]
  const unsigned __int16 *v25; // [rsp+B8h] [rbp-140h]
  unsigned int v26; // [rsp+C0h] [rbp-138h]
  DWORD TickCount; // [rsp+C4h] [rbp-134h]
  int v28; // [rsp+C8h] [rbp-130h]
  __int128 v29; // [rsp+D0h] [rbp-128h]
  __int128 v30; // [rsp+E0h] [rbp-118h]
  __int64 v31; // [rsp+F0h] [rbp-108h]
  const unsigned __int16 *v32; // [rsp+100h] [rbp-F8h] BYREF
  const unsigned __int16 *v33; // [rsp+108h] [rbp-F0h]
  const unsigned __int16 *v34; // [rsp+110h] [rbp-E8h]
  int v35; // [rsp+118h] [rbp-E0h]
  int v36; // [rsp+11Ch] [rbp-DCh]
  int v37; // [rsp+120h] [rbp-D8h]
  LPVOID pv[15]; // [rsp+128h] [rbp-D0h] BYREF
  int v39; // [rsp+1A0h] [rbp-58h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+1C0h] [rbp-38h] BYREF

  v32 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v33 = L"IsInGroup";
  v34 = L"SECSECRC";
  v35 = 221;
  v36 = 11;
  v37 = 255;
  v39 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v20 = 0;
  v25 = L"IsInGroup";
  v21 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v22 = L"SECSECRC";
  v23 = 221;
  v24 = 11;
  TickCount = GetTickCount();
  v19[1] = -1;
  v28 = 255;
  v19[0] = 0;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  v15 = 0;
  if ( (int)VssGetTracingContextPerThread(&v15) < 0 || (int)VssSetTracingContextPerThread(v19) < 0 )
  {
    v2 = v31;
  }
  else
  {
    v2 = v15;
    v31 = v15;
  }
  if ( v2 )
    v26 = *(_DWORD *)(v2 + 48) + 1;
  else
    v26 = 0;
  v3 = 160;
  if ( v28 != 255 )
    v3 = v28;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v19, v24) )
    VssTraceMessage(v21, v22, v23, v26, v24, v25, L"ENTER", v3, 0);
  if ( HIBYTE(v39) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v5 = pv[i];
      if ( v5 )
      {
        CoTaskMemFree(v5);
        pv[i] = 0;
      }
    }
  }
  TokenHandle = (HANDLE)-1LL;
  v17 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  SidToCheck = 0;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, nSubAuthority1, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v32 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v33 = L"IsInGroup";
    v34 = L"SECSECRC";
    v35 = 249;
    v36 = 11;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateError(v19, &v32, v11, L"AllocateAndInitializeSid");
  }
  CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&v17);
  if ( GetCurrentAccessToken(1, 0, &TokenHandle) )
    v6 = TokenHandle;
  else
    v6 = 0;
  if ( !CheckTokenMembership(v6, SidToCheck, &IsMember) )
  {
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    v32 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v33 = L"IsInGroup";
    v34 = L"SECSECRC";
    v35 = 281;
    v36 = 11;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateError(v19, &v32, v13, L"CheckTokenMembership");
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( v20 < 0 )
    CVssFunctionTracer::ReThrow((CVssFunctionTracer *)v19);
  v7 = IsMember != 0;
  v8 = L"TRUE";
  if ( !IsMember )
    v8 = L"FALSE";
  CVssFunctionTracer::TraceInternalWithFormat((CVssFunctionTracer *)v19, L"RETURN", 0xAAu, L"Returning BOOL: %s", v8);
  v17 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  TokenHandle = (HANDLE)-1LL;
  v17 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
  CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v19);
  return v7;
}

```

## disassembly

```asm
0x140030230  mov     r11, rsp
0x140030233  mov     [r11+10h], rbx
0x140030237  mov     [r11+18h], rsi
0x14003023b  push    rdi
0x14003023c  push    r12
0x14003023e  push    r13
0x140030240  push    r14
0x140030242  push    r15
0x140030244  sub     rsp, 1D0h
0x14003024b  mov     rax, cs:__security_cookie
0x140030252  xor     rax, rsp
0x140030255  mov     [rsp+1F8h+var_30], rax
0x14003025d  mov     esi, ecx
0x14003025f  lea     r15, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140030266  mov     [r11-0F8h], r15
0x14003026d  lea     r12, aIsingroup; "IsInGroup"
0x140030274  mov     [r11-0F0h], r12
0x14003027b  lea     r13, aSecsecrc; "SECSECRC"
0x140030282  mov     [r11-0E8h], r13
0x140030289  mov     [rsp+1F8h+var_E0], 0DDh
0x140030294  mov     [rsp+1F8h+var_DC], 0Bh
0x14003029f  mov     [rsp+1F8h+var_D8], 0FFh
0x1400302aa  xor     r14d, r14d
0x1400302ad  mov     dword ptr [r11-58h], 1000000h
0x1400302b5  xor     edx, edx; Val
0x1400302b7  mov     r8d, 78h ; 'x'; Size
0x1400302bd  lea     rcx, [r11-0D0h]; void *
0x1400302c4  call    memset_0
0x1400302c9  mov     [rsp+1F8h+var_160], r14d
0x1400302d1  mov     rax, [rsp+1F8h+var_F0]
0x1400302d9  mov     [rsp+1F8h+var_140], rax
0x1400302e1  mov     rax, [rsp+1F8h+var_F8]
0x1400302e9  mov     [rsp+1F8h+var_158], rax
0x1400302f1  mov     rax, [rsp+1F8h+var_E8]
0x1400302f9  mov     [rsp+1F8h+var_150], rax
0x140030301  mov     eax, [rsp+1F8h+var_E0]
0x140030308  mov     [rsp+1F8h+var_148], eax
0x14003030f  mov     eax, [rsp+1F8h+var_DC]
0x140030316  mov     [rsp+1F8h+var_144], eax
0x14003031d  call    cs:__imp_GetTickCount
0x140030323  mov     [rsp+1F8h+var_134], eax
0x14003032a  mov     [rsp+1F8h+var_164], 0FFFFFFFFh
0x140030335  mov     eax, [rsp+1F8h+var_D8]
0x14003033c  mov     [rsp+1F8h+var_130], eax
0x140030343  mov     [rsp+1F8h+var_168], r14d
0x14003034b  mov     [rsp+1F8h+var_108], r14
0x140030353  xorps   xmm0, xmm0
0x140030356  movdqa  [rsp+1F8h+var_128], xmm0
0x14003035f  xorps   xmm1, xmm1
0x140030362  movdqa  [rsp+1F8h+var_118], xmm1
0x14003036b  mov     [rsp+1F8h+var_190], r14
0x140030370  lea     rcx, [rsp+1F8h+var_190]
0x140030375  call    cs:__imp_VssGetTracingContextPerThread
0x14003037b  test    eax, eax
0x14003037d  jns     loc_1400305A5
0x140030383  mov     rax, [rsp+1F8h+var_108]
0x14003038b  test    rax, rax
0x14003038e  jz      loc_1400305CD
0x140030394  mov     eax, [rax+30h]
0x140030397  inc     eax
0x140030399  mov     [rsp+1F8h+var_138], eax
0x1400303a0  mov     ebx, 0A0h
0x1400303a5  cmp     [rsp+1F8h+var_130], 0FFh
0x1400303b0  cmovnz  ebx, [rsp+1F8h+var_130]
0x1400303b8  mov     edx, [rsp+1F8h+var_144]; unsigned int
0x1400303bf  lea     rcx, [rsp+1F8h+var_168]; this
0x1400303c7  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x1400303cc  test    eax, eax
0x1400303ce  jnz     loc_1400306FD
0x1400303d4  cmp     [rsp+1F8h+var_55], r14b
0x1400303dc  jz      short loc_1400303FB
0x1400303de  mov     rbx, r14
0x1400303e1  mov     rcx, [rsp+rbx*8+1F8h+pv]; pv
0x1400303e9  test    rcx, rcx
0x1400303ec  jnz     loc_140030592
0x1400303f2  inc     rbx
0x1400303f5  cmp     rbx, 0Fh
0x1400303f9  jnz     short loc_1400303E1
0x1400303fb  mov     [rsp+1F8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140030407  lea     rdi, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x14003040e  mov     [rsp+1F8h+var_180], rdi
0x140030413  mov     [rsp+1F8h+SidToCheck], r14
0x140030418  mov     [rsp+1F8h+IsMember], r14d
0x14003041d  mov     dword ptr [rsp+1F8h+pIdentifierAuthority.Value], 0
0x140030428  mov     word ptr [rsp+1F8h+pIdentifierAuthority.Value+4], 500h
0x140030432  lea     rax, [rsp+1F8h+SidToCheck]
0x140030437  mov     [rsp+1F8h+pSid], rax; pSid
0x14003043c  mov     [rsp+1F8h+nSubAuthority7], r14d; nSubAuthority7
0x140030441  mov     [rsp+1F8h+nSubAuthority6], r14d; nSubAuthority6
0x140030446  mov     [rsp+1F8h+nSubAuthority5], r14d; nSubAuthority5
0x14003044b  mov     [rsp+1F8h+nSubAuthority4], r14d; nSubAuthority4
0x140030450  mov     [rsp+1F8h+nSubAuthority3], r14d; nSubAuthority3
0x140030455  mov     [rsp+1F8h+nSubAuthority2], r14d; nSubAuthority2
0x14003045a  mov     r9d, esi; nSubAuthority1
0x14003045d  mov     r8d, 20h ; ' '; nSubAuthority0
0x140030463  mov     dl, 2; nSubAuthorityCount
0x140030465  lea     rcx, [rsp+1F8h+pIdentifierAuthority]; pIdentifierAuthority
0x14003046d  call    cs:__imp_AllocateAndInitializeSid
0x140030473  test    eax, eax
0x140030475  jz      loc_1400305E1
0x14003047b  lea     rcx, [rsp+1F8h+var_180]
0x140030480  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x140030485  lea     r8, [rsp+1F8h+TokenHandle]; void **
0x14003048d  xor     edx, edx; bool
0x14003048f  mov     cl, 1; bool
0x140030491  call    ?GetCurrentAccessToken@@YA_N_N0PEAPEAX@Z; GetCurrentAccessToken(bool,bool,void * *)
0x140030496  lea     r8, [rsp+1F8h+IsMember]; IsMember
0x14003049b  mov     rdx, [rsp+1F8h+SidToCheck]; SidToCheck
0x1400304a0  test    al, al
0x1400304a2  jz      loc_140030755
0x1400304a8  mov     rcx, [rsp+1F8h+TokenHandle]; TokenHandle
0x1400304b0  call    cs:__imp_CheckTokenMembership
0x1400304b6  test    eax, eax
0x1400304b8  jz      loc_14003066F
0x1400304be  mov     rcx, [rsp+1F8h+SidToCheck]; pSid
0x1400304c3  test    rcx, rcx
0x1400304c6  jz      short loc_1400304CE
0x1400304c8  call    cs:__imp_FreeSid
0x1400304ce  cmp     [rsp+1F8h+var_160], 0
0x1400304d6  jl      loc_14003076E
0x1400304dc  cmp     [rsp+1F8h+IsMember], 0
0x1400304e1  jnz     loc_1400305DA
0x1400304e7  xor     bl, bl
0x1400304e9  lea     rcx, aFalse; "FALSE"
0x1400304f0  lea     rax, aTrue; "TRUE"
0x1400304f7  test    bl, bl
0x1400304f9  cmovz   rax, rcx
0x1400304fd  mov     qword ptr [rsp+1F8h+nSubAuthority2], rax
0x140030502  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x140030509  mov     r8d, 0AAh; unsigned int
0x14003050f  lea     rdx, aReturn; "RETURN"
0x140030516  lea     rcx, [rsp+1F8h+var_168]; this
0x14003051e  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140030523  nop
0x140030524  mov     [rsp+1F8h+var_180], rdi
0x140030529  mov     rcx, [rsp+1F8h+TokenHandle]; hObject
0x140030531  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140030535  jz      short loc_14003053D
0x140030537  call    cs:__imp_CloseHandle
0x14003053d  mov     [rsp+1F8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140030549  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x140030550  mov     [rsp+1F8h+var_180], rax
0x140030555  lea     rcx, [rsp+1F8h+var_168]; this
0x14003055d  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140030562  movzx   eax, bl
0x140030565  mov     rcx, [rsp+1F8h+var_30]
0x14003056d  xor     rcx, rsp; StackCookie
0x140030570  call    __security_check_cookie
0x140030575  lea     r11, [rsp+1F8h+var_28]
0x14003057d  mov     rbx, [r11+38h]
0x140030581  mov     rsi, [r11+40h]
0x140030585  mov     rsp, r11
0x140030588  pop     r15
0x14003058a  pop     r14
0x14003058c  pop     r13
0x14003058e  pop     r12
0x140030590  pop     rdi
0x140030591  retn
0x140030592  call    cs:__imp_CoTaskMemFree
0x140030598  mov     [rsp+rbx*8+1F8h+pv], r14
0x1400305a0  jmp     loc_1400303F2
0x1400305a5  lea     rcx, [rsp+1F8h+var_168]
0x1400305ad  call    cs:__imp_VssSetTracingContextPerThread
0x1400305b3  test    eax, eax
0x1400305b5  js      loc_140030383
0x1400305bb  mov     rax, [rsp+1F8h+var_190]
0x1400305c0  mov     [rsp+1F8h+var_108], rax
0x1400305c8  jmp     loc_14003038B
0x1400305cd  mov     [rsp+1F8h+var_138], r14d
0x1400305d5  jmp     loc_1400303A0
0x1400305da  mov     bl, 1
0x1400305dc  jmp     loc_1400304E9
0x1400305e1  call    cs:__imp_GetLastError
0x1400305e7  mov     ebx, eax
0x1400305e9  test    eax, eax
0x1400305eb  jle     short loc_1400305F6
0x1400305ed  movzx   ebx, ax
0x1400305f0  or      ebx, 80070000h
0x1400305f6  mov     [rsp+1F8h+var_F8], r15
0x1400305fe  mov     [rsp+1F8h+var_F0], r12
0x140030606  mov     [rsp+1F8h+var_E8], r13
0x14003060e  mov     [rsp+1F8h+var_E0], 0F9h
0x140030619  mov     [rsp+1F8h+var_DC], 0Bh
0x140030624  mov     [rsp+1F8h+var_D8], 0FFh
0x14003062f  mov     dword ptr [rsp+1A0h], 1000000h
0x14003063a  xor     edx, edx; Val
0x14003063c  mov     r8d, 78h ; 'x'; Size
0x140030642  lea     rcx, [rsp+1F8h+pv]; void *
0x14003064a  call    memset_0
0x14003064f  lea     r9, aAllocateandini; "AllocateAndInitializeSid"
0x140030656  mov     r8d, ebx
0x140030659  lea     rdx, [rsp+1F8h+var_F8]
0x140030661  lea     rcx, [rsp+1F8h+var_168]
0x140030669  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x14003066f  call    cs:__imp_GetLastError
0x140030675  mov     ebx, eax
0x140030677  test    eax, eax
0x140030679  jle     short loc_140030684
0x14003067b  movzx   ebx, ax
0x14003067e  or      ebx, 80070000h
0x140030684  mov     [rsp+1F8h+var_F8], r15
0x14003068c  mov     [rsp+1F8h+var_F0], r12
0x140030694  mov     [rsp+1F8h+var_E8], r13
0x14003069c  mov     [rsp+1F8h+var_E0], 119h
0x1400306a7  mov     [rsp+1F8h+var_DC], 0Bh
0x1400306b2  mov     [rsp+1F8h+var_D8], 0FFh
0x1400306bd  mov     dword ptr [rsp+1A0h], 1000000h
0x1400306c8  xor     edx, edx; Val
0x1400306ca  mov     r8d, 78h ; 'x'; Size
0x1400306d0  lea     rcx, [rsp+1F8h+pv]; void *
0x1400306d8  call    memset_0
0x1400306dd  lea     r9, aChecktokenmemb; "CheckTokenMembership"
0x1400306e4  mov     r8d, ebx
0x1400306e7  lea     rdx, [rsp+1F8h+var_F8]
0x1400306ef  lea     rcx, [rsp+1F8h+var_168]
0x1400306f7  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x1400306fd  mov     qword ptr [rsp+1F8h+nSubAuthority6], r14
0x140030702  mov     [rsp+1F8h+nSubAuthority5], ebx
0x140030706  lea     rax, aEnter; "ENTER"
0x14003070d  mov     qword ptr [rsp+1F8h+nSubAuthority4], rax
0x140030712  mov     rax, [rsp+1F8h+var_140]
0x14003071a  mov     qword ptr [rsp+1F8h+nSubAuthority3], rax
0x14003071f  mov     eax, [rsp+1F8h+var_144]
0x140030726  mov     [rsp+1F8h+nSubAuthority2], eax
0x14003072a  mov     r9d, [rsp+1F8h+var_138]
0x140030732  mov     r8d, [rsp+1F8h+var_148]
0x14003073a  mov     rdx, [rsp+1F8h+var_150]
0x140030742  mov     rcx, [rsp+1F8h+var_158]
0x14003074a  call    cs:__imp_VssTraceMessage
0x140030750  jmp     loc_1400303D4
0x140030755  xor     ecx, ecx
0x140030757  jmp     loc_1400304B0
0x14003075c  jmp     short loc_140030762
0x14003075e  jmp     short loc_140030762
0x140030760  jmp     short $+2
0x140030762  lea     rdi, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x140030769  jmp     loc_1400304BE
0x14003076e  lea     rcx, [rsp+1F8h+var_168]; this
0x140030776  call    ?ReThrow@CVssFunctionTracer@@QEAAXXZ; CVssFunctionTracer::ReThrow(void)
```
