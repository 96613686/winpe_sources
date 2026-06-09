# ResponseWaitTimeout

- ea: `0x18000dd70`
- end: `0x18000deff`
- name: `ResponseWaitTimeout`
- size: `399`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002f50`
- `0x1800089dc`
- `0x180008b90`
- `0x18000dd70`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de86`
- `webio!__imp_WebCancelHttpRequest` at `0x18000de2b`
- `webio!__imp_WebCancelHttpRequest` at `0x18000de2b`

## string_xrefs

- `0x18000de4e`: `CoId=%hs:WebCancelHttpRequest(timeout) completes with %d`

## pseudocode

```c
void __fastcall ResponseWaitTimeout(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)
{
  unsigned int v4; // eax
  int v5; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString(&v5, L"Entering %ws", L"ResponseWaitTimeout");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v5);
  }
  _InterlockedIncrement((volatile signed __int32 *)Context + 52);
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 288));
  if ( !Context[464] )
  {
    v4 = WebCancelHttpRequest(*((_QWORD *)Context + 56), 0);
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString(&v5, L"CoId=%hs:WebCancelHttpRequest(timeout) completes with %d", Context + 552, v4);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
          (const wchar_t *)&v5);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 288));
  DereferenceRefCount(Context + 208);
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString(&v5, L"LEaving %ws", L"ResponseWaitTimeout");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v5);
  }
}

```

## disassembly

```asm
0x18000dd70  push    rbp
0x18000dd72  push    rbx
0x18000dd73  push    rsi
0x18000dd74  push    rdi
0x18000dd75  lea     rbp, [rsp-738h]
0x18000dd7d  sub     rsp, 838h
0x18000dd84  mov     rax, cs:__security_cookie
0x18000dd8b  xor     rax, rsp
0x18000dd8e  mov     [rbp+750h+var_30], rax
0x18000dd95  mov     rbx, rdx
0x18000dd98  lea     rcx, [rsp+850h+var_82C]; void *
0x18000dd9d  xor     eax, eax
0x18000dd9f  xor     edx, edx; Val
0x18000dda1  mov     r8d, 7FCh; Size
0x18000dda7  mov     [rsp+850h+var_830], eax
0x18000ddab  call    memset_0
0x18000ddb0  test    cs:byte_18002E903, 10h
0x18000ddb7  jz      short loc_18000DDF9
0x18000ddb9  xor     eax, eax
0x18000ddbb  lea     r8, aResponsewaitti; "ResponseWaitTimeout"
0x18000ddc2  lea     rdx, aEnteringWs; "Entering %ws"
0x18000ddc9  mov     word ptr [rsp+850h+var_830], ax
0x18000ddce  lea     rcx, [rsp+850h+var_830]
0x18000ddd3  call    FormatRRASErrorString
0x18000ddd8  test    cs:byte_18002E903, 10h
0x18000dddf  jz      short loc_18000DDF9
0x18000dde1  lea     r8, [rsp+850h+var_830]
0x18000dde6  lea     rdx, RasSSTPSvcTraceInfo
0x18000dded  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ddf4  call    McTemplateU0z_EventWriteTransfer
0x18000ddf9  lea     rdi, [rbx+0D0h]
0x18000de00  lock inc dword ptr [rdi]
0x18000de03  lea     rsi, [rbx+120h]
0x18000de0a  mov     rcx, rsi; lpCriticalSection
0x18000de0d  call    cs:__imp_EnterCriticalSection
0x18000de14  nop     dword ptr [rax+rax+00h]
0x18000de19  cmp     byte ptr [rbx+1D0h], 0
0x18000de20  jnz     short loc_18000DE83
0x18000de22  mov     rcx, [rbx+1C0h]
0x18000de29  xor     edx, edx
0x18000de2b  call    cs:__imp_WebCancelHttpRequest
0x18000de32  nop     dword ptr [rax+rax+00h]
0x18000de37  test    cs:byte_18002E903, 8
0x18000de3e  jz      short loc_18000DE83
0x18000de40  xor     ecx, ecx
0x18000de42  lea     r8, [rbx+228h]
0x18000de49  mov     word ptr [rsp+850h+var_830], cx
0x18000de4e  lea     rdx, aCoidHsWebcance_0; "CoId=%hs:WebCancelHttpRequest(timeout) "...
0x18000de55  lea     rcx, [rsp+850h+var_830]
0x18000de5a  mov     r9d, eax
0x18000de5d  call    FormatRRASErrorString
0x18000de62  test    cs:byte_18002E903, 8
0x18000de69  jz      short loc_18000DE83
0x18000de6b  lea     r8, [rsp+850h+var_830]
0x18000de70  lea     rdx, RasSSTPSvcTraceError
0x18000de77  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000de7e  call    McTemplateU0z_EventWriteTransfer
0x18000de83  mov     rcx, rsi; lpCriticalSection
0x18000de86  call    cs:__imp_LeaveCriticalSection
0x18000de8d  nop     dword ptr [rax+rax+00h]
0x18000de92  mov     rcx, rdi
0x18000de95  call    DereferenceRefCount
0x18000de9a  test    cs:byte_18002E903, 10h
0x18000dea1  jz      short loc_18000DEE3
0x18000dea3  xor     eax, eax
0x18000dea5  lea     r8, aResponsewaitti; "ResponseWaitTimeout"
0x18000deac  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000deb3  mov     word ptr [rsp+850h+var_830], ax
0x18000deb8  lea     rcx, [rsp+850h+var_830]
0x18000debd  call    FormatRRASErrorString
0x18000dec2  test    cs:byte_18002E903, 10h
0x18000dec9  jz      short loc_18000DEE3
0x18000decb  lea     r8, [rsp+850h+var_830]
0x18000ded0  lea     rdx, RasSSTPSvcTraceInfo
0x18000ded7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000dede  call    McTemplateU0z_EventWriteTransfer
0x18000dee3  mov     rcx, [rbp+750h+var_30]
0x18000deea  xor     rcx, rsp; StackCookie
0x18000deed  call    __security_check_cookie
0x18000def2  add     rsp, 838h
0x18000def9  pop     rdi
0x18000defa  pop     rsi
0x18000defb  pop     rbx
0x18000defc  pop     rbp
0x18000defd  retn
```
