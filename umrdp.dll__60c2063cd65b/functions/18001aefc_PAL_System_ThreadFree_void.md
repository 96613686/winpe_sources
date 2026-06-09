# PAL_System_ThreadFree(void *)

- ea: `0x18001aefc`
- end: `0x18001b027`
- name: `?PAL_System_ThreadFree@@YAJPEAX@Z`
- size: `299`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ac80`
- `0x18003b880`

## callees

- `0x1800010b0`
- `0x1800011c8`
- `0x18001aefc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af86`

## string_xrefs

- `0x18001af31`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001afc6`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001af18`: `PAL_System_ThreadFree`
- `0x18001afbb`: `PAL_System_ThreadFree`
- `0x18001afd1`: `Failed to CloseHandle on thread. GetLastError: 0x%x`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadFree(void *a1, __int64 a2, int a3, int a4)
{
  unsigned int v4; // ebx
  DWORD LastError; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  const char *v10; // [rsp+50h] [rbp-18h] BYREF
  const char *v11; // [rsp+58h] [rbp-10h] BYREF
  int v12; // [rsp+80h] [rbp+18h] BYREF
  int v13; // [rsp+88h] [rbp+20h] BYREF
  const char *v14; // [rsp+90h] [rbp+28h] BYREF
  const char *v15; // [rsp+98h] [rbp+30h] BYREF

  if ( a1 )
  {
    if ( CloseHandle(a1) )
    {
      return 0;
    }
    else
    {
      v4 = -2147467259;
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        LastError = GetLastError();
        v13 = 1570;
        v12 = LastError;
        v15 = "PAL_System_ThreadFree";
        v10 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
        v11 = "Failed to CloseHandle on thread. GetLastError: 0x%x";
        LODWORD(v14) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v6,
          (unsigned int)qword_180054288,
          v7,
          v8,
          (__int64)&v11,
          (__int64)&v14,
          (__int64)&v10,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v12);
      }
    }
  }
  else
  {
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      v12 = 1563;
      v14 = "PAL_System_ThreadFree";
      v15 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v10 = "NULL parameter passed";
      v13 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)byte_1800542DD,
        a3,
        a4,
        (__int64)&v10,
        (__int64)&v13,
        (__int64)&v15,
        (__int64)&v12,
        (__int64)&v14);
    }
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18001aefc  mov     r11, rsp
0x18001aeff  push    rbp
0x18001af00  push    rbx
0x18001af01  mov     rbp, rsp
0x18001af04  sub     rsp, 68h
0x18001af08  test    rcx, rcx
0x18001af0b  jnz     short loc_18001AF86
0x18001af0d  mov     eax, cs:dword_18005C008
0x18001af13  cmp     eax, 2
0x18001af16  jbe     short loc_18001AF7C
0x18001af18  lea     rax, aPalSystemThrea_2; "PAL_System_ThreadFree"
0x18001af1f  mov     [rbp+arg_0], 61Bh
0x18001af26  mov     [rbp+arg_10], rax
0x18001af2a  lea     rdx, byte_1800542DD
0x18001af31  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001af38  mov     ebx, 80004005h
0x18001af3d  mov     [rbp+arg_18], rax
0x18001af41  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001af48  mov     [rbp+var_18], rax
0x18001af4c  lea     rax, [rbp+arg_10]
0x18001af50  mov     [r11-38h], rax
0x18001af54  lea     rax, [rbp+arg_0]
0x18001af58  mov     [r11-40h], rax
0x18001af5c  lea     rax, [rbp+arg_18]
0x18001af60  mov     [r11-48h], rax
0x18001af64  lea     rax, [rbp+arg_8]
0x18001af68  mov     [r11-50h], rax
0x18001af6c  lea     rax, [rbp+var_18]
0x18001af70  mov     [r11-58h], rax
0x18001af74  mov     [rbp+arg_8], ebx
0x18001af77  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001af7c  mov     ebx, 80070057h
0x18001af81  jmp     loc_18001B01E
0x18001af86  call    cs:__imp_CloseHandle
0x18001af8c  test    eax, eax
0x18001af8e  jnz     loc_18001B01C
0x18001af94  mov     eax, cs:dword_18005C008
0x18001af9a  mov     ebx, 80004005h
0x18001af9f  cmp     eax, 2
0x18001afa2  jbe     short loc_18001B01E
0x18001afa4  call    cs:__imp_GetLastError
0x18001afaa  lea     rdx, qword_180054288
0x18001afb1  mov     [rbp+arg_8], 622h
0x18001afb8  mov     [rbp+arg_0], eax
0x18001afbb  lea     rax, aPalSystemThrea_2; "PAL_System_ThreadFree"
0x18001afc2  mov     [rbp+arg_18], rax
0x18001afc6  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001afcd  mov     [rbp+var_18], rax
0x18001afd1  lea     rax, aFailedToCloseh; "Failed to CloseHandle on thread. GetLas"...
0x18001afd8  mov     [rbp+var_10], rax
0x18001afdc  lea     rax, [rbp+arg_0]
0x18001afe0  mov     [rsp+68h+var_20], rax
0x18001afe5  lea     rax, [rbp+arg_18]
0x18001afe9  mov     [rsp+68h+var_28], rax
0x18001afee  lea     rax, [rbp+arg_8]
0x18001aff2  mov     [rsp+68h+var_30], rax
0x18001aff7  lea     rax, [rbp+var_18]
0x18001affb  mov     [rsp+68h+var_38], rax
0x18001b000  lea     rax, [rbp+arg_10]
0x18001b004  mov     [rsp+68h+var_40], rax
0x18001b009  lea     rax, [rbp+var_10]
0x18001b00d  mov     [rsp+68h+var_48], rax
0x18001b012  mov     dword ptr [rbp+arg_10], ebx
0x18001b015  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001b01a  jmp     short loc_18001B01E
0x18001b01c  xor     ebx, ebx
0x18001b01e  mov     eax, ebx
0x18001b020  add     rsp, 68h
0x18001b024  pop     rbx
0x18001b025  pop     rbp
0x18001b026  retn
```
