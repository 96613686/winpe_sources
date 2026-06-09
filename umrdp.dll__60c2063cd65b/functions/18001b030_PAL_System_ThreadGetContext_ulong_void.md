# PAL_System_ThreadGetContext(ulong,void * *)

- ea: `0x18001b030`
- end: `0x18001b15a`
- name: `?PAL_System_ThreadGetContext@@YAJKPEAPEAX@Z`
- size: `298`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003ce6c`

## callees

- `0x1800010b0`
- `0x18001b030`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18001b142`
- `KERNEL32!TlsGetValue` at `0x18001b142`

## string_xrefs

- `0x18001b074`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001b0f6`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001b05b`: `PAL_System_ThreadGetContext`
- `0x18001b0dd`: `PAL_System_ThreadGetContext`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadGetContext(DWORD a1, void **a2, int a3, int a4)
{
  unsigned int v4; // ebx
  char *v5; // rdx
  const char **v6; // rax
  const char **v8; // [rsp+30h] [rbp-30h]
  const char *v9; // [rsp+50h] [rbp-10h] BYREF
  const char *v10; // [rsp+58h] [rbp-8h] BYREF
  int v11; // [rsp+78h] [rbp+18h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF
  const char *v13; // [rsp+88h] [rbp+28h] BYREF

  if ( a2 )
  {
    if ( g_PAL_SYS_initState != 2 )
    {
      v4 = -2092629815;
      if ( (unsigned int)dword_18005C008 <= 2 )
        return v4;
      v11 = 1376;
      v13 = "PAL_System_ThreadGetContext";
      v5 = byte_180054243;
      v10 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v9 = "System PAL not initialized";
      v8 = &v10;
      v6 = &v9;
      goto LABEL_4;
    }
    if ( !a1 )
      a1 = g_PAL_SYS_threadContextIndex;
    *a2 = TlsGetValue(a1);
    return 0;
  }
  else
  {
    v4 = -2147024809;
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      v11 = 1370;
      v13 = "PAL_System_ThreadGetContext";
      v5 = byte_1800545C1;
      v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v10 = "NULL parameter passed";
      v8 = &v9;
      v6 = &v10;
LABEL_4:
      v12 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1,
        (_DWORD)v5,
        a3,
        a4,
        (__int64)v6,
        (__int64)&v12,
        (__int64)v8,
        (__int64)&v11,
        (__int64)&v13);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001b030  mov     r11, rsp
0x18001b033  mov     [r11+8], rbx
0x18001b037  push    rbp
0x18001b038  mov     rbp, rsp
0x18001b03b  sub     rsp, 60h
0x18001b03f  mov     rbx, rdx
0x18001b042  test    rdx, rdx
0x18001b045  jnz     short loc_18001B0C4
0x18001b047  mov     eax, cs:dword_18005C008
0x18001b04d  mov     ebx, 80070057h
0x18001b052  cmp     eax, 2
0x18001b055  jbe     loc_18001B14D
0x18001b05b  lea     rax, aPalSystemThrea; "PAL_System_ThreadGetContext"
0x18001b062  mov     [rbp+arg_8], 55Ah
0x18001b069  mov     [rbp+arg_18], rax
0x18001b06d  lea     rdx, byte_1800545C1
0x18001b074  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001b07b  mov     [rbp+var_10], rax
0x18001b07f  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001b086  mov     [rbp+var_8], rax
0x18001b08a  lea     rax, [rbp+arg_18]
0x18001b08e  mov     [r11-28h], rax
0x18001b092  lea     rax, [rbp+arg_8]
0x18001b096  mov     [r11-30h], rax
0x18001b09a  lea     rax, [rbp+var_10]
0x18001b09e  mov     [r11-38h], rax
0x18001b0a2  lea     rax, [rbp+arg_10]
0x18001b0a6  mov     [r11-40h], rax
0x18001b0aa  lea     rax, [rbp+var_8]
0x18001b0ae  mov     [rsp+60h+var_40], rax
0x18001b0b3  mov     [rbp+arg_10], 80004005h
0x18001b0ba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001b0bf  jmp     loc_18001B14D
0x18001b0c4  cmp     cs:?g_PAL_SYS_initState@@3W4PAL_SYS_STATE@@A, 2; PAL_SYS_STATE g_PAL_SYS_initState
0x18001b0cb  jz      short loc_18001B139
0x18001b0cd  mov     eax, cs:dword_18005C008
0x18001b0d3  mov     ebx, 834500C9h
0x18001b0d8  cmp     eax, 2
0x18001b0db  jbe     short loc_18001B14D
0x18001b0dd  lea     rax, aPalSystemThrea; "PAL_System_ThreadGetContext"
0x18001b0e4  mov     [rbp+arg_8], 560h
0x18001b0eb  mov     [rbp+arg_18], rax
0x18001b0ef  lea     rdx, byte_180054243
0x18001b0f6  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001b0fd  mov     [rbp+var_8], rax
0x18001b101  lea     rax, aSystemPalNotIn; "System PAL not initialized"
0x18001b108  mov     [rbp+var_10], rax
0x18001b10c  lea     rax, [rbp+arg_18]
0x18001b110  mov     [rsp+60h+var_20], rax
0x18001b115  lea     rax, [rbp+arg_8]
0x18001b119  mov     [rsp+60h+var_28], rax
0x18001b11e  lea     rax, [rbp+var_8]
0x18001b122  mov     [rsp+60h+var_30], rax
0x18001b127  lea     rax, [rbp+arg_10]
0x18001b12b  mov     [rsp+60h+var_38], rax
0x18001b130  lea     rax, [rbp+var_10]
0x18001b134  jmp     loc_18001B0AE
0x18001b139  test    ecx, ecx
0x18001b13b  cmovz   ecx, cs:?g_PAL_SYS_threadContextIndex@@3KA; dwTlsIndex
0x18001b142  call    cs:__imp_TlsGetValue
0x18001b148  mov     [rbx], rax
0x18001b14b  xor     ebx, ebx
0x18001b14d  mov     eax, ebx
0x18001b14f  mov     rbx, [rsp+60h+arg_0]
0x18001b154  add     rsp, 60h
0x18001b158  pop     rbp
0x18001b159  retn
```
