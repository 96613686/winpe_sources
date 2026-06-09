# DoNtsKeyExchange(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,_SecHandle &,NtsForNtpInfoInternal &,std::vector<ushort,std::allocator<ushort>> const &)

- ea: `0x18005997c`
- end: `0x180059a79`
- name: `?DoNtsKeyExchange@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEAU_SecHandle@@AEAUNtsForNtpInfoInternal@@AEBV?$vector@GV?$allocator@G@std@@@std@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(__int64, struct _SecHandle *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054b50`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x180045abc`
- `0x18005997c`
- `0x18005a214`
- `0x18005a5a4`

## import_xrefs

- `SspiCli!QueryContextAttributesW` at `0x1800599bc`
- `SspiCli!QueryContextAttributesW` at `0x1800599bc`

## string_xrefs

- `0x180059a0c`: `onecore\ds\security\services\w32time\nts\ntske.cpp`
- `0x180059a42`: `onecore\ds\security\services\w32time\nts\ntske.cpp`

## pseudocode

```c
__int64 __fastcall DoNtsKeyExchange(__int64 a1, struct _SecHandle *a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  int v15; // [rsp+20h] [rbp-58h]
  __int128 pBuffer; // [rsp+28h] [rbp-50h] BYREF
  int v17; // [rsp+38h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    pBuffer = 0;
    v17 = 0;
    v8 = QueryContextAttributesW(a2, 4u, &pBuffer);
    if ( (v8 & 0x80000000) == 0 )
    {
      v11 = SendKERequest(a1, a2, &pBuffer, a4);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v13 = ReceiveKEResponse(a1, a2, &pBuffer, a3);
        v14 = v13;
        if ( v13 >= 0 )
        {
          result = v8;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x215,
            (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntske.cpp",
            (const char *)(unsigned int)v13,
            v15);
          result = v14;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x214,
          (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntske.cpp",
          (const char *)(unsigned int)v11,
          v15);
        result = v12;
      }
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"DoNtsKeyExchange: QueryContextAttributesW failed with: 0x%08X\n", v8);
      result = v8;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x218,
                           (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntske.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18005997c  push    rbx
0x18005997e  push    rsi
0x18005997f  push    rdi
0x180059980  push    r14
0x180059982  push    r15
0x180059984  sub     rsp, 50h
0x180059988  mov     rax, cs:__security_cookie
0x18005998f  xor     rax, rsp
0x180059992  mov     [rsp+78h+var_38], rax
0x180059997  mov     rdi, r9
0x18005999a  mov     r15, r8
0x18005999d  mov     rsi, rdx
0x1800599a0  mov     r14, rcx
0x1800599a3  xorps   xmm0, xmm0
0x1800599a6  xor     eax, eax
0x1800599a8  movups  [rsp+78h+pBuffer], xmm0
0x1800599ad  mov     [rsp+78h+var_40], eax
0x1800599b1  lea     r8, [rsp+78h+pBuffer]; pBuffer
0x1800599b6  lea     edx, [rax+4]; ulAttribute
0x1800599b9  mov     rcx, rsi; phContext
0x1800599bc  call    cs:__imp_QueryContextAttributesW
0x1800599c3  nop     dword ptr [rax+rax+00h]
0x1800599c8  mov     ebx, eax
0x1800599ca  test    eax, eax
0x1800599cc  jns     short loc_1800599EB
0x1800599ce  xor     ecx, ecx
0x1800599d0  call    FileLogAllowEntry
0x1800599d5  test    al, al
0x1800599d7  jz      short loc_1800599E7
0x1800599d9  mov     edx, ebx
0x1800599db  lea     rcx, aDontskeyexchan_0; "DoNtsKeyExchange: QueryContextAttribute"...
0x1800599e2  call    FileLogAdd
0x1800599e7  mov     eax, ebx
0x1800599e9  jmp     short loc_180059A5F
0x1800599eb  mov     r9, rdi
0x1800599ee  lea     r8, [rsp+78h+pBuffer]
0x1800599f3  mov     rdx, rsi
0x1800599f6  mov     rcx, r14
0x1800599f9  call    ?SendKERequest@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEAU_SecHandle@@AEBU_SecPkgContext_StreamSizes@@AEBV?$vector@GV?$allocator@G@std@@@std@@@Z; SendKERequest(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,_SecHandle &,_SecPkgContext_StreamSizes const &,std::vector<ushort> const &)
0x1800599fe  mov     edi, eax
0x180059a00  test    eax, eax
0x180059a02  jns     short loc_180059A21
0x180059a04  mov     rcx, [rsp+78h]; this
0x180059a09  mov     r9d, eax; char *
0x180059a0c  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\w32tim"...
0x180059a13  mov     edx, 214h; void *
0x180059a18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059a1d  mov     eax, edi
0x180059a1f  jmp     short loc_180059A5F
0x180059a21  mov     r9, r15
0x180059a24  lea     r8, [rsp+78h+pBuffer]
0x180059a29  mov     rdx, rsi
0x180059a2c  mov     rcx, r14
0x180059a2f  call    ?ReceiveKEResponse@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEAU_SecHandle@@AEBU_SecPkgContext_StreamSizes@@AEAUNtsForNtpInfoInternal@@@Z; ReceiveKEResponse(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,_SecHandle &,_SecPkgContext_StreamSizes const &,NtsForNtpInfoInternal &)
0x180059a34  mov     edi, eax
0x180059a36  test    eax, eax
0x180059a38  jns     short loc_180059A57
0x180059a3a  mov     rcx, [rsp+78h]; this
0x180059a3f  mov     r9d, eax; char *
0x180059a42  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\w32tim"...
0x180059a49  mov     edx, 215h; void *
0x180059a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059a53  mov     eax, edi
0x180059a55  jmp     short loc_180059A5F
0x180059a57  mov     eax, ebx
0x180059a59  jmp     short loc_180059A5F
0x180059a5b  mov     eax, [rsp+78h+var_58]
0x180059a5f  mov     rcx, [rsp+78h+var_38]
0x180059a64  xor     rcx, rsp; StackCookie
0x180059a67  call    __security_check_cookie
0x180059a6c  add     rsp, 50h
0x180059a70  pop     r15
0x180059a72  pop     r14
0x180059a74  pop     rdi
0x180059a75  pop     rsi
0x180059a76  pop     rbx
0x180059a77  retn
```
