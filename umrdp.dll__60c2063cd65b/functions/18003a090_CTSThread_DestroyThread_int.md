# CTSThread::DestroyThread(int)

- ea: `0x18003a090`
- end: `0x18003a4d4`
- name: `?DestroyThread@CTSThread@@UEAAJH@Z`
- size: `1092`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x1800011c8`
- `0x1800012ec`
- `0x1800014c0`
- `0x18000f75c`
- `0x18000f79c`
- `0x18001b7c0`
- `0x18001b7ec`
- `0x18001bae0`
- `0x18003a090`
- `0x18003b880`
- `0x18003b9e4`
- `0x18003e718`
- `0x180049010`

## string_xrefs

- `0x18003a1fd`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003a306`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003a0d2`: `Thread initialized but not running. Bail destroy`
- `0x18003a126`: `Destroying Bound Thread`
- `0x18003a1f2`: `DestroyThread`
- `0x18003a2f8`: `DestroyThread`
- `0x18003a208`: `Trying to end thread ID %#x`
- `0x18003a28e`: `Attempt to stop thread %#x`
- `0x18003a311`: `Failed to end thread ID %#x, HR = 0x%x`
- `0x18003a498`: `Thread id %#x exited.`

## pseudocode

```c
__int64 __fastcall CTSThread::DestroyThread(CTSThread *this)
{
  CTSReaderWriterLock *v2; // rsi
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  int v6; // eax
  unsigned int v7; // edi
  int v8; // edi
  unsigned int ActivityIdPrefix; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // eax
  int v17; // ecx
  __int64 v18; // r8
  int v19; // r9d
  __int64 v20; // rcx
  __int64 v21; // rdx
  const char *v23; // [rsp+60h] [rbp+7h] BYREF
  int v24; // [rsp+68h] [rbp+Fh]
  const char *v25; // [rsp+70h] [rbp+17h] BYREF
  const char *v26; // [rsp+78h] [rbp+1Fh] BYREF
  const char *v27; // [rsp+80h] [rbp+27h] BYREF
  const char *v28; // [rsp+C0h] [rbp+67h] BYREF
  const char *v29; // [rsp+D0h] [rbp+77h] BYREF
  int v30; // [rsp+D8h] [rbp+7Fh] BYREF

  v24 = 0;
  v2 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  v6 = *((_DWORD *)this + 20);
  if ( v6 == 1 )
  {
    if ( (unsigned int)dword_18005C008 > 4 )
    {
      v28 = "Thread initialized but not running. Bail destroy";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (unsigned int)&dword_180055864,
        v4,
        v5,
        (__int64)&v28);
    }
    *((_DWORD *)this + 20) = 7;
LABEL_5:
    v7 = 0;
LABEL_22:
    CTSReaderWriterLock::WriteUnlock(v2);
    return v7;
  }
  if ( *((_DWORD *)this + 46) && (v6 == 6 || v6 == 3) )
  {
    if ( (unsigned int)dword_18005C008 > 4 )
    {
      v28 = "Destroying Bound Thread";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (unsigned int)byte_180055843,
        v4,
        v5,
        (__int64)&v28);
    }
    *((_DWORD *)this + 20) = 4;
    v8 = CTSThread::InternalRundownThread(this);
    if ( v8 < 0
      && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        33,
        &WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        ActivityIdPrefix,
        v8);
    }
    CTSThread::InternalFreeThreadHandle(this);
    goto LABEL_5;
  }
  if ( v6 == 5 )
  {
    CTSReaderWriterLock::WriteUnlock(v2);
    CTSThread::InternalFreeThreadHandle(this);
    return 0;
  }
  if ( !*((_DWORD *)this + 14) )
  {
    v7 = -2147467259;
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      LODWORD(v28) = *((_DWORD *)this + 14);
      v23 = "DestroyThread";
      v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v26 = "Trying to end thread ID %#x";
      LODWORD(v29) = 529;
      v30 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v3,
        (unsigned int)qword_1800557E8,
        v4,
        v5,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)&v25,
        (__int64)&v29,
        (__int64)&v23,
        (__int64)&v28);
    }
    goto LABEL_22;
  }
  *((_DWORD *)this + 20) = 4;
  CTSReaderWriterLock::WriteUnlock(v2);
  if ( (unsigned int)dword_18005C008 > 4 )
  {
    LODWORD(v28) = *((_DWORD *)this + 14);
    v29 = "Attempt to stop thread %#x";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)byte_1800557B1,
      v11,
      v12,
      (__int64)&v29,
      (__int64)&v28);
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 92) + 56LL))(
          *((_QWORD *)this + 92),
          *((unsigned int *)this + 14),
          *((_QWORD *)this + 88));
  if ( v13 < 0 && (unsigned int)dword_18005C008 > 2 )
  {
    LODWORD(v29) = *((_DWORD *)this + 14);
    LODWORD(v28) = v13;
    v26 = "DestroyThread";
    v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    v27 = "Failed to end thread ID %#x, HR = 0x%x";
    v30 = 548;
    LODWORD(v23) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)word_180055752,
      v14,
      v15,
      (__int64)&v27,
      (__int64)&v23,
      (__int64)&v25,
      (__int64)&v30,
      (__int64)&v26,
      (__int64)&v29,
      (__int64)&v28);
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64))(**((_QWORD **)this + 92) + 48LL))(
          *((_QWORD *)this + 92),
          (char *)this + 64,
          1);
  v7 = v16;
  if ( v16 == -2092629812 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) )
    {
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        34,
        &WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        *((unsigned int *)this + 14));
    }
    return v7;
  }
  if ( v16 == -2092629813 )
  {
    v20 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || !*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) )
    {
      return v7;
    }
    v21 = 35;
    goto LABEL_38;
  }
  if ( v16 < 0 )
  {
    v20 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || !*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) )
    {
      return v7;
    }
    v21 = 36;
LABEL_38:
    WPP_SF_Di(*(_QWORD *)(v20 + 16), v21, v18, *((unsigned int *)this + 14), *((_QWORD *)this + 8));
    return v7;
  }
  if ( (unsigned int)dword_18005C008 > 4 )
  {
    LODWORD(v28) = *((_DWORD *)this + 14);
    v29 = "Thread id %#x exited.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)byte_18005571B,
      v18,
      v19,
      (__int64)&v29,
      (__int64)&v28);
  }
  v7 = 0;
  CTSThread::InternalFreeThreadHandle(this);
  return v7;
}

```

## disassembly

```asm
0x18003a090  push    rbp
0x18003a092  push    rbx
0x18003a093  push    rsi
0x18003a094  push    rdi
0x18003a095  push    r14
0x18003a097  lea     rbp, [rsp-37h]
0x18003a09c  sub     rsp, 90h
0x18003a0a3  mov     r14d, edx
0x18003a0a6  mov     [rbp+57h+var_48], 0
0x18003a0ad  mov     rbx, rcx
0x18003a0b0  lea     rsi, [rcx+94h]
0x18003a0b7  mov     rcx, rsi; this
0x18003a0ba  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x18003a0bf  mov     eax, [rbx+50h]
0x18003a0c2  cmp     eax, 1
0x18003a0c5  jnz     short loc_18003A100
0x18003a0c7  mov     eax, cs:dword_18005C008
0x18003a0cd  cmp     eax, 4
0x18003a0d0  jbe     short loc_18003A0F2
0x18003a0d2  lea     rax, aThreadInitiali; "Thread initialized but not running. Bai"...
0x18003a0d9  mov     [rbp+57h+arg_0], rax
0x18003a0dd  lea     rdx, dword_180055864
0x18003a0e4  lea     rax, [rbp+57h+arg_0]
0x18003a0e8  mov     [rsp+0B0h+var_90], rax
0x18003a0ed  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003a0f2  mov     dword ptr [rbx+50h], 7
0x18003a0f9  xor     edi, edi
0x18003a0fb  jmp     loc_18003A258
0x18003a100  cmp     dword ptr [rbx+0B8h], 0
0x18003a107  jz      loc_18003A1AF
0x18003a10d  cmp     eax, 6
0x18003a110  jz      short loc_18003A11B
0x18003a112  cmp     eax, 3
0x18003a115  jnz     loc_18003A1AF
0x18003a11b  mov     eax, cs:dword_18005C008
0x18003a121  cmp     eax, 4
0x18003a124  jbe     short loc_18003A146
0x18003a126  lea     rax, aDestroyingBoun; "Destroying Bound Thread"
0x18003a12d  mov     [rbp+57h+arg_0], rax
0x18003a131  lea     rdx, byte_180055843
0x18003a138  lea     rax, [rbp+57h+arg_0]
0x18003a13c  mov     [rsp+0B0h+var_90], rax
0x18003a141  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003a146  mov     rcx, rbx; this
0x18003a149  mov     dword ptr [rbx+50h], 4
0x18003a150  call    ?InternalRundownThread@CTSThread@@AEAAJXZ; CTSThread::InternalRundownThread(void)
0x18003a155  mov     edi, eax
0x18003a157  test    eax, eax
0x18003a159  jns     short loc_18003A1A2
0x18003a15b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a162  lea     rax, WPP_GLOBAL_Control
0x18003a169  cmp     rcx, rax
0x18003a16c  jz      short loc_18003A1A2
0x18003a16e  test    byte ptr [rcx+1Ch], 8
0x18003a172  jz      short loc_18003A1A2
0x18003a174  cmp     byte ptr [rcx+19h], 2
0x18003a178  jb      short loc_18003A1A2
0x18003a17a  call    RdpX_GetActivityIdPrefix
0x18003a17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a186  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18003a18d  mov     edx, 21h ; '!'
0x18003a192  mov     dword ptr [rsp+0B0h+var_90], edi
0x18003a196  mov     r9d, eax
0x18003a199  mov     rcx, [rcx+10h]
0x18003a19d  call    WPP_SF_Dd
0x18003a1a2  mov     rcx, rbx; this
0x18003a1a5  call    ?InternalFreeThreadHandle@CTSThread@@AEAAJXZ; CTSThread::InternalFreeThreadHandle(void)
0x18003a1aa  jmp     loc_18003A0F9
0x18003a1af  cmp     eax, 5
0x18003a1b2  jnz     short loc_18003A1CB
0x18003a1b4  mov     rcx, rsi; this
0x18003a1b7  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x18003a1bc  mov     rcx, rbx; this
0x18003a1bf  call    ?InternalFreeThreadHandle@CTSThread@@AEAAJXZ; CTSThread::InternalFreeThreadHandle(void)
0x18003a1c4  xor     edi, edi
0x18003a1c6  jmp     loc_18003A4C4
0x18003a1cb  cmp     dword ptr [rbx+38h], 0
0x18003a1cf  jnz     loc_18003A265
0x18003a1d5  mov     eax, cs:dword_18005C008
0x18003a1db  mov     edi, 80004005h
0x18003a1e0  cmp     eax, 2
0x18003a1e3  jbe     short loc_18003A258
0x18003a1e5  mov     eax, [rbx+38h]
0x18003a1e8  lea     rdx, qword_1800557E8
0x18003a1ef  mov     dword ptr [rbp+57h+arg_0], eax
0x18003a1f2  lea     rax, aDestroythread; "DestroyThread"
0x18003a1f9  mov     [rbp+57h+var_50], rax
0x18003a1fd  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003a204  mov     [rbp+57h+var_40], rax
0x18003a208  lea     rax, aTryingToEndThr; "Trying to end thread ID %#x"
0x18003a20f  mov     [rbp+57h+var_38], rax
0x18003a213  lea     rax, [rbp+57h+arg_0]
0x18003a217  mov     [rsp+0B0h+var_68], rax
0x18003a21c  lea     rax, [rbp+57h+var_50]
0x18003a220  mov     [rsp+0B0h+var_70], rax
0x18003a225  lea     rax, [rbp+57h+arg_10]
0x18003a229  mov     [rsp+0B0h+var_78], rax
0x18003a22e  lea     rax, [rbp+57h+var_40]
0x18003a232  mov     [rsp+0B0h+var_80], rax
0x18003a237  lea     rax, [rbp+57h+arg_18]
0x18003a23b  mov     [rsp+0B0h+var_88], rax
0x18003a240  lea     rax, [rbp+57h+var_38]
0x18003a244  mov     [rsp+0B0h+var_90], rax
0x18003a249  mov     dword ptr [rbp+57h+arg_10], 211h
0x18003a250  mov     [rbp+57h+arg_18], edi
0x18003a253  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003a258  mov     rcx, rsi; this
0x18003a25b  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x18003a260  jmp     loc_18003A4C4
0x18003a265  mov     rcx, rsi; this
0x18003a268  mov     dword ptr [rbx+50h], 4
0x18003a26f  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x18003a274  mov     r11d, cs:dword_18005C008
0x18003a27b  cmp     r11d, 4
0x18003a27f  jbe     short loc_18003A2B0
0x18003a281  mov     eax, [rbx+38h]
0x18003a284  lea     rdx, byte_1800557B1
0x18003a28b  mov     dword ptr [rbp+57h+arg_0], eax
0x18003a28e  lea     rax, aAttemptToStopT; "Attempt to stop thread %#x"
0x18003a295  mov     [rbp+57h+arg_10], rax
0x18003a299  lea     rax, [rbp+57h+arg_0]
0x18003a29d  mov     [rsp+0B0h+var_88], rax
0x18003a2a2  lea     rax, [rbp+57h+arg_10]
0x18003a2a6  mov     [rsp+0B0h+var_90], rax
0x18003a2ab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003a2b0  mov     rcx, [rbx+2E0h]
0x18003a2b7  mov     r8, [rbx+2C0h]
0x18003a2be  mov     edx, [rbx+38h]
0x18003a2c1  mov     rax, [rcx]
0x18003a2c4  mov     rax, [rax+38h]
0x18003a2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2cd  mov     ecx, eax
0x18003a2cf  test    eax, eax
0x18003a2d1  jns     loc_18003A36A
0x18003a2d7  mov     eax, cs:dword_18005C008
0x18003a2dd  cmp     eax, 2
0x18003a2e0  jbe     loc_18003A36A
0x18003a2e6  mov     eax, [rbx+38h]
0x18003a2e9  lea     rdx, word_180055752
0x18003a2f0  mov     dword ptr [rbp+57h+arg_10], eax
0x18003a2f3  mov     edi, 80004005h
0x18003a2f8  lea     rax, aDestroythread; "DestroyThread"
0x18003a2ff  mov     dword ptr [rbp+57h+arg_0], ecx
0x18003a302  mov     [rbp+57h+var_38], rax
0x18003a306  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003a30d  mov     [rbp+57h+var_40], rax
0x18003a311  lea     rax, aFailedToEndThr; "Failed to end thread ID %#x, HR = 0x%x"
0x18003a318  mov     [rbp+57h+var_30], rax
0x18003a31c  lea     rax, [rbp+57h+arg_0]
0x18003a320  mov     [rsp+0B0h+var_60], rax
0x18003a325  lea     rax, [rbp+57h+arg_10]
0x18003a329  mov     [rsp+0B0h+var_68], rax
0x18003a32e  lea     rax, [rbp+57h+var_38]
0x18003a332  mov     [rsp+0B0h+var_70], rax
0x18003a337  lea     rax, [rbp+57h+arg_18]
0x18003a33b  mov     [rsp+0B0h+var_78], rax
0x18003a340  lea     rax, [rbp+57h+var_40]
0x18003a344  mov     [rsp+0B0h+var_80], rax
0x18003a349  lea     rax, [rbp+57h+var_50]
0x18003a34d  mov     [rsp+0B0h+var_88], rax
0x18003a352  lea     rax, [rbp+57h+var_30]
0x18003a356  mov     [rsp+0B0h+var_90], rax
0x18003a35b  mov     [rbp+57h+arg_18], 224h
0x18003a362  mov     dword ptr [rbp+57h+var_50], edi
0x18003a365  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003a36a  mov     rcx, [rbx+2E0h]
0x18003a371  lea     rdx, [rbx+40h]
0x18003a375  xor     r8d, r8d
0x18003a378  test    r14d, r14d
0x18003a37b  mov     rax, [rcx]
0x18003a37e  setz    r8b
0x18003a382  xor     r9d, r9d
0x18003a385  mov     r10, [rax+30h]
0x18003a389  lea     rax, [rbp+57h+var_48]
0x18003a38d  mov     [rsp+0B0h+var_78], rax
0x18003a392  mov     eax, [rbx+90h]
0x18003a398  mov     dword ptr [rsp+0B0h+var_80], r8d
0x18003a39d  lea     r8d, [r9+1]
0x18003a3a1  mov     dword ptr [rsp+0B0h+var_88], 1
0x18003a3a9  mov     dword ptr [rsp+0B0h+var_90], eax
0x18003a3ad  mov     rax, r10
0x18003a3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3b5  mov     edi, eax
0x18003a3b7  cmp     eax, 834500CCh
0x18003a3bc  jnz     short loc_18003A407
0x18003a3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3c5  lea     rax, WPP_GLOBAL_Control
0x18003a3cc  cmp     rcx, rax
0x18003a3cf  jz      loc_18003A4C4
0x18003a3d5  test    byte ptr [rcx+1Ch], 1
0x18003a3d9  jz      loc_18003A4C4
0x18003a3df  cmp     byte ptr [rcx+19h], 1
0x18003a3e3  jb      loc_18003A4C4
0x18003a3e9  mov     r9d, [rbx+38h]
0x18003a3ed  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18003a3f4  mov     rcx, [rcx+10h]
0x18003a3f8  mov     edx, 22h ; '"'
0x18003a3fd  call    WPP_SF_D
0x18003a402  jmp     loc_18003A4C4
0x18003a407  cmp     eax, 834500CBh
0x18003a40c  jnz     short loc_18003A456
0x18003a40e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a415  lea     rax, WPP_GLOBAL_Control
0x18003a41c  cmp     rcx, rax
0x18003a41f  jz      loc_18003A4C4
0x18003a425  test    byte ptr [rcx+1Ch], 1
0x18003a429  jz      loc_18003A4C4
0x18003a42f  cmp     byte ptr [rcx+19h], 1
0x18003a433  jb      loc_18003A4C4
0x18003a439  mov     edx, 23h ; '#'
0x18003a43e  mov     rax, [rbx+40h]
0x18003a442  mov     r9d, [rbx+38h]
0x18003a446  mov     rcx, [rcx+10h]
0x18003a44a  mov     [rsp+0B0h+var_90], rax
0x18003a44f  call    WPP_SF_Di
0x18003a454  jmp     short loc_18003A4C4
0x18003a456  test    eax, eax
0x18003a458  jns     short loc_18003A480
0x18003a45a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a461  lea     rax, WPP_GLOBAL_Control
0x18003a468  cmp     rcx, rax
0x18003a46b  jz      short loc_18003A4C4
0x18003a46d  test    byte ptr [rcx+1Ch], 1
0x18003a471  jz      short loc_18003A4C4
0x18003a473  cmp     byte ptr [rcx+19h], 1
0x18003a477  jb      short loc_18003A4C4
0x18003a479  mov     edx, 24h ; '$'
0x18003a47e  jmp     short loc_18003A43E
0x18003a480  mov     eax, cs:dword_18005C008
0x18003a486  cmp     eax, 4
0x18003a489  jbe     short loc_18003A4BA
0x18003a48b  mov     eax, [rbx+38h]
0x18003a48e  lea     rdx, byte_18005571B
0x18003a495  mov     dword ptr [rbp+57h+arg_0], eax
0x18003a498  lea     rax, aThreadIdXExite; "Thread id %#x exited."
0x18003a49f  mov     [rbp+57h+arg_10], rax
0x18003a4a3  lea     rax, [rbp+57h+arg_0]
0x18003a4a7  mov     [rsp+0B0h+var_88], rax
0x18003a4ac  lea     rax, [rbp+57h+arg_10]
0x18003a4b0  mov     [rsp+0B0h+var_90], rax
0x18003a4b5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003a4ba  xor     edi, edi
0x18003a4bc  mov     rcx, rbx; this
0x18003a4bf  call    ?InternalFreeThreadHandle@CTSThread@@AEAAJXZ; CTSThread::InternalFreeThreadHandle(void)
0x18003a4c4  mov     eax, edi
0x18003a4c6  add     rsp, 90h
0x18003a4cd  pop     r14
0x18003a4cf  pop     rdi
0x18003a4d0  pop     rsi
0x18003a4d1  pop     rbx
0x18003a4d2  pop     rbp
0x18003a4d3  retn
```
