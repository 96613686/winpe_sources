# XmlGetNodeText(IXMLDOMNode *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x140010704`
- end: `0x140010856`
- name: `?XmlGetNodeText@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `338`
- prototype: ``
- caller_count: `7`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fc50`
- `0x1400104f8`
- `0x140010c90`
- `0x140010f08`
- `0x14001117c`
- `0x140011f60`
- `0x1400124fc`

## callees

- `0x140010450`
- `0x140010704`
- `0x14001085c`
- `0x140011570`
- `0x14001950c`
- `0x140021b00`
- `0x140022cec`
- `0x140027744`
- `0x140031810`
- `0x140034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall XmlGetNodeText(_QWORD *a1, __int64 a2, _OWORD *a3)
{
  signed int Node; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64); // rbx
  __int64 v8; // rax
  const wchar_t *Src; // rax
  const char *v11; // [rsp+20h] [rbp-59h]
  __int64 v12; // [rsp+40h] [rbp-39h] BYREF
  int v13; // [rsp+48h] [rbp-31h]
  _QWORD *v14; // [rsp+50h] [rbp-29h]
  _BYTE pExceptionObject[40]; // [rsp+58h] [rbp-21h] BYREF
  wchar_t *v16[2]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 v17; // [rsp+98h] [rbp+1Fh]

  v14 = a1;
  *a1 = 0;
  v13 = 1;
  v12 = 0;
  *(_OWORD *)v16 = *a3;
  Node = XmlTryGetNode(a2, v16, &v12);
  if ( !Node )
  {
    v6 = v12;
    v7 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 208LL);
    v8 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(a1);
    Node = v7(v6, v8);
  }
  if ( Node < 0 )
  {
    std::wstring::wstring(v16, a3);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids,
        (unsigned int)Node);
    }
    Src = (const wchar_t *)v16;
    if ( v17 > 7 )
      Src = v16[0];
    EvtException::EvtException((EvtException *)pExceptionObject, Node, 0, 0, v11, 209, 0x21u, Src);
    throw (EvtException *)pExceptionObject;
  }
  if ( v12 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v12);
  return a1;
}

```

## disassembly

```asm
0x140010704  push    rbp
0x140010706  push    rbx
0x140010707  push    rsi
0x140010708  push    rdi
0x140010709  push    r14
0x14001070b  lea     rbp, [rsp-37h]
0x140010710  sub     rsp, 0B0h
0x140010717  mov     rax, cs:__security_cookie
0x14001071e  xor     rax, rsp
0x140010721  mov     [rbp+57h+var_30], rax
0x140010725  mov     r14, r8
0x140010728  mov     rax, rdx
0x14001072b  mov     rsi, rcx
0x14001072e  mov     [rbp+57h+var_80], rcx
0x140010732  mov     [rbp+57h+var_88], 0
0x140010739  mov     qword ptr [rcx], 0
0x140010740  mov     [rbp+57h+var_88], 1
0x140010747  mov     [rbp+57h+var_90], 0
0x14001074f  movaps  xmm0, xmmword ptr [r8]
0x140010753  movdqa  xmmword ptr [rbp+57h+var_50], xmm0
0x140010758  lea     r8, [rbp+57h+var_90]
0x14001075c  lea     rdx, [rbp+57h+var_50]
0x140010760  mov     rcx, rax
0x140010763  call    XmlTryGetNode
0x140010768  mov     ebx, eax
0x14001076a  test    eax, eax
0x14001076c  jnz     short loc_140010794
0x14001076e  mov     rdi, [rbp+57h+var_90]
0x140010772  mov     rax, [rdi]
0x140010775  mov     rbx, [rax+0D0h]
0x14001077c  mov     rcx, rsi
0x14001077f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(void)
0x140010784  mov     rdx, rax
0x140010787  mov     rcx, rdi
0x14001078a  mov     rax, rbx
0x14001078d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010792  mov     ebx, eax
0x140010794  test    ebx, ebx
0x140010796  jns     loc_140010828
0x14001079c  mov     rdx, r14
0x14001079f  lea     rcx, [rbp+57h+var_50]
0x1400107a3  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x1400107a8  nop
0x1400107a9  lea     rax, WPP_GLOBAL_Control
0x1400107b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400107b7  cmp     rcx, rax
0x1400107ba  jz      short loc_1400107E3
0x1400107bc  test    dword ptr [rcx+1Ch], 400000h
0x1400107c3  jz      short loc_1400107E3
0x1400107c5  cmp     byte ptr [rcx+19h], 2
0x1400107c9  jb      short loc_1400107E3
0x1400107cb  mov     edx, 17h
0x1400107d0  mov     r9d, ebx
0x1400107d3  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x1400107da  mov     rcx, [rcx+10h]
0x1400107de  call    WPP_SF_d
0x1400107e3  lea     rax, [rbp+57h+var_50]
0x1400107e7  cmp     [rbp+57h+var_38], 7
0x1400107ec  cmova   rax, [rbp+57h+var_50]
0x1400107f1  mov     [rsp+0D0h+Src], rax; Src
0x1400107f6  mov     [rsp+0D0h+var_A0], 21h ; '!'; unsigned int
0x1400107fe  mov     [rsp+0D0h+var_A8], 0D1h; int
0x140010806  xor     r9d, r9d; unsigned int
0x140010809  xor     r8d, r8d; unsigned int
0x14001080c  mov     edx, ebx; unsigned int
0x14001080e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140010812  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140010817  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001081e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140010822  call    _CxxThrowException_0
0x140010828  cmp     [rbp+57h+var_90], 0
0x14001082d  jz      short loc_140010838
0x14001082f  lea     rcx, [rbp+57h+var_90]
0x140010833  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140010838  mov     rax, rsi
0x14001083b  mov     rcx, [rbp+57h+var_30]
0x14001083f  xor     rcx, rsp; StackCookie
0x140010842  call    __security_check_cookie
0x140010847  add     rsp, 0B0h
0x14001084e  pop     r14
0x140010850  pop     rdi
0x140010851  pop     rsi
0x140010852  pop     rbx
0x140010853  pop     rbp
0x140010854  retn
```
