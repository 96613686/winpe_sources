# CSLEventLogT<CEmptyType>::LogEventHR(ushort,uint,long,ushort const *,ushort const *,ushort const *)

- ea: `0x18002214c`
- end: `0x1800222c0`
- name: `?LogEventHR@?$CSLEventLogT@VCEmptyType@@@@SAXGIJPEBG00@Z`
- size: `372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180022720`
- `0x1800236b4`

## callees

- `0x180003520`
- `0x180004288`
- `0x18000466c`
- `0x18002214c`
- `0x18003c560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002223e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002223e`
- `ADVAPI32!ReportEventW` at `0x18002222e`
- `ADVAPI32!ReportEventW` at `0x18002222e`
- `ADVAPI32!RegisterEventSourceW` at `0x1800221ba`
- `ADVAPI32!RegisterEventSourceW` at `0x1800221ba`
- `ADVAPI32!DeregisterEventSource` at `0x18002227c`
- `ADVAPI32!DeregisterEventSource` at `0x18002227c`

## string_xrefs

- `0x1800221b1`: `Software Protection Platform Service`

## pseudocode

```c
__int64 __fastcall CSLEventLogT<CEmptyType>::LogEventHR(__int64 a1, DWORD a2, unsigned int a3)
{
  int v4; // eax
  unsigned int v5; // edi
  __int64 v6; // rcx
  HANDLE v7; // rax
  void *v8; // rbx
  signed int v9; // eax
  signed int LastError; // eax
  LPCWSTR Strings; // [rsp+50h] [rbp-58h] BYREF
  __int128 v13; // [rsp+58h] [rbp-50h]
  __int64 v14; // [rsp+68h] [rbp-40h]
  unsigned __int16 v15[20]; // [rsp+70h] [rbp-38h] BYREF

  Strings = v15;
  v13 = 0;
  v14 = 0;
  v4 = StringCchPrintfW(v15, 0x14u, L"hr=0x%X", a3);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = (unsigned int)v4;
LABEL_20:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    return CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  }
  v7 = RegisterEventSourceW(0, L"Software Protection Platform Service");
  v8 = v7;
  if ( v7 )
  {
    if ( ReportEventW(v7, 1u, 0, a2, 0, 1u, 0, &Strings, 0) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v5 = -2147467259;
      }
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    }
  }
  else
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    v8 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v8 )
    DeregisterEventSource(v8);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = v5;
    goto LABEL_20;
  }
  return CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
}

```

## disassembly

```asm
0x18002214c  mov     r11, rsp
0x18002214f  mov     [r11+8], rbx
0x180022153  mov     [r11+20h], rsi
0x180022157  push    rdi
0x180022158  sub     rsp, 0A0h
0x18002215f  mov     rax, cs:__security_cookie
0x180022166  xor     rax, rsp
0x180022169  mov     [rsp+0A8h+var_10], rax
0x180022171  lea     rax, [r11-38h]
0x180022175  xorps   xmm0, xmm0
0x180022178  mov     [r11-58h], rax
0x18002217c  lea     rcx, [r11-38h]; unsigned __int16 *
0x180022180  mov     esi, edx
0x180022182  mov     r9d, r8d
0x180022185  movdqu  [rsp+0A8h+var_50], xmm0
0x18002218b  lea     r8, aHr0xX; "hr=0x%X"
0x180022192  mov     qword ptr [r11-40h], 0
0x18002219a  mov     edx, 14h; unsigned __int64
0x18002219f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800221a4  mov     edi, eax
0x1800221a6  test    eax, eax
0x1800221a8  jns     short loc_1800221B1
0x1800221aa  mov     ecx, eax
0x1800221ac  jmp     loc_18002228E
0x1800221b1  lea     rdx, SourceName; "Software Protection Platform Service"
0x1800221b8  xor     ecx, ecx; lpUNCServerName
0x1800221ba  call    cs:__imp_RegisterEventSourceW
0x1800221c1  nop     dword ptr [rax+rax+00h]
0x1800221c6  mov     rbx, rax
0x1800221c9  test    rax, rax
0x1800221cc  jnz     short loc_1800221FD
0x1800221ce  call    cs:__imp_GetLastError
0x1800221d5  nop     dword ptr [rax+rax+00h]
0x1800221da  mov     edi, eax
0x1800221dc  test    eax, eax
0x1800221de  jnz     short loc_1800221E7
0x1800221e0  mov     edi, 80004005h
0x1800221e5  jmp     short loc_1800221F2
0x1800221e7  jle     short loc_1800221F2
0x1800221e9  movzx   edi, ax
0x1800221ec  or      edi, 80070000h
0x1800221f2  mov     ecx, edi
0x1800221f4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800221f9  xor     ebx, ebx
0x1800221fb  jmp     short loc_18002226D
0x1800221fd  xor     r8d, r8d; wCategory
0x180022200  mov     r9d, 1
0x180022206  mov     [rsp+0A8h+lpRawData], r8; lpRawData
0x18002220b  mov     rcx, rax; hEventLog
0x18002220e  lea     rax, [rsp+0A8h+Strings]
0x180022213  mov     edx, r9d; wType
0x180022216  mov     [rsp+0A8h+lpStrings], rax; lpStrings
0x18002221b  mov     [rsp+0A8h+dwDataSize], r8d; dwDataSize
0x180022220  mov     [rsp+0A8h+wNumStrings], r9w; wNumStrings
0x180022226  mov     r9d, esi; dwEventID
0x180022229  mov     [rsp+0A8h+lpUserSid], r8; lpUserSid
0x18002222e  call    cs:__imp_ReportEventW
0x180022235  nop     dword ptr [rax+rax+00h]
0x18002223a  test    eax, eax
0x18002223c  jnz     short loc_18002226B
0x18002223e  call    cs:__imp_GetLastError
0x180022245  nop     dword ptr [rax+rax+00h]
0x18002224a  mov     edi, eax
0x18002224c  test    eax, eax
0x18002224e  jnz     short loc_180022257
0x180022250  mov     edi, 80004005h
0x180022255  jmp     short loc_180022262
0x180022257  jle     short loc_180022262
0x180022259  movzx   edi, ax
0x18002225c  or      edi, 80070000h
0x180022262  mov     ecx, edi
0x180022264  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180022269  jmp     short loc_18002226D
0x18002226b  xor     edi, edi
0x18002226d  mov     ecx, edi
0x18002226f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180022274  test    rbx, rbx
0x180022277  jz      short loc_180022288
0x180022279  mov     rcx, rbx; hEventLog
0x18002227c  call    cs:__imp_DeregisterEventSource
0x180022283  nop     dword ptr [rax+rax+00h]
0x180022288  test    edi, edi
0x18002228a  jns     short loc_180022293
0x18002228c  mov     ecx, edi
0x18002228e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180022293  mov     ecx, edi
0x180022295  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002229a  mov     rcx, [rsp+0A8h+var_10]
0x1800222a2  xor     rcx, rsp; StackCookie
0x1800222a5  call    __security_check_cookie
0x1800222aa  lea     r11, [rsp+0A8h+var_8]
0x1800222b2  mov     rbx, [r11+10h]
0x1800222b6  mov     rsi, [r11+28h]
0x1800222ba  mov     rsp, r11
0x1800222bd  pop     rdi
0x1800222be  retn
```
