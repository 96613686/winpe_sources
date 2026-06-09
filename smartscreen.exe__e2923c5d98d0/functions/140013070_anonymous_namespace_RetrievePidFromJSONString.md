# _anonymous_namespace_::RetrievePidFromJSONString

- ea: `0x140013070`
- end: `0x1400131d4`
- name: `_anonymous_namespace_::RetrievePidFromJSONString`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012f94`

## callees

- `0x140013070`
- `0x140014994`
- `0x140015464`
- `0x140016ce4`
- `0x1400218fc`
- `0x140025aa0`
- `0x14002b8d0`
- `0x14002b970`
- `0x14002ba20`
- `0x14002ba80`
- `0x14003b034`

## string_xrefs

- `0x1400130af`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x140013124`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x14001317f`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`

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
0x140013070  mov     [rsp+arg_10], rbx
0x140013075  mov     [rsp+arg_18], rsi
0x14001307a  push    rdi
0x14001307b  sub     rsp, 0E0h
0x140013082  mov     rax, cs:__security_cookie
0x140013089  xor     rax, rsp
0x14001308c  mov     [rsp+0E8h+var_18], rax
0x140013094  mov     rdi, rdx
0x140013097  mov     rbx, rcx
0x14001309a  test    rdx, rdx
0x14001309d  jnz     short loc_1400130C5
0x14001309f  mov     rcx, [rsp+0E8h]; this
0x1400130a7  mov     ebx, 80004003h
0x1400130ac  mov     r9d, ebx; char *
0x1400130af  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400130b6  mov     edx, 190h; void *
0x1400130bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400130c0  jmp     loc_1400131AD
0x1400130c5  lea     rcx, [rsp+0E8h+var_98]
0x1400130ca  call    ??0?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1400130cf  nop
0x1400130d0  cmp     qword ptr [rbx+18h], 7
0x1400130d5  jbe     short loc_1400130DC
0x1400130d7  mov     r8, [rbx]
0x1400130da  jmp     short loc_1400130DF
0x1400130dc  mov     r8, rbx
0x1400130df  mov     rax, [rbx+10h]
0x1400130e3  lea     r9, [r8+rax*2]
0x1400130e7  lea     rdx, [rsp+0E8h+var_C0]
0x1400130ec  lea     rcx, [rsp+0E8h+var_98]
0x1400130f1  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x1400130f6  lea     rcx, [rsp+0E8h+var_C0]
0x1400130fb  cmp     [rsp+0E8h+var_A8], 0Fh
0x140013101  cmova   rcx, [rsp+0E8h+var_C0]
0x140013107  call    cJSON_Parse
0x14001310c  mov     rsi, rax
0x14001310f  test    rax, rax
0x140013112  jnz     short loc_140013137
0x140013114  mov     rcx, [rsp+0E8h]; this
0x14001311c  mov     ebx, 80070057h
0x140013121  mov     r9d, ebx; char *
0x140013124  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001312b  mov     edx, 19Ah; void *
0x140013130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013135  jmp     short loc_140013198
0x140013137  lea     rdx, aPid; "pid"
0x14001313e  mov     rcx, rsi
0x140013141  call    cJSON_GetObjectItemCaseSensitive
0x140013146  mov     rbx, rax
0x140013149  mov     rcx, rax
0x14001314c  call    cJSON_IsNumber
0x140013151  test    eax, eax
0x140013153  jnz     short loc_14001315C
0x140013155  mov     ebx, 80070057h
0x14001315a  jmp     short loc_140013190
0x14001315c  mov     eax, [rbx+28h]
0x14001315f  test    eax, eax
0x140013161  js      short loc_140013169
0x140013163  mov     [rdi], eax
0x140013165  xor     ebx, ebx
0x140013167  jmp     short loc_140013190
0x140013169  mov     dword ptr [rdi], 0FFFFFFFFh
0x14001316f  mov     rcx, [rsp+0E8h]; this
0x140013177  mov     ebx, 80070216h
0x14001317c  mov     r9d, ebx; char *
0x14001317f  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140013186  mov     edx, 1AAh; void *
0x14001318b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013190  mov     rcx, rsi
0x140013193  call    cJSON_Delete
0x140013198  lea     rcx, [rsp+0E8h+var_C0]
0x14001319d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400131a2  nop
0x1400131a3  lea     rcx, [rsp+0E8h+var_98]
0x1400131a8  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1400131ad  mov     eax, ebx
0x1400131af  mov     rcx, [rsp+0E8h+var_18]
0x1400131b7  xor     rcx, rsp; StackCookie
0x1400131ba  call    __security_check_cookie
0x1400131bf  lea     r11, [rsp+0E8h+var_8]
0x1400131c7  mov     rbx, [r11+20h]
0x1400131cb  mov     rsi, [r11+28h]
0x1400131cf  mov     rsp, r11
0x1400131d2  pop     rdi
0x1400131d3  retn
```
