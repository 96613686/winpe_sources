# OSDeploymentRemote::RemoteDeploymentSessionWrapper::CreateRemoteDeploymentSession(wchar_t const *,wchar_t const *,tagOptionalSessionInfo6 &,IRemoteDeploymentSession * *)

- ea: `0x18002e66c`
- end: `0x18002e9ad`
- name: `?CreateRemoteDeploymentSession@RemoteDeploymentSessionWrapper@OSDeploymentRemote@@AEAAJPEB_W0AEAUtagOptionalSessionInfo6@@PEAPEAUIRemoteDeploymentSession@@@Z`
- size: `833`
- prototype: `__int64 __fastcall(OSDeploymentRemote::RemoteDeploymentSessionWrapper *__hidden this, const wchar_t *, const wchar_t *, struct tagOptionalSessionInfo6 *, struct IRemoteDeploymentSession **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022a8c`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18002e66c`
- `0x1800316bc`
- `0x18003170c`
- `0x180031804`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e737`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e759`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e737`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e759`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e6e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e6e5`

## string_xrefs

- `0x18002e7fb`: `C:\__w\1\s\src\Client\inc\ComTimeout.h`
- `0x18002e7b2`: `ComTimeout::MakeComCall [%hs]`
- `0x18002e875`: `COM call timed out`
- `0x18002e8a9`: `WUComTimeout::ComTimeout::MakeComCall`
- `0x18002e8e2`: `COM call [%hs, from %hs:%u] timed out after %u seconds`
- `0x18002e7a6`: `uhosHostIfc->CreateDeploymentSession(dllPath, sandbox, c_dwOptionalSessionInfo6Version, &sessionInfo, &remoteDeploymentSession)`
- `0x18002e8d6`: `uhosHostIfc->CreateDeploymentSession(dllPath, sandbox, c_dwOptionalSessionInfo6Version, &sessionInfo, &remoteDeploymentSession)`
- `0x18002e8ca`: `OSDeploymentRemote::RemoteDeploymentSessionWrapper::CreateRemoteDeploymentSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSDeploymentRemote::RemoteDeploymentSessionWrapper::CreateRemoteDeploymentSession(
        OSDeploymentRemote::RemoteDeploymentSessionWrapper *this,
        const wchar_t *a2,
        const wchar_t *a3,
        struct tagOptionalSessionInfo6 *a4,
        struct IRemoteDeploymentSession **a5)
{
  int v5; // r15d
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // edi
  int v15; // eax
  unsigned int v16; // edx
  int v17; // eax
  unsigned int v18; // edx
  unsigned int v19; // ecx
  int v20; // [rsp+20h] [rbp-60h]
  int v21; // [rsp+20h] [rbp-60h]
  int v22; // [rsp+20h] [rbp-60h]
  __int64 v23; // [rsp+60h] [rbp-20h] BYREF
  __int128 pv; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v5 = (int)a4;
  if ( a5 )
  {
    *(_QWORD *)&pv = this;
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
    if ( this )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v11 = *((_QWORD *)this + 6);
    v12 = 0;
    v13 = *(_QWORD *)(v11 + 128);
    if ( v13 )
    {
      v12 = *(_QWORD *)(v11 + 128);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      LeaveCriticalSection(v10);
      v23 = 0;
      v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
              v12,
              &GUID_93b94125_6847_415d_baec_f43b1b3a0511,
              &v23);
      v14 = v15;
      if ( v15 >= 0 )
      {
        WUTrace(0, 0, 0x10000, 5);
        pv = 0u;
        WORD6(pv) = 0;
        v17 = WUComTimeout::ComTimeout::SetTimer(&pv, v16);
        v14 = v17;
        if ( v17 >= 0 )
        {
          v22 = v5;
          v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v23 + 32LL))(
                  v23,
                  a2,
                  a3,
                  6);
          if ( v14 < 0 && BYTE13(pv) )
          {
            WUTrace("WUComTimeout::ComTimeout::MakeComCall", 52, 32, 3);
            WUTelemetryAssertTriggered(v19, v18);
            v22 = v14;
            WUTrace(0, 0, 0x10000, 1);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2E,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\ComTimeout.h",
            (const char *)(unsigned int)v17,
            0);
        }
        WUComTimeout::ComTimeout::~ComTimeout((WUComTimeout::ComTimeout *)&pv);
        if ( v14 >= 0 )
        {
          *a5 = 0;
          v14 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA0,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSessionWrapper.cpp",
            (const char *)(unsigned int)v14,
            v22);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x98,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSessionWrapper.cpp",
          (const char *)(unsigned int)v15,
          v20);
      }
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    else
    {
      v14 = -2145124348;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
        (const char *)0x80240004LL,
        v20);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSessionWrapper.cpp",
        (const char *)0x80240004LL,
        v21);
      LeaveCriticalSection(v10);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    return (unsigned int)v14;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSessionWrapper.cpp",
      (const char *)0x80004003LL,
      v20);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18002e66c  mov     [rsp-28h+arg_0], rbx
0x18002e671  mov     [rsp-28h+arg_8], rsi
0x18002e676  mov     [rsp-28h+arg_10], rdi
0x18002e67b  push    rbp
0x18002e67c  push    r12
0x18002e67e  push    r13
0x18002e680  push    r14
0x18002e682  push    r15
0x18002e684  mov     rbp, rsp
0x18002e687  sub     rsp, 80h
0x18002e68e  mov     rax, cs:__security_cookie
0x18002e695  xor     rax, rsp
0x18002e698  mov     [rbp+var_8], rax
0x18002e69c  mov     r15, r9
0x18002e69f  mov     r12, r8
0x18002e6a2  mov     r13, rdx
0x18002e6a5  mov     rbx, rcx
0x18002e6a8  mov     r14, [rbp+arg_20]
0x18002e6ac  test    r14, r14
0x18002e6af  jnz     short loc_18002E6D5
0x18002e6b1  mov     rcx, [rbp+28h]; this
0x18002e6b5  mov     ebx, 80004003h
0x18002e6ba  mov     r9d, ebx; char *
0x18002e6bd  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002e6c4  mov     edx, 8Eh; void *
0x18002e6c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e6ce  mov     eax, ebx
0x18002e6d0  jmp     loc_18002E980
0x18002e6d5  mov     qword ptr [rbp+pv], rbx
0x18002e6d9  lea     rsi, [rcx+8]
0x18002e6dd  test    rbx, rbx
0x18002e6e0  jz      short loc_18002E6EC
0x18002e6e2  mov     rcx, rsi; lpCriticalSection
0x18002e6e5  call    cs:__imp_EnterCriticalSection
0x18002e6eb  nop
0x18002e6ec  mov     rax, [rbx+30h]
0x18002e6f0  xor     ebx, ebx
0x18002e6f2  mov     rcx, [rax+80h]
0x18002e6f9  test    rcx, rcx
0x18002e6fc  jnz     short loc_18002E742
0x18002e6fe  mov     rcx, [rbp+28h]; this
0x18002e702  mov     edi, 80240004h
0x18002e707  mov     r9d, edi; char *
0x18002e70a  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002e711  mov     edx, 14Bh; void *
0x18002e716  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e71b  mov     rcx, [rbp+28h]; this
0x18002e71f  mov     r9d, edi; char *
0x18002e722  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002e729  mov     edx, 94h; void *
0x18002e72e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e733  nop
0x18002e734  mov     rcx, rsi; lpCriticalSection
0x18002e737  call    cs:__imp_LeaveCriticalSection
0x18002e73d  jmp     loc_18002E969
0x18002e742  mov     rbx, rcx
0x18002e745  mov     [rbp+var_30], rcx
0x18002e749  mov     rax, [rcx]
0x18002e74c  mov     rax, [rax+8]
0x18002e750  call    _guard_dispatch_icall
0x18002e755  nop
0x18002e756  mov     rcx, rsi; lpCriticalSection
0x18002e759  call    cs:__imp_LeaveCriticalSection
0x18002e75f  nop
0x18002e760  xor     esi, esi
0x18002e762  mov     [rbp+var_20], rsi
0x18002e766  mov     rax, [rbx]
0x18002e769  lea     r8, [rbp+var_20]
0x18002e76d  lea     rdx, _GUID_93b94125_6847_415d_baec_f43b1b3a0511
0x18002e774  mov     rcx, rbx
0x18002e777  mov     rax, [rax]
0x18002e77a  call    _guard_dispatch_icall
0x18002e77f  mov     edi, eax
0x18002e781  test    eax, eax
0x18002e783  jns     short loc_18002E7A2
0x18002e785  mov     rcx, [rbp+28h]; this
0x18002e789  mov     r9d, eax; char *
0x18002e78c  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002e793  mov     edx, 98h; void *
0x18002e798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e79d  jmp     loc_18002E953
0x18002e7a2  mov     [rbp+var_28], rsi
0x18002e7a6  lea     rax, aUhoshostifcCre; "uhosHostIfc->CreateDeploymentSession(dl"...
0x18002e7ad  mov     [rsp+80h+var_50], rax
0x18002e7b2  lea     rax, aComtimeoutMake; "ComTimeout::MakeComCall [%hs]"
0x18002e7b9  mov     [rsp+80h+var_58], rax
0x18002e7be  mov     qword ptr [rsp+80h+var_60], rsi; int
0x18002e7c3  xor     edx, edx
0x18002e7c5  xor     ecx, ecx
0x18002e7c7  lea     r9d, [rdx+5]
0x18002e7cb  mov     r8d, 10000h
0x18002e7d1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002e7d6  xorps   xmm0, xmm0
0x18002e7d9  movups  [rbp+pv], xmm0
0x18002e7dd  mov     qword ptr [rbp+pv], rsi
0x18002e7e1  mov     word ptr [rbp+pv+0Ch], si
0x18002e7e5  lea     rcx, [rbp+pv]; pv
0x18002e7e9  call    ?SetTimer@ComTimeout@WUComTimeout@@QEAAJK@Z; WUComTimeout::ComTimeout::SetTimer(ulong)
0x18002e7ee  mov     edi, eax
0x18002e7f0  test    eax, eax
0x18002e7f2  jns     short loc_18002E811
0x18002e7f4  mov     rcx, [rbp+28h]; this
0x18002e7f8  mov     r9d, eax; char *
0x18002e7fb  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\ComTim"...
0x18002e802  mov     edx, 2Eh ; '.'; void *
0x18002e807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e80c  jmp     loc_18002E906
0x18002e811  mov     rdi, [rbp+var_20]
0x18002e815  mov     rax, [rdi]
0x18002e818  mov     rsi, [rax+20h]
0x18002e81c  mov     rcx, [rbp+var_28]
0x18002e820  mov     [rbp+var_28], 0
0x18002e828  test    rcx, rcx
0x18002e82b  jz      short loc_18002E83A
0x18002e82d  mov     rax, [rcx]
0x18002e830  mov     rax, [rax+10h]
0x18002e834  call    _guard_dispatch_icall
0x18002e839  nop
0x18002e83a  lea     rax, [rbp+var_28]
0x18002e83e  mov     [rsp+80h+var_58], rax
0x18002e843  mov     qword ptr [rsp+80h+var_60], r15
0x18002e848  mov     r9d, 6
0x18002e84e  mov     r8, r12
0x18002e851  mov     rdx, r13
0x18002e854  mov     rcx, rdi
0x18002e857  mov     rax, rsi
0x18002e85a  call    _guard_dispatch_icall
0x18002e85f  mov     edi, eax
0x18002e861  xor     esi, esi
0x18002e863  test    eax, eax
0x18002e865  jns     loc_18002E906
0x18002e86b  cmp     byte ptr [rbp+pv+0Dh], sil
0x18002e86f  jz      loc_18002E906
0x18002e875  lea     rax, aComCallTimedOu; "COM call timed out"
0x18002e87c  mov     [rsp+80h+var_48], rax
0x18002e881  lea     rax, aFalse; "false"
0x18002e888  mov     [rsp+80h+var_50], rax
0x18002e88d  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x18002e894  mov     [rsp+80h+var_58], rax
0x18002e899  mov     qword ptr [rsp+80h+var_60], rsi
0x18002e89e  lea     edx, [rsi+34h]
0x18002e8a1  lea     r9d, [rsi+3]
0x18002e8a5  lea     r8d, [rsi+20h]
0x18002e8a9  lea     rcx, aWucomtimeoutCo; "WUComTimeout::ComTimeout::MakeComCall"
0x18002e8b0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002e8b5  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x18002e8ba  mov     [rsp+80h+var_38], 1Eh
0x18002e8c2  mov     [rsp+80h+var_40], 0A0h
0x18002e8ca  lea     rax, aOsdeploymentre; "OSDeploymentRemote::RemoteDeploymentSes"...
0x18002e8d1  mov     [rsp+80h+var_48], rax
0x18002e8d6  lea     rax, aUhoshostifcCre; "uhosHostIfc->CreateDeploymentSession(dl"...
0x18002e8dd  mov     [rsp+80h+var_50], rax
0x18002e8e2  lea     rax, aComCallHsFromH; "COM call [%hs, from %hs:%u] timed out a"...
0x18002e8e9  mov     [rsp+80h+var_58], rax
0x18002e8ee  mov     [rsp+80h+var_60], edi; int
0x18002e8f2  xor     edx, edx
0x18002e8f4  xor     ecx, ecx
0x18002e8f6  lea     r9d, [rsi+1]
0x18002e8fa  mov     r8d, 10000h
0x18002e900  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002e905  nop
0x18002e906  lea     rcx, [rbp+pv]; this
0x18002e90a  call    ??1ComTimeout@WUComTimeout@@QEAA@XZ; WUComTimeout::ComTimeout::~ComTimeout(void)
0x18002e90f  test    edi, edi
0x18002e911  jns     short loc_18002E931
0x18002e913  mov     rcx, [rbp+28h]; this
0x18002e917  mov     r9d, edi; char *
0x18002e91a  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002e921  mov     edx, 0A0h; void *
0x18002e926  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e92b  mov     rcx, [rbp+var_28]
0x18002e92f  jmp     short loc_18002E941
0x18002e931  mov     rax, [rbp+var_28]
0x18002e935  mov     rcx, rsi
0x18002e938  mov     [rbp+var_28], rcx
0x18002e93c  mov     [r14], rax
0x18002e93f  mov     edi, esi
0x18002e941  test    rcx, rcx
0x18002e944  jz      short loc_18002E953
0x18002e946  mov     rax, [rcx]
0x18002e949  mov     rax, [rax+10h]
0x18002e94d  call    _guard_dispatch_icall
0x18002e952  nop
0x18002e953  mov     rcx, [rbp+var_20]
0x18002e957  test    rcx, rcx
0x18002e95a  jz      short loc_18002E969
0x18002e95c  mov     rax, [rcx]
0x18002e95f  mov     rax, [rax+10h]
0x18002e963  call    _guard_dispatch_icall
0x18002e968  nop
0x18002e969  test    rbx, rbx
0x18002e96c  jz      short loc_18002E97E
0x18002e96e  mov     rcx, [rbx]
0x18002e971  mov     rax, [rcx+10h]
0x18002e975  mov     rcx, rbx
0x18002e978  call    _guard_dispatch_icall
0x18002e97d  nop
0x18002e97e  mov     eax, edi
0x18002e980  mov     rcx, [rbp+var_8]
0x18002e984  xor     rcx, rsp; StackCookie
0x18002e987  call    __security_check_cookie
0x18002e98c  lea     r11, [rsp+80h+var_s0]
0x18002e994  mov     rbx, [r11+30h]
0x18002e998  mov     rsi, [r11+38h]
0x18002e99c  mov     rdi, [r11+40h]
0x18002e9a0  mov     rsp, r11
0x18002e9a3  pop     r15
0x18002e9a5  pop     r14
0x18002e9a7  pop     r13
0x18002e9a9  pop     r12
0x18002e9ab  pop     rbp
0x18002e9ac  retn
```
