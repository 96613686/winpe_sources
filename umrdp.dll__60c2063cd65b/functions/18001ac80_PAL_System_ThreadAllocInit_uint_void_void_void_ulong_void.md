# PAL_System_ThreadAllocInit(uint (*)(void *),void *,void *,ulong *,void * *)

- ea: `0x18001ac80`
- end: `0x18001aef5`
- name: `?PAL_System_ThreadAllocInit@@YAJP6AIPEAX@Z00PEAKPEAPEAX@Z`
- size: `629`
- prototype: `int(unsigned int (*)(void *), void *, void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003caa0`

## callees

- `0x1800010b0`
- `0x1800011c8`
- `0x18001aa68`
- `0x18001ac80`
- `0x18001aefc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001add2`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001add2`

## string_xrefs

- `0x18001acde`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001ad71`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001adef`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001accb`: `PAL_System_ThreadAllocInit`
- `0x18001ad5d`: `PAL_System_ThreadAllocInit`
- `0x18001ade8`: `PAL_System_ThreadAllocInit`
- `0x18001ad4b`: `Could not allocate thread`
- `0x18001ae0f`: `Could not free newly-created thread. Error hr=0x%08x`
- `0x18001ae89`: `Failed to wait on thread events`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadAllocInit(
        unsigned int (*a1)(void *),
        void *a2,
        void *a3,
        unsigned int *a4,
        void **a5)
{
  int v7; // ebx
  void **v8; // r14
  int v9; // r8d
  int v10; // r9d
  void *v11; // rax
  int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // eax
  const char *v18; // [rsp+50h] [rbp-30h] BYREF
  const char *v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned int (*v23)(void *); // [rsp+B0h] [rbp+30h] BYREF
  int v24; // [rsp+C0h] [rbp+40h] BYREF

  v23 = a1;
  *(_OWORD *)Handles = 0;
  if ( a3 )
  {
    v8 = a5;
    v7 = PAL_System_ThreadAlloc(a1, a2, a4, a5);
    if ( v7 >= 0 )
    {
      v11 = *v8;
      Handles[0] = a3;
      Handles[1] = v11;
      if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
      {
        v12 = PAL_System_ThreadFree(*v8);
        if ( v12 < 0 )
        {
          v13 = dword_18005C008;
          if ( (unsigned int)dword_18005C008 > 2 )
          {
            LODWORD(v23) = v12;
            v20 = "PAL_System_ThreadAllocInit";
            v21 = "Could not free newly-created thread. Error hr=0x%08x";
            v24 = 1209;
            v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
            LODWORD(v18) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              dword_18005C008,
              (unsigned int)byte_180054381,
              v14,
              v15,
              (__int64)&v21,
              (__int64)&v18,
              (__int64)&v19,
              (__int64)&v24,
              (__int64)&v20,
              (__int64)&v23);
          }
        }
        v16 = dword_18005C008;
        v7 = -2147467259;
        *a4 = 0;
        *v8 = 0;
        if ( v16 > 2 )
        {
          v21 = "PAL_System_ThreadAllocInit";
          v19 = "Failed to wait on thread events";
          LODWORD(v23) = 1217;
          v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
          v24 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v13,
            (unsigned int)qword_180054458,
            v14,
            v15,
            (__int64)&v19,
            (__int64)&v24,
            (__int64)&v20,
            (__int64)&v23,
            (__int64)&v21);
        }
      }
      else
      {
        return 0;
      }
    }
    else if ( (unsigned int)dword_18005C008 > 2 )
    {
      LODWORD(v23) = 1181;
      v18 = "Could not allocate thread";
      v20 = "PAL_System_ThreadAllocInit";
      v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_18005C008,
        (unsigned int)byte_180054413,
        v9,
        v10,
        (__int64)&v18,
        (__int64)&v24,
        (__int64)&v19,
        (__int64)&v23,
        (__int64)&v20);
    }
  }
  else
  {
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      LODWORD(v23) = 1171;
      v20 = "NULL parameter passed";
      v18 = "PAL_System_ThreadAllocInit";
      v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)&word_1800543CE,
        0,
        (_DWORD)a4,
        (__int64)&v20,
        (__int64)&v24,
        (__int64)&v19,
        (__int64)&v23,
        (__int64)&v18);
    }
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ac80  mov     r11, rsp
0x18001ac83  mov     [r11+10h], rbx
0x18001ac87  mov     [r11+8], rcx
0x18001ac8b  push    rbp
0x18001ac8c  push    rsi
0x18001ac8d  push    rdi
0x18001ac8e  push    r14
0x18001ac90  push    r15
0x18001ac92  mov     rbp, rsp
0x18001ac95  sub     rsp, 80h
0x18001ac9c  xorps   xmm0, xmm0
0x18001ac9f  mov     r15, r9
0x18001aca2  mov     rdi, r8
0x18001aca5  movups  xmmword ptr [rbp+Handles], xmm0
0x18001aca9  test    r8, r8
0x18001acac  jnz     short loc_18001AD27
0x18001acae  mov     eax, cs:dword_18005C008
0x18001acb4  cmp     eax, 2
0x18001acb7  jbe     short loc_18001AD1D
0x18001acb9  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001acc0  mov     dword ptr [rbp+arg_0], 493h
0x18001acc7  mov     [rbp+var_20], rax
0x18001accb  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x18001acd2  lea     rax, [rbp+var_30]
0x18001acd6  mov     [rbp+var_30], rdi
0x18001acda  mov     [r11-68h], rax
0x18001acde  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ace5  lea     rax, [rbp+arg_0]
0x18001ace9  mov     [rbp+var_28], rsi
0x18001aced  mov     [r11-70h], rax
0x18001acf1  lea     rdx, word_1800543CE
0x18001acf8  lea     rax, [rbp+var_28]
0x18001acfc  mov     [rbp+arg_10], 80004005h
0x18001ad03  mov     [r11-78h], rax
0x18001ad07  lea     rax, [rbp+arg_10]
0x18001ad0b  mov     [r11-80h], rax
0x18001ad0f  lea     rax, [rbp+var_20]
0x18001ad13  mov     [rsp+80h+var_60], rax
0x18001ad18  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ad1d  mov     ebx, 80070057h
0x18001ad22  jmp     loc_18001AEDC
0x18001ad27  mov     r14, [rbp+arg_20]
0x18001ad2b  mov     r8, r15; unsigned int *
0x18001ad2e  mov     r9, r14; void **
0x18001ad31  call    ?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z; PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)
0x18001ad36  mov     ebx, eax
0x18001ad38  test    eax, eax
0x18001ad3a  jns     short loc_18001ADB8
0x18001ad3c  mov     ecx, cs:dword_18005C008
0x18001ad42  cmp     ecx, 2
0x18001ad45  jbe     loc_18001AEDC
0x18001ad4b  lea     rax, aCouldNotAlloca; "Could not allocate thread"
0x18001ad52  mov     dword ptr [rbp+arg_0], 49Dh
0x18001ad59  mov     [rbp+var_30], rax
0x18001ad5d  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x18001ad64  lea     rax, [rbp+var_20]
0x18001ad68  mov     [rbp+var_20], rdi
0x18001ad6c  mov     [rsp+80h+var_40], rax
0x18001ad71  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ad78  lea     rax, [rbp+arg_0]
0x18001ad7c  mov     [rbp+var_28], rsi
0x18001ad80  mov     [rsp+80h+var_48], rax
0x18001ad85  lea     rdx, byte_180054413
0x18001ad8c  lea     rax, [rbp+var_28]
0x18001ad90  mov     [rbp+arg_10], 80004005h
0x18001ad97  mov     [rsp+80h+var_50], rax
0x18001ad9c  lea     rax, [rbp+arg_10]
0x18001ada0  mov     [rsp+80h+var_58], rax
0x18001ada5  lea     rax, [rbp+var_30]
0x18001ada9  mov     [rsp+80h+var_60], rax
0x18001adae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001adb3  jmp     loc_18001AEDC
0x18001adb8  mov     rax, [r14]
0x18001adbb  lea     rdx, [rbp+Handles]; lpHandles
0x18001adbf  xor     r8d, r8d; bWaitAll
0x18001adc2  mov     [rbp+Handles], rdi
0x18001adc6  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001adca  mov     [rbp+Handles+8], rax
0x18001adce  lea     ecx, [r8+2]; nCount
0x18001add2  call    cs:__imp_WaitForMultipleObjects
0x18001add8  test    eax, eax
0x18001adda  jz      loc_18001AEDA
0x18001ade0  mov     rcx, [r14]; void *
0x18001ade3  call    ?PAL_System_ThreadFree@@YAJPEAX@Z; PAL_System_ThreadFree(void *)
0x18001ade8  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x18001adef  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001adf6  test    eax, eax
0x18001adf8  jns     short loc_18001AE6B
0x18001adfa  mov     ecx, cs:dword_18005C008
0x18001ae00  cmp     ecx, 2
0x18001ae03  jbe     short loc_18001AE6B
0x18001ae05  mov     dword ptr [rbp+arg_0], eax
0x18001ae08  lea     rdx, byte_180054381
0x18001ae0f  lea     rax, aCouldNotFreeNe; "Could not free newly-created thread. Er"...
0x18001ae16  mov     [rbp+var_20], rdi
0x18001ae1a  mov     [rbp+var_18], rax
0x18001ae1e  lea     rax, [rbp+arg_0]
0x18001ae22  mov     [rsp+80h+var_38], rax
0x18001ae27  lea     rax, [rbp+var_20]
0x18001ae2b  mov     [rsp+80h+var_40], rax
0x18001ae30  lea     rax, [rbp+arg_10]
0x18001ae34  mov     [rsp+80h+var_48], rax
0x18001ae39  lea     rax, [rbp+var_28]
0x18001ae3d  mov     [rsp+80h+var_50], rax
0x18001ae42  lea     rax, [rbp+var_30]
0x18001ae46  mov     [rsp+80h+var_58], rax
0x18001ae4b  lea     rax, [rbp+var_18]
0x18001ae4f  mov     [rsp+80h+var_60], rax
0x18001ae54  mov     [rbp+arg_10], 4B9h
0x18001ae5b  mov     [rbp+var_28], rsi
0x18001ae5f  mov     dword ptr [rbp+var_30], 80004005h
0x18001ae66  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001ae6b  mov     eax, cs:dword_18005C008
0x18001ae71  mov     ebx, 80004005h
0x18001ae76  mov     dword ptr [r15], 0
0x18001ae7d  mov     qword ptr [r14], 0
0x18001ae84  cmp     eax, 2
0x18001ae87  jbe     short loc_18001AEDC
0x18001ae89  lea     rax, aFailedToWaitOn; "Failed to wait on thread events"
0x18001ae90  mov     [rbp+var_18], rdi
0x18001ae94  mov     [rbp+var_28], rax
0x18001ae98  lea     rdx, qword_180054458
0x18001ae9f  lea     rax, [rbp+var_18]
0x18001aea3  mov     dword ptr [rbp+arg_0], 4C1h
0x18001aeaa  mov     [rsp+80h+var_40], rax
0x18001aeaf  lea     rax, [rbp+arg_0]
0x18001aeb3  mov     [rsp+80h+var_48], rax
0x18001aeb8  lea     rax, [rbp+var_20]
0x18001aebc  mov     [rsp+80h+var_50], rax
0x18001aec1  lea     rax, [rbp+arg_10]
0x18001aec5  mov     [rsp+80h+var_58], rax
0x18001aeca  lea     rax, [rbp+var_28]
0x18001aece  mov     [rbp+var_20], rsi
0x18001aed2  mov     [rbp+arg_10], ebx
0x18001aed5  jmp     loc_18001ADA9
0x18001aeda  xor     ebx, ebx
0x18001aedc  mov     eax, ebx
0x18001aede  mov     rbx, [rsp+80h+arg_8]
0x18001aee6  add     rsp, 80h
0x18001aeed  pop     r15
0x18001aeef  pop     r14
0x18001aef1  pop     rdi
0x18001aef2  pop     rsi
0x18001aef3  pop     rbp
0x18001aef4  retn
```
