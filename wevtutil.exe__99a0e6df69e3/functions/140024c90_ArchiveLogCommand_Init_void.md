# ArchiveLogCommand::Init(void)

- ea: `0x140024c90`
- end: `0x140024df6`
- name: `?Init@ArchiveLogCommand@@UEAAXXZ`
- size: `358`
- prototype: `void __fastcall(ArchiveLogCommand *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140010450`
- `0x140011bbc`
- `0x1400165a4`
- `0x140022cec`
- `0x14002445c`
- `0x1400247c8`
- `0x140024c5c`
- `0x140024c90`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x140024d44`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x140024d44`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x140024dd8`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x140024dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024d55`

## pseudocode

```c
void __fastcall ArchiveLogCommand::Init(CommandArguments **this)
{
  __int64 Argument; // rax
  CommandArguments *v3; // rcx
  const WCHAR *OptionString; // rax
  const wchar_t *Src; // rdi
  LCID v6; // eax
  DWORD LastError; // ebx
  char *v8; // [rsp+20h] [rbp-78h]
  _QWORD v9[2]; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v10[2]; // [rsp+50h] [rbp-48h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+60h] [rbp-38h] BYREF
  char v12; // [rsp+A0h] [rbp+8h] BYREF

  CommandArguments::ValidateArgumentCount(this[1], 2u);
  CommandArguments::ValidateOptions<2>(this[1], off_140042008);
  Argument = CommandArguments::GetArgument(this[1], 1);
  std::wstring::operator=(this + 5, Argument);
  v3 = this[1];
  v9[0] = L"l";
  v9[1] = 1;
  v10[0] = L"locale";
  v10[1] = 6;
  OptionString = (const WCHAR *)CommandArguments::GetOptionString(
                                  (_DWORD)v3,
                                  (unsigned int)v10,
                                  (unsigned int)v9,
                                  0,
                                  (__int64)&v12);
  Src = OptionString;
  if ( OptionString && *OptionString )
  {
    v6 = LocaleNameToLCID(OptionString, 0);
    *((_DWORD *)this + 18) = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ee7c0376249a395d0a854157790e85e8_Traceguids, LastError);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v8, 31, 0x24u, Src);
      throw (EvtException *)pExceptionObject;
    }
  }
  else
  {
    *((_DWORD *)this + 18) = GetThreadLocale();
  }
}

```

## disassembly

```asm
0x140024c90  mov     [rsp+arg_8], rbx
0x140024c95  mov     [rsp+arg_10], rsi
0x140024c9a  push    rdi
0x140024c9b  sub     rsp, 90h
0x140024ca2  mov     rbx, rcx
0x140024ca5  mov     edx, 2; unsigned __int64
0x140024caa  mov     rcx, [rcx+8]; this
0x140024cae  call    ?ValidateArgumentCount@CommandArguments@@QEBAX_K@Z; CommandArguments::ValidateArgumentCount(unsigned __int64)
0x140024cb3  mov     rcx, [rbx+8]
0x140024cb7  lea     rdx, off_140042008; "locale"
0x140024cbe  call    ??$ValidateOptions@$01@CommandArguments@@QEBAXAEAY01PEB_W@Z; CommandArguments::ValidateOptions<2>(wchar_t const * (&)[2])
0x140024cc3  mov     rcx, [rbx+8]
0x140024cc7  mov     edi, 1
0x140024ccc  mov     edx, edi
0x140024cce  call    ?GetArgument@CommandArguments@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; CommandArguments::GetArgument(unsigned __int64)
0x140024cd3  mov     rdx, rax
0x140024cd6  lea     rcx, [rbx+28h]
0x140024cda  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140024cdf  mov     rcx, [rbx+8]
0x140024ce3  lea     rax, asc_1400387C0; "l"
0x140024cea  mov     [rsp+98h+var_58], rax
0x140024cef  lea     r8, [rsp+98h+var_58]
0x140024cf4  lea     rax, aLocale; "locale"
0x140024cfb  mov     [rsp+98h+var_50], rdi
0x140024d00  mov     [rsp+98h+var_48], rax
0x140024d05  lea     rdx, [rsp+98h+var_48]
0x140024d0a  lea     rax, [rsp+98h+arg_0]
0x140024d12  mov     [rsp+98h+var_40], 6
0x140024d1b  xor     r9d, r9d
0x140024d1e  mov     [rsp+98h+var_78], rax; char *
0x140024d23  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x140024d28  xor     esi, esi
0x140024d2a  mov     rdi, rax
0x140024d2d  test    rax, rax
0x140024d30  jz      loc_140024DD8
0x140024d36  cmp     [rax], si
0x140024d39  jz      loc_140024DD8
0x140024d3f  xor     edx, edx; dwFlags
0x140024d41  mov     rcx, rax; lpName
0x140024d44  call    cs:__imp_LocaleNameToLCID
0x140024d4a  mov     [rbx+48h], eax
0x140024d4d  test    eax, eax
0x140024d4f  jnz     loc_140024DE1
0x140024d55  call    cs:__imp_GetLastError
0x140024d5b  mov     ebx, eax
0x140024d5d  mov     eax, 507h
0x140024d62  test    ebx, ebx
0x140024d64  cmovz   ebx, eax
0x140024d67  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d6e  lea     rax, WPP_GLOBAL_Control
0x140024d75  cmp     rcx, rax
0x140024d78  jz      short loc_140024D9F
0x140024d7a  test    dword ptr [rcx+1Ch], 400000h
0x140024d81  jz      short loc_140024D9F
0x140024d83  cmp     byte ptr [rcx+19h], 2
0x140024d87  jb      short loc_140024D9F
0x140024d89  mov     rcx, [rcx+10h]
0x140024d8d  lea     edx, [rsi+0Ah]
0x140024d90  mov     r9d, ebx
0x140024d93  lea     r8, WPP_ee7c0376249a395d0a854157790e85e8_Traceguids
0x140024d9a  call    WPP_SF_d
0x140024d9f  mov     [rsp+98h+Src], rdi; Src
0x140024da4  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140024da9  mov     [rsp+98h+var_68], 24h ; '$'; unsigned int
0x140024db1  xor     r9d, r9d; unsigned int
0x140024db4  xor     r8d, r8d; unsigned int
0x140024db7  mov     [rsp+98h+var_70], 1Fh; int
0x140024dbf  mov     edx, ebx; unsigned int
0x140024dc1  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140024dc6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140024dcd  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140024dd2  call    _CxxThrowException_0
0x140024dd8  call    cs:__imp_GetThreadLocale
0x140024dde  mov     [rbx+48h], eax
0x140024de1  lea     r11, [rsp+98h+var_8]
0x140024de9  mov     rbx, [r11+18h]
0x140024ded  mov     rsi, [r11+20h]
0x140024df1  mov     rsp, r11
0x140024df4  pop     rdi
0x140024df5  retn
```
