# _anonymous_namespace_::SendWebViewUriRepEvent

- ea: `0x140013a5c`
- end: `0x140013b33`
- name: `_anonymous_namespace_::SendWebViewUriRepEvent`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003ca14`

## callees

- `0x140006d90`
- `0x140013a5c`
- `0x140013b3c`
- `0x1400184f0`
- `0x140039a6c`

## string_xrefs

- `0x140013a89`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x140013ad8`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`

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
  v6 = qword_140088718;
  if ( qword_140088718 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_140088718 + 2);
    v6 = qword_140088718;
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
0x140013a5c  mov     [rsp+arg_0], rbx
0x140013a61  push    rdi
0x140013a62  sub     rsp, 30h
0x140013a66  mov     rdi, rdx
0x140013a69  mov     [rsp+38h+arg_10], 0
0x140013a71  lea     rdx, [rsp+38h+arg_10]
0x140013a76  call    _anonymous_namespace___RetrievePidFromJSONString
0x140013a7b  mov     ebx, eax
0x140013a7d  test    eax, eax
0x140013a7f  jns     short loc_140013AA1
0x140013a81  mov     rcx, [rsp+38h]; this
0x140013a86  mov     r9d, eax; char *
0x140013a89  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140013a90  mov     edx, 1C4h; void *
0x140013a95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013a9a  mov     eax, ebx
0x140013a9c  jmp     loc_140013B27
0x140013aa1  mov     rbx, cs:qword_140088718
0x140013aa8  test    rbx, rbx
0x140013aab  jz      short loc_140013AB8
0x140013aad  lock inc dword ptr [rbx+8]
0x140013ab1  mov     rbx, cs:qword_140088718
0x140013ab8  mov     rcx, cs:?s_wtd_communicator@wtd_communicator@@0V?$shared_ptr@Vwtd_communicator@@@std@@A; std::shared_ptr<wtd_communicator> wtd_communicator::s_wtd_communicator
0x140013abf  mov     qword ptr [rsp+38h+var_18], rcx; int
0x140013ac4  mov     [rsp+38h+var_10], rbx
0x140013ac9  test    rcx, rcx
0x140013acc  jnz     short loc_140013AFE
0x140013ace  mov     edi, 8007139Fh
0x140013ad3  mov     edx, 1C8h; void *
0x140013ad8  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140013adf  mov     r9d, edi; char *
0x140013ae2  mov     rcx, [rsp+38h]; this
0x140013ae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013aec  nop
0x140013aed  test    rbx, rbx
0x140013af0  jz      short loc_140013AFA
0x140013af2  mov     rcx, rbx; this
0x140013af5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140013afa  mov     eax, edi
0x140013afc  jmp     short loc_140013B27
0x140013afe  mov     r8d, [rsp+38h+arg_10]
0x140013b03  mov     rdx, rdi
0x140013b06  call    ?SendSensorEvent@wtd_communicator@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wtd_communicator::SendSensorEvent(std::wstring const &,ulong)
0x140013b0b  mov     edi, eax
0x140013b0d  test    eax, eax
0x140013b0f  jns     short loc_140013B18
0x140013b11  mov     edx, 1C9h
0x140013b16  jmp     short loc_140013AD8
0x140013b18  test    rbx, rbx
0x140013b1b  jz      short loc_140013B25
0x140013b1d  mov     rcx, rbx; this
0x140013b20  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140013b25  xor     eax, eax
0x140013b27  mov     rbx, [rsp+38h+arg_0]
0x140013b2c  add     rsp, 30h
0x140013b30  pop     rdi
0x140013b31  retn
```
