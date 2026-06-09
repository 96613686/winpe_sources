# ChannelRequestCompleteWork::Invoke(void)

- ea: `0x180004ba0`
- end: `0x180004e26`
- name: `?Invoke@ChannelRequestCompleteWork@@UEAAJXZ`
- size: `646`
- prototype: `__int64 __fastcall(ChannelRequestCompleteWork *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004918`
- `0x180004ba0`
- `0x180004e38`
- `0x180004e64`
- `0x1800052ac`
- `0x18000e5f4`
- `0x18002cf14`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c5b`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180004d30`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180004d30`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180004c7d`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180004c7d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004cb6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004cb6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180004d46`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180004d46`
- `OLEAUT32!__imp_SysFreeString` at `0x180004dcf`
- `OLEAUT32!__imp_SysFreeString` at `0x180004dcf`

## string_xrefs

- `0x180004d90`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\requestcompletework.cpp`
- `0x180004da5`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\requestcompletework.cpp`
- `0x180004dba`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\requestcompletework.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ChannelRequestCompleteWork::Invoke(ChannelRequestCompleteWork *this)
{
  ChannelRequests *v2; // rbx
  int v3; // eax
  __int64 v4; // r9
  unsigned __int16 *v5; // rbx
  int v6; // eax
  const char *v7; // r9
  struct IWpnChannelRequest *v8; // rcx
  __int64 result; // rax
  int v10; // eax
  int DueTime; // [rsp+20h] [rbp-58h]
  int DueTimea; // [rsp+20h] [rbp-58h]
  int v13[2]; // [rsp+40h] [rbp-38h] BYREF
  int v14; // [rsp+48h] [rbp-30h]
  DWORD Parameter; // [rsp+50h] [rbp-28h] BYREF
  char v16; // [rsp+54h] [rbp-24h]
  HRESULT v17; // [rsp+58h] [rbp-20h]
  void *phNewTimer; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v20; // [rsp+80h] [rbp+8h] BYREF
  struct IWpnChannelRequest *v21; // [rsp+88h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp+18h] BYREF

  try
  {
    v2 = *(ChannelRequests **)(*((_QWORD *)this + 13) + 24LL);
    if ( !v2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
        *(_QWORD *)(*((_QWORD *)this + 13) + 24LL) == 0 ? (const char *)0x803E0105LL : 0,
        DueTime);
    v21 = 0;
    v20 = 0;
    bstrString = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v3 = ChannelRequests::GetAndRemoveRequest(v2, *((_DWORD *)this + 2), &v21, &bstrString, &v20);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
        (const char *)(unsigned int)v3,
        DueTimea);
    *(_QWORD *)v13 = 0;
    v14 = 0;
    v4 = *((unsigned int *)this + 20);
    v5 = bstrString;
    if ( (_DWORD)v4 )
    {
      if ( (byte_18015DE45 & 4) != 0 )
        McTemplateU0zq_EventWriteTransfer(retaddr, WPNEND_CHANNEL_REQUEST_FAILED, bstrString, v4);
    }
    else
    {
      v10 = ChannelRequestCompleteWork::AddChannelToTable(this, bstrString, (struct _WPN_FILE_TIME *)v13);
      if ( v10 >= 0 )
        ChannelRequestCompleteWork::AddToExemptionList(this, v5);
      else
        *((_DWORD *)this + 20) = v10;
    }
    Parameter = GetCurrentThreadId();
    v16 = 0;
    v17 = -2147467259;
    phNewTimer = 0;
    v17 = CoEnableCallCancellation(0);
    if ( v17 >= 0 )
      CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x3A98u, 0x3E8u, 0);
    v6 = (*(__int64 (__fastcall **)(struct IWpnChannelRequest *, _QWORD))(*(_QWORD *)v21 + 24LL))(
           v21,
           *((unsigned int *)this + 20));
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\requestcompletework.cpp",
        (const char *)(unsigned int)v6,
        (int)v13);
    if ( v17 >= 0 )
    {
      v17 = -2147467259;
      CoDisableCallCancellation(0);
      if ( phNewTimer )
        DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    }
    if ( v5 )
      SysFreeString(v5);
    v8 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(struct IWpnChannelRequest *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5C,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\reque"
                                         "stcompletework.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180004ba0  mov     r11, rsp
0x180004ba3  mov     [r11+20h], rbx
0x180004ba7  push    rdi
0x180004ba8  sub     rsp, 70h
0x180004bac  mov     rdi, rcx
0x180004baf  mov     rax, [rcx+68h]
0x180004bb3  mov     rbx, [rax+18h]
0x180004bb7  mov     rax, rbx
0x180004bba  neg     rax
0x180004bbd  sbb     r9d, r9d
0x180004bc0  not     r9d
0x180004bc3  and     r9d, 803E0105h; char *
0x180004bca  mov     rcx, [rsp+78h]; this
0x180004bcf  test    rbx, rbx
0x180004bd2  jz      loc_180004D90
0x180004bd8  mov     qword ptr [r11+10h], 0
0x180004be0  mov     dword ptr [r11+8], 0
0x180004be8  mov     qword ptr [r11+18h], 0
0x180004bf0  lea     rcx, [r11+10h]
0x180004bf4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004bf9  lea     rax, [rsp+78h+arg_0]
0x180004c01  mov     qword ptr [rsp+78h+DueTime], rax; int
0x180004c06  lea     r9, [rsp+78h+bstrString]; unsigned __int16 **
0x180004c0e  lea     r8, [rsp+78h+arg_8]; struct IWpnChannelRequest **
0x180004c16  mov     edx, [rdi+8]; unsigned int
0x180004c19  mov     rcx, rbx; this
0x180004c1c  call    ?GetAndRemoveRequest@ChannelRequests@@QEAAJKPEAPEAUIWpnChannelRequest@@PEAPEAGPEAH@Z; ChannelRequests::GetAndRemoveRequest(ulong,IWpnChannelRequest * *,ushort * *,int *)
0x180004c21  mov     rcx, [rsp+78h]; this
0x180004c26  test    eax, eax
0x180004c28  js      loc_180004DA2
0x180004c2e  xor     eax, eax
0x180004c30  mov     qword ptr [rsp+78h+var_38], rax
0x180004c35  mov     [rsp+78h+var_30], eax
0x180004c39  mov     r9d, [rdi+50h]
0x180004c3d  mov     rbx, [rsp+78h+bstrString]
0x180004c45  test    r9d, r9d
0x180004c48  jz      loc_180004DDA
0x180004c4e  test    cs:byte_18015DE45, 4
0x180004c55  jnz     loc_180004E06
0x180004c5b  call    cs:__imp_GetCurrentThreadId
0x180004c61  mov     [rsp+78h+Parameter], eax
0x180004c65  mov     [rsp+78h+var_24], 0
0x180004c6a  mov     [rsp+78h+var_20], 80004005h
0x180004c72  mov     [rsp+78h+phNewTimer], 0
0x180004c7b  xor     ecx, ecx; pReserved
0x180004c7d  call    cs:__imp_CoEnableCallCancellation
0x180004c83  mov     [rsp+78h+var_20], eax
0x180004c87  test    eax, eax
0x180004c89  js      short loc_180004CBD
0x180004c8b  mov     [rsp+78h+Flags], 0; Flags
0x180004c93  mov     [rsp+78h+Period], 3E8h; Period
0x180004c9b  mov     [rsp+78h+DueTime], 3A98h; DueTime
0x180004ca3  lea     r9, [rsp+78h+Parameter]; Parameter
0x180004ca8  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180004caf  xor     edx, edx; TimerQueue
0x180004cb1  lea     rcx, [rsp+78h+phNewTimer]; phNewTimer
0x180004cb6  call    cs:__imp_CreateTimerQueueTimer
0x180004cbc  nop
0x180004cbd  mov     rcx, [rsp+78h+arg_8]
0x180004cc5  mov     rax, [rcx]
0x180004cc8  mov     r10, [rax+18h]
0x180004ccc  movsd   xmm0, qword ptr [rsp+78h+var_38]
0x180004cd2  mov     eax, [rsp+78h+var_30]
0x180004cd6  lea     r9, [rdi+30h]
0x180004cda  cmp     qword ptr [r9+18h], 7
0x180004cdf  jbe     short loc_180004CE4
0x180004ce1  mov     r9, [r9]
0x180004ce4  lea     r8, [rdi+10h]
0x180004ce8  cmp     qword ptr [r8+18h], 7
0x180004ced  ja      loc_180004D88
0x180004cf3  movsd   qword ptr [rsp+78h+var_38], xmm0
0x180004cf9  mov     [rsp+78h+var_30], eax
0x180004cfd  lea     rax, [rsp+78h+var_38]
0x180004d02  mov     qword ptr [rsp+78h+DueTime], rax; int
0x180004d07  mov     edx, [rdi+50h]
0x180004d0a  mov     rax, r10
0x180004d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d12  mov     rcx, [rsp+78h]; this
0x180004d17  test    eax, eax
0x180004d19  js      loc_180004DB7
0x180004d1f  cmp     [rsp+78h+var_20], 0
0x180004d24  jl      short loc_180004D4D
0x180004d26  mov     [rsp+78h+var_20], 80004005h
0x180004d2e  xor     ecx, ecx; pReserved
0x180004d30  call    cs:__imp_CoDisableCallCancellation
0x180004d36  mov     rdx, [rsp+78h+phNewTimer]; Timer
0x180004d3b  test    rdx, rdx
0x180004d3e  jz      short loc_180004D4D
0x180004d40  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180004d44  xor     ecx, ecx; TimerQueue
0x180004d46  call    cs:__imp_DeleteTimerQueueTimer
0x180004d4c  nop
0x180004d4d  test    rbx, rbx
0x180004d50  jnz     short loc_180004DCC
0x180004d52  mov     rcx, [rsp+78h+arg_8]
0x180004d5a  test    rcx, rcx
0x180004d5d  jz      short loc_180004D78
0x180004d5f  mov     [rsp+78h+arg_8], 0
0x180004d6b  mov     rax, [rcx]
0x180004d6e  mov     rax, [rax+10h]
0x180004d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d77  nop
0x180004d78  xor     eax, eax
0x180004d7a  mov     rbx, [rsp+78h+arg_18]
0x180004d82  add     rsp, 70h
0x180004d86  pop     rdi
0x180004d87  retn
0x180004d88  mov     r8, [r8]
0x180004d8b  jmp     loc_180004CF3
0x180004d90  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004d97  mov     edx, 2Fh ; '/'; void *
0x180004d9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004da2  mov     r9d, eax; char *
0x180004da5  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004dac  mov     edx, 38h ; '8'; void *
0x180004db1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004db7  mov     r9d, eax; char *
0x180004dba  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004dc1  mov     edx, 57h ; 'W'; void *
0x180004dc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004dcc  mov     rcx, rbx; bstrString
0x180004dcf  call    cs:__imp_SysFreeString
0x180004dd5  jmp     loc_180004D52
0x180004dda  lea     r8, [rsp+78h+var_38]; struct _WPN_FILE_TIME *
0x180004ddf  mov     rdx, rbx; unsigned __int16 *
0x180004de2  mov     rcx, rdi; this
0x180004de5  call    ?AddChannelToTable@ChannelRequestCompleteWork@@AEAAJPEBGAEAU_WPN_FILE_TIME@@@Z; ChannelRequestCompleteWork::AddChannelToTable(ushort const *,_WPN_FILE_TIME &)
0x180004dea  test    eax, eax
0x180004dec  jns     short loc_180004DF6
0x180004dee  mov     [rdi+50h], eax
0x180004df1  jmp     loc_180004C5B
0x180004df6  mov     rdx, rbx; unsigned __int16 *
0x180004df9  mov     rcx, rdi; this
0x180004dfc  call    ?AddToExemptionList@ChannelRequestCompleteWork@@AEAAXPEBG@Z; ChannelRequestCompleteWork::AddToExemptionList(ushort const *)
0x180004e01  jmp     loc_180004C5B
0x180004e06  mov     r8, rbx
0x180004e09  lea     rdx, WPNEND_CHANNEL_REQUEST_FAILED
0x180004e10  call    McTemplateU0zq_EventWriteTransfer
0x180004e15  jmp     loc_180004C5B
0x180004e1a  mov     eax, [rsp+78h+arg_0]
0x180004e21  jmp     loc_180004D7A
```
