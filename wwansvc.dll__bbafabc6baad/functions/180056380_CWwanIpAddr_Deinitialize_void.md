# CWwanIpAddr::Deinitialize(void)

- ea: `0x180056380`
- end: `0x18005645f`
- name: `?Deinitialize@CWwanIpAddr@@AEAAXXZ`
- size: `223`
- prototype: `void __fastcall(CWwanIpAddr *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18007aa2c`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x180056380`
- `0x180056838`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056398`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800563b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005644e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800563b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005644e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180056408`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180056408`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800563f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800563f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800563d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800563d7`

## pseudocode

```c
void __fastcall CWwanIpAddr::Deinitialize(CWwanIpAddr *this)
{
  CWwanIpAddr *v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 i; // rdi
  __int64 j; // rdi
  __int64 k; // rdi

  v1 = CWwanIpAddr::m_s_pWwanIpAddr;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)CWwanIpAddr::m_s_pWwanIpAddr + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)CWwanIpAddr::m_s_pWwanIpAddr + 8));
  if ( *(_DWORD *)v1 )
  {
    *(_DWORD *)v1 = 0;
    LeaveCriticalSection(v2);
    WwanLog::Info("CWwanIpAddr::Deinitialize", 0, L" called while m_fInitialized is false ");
    for ( i = 0; i != 2; ++i )
      SetThreadpoolWait(*((PTP_WAIT *)v1 + i + 13), 0, 0);
    for ( j = 0; j != 2; ++j )
      WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)v1 + j + 13), 1);
    for ( k = 0; k != 2; ++k )
      CloseThreadpoolWait(*((PTP_WAIT *)v1 + k + 13));
    CWwanIpAddr::IpAddr_DeInitialize(v1);
    WwanLog::Info("CWwanIpAddr::Deinitialize", 0, L" Deinitialized CWwanIpAddr");
  }
  else
  {
    WwanLog::Error("CWwanIpAddr::Deinitialize", 0, L"called while m_fInitialized is false ");
    LeaveCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x180056380  mov     [rsp+arg_0], rbx
0x180056385  push    rdi
0x180056386  sub     rsp, 20h
0x18005638a  mov     rbx, cs:?m_s_pWwanIpAddr@CWwanIpAddr@@0PEAV1@EA; CWwanIpAddr * CWwanIpAddr::m_s_pWwanIpAddr
0x180056391  lea     rdi, [rbx+8]
0x180056395  mov     rcx, rdi; lpCriticalSection
0x180056398  call    cs:__imp_EnterCriticalSection
0x18005639e  cmp     dword ptr [rbx], 0
0x1800563a1  jz      loc_180056436
0x1800563a7  mov     rcx, rdi; lpCriticalSection
0x1800563aa  mov     dword ptr [rbx], 0
0x1800563b0  call    cs:__imp_LeaveCriticalSection
0x1800563b6  lea     r8, aCalledWhileMFi_0; " called while m_fInitialized is false "
0x1800563bd  xor     edx, edx; struct _GUID *
0x1800563bf  lea     rcx, aCwwanipaddrDei; "CWwanIpAddr::Deinitialize"
0x1800563c6  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800563cb  xor     edi, edi
0x1800563cd  mov     rcx, [rbx+rdi*8+68h]; pwa
0x1800563d2  xor     r8d, r8d; pftTimeout
0x1800563d5  xor     edx, edx; h
0x1800563d7  call    cs:__imp_SetThreadpoolWait
0x1800563dd  inc     rdi
0x1800563e0  cmp     rdi, 2
0x1800563e4  jnz     short loc_1800563CD
0x1800563e6  xor     edi, edi
0x1800563e8  mov     rcx, [rbx+rdi*8+68h]; pwa
0x1800563ed  mov     edx, 1; fCancelPendingCallbacks
0x1800563f2  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800563f8  inc     rdi
0x1800563fb  cmp     rdi, 2
0x1800563ff  jnz     short loc_1800563E8
0x180056401  xor     edi, edi
0x180056403  mov     rcx, [rbx+rdi*8+68h]; pwa
0x180056408  call    cs:__imp_CloseThreadpoolWait
0x18005640e  inc     rdi
0x180056411  cmp     rdi, 2
0x180056415  jnz     short loc_180056403
0x180056417  mov     rcx, rbx; this
0x18005641a  call    ?IpAddr_DeInitialize@CWwanIpAddr@@AEAAXXZ; CWwanIpAddr::IpAddr_DeInitialize(void)
0x18005641f  lea     r8, aDeinitializedC; " Deinitialized CWwanIpAddr"
0x180056426  xor     edx, edx; struct _GUID *
0x180056428  lea     rcx, aCwwanipaddrDei; "CWwanIpAddr::Deinitialize"
0x18005642f  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180056434  jmp     short loc_180056454
0x180056436  lea     r8, aCalledWhileMFi; "called while m_fInitialized is false "
0x18005643d  xor     edx, edx; struct _GUID *
0x18005643f  lea     rcx, aCwwanipaddrDei; "CWwanIpAddr::Deinitialize"
0x180056446  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18005644b  mov     rcx, rdi; lpCriticalSection
0x18005644e  call    cs:__imp_LeaveCriticalSection
0x180056454  mov     rbx, [rsp+28h+arg_0]
0x180056459  add     rsp, 20h
0x18005645d  pop     rdi
0x18005645e  retn
```
