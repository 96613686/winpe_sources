# os_smartscreen::ux::NotificationButton::ToJsonValue(void)

- ea: `0x14003f660`
- end: `0x14003f795`
- name: `?ToJsonValue@NotificationButton@ux@os_smartscreen@@QEBA?AV?$optional@Vjbuilder@ux@os_smartscreen@@@std@@XZ`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003f414`

## callees

- `0x140014994`
- `0x140014b7c`
- `0x140025aa0`
- `0x14003f660`
- `0x14004c420`
- `0x14004c460`
- `0x14004c498`
- `0x14004c61c`
- `0x14004c660`
- `0x14004c6ac`

## string_xrefs

- `0x14003f6d4`: `actionUri`

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
      v4 = word_14007089A;
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
0x14003f660  mov     [rsp-8+arg_10], rbx
0x14003f665  mov     [rsp-8+arg_18], rdi
0x14003f66a  push    rbp
0x14003f66b  lea     rbp, [rsp-57h]
0x14003f670  sub     rsp, 90h
0x14003f677  mov     rax, cs:__security_cookie
0x14003f67e  xor     rax, rsp
0x14003f681  mov     [rbp+57h+var_10], rax
0x14003f685  mov     rbx, rdx
0x14003f688  mov     rdi, rcx
0x14003f68b  mov     [rbp+57h+var_68], rdx
0x14003f68f  lea     rcx, [rbp+57h+var_60]; this
0x14003f693  call    ??0jbuilder@ux@os_smartscreen@@QEAA@XZ; os_smartscreen::ux::jbuilder::jbuilder(void)
0x14003f698  nop
0x14003f699  lea     r8, [rdi+28h]
0x14003f69d  lea     rdx, aText; "text"
0x14003f6a4  lea     rcx, [rbp+57h+var_60]
0x14003f6a8  call    ?add_string@jbuilder@ux@os_smartscreen@@QEBA_NPEBDAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; os_smartscreen::ux::jbuilder::add_string(char const *,std::wstring const &)
0x14003f6ad  test    al, al
0x14003f6af  jz      loc_14003F764
0x14003f6b5  mov     r8, rdi
0x14003f6b8  lea     rdx, aTitle; "title"
0x14003f6bf  lea     rcx, [rbp+57h+var_60]
0x14003f6c3  call    ?add_optional_string@jbuilder@ux@os_smartscreen@@QEBA_NPEBDAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z; os_smartscreen::ux::jbuilder::add_optional_string(char const *,std::optional<std::wstring> const &)
0x14003f6c8  test    al, al
0x14003f6ca  jz      loc_14003F764
0x14003f6d0  lea     r8, [rdi+48h]
0x14003f6d4  lea     rdx, aActionuri; "actionUri"
0x14003f6db  lea     rcx, [rbp+57h+var_60]
0x14003f6df  call    ?add_optional_string@jbuilder@ux@os_smartscreen@@QEBA_NPEBDAEBV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z; os_smartscreen::ux::jbuilder::add_optional_string(char const *,std::optional<std::wstring> const &)
0x14003f6e4  test    al, al
0x14003f6e6  jz      short loc_14003F764
0x14003f6e8  cmp     byte ptr [rdi+74h], 0
0x14003f6ec  jz      short loc_14003F752
0x14003f6ee  cmp     dword ptr [rdi+70h], 0
0x14003f6f2  jnz     short loc_14003F6FD
0x14003f6f4  lea     rdx, aInvisible; "invisible"
0x14003f6fb  jmp     short loc_14003F713
0x14003f6fd  lea     rdx, aNewTab; "new_tab"
0x14003f704  lea     rax, word_14007089A
0x14003f70b  cmp     dword ptr [rdi+70h], 1
0x14003f70f  cmovnz  rdx, rax
0x14003f713  lea     rcx, [rbp+57h+var_30]
0x14003f717  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14003f71c  cmp     [rbp+57h+var_20], 0
0x14003f721  jz      short loc_14003F749
0x14003f723  lea     r8, [rbp+57h+var_30]
0x14003f727  lea     rdx, aTarget; "target"
0x14003f72e  lea     rcx, [rbp+57h+var_60]
0x14003f732  call    ?add_string@jbuilder@ux@os_smartscreen@@QEBA_NPEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; os_smartscreen::ux::jbuilder::add_string(char const *,std::string const &)
0x14003f737  test    al, al
0x14003f739  jnz     short loc_14003F749
0x14003f73b  mov     [rbx+30h], al
0x14003f73e  lea     rcx, [rbp+57h+var_30]
0x14003f742  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14003f747  jmp     short loc_14003F768
0x14003f749  lea     rcx, [rbp+57h+var_30]
0x14003f74d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14003f752  lea     rdx, [rbp+57h+var_60]
0x14003f756  mov     rcx, rbx
0x14003f759  call    ??0jbuilder@ux@os_smartscreen@@QEAA@$$QEAV012@@Z; os_smartscreen::ux::jbuilder::jbuilder(os_smartscreen::ux::jbuilder &&)
0x14003f75e  mov     byte ptr [rbx+30h], 1
0x14003f762  jmp     short loc_14003F768
0x14003f764  mov     byte ptr [rbx+30h], 0
0x14003f768  lea     rcx, [rbp+57h+var_60]; this
0x14003f76c  call    ??1jbuilder@ux@os_smartscreen@@UEAA@XZ; os_smartscreen::ux::jbuilder::~jbuilder(void)
0x14003f771  mov     rax, rbx
0x14003f774  mov     rcx, [rbp+57h+var_10]
0x14003f778  xor     rcx, rsp; StackCookie
0x14003f77b  call    __security_check_cookie
0x14003f780  lea     r11, [rsp+90h+var_s0]
0x14003f788  mov     rbx, [r11+20h]
0x14003f78c  mov     rdi, [r11+28h]
0x14003f790  mov     rsp, r11
0x14003f793  pop     rbp
0x14003f794  retn
```
