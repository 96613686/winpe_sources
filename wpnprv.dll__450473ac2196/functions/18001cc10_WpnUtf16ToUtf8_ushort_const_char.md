# WpnUtf16ToUtf8(ushort const *,char * *)

- ea: `0x18001cc10`
- end: `0x18001ce1c`
- name: `?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z`
- size: `524`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **)`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c52c`
- `0x18003e6fc`
- `0x18003f0a0`
- `0x180056538`
- `0x1800678a4`
- `0x18006b930`
- `0x180072bc0`
- `0x180072f00`
- `0x180073680`
- `0x180073940`
- `0x180073f20`
- `0x18007862c`
- `0x180086860`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001cc10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ccfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ccfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ce02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ce02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ccec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cdf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ccec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cdf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd8b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cc69`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cd81`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cc69`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cd81`

## string_xrefs

- `0x18001cc90`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001cd10`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001cda5`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`

## pseudocode

```c
__int64 __fastcall WpnUtf16ToUtf8(LPCWCH lpWideCharStr, char **a2)
{
  int v4; // eax
  SIZE_T cbMultiByte; // rbp
  signed int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  HANDLE ProcessHeap; // rax
  CHAR *v12; // rax
  char *v13; // rsi
  signed int LastError; // eax
  HANDLE v15; // rax
  int lpMultiByteStr; // [rsp+20h] [rbp-48h]
  int lpMultiByteStra; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(lpWideCharStr);
  if ( !lpWideCharStr )
    MicrosoftTelemetryAssertTriggeredNoArgs(lpWideCharStr);
  v4 = WideCharToMultiByte(0xFDE9u, 0x80u, lpWideCharStr, -1, 0, 0, 0, 0);
  cbMultiByte = v4;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    v12 = (CHAR *)HeapAlloc(ProcessHeap, 8u, cbMultiByte);
    v13 = v12;
    if ( v12 )
    {
      if ( WideCharToMultiByte(0xFDE9u, 0x80u, lpWideCharStr, -1, v12, cbMultiByte, 0, 0) )
      {
        *a2 = v13;
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( (v7 & 0x80000000) == 0 )
          v7 = -2147467259;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x143,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
          (const char *)v7,
          lpMultiByteStra);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, v7);
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v13);
      }
    }
    else
    {
      v7 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x138,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
        (const char *)0x8007000ELL,
        lpMultiByteStr);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v9 = 25;
        v10 = 2147942414LL;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( (v7 & 0x80000000) == 0 )
      v7 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
      (const char *)v7,
      lpMultiByteStr);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v9 = 24;
      v10 = v7;
LABEL_13:
      WPP_SF_d(v8[2], v9, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, v10);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18001cc10  push    rbx
0x18001cc12  push    rbp
0x18001cc13  push    rsi
0x18001cc14  push    rdi
0x18001cc15  push    r14
0x18001cc17  sub     rsp, 40h
0x18001cc1b  mov     r14, rdx
0x18001cc1e  mov     rdi, rcx
0x18001cc21  test    rdx, rdx
0x18001cc24  jnz     short loc_18001CC2B
0x18001cc26  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001cc2b  test    rdi, rdi
0x18001cc2e  jnz     short loc_18001CC35
0x18001cc30  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001cc35  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001cc3e  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001cc42  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18001cc4b  mov     r8, rdi; lpWideCharStr
0x18001cc4e  mov     [rsp+68h+cbMultiByte], 0; cbMultiByte
0x18001cc56  mov     edx, 80h; dwFlags
0x18001cc5b  mov     ecx, 0FDE9h; CodePage
0x18001cc60  mov     [rsp+68h+lpMultiByteStr], 0; int
0x18001cc69  call    cs:__imp_WideCharToMultiByte
0x18001cc6f  movsxd  rbp, eax
0x18001cc72  test    eax, eax
0x18001cc74  jnz     short loc_18001CCEC
0x18001cc76  call    cs:__imp_GetLastError
0x18001cc7c  mov     ebx, eax
0x18001cc7e  test    eax, eax
0x18001cc80  jle     short loc_18001CC8B
0x18001cc82  movzx   ebx, ax
0x18001cc85  or      ebx, 80070000h
0x18001cc8b  mov     rcx, [rsp+68h]; this
0x18001cc90  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001cc97  test    ebx, ebx
0x18001cc99  mov     eax, 80004005h
0x18001cc9e  mov     edx, 135h; void *
0x18001cca3  cmovns  ebx, eax
0x18001cca6  mov     r9d, ebx; char *
0x18001cca9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ccae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccb5  lea     rax, WPP_GLOBAL_Control
0x18001ccbc  cmp     rcx, rax
0x18001ccbf  jz      loc_18001CE0F
0x18001ccc5  test    byte ptr [rcx+1Ch], 80h
0x18001ccc9  jz      loc_18001CE0F
0x18001cccf  mov     edx, 18h
0x18001ccd4  mov     r9d, ebx
0x18001ccd7  mov     rcx, [rcx+10h]
0x18001ccdb  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001cce2  call    WPP_SF_d
0x18001cce7  jmp     loc_18001CE0F
0x18001ccec  call    cs:__imp_GetProcessHeap
0x18001ccf2  mov     r8, rbp; dwBytes
0x18001ccf5  mov     edx, 8; dwFlags
0x18001ccfa  mov     rcx, rax; hHeap
0x18001ccfd  call    cs:__imp_HeapAlloc
0x18001cd03  mov     rsi, rax
0x18001cd06  test    rax, rax
0x18001cd09  jnz     short loc_18001CD55
0x18001cd0b  mov     rcx, [rsp+68h]; this
0x18001cd10  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001cd17  mov     ebx, 8007000Eh
0x18001cd1c  mov     edx, 138h; void *
0x18001cd21  mov     r9d, ebx; char *
0x18001cd24  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cd29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd30  lea     rax, WPP_GLOBAL_Control
0x18001cd37  cmp     rcx, rax
0x18001cd3a  jz      loc_18001CE0F
0x18001cd40  test    byte ptr [rcx+1Ch], 80h
0x18001cd44  jz      loc_18001CE0F
0x18001cd4a  lea     edx, [rsi+19h]
0x18001cd4d  mov     r9d, 8007000Eh
0x18001cd53  jmp     short loc_18001CCD7
0x18001cd55  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001cd5e  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001cd62  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18001cd6b  mov     r8, rdi; lpWideCharStr
0x18001cd6e  mov     [rsp+68h+cbMultiByte], ebp; cbMultiByte
0x18001cd72  mov     edx, 80h; dwFlags
0x18001cd77  mov     ecx, 0FDE9h; CodePage
0x18001cd7c  mov     [rsp+68h+lpMultiByteStr], rsi; int
0x18001cd81  call    cs:__imp_WideCharToMultiByte
0x18001cd87  test    eax, eax
0x18001cd89  jnz     short loc_18001CE0A
0x18001cd8b  call    cs:__imp_GetLastError
0x18001cd91  mov     ebx, eax
0x18001cd93  test    eax, eax
0x18001cd95  jle     short loc_18001CDA0
0x18001cd97  movzx   ebx, ax
0x18001cd9a  or      ebx, 80070000h
0x18001cda0  mov     rcx, [rsp+68h]; this
0x18001cda5  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001cdac  test    ebx, ebx
0x18001cdae  mov     eax, 80004005h
0x18001cdb3  mov     edx, 143h; void *
0x18001cdb8  cmovns  ebx, eax
0x18001cdbb  mov     r9d, ebx; char *
0x18001cdbe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cdc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdca  lea     rax, WPP_GLOBAL_Control
0x18001cdd1  cmp     rcx, rax
0x18001cdd4  jz      short loc_18001CDF4
0x18001cdd6  test    byte ptr [rcx+1Ch], 80h
0x18001cdda  jz      short loc_18001CDF4
0x18001cddc  mov     rcx, [rcx+10h]
0x18001cde0  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001cde7  mov     edx, 1Ah
0x18001cdec  mov     r9d, ebx
0x18001cdef  call    WPP_SF_d
0x18001cdf4  call    cs:__imp_GetProcessHeap
0x18001cdfa  mov     r8, rsi; lpMem
0x18001cdfd  xor     edx, edx; dwFlags
0x18001cdff  mov     rcx, rax; hHeap
0x18001ce02  call    cs:__imp_HeapFree
0x18001ce08  jmp     short loc_18001CE0F
0x18001ce0a  mov     [r14], rsi
0x18001ce0d  xor     ebx, ebx
0x18001ce0f  mov     eax, ebx
0x18001ce11  add     rsp, 40h
0x18001ce15  pop     r14
0x18001ce17  pop     rdi
0x18001ce18  pop     rsi
0x18001ce19  pop     rbp
0x18001ce1a  pop     rbx
0x18001ce1b  retn
```
