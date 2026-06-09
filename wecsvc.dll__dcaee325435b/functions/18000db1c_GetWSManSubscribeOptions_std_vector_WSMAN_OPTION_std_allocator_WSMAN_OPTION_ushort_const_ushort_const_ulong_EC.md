# GetWSManSubscribeOptions(std::vector<_WSMAN_OPTION,std::allocator<_WSMAN_OPTION>> &,ushort const *,ushort const *,ulong,_EC_SUBSCRIPTION_CONTENT_FORMAT,bool)

- ea: `0x18000db1c`
- end: `0x18000dc46`
- name: `?GetWSManSubscribeOptions@@YAXAEAV?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@PEBG1KW4_EC_SUBSCRIPTION_CONTENT_FORMAT@@_N@Z`
- size: `298`
- prototype: `const wchar_t *__fastcall(__int64, const wchar_t *, _WORD *, char, int, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009a10`
- `0x18000c724`

## callees

- `0x18000db1c`
- `0x180011148`

## string_xrefs

- `0x18000dbcd`: `ReadExistingEvents`
- `0x18000dbec`: `http://schemas.microsoft.com/wbem/wsman/1/windows/EventLog`
- `0x18000db56`: `Compression`

## pseudocode

```c
const wchar_t *__fastcall GetWSManSubscribeOptions(__int64 a1, const wchar_t *a2, _WORD *a3, char a4, int a5, char a6)
{
  const wchar_t *result; // rax
  const wchar_t *v10; // [rsp+20h] [rbp-20h] BYREF
  const wchar_t *v11; // [rsp+28h] [rbp-18h]
  __int64 v12; // [rsp+30h] [rbp-10h]

  v11 = a2;
  v10 = L"SubscriptionName";
  v12 = 0;
  std::vector<_WSMAN_OPTION>::push_back(a1, &v10);
  if ( a4 < 0 )
  {
    LODWORD(v12) = 0;
    v10 = L"Compression";
    v11 = L"SLDC";
    std::vector<_WSMAN_OPTION>::push_back(a1, &v10);
    v11 = 0;
    v10 = L"CDATA";
    LODWORD(v12) = 0;
    std::vector<_WSMAN_OPTION>::push_back(a1, &v10);
  }
  if ( a5 == 2 )
  {
    LODWORD(v12) = 0;
    v10 = L"ContentFormat";
    v11 = L"RenderedText";
    std::vector<_WSMAN_OPTION>::push_back(a1, &v10);
  }
  if ( a6 )
  {
    v11 = 0;
    v10 = L"ReadExistingEvents";
    LODWORD(v12) = 0;
    std::vector<_WSMAN_OPTION>::push_back(a1, &v10);
  }
  for ( result = L"http://schemas.microsoft.com/wbem/wsman/1/windows/EventLog"; *a3 && *a3 == *result; ++result )
    ++a3;
  if ( !*result && (!*a3 || *a3 == 63) )
  {
    v11 = 0;
    v10 = L"IgnoreChannelError";
    LODWORD(v12) = 0;
    return (const wchar_t *)std::vector<_WSMAN_OPTION>::push_back(a1, &v10);
  }
  return result;
}

```

## disassembly

```asm
0x18000db1c  push    rbp
0x18000db1e  push    rbx
0x18000db1f  push    rsi
0x18000db20  push    rdi
0x18000db21  push    r14
0x18000db23  mov     rbp, rsp
0x18000db26  sub     rsp, 40h
0x18000db2a  lea     rax, aSubscriptionna; "SubscriptionName"
0x18000db31  mov     [rbp+var_18], rdx
0x18000db35  xor     r14d, r14d
0x18000db38  mov     [rbp+var_20], rax
0x18000db3c  lea     rdx, [rbp+var_20]
0x18000db40  mov     [rbp+var_10], r14
0x18000db44  mov     ebx, r9d
0x18000db47  mov     rdi, r8
0x18000db4a  mov     rsi, rcx
0x18000db4d  call    ?push_back@?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAAXAEBU_WSMAN_OPTION@@@Z; std::vector<_WSMAN_OPTION>::push_back(_WSMAN_OPTION const &)
0x18000db52  test    bl, bl
0x18000db54  jns     short loc_18000DB9B
0x18000db56  lea     rax, aCompression; "Compression"
0x18000db5d  mov     dword ptr [rbp+var_10], r14d
0x18000db61  mov     [rbp+var_20], rax
0x18000db65  lea     rdx, [rbp+var_20]
0x18000db69  lea     rax, aSldc; "SLDC"
0x18000db70  mov     rcx, rsi
0x18000db73  mov     [rbp+var_18], rax
0x18000db77  call    ?push_back@?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAAXAEBU_WSMAN_OPTION@@@Z; std::vector<_WSMAN_OPTION>::push_back(_WSMAN_OPTION const &)
0x18000db7c  lea     rax, aCdata; "CDATA"
0x18000db83  mov     [rbp+var_18], r14
0x18000db87  lea     rdx, [rbp+var_20]
0x18000db8b  mov     [rbp+var_20], rax
0x18000db8f  mov     rcx, rsi
0x18000db92  mov     dword ptr [rbp+var_10], r14d
0x18000db96  call    ?push_back@?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAAXAEBU_WSMAN_OPTION@@@Z; std::vector<_WSMAN_OPTION>::push_back(_WSMAN_OPTION const &)
0x18000db9b  cmp     [rbp+arg_20], 2
0x18000db9f  jnz     short loc_18000DBC7
0x18000dba1  lea     rax, aContentformat; "ContentFormat"
0x18000dba8  mov     dword ptr [rbp+var_10], r14d
0x18000dbac  mov     [rbp+var_20], rax
0x18000dbb0  lea     rdx, [rbp+var_20]
0x18000dbb4  lea     rax, aRenderedtext; "RenderedText"
0x18000dbbb  mov     rcx, rsi
0x18000dbbe  mov     [rbp+var_18], rax
0x18000dbc2  call    ?push_back@?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAAXAEBU_WSMAN_OPTION@@@Z; std::vector<_WSMAN_OPTION>::push_back(_WSMAN_OPTION const &)
0x18000dbc7  cmp     [rbp+arg_28], r14b
0x18000dbcb  jz      short loc_18000DBEC
0x18000dbcd  lea     rax, aReadexistingev; "ReadExistingEvents"
0x18000dbd4  mov     [rbp+var_18], r14
0x18000dbd8  lea     rdx, [rbp+var_20]
0x18000dbdc  mov     [rbp+var_20], rax
0x18000dbe0  mov     rcx, rsi
0x18000dbe3  mov     dword ptr [rbp+var_10], r14d
0x18000dbe7  call    ?push_back@?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAAXAEBU_WSMAN_OPTION@@@Z; std::vector<_WSMAN_OPTION>::push_back(_WSMAN_OPTION const &)
0x18000dbec  lea     rax, aHttpSchemasMic_0; "http://schemas.microsoft.com/wbem/wsman"...
0x18000dbf3  jmp     short loc_18000DC02
0x18000dbf5  cmp     cx, [rax]
0x18000dbf8  jnz     short loc_18000DC0A
0x18000dbfa  add     rdi, 2
0x18000dbfe  add     rax, 2
0x18000dc02  movzx   ecx, word ptr [rdi]
0x18000dc05  test    cx, cx
0x18000dc08  jnz     short loc_18000DBF5
0x18000dc0a  cmp     [rax], r14w
0x18000dc0e  jnz     short loc_18000DC3B
0x18000dc10  cmp     [rdi], r14w
0x18000dc14  jz      short loc_18000DC1C
0x18000dc16  cmp     word ptr [rdi], 3Fh ; '?'
0x18000dc1a  jnz     short loc_18000DC3B
0x18000dc1c  lea     rax, aIgnorechannele; "IgnoreChannelError"
0x18000dc23  mov     [rbp+var_18], r14
0x18000dc27  lea     rdx, [rbp+var_20]
0x18000dc2b  mov     [rbp+var_20], rax
0x18000dc2f  mov     rcx, rsi
0x18000dc32  mov     dword ptr [rbp+var_10], r14d
0x18000dc36  call    ?push_back@?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAAXAEBU_WSMAN_OPTION@@@Z; std::vector<_WSMAN_OPTION>::push_back(_WSMAN_OPTION const &)
0x18000dc3b  add     rsp, 40h
0x18000dc3f  pop     r14
0x18000dc41  pop     rdi
0x18000dc42  pop     rsi
0x18000dc43  pop     rbx
0x18000dc44  pop     rbp
0x18000dc45  retn
```
