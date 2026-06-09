# WFDSConMgr::CThreadTokenImpersonationProvider::CreateForCurrentThread(void)

- ea: `0x18005e94c`
- end: `0x18005ea71`
- name: `?CreateForCurrentThread@CThreadTokenImpersonationProvider@WFDSConMgr@@SA?AV?$shared_ptr@VCThreadTokenImpersonationProvider@WFDSConMgr@@@std@@XZ`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800074d8`

## callees

- `0x18000421c`
- `0x180004870`
- `0x18005c800`
- `0x18005e4c4`
- `0x18005e4e8`
- `0x18005e94c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005e9a9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005e9a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005e990`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005e990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9b3`

## string_xrefs

- `0x18005e9d7`: `onecoreuap\net\wlan\wfdsconmgr\util\src\impersonationprovider.cpp`
- `0x18005e9c5`: `OpenThreadToken failed, will not be able to impersonate client`
- `0x18005e9de`: `WFDSConMgr::CThreadTokenImpersonationProvider::CreateForCurrentThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall WFDSConMgr::CThreadTokenImpersonationProvider::CreateForCurrentThread(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  _DWORD *v7; // rdi
  char v9[8]; // [rsp+38h] [rbp-30h] BYREF
  void *v10; // [rsp+40h] [rbp-28h]
  void *TokenHandle; // [rsp+78h] [rbp+10h] BYREF
  void **p_TokenHandle; // [rsp+80h] [rbp+18h] BYREF
  _DWORD *v13; // [rsp+88h] [rbp+20h]

  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_7d681293e58d38db1ed4308781b49152_Traceguids, a4);
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WFDSConMgr::CException::Throw(
      LastError,
      "WFDSConMgr::CThreadTokenImpersonationProvider::CreateForCurrentThread",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\impersonationprovider.cpp",
      49,
      L"OpenThreadToken failed, will not be able to impersonate client");
  }
  v10 = TokenHandle;
  p_TokenHandle = &TokenHandle;
  v7 = operator new(0x20u);
  v13 = v7;
  *(_OWORD *)v7 = 0;
  v7[2] = 1;
  v7[3] = 1;
  *(_QWORD *)v7 = &std::_Ref_count_obj2<WFDSConMgr::CRpcImpersonationProvider>::`vftable';
  std::_Construct_in_place<WFDSConMgr::CThreadTokenImpersonationProvider,void * *>((_QWORD *)v7 + 2, &p_TokenHandle);
  *a1 = v7 + 4;
  a1[1] = v7;
  v9[0] = 1;
  ScopeGuardImplBase::SafeExecute_ScopeGuardImpl0__lambda_b6cd38561ff647791b3ec35d5a12cce9_____(v9);
  return a1;
}

```

## disassembly

```asm
0x18005e94c  push    rbx
0x18005e94e  push    rsi
0x18005e94f  push    rdi
0x18005e950  sub     rsp, 50h
0x18005e954  mov     rsi, rcx
0x18005e957  xor     ebx, ebx
0x18005e959  mov     [rsp+68h+TokenHandle], rbx
0x18005e95e  lea     rax, WPP_GLOBAL_Control
0x18005e965  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e96c  cmp     rcx, rax
0x18005e96f  jz      short loc_18005E990
0x18005e971  cmp     byte ptr [rcx+19h], 4
0x18005e975  jb      short loc_18005E990
0x18005e977  test    byte ptr [rcx+1Ch], 1
0x18005e97b  jz      short loc_18005E990
0x18005e97d  lea     edx, [rbx+0Dh]
0x18005e980  lea     r8, WPP_7d681293e58d38db1ed4308781b49152_Traceguids
0x18005e987  mov     rcx, [rcx+10h]
0x18005e98b  call    WPP_SF_
0x18005e990  call    cs:__imp_GetCurrentThread
0x18005e996  mov     rcx, rax; ThreadHandle
0x18005e999  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x18005e99e  mov     edx, 2000Ch; DesiredAccess
0x18005e9a3  mov     r8d, 1; OpenAsSelf
0x18005e9a9  call    cs:__imp_OpenThreadToken
0x18005e9af  test    eax, eax
0x18005e9b1  jnz     short loc_18005E9ED
0x18005e9b3  call    cs:__imp_GetLastError
0x18005e9b9  test    eax, eax
0x18005e9bb  jle     short loc_18005E9C5
0x18005e9bd  movzx   eax, ax
0x18005e9c0  or      eax, 80070000h
0x18005e9c5  lea     rcx, aOpenthreadtoke; "OpenThreadToken failed, will not be abl"...
0x18005e9cc  mov     [rsp+68h+var_48], rcx; unsigned __int16 *
0x18005e9d1  mov     r9d, 31h ; '1'; char
0x18005e9d7  lea     r8, aOnecoreuapNetW_15; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005e9de  lea     rdx, aWfdsconmgrCthr_1; "WFDSConMgr::CThreadTokenImpersonationPr"...
0x18005e9e5  mov     ecx, eax; int
0x18005e9e7  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18005e9ed  mov     rax, [rsp+68h+TokenHandle]
0x18005e9f2  mov     [rsp+68h+var_30], bl
0x18005e9f6  mov     [rsp+68h+var_28], rax
0x18005e9fb  lea     rax, [rsp+68h+TokenHandle]
0x18005ea00  mov     [rsp+68h+arg_10], rax
0x18005ea08  mov     ecx, 20h ; ' '; Size
0x18005ea0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ea12  mov     rdi, rax
0x18005ea15  mov     [rsp+68h+arg_18], rax
0x18005ea1d  xorps   xmm0, xmm0
0x18005ea20  movups  xmmword ptr [rax], xmm0
0x18005ea23  mov     dword ptr [rax+8], 1
0x18005ea2a  mov     dword ptr [rax+0Ch], 1
0x18005ea31  lea     rax, ??_7?$_Ref_count_obj2@VCRpcImpersonationProvider@WFDSConMgr@@@std@@6B@; const std::_Ref_count_obj2<WFDSConMgr::CRpcImpersonationProvider>::`vftable'
0x18005ea38  mov     [rdi], rax
0x18005ea3b  lea     rbx, [rdi+10h]
0x18005ea3f  lea     rdx, [rsp+68h+arg_10]
0x18005ea47  mov     rcx, rbx; void *
0x18005ea4a  call    ??$_Construct_in_place@VCThreadTokenImpersonationProvider@WFDSConMgr@@PEAPEAX@std@@YAXAEAVCThreadTokenImpersonationProvider@WFDSConMgr@@$$QEAPEAPEAX@Z; std::_Construct_in_place<WFDSConMgr::CThreadTokenImpersonationProvider,void * *>(WFDSConMgr::CThreadTokenImpersonationProvider &,void * * &&)
0x18005ea4f  nop
0x18005ea50  mov     [rsi], rbx
0x18005ea53  mov     [rsi+8], rdi
0x18005ea57  mov     [rsp+68h+var_30], 1
0x18005ea5c  lea     rcx, [rsp+68h+var_30]
0x18005ea61  call    ScopeGuardImplBase__SafeExecute_ScopeGuardImpl0__lambda_b6cd38561ff647791b3ec35d5a12cce9_____
0x18005ea66  mov     rax, rsi
0x18005ea69  add     rsp, 50h
0x18005ea6d  pop     rdi
0x18005ea6e  pop     rsi
0x18005ea6f  pop     rbx
0x18005ea70  retn
```
