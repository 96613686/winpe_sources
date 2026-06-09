# PAL_System_ThreadAllocInit(uint (*)(void *),void *,void *,ulong *,void * *)

- ea: `0x18001bd9c`
- end: `0x18001c011`
- name: `?PAL_System_ThreadAllocInit@@YAJP6AIPEAX@Z00PEAKPEAPEAX@Z`
- size: `629`
- prototype: `int(unsigned int (*)(void *), void *, void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016300`

## callees

- `0x180001180`
- `0x1800013f4`
- `0x18001bb84`
- `0x18001bd9c`
- `0x18001c018`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001beee`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001beee`

## string_xrefs

- `0x18001bdfa`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001be8d`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001bf0b`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001bde7`: `PAL_System_ThreadAllocInit`
- `0x18001be79`: `PAL_System_ThreadAllocInit`
- `0x18001bf04`: `PAL_System_ThreadAllocInit`
- `0x18001be67`: `Could not allocate thread`
- `0x18001bf2b`: `Could not free newly-created thread. Error hr=0x%08x`
- `0x18001bfa5`: `Failed to wait on thread events`

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
          v13 = dword_1800EB958;
          if ( (unsigned int)dword_1800EB958 > 2 )
          {
            LODWORD(v23) = v12;
            v20 = "PAL_System_ThreadAllocInit";
            v21 = "Could not free newly-created thread. Error hr=0x%08x";
            v24 = 1209;
            v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
            LODWORD(v18) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              dword_1800EB958,
              (unsigned int)byte_1800CD67D,
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
        v16 = dword_1800EB958;
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
            (unsigned int)&dword_1800CD754,
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
    else if ( (unsigned int)dword_1800EB958 > 2 )
    {
      LODWORD(v23) = 1181;
      v18 = "Could not allocate thread";
      v20 = "PAL_System_ThreadAllocInit";
      v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1800EB958,
        (unsigned int)&byte_1800CD70F,
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
    if ( (unsigned int)dword_1800EB958 > 2 )
    {
      LODWORD(v23) = 1171;
      v20 = "NULL parameter passed";
      v18 = "PAL_System_ThreadAllocInit";
      v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)word_1800CD6CA,
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
0x18001bd9c  mov     r11, rsp
0x18001bd9f  mov     [r11+10h], rbx
0x18001bda3  mov     [r11+8], rcx
0x18001bda7  push    rbp
0x18001bda8  push    rsi
0x18001bda9  push    rdi
0x18001bdaa  push    r14
0x18001bdac  push    r15
0x18001bdae  mov     rbp, rsp
0x18001bdb1  sub     rsp, 80h
0x18001bdb8  xorps   xmm0, xmm0
0x18001bdbb  mov     r15, r9
0x18001bdbe  mov     rdi, r8
0x18001bdc1  movups  xmmword ptr [rbp+Handles], xmm0
0x18001bdc5  test    r8, r8
0x18001bdc8  jnz     short loc_18001BE43
0x18001bdca  mov     eax, cs:dword_1800EB958
0x18001bdd0  cmp     eax, 2
0x18001bdd3  jbe     short loc_18001BE39
0x18001bdd5  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001bddc  mov     dword ptr [rbp+arg_0], 493h
0x18001bde3  mov     [rbp+var_20], rax
0x18001bde7  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x18001bdee  lea     rax, [rbp+var_30]
0x18001bdf2  mov     [rbp+var_30], rdi
0x18001bdf6  mov     [r11-68h], rax
0x18001bdfa  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001be01  lea     rax, [rbp+arg_0]
0x18001be05  mov     [rbp+var_28], rsi
0x18001be09  mov     [r11-70h], rax
0x18001be0d  lea     rdx, word_1800CD6CA
0x18001be14  lea     rax, [rbp+var_28]
0x18001be18  mov     [rbp+arg_10], 80004005h
0x18001be1f  mov     [r11-78h], rax
0x18001be23  lea     rax, [rbp+arg_10]
0x18001be27  mov     [r11-80h], rax
0x18001be2b  lea     rax, [rbp+var_20]
0x18001be2f  mov     [rsp+80h+var_60], rax
0x18001be34  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001be39  mov     ebx, 80070057h
0x18001be3e  jmp     loc_18001BFF8
0x18001be43  mov     r14, [rbp+arg_20]
0x18001be47  mov     r8, r15; unsigned int *
0x18001be4a  mov     r9, r14; void **
0x18001be4d  call    ?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z; PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)
0x18001be52  mov     ebx, eax
0x18001be54  test    eax, eax
0x18001be56  jns     short loc_18001BED4
0x18001be58  mov     ecx, cs:dword_1800EB958
0x18001be5e  cmp     ecx, 2
0x18001be61  jbe     loc_18001BFF8
0x18001be67  lea     rax, aCouldNotAlloca_1; "Could not allocate thread"
0x18001be6e  mov     dword ptr [rbp+arg_0], 49Dh
0x18001be75  mov     [rbp+var_30], rax
0x18001be79  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x18001be80  lea     rax, [rbp+var_20]
0x18001be84  mov     [rbp+var_20], rdi
0x18001be88  mov     [rsp+80h+var_40], rax
0x18001be8d  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001be94  lea     rax, [rbp+arg_0]
0x18001be98  mov     [rbp+var_28], rsi
0x18001be9c  mov     [rsp+80h+var_48], rax
0x18001bea1  lea     rdx, byte_1800CD70F
0x18001bea8  lea     rax, [rbp+var_28]
0x18001beac  mov     [rbp+arg_10], 80004005h
0x18001beb3  mov     [rsp+80h+var_50], rax
0x18001beb8  lea     rax, [rbp+arg_10]
0x18001bebc  mov     [rsp+80h+var_58], rax
0x18001bec1  lea     rax, [rbp+var_30]
0x18001bec5  mov     [rsp+80h+var_60], rax
0x18001beca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001becf  jmp     loc_18001BFF8
0x18001bed4  mov     rax, [r14]
0x18001bed7  lea     rdx, [rbp+Handles]; lpHandles
0x18001bedb  xor     r8d, r8d; bWaitAll
0x18001bede  mov     [rbp+Handles], rdi
0x18001bee2  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001bee6  mov     [rbp+Handles+8], rax
0x18001beea  lea     ecx, [r8+2]; nCount
0x18001beee  call    cs:__imp_WaitForMultipleObjects
0x18001bef4  test    eax, eax
0x18001bef6  jz      loc_18001BFF6
0x18001befc  mov     rcx, [r14]; void *
0x18001beff  call    ?PAL_System_ThreadFree@@YAJPEAX@Z; PAL_System_ThreadFree(void *)
0x18001bf04  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x18001bf0b  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001bf12  test    eax, eax
0x18001bf14  jns     short loc_18001BF87
0x18001bf16  mov     ecx, cs:dword_1800EB958
0x18001bf1c  cmp     ecx, 2
0x18001bf1f  jbe     short loc_18001BF87
0x18001bf21  mov     dword ptr [rbp+arg_0], eax
0x18001bf24  lea     rdx, byte_1800CD67D
0x18001bf2b  lea     rax, aCouldNotFreeNe; "Could not free newly-created thread. Er"...
0x18001bf32  mov     [rbp+var_20], rdi
0x18001bf36  mov     [rbp+var_18], rax
0x18001bf3a  lea     rax, [rbp+arg_0]
0x18001bf3e  mov     [rsp+80h+var_38], rax
0x18001bf43  lea     rax, [rbp+var_20]
0x18001bf47  mov     [rsp+80h+var_40], rax
0x18001bf4c  lea     rax, [rbp+arg_10]
0x18001bf50  mov     [rsp+80h+var_48], rax
0x18001bf55  lea     rax, [rbp+var_28]
0x18001bf59  mov     [rsp+80h+var_50], rax
0x18001bf5e  lea     rax, [rbp+var_30]
0x18001bf62  mov     [rsp+80h+var_58], rax
0x18001bf67  lea     rax, [rbp+var_18]
0x18001bf6b  mov     [rsp+80h+var_60], rax
0x18001bf70  mov     [rbp+arg_10], 4B9h
0x18001bf77  mov     [rbp+var_28], rsi
0x18001bf7b  mov     dword ptr [rbp+var_30], 80004005h
0x18001bf82  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001bf87  mov     eax, cs:dword_1800EB958
0x18001bf8d  mov     ebx, 80004005h
0x18001bf92  mov     dword ptr [r15], 0
0x18001bf99  mov     qword ptr [r14], 0
0x18001bfa0  cmp     eax, 2
0x18001bfa3  jbe     short loc_18001BFF8
0x18001bfa5  lea     rax, aFailedToWaitOn; "Failed to wait on thread events"
0x18001bfac  mov     [rbp+var_18], rdi
0x18001bfb0  mov     [rbp+var_28], rax
0x18001bfb4  lea     rdx, dword_1800CD754
0x18001bfbb  lea     rax, [rbp+var_18]
0x18001bfbf  mov     dword ptr [rbp+arg_0], 4C1h
0x18001bfc6  mov     [rsp+80h+var_40], rax
0x18001bfcb  lea     rax, [rbp+arg_0]
0x18001bfcf  mov     [rsp+80h+var_48], rax
0x18001bfd4  lea     rax, [rbp+var_20]
0x18001bfd8  mov     [rsp+80h+var_50], rax
0x18001bfdd  lea     rax, [rbp+arg_10]
0x18001bfe1  mov     [rsp+80h+var_58], rax
0x18001bfe6  lea     rax, [rbp+var_28]
0x18001bfea  mov     [rbp+var_20], rsi
0x18001bfee  mov     [rbp+arg_10], ebx
0x18001bff1  jmp     loc_18001BEC5
0x18001bff6  xor     ebx, ebx
0x18001bff8  mov     eax, ebx
0x18001bffa  mov     rbx, [rsp+80h+arg_8]
0x18001c002  add     rsp, 80h
0x18001c009  pop     r15
0x18001c00b  pop     r14
0x18001c00d  pop     rdi
0x18001c00e  pop     rsi
0x18001c00f  pop     rbp
0x18001c010  retn
```
