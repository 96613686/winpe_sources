# WpnUtf8ToUtf16(char const *,ushort * *)

- ea: `0x18001ce24`
- end: `0x18001d014`
- name: `?WpnUtf8ToUtf16@@YAJPEBDPEAPEAG@Z`
- size: `496`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c594`
- `0x180037c60`
- `0x180051760`
- `0x1800620e4`
- `0x180070d10`
- `0x1800771ec`
- `0x180077820`
- `0x180077a3c`
- `0x1800794a4`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001ce24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cf04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cf04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cffa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cef3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cfec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cef3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cfec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf83`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ce6a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cf79`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ce6a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cf79`

## string_xrefs

- `0x18001ce91`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001cf17`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001cf9d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`

## pseudocode

```c
__int64 __fastcall WpnUtf8ToUtf16(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  int v4; // eax
  __int64 cchWideChar; // r14
  signed int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  HANDLE ProcessHeap; // rax
  WCHAR *v12; // rax
  unsigned __int16 *v13; // rsi
  signed int LastError; // eax
  HANDLE v15; // rax
  int lpWideCharStr; // [rsp+20h] [rbp-38h]
  int lpWideCharStra; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !lpMultiByteStr )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(lpMultiByteStr);
  v4 = MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v4;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    v12 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * cchWideChar);
    v13 = v12;
    if ( v12 )
    {
      if ( MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, -1, v12, cchWideChar) )
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
          (void *)0xFD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
          (const char *)v7,
          lpWideCharStra);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, v7);
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v13);
      }
    }
    else
    {
      v7 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
        (const char *)0x8007000ELL,
        lpWideCharStr);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v9 = 22;
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
      (void *)0xF1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
      (const char *)v7,
      lpWideCharStr);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v9 = 21;
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
0x18001ce24  push    rbx
0x18001ce26  push    rbp
0x18001ce27  push    rsi
0x18001ce28  push    rdi
0x18001ce29  push    r14
0x18001ce2b  sub     rsp, 30h
0x18001ce2f  mov     rdi, rdx
0x18001ce32  mov     rbp, rcx
0x18001ce35  test    rcx, rcx
0x18001ce38  jnz     short loc_18001CE3F
0x18001ce3a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ce3f  test    rdi, rdi
0x18001ce42  jnz     short loc_18001CE49
0x18001ce44  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ce49  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001ce4d  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x18001ce55  mov     r8, rbp; lpMultiByteStr
0x18001ce58  mov     [rsp+58h+lpWideCharStr], 0; int
0x18001ce61  mov     ecx, 0FDE9h; CodePage
0x18001ce66  lea     edx, [r9+9]; dwFlags
0x18001ce6a  call    cs:__imp_MultiByteToWideChar
0x18001ce70  movsxd  r14, eax
0x18001ce73  test    eax, eax
0x18001ce75  jnz     short loc_18001CEED
0x18001ce77  call    cs:__imp_GetLastError
0x18001ce7d  mov     ebx, eax
0x18001ce7f  test    eax, eax
0x18001ce81  jle     short loc_18001CE8C
0x18001ce83  movzx   ebx, ax
0x18001ce86  or      ebx, 80070000h
0x18001ce8c  mov     rcx, [rsp+58h]; this
0x18001ce91  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ce98  test    ebx, ebx
0x18001ce9a  mov     eax, 80004005h
0x18001ce9f  mov     edx, 0F1h; void *
0x18001cea4  cmovns  ebx, eax
0x18001cea7  mov     r9d, ebx; char *
0x18001ceaa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ceaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ceb6  lea     rax, WPP_GLOBAL_Control
0x18001cebd  cmp     rcx, rax
0x18001cec0  jz      loc_18001D007
0x18001cec6  test    byte ptr [rcx+1Ch], 80h
0x18001ceca  jz      loc_18001D007
0x18001ced0  mov     edx, 15h
0x18001ced5  mov     r9d, ebx
0x18001ced8  mov     rcx, [rcx+10h]
0x18001cedc  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001cee3  call    WPP_SF_d
0x18001cee8  jmp     loc_18001D007
0x18001ceed  mov     rbx, r14
0x18001cef0  add     rbx, rbx
0x18001cef3  call    cs:__imp_GetProcessHeap
0x18001cef9  mov     r8, rbx; dwBytes
0x18001cefc  mov     edx, 8; dwFlags
0x18001cf01  mov     rcx, rax; hHeap
0x18001cf04  call    cs:__imp_HeapAlloc
0x18001cf0a  mov     rsi, rax
0x18001cf0d  test    rax, rax
0x18001cf10  jnz     short loc_18001CF5F
0x18001cf12  mov     rcx, [rsp+58h]; this
0x18001cf17  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001cf1e  mov     ebx, 8007000Eh
0x18001cf23  mov     edx, 0F4h; void *
0x18001cf28  mov     r9d, ebx; char *
0x18001cf2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cf30  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf37  lea     rax, WPP_GLOBAL_Control
0x18001cf3e  cmp     rcx, rax
0x18001cf41  jz      loc_18001D007
0x18001cf47  test    byte ptr [rcx+1Ch], 80h
0x18001cf4b  jz      loc_18001D007
0x18001cf51  lea     edx, [rsi+16h]
0x18001cf54  mov     r9d, 8007000Eh
0x18001cf5a  jmp     loc_18001CED8
0x18001cf5f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001cf63  mov     [rsp+58h+cchWideChar], r14d; cchWideChar
0x18001cf68  mov     r8, rbp; lpMultiByteStr
0x18001cf6b  mov     [rsp+58h+lpWideCharStr], rsi; int
0x18001cf70  mov     ecx, 0FDE9h; CodePage
0x18001cf75  lea     edx, [r9+9]; dwFlags
0x18001cf79  call    cs:__imp_MultiByteToWideChar
0x18001cf7f  test    eax, eax
0x18001cf81  jnz     short loc_18001D002
0x18001cf83  call    cs:__imp_GetLastError
0x18001cf89  mov     ebx, eax
0x18001cf8b  test    eax, eax
0x18001cf8d  jle     short loc_18001CF98
0x18001cf8f  movzx   ebx, ax
0x18001cf92  or      ebx, 80070000h
0x18001cf98  mov     rcx, [rsp+58h]; this
0x18001cf9d  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001cfa4  test    ebx, ebx
0x18001cfa6  mov     eax, 80004005h
0x18001cfab  mov     edx, 0FDh; void *
0x18001cfb0  cmovns  ebx, eax
0x18001cfb3  mov     r9d, ebx; char *
0x18001cfb6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cfbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfc2  lea     rax, WPP_GLOBAL_Control
0x18001cfc9  cmp     rcx, rax
0x18001cfcc  jz      short loc_18001CFEC
0x18001cfce  test    byte ptr [rcx+1Ch], 80h
0x18001cfd2  jz      short loc_18001CFEC
0x18001cfd4  mov     rcx, [rcx+10h]
0x18001cfd8  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001cfdf  mov     edx, 17h
0x18001cfe4  mov     r9d, ebx
0x18001cfe7  call    WPP_SF_d
0x18001cfec  call    cs:__imp_GetProcessHeap
0x18001cff2  mov     r8, rsi; lpMem
0x18001cff5  xor     edx, edx; dwFlags
0x18001cff7  mov     rcx, rax; hHeap
0x18001cffa  call    cs:__imp_HeapFree
0x18001d000  jmp     short loc_18001D007
0x18001d002  mov     [rdi], rsi
0x18001d005  xor     ebx, ebx
0x18001d007  mov     eax, ebx
0x18001d009  add     rsp, 30h
0x18001d00d  pop     r14
0x18001d00f  pop     rdi
0x18001d010  pop     rsi
0x18001d011  pop     rbp
0x18001d012  pop     rbx
0x18001d013  retn
```
