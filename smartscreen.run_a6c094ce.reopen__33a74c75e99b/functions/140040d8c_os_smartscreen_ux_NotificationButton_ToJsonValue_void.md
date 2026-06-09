# os_smartscreen::ux::NotificationButton::ToJsonValue(void)

- ea: `0x140040d8c`
- end: `0x140040ec2`
- name: `?ToJsonValue@NotificationButton@ux@os_smartscreen@@QEBA?AV?$optional@Vjbuilder@ux@os_smartscreen@@@std@@XZ`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140040b3c`

## callees

- `0x1400154d8`
- `0x1400156e8`
- `0x140026c20`
- `0x140040d8c`
- `0x14004dd74`
- `0x14004ddb4`
- `0x14004ddf0`
- `0x14004df70`
- `0x14004dfb4`
- `0x14004e004`

## string_xrefs

- `0x140040e00`: `actionUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall os_smartscreen::ux::NotificationButton::ToJsonValue(__int64 a1, __int64 a2)
{
  const char *v4; // rdx
  _BYTE v6[48]; // [rsp+30h] [rbp-9h] BYREF
  _BYTE v7[16]; // [rsp+60h] [rbp+27h] BYREF
  __int64 v8; // [rsp+70h] [rbp+37h]

  os_smartscreen::ux::jbuilder::jbuilder((os_smartscreen::ux::jbuilder *)v6);
  if ( !(unsigned __int8)os_smartscreen::ux::jbuilder::add_string(v6, "text", a1 + 40)
    || !(unsigned __int8)os_smartscreen::ux::jbuilder::add_optional_string(v6, "title", a1)
    || !(unsigned __int8)os_smartscreen::ux::jbuilder::add_optional_string(v6, "actionUri", a1 + 72) )
  {
    *(_BYTE *)(a2 + 48) = 0;
    goto LABEL_15;
  }
  if ( !*(_BYTE *)(a1 + 116) )
    goto LABEL_13;
  if ( *(_DWORD *)(a1 + 112) )
  {
    v4 = "new_tab";
    if ( *(_DWORD *)(a1 + 112) != 1 )
      v4 = word_1400726BA;
  }
  else
  {
    v4 = "invisible";
  }
  std::string::string(v7, v4);
  if ( !v8 || (unsigned __int8)os_smartscreen::ux::jbuilder::add_string(v6, "target", v7) )
  {
    std::string::_Tidy_deallocate(v7);
LABEL_13:
    os_smartscreen::ux::jbuilder::jbuilder(a2, v6);
    *(_BYTE *)(a2 + 48) = 1;
    goto LABEL_15;
  }
  *(_BYTE *)(a2 + 48) = 0;
  std::string::_Tidy_deallocate(v7);
LABEL_15:
  os_smartscreen::ux::jbuilder::~jbuilder((os_smartscreen::ux::jbuilder *)v6);
  return a2;
}

```

## disassembly

```asm
0x140040d8c  mov     [rsp-8+arg_10], rbx
0x140040d91  mov     [rsp-8+arg_18], rdi
0x140040d96  push    rbp
0x140040d97  lea     rbp, [rsp-57h]
0x140040d9c  sub     rsp, 90h
0x140040da3  mov     rax, cs:__security_cookie
0x140040daa  xor     rax, rsp
0x140040dad  mov     [rbp+57h+var_10], rax
0x140040db1  mov     rbx, rdx
0x140040db4  mov     rdi, rcx
0x140040db7  mov     [rbp+57h+var_68], rdx
0x140040dbb  lea     rcx, [rbp+57h+var_60]; this
0x140040dbf  call    ??0jbuilder@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::jbuilder::jbuilder(void)
0x140040dc4  nop
0x140040dc5  lea     r8, [rdi+28h]
0x140040dc9  lea     rdx, aText; "text"
0x140040dd0  lea     rcx, [rbp+57h+var_60]
0x140040dd4  call    ?add_string@jbuilder@ux@os_smartscreen@@QEBA_NPEBDAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; os_smartscreen::ux::jbuilder::add_string(char const *,std::wstring const &)
0x140040dd9  test    al, al
0x140040ddb  jz      loc_140040E90
0x140040de1  mov     r8, rdi
0x140040de4  lea     rdx, aTitle; "title"
0x140040deb  lea     rcx, [rbp+57h+var_60]
0x140040def  call    ?add_optional_string@jbuilder@ux@os_smartscreen@@QEBA_NPEBDAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z; os_smartscreen::ux::jbuilder::add_optional_string(char const *,std::optional<std::wstring> const &)
0x140040df4  test    al, al
0x140040df6  jz      loc_140040E90
0x140040dfc  lea     r8, [rdi+48h]
0x140040e00  lea     rdx, aActionuri; "actionUri"
0x140040e07  lea     rcx, [rbp+57h+var_60]
0x140040e0b  call    ?add_optional_string@jbuilder@ux@os_smartscreen@@QEBA_NPEBDAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z; os_smartscreen::ux::jbuilder::add_optional_string(char const *,std::optional<std::wstring> const &)
0x140040e10  test    al, al
0x140040e12  jz      short loc_140040E90
0x140040e14  cmp     byte ptr [rdi+74h], 0
0x140040e18  jz      short loc_140040E7E
0x140040e1a  cmp     dword ptr [rdi+70h], 0
0x140040e1e  jnz     short loc_140040E29
0x140040e20  lea     rdx, aInvisible; "invisible"
0x140040e27  jmp     short loc_140040E3F
0x140040e29  lea     rdx, aNewTab; "new_tab"
0x140040e30  lea     rax, word_1400726BA
0x140040e37  cmp     dword ptr [rdi+70h], 1
0x140040e3b  cmovnz  rdx, rax
0x140040e3f  lea     rcx, [rbp+57h+var_30]
0x140040e43  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140040e48  cmp     [rbp+57h+var_20], 0
0x140040e4d  jz      short loc_140040E75
0x140040e4f  lea     r8, [rbp+57h+var_30]
0x140040e53  lea     rdx, aTarget; "target"
0x140040e5a  lea     rcx, [rbp+57h+var_60]
0x140040e5e  call    ?add_string@jbuilder@ux@os_smartscreen@@QEBA_NPEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; os_smartscreen::ux::jbuilder::add_string(char const *,std::string const &)
0x140040e63  test    al, al
0x140040e65  jnz     short loc_140040E75
0x140040e67  mov     [rbx+30h], al
0x140040e6a  lea     rcx, [rbp+57h+var_30]
0x140040e6e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140040e73  jmp     short loc_140040E94
0x140040e75  lea     rcx, [rbp+57h+var_30]
0x140040e79  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140040e7e  lea     rdx, [rbp+57h+var_60]
0x140040e82  mov     rcx, rbx
0x140040e85  call    ??0jbuilder@ux@os_smartscreen@@QEAA@$$QEAV012@@Z; os_smartscreen::ux::jbuilder::jbuilder(os_smartscreen::ux::jbuilder &&)
0x140040e8a  mov     byte ptr [rbx+30h], 1
0x140040e8e  jmp     short loc_140040E94
0x140040e90  mov     byte ptr [rbx+30h], 0
0x140040e94  lea     rcx, [rbp+57h+var_60]; this
0x140040e98  call    ??1jbuilder@ux@os_smartscreen@@UEAA@XZ; os_smartscreen::ux::jbuilder::~jbuilder(void)
0x140040e9d  mov     rax, rbx
0x140040ea0  mov     rcx, [rbp+57h+var_10]
0x140040ea4  xor     rcx, rsp; StackCookie
0x140040ea7  call    __security_check_cookie
0x140040eac  lea     r11, [rsp+90h+var_s0]
0x140040eb4  mov     rbx, [r11+20h]
0x140040eb8  mov     rdi, [r11+28h]
0x140040ebc  mov     rsp, r11
0x140040ebf  pop     rbp
0x140040ec0  retn
```
