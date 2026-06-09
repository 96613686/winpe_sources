# GetFilePath(_GUID,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180075ed8`
- end: `0x180076031`
- name: `?GetFilePath@@YAJU_GUID@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(UUID *Uuid1, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180055b14`

## callees

- `0x18001434c`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x18003f80c`
- `0x18005388c`
- `0x180068f60`
- `0x180069cc8`
- `0x180075b84`
- `0x180075ed8`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x180075fd9`
- `RPCRT4!UuidEqual` at `0x180075fd9`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180075f2f`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180075f2f`

## string_xrefs

- `0x180075f45`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`
- `0x180075f9e`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFilePath(UUID *Uuid1, __int64 a2)
{
  int BasicProfileFolderPath; // eax
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rax
  struct _SECURITY_ATTRIBUTES *v7; // rdx
  int NestedDirectory; // eax
  RPC_STATUS Status; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v11[40]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v12[528]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  memset_0(v12, 0, 0x208u);
  BasicProfileFolderPath = GetBasicProfileFolderPath(8, L"S-1-5-18", v12, 260);
  v5 = BasicProfileFolderPath;
  if ( BasicProfileFolderPath >= 0 )
  {
    std::wstring::wstring(v11, v12);
    std::wstring::append(v11, L"\\Microsoft\\Windows\\WinBio");
    v6 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
    NestedDirectory = CreateNestedDirectory(v6, v7);
    v5 = NestedDirectory;
    if ( NestedDirectory >= 0 )
    {
      std::wstring::append(v11, L"\\");
      Status = 0;
      if ( UuidEqual(Uuid1, (UUID *)&Uuid2, &Status) )
        std::wstring::append(v11, L"C376F18B-FBC3-470D-9382-D9FA3CD416CD.dat");
      std::wstring::operator=(a2, v11);
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
        (const char *)(unsigned int)NestedDirectory,
        Status);
    }
    std::wstring::_Tidy_deallocate(v11);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      Status);
  }
  return v5;
}

```

## disassembly

```asm
0x180075ed8  mov     [rsp-8+arg_10], rbx
0x180075edd  push    rbp
0x180075ede  push    rsi
0x180075edf  push    rdi
0x180075ee0  lea     rbp, [rsp-170h]
0x180075ee8  sub     rsp, 270h
0x180075eef  mov     rax, cs:__security_cookie
0x180075ef6  xor     rax, rsp
0x180075ef9  mov     [rbp+180h+var_20], rax
0x180075f00  mov     rdi, rdx
0x180075f03  mov     rsi, rcx
0x180075f06  xor     edx, edx; Val
0x180075f08  mov     r8d, 208h; Size
0x180075f0e  lea     rcx, [rsp+280h+var_230]; void *
0x180075f13  call    memset_0
0x180075f18  mov     r9d, 104h
0x180075f1e  lea     r8, [rsp+280h+var_230]
0x180075f23  lea     rdx, aS1518; "S-1-5-18"
0x180075f2a  mov     ecx, 8
0x180075f2f  call    cs:__imp_GetBasicProfileFolderPath
0x180075f35  mov     ebx, eax
0x180075f37  test    eax, eax
0x180075f39  jns     short loc_180075F5B
0x180075f3b  mov     rcx, [rbp+188h]; this
0x180075f42  mov     r9d, eax; char *
0x180075f45  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x180075f4c  mov     edx, 103h; void *
0x180075f51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075f56  jmp     loc_18007600D
0x180075f5b  lea     rdx, [rsp+280h+var_230]
0x180075f60  lea     rcx, [rsp+280h+var_258]
0x180075f65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180075f6a  nop
0x180075f6b  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\WinBio"
0x180075f72  lea     rcx, [rsp+280h+var_258]
0x180075f77  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180075f7c  lea     rcx, [rsp+280h+var_258]
0x180075f81  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180075f86  mov     rcx, rax; unsigned __int16 *
0x180075f89  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x180075f8e  mov     ebx, eax
0x180075f90  test    eax, eax
0x180075f92  jns     short loc_180075FB1
0x180075f94  mov     rcx, [rbp+188h]; this
0x180075f9b  mov     r9d, eax; char *
0x180075f9e  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x180075fa5  mov     edx, 10Bh; void *
0x180075faa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075faf  jmp     short loc_180076003
0x180075fb1  lea     rdx, asc_1800DC1E4; "\\"
0x180075fb8  lea     rcx, [rsp+280h+var_258]
0x180075fbd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180075fc2  mov     [rsp+280h+Status], 0
0x180075fca  lea     r8, [rsp+280h+Status]; Status
0x180075fcf  lea     rdx, Uuid2; Uuid2
0x180075fd6  mov     rcx, rsi; Uuid1
0x180075fd9  call    cs:__imp_UuidEqual
0x180075fdf  test    eax, eax
0x180075fe1  jz      short loc_180075FF4
0x180075fe3  lea     rdx, aC376f18bFbc347; "C376F18B-FBC3-470D-9382-D9FA3CD416CD.da"...
0x180075fea  lea     rcx, [rsp+280h+var_258]
0x180075fef  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180075ff4  lea     rdx, [rsp+280h+var_258]
0x180075ff9  mov     rcx, rdi
0x180075ffc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180076001  xor     ebx, ebx
0x180076003  lea     rcx, [rsp+280h+var_258]
0x180076008  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007600d  mov     eax, ebx
0x18007600f  mov     rcx, [rbp+180h+var_20]
0x180076016  xor     rcx, rsp; StackCookie
0x180076019  call    __security_check_cookie
0x18007601e  mov     rbx, [rsp+280h+arg_10]
0x180076026  add     rsp, 270h
0x18007602d  pop     rdi
0x18007602e  pop     rsi
0x18007602f  pop     rbp
0x180076030  retn
```
