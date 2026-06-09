# CreateProcessUserTask(ulong,ulong,int)

- ea: `0x18002351c`
- end: `0x1800237d9`
- name: `?CreateProcessUserTask@@YAXKKH@Z`
- size: `701`
- prototype: `void __fastcall(ULONG SessionId, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180054d20`
- `0x1800e6164`

## callees

- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180022f08`
- `0x18002351c`
- `0x180023860`
- `0x1800a3b60`
- `0x1800a400c`
- `0x1800a614c`
- `0x1800a63ec`
- `0x1800a716c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023792`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002366c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002366c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023662`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023662`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002361c`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002361c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800235c7`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800235c7`

## string_xrefs

- `0x18002357a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002354e`: `CreateProcessUserTask`
- `0x1800236a9`: `CreateProcessUserTask. SessionId %d, LogonId %d, %d. (0x%x)`
- `0x18002367e`: `Error - 0x%lx GetTokenInformation.`
- `0x180023638`: `Error - 0x%lx QueryUserToken.`
- `0x1800235e3`: `Error - 0x%lx WTSQueryUserToken.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CreateProcessUserTask(ULONG SessionId, int a2, int a3)
{
  WLIDSessionChangeData *v6; // rbx
  signed int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  char *v10; // rax
  void *v11; // rcx
  void (*v12)(void *, unsigned __int8, unsigned __int8); // rdx
  const unsigned __int16 *ReturnLength; // [rsp+20h] [rbp-79h]
  PDWORD ReturnLengtha; // [rsp+20h] [rbp-79h]
  signed int v15; // [rsp+40h] [rbp-59h] BYREF
  void *phToken; // [rsp+48h] [rbp-51h] BYREF
  DWORD v17; // [rsp+50h] [rbp-49h] BYREF
  char *v18; // [rsp+58h] [rbp-41h]
  _QWORD v19[4]; // [rsp+60h] [rbp-39h] BYREF
  int TokenInformation; // [rsp+80h] [rbp-19h] BYREF
  __int128 v21; // [rsp+84h] [rbp-15h]
  __int128 v22; // [rsp+94h] [rbp-5h]
  __int128 v23; // [rsp+A4h] [rbp+Bh]
  int v24; // [rsp+B4h] [rbp+1Bh]

  v15 = 0;
  v19[0] = "CreateProcessUserTask";
  v19[1] = &v15;
  v19[2] = 0;
  v19[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "CreateProcessUserTask",
    (const char *)0x2685,
    0,
    ReturnLength);
  phToken = 0;
  v6 = 0;
  TokenInformation = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v17 = 0;
  if ( a2 == 5 )
  {
    if ( (unsigned __int8)IsWTSFreeMemoryPresent() )
    {
      if ( !WTSQueryUserToken(SessionId, &phToken) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v8 = L"Error - 0x%lx WTSQueryUserToken.";
        v9 = 9879;
LABEL_7:
        v15 = LastError;
LABEL_8:
        LODWORD(ReturnLengtha) = LastError;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          v9,
          v8,
          ReturnLengtha);
        goto LABEL_25;
      }
    }
    else
    {
      if ( !(unsigned __int8)IsQueryUserTokenPresent() )
        goto LABEL_25;
      if ( !(unsigned int)QueryUserToken(SessionId, &phToken) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v8 = L"Error - 0x%lx QueryUserToken.";
        v9 = 9890;
        goto LABEL_7;
      }
    }
    if ( !GetTokenInformation(phToken, TokenStatistics, &TokenInformation, 0x38u, &v17) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = L"Error - 0x%lx GetTokenInformation.";
      v9 = 9902;
      goto LABEL_7;
    }
  }
  LODWORD(ReturnLengtha) = SessionId;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    0x26B4u,
    L"CreateProcessUserTask. SessionId %d, LogonId %d, %d. (0x%x)",
    ReturnLengtha,
    DWORD2(v21),
    DWORD1(v21),
    v15);
  v10 = (char *)operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
  v6 = (WLIDSessionChangeData *)v10;
  v18 = v10;
  if ( v10 )
  {
    v11 = phToken;
    *(_QWORD *)v10 = &ATL::CAccessToken::`vftable';
    *((_QWORD *)v10 + 1) = 0;
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = 0;
    *((_DWORD *)v10 + 8) = SessionId;
    *(_QWORD *)(v10 + 36) = *(_QWORD *)((char *)&v21 + 4);
    *((_DWORD *)v10 + 11) = a3;
    *((_QWORD *)v10 + 1) = v11;
    *((_QWORD *)v10 + 6) = -1;
    v18 = v10;
    phToken = 0;
    if ( g_lShutdownInProgress )
      goto LABEL_27;
    v12 = (void (*)(void *, unsigned __int8, unsigned __int8))ProcessUserLogon;
    if ( a2 != 5 )
      v12 = (void (*)(void *, unsigned __int8, unsigned __int8))ProcessUserLogoff;
    LastError = CWLIDTimerQueue::QueueWorkItem((CWLIDTimerQueue *)g_WLIDTimerQueue, v12, v10, 0, 0x118u);
    v15 = LastError;
    if ( LastError < 0 )
    {
      v8 = L"Error - 0x%lx QueueWorkItem.";
      v9 = 9943;
      goto LABEL_8;
    }
  }
  v6 = 0;
LABEL_25:
  if ( phToken )
    CloseHandle(phToken);
LABEL_27:
  if ( v6 )
  {
    WLIDSessionChangeData::~WLIDSessionChangeData(v6);
    operator delete(v6);
  }
  CTraceFuncW<long>::~CTraceFuncW<long>(v19);
}

```

## disassembly

```asm
0x18002351c  push    rbp
0x18002351e  push    rbx
0x18002351f  push    rsi
0x180023520  push    rdi
0x180023521  push    r12
0x180023523  push    r14
0x180023525  lea     rbp, [rsp-2Fh]
0x18002352a  sub     rsp, 0C8h
0x180023531  mov     rax, cs:__security_cookie
0x180023538  xor     rax, rsp
0x18002353b  mov     [rbp+57h+var_38], rax
0x18002353f  mov     esi, r8d
0x180023542  mov     r14d, edx
0x180023545  mov     edi, ecx
0x180023547  mov     [rbp+57h+var_B0], 0
0x18002354e  lea     rdx, aCreateprocessu_0; "CreateProcessUserTask"
0x180023555  mov     [rbp+57h+var_90], rdx
0x180023559  lea     rax, [rbp+57h+var_B0]
0x18002355d  mov     [rbp+57h+var_88], rax
0x180023561  mov     [rbp+57h+var_80], 0
0x180023569  mov     [rbp+57h+var_78], 0
0x180023571  xor     r9d, r9d; unsigned int
0x180023574  mov     r8d, 2685h; char *
0x18002357a  lea     r12, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180023581  mov     rcx, r12; this
0x180023584  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180023589  nop
0x18002358a  mov     [rbp+57h+phToken], 0
0x180023592  xor     ebx, ebx
0x180023594  mov     [rbp+57h+TokenInformation], ebx
0x180023597  xorps   xmm0, xmm0
0x18002359a  xor     eax, eax
0x18002359c  movups  [rbp+57h+var_6C], xmm0
0x1800235a0  movups  [rbp+57h+var_5C], xmm0
0x1800235a4  movups  [rbp+57h+var_4C], xmm0
0x1800235a8  mov     [rbp+57h+var_3C], eax
0x1800235ab  mov     [rbp+57h+var_A0], eax
0x1800235ae  cmp     r14d, 5
0x1800235b2  jnz     loc_180023690
0x1800235b8  call    IsWTSFreeMemoryPresent
0x1800235bd  test    al, al
0x1800235bf  jz      short loc_180023609
0x1800235c1  lea     rdx, [rbp+57h+phToken]; phToken
0x1800235c5  mov     ecx, edi; SessionId
0x1800235c7  call    cs:__imp_WTSQueryUserToken
0x1800235cd  test    eax, eax
0x1800235cf  jnz     short loc_180023647
0x1800235d1  call    cs:__imp_GetLastError
0x1800235d7  test    eax, eax
0x1800235d9  jle     short loc_1800235E3
0x1800235db  movzx   eax, ax
0x1800235de  or      eax, 80070000h
0x1800235e3  lea     r9, aError0xLxWtsqu; "Error - 0x%lx WTSQueryUserToken."
0x1800235ea  mov     r8d, 2697h; unsigned int
0x1800235f0  mov     [rbp+57h+var_B0], eax
0x1800235f3  mov     dword ptr [rsp+0F0h+ReturnLength], eax
0x1800235f7  mov     rdx, r12; char *
0x1800235fa  mov     ecx, 2; unsigned __int8
0x1800235ff  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180023604  jmp     loc_180023789
0x180023609  call    IsQueryUserTokenPresent
0x18002360e  test    al, al
0x180023610  jz      loc_180023789
0x180023616  lea     rdx, [rbp+57h+phToken]
0x18002361a  mov     ecx, edi
0x18002361c  call    cs:__imp_QueryUserToken
0x180023622  test    eax, eax
0x180023624  jnz     short loc_180023647
0x180023626  call    cs:__imp_GetLastError
0x18002362c  test    eax, eax
0x18002362e  jle     short loc_180023638
0x180023630  movzx   eax, ax
0x180023633  or      eax, 80070000h
0x180023638  lea     r9, aError0xLxQuery; "Error - 0x%lx QueryUserToken."
0x18002363f  mov     r8d, 26A2h
0x180023645  jmp     short loc_1800235F0
0x180023647  lea     rax, [rbp+57h+var_A0]
0x18002364b  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x180023650  mov     r9d, 38h ; '8'; TokenInformationLength
0x180023656  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002365a  lea     edx, [r9-2Eh]; TokenInformationClass
0x18002365e  mov     rcx, [rbp+57h+phToken]; TokenHandle
0x180023662  call    cs:__imp_GetTokenInformation
0x180023668  test    eax, eax
0x18002366a  jnz     short loc_180023690
0x18002366c  call    cs:__imp_GetLastError
0x180023672  test    eax, eax
0x180023674  jle     short loc_18002367E
0x180023676  movzx   eax, ax
0x180023679  or      eax, 80070000h
0x18002367e  lea     r9, aError0xLxGetto; "Error - 0x%lx GetTokenInformation."
0x180023685  mov     r8d, 26AEh
0x18002368b  jmp     loc_1800235F0
0x180023690  mov     eax, [rbp+57h+var_B0]
0x180023693  mov     [rsp+0F0h+var_B8], eax
0x180023697  mov     eax, dword ptr [rbp+57h+var_6C+4]
0x18002369a  mov     [rsp+0F0h+var_C0], eax
0x18002369e  mov     eax, dword ptr [rbp+57h+var_6C+8]
0x1800236a1  mov     [rsp+0F0h+var_C8], eax
0x1800236a5  mov     dword ptr [rsp+0F0h+ReturnLength], edi
0x1800236a9  lea     r9, aCreateprocessu_1; "CreateProcessUserTask. SessionId %d, Lo"...
0x1800236b0  mov     r8d, 26B4h; unsigned int
0x1800236b6  mov     rdx, r12; char *
0x1800236b9  mov     ecx, 2; unsigned __int8
0x1800236be  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800236c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800236ca  mov     ecx, 38h ; '8'; unsigned __int64
0x1800236cf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800236d4  mov     rbx, rax
0x1800236d7  mov     [rbp+57h+var_98], rax
0x1800236db  test    rax, rax
0x1800236de  jz      loc_180023787
0x1800236e4  mov     rcx, [rbp+57h+phToken]
0x1800236e8  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x1800236ef  mov     [rbx], rax
0x1800236f2  mov     qword ptr [rbx+8], 0
0x1800236fa  mov     qword ptr [rbx+10h], 0
0x180023702  mov     qword ptr [rbx+18h], 0
0x18002370a  mov     [rbx+20h], edi
0x18002370d  mov     rax, qword ptr [rbp+57h+var_6C+4]
0x180023711  mov     [rbx+24h], rax
0x180023715  mov     [rbx+2Ch], esi
0x180023718  mov     [rbx+8], rcx
0x18002371c  mov     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFFFh
0x180023724  mov     [rbp+57h+var_98], rbx
0x180023728  test    rbx, rbx
0x18002372b  jz      short loc_180023789
0x18002372d  mov     [rbp+57h+phToken], 0
0x180023735  cmp     cs:?g_lShutdownInProgress@@3JA, 0; long g_lShutdownInProgress
0x18002373c  jnz     short loc_180023799
0x18002373e  lea     rax, ?ProcessUserLogoff@@YAXPEAXEE@Z; ProcessUserLogoff(void *,uchar,uchar)
0x180023745  lea     rdx, ?ProcessUserLogon@@YAXPEAXEE@Z; ProcessUserLogon(void *,uchar,uchar)
0x18002374c  cmp     r14d, 5
0x180023750  cmovnz  rdx, rax; void (*)(void *, unsigned __int8, unsigned __int8)
0x180023754  mov     dword ptr [rsp+0F0h+ReturnLength], 118h; unsigned int
0x18002375c  xor     r9d, r9d; unsigned int
0x18002375f  mov     r8, rbx; void *
0x180023762  lea     rcx, ?g_WLIDTimerQueue@@3VCWLIDTimerQueue@@A; this
0x180023769  call    ?QueueWorkItem@CWLIDTimerQueue@@UEAAJP6AXPEAXEE@Z0KK@Z; CWLIDTimerQueue::QueueWorkItem(void (*)(void *,uchar,uchar),void *,ulong,ulong)
0x18002376e  mov     [rbp+57h+var_B0], eax
0x180023771  test    eax, eax
0x180023773  jns     short loc_180023787
0x180023775  lea     r9, aError0xLxQueue; "Error - 0x%lx QueueWorkItem."
0x18002377c  mov     r8d, 26D7h
0x180023782  jmp     loc_1800235F3
0x180023787  xor     ebx, ebx
0x180023789  mov     rcx, [rbp+57h+phToken]; hObject
0x18002378d  test    rcx, rcx
0x180023790  jz      short loc_180023799
0x180023792  call    cs:__imp_CloseHandle
0x180023798  nop
0x180023799  test    rbx, rbx
0x18002379c  jz      short loc_1800237B4
0x18002379e  mov     rcx, rbx; this
0x1800237a1  call    ??1WLIDSessionChangeData@@QEAA@XZ; WLIDSessionChangeData::~WLIDSessionChangeData(void)
0x1800237a6  mov     edx, 38h ; '8'
0x1800237ab  mov     rcx, rbx; Block
0x1800237ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800237b3  nop
0x1800237b4  lea     rcx, [rbp+57h+var_90]
0x1800237b8  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800237bd  mov     rcx, [rbp+57h+var_38]
0x1800237c1  xor     rcx, rsp; StackCookie
0x1800237c4  call    __security_check_cookie
0x1800237c9  add     rsp, 0C8h
0x1800237d0  pop     r14
0x1800237d2  pop     r12
0x1800237d4  pop     rdi
0x1800237d5  pop     rsi
0x1800237d6  pop     rbx
0x1800237d7  pop     rbp
0x1800237d8  retn
```
