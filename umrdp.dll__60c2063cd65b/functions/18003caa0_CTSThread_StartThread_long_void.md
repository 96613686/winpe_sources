# CTSThread::StartThread(long (*)(void *))

- ea: `0x18003caa0`
- end: `0x18003ce64`
- name: `?StartThread@CTSThread@@UEAAJP6AJPEAX@Z@Z`
- size: `964`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, int (*)(void *))`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x1800010b0`
- `0x1800011c8`
- `0x1800014c0`
- `0x180001738`
- `0x18001ac80`
- `0x18001b40c`
- `0x18001b7c0`
- `0x18001b7ec`
- `0x18001bae0`
- `0x18003caa0`
- `0x18003e6b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003cb89`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003cb89`

## string_xrefs

- `0x18003cb31`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003cc1e`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003cb1d`: `StartThread`
- `0x18003cc11`: `StartThread`
- `0x18003cb0b`: `Entry function does not exist can't start thread`
- `0x18003cba6`: `start sync event %p created - now create thread`
- `0x18003cc47`: `Thread exited with error code: 0x%x`
- `0x18003ccb1`: `Thread exited with success error code`
- `0x18003ccde`: `thread %d created successfully`

## pseudocode

```c
__int64 __fastcall CTSThread::StartThread(CTSThread *this, int (*a2)(void *))
{
  CTSReaderWriterLock *v4; // r13
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  unsigned int (*v9)(void *); // rcx
  char *EventW; // rdi
  int v11; // r8d
  int v12; // r9d
  unsigned int *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  int v16; // esi
  void *v17; // r12
  unsigned int ActivityIdPrefix; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // r8d
  int v22; // r9d
  const char *v24; // [rsp+50h] [rbp-29h] BYREF
  const char *v25; // [rsp+58h] [rbp-21h] BYREF
  const char *v26; // [rsp+60h] [rbp-19h] BYREF
  __int128 v27; // [rsp+68h] [rbp-11h] BYREF
  __int128 v28; // [rsp+78h] [rbp-1h]
  __int128 v29; // [rsp+88h] [rbp+Fh]
  const char *v30; // [rsp+E0h] [rbp+67h] BYREF
  void *v31; // [rsp+F0h] [rbp+77h] BYREF
  const char *v32; // [rsp+F8h] [rbp+7Fh] BYREF

  LODWORD(v30) = 0;
  v27 = 0;
  v28 = 0;
  v31 = 0;
  v29 = 0;
  v4 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  if ( *((_DWORD *)this + 20) != 1 )
    goto LABEL_28;
  if ( !*((_QWORD *)this + 11) )
  {
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      LODWORD(v30) = 703;
      v25 = "Entry function does not exist can't start thread";
      v32 = "StartThread";
      v24 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      LODWORD(v31) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&dword_180055694,
        v6,
        v7,
        (__int64)&v25,
        (__int64)&v31,
        (__int64)&v24,
        (__int64)&v30,
        (__int64)&v32);
    }
    v8 = -2147024809;
    goto LABEL_29;
  }
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
LABEL_28:
    v8 = -2147467259;
    goto LABEL_29;
  }
  if ( (unsigned int)dword_18005C008 > 4 )
  {
    v32 = EventW;
    v25 = "start sync event %p created - now create thread";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v9,
      (unsigned int)&dword_18005565C,
      v11,
      v12,
      (__int64)&v25,
      (__int64)&v32);
  }
  *((_QWORD *)&v28 + 1) = *((_QWORD *)this + 12);
  *(_QWORD *)&v27 = *((_QWORD *)this + 11);
  *(_QWORD *)&v28 = EventW;
  *(_QWORD *)&v29 = this;
  *((_QWORD *)&v27 + 1) = a2;
  DWORD2(v29) = 0;
  if ( PAL_System_ThreadAllocInit(v9, &v27, EventW, (unsigned int *)&v30, &v31) >= 0 )
  {
    v16 = (int)v30;
    if ( (unsigned int)dword_18005C008 > 4 )
    {
      v32 = "thread %d created successfully";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v13,
        (unsigned int)&byte_1800555B7,
        v14,
        v15,
        (__int64)&v32,
        (__int64)&v30);
    }
    if ( (unsigned int)dword_18005C008 > 4 )
    {
      v30 = "event signalled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v13,
        (unsigned int)&word_180055596,
        v14,
        v15,
        (__int64)&v30);
    }
    v17 = v31;
    *((_DWORD *)this + 20) = 2;
    *((_QWORD *)this + 8) = v17;
    *((_DWORD *)this + 14) = v16;
    *((_DWORD *)this + 18) = 1;
    v13 = &WPP_GLOBAL_Control;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      WPP_SF_DDi(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), v19, v20, ActivityIdPrefix, v16, v17);
    }
  }
  else if ( (SDWORD2(v29) & 0x80000000) == 0 )
  {
    if ( (unsigned int)dword_18005C008 > 4 )
    {
      v30 = "Thread exited with success error code";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v13,
        (unsigned int)word_1800555E2,
        v14,
        v15,
        (__int64)&v30);
    }
  }
  else if ( (unsigned int)dword_18005C008 > 2 )
  {
    LODWORD(v30) = DWORD2(v29);
    v26 = "Thread exited with error code: 0x%x";
    v25 = "StartThread";
    LODWORD(v31) = 746;
    v24 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    LODWORD(v32) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)byte_180055603,
      v14,
      v15,
      (__int64)&v26,
      (__int64)&v32,
      (__int64)&v24,
      (__int64)&v31,
      (__int64)&v25,
      (__int64)&v30);
  }
  if ( (unsigned int)dword_18005C008 > 4 )
  {
    v30 = "Destroy event object";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v13,
      (unsigned int)byte_180055575,
      v14,
      v15,
      (__int64)&v30);
  }
  v8 = PAL_System_HandleFree(EventW);
  if ( v8 < 0 && (unsigned int)dword_18005C008 > 2 )
  {
    v32 = "StartThread";
    v25 = "Failed to close condition handle";
    LODWORD(v30) = 778;
    v26 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    LODWORD(v31) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_18005C008,
      (unsigned int)qword_180055530,
      v21,
      v22,
      (__int64)&v25,
      (__int64)&v31,
      (__int64)&v26,
      (__int64)&v30,
      (__int64)&v32);
  }
LABEL_29:
  CTSReaderWriterLock::WriteUnlock(v4);
  if ( v8 >= 0 && SDWORD2(v29) < 0 )
    return (unsigned int)DWORD2(v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003caa0  mov     [rsp-8+arg_8], rbx
0x18003caa5  push    rbp
0x18003caa6  push    rsi
0x18003caa7  push    rdi
0x18003caa8  push    r12
0x18003caaa  push    r13
0x18003caac  push    r14
0x18003caae  push    r15
0x18003cab0  lea     rbp, [rsp-27h]
0x18003cab5  sub     rsp, 0A0h
0x18003cabc  xorps   xmm0, xmm0
0x18003cabf  mov     dword ptr [rbp+57h+arg_0], 0
0x18003cac6  movups  [rbp+57h+var_68], xmm0
0x18003caca  mov     rsi, rdx
0x18003cacd  mov     rbx, rcx
0x18003cad0  movups  [rbp+57h+var_58], xmm0
0x18003cad4  mov     [rbp+57h+arg_10], 0
0x18003cadc  movups  [rbp+57h+var_48], xmm0
0x18003cae0  lea     r13, [rcx+94h]
0x18003cae7  mov     rcx, r13; this
0x18003caea  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x18003caef  cmp     dword ptr [rbx+50h], 1
0x18003caf3  jnz     loc_18003CE2E
0x18003caf9  cmp     qword ptr [rbx+58h], 0
0x18003cafe  jnz     short loc_18003CB7D
0x18003cb00  mov     eax, cs:dword_18005C008
0x18003cb06  cmp     eax, 2
0x18003cb09  jbe     short loc_18003CB73
0x18003cb0b  lea     rax, aEntryFunctionD; "Entry function does not exist can't sta"...
0x18003cb12  mov     dword ptr [rbp+57h+arg_0], 2BFh
0x18003cb19  mov     [rbp+57h+var_78], rax
0x18003cb1d  lea     r14, aStartthread; "StartThread"
0x18003cb24  lea     rax, [rbp+57h+arg_18]
0x18003cb28  mov     [rbp+57h+arg_18], r14
0x18003cb2c  mov     [rsp+0D0h+var_90], rax
0x18003cb31  lea     r15, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003cb38  lea     rax, [rbp+57h+arg_0]
0x18003cb3c  mov     [rbp+57h+var_80], r15
0x18003cb40  mov     [rsp+0D0h+var_98], rax
0x18003cb45  lea     rdx, dword_180055694
0x18003cb4c  lea     rax, [rbp+57h+var_80]
0x18003cb50  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x18003cb57  mov     [rsp+0D0h+var_A0], rax
0x18003cb5c  lea     rax, [rbp+57h+arg_10]
0x18003cb60  mov     [rsp+0D0h+var_A8], rax
0x18003cb65  lea     rax, [rbp+57h+var_78]
0x18003cb69  mov     [rsp+0D0h+var_B0], rax
0x18003cb6e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003cb73  mov     ebx, 80070057h
0x18003cb78  jmp     loc_18003CE33
0x18003cb7d  xor     r9d, r9d; lpName
0x18003cb80  xor     r8d, r8d; bInitialState
0x18003cb83  xor     ecx, ecx; lpEventAttributes
0x18003cb85  lea     edx, [r9+1]; bManualReset
0x18003cb89  call    cs:__imp_CreateEventW
0x18003cb8f  mov     rdi, rax
0x18003cb92  test    rax, rax
0x18003cb95  jz      loc_18003CE2E
0x18003cb9b  mov     eax, cs:dword_18005C008
0x18003cba1  cmp     eax, 4
0x18003cba4  jbe     short loc_18003CBD3
0x18003cba6  lea     rax, aStartSyncEvent; "start sync event %p created - now creat"...
0x18003cbad  mov     [rbp+57h+arg_18], rdi
0x18003cbb1  mov     [rbp+57h+var_78], rax
0x18003cbb5  lea     rdx, dword_18005565C
0x18003cbbc  lea     rax, [rbp+57h+arg_18]
0x18003cbc0  mov     [rsp+0D0h+var_A8], rax
0x18003cbc5  lea     rax, [rbp+57h+var_78]
0x18003cbc9  mov     [rsp+0D0h+var_B0], rax
0x18003cbce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18003cbd3  mov     rax, [rbx+60h]
0x18003cbd7  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x18003cbdb  mov     qword ptr [rbp+57h+var_58+8], rax
0x18003cbdf  lea     rdx, [rbp+57h+var_68]; void *
0x18003cbe3  mov     rax, [rbx+58h]
0x18003cbe7  mov     r8, rdi; void *
0x18003cbea  mov     qword ptr [rbp+57h+var_68], rax
0x18003cbee  lea     rax, [rbp+57h+arg_10]
0x18003cbf2  mov     [rsp+0D0h+var_B0], rax; void **
0x18003cbf7  mov     qword ptr [rbp+57h+var_58], rdi
0x18003cbfb  mov     qword ptr [rbp+57h+var_48], rbx
0x18003cbff  mov     qword ptr [rbp+57h+var_68+8], rsi
0x18003cc03  mov     dword ptr [rbp+57h+var_48+8], 0
0x18003cc0a  call    ?PAL_System_ThreadAllocInit@@YAJP6AIPEAX@Z00PEAKPEAPEAX@Z; PAL_System_ThreadAllocInit(uint (*)(void *),void *,void *,ulong *,void * *)
0x18003cc0f  test    eax, eax
0x18003cc11  lea     r14, aStartthread; "StartThread"
0x18003cc18  mov     eax, cs:dword_18005C008
0x18003cc1e  lea     r15, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003cc25  jns     loc_18003CCD6
0x18003cc2b  cmp     dword ptr [rbp+57h+var_48+8], 0
0x18003cc2f  jge     short loc_18003CCA8
0x18003cc31  cmp     eax, 2
0x18003cc34  jbe     loc_18003CD8E
0x18003cc3a  mov     eax, dword ptr [rbp+57h+var_48+8]
0x18003cc3d  lea     rdx, byte_180055603
0x18003cc44  mov     dword ptr [rbp+57h+arg_0], eax
0x18003cc47  lea     rax, aThreadExitedWi; "Thread exited with error code: 0x%x"
0x18003cc4e  mov     [rbp+57h+var_70], rax
0x18003cc52  lea     rax, [rbp+57h+arg_0]
0x18003cc56  mov     [rsp+0D0h+var_88], rax
0x18003cc5b  lea     rax, [rbp+57h+var_78]
0x18003cc5f  mov     [rsp+0D0h+var_90], rax
0x18003cc64  lea     rax, [rbp+57h+arg_10]
0x18003cc68  mov     [rsp+0D0h+var_98], rax
0x18003cc6d  lea     rax, [rbp+57h+var_80]
0x18003cc71  mov     [rsp+0D0h+var_A0], rax
0x18003cc76  lea     rax, [rbp+57h+arg_18]
0x18003cc7a  mov     [rsp+0D0h+var_A8], rax
0x18003cc7f  lea     rax, [rbp+57h+var_70]
0x18003cc83  mov     [rsp+0D0h+var_B0], rax
0x18003cc88  mov     [rbp+57h+var_78], r14
0x18003cc8c  mov     dword ptr [rbp+57h+arg_10], 2EAh
0x18003cc93  mov     [rbp+57h+var_80], r15
0x18003cc97  mov     dword ptr [rbp+57h+arg_18], 80004005h
0x18003cc9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003cca3  jmp     loc_18003CD8E
0x18003cca8  cmp     eax, 4
0x18003ccab  jbe     loc_18003CD8E
0x18003ccb1  lea     rax, aThreadExitedWi_0; "Thread exited with success error code"
0x18003ccb8  mov     [rbp+57h+arg_0], rax
0x18003ccbc  lea     rdx, word_1800555E2
0x18003ccc3  lea     rax, [rbp+57h+arg_0]
0x18003ccc7  mov     [rsp+0D0h+var_B0], rax
0x18003cccc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003ccd1  jmp     loc_18003CD8E
0x18003ccd6  mov     esi, dword ptr [rbp+57h+arg_0]
0x18003ccd9  cmp     eax, 4
0x18003ccdc  jbe     short loc_18003CD0A
0x18003ccde  lea     rax, aThreadDCreated; "thread %d created successfully"
0x18003cce5  mov     dword ptr [rbp+57h+arg_0], esi
0x18003cce8  mov     [rbp+57h+arg_18], rax
0x18003ccec  lea     rdx, byte_1800555B7
0x18003ccf3  lea     rax, [rbp+57h+arg_0]
0x18003ccf7  mov     [rsp+0D0h+var_A8], rax
0x18003ccfc  lea     rax, [rbp+57h+arg_18]
0x18003cd00  mov     [rsp+0D0h+var_B0], rax
0x18003cd05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003cd0a  mov     eax, cs:dword_18005C008
0x18003cd10  cmp     eax, 4
0x18003cd13  jbe     short loc_18003CD35
0x18003cd15  lea     rax, aEventSignalled; "event signalled"
0x18003cd1c  mov     [rbp+57h+arg_0], rax
0x18003cd20  lea     rdx, word_180055596
0x18003cd27  lea     rax, [rbp+57h+arg_0]
0x18003cd2b  mov     [rsp+0D0h+var_B0], rax
0x18003cd30  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003cd35  mov     r12, [rbp+57h+arg_10]
0x18003cd39  mov     dword ptr [rbx+50h], 2
0x18003cd40  mov     [rbx+40h], r12
0x18003cd44  mov     [rbx+38h], esi
0x18003cd47  mov     dword ptr [rbx+48h], 1
0x18003cd4e  mov     rax, cs:WPP_GLOBAL_Control
0x18003cd55  lea     rcx, WPP_GLOBAL_Control
0x18003cd5c  cmp     rax, rcx
0x18003cd5f  jz      short loc_18003CD8E
0x18003cd61  test    byte ptr [rax+1Ch], 1
0x18003cd65  jz      short loc_18003CD8E
0x18003cd67  cmp     byte ptr [rax+19h], 3
0x18003cd6b  jb      short loc_18003CD8E
0x18003cd6d  call    RdpX_GetActivityIdPrefix
0x18003cd72  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd79  mov     r9d, eax
0x18003cd7c  mov     [rsp+0D0h+var_A8], r12
0x18003cd81  mov     dword ptr [rsp+0D0h+var_B0], esi
0x18003cd85  mov     rcx, [rcx+10h]
0x18003cd89  call    WPP_SF_DDi
0x18003cd8e  mov     eax, cs:dword_18005C008
0x18003cd94  cmp     eax, 4
0x18003cd97  jbe     short loc_18003CDB9
0x18003cd99  lea     rax, aDestroyEventOb; "Destroy event object"
0x18003cda0  mov     [rbp+57h+arg_0], rax
0x18003cda4  lea     rdx, byte_180055575
0x18003cdab  lea     rax, [rbp+57h+arg_0]
0x18003cdaf  mov     [rsp+0D0h+var_B0], rax
0x18003cdb4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003cdb9  mov     rcx, rdi
0x18003cdbc  call    PAL_System_HandleFree
0x18003cdc1  mov     ebx, eax
0x18003cdc3  test    eax, eax
0x18003cdc5  jns     short loc_18003CE33
0x18003cdc7  mov     ecx, cs:dword_18005C008
0x18003cdcd  cmp     ecx, 2
0x18003cdd0  jbe     short loc_18003CE33
0x18003cdd2  lea     rax, aFailedToCloseC; "Failed to close condition handle"
0x18003cdd9  mov     [rbp+57h+arg_18], r14
0x18003cddd  mov     [rbp+57h+var_78], rax
0x18003cde1  lea     rdx, qword_180055530
0x18003cde8  lea     rax, [rbp+57h+arg_18]
0x18003cdec  mov     dword ptr [rbp+57h+arg_0], 30Ah
0x18003cdf3  mov     [rsp+0D0h+var_90], rax
0x18003cdf8  lea     rax, [rbp+57h+arg_0]
0x18003cdfc  mov     [rsp+0D0h+var_98], rax
0x18003ce01  lea     rax, [rbp+57h+var_70]
0x18003ce05  mov     [rsp+0D0h+var_A0], rax
0x18003ce0a  lea     rax, [rbp+57h+arg_10]
0x18003ce0e  mov     [rsp+0D0h+var_A8], rax
0x18003ce13  lea     rax, [rbp+57h+var_78]
0x18003ce17  mov     [rsp+0D0h+var_B0], rax
0x18003ce1c  mov     [rbp+57h+var_70], r15
0x18003ce20  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x18003ce27  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003ce2c  jmp     short loc_18003CE33
0x18003ce2e  mov     ebx, 80004005h
0x18003ce33  mov     rcx, r13; this
0x18003ce36  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x18003ce3b  test    ebx, ebx
0x18003ce3d  js      short loc_18003CE47
0x18003ce3f  mov     eax, dword ptr [rbp+57h+var_48+8]
0x18003ce42  test    eax, eax
0x18003ce44  cmovs   ebx, eax
0x18003ce47  mov     eax, ebx
0x18003ce49  mov     rbx, [rsp+0D0h+arg_8]
0x18003ce51  add     rsp, 0A0h
0x18003ce58  pop     r15
0x18003ce5a  pop     r14
0x18003ce5c  pop     r13
0x18003ce5e  pop     r12
0x18003ce60  pop     rdi
0x18003ce61  pop     rsi
0x18003ce62  pop     rbp
0x18003ce63  retn
```
