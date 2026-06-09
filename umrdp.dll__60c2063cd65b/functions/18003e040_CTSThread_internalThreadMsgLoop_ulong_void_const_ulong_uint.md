# CTSThread::internalThreadMsgLoop(ulong,void * const *,ulong,uint *)

- ea: `0x18003e040`
- end: `0x18003e459`
- name: `?internalThreadMsgLoop@CTSThread@@IEAAJKPEBQEAXKPEAI@Z`
- size: `1049`
- prototype: `__int64 __usercall@<rax>(CTSThread *__hidden this@<rcx>, unsigned int@<edx>, void *const *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18003d5b0`
- `0x18003e460`

## callees

- `0x180001008`
- `0x1800010b0`
- `0x1800011c8`
- `0x1800014c0`
- `0x180001674`
- `0x18000b98c`
- `0x18001bae0`
- `0x18003bb90`
- `0x18003c220`
- `0x18003ddc4`
- `0x18003e040`
- `0x180047ea6`
- `0x180047ebe`
- `0x180047ef0`
- `0x180049010`

## string_xrefs

- `0x18003e0be`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003e31c`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003e3cc`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003e0a3`: `internalThreadMsgLoop`
- `0x18003e308`: `internalThreadMsgLoop`
- `0x18003e3c0`: `internalThreadMsgLoop`
- `0x18003e141`: `Entering thread msg loop for ID %#x`
- `0x18003e189`: `Leaving thread msg loop for ID %#x. Status: 0x%x`
- `0x18003e227`: `Failed to run thread events`
- `0x18003e2af`: `Thread msg queued`
- `0x18003e328`: `Thread: 0x%x bailing out because of defered quit`
- `0x18003e3d8`: `Thread: 0x%x bailing because of error while waiting on condition`

## pseudocode

```c
__int64 __fastcall CTSThread::internalThreadMsgLoop(
        CTSThread *this,
        unsigned int a2,
        void *const *a3,
        int a4,
        unsigned int *a5)
{
  __int64 v6; // rsi
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ebx
  int v13; // eax
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int ActivityIdPrefix; // eax
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  const char *v25; // [rsp+58h] [rbp-A8h] BYREF
  const char *v26; // [rsp+60h] [rbp-A0h] BYREF
  const char *v27; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v28[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v29[64]; // [rsp+80h] [rbp-80h] BYREF

  v6 = a2;
  memset_0(v29, 0, sizeof(v29));
  if ( (unsigned int)v6 >= 0x40 )
  {
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      v24 = 1854;
      v26 = "internalThreadMsgLoop";
      v27 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v25 = "Too many wait objects";
      v23 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)word_1800552EA,
        v10,
        v11,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v27,
        (__int64)&v24,
        (__int64)&v26);
    }
    return (unsigned int)-2147024809;
  }
  if ( !(_DWORD)v6 )
  {
    if ( (unsigned int)dword_18005C008 > 5 )
    {
      v23 = *((_DWORD *)this + 14);
      v25 = "Entering thread msg loop for ID %#x";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_1800552B3,
        v10,
        v11,
        (__int64)&v25,
        (__int64)&v23);
    }
    v13 = CTSThread::internalMsgPump(this);
    v12 = v13;
    if ( (unsigned int)dword_18005C008 > 5 )
    {
      v16 = *((_DWORD *)this + 14);
      v23 = v13;
      v25 = "Leaving thread msg loop for ID %#x. Status: 0x%x";
      v24 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)qword_180055278,
        v14,
        v15,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23);
    }
    goto LABEL_10;
  }
  memcpy_0(v29, a3, 8 * v6);
  v29[v6] = *((_QWORD *)this + 86);
  v12 = CTSThread::RunAllQueueEvents(this, 0);
  if ( v12 >= 0 )
  {
    while ( 1 )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD, int, _DWORD, _DWORD, unsigned int *))(**((_QWORD **)this + 92) + 48LL))(
              *((_QWORD *)this + 92),
              v29,
              (unsigned int)(v6 + 1),
              *((_QWORD *)this + 88),
              a4,
              0,
              0,
              a5);
      if ( v18 < 0 )
        break;
      if ( *a5 != (_DWORD)v6 )
        return 0;
      if ( (unsigned int)dword_18005C008 > 5 )
      {
        v25 = "Thread msg queued";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v19,
          (unsigned int)&byte_180055257,
          v20,
          v21,
          (__int64)&v25);
      }
      CTSThread::OnNotifyThreadEventQueue(this);
    }
    if ( v18 == -2092629812 )
    {
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        v23 = *((_DWORD *)this + 14);
        v24 = 1928;
        v25 = "internalThreadMsgLoop";
        v27 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v28[0] = "Thread: 0x%x bailing out because of defered quit";
        LODWORD(v26) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)&dword_1800551FC,
          v20,
          v21,
          (__int64)v28,
          (__int64)&v26,
          (__int64)&v27,
          (__int64)&v24,
          (__int64)&v25,
          (__int64)&v23);
      }
      *((_DWORD *)this + 45) = 1;
      *a5 = 0;
      return 0;
    }
    if ( v18 == -2092629813 )
    {
      v12 = -2092630012;
LABEL_10:
      *a5 = 0;
      return (unsigned int)v12;
    }
    v12 = -2147467259;
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      LODWORD(v26) = *((_DWORD *)this + 14);
      v28[0] = "internalThreadMsgLoop";
      v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v27 = "Thread: 0x%x bailing because of error while waiting on condition";
      v23 = 1944;
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)byte_1800551A1,
        v20,
        v21,
        (__int64)&v27,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)v28,
        (__int64)&v26);
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      95,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)"Failed to run thread events",
      v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003e040  mov     [rsp-8+arg_10], rbx
0x18003e045  push    rbp
0x18003e046  push    rsi
0x18003e047  push    rdi
0x18003e048  push    r14
0x18003e04a  push    r15
0x18003e04c  lea     rbp, [rsp-190h]
0x18003e054  sub     rsp, 290h
0x18003e05b  mov     rax, cs:__security_cookie
0x18003e062  xor     rax, rsp
0x18003e065  mov     [rbp+1B0h+var_30], rax
0x18003e06c  mov     r14, [rbp+1B0h+arg_20]
0x18003e073  mov     rbx, r8
0x18003e076  mov     esi, edx
0x18003e078  mov     rdi, rcx
0x18003e07b  xor     edx, edx; Val
0x18003e07d  lea     rcx, [rbp+1B0h+var_230]; void *
0x18003e081  mov     r8d, 200h; Size
0x18003e087  mov     r15d, r9d
0x18003e08a  call    memset_0
0x18003e08f  cmp     esi, 40h ; '@'
0x18003e092  jb      loc_18003E120
0x18003e098  mov     eax, cs:dword_18005C008
0x18003e09e  cmp     eax, 2
0x18003e0a1  jbe     short loc_18003E116
0x18003e0a3  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x18003e0aa  mov     [rsp+2B0h+var_25C], 73Eh
0x18003e0b2  mov     [rsp+2B0h+var_250], rax
0x18003e0b7  lea     rdx, word_1800552EA
0x18003e0be  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003e0c5  mov     ebx, 80004005h
0x18003e0ca  mov     [rsp+2B0h+var_248], rax
0x18003e0cf  lea     rax, aTooManyWaitObj; "Too many wait objects"
0x18003e0d6  mov     [rsp+2B0h+var_258], rax
0x18003e0db  lea     rax, [rsp+2B0h+var_250]
0x18003e0e0  mov     [rsp+2B0h+var_270], rax
0x18003e0e5  lea     rax, [rsp+2B0h+var_25C]
0x18003e0ea  mov     [rsp+2B0h+var_278], rax
0x18003e0ef  lea     rax, [rsp+2B0h+var_248]
0x18003e0f4  mov     [rsp+2B0h+var_280], rax
0x18003e0f9  lea     rax, [rsp+2B0h+var_260]
0x18003e0fe  mov     [rsp+2B0h+var_288], rax
0x18003e103  lea     rax, [rsp+2B0h+var_258]
0x18003e108  mov     [rsp+2B0h+var_290], rax
0x18003e10d  mov     [rsp+2B0h+var_260], ebx
0x18003e111  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003e116  mov     ebx, 80070057h
0x18003e11b  jmp     loc_18003E431
0x18003e120  test    esi, esi
0x18003e122  jnz     loc_18003E1C8
0x18003e128  mov     eax, cs:dword_18005C008
0x18003e12e  cmp     eax, 5
0x18003e131  jbe     short loc_18003E166
0x18003e133  mov     eax, [rdi+38h]
0x18003e136  lea     rdx, byte_1800552B3
0x18003e13d  mov     [rsp+2B0h+var_260], eax
0x18003e141  lea     rax, aEnteringThread; "Entering thread msg loop for ID %#x"
0x18003e148  mov     [rsp+2B0h+var_258], rax
0x18003e14d  lea     rax, [rsp+2B0h+var_260]
0x18003e152  mov     [rsp+2B0h+var_288], rax
0x18003e157  lea     rax, [rsp+2B0h+var_258]
0x18003e15c  mov     [rsp+2B0h+var_290], rax
0x18003e161  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003e166  mov     rcx, rdi; this
0x18003e169  call    ?internalMsgPump@CTSThread@@IEAAJXZ; CTSThread::internalMsgPump(void)
0x18003e16e  mov     ecx, cs:dword_18005C008
0x18003e174  mov     ebx, eax
0x18003e176  cmp     ecx, 5
0x18003e179  jbe     short loc_18003E1BC
0x18003e17b  mov     ecx, [rdi+38h]
0x18003e17e  lea     rdx, qword_180055278
0x18003e185  mov     [rsp+2B0h+var_260], eax
0x18003e189  lea     rax, aLeavingThreadM; "Leaving thread msg loop for ID %#x. Sta"...
0x18003e190  mov     [rsp+2B0h+var_258], rax
0x18003e195  lea     rax, [rsp+2B0h+var_260]
0x18003e19a  mov     [rsp+2B0h+var_280], rax
0x18003e19f  lea     rax, [rsp+2B0h+var_25C]
0x18003e1a4  mov     [rsp+2B0h+var_288], rax
0x18003e1a9  lea     rax, [rsp+2B0h+var_258]
0x18003e1ae  mov     [rsp+2B0h+var_290], rax
0x18003e1b3  mov     [rsp+2B0h+var_25C], ecx
0x18003e1b7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003e1bc  mov     dword ptr [r14], 0
0x18003e1c3  jmp     loc_18003E431
0x18003e1c8  mov     r8, rsi
0x18003e1cb  lea     rcx, [rbp+1B0h+var_230]; void *
0x18003e1cf  shl     r8, 3; Size
0x18003e1d3  mov     rdx, rbx; Src
0x18003e1d6  call    memcpy_0
0x18003e1db  mov     rax, [rdi+2B0h]
0x18003e1e2  xor     edx, edx; struct ITSEventFilter *
0x18003e1e4  mov     rcx, rdi; this
0x18003e1e7  mov     [rbp+rsi*8+1B0h+var_230], rax
0x18003e1ec  call    ?RunAllQueueEvents@CTSThread@@MEAAJPEAVITSEventFilter@@@Z; CTSThread::RunAllQueueEvents(ITSEventFilter *)
0x18003e1f1  mov     ebx, eax
0x18003e1f3  test    eax, eax
0x18003e1f5  jns     short loc_18003E25B
0x18003e1f7  mov     rax, cs:WPP_GLOBAL_Control
0x18003e1fe  lea     rcx, WPP_GLOBAL_Control
0x18003e205  cmp     rax, rcx
0x18003e208  jz      loc_18003E431
0x18003e20e  test    byte ptr [rax+1Ch], 8
0x18003e212  jz      loc_18003E431
0x18003e218  cmp     byte ptr [rax+19h], 2
0x18003e21c  jb      loc_18003E431
0x18003e222  call    RdpX_GetActivityIdPrefix
0x18003e227  lea     rcx, aFailedToRunThr; "Failed to run thread events"
0x18003e22e  mov     dword ptr [rsp+2B0h+var_288], ebx
0x18003e232  mov     [rsp+2B0h+var_290], rcx
0x18003e237  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18003e23e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e245  mov     edx, 5Fh ; '_'
0x18003e24a  mov     r9d, eax
0x18003e24d  mov     rcx, [rcx+10h]
0x18003e251  call    WPP_SF_DsD
0x18003e256  jmp     loc_18003E431
0x18003e25b  mov     rcx, [rdi+2E0h]
0x18003e262  lea     r8d, [rsi+1]
0x18003e266  mov     r9, [rdi+2C0h]
0x18003e26d  lea     rdx, [rbp+1B0h+var_230]
0x18003e271  mov     [rsp+2B0h+var_278], r14
0x18003e276  mov     dword ptr [rsp+2B0h+var_280], 0
0x18003e27e  mov     rax, [rcx]
0x18003e281  mov     dword ptr [rsp+2B0h+var_288], 0
0x18003e289  mov     dword ptr [rsp+2B0h+var_290], r15d
0x18003e28e  mov     rax, [rax+30h]
0x18003e292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e297  test    eax, eax
0x18003e299  js      short loc_18003E2DB
0x18003e29b  cmp     [r14], esi
0x18003e29e  jnz     loc_18003E38A
0x18003e2a4  mov     eax, cs:dword_18005C008
0x18003e2aa  cmp     eax, 5
0x18003e2ad  jbe     short loc_18003E2D1
0x18003e2af  lea     rax, aThreadMsgQueue; "Thread msg queued"
0x18003e2b6  mov     [rsp+2B0h+var_258], rax
0x18003e2bb  lea     rdx, byte_180055257
0x18003e2c2  lea     rax, [rsp+2B0h+var_258]
0x18003e2c7  mov     [rsp+2B0h+var_290], rax
0x18003e2cc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003e2d1  mov     rcx, rdi; this
0x18003e2d4  call    ?OnNotifyThreadEventQueue@CTSThread@@UEAAJXZ; CTSThread::OnNotifyThreadEventQueue(void)
0x18003e2d9  jmp     short loc_18003E25B
0x18003e2db  cmp     eax, 834500CCh
0x18003e2e0  jnz     loc_18003E391
0x18003e2e6  mov     eax, cs:dword_18005C008
0x18003e2ec  cmp     eax, 2
0x18003e2ef  jbe     loc_18003E379
0x18003e2f5  mov     eax, [rdi+38h]
0x18003e2f8  lea     rdx, dword_1800551FC
0x18003e2ff  mov     [rsp+2B0h+var_260], eax
0x18003e303  mov     ebx, 80004005h
0x18003e308  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x18003e30f  mov     [rsp+2B0h+var_25C], 788h
0x18003e317  mov     [rsp+2B0h+var_258], rax
0x18003e31c  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003e323  mov     [rsp+2B0h+var_248], rax
0x18003e328  lea     rax, aThread0xXBaili; "Thread: 0x%x bailing out because of def"...
0x18003e32f  mov     [rsp+2B0h+var_240], rax
0x18003e334  lea     rax, [rsp+2B0h+var_260]
0x18003e339  mov     [rsp+2B0h+var_268], rax
0x18003e33e  lea     rax, [rsp+2B0h+var_258]
0x18003e343  mov     [rsp+2B0h+var_270], rax
0x18003e348  lea     rax, [rsp+2B0h+var_25C]
0x18003e34d  mov     [rsp+2B0h+var_278], rax
0x18003e352  lea     rax, [rsp+2B0h+var_248]
0x18003e357  mov     [rsp+2B0h+var_280], rax
0x18003e35c  lea     rax, [rsp+2B0h+var_250]
0x18003e361  mov     [rsp+2B0h+var_288], rax
0x18003e366  lea     rax, [rsp+2B0h+var_240]
0x18003e36b  mov     [rsp+2B0h+var_290], rax
0x18003e370  mov     dword ptr [rsp+2B0h+var_250], ebx
0x18003e374  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003e379  mov     dword ptr [rdi+0B4h], 1
0x18003e383  mov     dword ptr [r14], 0
0x18003e38a  xor     ebx, ebx
0x18003e38c  jmp     loc_18003E431
0x18003e391  cmp     eax, 834500CBh
0x18003e396  jnz     short loc_18003E3A2
0x18003e398  mov     ebx, 83450004h
0x18003e39d  jmp     loc_18003E1BC
0x18003e3a2  mov     eax, cs:dword_18005C008
0x18003e3a8  mov     ebx, 80004005h
0x18003e3ad  cmp     eax, 2
0x18003e3b0  jbe     short loc_18003E431
0x18003e3b2  mov     eax, [rdi+38h]
0x18003e3b5  lea     rdx, byte_1800551A1
0x18003e3bc  mov     dword ptr [rsp+2B0h+var_250], eax
0x18003e3c0  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x18003e3c7  mov     [rsp+2B0h+var_240], rax
0x18003e3cc  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003e3d3  mov     [rsp+2B0h+var_258], rax
0x18003e3d8  lea     rax, aThread0xXBaili_0; "Thread: 0x%x bailing because of error w"...
0x18003e3df  mov     [rsp+2B0h+var_248], rax
0x18003e3e4  lea     rax, [rsp+2B0h+var_250]
0x18003e3e9  mov     [rsp+2B0h+var_268], rax
0x18003e3ee  lea     rax, [rsp+2B0h+var_240]
0x18003e3f3  mov     [rsp+2B0h+var_270], rax
0x18003e3f8  lea     rax, [rsp+2B0h+var_260]
0x18003e3fd  mov     [rsp+2B0h+var_278], rax
0x18003e402  lea     rax, [rsp+2B0h+var_258]
0x18003e407  mov     [rsp+2B0h+var_280], rax
0x18003e40c  lea     rax, [rsp+2B0h+var_25C]
0x18003e411  mov     [rsp+2B0h+var_288], rax
0x18003e416  lea     rax, [rsp+2B0h+var_248]
0x18003e41b  mov     [rsp+2B0h+var_290], rax
0x18003e420  mov     [rsp+2B0h+var_260], 798h
0x18003e428  mov     [rsp+2B0h+var_25C], ebx
0x18003e42c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003e431  mov     eax, ebx
0x18003e433  mov     rcx, [rbp+1B0h+var_30]
0x18003e43a  xor     rcx, rsp; StackCookie
0x18003e43d  call    __security_check_cookie
0x18003e442  mov     rbx, [rsp+2B0h+arg_10]
0x18003e44a  add     rsp, 290h
0x18003e451  pop     r15
0x18003e453  pop     r14
0x18003e455  pop     rdi
0x18003e456  pop     rsi
0x18003e457  pop     rbp
0x18003e458  retn
```
