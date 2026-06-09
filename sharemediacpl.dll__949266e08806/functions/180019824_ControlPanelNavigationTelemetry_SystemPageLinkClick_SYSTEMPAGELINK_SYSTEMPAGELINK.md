# ControlPanelNavigationTelemetry::SystemPageLinkClick<SYSTEMPAGELINK>(SYSTEMPAGELINK &&)

- ea: `0x180019824`
- end: `0x180019984`
- name: `??$SystemPageLinkClick@W4SYSTEMPAGELINK@@@ControlPanelNavigationTelemetry@@SAX$$QEAW4SYSTEMPAGELINK@@@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b960`

## callees

- `0x18000163c`
- `0x180001d60`
- `0x18000213c`
- `0x180019824`
- `0x180019a58`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18001986f`
- `KERNEL32!InitOnceBeginInitialize` at `0x18001986f`

## pseudocode

```c
__int64 __fastcall ControlPanelNavigationTelemetry::SystemPageLinkClick<enum SYSTEMPAGELINK>(char *a1)
{
  unsigned int *v2; // rcx
  __int64 result; // rax
  __int64 v4; // rdx
  char v5; // [rsp+30h] [rbp-19h] BYREF
  WINBOOL fPending; // [rsp+34h] [rbp-15h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-11h] BYREF
  union _RTL_RUN_ONCE *v8; // [rsp+40h] [rbp-9h] BYREF
  int v9; // [rsp+48h] [rbp-1h]
  _BYTE v10[32]; // [rsp+50h] [rbp+7h] BYREF
  char *v11; // [rsp+70h] [rbp+27h]
  __int64 v12; // [rsp+78h] [rbp+2Fh]
  LPVOID *p_Context; // [rsp+80h] [rbp+37h]
  __int64 v14; // [rsp+88h] [rbp+3Fh]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`ControlPanelNavigationTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    v8 = &`ControlPanelNavigationTelemetry::Instance'::`2'::wrapper;
    Context = &qword_18002A970;
    qword_18002A970 = (__int64)&wil::TraceLoggingProvider::`vftable';
    qword_18002A978 = 0;
    byte_18002A980 = 0;
    dword_18002A984 = 0;
    qword_18002A988 = (__int64)&`ControlPanelNavigationTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_0ca99fd8aeb53e91e15a05469392764c_::_lambda_invoker_cdecl_);
    v9 = 0;
    wil::details::static_lazy<ControlPanelNavigationTelemetry>::Completer::~Completer(&v8);
  }
  v2 = (unsigned int *)*((_QWORD *)Context + 1);
  result = *v2;
  if ( (unsigned int)result > 5 )
  {
    v4 = *((_QWORD *)v2 + 3);
    result = *((_QWORD *)v2 + 2);
    if ( (result & 0x400000000000LL) != 0 )
    {
      result = v4 & 0x400000000000LL;
      if ( (v4 & 0x400000000000LL) == v4 )
      {
        v5 = *a1;
        Context = (LPVOID)0x2000000;
        p_Context = &Context;
        v14 = 8;
        v11 = &v5;
        v12 = 1;
        return tlgWriteTransfer_EtwEventWriteTransfer(
                 (__int64)v2,
                 (unsigned __int8 *)byte_180024009,
                 0,
                 0,
                 4,
                 (__int64)v10);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019824  mov     [rsp-8+arg_0], rbx
0x180019829  mov     [rsp-8+arg_8], rsi
0x18001982e  push    rbp
0x18001982f  lea     rbp, [rsp-57h]
0x180019834  sub     rsp, 0A0h
0x18001983b  mov     rax, cs:__security_cookie
0x180019842  xor     rax, rsp
0x180019845  mov     [rbp+57h+var_10], rax
0x180019849  mov     rbx, rcx
0x18001984c  mov     [rbp+57h+Context], 0
0x180019854  lea     rsi, ?wrapper@?1??Instance@ControlPanelNavigationTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VControlPanelNavigationTelemetry@@@details@wil@@A; wil::details::static_lazy<ControlPanelNavigationTelemetry> `ControlPanelNavigationTelemetry::Instance(void)'::`2'::wrapper
0x18001985b  mov     [rbp+57h+fPending], 0
0x180019862  mov     rcx, rsi; lpInitOnce
0x180019865  lea     r9, [rbp+57h+Context]; lpContext
0x180019869  lea     r8, [rbp+57h+fPending]; fPending
0x18001986d  xor     edx, edx; dwFlags
0x18001986f  call    cs:__imp_InitOnceBeginInitialize
0x180019875  test    eax, eax
0x180019877  jz      short loc_1800198E2
0x180019879  cmp     [rbp+57h+fPending], 0
0x18001987d  jz      short loc_1800198E2
0x18001987f  lea     rax, qword_18002A970
0x180019886  mov     [rbp+57h+var_60], rsi
0x18001988a  mov     [rbp+57h+Context], rax
0x18001988e  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180019895  mov     cs:qword_18002A970, rax
0x18001989c  mov     cs:qword_18002A978, 0
0x1800198a7  mov     cs:byte_18002A980, 0
0x1800198ae  mov     cs:dword_18002A984, 0
0x1800198b8  lea     rax, ?__hInner@?1???0StaticHandle@ControlPanelNavigationTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ControlPanelNavigationTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800198bf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0ca99fd8aeb53e91e15a05469392764c_@@CA@XZ; void (__cdecl *)()
0x1800198c6  mov     cs:qword_18002A988, rax
0x1800198cd  call    atexit
0x1800198d2  lea     rcx, [rbp+57h+var_60]
0x1800198d6  mov     [rbp+57h+var_58], 0
0x1800198dd  call    ??1Completer@?$static_lazy@VControlPanelNavigationTelemetry@@@details@wil@@QEAA@XZ; wil::details::static_lazy<ControlPanelNavigationTelemetry>::Completer::~Completer(void)
0x1800198e2  mov     rax, [rbp+57h+Context]
0x1800198e6  mov     rcx, [rax+8]
0x1800198ea  mov     eax, [rcx]
0x1800198ec  cmp     eax, 5
0x1800198ef  jbe     short loc_180019963
0x1800198f1  mov     rdx, [rcx+18h]
0x1800198f5  mov     r8, 400000000000h
0x1800198ff  mov     rax, [rcx+10h]
0x180019903  test    r8, rax
0x180019906  jz      short loc_180019963
0x180019908  mov     rax, rdx
0x18001990b  and     rax, r8
0x18001990e  cmp     rax, rdx
0x180019911  jnz     short loc_180019963
0x180019913  mov     al, [rbx]
0x180019915  lea     rdx, byte_180024009
0x18001991c  mov     [rbp+57h+var_70], al
0x18001991f  xor     r9d, r9d
0x180019922  lea     rax, [rbp+57h+Context]
0x180019926  mov     [rbp+57h+Context], 2000000h
0x18001992e  mov     [rbp+57h+var_20], rax
0x180019932  xor     r8d, r8d
0x180019935  lea     rax, [rbp+57h+var_70]
0x180019939  mov     [rbp+57h+var_18], 8
0x180019941  mov     [rbp+57h+var_30], rax
0x180019945  lea     rax, [rbp+57h+var_50]
0x180019949  mov     [rsp+0A0h+var_78], rax
0x18001994e  mov     [rsp+0A0h+var_80], 4
0x180019956  mov     [rbp+57h+var_28], 1
0x18001995e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180019963  mov     rcx, [rbp+57h+var_10]
0x180019967  xor     rcx, rsp; StackCookie
0x18001996a  call    __security_check_cookie
0x18001996f  lea     r11, [rsp+0A0h+var_s0]
0x180019977  mov     rbx, [r11+10h]
0x18001997b  mov     rsi, [r11+18h]
0x18001997f  mov     rsp, r11
0x180019982  pop     rbp
0x180019983  retn
```
