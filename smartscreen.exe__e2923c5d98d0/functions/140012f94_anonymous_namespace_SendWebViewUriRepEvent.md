# _anonymous_namespace_::SendWebViewUriRepEvent

- ea: `0x140012f94`
- end: `0x14001306a`
- name: `_anonymous_namespace_::SendWebViewUriRepEvent`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003b390`

## callees

- `0x140006a00`
- `0x140012f94`
- `0x140013070`
- `0x140016ce4`
- `0x1400384d8`

## string_xrefs

- `0x140012fc1`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x140013010`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::SendWebViewUriRepEvent(_QWORD *a1, __int64 *a2)
{
  int PidFromJSONString; // eax
  unsigned int v4; // ebx
  std::_Ref_count_base *v6; // rbx
  int v7; // edi
  __int64 v8; // rdx
  int v9; // [rsp+20h] [rbp-18h]
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = 0;
  PidFromJSONString = anonymous_namespace_::RetrievePidFromJSONString(a1, (int *)&v12);
  v4 = PidFromJSONString;
  if ( PidFromJSONString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\com_api.cpp",
      (const char *)(unsigned int)PidFromJSONString,
      v9);
    return v4;
  }
  v6 = qword_140086728;
  if ( qword_140086728 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_140086728 + 2);
    v6 = qword_140086728;
  }
  v10 = wtd_communicator::s_wtd_communicator;
  if ( !*(_QWORD *)&wtd_communicator::s_wtd_communicator )
  {
    v7 = -2147019873;
    v8 = 456;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\com_api.cpp",
      (const char *)(unsigned int)v7,
      v10);
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
    return (unsigned int)v7;
  }
  v7 = wtd_communicator::SendSensorEvent(*(__int64 *)&wtd_communicator::s_wtd_communicator, a2, v12);
  if ( v7 < 0 )
  {
    v8 = 457;
    goto LABEL_7;
  }
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  return 0;
}

```

## disassembly

```asm
0x140012f94  mov     [rsp+arg_0], rbx
0x140012f99  push    rdi
0x140012f9a  sub     rsp, 30h
0x140012f9e  mov     rdi, rdx
0x140012fa1  mov     [rsp+38h+arg_10], 0
0x140012fa9  lea     rdx, [rsp+38h+arg_10]
0x140012fae  call    _anonymous_namespace___RetrievePidFromJSONString
0x140012fb3  mov     ebx, eax
0x140012fb5  test    eax, eax
0x140012fb7  jns     short loc_140012FD9
0x140012fb9  mov     rcx, [rsp+38h]; this
0x140012fbe  mov     r9d, eax; char *
0x140012fc1  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140012fc8  mov     edx, 1C4h; void *
0x140012fcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012fd2  mov     eax, ebx
0x140012fd4  jmp     loc_14001305F
0x140012fd9  mov     rbx, cs:qword_140086728
0x140012fe0  test    rbx, rbx
0x140012fe3  jz      short loc_140012FF0
0x140012fe5  lock inc dword ptr [rbx+8]
0x140012fe9  mov     rbx, cs:qword_140086728
0x140012ff0  mov     rcx, cs:?s_wtd_communicator@wtd_communicator@@0V?$shared_ptr@Vwtd_communicator@@@std@@A; std::shared_ptr<wtd_communicator> wtd_communicator::s_wtd_communicator
0x140012ff7  mov     qword ptr [rsp+38h+var_18], rcx; int
0x140012ffc  mov     [rsp+38h+var_10], rbx
0x140013001  test    rcx, rcx
0x140013004  jnz     short loc_140013036
0x140013006  mov     edi, 8007139Fh
0x14001300b  mov     edx, 1C8h; void *
0x140013010  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140013017  mov     r9d, edi; char *
0x14001301a  mov     rcx, [rsp+38h]; this
0x14001301f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013024  nop
0x140013025  test    rbx, rbx
0x140013028  jz      short loc_140013032
0x14001302a  mov     rcx, rbx; this
0x14001302d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140013032  mov     eax, edi
0x140013034  jmp     short loc_14001305F
0x140013036  mov     r8d, [rsp+38h+arg_10]
0x14001303b  mov     rdx, rdi
0x14001303e  call    ?SendSensorEvent@wtd_communicator@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wtd_communicator::SendSensorEvent(std::wstring const &,ulong)
0x140013043  mov     edi, eax
0x140013045  test    eax, eax
0x140013047  jns     short loc_140013050
0x140013049  mov     edx, 1C9h
0x14001304e  jmp     short loc_140013010
0x140013050  test    rbx, rbx
0x140013053  jz      short loc_14001305D
0x140013055  mov     rcx, rbx; this
0x140013058  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001305d  xor     eax, eax
0x14001305f  mov     rbx, [rsp+38h+arg_0]
0x140013064  add     rsp, 30h
0x140013068  pop     rdi
0x140013069  retn
```
