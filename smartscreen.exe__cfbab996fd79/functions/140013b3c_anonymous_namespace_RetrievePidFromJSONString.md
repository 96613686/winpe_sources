# _anonymous_namespace_::RetrievePidFromJSONString

- ea: `0x140013b3c`
- end: `0x140013ca1`
- name: `_anonymous_namespace_::RetrievePidFromJSONString`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013a5c`

## callees

- `0x140013b3c`
- `0x1400154d8`
- `0x14001602c`
- `0x1400184f0`
- `0x140022a70`
- `0x140026c20`
- `0x14002caa0`
- `0x14002cb40`
- `0x14002cbf0`
- `0x14002cc50`
- `0x14003c6b0`

## string_xrefs

- `0x140013b7b`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x140013bf0`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x140013c4b`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::RetrievePidFromJSONString(_QWORD *a1, int *a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // r8
  _QWORD *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rsi
  __int64 ObjectItemCaseSensitive; // rbx
  int v10; // eax
  int v12; // [rsp+20h] [rbp-C8h]
  _QWORD v13[5]; // [rsp+28h] [rbp-C0h] BYREF
  _BYTE v14[128]; // [rsp+50h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( a2 )
  {
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v14);
    if ( a1[3] <= 7u )
      v5 = a1;
    else
      v5 = (_QWORD *)*a1;
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
      v14,
      v13,
      v5,
      (char *)v5 + 2 * a1[2]);
    v6 = v13;
    if ( v13[3] > 0xFu )
      v6 = (_QWORD *)v13[0];
    v7 = cJSON_Parse(v6);
    v8 = v7;
    if ( v7 )
    {
      ObjectItemCaseSensitive = cJSON_GetObjectItemCaseSensitive(v7, "pid");
      if ( (unsigned int)cJSON_IsNumber(ObjectItemCaseSensitive) )
      {
        v10 = *(_DWORD *)(ObjectItemCaseSensitive + 40);
        if ( v10 < 0 )
        {
          *a2 = -1;
          v4 = -2147024362;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\com_api.cpp",
            (const char *)0x80070216LL,
            v12);
        }
        else
        {
          *a2 = v10;
          v4 = 0;
        }
      }
      else
      {
        v4 = -2147024809;
      }
      cJSON_Delete(v8);
    }
    else
    {
      v4 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\com_api.cpp",
        (const char *)0x80070057LL,
        v12);
    }
    std::string::_Tidy_deallocate(v13);
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v14);
  }
  else
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x190,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\com_api.cpp",
      (const char *)0x80004003LL,
      v12);
  }
  return v4;
}

```

## disassembly

```asm
0x140013b3c  mov     [rsp+arg_10], rbx
0x140013b41  mov     [rsp+arg_18], rsi
0x140013b46  push    rdi
0x140013b47  sub     rsp, 0E0h
0x140013b4e  mov     rax, cs:__security_cookie
0x140013b55  xor     rax, rsp
0x140013b58  mov     [rsp+0E8h+var_18], rax
0x140013b60  mov     rdi, rdx
0x140013b63  mov     rbx, rcx
0x140013b66  test    rdx, rdx
0x140013b69  jnz     short loc_140013B91
0x140013b6b  mov     rcx, [rsp+0E8h]; this
0x140013b73  mov     ebx, 80004003h
0x140013b78  mov     r9d, ebx; char *
0x140013b7b  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140013b82  mov     edx, 190h; void *
0x140013b87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013b8c  jmp     loc_140013C79
0x140013b91  lea     rcx, [rsp+0E8h+var_98]
0x140013b96  call    ??0?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x140013b9b  nop
0x140013b9c  cmp     qword ptr [rbx+18h], 7
0x140013ba1  jbe     short loc_140013BA8
0x140013ba3  mov     r8, [rbx]
0x140013ba6  jmp     short loc_140013BAB
0x140013ba8  mov     r8, rbx
0x140013bab  mov     rax, [rbx+10h]
0x140013baf  lea     r9, [r8+rax*2]
0x140013bb3  lea     rdx, [rsp+0E8h+var_C0]
0x140013bb8  lea     rcx, [rsp+0E8h+var_98]
0x140013bbd  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x140013bc2  lea     rcx, [rsp+0E8h+var_C0]
0x140013bc7  cmp     [rsp+0E8h+var_A8], 0Fh
0x140013bcd  cmova   rcx, [rsp+0E8h+var_C0]
0x140013bd3  call    cJSON_Parse
0x140013bd8  mov     rsi, rax
0x140013bdb  test    rax, rax
0x140013bde  jnz     short loc_140013C03
0x140013be0  mov     rcx, [rsp+0E8h]; this
0x140013be8  mov     ebx, 80070057h
0x140013bed  mov     r9d, ebx; char *
0x140013bf0  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140013bf7  mov     edx, 19Ah; void *
0x140013bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013c01  jmp     short loc_140013C64
0x140013c03  lea     rdx, aPid; "pid"
0x140013c0a  mov     rcx, rsi
0x140013c0d  call    cJSON_GetObjectItemCaseSensitive
0x140013c12  mov     rbx, rax
0x140013c15  mov     rcx, rax
0x140013c18  call    cJSON_IsNumber
0x140013c1d  test    eax, eax
0x140013c1f  jnz     short loc_140013C28
0x140013c21  mov     ebx, 80070057h
0x140013c26  jmp     short loc_140013C5C
0x140013c28  mov     eax, [rbx+28h]
0x140013c2b  test    eax, eax
0x140013c2d  js      short loc_140013C35
0x140013c2f  mov     [rdi], eax
0x140013c31  xor     ebx, ebx
0x140013c33  jmp     short loc_140013C5C
0x140013c35  mov     dword ptr [rdi], 0FFFFFFFFh
0x140013c3b  mov     rcx, [rsp+0E8h]; this
0x140013c43  mov     ebx, 80070216h
0x140013c48  mov     r9d, ebx; char *
0x140013c4b  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140013c52  mov     edx, 1AAh; void *
0x140013c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013c5c  mov     rcx, rsi
0x140013c5f  call    cJSON_Delete
0x140013c64  lea     rcx, [rsp+0E8h+var_C0]
0x140013c69  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140013c6e  nop
0x140013c6f  lea     rcx, [rsp+0E8h+var_98]
0x140013c74  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x140013c79  mov     eax, ebx
0x140013c7b  mov     rcx, [rsp+0E8h+var_18]
0x140013c83  xor     rcx, rsp; StackCookie
0x140013c86  call    __security_check_cookie
0x140013c8b  lea     r11, [rsp+0E8h+var_8]
0x140013c93  mov     rbx, [r11+20h]
0x140013c97  mov     rsi, [r11+28h]
0x140013c9b  mov     rsp, r11
0x140013c9e  pop     rdi
0x140013c9f  retn
```
