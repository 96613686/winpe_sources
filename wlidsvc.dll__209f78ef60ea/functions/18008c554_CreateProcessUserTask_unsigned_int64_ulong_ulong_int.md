# CreateProcessUserTask(unsigned __int64 &,ulong,ulong,int)

- ea: `0x18008c554`
- end: `0x18008c798`
- name: `?CreateProcessUserTask@@YAXAEA_KKKH@Z`
- size: `580`
- prototype: `void __fastcall(unsigned __int64 *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180054d20`
- `0x1800e6164`

## callees

- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180022f08`
- `0x180023860`
- `0x18008c554`
- `0x18008c7a0`
- `0x1800a3b60`
- `0x1800a400c`
- `0x1800a716c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c617`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008c60d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008c60d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18008c5eb`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18008c5eb`

## string_xrefs

- `0x18008c5ad`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18008c63d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18008c670`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18008c738`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18008c589`: `CreateProcessUserTask`
- `0x18008c630`: `Error - 0x%lx GetTokenInformation.`
- `0x18008c663`: `CreateProcessUserTask. LogonId %d, %d. (0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CreateProcessUserTask(unsigned __int64 *a1, int a2, int a3, int a4)
{
  signed int LastError; // eax
  char *v9; // rax
  WLIDSessionChangeData *v10; // rbx
  HANDLE v11; // rcx
  void (*v12)(void *, unsigned __int8, unsigned __int8); // rdx
  int v13; // eax
  const unsigned __int16 *ReturnLength; // [rsp+20h] [rbp-79h]
  PDWORD ReturnLengtha; // [rsp+20h] [rbp-79h]
  PDWORD ReturnLengthb; // [rsp+20h] [rbp-79h]
  signed int v17; // [rsp+40h] [rbp-59h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-51h] BYREF
  DWORD v19; // [rsp+50h] [rbp-49h] BYREF
  char *v20; // [rsp+58h] [rbp-41h]
  _QWORD v21[4]; // [rsp+60h] [rbp-39h] BYREF
  int TokenInformation; // [rsp+80h] [rbp-19h] BYREF
  __int128 v23; // [rsp+84h] [rbp-15h]
  __int128 v24; // [rsp+94h] [rbp-5h]
  __int128 v25; // [rsp+A4h] [rbp+Bh]
  int v26; // [rsp+B4h] [rbp+1Bh]

  v17 = 0;
  v21[0] = "CreateProcessUserTask";
  v21[1] = &v17;
  v21[2] = 0;
  v21[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "CreateProcessUserTask",
    (const char *)0x26E6,
    0,
    ReturnLength);
  TokenInformation = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v19 = 0;
  TokenHandle = 0;
  if ( a3 == 5 )
  {
    TokenHandle = 0;
    v17 = UMgrQueryUserToken(*a1, &TokenHandle);
    if ( !GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &v19) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v17 = LastError;
      LODWORD(ReturnLengtha) = LastError;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x26F5u,
        L"Error - 0x%lx GetTokenInformation.",
        ReturnLengtha);
    }
  }
  LODWORD(ReturnLengtha) = DWORD2(v23);
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    0x26F9u,
    L"CreateProcessUserTask. LogonId %d, %d. (0x%x)",
    ReturnLengtha,
    DWORD1(v23),
    v17);
  if ( !g_lShutdownInProgress )
  {
    v9 = (char *)operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
    v10 = (WLIDSessionChangeData *)v9;
    v20 = v9;
    if ( !v9 )
      goto LABEL_12;
    v11 = TokenHandle;
    TokenHandle = 0;
    *(_QWORD *)v9 = &ATL::CAccessToken::`vftable';
    *((_QWORD *)v9 + 1) = 0;
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
    *((_DWORD *)v9 + 8) = a2;
    *(_QWORD *)(v9 + 36) = *(_QWORD *)((char *)&v23 + 4);
    *((_DWORD *)v9 + 11) = a4;
    *((_QWORD *)v9 + 1) = v11;
    *((_QWORD *)v9 + 6) = -1;
    v20 = v9;
    v12 = (void (*)(void *, unsigned __int8, unsigned __int8))ProcessUserLogon;
    if ( a3 != 5 )
      v12 = (void (*)(void *, unsigned __int8, unsigned __int8))ProcessUserLogoff;
    v13 = CWLIDTimerQueue::QueueWorkItem((CWLIDTimerQueue *)g_WLIDTimerQueue, v12, v9, 0, 0x118u);
    v17 = v13;
    if ( v13 < 0 )
    {
      LODWORD(ReturnLengthb) = v13;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x2715u,
        L"Error - 0x%lx QueueWorkItem.",
        ReturnLengthb);
    }
    else
    {
LABEL_12:
      v10 = 0;
    }
    if ( v10 )
    {
      WLIDSessionChangeData::~WLIDSessionChangeData(v10);
      operator delete(v10);
    }
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v21);
}

```

## disassembly

```asm
0x18008c554  push    rbp
0x18008c556  push    rbx
0x18008c557  push    rsi
0x18008c558  push    rdi
0x18008c559  push    r14
0x18008c55b  push    r15
0x18008c55d  lea     rbp, [rsp-2Fh]
0x18008c562  sub     rsp, 0C8h
0x18008c569  mov     rax, cs:__security_cookie
0x18008c570  xor     rax, rsp
0x18008c573  mov     [rbp+57h+var_38], rax
0x18008c577  mov     edi, r9d
0x18008c57a  mov     r14d, r8d
0x18008c57d  mov     esi, edx
0x18008c57f  mov     rbx, rcx
0x18008c582  xor     r15d, r15d
0x18008c585  mov     [rbp+57h+var_B0], r15d
0x18008c589  lea     rdx, aCreateprocessu_0; "CreateProcessUserTask"
0x18008c590  mov     [rbp+57h+var_90], rdx
0x18008c594  lea     rax, [rbp+57h+var_B0]
0x18008c598  mov     [rbp+57h+var_88], rax
0x18008c59c  mov     [rbp+57h+var_80], r15
0x18008c5a0  mov     [rbp+57h+var_78], r15
0x18008c5a4  xor     r9d, r9d; unsigned int
0x18008c5a7  mov     r8d, 26E6h; char *
0x18008c5ad  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008c5b4  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18008c5b9  nop
0x18008c5ba  mov     [rbp+57h+TokenInformation], r15d
0x18008c5be  xorps   xmm0, xmm0
0x18008c5c1  xor     eax, eax
0x18008c5c3  movups  [rbp+57h+var_6C], xmm0
0x18008c5c7  movups  [rbp+57h+var_5C], xmm0
0x18008c5cb  movups  [rbp+57h+var_4C], xmm0
0x18008c5cf  mov     [rbp+57h+var_3C], eax
0x18008c5d2  mov     [rbp+57h+var_A0], r15d
0x18008c5d6  mov     [rbp+57h+TokenHandle], r15
0x18008c5da  cmp     r14d, 5
0x18008c5de  jnz     short loc_18008C64E
0x18008c5e0  mov     [rbp+57h+TokenHandle], r15
0x18008c5e4  lea     rdx, [rbp+57h+TokenHandle]
0x18008c5e8  mov     rcx, [rbx]
0x18008c5eb  call    cs:__imp_UMgrQueryUserToken
0x18008c5f1  mov     [rbp+57h+var_B0], eax
0x18008c5f4  lea     rax, [rbp+57h+var_A0]
0x18008c5f8  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x18008c5fd  lea     r9d, [r15+38h]; TokenInformationLength
0x18008c601  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18008c605  lea     edx, [r15+0Ah]; TokenInformationClass
0x18008c609  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18008c60d  call    cs:__imp_GetTokenInformation
0x18008c613  test    eax, eax
0x18008c615  jnz     short loc_18008C64E
0x18008c617  call    cs:__imp_GetLastError
0x18008c61d  test    eax, eax
0x18008c61f  jle     short loc_18008C629
0x18008c621  movzx   eax, ax
0x18008c624  or      eax, 80070000h
0x18008c629  mov     [rbp+57h+var_B0], eax
0x18008c62c  mov     dword ptr [rsp+0F0h+ReturnLength], eax
0x18008c630  lea     r9, aError0xLxGetto; "Error - 0x%lx GetTokenInformation."
0x18008c637  mov     r8d, 26F5h; unsigned int
0x18008c63d  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008c644  mov     ecx, 2; unsigned __int8
0x18008c649  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18008c64e  mov     eax, [rbp+57h+var_B0]
0x18008c651  mov     [rsp+0F0h+var_C0], eax
0x18008c655  mov     eax, dword ptr [rbp+57h+var_6C+4]
0x18008c658  mov     [rsp+0F0h+var_C8], eax
0x18008c65c  mov     eax, dword ptr [rbp+57h+var_6C+8]
0x18008c65f  mov     dword ptr [rsp+0F0h+ReturnLength], eax
0x18008c663  lea     r9, aCreateprocessu; "CreateProcessUserTask. LogonId %d, %d. "...
0x18008c66a  mov     r8d, 26F9h; unsigned int
0x18008c670  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008c677  mov     ecx, 2; unsigned __int8
0x18008c67c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18008c681  cmp     cs:?g_lShutdownInProgress@@3JA, r15d; long g_lShutdownInProgress
0x18008c688  jnz     loc_18008C769
0x18008c68e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008c695  mov     ecx, 38h ; '8'; unsigned __int64
0x18008c69a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008c69f  mov     rbx, rax
0x18008c6a2  mov     [rbp+57h+var_98], rax
0x18008c6a6  test    rax, rax
0x18008c6a9  jz      loc_18008C74B
0x18008c6af  mov     rcx, [rbp+57h+TokenHandle]
0x18008c6b3  mov     [rbp+57h+TokenHandle], r15
0x18008c6b7  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18008c6be  mov     [rbx], rax
0x18008c6c1  mov     [rbx+8], r15
0x18008c6c5  mov     [rbx+10h], r15
0x18008c6c9  mov     [rbx+18h], r15
0x18008c6cd  mov     [rbx+20h], esi
0x18008c6d0  mov     rax, qword ptr [rbp+57h+var_6C+4]
0x18008c6d4  mov     [rbx+24h], rax
0x18008c6d8  mov     [rbx+2Ch], edi
0x18008c6db  mov     [rbx+8], rcx
0x18008c6df  mov     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFFFh
0x18008c6e7  mov     [rbp+57h+var_98], rbx
0x18008c6eb  test    rbx, rbx
0x18008c6ee  jz      short loc_18008C74E
0x18008c6f0  lea     rax, ?ProcessUserLogoff@@YAXPEAXEE@Z; ProcessUserLogoff(void *,uchar,uchar)
0x18008c6f7  lea     rdx, ?ProcessUserLogon@@YAXPEAXEE@Z; ProcessUserLogon(void *,uchar,uchar)
0x18008c6fe  cmp     r14d, 5
0x18008c702  cmovnz  rdx, rax; void (*)(void *, unsigned __int8, unsigned __int8)
0x18008c706  mov     dword ptr [rsp+0F0h+ReturnLength], 118h; unsigned int
0x18008c70e  xor     r9d, r9d; unsigned int
0x18008c711  mov     r8, rbx; void *
0x18008c714  lea     rcx, ?g_WLIDTimerQueue@@3VCWLIDTimerQueue@@A; this
0x18008c71b  call    ?QueueWorkItem@CWLIDTimerQueue@@UEAAJP6AXPEAXEE@Z0KK@Z; CWLIDTimerQueue::QueueWorkItem(void (*)(void *,uchar,uchar),void *,ulong,ulong)
0x18008c720  mov     [rbp+57h+var_B0], eax
0x18008c723  test    eax, eax
0x18008c725  jns     short loc_18008C74B
0x18008c727  mov     dword ptr [rsp+0F0h+ReturnLength], eax
0x18008c72b  lea     r9, aError0xLxQueue; "Error - 0x%lx QueueWorkItem."
0x18008c732  mov     r8d, 2715h; unsigned int
0x18008c738  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008c73f  mov     ecx, 2; unsigned __int8
0x18008c744  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18008c749  jmp     short loc_18008C74E
0x18008c74b  mov     rbx, r15
0x18008c74e  test    rbx, rbx
0x18008c751  jz      short loc_18008C769
0x18008c753  mov     rcx, rbx; this
0x18008c756  call    ??1WLIDSessionChangeData@@QEAA@XZ; WLIDSessionChangeData::~WLIDSessionChangeData(void)
0x18008c75b  mov     edx, 38h ; '8'
0x18008c760  mov     rcx, rbx; Block
0x18008c763  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c768  nop
0x18008c769  lea     rcx, [rbp+57h+TokenHandle]
0x18008c76d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008c772  nop
0x18008c773  lea     rcx, [rbp+57h+var_90]
0x18008c777  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18008c77c  mov     rcx, [rbp+57h+var_38]
0x18008c780  xor     rcx, rsp; StackCookie
0x18008c783  call    __security_check_cookie
0x18008c788  add     rsp, 0C8h
0x18008c78f  pop     r15
0x18008c791  pop     r14
0x18008c793  pop     rdi
0x18008c794  pop     rsi
0x18008c795  pop     rbx
0x18008c796  pop     rbp
0x18008c797  retn
```
