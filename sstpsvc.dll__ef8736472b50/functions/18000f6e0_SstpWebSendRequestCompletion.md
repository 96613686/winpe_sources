# SstpWebSendRequestCompletion

- ea: `0x18000f6e0`
- end: `0x18000f8e9`
- name: `SstpWebSendRequestCompletion`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000df08`

## callees

- `0x180002aac`
- `0x180002f50`
- `0x18000823c`
- `0x1800089dc`
- `0x180008b90`
- `0x18000ebd0`
- `0x18000f6e0`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f793`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f7fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f793`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f7fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f872`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f872`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f85c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f85c`
- `webio!__imp_WebReceiveHttpResponse` at `0x18000f898`
- `webio!__imp_WebReceiveHttpResponse` at `0x18000f898`

## string_xrefs

- `0x18000f7b9`: `CoId=%hs:SendRequest completes successfully`

## pseudocode

```c
__int64 __fastcall SstpWebSendRequestCompletion(__int64 a1, unsigned int a2)
{
  struct _TP_TIMER *v4; // rcx
  unsigned int v5; // eax
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp-C8h] BYREF
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v10[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( a2 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"CoId=%hs:SendRequest fails with error %d", a1 + 552, a2);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v9);
    }
    LogEventWithErrorParameter(1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    *(_DWORD *)(a1 + 268) = a2;
LABEL_10:
    *(_DWORD *)(a1 + 252) &= ~0x10000u;
    InitiateCallContextCleanup(a1, 2u);
    return DereferenceRefCount(a1 + 208);
  }
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"CoId=%hs:SendRequest completes successfully", a1 + 552);
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v9);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  if ( *(_BYTE *)(a1 + 435) )
    goto LABEL_10;
  pftDueTime = 0;
  v7 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
  v4 = *(struct _TP_TIMER **)(a1 + 456);
  pftDueTime = (struct _FILETIME)-600000000LL;
  SetThreadpoolTimer(v4, &pftDueTime, 0, 0);
  *(_BYTE *)(a1 + 464) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  v5 = WebReceiveHttpResponse(*(_QWORD *)(a1 + 448), 0, &v7, SstpWebReceiveResponseCompletion, a1);
  if ( v5 != 997 )
    SstpWebReceiveResponseCompletion(a1, v5);
  return DereferenceRefCount(a1 + 208);
}

```

## disassembly

```asm
0x18000f6e0  mov     [rsp-8+arg_10], rbx
0x18000f6e5  mov     [rsp-8+arg_18], rdi
0x18000f6ea  push    rbp
0x18000f6eb  lea     rbp, [rsp-750h]
0x18000f6f3  sub     rsp, 850h
0x18000f6fa  mov     rax, cs:__security_cookie
0x18000f701  xor     rax, rsp
0x18000f704  mov     [rbp+750h+var_10], rax
0x18000f70b  mov     edi, edx
0x18000f70d  mov     rbx, rcx
0x18000f710  xor     eax, eax
0x18000f712  lea     rcx, [rsp+850h+var_80C]; void *
0x18000f717  xor     edx, edx; Val
0x18000f719  mov     [rsp+850h+var_810], eax
0x18000f71d  mov     r8d, 7FCh; Size
0x18000f723  call    memset_0
0x18000f728  test    edi, edi
0x18000f72a  jz      short loc_18000F7A7
0x18000f72c  test    cs:byte_18002E903, 8
0x18000f733  jz      short loc_18000F778
0x18000f735  xor     eax, eax
0x18000f737  lea     r8, [rbx+228h]
0x18000f73e  mov     r9d, edi
0x18000f741  mov     word ptr [rsp+850h+var_810], ax
0x18000f746  lea     rdx, aCoidHsSendrequ_0; "CoId=%hs:SendRequest fails with error %"...
0x18000f74d  lea     rcx, [rsp+850h+var_810]
0x18000f752  call    FormatRRASErrorString
0x18000f757  test    cs:byte_18002E903, 8
0x18000f75e  jz      short loc_18000F778
0x18000f760  lea     r8, [rsp+850h+var_810]
0x18000f765  lea     rdx, RasSSTPSvcTraceError
0x18000f76c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f773  call    McTemplateU0z_EventWriteTransfer
0x18000f778  lea     r9, [rbx+228h]
0x18000f77f  mov     r8d, edi
0x18000f782  mov     ecx, 1; dwMessageId
0x18000f787  call    LogEventWithErrorParameter
0x18000f78c  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000f793  call    cs:__imp_EnterCriticalSection
0x18000f79a  nop     dword ptr [rax+rax+00h]
0x18000f79f  mov     [rbx+10Ch], edi
0x18000f7a5  jmp     short loc_18000F80F
0x18000f7a7  test    cs:byte_18002E903, 10h
0x18000f7ae  jz      short loc_18000F7F0
0x18000f7b0  xor     eax, eax
0x18000f7b2  lea     r8, [rbx+228h]
0x18000f7b9  lea     rdx, aCoidHsSendrequ; "CoId=%hs:SendRequest completes successf"...
0x18000f7c0  mov     word ptr [rsp+850h+var_810], ax
0x18000f7c5  lea     rcx, [rsp+850h+var_810]
0x18000f7ca  call    FormatRRASErrorString
0x18000f7cf  test    cs:byte_18002E903, 10h
0x18000f7d6  jz      short loc_18000F7F0
0x18000f7d8  lea     r8, [rsp+850h+var_810]
0x18000f7dd  lea     rdx, RasSSTPSvcTraceInfo
0x18000f7e4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f7eb  call    McTemplateU0z_EventWriteTransfer
0x18000f7f0  lea     rdi, [rbx+120h]
0x18000f7f7  mov     rcx, rdi; lpCriticalSection
0x18000f7fa  call    cs:__imp_EnterCriticalSection
0x18000f801  nop     dword ptr [rax+rax+00h]
0x18000f806  cmp     byte ptr [rbx+1B3h], 0
0x18000f80d  jz      short loc_18000F829
0x18000f80f  btr     dword ptr [rbx+0FCh], 10h
0x18000f817  mov     edx, 2
0x18000f81c  mov     rcx, rbx
0x18000f81f  call    InitiateCallContextCleanup
0x18000f824  jmp     loc_18000F8B8
0x18000f829  mov     qword ptr [rsp+850h+pftDueTime.dwLowDateTime], 0
0x18000f832  mov     [rsp+850h+var_820], 0
0x18000f83a  lock inc dword ptr [rbx+0D0h]
0x18000f841  mov     rcx, [rbx+1C8h]; pti
0x18000f848  lea     rdx, [rsp+850h+pftDueTime]; pftDueTime
0x18000f84d  xor     r9d, r9d; msWindowLength
0x18000f850  mov     qword ptr [rsp+850h+pftDueTime.dwLowDateTime], 0FFFFFFFFDC3CBA00h
0x18000f859  xor     r8d, r8d; msPeriod
0x18000f85c  call    cs:__imp_SetThreadpoolTimer
0x18000f863  nop     dword ptr [rax+rax+00h]
0x18000f868  mov     rcx, rdi; lpCriticalSection
0x18000f86b  mov     byte ptr [rbx+1D0h], 0
0x18000f872  call    cs:__imp_LeaveCriticalSection
0x18000f879  nop     dword ptr [rax+rax+00h]
0x18000f87e  mov     rcx, [rbx+1C0h]
0x18000f885  lea     r9, SstpWebReceiveResponseCompletion
0x18000f88c  lea     r8, [rsp+850h+var_820]
0x18000f891  mov     [rsp+850h+var_830], rbx
0x18000f896  xor     edx, edx
0x18000f898  call    cs:__imp_WebReceiveHttpResponse
0x18000f89f  nop     dword ptr [rax+rax+00h]
0x18000f8a4  cmp     eax, 3E5h
0x18000f8a9  jz      short loc_18000F8B8
0x18000f8ab  xor     r8d, r8d
0x18000f8ae  mov     edx, eax
0x18000f8b0  mov     rcx, rbx
0x18000f8b3  call    SstpWebReceiveResponseCompletion
0x18000f8b8  lea     rcx, [rbx+0D0h]
0x18000f8bf  call    DereferenceRefCount
0x18000f8c4  mov     rcx, [rbp+750h+var_10]
0x18000f8cb  xor     rcx, rsp; StackCookie
0x18000f8ce  call    __security_check_cookie
0x18000f8d3  lea     r11, [rsp+850h+var_s0]
0x18000f8db  mov     rbx, [r11+20h]
0x18000f8df  mov     rdi, [r11+28h]
0x18000f8e3  mov     rsp, r11
0x18000f8e6  pop     rbp
0x18000f8e7  retn
```
