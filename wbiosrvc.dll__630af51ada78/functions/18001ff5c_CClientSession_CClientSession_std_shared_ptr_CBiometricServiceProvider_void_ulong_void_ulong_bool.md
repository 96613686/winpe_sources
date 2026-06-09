# CClientSession::CClientSession(std::shared_ptr<CBiometricServiceProvider>,void *,ulong,void *,ulong,bool)

- ea: `0x18001ff5c`
- end: `0x18002021f`
- name: `??0CClientSession@@QEAA@V?$shared_ptr@VCBiometricServiceProvider@@@std@@PEAXK1K_N@Z`
- size: `707`
- prototype: `CClientSession *__fastcall(CClientSession *this, _QWORD *, void *, int, HANDLE TokenHandle, char, char)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001ef0c`

## callees

- `0x18000b760`
- `0x180011be8`
- `0x180011c14`
- `0x180011d24`
- `0x1800128c0`
- `0x18001434c`
- `0x180014854`
- `0x18001ff5c`
- `0x180038e88`
- `0x1800530c4`
- `0x180068f60`
- `0x180069cc8`
- `0x180069cd4`
- `0x1800702a8`
- `0x180081b64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020090`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020079`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800200ce`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020079`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800200ce`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020133`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020133`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020109`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020109`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CClientSession *__fastcall CClientSession::CClientSession(
        CClientSession *this,
        _QWORD *a2,
        void *a3,
        int a4,
        HANDLE TokenHandle,
        char a6,
        char a7)
{
  PSID *v11; // r14
  DWORD LengthSid; // edi
  unsigned int v13; // ecx
  std::_Ref_count_base *v14; // rcx
  _BYTE v16[4]; // [rsp+30h] [rbp-51h] BYREF
  DWORD TokenInformationLength; // [rsp+34h] [rbp-4Dh] BYREF
  CClientSession *v18; // [rsp+38h] [rbp-49h]
  _QWORD *v19; // [rsp+40h] [rbp-41h]
  LPVOID TokenInformation[3]; // [rsp+48h] [rbp-39h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-21h] BYREF
  const char *v22; // [rsp+68h] [rbp-19h]
  __int64 v23; // [rsp+70h] [rbp-11h]

  v18 = this;
  v19 = a2;
  winbio::lockable_object::lockable_object(this);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = &CClientSession::`vftable'{for `winbio::lockable_object'};
  *((_QWORD *)this + 2) = &CClientSession::`vftable'{for `BindingHelper'};
  *((_DWORD *)this + 10) = 1;
  *((_DWORD *)this + 11) = a4;
  std::weak_ptr<CAsyncWorkItem>::weak_ptr<CAsyncWorkItem>((char *)this + 128, a2);
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 40) = 4;
  *((_BYTE *)this + 164) = a7;
  std::list<std::shared_ptr<CPresenceChangeItem>>::list<std::shared_ptr<CPresenceChangeItem>>((char *)this + 168);
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 50) = 0;
  *((_DWORD *)this + 51) = 0;
  *((_BYTE *)this + 208) = 0;
  *((_DWORD *)this + 53) = 0;
  *((_BYTE *)this + 216) = 0;
  *((_DWORD *)this + 55) = 0;
  *((_BYTE *)this + 224) = 0;
  *((_QWORD *)this + 38) = 0;
  std::list<std::shared_ptr<CPresenceChangeItem>>::list<std::shared_ptr<CPresenceChangeItem>>((char *)this + 328);
  *((_DWORD *)this + 86) = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength)
    || !TokenInformationLength
    || GetLastError() != 122 )
  {
    v23 = 0;
    v22 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v16[0] = 0;
  std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength, v16);
  v11 = (PSID *)TokenInformation[0];
  if ( !GetTokenInformation(
          TokenHandle,
          TokenUser,
          TokenInformation[0],
          TokenInformationLength,
          &TokenInformationLength) )
  {
    v23 = 0;
    v22 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  LengthSid = GetLengthSid(*v11);
  memset_0((char *)this + 48, 0, 0x4Cu);
  *((_DWORD *)this + 12) = 3;
  *((_DWORD *)this + 13) = LengthSid;
  CopySid(LengthSid, (char *)this + 56, *v11);
  memset_0((char *)this + 228, 0, 0x4Cu);
  *(_OWORD *)((char *)this + 312) = 0;
  if ( (a6 & 1) != 0 )
  {
    std::wstring::wstring(&pExceptionObject, L"WinBioFlagRawUsed");
    CBioTraceLogging::OnLegacyFeatureUsed(&pExceptionObject);
    std::wstring::_Tidy_deallocate(&pExceptionObject);
  }
  CClientSession::ComputeGrantedAccess(this, TokenHandle, a6, a3);
  if ( *a2 )
    v13 = *(_DWORD *)(*a2 + 32LL);
  else
    v13 = -1056964609;
  CActivityMonitor::NotifyClientArrival(v13);
  std::_Deallocate<16>(v11, (char *)TokenInformation[2] - (char *)v11);
  v14 = (std::_Ref_count_base *)a2[1];
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  return this;
}

```

## disassembly

```asm
0x18001ff5c  mov     [rsp-8+arg_18], rbx
0x18001ff61  push    rbp
0x18001ff62  push    rsi
0x18001ff63  push    rdi
0x18001ff64  push    r12
0x18001ff66  push    r13
0x18001ff68  push    r14
0x18001ff6a  push    r15
0x18001ff6c  lea     rbp, [rsp-0Fh]
0x18001ff71  sub     rsp, 90h
0x18001ff78  mov     rax, cs:__security_cookie
0x18001ff7f  xor     rax, rsp
0x18001ff82  mov     [rbp+3Fh+var_40], rax
0x18001ff86  mov     ebx, r9d
0x18001ff89  mov     r13, r8
0x18001ff8c  mov     r15, rdx
0x18001ff8f  mov     rsi, rcx
0x18001ff92  mov     [rbp+3Fh+var_88], rcx
0x18001ff96  mov     [rbp+3Fh+var_80], rdx
0x18001ff9a  mov     r12, [rbp+3Fh+TokenHandle]
0x18001ff9e  call    ??0lockable_object@winbio@@QEAA@XZ; winbio::lockable_object::lockable_object(void)
0x18001ffa3  nop
0x18001ffa4  xor     edi, edi
0x18001ffa6  mov     [rsi+18h], rdi
0x18001ffaa  mov     [rsi+20h], rdi
0x18001ffae  lea     rax, ??_7CClientSession@@6Blockable_object@winbio@@@; const CClientSession::`vftable'{for `winbio::lockable_object'}
0x18001ffb5  mov     [rsi], rax
0x18001ffb8  lea     rax, ??_7CClientSession@@6BBindingHelper@@@; const CClientSession::`vftable'{for `BindingHelper'}
0x18001ffbf  mov     [rsi+10h], rax
0x18001ffc3  lea     r14d, [rdi+1]
0x18001ffc7  mov     [rsi+28h], r14d
0x18001ffcb  mov     [rsi+2Ch], ebx
0x18001ffce  lea     rcx, [rsi+80h]
0x18001ffd5  mov     rdx, r15
0x18001ffd8  call    ??$?0VCAsyncWorkItem@@$0A@@?$weak_ptr@VCAsyncWorkItem@@@std@@QEAA@AEBV?$shared_ptr@VCAsyncWorkItem@@@1@@Z; std::weak_ptr<CAsyncWorkItem>::weak_ptr<CAsyncWorkItem>(std::shared_ptr<CAsyncWorkItem> const &)
0x18001ffdd  nop
0x18001ffde  mov     [rsi+90h], rdi
0x18001ffe5  mov     [rsi+98h], rdi
0x18001ffec  mov     dword ptr [rsi+0A0h], 4
0x18001fff6  mov     al, [rbp+3Fh+arg_30]
0x18001fff9  mov     [rsi+0A4h], al
0x18001ffff  lea     rcx, [rsi+0A8h]
0x180020006  call    ??0?$list@V?$shared_ptr@VCPresenceChangeItem@@@std@@V?$allocator@V?$shared_ptr@VCPresenceChangeItem@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<CPresenceChangeItem>>::list<std::shared_ptr<CPresenceChangeItem>>(void)
0x18002000b  nop
0x18002000c  mov     [rsi+0B8h], rdi
0x180020013  mov     [rsi+0C0h], rdi
0x18002001a  mov     [rsi+0C8h], edi
0x180020020  mov     [rsi+0CCh], edi
0x180020026  mov     [rsi+0D0h], dil
0x18002002d  mov     [rsi+0D4h], edi
0x180020033  mov     [rsi+0D8h], dil
0x18002003a  mov     [rsi+0DCh], edi
0x180020040  mov     [rsi+0E0h], dil
0x180020047  mov     [rsi+130h], rdi
0x18002004e  lea     rcx, [rsi+148h]
0x180020055  call    ??0?$list@V?$shared_ptr@VCPresenceChangeItem@@@std@@V?$allocator@V?$shared_ptr@VCPresenceChangeItem@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<CPresenceChangeItem>>::list<std::shared_ptr<CPresenceChangeItem>>(void)
0x18002005a  nop
0x18002005b  mov     [rsi+158h], edi
0x180020061  mov     [rbp+3Fh+TokenInformationLength], edi
0x180020064  lea     rax, [rbp+3Fh+TokenInformationLength]
0x180020068  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18002006d  xor     r9d, r9d; TokenInformationLength
0x180020070  xor     r8d, r8d; TokenInformation
0x180020073  mov     edx, r14d; TokenInformationClass
0x180020076  mov     rcx, r12; TokenHandle
0x180020079  call    cs:__imp_GetTokenInformation
0x18002007f  test    eax, eax
0x180020081  jnz     loc_1800201F1
0x180020087  cmp     [rbp+3Fh+TokenInformationLength], edi
0x18002008a  jz      loc_1800201F1
0x180020090  call    cs:__imp_GetLastError
0x180020096  cmp     eax, 7Ah ; 'z'
0x180020099  jnz     loc_1800201F1
0x18002009f  mov     [rbp+3Fh+var_90], dil
0x1800200a3  mov     edx, [rbp+3Fh+TokenInformationLength]
0x1800200a6  lea     r8, [rbp+3Fh+var_90]
0x1800200aa  lea     rcx, [rbp+3Fh+TokenInformation]
0x1800200ae  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x1800200b3  nop
0x1800200b4  mov     r14, [rbp+3Fh+TokenInformation]
0x1800200b8  lea     rax, [rbp+3Fh+TokenInformationLength]
0x1800200bc  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1800200c1  mov     r9d, [rbp+3Fh+TokenInformationLength]; TokenInformationLength
0x1800200c5  mov     r8, r14; TokenInformation
0x1800200c8  lea     edx, [rdi+1]; TokenInformationClass
0x1800200cb  mov     rcx, r12; TokenHandle
0x1800200ce  call    cs:__imp_GetTokenInformation
0x1800200d4  test    eax, eax
0x1800200d6  jnz     short loc_180020106
0x1800200d8  xorps   xmm0, xmm0
0x1800200db  movups  [rbp+3Fh+var_58], xmm0
0x1800200df  lea     rax, aBadAllocation; "bad allocation"
0x1800200e6  mov     qword ptr [rbp+3Fh+var_58], rax
0x1800200ea  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800200f1  mov     [rbp+3Fh+pExceptionObject], rax
0x1800200f5  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800200fc  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180020100  call    _CxxThrowException_0
0x180020106  mov     rcx, [r14]; pSid
0x180020109  call    cs:__imp_GetLengthSid
0x18002010f  mov     edi, eax
0x180020111  xor     edx, edx; Val
0x180020113  lea     r8d, [rdx+4Ch]; Size
0x180020117  lea     rcx, [rsi+30h]; void *
0x18002011b  call    memset_0
0x180020120  mov     dword ptr [rsi+30h], 3
0x180020127  mov     [rsi+34h], edi
0x18002012a  lea     rdx, [rsi+38h]; pDestinationSid
0x18002012e  mov     r8, [r14]; pSourceSid
0x180020131  mov     ecx, edi; nDestinationSidLength
0x180020133  call    cs:__imp_CopySid
0x180020139  lea     rcx, [rsi+0E4h]; void *
0x180020140  xor     edx, edx; Val
0x180020142  lea     r8d, [rdx+4Ch]; Size
0x180020146  call    memset_0
0x18002014b  xorps   xmm0, xmm0
0x18002014e  movups  xmmword ptr [rsi+138h], xmm0
0x180020155  test    [rbp+3Fh+arg_28], 1
0x180020159  jz      short loc_18002017F
0x18002015b  lea     rdx, aWinbioflagrawu; "WinBioFlagRawUsed"
0x180020162  lea     rcx, [rbp+3Fh+pExceptionObject]
0x180020166  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002016b  nop
0x18002016c  lea     rcx, [rbp+3Fh+pExceptionObject]
0x180020170  call    ?OnLegacyFeatureUsed@CBioTraceLogging@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CBioTraceLogging::OnLegacyFeatureUsed(std::wstring const &)
0x180020175  nop
0x180020176  lea     rcx, [rbp+3Fh+pExceptionObject]
0x18002017a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002017f  mov     r9, r13; void *
0x180020182  mov     r8d, dword ptr [rbp+3Fh+arg_28]; unsigned int
0x180020186  mov     rdx, r12; void *
0x180020189  mov     rcx, rsi; this
0x18002018c  call    ?ComputeGrantedAccess@CClientSession@@AEAAXPEAXK0@Z; CClientSession::ComputeGrantedAccess(void *,ulong,void *)
0x180020191  mov     rcx, [r15]
0x180020194  test    rcx, rcx
0x180020197  jz      short loc_18002019E
0x180020199  mov     ecx, [rcx+20h]
0x18002019c  jmp     short loc_1800201A3
0x18002019e  mov     ecx, 0C0FFFFFFh; unsigned int
0x1800201a3  call    ?NotifyClientArrival@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientArrival(uint)
0x1800201a8  nop
0x1800201a9  mov     rdx, [rbp+3Fh+var_68]
0x1800201ad  sub     rdx, r14
0x1800201b0  mov     rcx, r14
0x1800201b3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800201b8  nop
0x1800201b9  mov     rcx, [r15+8]; this
0x1800201bd  test    rcx, rcx
0x1800201c0  jz      short loc_1800201C7
0x1800201c2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800201c7  mov     rax, rsi
0x1800201ca  mov     rcx, [rbp+3Fh+var_40]
0x1800201ce  xor     rcx, rsp; StackCookie
0x1800201d1  call    __security_check_cookie
0x1800201d6  mov     rbx, [rsp+0C0h+arg_18]
0x1800201de  add     rsp, 90h
0x1800201e5  pop     r15
0x1800201e7  pop     r14
0x1800201e9  pop     r13
0x1800201eb  pop     r12
0x1800201ed  pop     rdi
0x1800201ee  pop     rsi
0x1800201ef  pop     rbp
0x1800201f0  retn
0x1800201f1  xorps   xmm0, xmm0
0x1800201f4  movups  [rbp+3Fh+var_58], xmm0
0x1800201f8  lea     rax, aBadAllocation; "bad allocation"
0x1800201ff  mov     qword ptr [rbp+3Fh+var_58], rax
0x180020203  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18002020a  mov     [rbp+3Fh+pExceptionObject], rax
0x18002020e  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180020215  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180020219  call    _CxxThrowException_0
```
