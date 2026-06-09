# GetLogInfoCommand::Init(void)

- ea: `0x140026a90`
- end: `0x140026b69`
- name: `?Init@GetLogInfoCommand@@UEAAXXZ`
- size: `217`
- prototype: `void __fastcall(GetLogInfoCommand *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011a38`
- `0x1400165a4`
- `0x14002445c`
- `0x1400247c8`
- `0x140024c5c`

## pseudocode

```c
void __fastcall GetLogInfoCommand::Init(CommandArguments **this)
{
  __int64 Argument; // rax
  CommandArguments *v3; // rcx
  __int64 v4; // r9
  char OptionBool; // al
  CommandArguments *v6; // rcx
  __int64 v7; // r9
  __int128 v8; // [rsp+30h] [rbp-20h] BYREF
  __int128 v9; // [rsp+40h] [rbp-10h] BYREF
  char v10; // [rsp+60h] [rbp+10h] BYREF

  CommandArguments::ValidateArgumentCount(this[1], 2u);
  CommandArguments::ValidateOptions<2>(this[1], off_140042080);
  Argument = CommandArguments::GetArgument((__int64)this[1], 1u);
  std::wstring::operator=(this + 5, Argument);
  v3 = this[1];
  *(_QWORD *)&v8 = &ValueName;
  *((_QWORD *)&v8 + 1) = 0;
  *(_QWORD *)&v9 = L"Xml";
  *((_QWORD *)&v9 + 1) = 3;
  OptionBool = CommandArguments::GetOptionBool(v3, &v9, &v8, v4, &v10);
  v6 = this[1];
  *((_BYTE *)this + 112) = OptionBool;
  *((_QWORD *)&v9 + 1) = 2;
  *(_QWORD *)&v9 = L"lf";
  *(_QWORD *)&v8 = L"logfile";
  *((_QWORD *)&v8 + 1) = 7;
  *((_BYTE *)this + 113) = CommandArguments::GetOptionBool(v6, &v8, &v9, v7, &v10);
}

```

## disassembly

```asm
0x140026a90  mov     [rsp-8+arg_8], rbx
0x140026a95  push    rbp
0x140026a96  mov     rbp, rsp
0x140026a99  sub     rsp, 50h
0x140026a9d  mov     rbx, rcx
0x140026aa0  mov     edx, 2; unsigned __int64
0x140026aa5  mov     rcx, [rcx+8]; this
0x140026aa9  call    ?ValidateArgumentCount@CommandArguments@@QEBAX_K@Z; CommandArguments::ValidateArgumentCount(unsigned __int64)
0x140026aae  mov     rcx, [rbx+8]
0x140026ab2  lea     rdx, off_140042080; "logfile"
0x140026ab9  call    ??$ValidateOptions@$01@CommandArguments@@QEBAXAEAY01PEB_W@Z; CommandArguments::ValidateOptions<2>(wchar_t const * (&)[2])
0x140026abe  mov     rcx, [rbx+8]
0x140026ac2  mov     edx, 1
0x140026ac7  call    ?GetArgument@CommandArguments@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; CommandArguments::GetArgument(unsigned __int64)
0x140026acc  mov     rdx, rax
0x140026acf  lea     rcx, [rbx+28h]
0x140026ad3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140026ad8  mov     rcx, [rbx+8]
0x140026adc  lea     rax, ValueName
0x140026ae3  mov     [rbp+var_20], rax
0x140026ae7  lea     r8, [rbp+var_20]
0x140026aeb  lea     rax, aXml; "Xml"
0x140026af2  mov     [rbp+var_18], 0
0x140026afa  mov     [rbp+var_10], rax
0x140026afe  lea     rdx, [rbp+var_10]
0x140026b02  lea     rax, [rbp+arg_0]
0x140026b06  mov     [rbp+var_8], 3
0x140026b0e  mov     [rsp+50h+var_30], rax
0x140026b13  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x140026b18  mov     rcx, [rbx+8]
0x140026b1c  lea     r8, [rbp+var_10]
0x140026b20  mov     [rbx+70h], al
0x140026b23  lea     rdx, [rbp+var_20]
0x140026b27  lea     rax, aLf; "lf"
0x140026b2e  mov     [rbp+var_8], 2
0x140026b36  mov     [rbp+var_10], rax
0x140026b3a  lea     rax, aLogfile; "logfile"
0x140026b41  mov     [rbp+var_20], rax
0x140026b45  lea     rax, [rbp+arg_0]
0x140026b49  mov     [rsp+50h+var_30], rax
0x140026b4e  mov     [rbp+var_18], 7
0x140026b56  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x140026b5b  mov     [rbx+71h], al
0x140026b5e  mov     rbx, [rsp+50h+arg_8]
0x140026b63  add     rsp, 50h
0x140026b67  pop     rbp
0x140026b68  retn
```
