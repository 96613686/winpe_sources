# SstpWebSendRequestCompletion

- ea: `0x18000e9a0`
- end: `0x18000eb87`
- name: `SstpWebSendRequestCompletion`
- size: `487`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000d324`

## callees

- `0x180002908`
- `0x180002d40`
- `0x180007a84`
- `0x18000827c`
- `0x180008360`
- `0x18000df30`
- `0x18000e9a0`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eab4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eab4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eb0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eb0d`
- `webio!__imp_WebReceiveHttpResponse` at `0x18000eb3d`
- `webio!__imp_WebReceiveHttpResponse` at `0x18000eb3d`

## string_xrefs

- `0x18000ea73`: `CoId=%hs:SendRequest completes successfully`

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
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"CoId=%hs:SendRequest fails with error %d", a1 + 552, a2);
      if ( (byte_18002D803 & 8) != 0 )
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
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"CoId=%hs:SendRequest completes successfully", a1 + 552);
    if ( (byte_18002D803 & 0x10) != 0 )
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
0x18000e9a0  mov     [rsp-8+arg_10], rbx
0x18000e9a5  mov     [rsp-8+arg_18], rdi
0x18000e9aa  push    rbp
0x18000e9ab  lea     rbp, [rsp-750h]
0x18000e9b3  sub     rsp, 850h
0x18000e9ba  mov     rax, cs:__security_cookie
0x18000e9c1  xor     rax, rsp
0x18000e9c4  mov     [rbp+750h+var_10], rax
0x18000e9cb  mov     edi, edx
0x18000e9cd  mov     rbx, rcx
0x18000e9d0  xor     eax, eax
0x18000e9d2  lea     rcx, [rsp+850h+var_80C]; void *
0x18000e9d7  xor     edx, edx; Val
0x18000e9d9  mov     [rsp+850h+var_810], eax
0x18000e9dd  mov     r8d, 7FCh; Size
0x18000e9e3  call    memset_0
0x18000e9e8  test    edi, edi
0x18000e9ea  jz      short loc_18000EA61
0x18000e9ec  test    cs:byte_18002D803, 8
0x18000e9f3  jz      short loc_18000EA38
0x18000e9f5  xor     eax, eax
0x18000e9f7  lea     r8, [rbx+228h]
0x18000e9fe  mov     r9d, edi
0x18000ea01  mov     word ptr [rsp+850h+var_810], ax
0x18000ea06  lea     rdx, aCoidHsSendrequ_0; "CoId=%hs:SendRequest fails with error %"...
0x18000ea0d  lea     rcx, [rsp+850h+var_810]
0x18000ea12  call    FormatRRASErrorString
0x18000ea17  test    cs:byte_18002D803, 8
0x18000ea1e  jz      short loc_18000EA38
0x18000ea20  lea     r8, [rsp+850h+var_810]
0x18000ea25  lea     rdx, RasSSTPSvcTraceError
0x18000ea2c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ea33  call    McTemplateU0z_EventWriteTransfer
0x18000ea38  lea     r9, [rbx+228h]
0x18000ea3f  mov     r8d, edi
0x18000ea42  mov     ecx, 1; dwMessageId
0x18000ea47  call    LogEventWithErrorParameter
0x18000ea4c  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000ea53  call    cs:__imp_EnterCriticalSection
0x18000ea59  mov     [rbx+10Ch], edi
0x18000ea5f  jmp     short loc_18000EAC3
0x18000ea61  test    cs:byte_18002D803, 10h
0x18000ea68  jz      short loc_18000EAAA
0x18000ea6a  xor     eax, eax
0x18000ea6c  lea     r8, [rbx+228h]
0x18000ea73  lea     rdx, aCoidHsSendrequ; "CoId=%hs:SendRequest completes successf"...
0x18000ea7a  mov     word ptr [rsp+850h+var_810], ax
0x18000ea7f  lea     rcx, [rsp+850h+var_810]
0x18000ea84  call    FormatRRASErrorString
0x18000ea89  test    cs:byte_18002D803, 10h
0x18000ea90  jz      short loc_18000EAAA
0x18000ea92  lea     r8, [rsp+850h+var_810]
0x18000ea97  lea     rdx, RasSSTPSvcTraceInfo
0x18000ea9e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000eaa5  call    McTemplateU0z_EventWriteTransfer
0x18000eaaa  lea     rdi, [rbx+120h]
0x18000eab1  mov     rcx, rdi; lpCriticalSection
0x18000eab4  call    cs:__imp_EnterCriticalSection
0x18000eaba  cmp     byte ptr [rbx+1B3h], 0
0x18000eac1  jz      short loc_18000EADA
0x18000eac3  btr     dword ptr [rbx+0FCh], 10h
0x18000eacb  mov     edx, 2
0x18000ead0  mov     rcx, rbx
0x18000ead3  call    InitiateCallContextCleanup
0x18000ead8  jmp     short loc_18000EB57
0x18000eada  mov     qword ptr [rsp+850h+pftDueTime.dwLowDateTime], 0
0x18000eae3  mov     [rsp+850h+var_820], 0
0x18000eaeb  lock inc dword ptr [rbx+0D0h]
0x18000eaf2  mov     rcx, [rbx+1C8h]; pti
0x18000eaf9  lea     rdx, [rsp+850h+pftDueTime]; pftDueTime
0x18000eafe  xor     r9d, r9d; msWindowLength
0x18000eb01  mov     qword ptr [rsp+850h+pftDueTime.dwLowDateTime], 0FFFFFFFFDC3CBA00h
0x18000eb0a  xor     r8d, r8d; msPeriod
0x18000eb0d  call    cs:__imp_SetThreadpoolTimer
0x18000eb13  mov     rcx, rdi; lpCriticalSection
0x18000eb16  mov     byte ptr [rbx+1D0h], 0
0x18000eb1d  call    cs:__imp_LeaveCriticalSection
0x18000eb23  mov     rcx, [rbx+1C0h]
0x18000eb2a  lea     r9, SstpWebReceiveResponseCompletion
0x18000eb31  lea     r8, [rsp+850h+var_820]
0x18000eb36  mov     [rsp+850h+var_830], rbx
0x18000eb3b  xor     edx, edx
0x18000eb3d  call    cs:__imp_WebReceiveHttpResponse
0x18000eb43  cmp     eax, 3E5h
0x18000eb48  jz      short loc_18000EB57
0x18000eb4a  xor     r8d, r8d
0x18000eb4d  mov     edx, eax
0x18000eb4f  mov     rcx, rbx
0x18000eb52  call    SstpWebReceiveResponseCompletion
0x18000eb57  lea     rcx, [rbx+0D0h]
0x18000eb5e  call    DereferenceRefCount
0x18000eb63  mov     rcx, [rbp+750h+var_10]
0x18000eb6a  xor     rcx, rsp; StackCookie
0x18000eb6d  call    __security_check_cookie
0x18000eb72  lea     r11, [rsp+850h+var_s0]
0x18000eb7a  mov     rbx, [r11+20h]
0x18000eb7e  mov     rdi, [r11+28h]
0x18000eb82  mov     rsp, r11
0x18000eb85  pop     rbp
0x18000eb86  retn
```
