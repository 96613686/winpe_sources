# UpdatePolicyTelemetry::GPPolicyRefresh<wchar_t const *,bool &,bool &,unsigned __int64 &,long &>(wchar_t const * &&,bool &,bool &,unsigned __int64 &,long &)

- ea: `0x18000e0dc`
- end: `0x18000e30a`
- name: `??$GPPolicyRefresh@PEB_WAEA_NAEA_NAEA_KAEAJ@UpdatePolicyTelemetry@@SAX$$QEAPEB_WAEA_N1AEA_KAEAJ@Z`
- size: `558`
- prototype: `__int64 __fastcall(const OLECHAR **, char *, char *, __int64 *, WINBOOL *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cfc0`

## callees

- `0x18000109c`
- `0x18000140c`
- `0x18000e0dc`
- `0x18002ffd0`
- `0x180030714`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e1d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e1d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e135`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e135`

## pseudocode

```c
__int64 __fastcall UpdatePolicyTelemetry::GPPolicyRefresh<wchar_t const *,bool &,bool &,unsigned __int64 &,long &>(
        const OLECHAR **a1,
        char *a2,
        char *a3,
        __int64 *a4,
        WINBOOL *a5)
{
  __int64 result; // rax
  __int64 v10; // r10
  WINBOOL v11; // ecx
  const OLECHAR *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  char v15; // [rsp+38h] [rbp-71h] BYREF
  char v16; // [rsp+39h] [rbp-70h] BYREF
  __int64 v17; // [rsp+40h] [rbp-69h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-61h] BYREF
  WINBOOL fPending; // [rsp+50h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+58h] [rbp-51h] BYREF
  const OLECHAR *v21; // [rsp+78h] [rbp-31h]
  int v22; // [rsp+80h] [rbp-29h]
  int v23; // [rsp+84h] [rbp-25h]
  char *v24; // [rsp+88h] [rbp-21h]
  __int64 v25; // [rsp+90h] [rbp-19h]
  char *v26; // [rsp+98h] [rbp-11h]
  __int64 v27; // [rsp+A0h] [rbp-9h]
  __int64 *v28; // [rsp+A8h] [rbp-1h]
  __int64 v29; // [rsp+B0h] [rbp+7h]
  WINBOOL *p_fPending; // [rsp+B8h] [rbp+Fh]
  __int64 v31; // [rsp+C0h] [rbp+17h]
  LPVOID *p_Context; // [rsp+C8h] [rbp+1Fh]
  __int64 v33; // [rsp+D0h] [rbp+27h]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`UpdatePolicyTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_18004ECE0 = 0;
    Context = &qword_18004ECD8;
    qword_18004ECD8 = (__int64)&UpdatePolicyTelemetry::`vftable';
    byte_18004ECE8 = 0;
    dword_18004ECEC = 0;
    CallbackContext = &`UpdatePolicyTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_681e915199f9cd14aaed8046bf90802b_::_lambda_invoker_cdecl_);
    qword_18004ECE0 = (__int64)CallbackContext;
    byte_18004ECE8 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_18004ECEC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004ECD8 + 8))(&qword_18004ECD8);
    InitOnceComplete(&`UpdatePolicyTelemetry::Instance'::`2'::wrapper, 0, &qword_18004ECD8);
  }
  result = (__int64)Context;
  v10 = *((_QWORD *)Context + 1);
  if ( *(_DWORD *)v10 > 5u && (*(_QWORD *)(v10 + 16) & 0x800000000000LL) != 0 )
  {
    result = *(_QWORD *)(v10 + 24) & 0x800000000000LL;
    if ( result == *(_QWORD *)(v10 + 24) )
    {
      v31 = 4;
      Context = (LPVOID)2164260864LL;
      v33 = 8;
      v29 = 8;
      v27 = 1;
      v11 = *a5;
      v17 = *a4;
      v15 = *a3;
      v16 = *a2;
      p_Context = &Context;
      p_fPending = &fPending;
      v28 = &v17;
      fPending = v11;
      v12 = *a1;
      v26 = &v15;
      v24 = &v16;
      v25 = 1;
      if ( v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        v14 = 2 * v13 + 2;
      }
      else
      {
        v12 = &psz;
        v14 = 2;
      }
      v22 = v14;
      v21 = v12;
      v23 = 0;
      return tlgWriteTransfer_EventWriteTransfer(v10, (int)&byte_180042C49, 0, 0, 8u, &v20);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e0dc  mov     rax, rsp
0x18000e0df  mov     [rax+8], rbx
0x18000e0e3  mov     [rax+10h], rsi
0x18000e0e7  mov     [rax+18h], rdi
0x18000e0eb  mov     [rax+20h], r12
0x18000e0ef  push    rbp
0x18000e0f0  push    r14
0x18000e0f2  push    r15
0x18000e0f4  lea     rbp, [rax-57h]
0x18000e0f8  sub     rsp, 0E0h
0x18000e0ff  mov     rax, cs:__security_cookie
0x18000e106  xor     rax, rsp
0x18000e109  mov     [rbp+4Fh+var_20], rax
0x18000e10d  mov     rbx, r9
0x18000e110  mov     rdi, r8
0x18000e113  mov     rsi, rdx
0x18000e116  lea     r9, [rbp+4Fh+Context]; lpContext
0x18000e11a  mov     r14, rcx
0x18000e11d  lea     r8, [rbp+4Fh+fPending]; fPending
0x18000e121  xor     r12d, r12d
0x18000e124  lea     rcx, ?wrapper@?1??Instance@UpdatePolicyTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUpdatePolicyTelemetry@@@details@wil@@A; lpInitOnce
0x18000e12b  xor     edx, edx; dwFlags
0x18000e12d  mov     [rbp+4Fh+Context], r12
0x18000e131  mov     [rbp+4Fh+fPending], r12d
0x18000e135  call    cs:__imp_InitOnceBeginInitialize
0x18000e13b  test    eax, eax
0x18000e13d  jz      loc_18000E1DE
0x18000e143  cmp     [rbp+4Fh+fPending], r12d
0x18000e147  jz      loc_18000E1DE
0x18000e14d  lea     r15, qword_18004ECD8
0x18000e154  mov     cs:qword_18004ECE0, r12
0x18000e15b  lea     rax, ??_7UpdatePolicyTelemetry@@6B@; const UpdatePolicyTelemetry::`vftable'
0x18000e162  mov     [rbp+4Fh+Context], r15
0x18000e166  mov     cs:qword_18004ECD8, rax
0x18000e16d  mov     cs:byte_18004ECE8, r12b
0x18000e174  mov     cs:dword_18004ECEC, r12d
0x18000e17b  lea     rax, ?__hInner@?1???0StaticHandle@UpdatePolicyTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UpdatePolicyTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e182  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_681e915199f9cd14aaed8046bf90802b_@@CA@XZ; void (__cdecl *)()
0x18000e189  mov     cs:CallbackContext, rax
0x18000e190  call    atexit
0x18000e195  mov     rcx, cs:CallbackContext; CallbackContext
0x18000e19c  mov     cs:qword_18004ECE0, rcx
0x18000e1a3  mov     cs:byte_18004ECE8, 1
0x18000e1aa  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000e1af  mov     rax, cs:qword_18004ECD8
0x18000e1b6  mov     rcx, r15
0x18000e1b9  mov     cs:dword_18004ECEC, 1
0x18000e1c3  mov     rax, [rax+8]
0x18000e1c7  call    _guard_dispatch_icall
0x18000e1cc  mov     r8, r15; lpContext
0x18000e1cf  lea     rcx, ?wrapper@?1??Instance@UpdatePolicyTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUpdatePolicyTelemetry@@@details@wil@@A; lpInitOnce
0x18000e1d6  xor     edx, edx; dwFlags
0x18000e1d8  call    cs:__imp_InitOnceComplete
0x18000e1de  mov     rax, [rbp+4Fh+Context]
0x18000e1e2  mov     r10, [rax+8]
0x18000e1e6  cmp     dword ptr [r10], 5
0x18000e1ea  jbe     loc_18000E2DD
0x18000e1f0  mov     rcx, 800000000000h
0x18000e1fa  test    [r10+10h], rcx
0x18000e1fe  jz      loc_18000E2DD
0x18000e204  mov     rax, [r10+18h]
0x18000e208  and     rax, rcx
0x18000e20b  cmp     rax, [r10+18h]
0x18000e20f  jnz     loc_18000E2DD
0x18000e215  mov     eax, 81000000h
0x18000e21a  mov     [rbp+4Fh+var_38], 4
0x18000e222  mov     [rbp+4Fh+Context], rax
0x18000e226  mov     edx, 8
0x18000e22b  mov     rax, [rbp+4Fh+arg_20]
0x18000e22f  mov     [rbp+4Fh+var_28], rdx
0x18000e233  mov     [rbp+4Fh+var_48], rdx
0x18000e237  mov     [rbp+4Fh+var_58], 1
0x18000e23f  mov     ecx, [rax]
0x18000e241  mov     rax, [rbx]
0x18000e244  mov     [rbp+4Fh+var_B8], rax
0x18000e248  mov     al, [rdi]
0x18000e24a  mov     [rbp+4Fh+var_C0], al
0x18000e24d  mov     al, [rsi]
0x18000e24f  mov     [rbp+4Fh+var_BF], al
0x18000e252  lea     rax, [rbp+4Fh+Context]
0x18000e256  mov     [rbp+4Fh+var_30], rax
0x18000e25a  lea     rax, [rbp+4Fh+fPending]
0x18000e25e  mov     [rbp+4Fh+var_40], rax
0x18000e262  lea     rax, [rbp+4Fh+var_B8]
0x18000e266  mov     [rbp+4Fh+var_50], rax
0x18000e26a  lea     rax, [rbp+4Fh+var_C0]
0x18000e26e  mov     [rbp+4Fh+fPending], ecx
0x18000e271  mov     rcx, [r14]
0x18000e274  mov     [rbp+4Fh+var_60], rax
0x18000e278  lea     rax, [rbp+4Fh+var_BF]
0x18000e27c  mov     [rbp+4Fh+var_70], rax
0x18000e280  mov     [rbp+4Fh+var_68], 1
0x18000e288  test    rcx, rcx
0x18000e28b  jz      short loc_18000E2A4
0x18000e28d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e291  inc     rax
0x18000e294  cmp     [rcx+rax*2], r12w
0x18000e299  jnz     short loc_18000E291
0x18000e29b  lea     eax, ds:2[rax*2]
0x18000e2a2  jmp     short loc_18000E2B0
0x18000e2a4  lea     rcx, psz
0x18000e2ab  mov     eax, 2
0x18000e2b0  mov     [rbp+4Fh+var_78], eax
0x18000e2b3  xor     r9d, r9d; int
0x18000e2b6  lea     rax, [rbp+4Fh+var_A0]
0x18000e2ba  mov     [rbp+4Fh+var_80], rcx
0x18000e2be  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x18000e2c3  xor     r8d, r8d; int
0x18000e2c6  mov     [rsp+0F0h+var_D0], edx; ULONG
0x18000e2ca  mov     rcx, r10; int
0x18000e2cd  lea     rdx, byte_180042C49; int
0x18000e2d4  mov     [rbp+4Fh+var_74], r12d
0x18000e2d8  call    _tlgWriteTransfer_EventWriteTransfer
0x18000e2dd  mov     rcx, [rbp+4Fh+var_20]
0x18000e2e1  xor     rcx, rsp; StackCookie
0x18000e2e4  call    __security_check_cookie
0x18000e2e9  lea     r11, [rsp+0F0h+var_10]
0x18000e2f1  mov     rbx, [r11+20h]
0x18000e2f5  mov     rsi, [r11+28h]
0x18000e2f9  mov     rdi, [r11+30h]
0x18000e2fd  mov     r12, [r11+38h]
0x18000e301  mov     rsp, r11
0x18000e304  pop     r15
0x18000e306  pop     r14
0x18000e308  pop     rbp
0x18000e309  retn
```
