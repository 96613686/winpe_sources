# WpnParseVarDate(ushort const *,double *)

- ea: `0x180084f88`
- end: `0x1800850ce`
- name: `?WpnParseVarDate@@YAJPEBGPEAN@Z`
- size: `326`
- prototype: `__int64 __fastcall(wchar_t *Buffer, DOUBLE *pvtime)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180077820`
- `0x180078c40`

## callees

- `0x180007440`
- `0x180008300`
- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x180084f88`

## import_xrefs

- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180085066`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180085066`

## string_xrefs

- `0x18008500e`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180085075`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
__int64 __fastcall WpnParseVarDate(wchar_t *Buffer, DOUBLE *pvtime)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-48h]
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  SystemTime = 0;
  if ( !Buffer )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  if ( !pvtime )
    MicrosoftTelemetryAssertTriggeredNoArgs(Buffer);
  if ( swscanf_s(
         Buffer,
         L"%4hu-%2hu-%2huT%2hu:%2hu:%2huZ",
         &SystemTime,
         &SystemTime.wMonth,
         &SystemTime.wDay,
         &SystemTime.wHour,
         &SystemTime.wMinute,
         &SystemTime.wSecond) == 6 )
  {
    if ( SystemTimeToVariantTime(&SystemTime, pvtime) )
      return 0;
    v4 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)0x80004005LL,
      v8);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v6 = 19;
      goto LABEL_9;
    }
  }
  else
  {
    v4 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)0x80004005LL,
      v8);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v6 = 18;
LABEL_9:
      WPP_SF_d(v5[2], v6, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids, 2147500037LL);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180084f88  mov     [rsp+arg_10], rbx
0x180084f8d  push    rdi
0x180084f8e  sub     rsp, 60h
0x180084f92  mov     rax, cs:__security_cookie
0x180084f99  xor     rax, rsp
0x180084f9c  mov     [rsp+68h+var_18], rax
0x180084fa1  xorps   xmm0, xmm0
0x180084fa4  mov     rbx, rdx
0x180084fa7  mov     rdi, rcx
0x180084faa  movups  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x180084faf  test    rcx, rcx
0x180084fb2  jnz     short loc_180084FB9
0x180084fb4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180084fb9  test    rbx, rbx
0x180084fbc  jnz     short loc_180084FC3
0x180084fbe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180084fc3  lea     rax, [rsp+68h+SystemTime.wSecond]
0x180084fc8  mov     rcx, rdi; Buffer
0x180084fcb  mov     [rsp+68h+var_30], rax
0x180084fd0  lea     r9, [rsp+68h+SystemTime.wMonth]
0x180084fd5  lea     rax, [rsp+68h+SystemTime.wMinute]
0x180084fda  mov     [rsp+68h+var_38], rax
0x180084fdf  lea     r8, [rsp+68h+SystemTime]
0x180084fe4  lea     rax, [rsp+68h+SystemTime.wHour]
0x180084fe9  mov     [rsp+68h+var_40], rax
0x180084fee  lea     rdx, a4hu2hu2hut2hu2; "%4hu-%2hu-%2huT%2hu:%2hu:%2huZ"
0x180084ff5  lea     rax, [rsp+68h+SystemTime.wDay]
0x180084ffa  mov     qword ptr [rsp+68h+var_48], rax; int
0x180084fff  call    swscanf_s
0x180085004  cmp     eax, 6
0x180085007  jz      short loc_18008505E
0x180085009  mov     rcx, [rsp+68h]; this
0x18008500e  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085015  mov     r9d, 80004005h; char *
0x18008501b  mov     edx, 1AEh; void *
0x180085020  mov     ebx, r9d
0x180085023  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180085028  mov     rcx, cs:WPP_GLOBAL_Control
0x18008502f  lea     rax, WPP_GLOBAL_Control
0x180085036  cmp     rcx, rax
0x180085039  jz      short loc_1800850B1
0x18008503b  test    byte ptr [rcx+1Ch], 80h
0x18008503f  jz      short loc_1800850B1
0x180085041  mov     edx, 12h
0x180085046  mov     rcx, [rcx+10h]
0x18008504a  lea     r8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids
0x180085051  mov     r9d, 80004005h
0x180085057  call    WPP_SF_d
0x18008505c  jmp     short loc_1800850B1
0x18008505e  mov     rdx, rbx; pvtime
0x180085061  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x180085066  call    cs:__imp_SystemTimeToVariantTime
0x18008506c  test    eax, eax
0x18008506e  jnz     short loc_1800850AF
0x180085070  mov     rcx, [rsp+68h]; this
0x180085075  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008507c  mov     r9d, 80004005h; char *
0x180085082  mov     edx, 1B3h; void *
0x180085087  mov     ebx, r9d
0x18008508a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008508f  mov     rcx, cs:WPP_GLOBAL_Control
0x180085096  lea     rax, WPP_GLOBAL_Control
0x18008509d  cmp     rcx, rax
0x1800850a0  jz      short loc_1800850B1
0x1800850a2  test    byte ptr [rcx+1Ch], 80h
0x1800850a6  jz      short loc_1800850B1
0x1800850a8  mov     edx, 13h
0x1800850ad  jmp     short loc_180085046
0x1800850af  xor     ebx, ebx
0x1800850b1  mov     eax, ebx
0x1800850b3  mov     rcx, [rsp+68h+var_18]
0x1800850b8  xor     rcx, rsp; StackCookie
0x1800850bb  call    __security_check_cookie
0x1800850c0  mov     rbx, [rsp+68h+arg_10]
0x1800850c8  add     rsp, 60h
0x1800850cc  pop     rdi
0x1800850cd  retn
```
