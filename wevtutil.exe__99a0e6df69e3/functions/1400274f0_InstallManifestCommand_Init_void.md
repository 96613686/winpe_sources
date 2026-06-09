# InstallManifestCommand::Init(void)

- ea: `0x1400274f0`
- end: `0x1400276b8`
- name: `?Init@InstallManifestCommand@@UEAAXXZ`
- size: `456`
- prototype: `void __fastcall(InstallManifestCommand *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14000ebbc`
- `0x140011a38`
- `0x140011bbc`
- `0x1400163cc`
- `0x1400165a4`
- `0x14002445c`
- `0x1400247c8`

## string_xrefs

- `0x1400275ea`: `resourceFilePath`
- `0x14002762a`: `messageFilePath`
- `0x140027671`: `parameterFilePath`

## pseudocode

```c
void __fastcall InstallManifestCommand::Init(CommandArguments **this)
{
  __int64 ***v2; // rcx
  __int64 Argument; // rax
  CommandArguments *v4; // rcx
  __int64 v5; // r9
  char OptionBool; // al
  CommandArguments *v7; // rcx
  __int64 v8; // r9
  char v9; // al
  CommandArguments *v10; // rcx
  CommandArguments *v11; // rcx
  __int128 v12; // [rsp+30h] [rbp-28h] BYREF
  __int128 v13; // [rsp+40h] [rbp-18h] BYREF
  char v14; // [rsp+80h] [rbp+28h] BYREF

  CommandArguments::ValidateArgumentCount(this[1], 2u);
  v2 = (__int64 ***)this[1];
  *(_QWORD *)&v12 = off_1400420C0;
  *((_QWORD *)&v12 + 1) = 8;
  CommandArguments::ValidateOptions(v2, (__int64)&v12);
  Argument = CommandArguments::GetArgument(this[1], 1);
  std::wstring::operator=(this + 5, Argument);
  v4 = this[1];
  *(_QWORD *)&v13 = L"fromwow64";
  *(_QWORD *)&v12 = &ValueName;
  *((_QWORD *)&v12 + 1) = 0;
  *((_QWORD *)&v13 + 1) = 9;
  OptionBool = CommandArguments::GetOptionBool(v4, &v13, &v12, v5, &v14);
  v7 = this[1];
  *((_BYTE *)this + 169) = OptionBool;
  *(_QWORD *)&v13 = &ValueName;
  *(_QWORD *)&v12 = L"offline";
  *((_QWORD *)&v13 + 1) = 0;
  *((_QWORD *)&v12 + 1) = 7;
  v9 = CommandArguments::GetOptionBool(v7, &v12, &v13, v8, &v14);
  v10 = this[1];
  *((_BYTE *)this + 170) = v9;
  *((_QWORD *)&v13 + 1) = 2;
  *(_QWORD *)&v13 = L"rf";
  *((_QWORD *)&v12 + 1) = 16;
  *(_QWORD *)&v12 = L"resourceFilePath";
  CommandArguments::GetOptionString(
    (_DWORD)v10,
    (unsigned int)&v12,
    (unsigned int)&v13,
    (unsigned int)&ValueName,
    (__int64)&v14);
  std::wstring::assign(this + 9);
  v11 = this[1];
  *(_QWORD *)&v13 = L"mf";
  *((_QWORD *)&v13 + 1) = 2;
  *(_QWORD *)&v12 = L"messageFilePath";
  *((_QWORD *)&v12 + 1) = 15;
  CommandArguments::GetOptionString(
    (_DWORD)v11,
    (unsigned int)&v12,
    (unsigned int)&v13,
    (unsigned int)&ValueName,
    (__int64)&v14);
  std::wstring::assign(this + 13);
  *((_QWORD *)&v13 + 1) = 2;
  *(_QWORD *)&v13 = L"pf";
  *(_QWORD *)&v12 = L"parameterFilePath";
  *((_QWORD *)&v12 + 1) = 17;
  CommandArguments::GetOptionString(
    (unsigned int)this[1],
    (unsigned int)&v12,
    (unsigned int)&v13,
    (unsigned int)&ValueName,
    (__int64)&v14);
  std::wstring::assign(this + 17);
}

```

## disassembly

```asm
0x1400274f0  push    rbp
0x1400274f2  push    rbx
0x1400274f3  push    rsi
0x1400274f4  push    rdi
0x1400274f5  mov     rbp, rsp
0x1400274f8  sub     rsp, 58h
0x1400274fc  mov     rbx, rcx
0x1400274ff  mov     esi, 2
0x140027504  mov     rcx, [rcx+8]; this
0x140027508  mov     edx, esi; unsigned __int64
0x14002750a  call    ?ValidateArgumentCount@CommandArguments@@QEBAX_K@Z; CommandArguments::ValidateArgumentCount(unsigned __int64)
0x14002750f  mov     rcx, [rbx+8]
0x140027513  lea     rax, off_1400420C0; "fromwow64"
0x14002751a  lea     rdx, [rbp+var_28]
0x14002751e  mov     [rbp+var_28], rax
0x140027522  mov     [rbp+var_20], 8
0x14002752a  call    ?ValidateOptions@CommandArguments@@QEBAXV?$span@PEB_W$0?0@utl@@@Z; CommandArguments::ValidateOptions(utl::span<wchar_t const *,-1>)
0x14002752f  mov     rcx, [rbx+8]
0x140027533  lea     edx, [rsi-1]
0x140027536  call    ?GetArgument@CommandArguments@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; CommandArguments::GetArgument(unsigned __int64)
0x14002753b  mov     rdx, rax
0x14002753e  lea     rcx, [rbx+28h]
0x140027542  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140027547  mov     rcx, [rbx+8]
0x14002754b  lea     rax, aFromwow64_0; "fromwow64"
0x140027552  mov     [rbp+var_18], rax
0x140027556  lea     rdi, ValueName
0x14002755d  lea     rax, [rbp+arg_0]
0x140027561  mov     [rbp+var_28], rdi
0x140027565  lea     r8, [rbp+var_28]
0x140027569  mov     [rsp+58h+var_38], rax
0x14002756e  lea     rdx, [rbp+var_18]
0x140027572  mov     [rbp+var_20], 0
0x14002757a  mov     [rbp+var_10], 9
0x140027582  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x140027587  mov     rcx, [rbx+8]
0x14002758b  lea     r8, [rbp+var_18]
0x14002758f  mov     [rbx+0A9h], al
0x140027595  lea     rdx, [rbp+var_28]
0x140027599  lea     rax, aOffline; "offline"
0x1400275a0  mov     [rbp+var_18], rdi
0x1400275a4  mov     [rbp+var_28], rax
0x1400275a8  lea     rax, [rbp+arg_0]
0x1400275ac  mov     [rsp+58h+var_38], rax
0x1400275b1  mov     [rbp+var_10], 0
0x1400275b9  mov     [rbp+var_20], 7
0x1400275c1  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x1400275c6  mov     rcx, [rbx+8]
0x1400275ca  lea     r8, [rbp+var_18]
0x1400275ce  mov     [rbx+0AAh], al
0x1400275d4  lea     rdx, [rbp+var_28]
0x1400275d8  lea     rax, aRf; "rf"
0x1400275df  mov     [rbp+var_10], rsi
0x1400275e3  mov     [rbp+var_18], rax
0x1400275e7  mov     r9, rdi
0x1400275ea  lea     rax, aResourcefilepa; "resourceFilePath"
0x1400275f1  mov     [rbp+var_20], 10h
0x1400275f9  mov     [rbp+var_28], rax
0x1400275fd  lea     rax, [rbp+arg_0]
0x140027601  mov     [rsp+58h+var_38], rax
0x140027606  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x14002760b  lea     rcx, [rbx+48h]
0x14002760f  mov     rdx, rax
0x140027612  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x140027617  mov     rcx, [rbx+8]
0x14002761b  lea     rax, aMf; "mf"
0x140027622  mov     [rbp+var_18], rax
0x140027626  lea     r8, [rbp+var_18]
0x14002762a  lea     rax, aMessagefilepat; "messageFilePath"
0x140027631  mov     [rbp+var_10], rsi
0x140027635  mov     [rbp+var_28], rax
0x140027639  lea     rdx, [rbp+var_28]
0x14002763d  lea     rax, [rbp+arg_0]
0x140027641  mov     [rbp+var_20], 0Fh
0x140027649  mov     r9, rdi
0x14002764c  mov     [rsp+58h+var_38], rax
0x140027651  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x140027656  lea     rcx, [rbx+68h]
0x14002765a  mov     rdx, rax
0x14002765d  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x140027662  lea     rax, aPf; "pf"
0x140027669  mov     [rbp+var_10], rsi
0x14002766d  mov     [rbp+var_18], rax
0x140027671  lea     rax, aParameterfilep; "parameterFilePath"
0x140027678  mov     [rbp+var_28], rax
0x14002767c  lea     rax, [rbp+arg_0]
0x140027680  mov     [rbp+var_20], 11h
0x140027688  mov     rcx, [rbx+8]
0x14002768c  lea     r8, [rbp+var_18]
0x140027690  mov     r9, rdi
0x140027693  mov     [rsp+58h+var_38], rax
0x140027698  lea     rdx, [rbp+var_28]
0x14002769c  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x1400276a1  lea     rcx, [rbx+88h]
0x1400276a8  mov     rdx, rax
0x1400276ab  add     rsp, 58h
0x1400276af  pop     rdi
0x1400276b0  pop     rsi
0x1400276b1  pop     rbx
0x1400276b2  pop     rbp
0x1400276b3  jmp     ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
```
