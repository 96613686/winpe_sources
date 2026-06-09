# CTSThread::SignalEventQueue(void)

- ea: `0x18003c900`
- end: `0x18003ca97`
- name: `?SignalEventQueue@CTSThread@@MEAAJXZ`
- size: `407`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180038cf0`
- `0x18003a9b0`
- `0x18003c220`
- `0x18003d5e0`
- `0x18003e460`

## callees

- `0x1800010b0`
- `0x18001b394`
- `0x18003c900`
- `0x180049010`

## string_xrefs

- `0x18003c970`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003c9af`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003ca0a`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003ca42`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003c97b`: `Failed to add thread for OnNotifyThreadMessage callback`
- `0x18003ca15`: `Failed to add thread for OnNotifyThreadMessage callback`
- `0x18003c9ba`: `_threadSignal is NULL!`
- `0x18003ca4d`: `_hThreadSignalEvent is NULL!`

## pseudocode

```c
__int64 __fastcall CTSThread::SignalEventQueue(CTSThread *this, __int64 a2, int a3, int a4)
{
  int v4; // ebx
  char *v5; // rdx
  const char *v6; // rax
  const char *v8; // [rsp+50h] [rbp-10h] BYREF
  int v9; // [rsp+80h] [rbp+20h] BYREF
  int v10; // [rsp+88h] [rbp+28h] BYREF
  const char *v11; // [rsp+90h] [rbp+30h] BYREF
  const char *v12; // [rsp+98h] [rbp+38h] BYREF

  v4 = -2147467259;
  if ( *((_DWORD *)this + 46) )
  {
    if ( *((_QWORD *)this + 85) )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 92) + 64LL))(*((_QWORD *)this + 92));
      if ( v4 < 0 )
      {
        LODWORD(this) = dword_18005C008;
        if ( (unsigned int)dword_18005C008 > 2 )
        {
          v9 = 2570;
          v11 = "SignalEventQueue";
          v5 = (char *)&dword_180054FF4;
          v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
          v6 = "Failed to add thread for OnNotifyThreadMessage callback";
LABEL_14:
          v8 = v6;
          v10 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)this,
            (_DWORD)v5,
            a3,
            a4,
            (__int64)&v8,
            (__int64)&v10,
            (__int64)&v12,
            (__int64)&v9,
            (__int64)&v11);
        }
      }
    }
    else if ( (unsigned int)dword_18005C008 > 2 )
    {
      v9 = 2575;
      v11 = "SignalEventQueue";
      v5 = &byte_180054FAF;
      v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v6 = "_threadSignal is NULL!";
      goto LABEL_14;
    }
  }
  else
  {
    this = (CTSThread *)*((_QWORD *)this + 86);
    if ( this == (CTSThread *)-1LL )
    {
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        v9 = 2588;
        v11 = "SignalEventQueue";
        v5 = byte_180054F25;
        v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v6 = "_hThreadSignalEvent is NULL!";
        goto LABEL_14;
      }
    }
    else
    {
      v4 = PAL_System_CondSignal();
      if ( v4 < 0 && (unsigned int)dword_18005C008 > 2 )
      {
        v9 = 2583;
        v11 = "SignalEventQueue";
        v5 = (char *)word_180054F6A;
        v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v6 = "Failed to add thread for OnNotifyThreadMessage callback";
        goto LABEL_14;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003c900  push    rbp
0x18003c902  push    rbx
0x18003c903  push    rdi
0x18003c904  mov     rbp, rsp
0x18003c907  sub     rsp, 60h
0x18003c90b  mov     edi, 80004005h
0x18003c910  mov     ebx, edi
0x18003c912  cmp     dword ptr [rcx+0B8h], 0
0x18003c919  jz      loc_18003C9C6
0x18003c91f  mov     rdx, [rcx+2A8h]
0x18003c926  test    rdx, rdx
0x18003c929  jz      short loc_18003C987
0x18003c92b  mov     rcx, [rcx+2E0h]
0x18003c932  mov     rax, [rcx]
0x18003c935  mov     rax, [rax+40h]
0x18003c939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c93e  mov     ebx, eax
0x18003c940  test    eax, eax
0x18003c942  jns     loc_18003CA8D
0x18003c948  mov     ecx, cs:dword_18005C008
0x18003c94e  cmp     ecx, 2
0x18003c951  jbe     loc_18003CA8D
0x18003c957  lea     rax, aSignaleventque; "SignalEventQueue"
0x18003c95e  mov     [rbp+arg_0], 0A0Ah
0x18003c965  mov     [rbp+arg_10], rax
0x18003c969  lea     rdx, dword_180054FF4
0x18003c970  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003c977  mov     [rbp+arg_18], rax
0x18003c97b  lea     rax, aFailedToAddThr; "Failed to add thread for OnNotifyThread"...
0x18003c982  jmp     loc_18003CA54
0x18003c987  mov     eax, cs:dword_18005C008
0x18003c98d  cmp     eax, 2
0x18003c990  jbe     loc_18003CA8D
0x18003c996  lea     rax, aSignaleventque; "SignalEventQueue"
0x18003c99d  mov     [rbp+arg_0], 0A0Fh
0x18003c9a4  mov     [rbp+arg_10], rax
0x18003c9a8  lea     rdx, byte_180054FAF
0x18003c9af  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003c9b6  mov     [rbp+arg_18], rax
0x18003c9ba  lea     rax, aThreadsignalIs; "_threadSignal is NULL!"
0x18003c9c1  jmp     loc_18003CA54
0x18003c9c6  mov     rcx, [rcx+2B0h]
0x18003c9cd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003c9d1  jz      short loc_18003CA1E
0x18003c9d3  call    PAL_System_CondSignal
0x18003c9d8  mov     ebx, eax
0x18003c9da  test    eax, eax
0x18003c9dc  jns     loc_18003CA8D
0x18003c9e2  mov     eax, cs:dword_18005C008
0x18003c9e8  cmp     eax, 2
0x18003c9eb  jbe     loc_18003CA8D
0x18003c9f1  lea     rax, aSignaleventque; "SignalEventQueue"
0x18003c9f8  mov     [rbp+arg_0], 0A17h
0x18003c9ff  mov     [rbp+arg_10], rax
0x18003ca03  lea     rdx, word_180054F6A
0x18003ca0a  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003ca11  mov     [rbp+arg_18], rax
0x18003ca15  lea     rax, aFailedToAddThr; "Failed to add thread for OnNotifyThread"...
0x18003ca1c  jmp     short loc_18003CA54
0x18003ca1e  mov     eax, cs:dword_18005C008
0x18003ca24  cmp     eax, 2
0x18003ca27  jbe     short loc_18003CA8D
0x18003ca29  lea     rax, aSignaleventque; "SignalEventQueue"
0x18003ca30  mov     [rbp+arg_0], 0A1Ch
0x18003ca37  mov     [rbp+arg_10], rax
0x18003ca3b  lea     rdx, byte_180054F25
0x18003ca42  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003ca49  mov     [rbp+arg_18], rax
0x18003ca4d  lea     rax, aHthreadsignale; "_hThreadSignalEvent is NULL!"
0x18003ca54  mov     [rbp+var_10], rax
0x18003ca58  lea     rax, [rbp+arg_10]
0x18003ca5c  mov     [rsp+60h+var_20], rax
0x18003ca61  lea     rax, [rbp+arg_0]
0x18003ca65  mov     [rsp+60h+var_28], rax
0x18003ca6a  lea     rax, [rbp+arg_18]
0x18003ca6e  mov     [rsp+60h+var_30], rax
0x18003ca73  lea     rax, [rbp+arg_8]
0x18003ca77  mov     [rsp+60h+var_38], rax
0x18003ca7c  lea     rax, [rbp+var_10]
0x18003ca80  mov     [rsp+60h+var_40], rax
0x18003ca85  mov     [rbp+arg_8], edi
0x18003ca88  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003ca8d  mov     eax, ebx
0x18003ca8f  add     rsp, 60h
0x18003ca93  pop     rdi
0x18003ca94  pop     rbx
0x18003ca95  pop     rbp
0x18003ca96  retn
```
