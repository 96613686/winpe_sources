# SetChannelCommand::Init(void)

- ea: `0x140027e70`
- end: `0x140027f69`
- name: `?Init@SetChannelCommand@@UEAAXXZ`
- size: `249`
- prototype: `void __fastcall(SetChannelCommand *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000ebbc`
- `0x140011bbc`
- `0x1400163cc`
- `0x1400165a4`
- `0x14002445c`
- `0x1400247c8`
- `0x140024b00`
- `0x140027e70`

## string_xrefs

- `0x140027ebc`: `Config`

## pseudocode

```c
void __fastcall SetChannelCommand::Init(SetChannelCommand *this)
{
  __int64 ***v2; // rcx
  __int64 v3; // rcx
  char HasOption; // al
  CommandArguments *v5; // rcx
  __int64 v6; // rcx
  __int64 Argument; // rax
  const wchar_t *v8; // [rsp+30h] [rbp-20h] BYREF
  __int64 v9; // [rsp+38h] [rbp-18h]
  const wchar_t *v10; // [rsp+40h] [rbp-10h] BYREF
  __int64 v11; // [rsp+48h] [rbp-8h]
  char v12; // [rsp+70h] [rbp+20h] BYREF

  v9 = 24;
  v2 = (__int64 ***)*((_QWORD *)this + 1);
  v8 = (const wchar_t *)off_140042100;
  CommandArguments::ValidateOptions(v2, (__int64)&v8);
  v3 = *((_QWORD *)this + 1);
  v8 = L"C";
  v9 = 1;
  v10 = L"Config";
  v11 = 6;
  HasOption = CommandArguments::HasOption(v3, &v10, &v8);
  v5 = (CommandArguments *)*((_QWORD *)this + 1);
  if ( HasOption )
  {
    CommandArguments::ValidateArgumentCount(v5, 1u);
    v6 = *((_QWORD *)this + 1);
    v10 = L"C";
    v11 = 1;
    v8 = L"Config";
    v9 = 6;
    CommandArguments::GetOptionString(
      v6,
      (unsigned int)&v8,
      (unsigned int)&v10,
      (unsigned int)&ValueName,
      (__int64)&v12);
    std::wstring::assign((char *)this + 72);
  }
  else
  {
    CommandArguments::ValidateArgumentCount(v5, 2u);
    Argument = CommandArguments::GetArgument(*((_QWORD *)this + 1), 1);
    std::wstring::operator=((char *)this + 40, Argument);
  }
}

```

## disassembly

```asm
0x140027e70  mov     [rsp-18h+arg_8], rbx
0x140027e75  mov     [rsp-18h+arg_10], rsi
0x140027e7a  push    rbp
0x140027e7b  push    rdi
0x140027e7c  push    r14
0x140027e7e  mov     rbp, rsp
0x140027e81  sub     rsp, 50h
0x140027e85  mov     rbx, rcx
0x140027e88  mov     [rbp+var_18], 18h
0x140027e90  mov     rcx, [rcx+8]
0x140027e94  lea     rax, off_140042100; "Enabled"
0x140027e9b  lea     rdx, [rbp+var_20]
0x140027e9f  mov     [rbp+var_20], rax
0x140027ea3  call    ?ValidateOptions@CommandArguments@@QEBAXV?$span@PEB_W$0?0@utl@@@Z; CommandArguments::ValidateOptions(utl::span<wchar_t const *,-1>)
0x140027ea8  mov     rcx, [rbx+8]
0x140027eac  lea     rsi, aC_0; "C"
0x140027eb3  mov     edi, 1
0x140027eb8  mov     [rbp+var_20], rsi
0x140027ebc  lea     r14, aConfig; "Config"
0x140027ec3  mov     [rbp+var_18], rdi
0x140027ec7  lea     r8, [rbp+var_20]
0x140027ecb  mov     [rbp+var_10], r14
0x140027ecf  lea     rdx, [rbp+var_10]
0x140027ed3  mov     [rbp+var_8], 6
0x140027edb  call    ?HasOption@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::HasOption(std::wstring_view,std::wstring_view)
0x140027ee0  mov     rcx, [rbx+8]; this
0x140027ee4  test    al, al
0x140027ee6  jz      short loc_140027F32
0x140027ee8  mov     edx, edi; unsigned __int64
0x140027eea  call    ?ValidateArgumentCount@CommandArguments@@QEBAX_K@Z; CommandArguments::ValidateArgumentCount(unsigned __int64)
0x140027eef  mov     rcx, [rbx+8]
0x140027ef3  lea     rax, [rbp+arg_0]
0x140027ef7  lea     r9, ValueName
0x140027efe  mov     [rsp+50h+var_30], rax
0x140027f03  lea     r8, [rbp+var_10]
0x140027f07  mov     [rbp+var_10], rsi
0x140027f0b  lea     rdx, [rbp+var_20]
0x140027f0f  mov     [rbp+var_8], rdi
0x140027f13  mov     [rbp+var_20], r14
0x140027f17  mov     [rbp+var_18], 6
0x140027f1f  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x140027f24  lea     rcx, [rbx+48h]
0x140027f28  mov     rdx, rax
0x140027f2b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x140027f30  jmp     short loc_140027F54
0x140027f32  mov     edx, 2; unsigned __int64
0x140027f37  call    ?ValidateArgumentCount@CommandArguments@@QEBAX_K@Z; CommandArguments::ValidateArgumentCount(unsigned __int64)
0x140027f3c  mov     rcx, [rbx+8]
0x140027f40  mov     rdx, rdi
0x140027f43  call    ?GetArgument@CommandArguments@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; CommandArguments::GetArgument(unsigned __int64)
0x140027f48  mov     rdx, rax
0x140027f4b  lea     rcx, [rbx+28h]
0x140027f4f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140027f54  lea     r11, [rsp+50h+var_s0]
0x140027f59  mov     rbx, [r11+28h]
0x140027f5d  mov     rsi, [r11+30h]
0x140027f61  mov     rsp, r11
0x140027f64  pop     r14
0x140027f66  pop     rdi
0x140027f67  pop     rbp
0x140027f68  retn
```
