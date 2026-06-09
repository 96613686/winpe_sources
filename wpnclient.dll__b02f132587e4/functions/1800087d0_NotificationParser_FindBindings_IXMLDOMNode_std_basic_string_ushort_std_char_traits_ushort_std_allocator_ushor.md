# NotificationParser::FindBindings(IXMLDOMNode *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *)

- ea: `0x1800087d0`
- end: `0x1800088fe`
- name: `?FindBindings@NotificationParser@@AEAAXPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIXMLDOMNodeList@@@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018d90`

## callees

- `0x1800087d0`
- `0x180008910`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## string_xrefs

- `0x18000880f`: `//binding[starts-with(@template, '%s')]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NotificationParser::FindBindings(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  int v6; // eax
  __int64 (__fastcall *v7)(__int64, unsigned __int16 *, int *); // rsi
  __int64 v8; // rcx
  int v9; // eax
  __int64 result; // rax
  int v11[4]; // [rsp+20h] [rbp-248h] BYREF
  unsigned __int16 v12[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *(_QWORD *)v11 = 0;
  *a4 = 0;
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  v6 = StringCchPrintfW(v12, 0x104u, L"//binding[starts-with(@template, '%s')]", a3, *(_QWORD *)v11);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v6,
      v11[0]);
  v7 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, int *))(*(_QWORD *)a2 + 288LL);
  v8 = *(_QWORD *)v11;
  if ( *(_QWORD *)v11 )
  {
    *(_QWORD *)v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = v7(a2, v12, v11);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v9,
      v11[0]);
  result = *(_QWORD *)v11;
  if ( !*(_QWORD *)v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)0x80070490LL,
      0);
  *a4 = *(_QWORD *)v11;
  return result;
}

```

## disassembly

```asm
0x1800087d0  mov     [rsp+arg_0], rbx
0x1800087d5  push    rbp
0x1800087d6  push    rsi
0x1800087d7  push    rdi
0x1800087d8  sub     rsp, 250h
0x1800087df  mov     rax, cs:__security_cookie
0x1800087e6  xor     rax, rsp
0x1800087e9  mov     [rsp+268h+var_28], rax
0x1800087f1  mov     rbx, r9
0x1800087f4  mov     rdi, rdx
0x1800087f7  xor     ebp, ebp
0x1800087f9  mov     qword ptr [rsp+268h+var_248], rbp; int
0x1800087fe  mov     [r9], rbp
0x180008801  cmp     qword ptr [r8+18h], 7
0x180008806  ja      loc_1800088B4
0x18000880c  mov     r9, r8
0x18000880f  lea     r8, aBindingStartsW; "//binding[starts-with(@template, '%s')]"
0x180008816  mov     edx, 104h; unsigned __int64
0x18000881b  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180008820  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008825  mov     rcx, [rsp+268h]; this
0x18000882d  test    eax, eax
0x18000882f  js      loc_1800088BC
0x180008835  mov     rax, [rdi]
0x180008838  mov     rsi, [rax+120h]
0x18000883f  mov     rcx, qword ptr [rsp+268h+var_248]
0x180008844  test    rcx, rcx
0x180008847  jz      short loc_18000885B
0x180008849  mov     qword ptr [rsp+268h+var_248], rbp; int
0x18000884e  mov     rdx, [rcx]
0x180008851  mov     rax, [rdx+10h]
0x180008855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885a  nop
0x18000885b  lea     r8, [rsp+268h+var_248]
0x180008860  lea     rdx, [rsp+268h+var_238]
0x180008865  mov     rcx, rdi
0x180008868  mov     rax, rsi
0x18000886b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008870  mov     rcx, [rsp+268h]; this
0x180008878  test    eax, eax
0x18000887a  js      short loc_1800088D1
0x18000887c  mov     rcx, [rsp+268h]; this
0x180008884  mov     rax, qword ptr [rsp+268h+var_248]
0x180008889  test    rax, rax
0x18000888c  jz      short loc_1800088E6
0x18000888e  mov     [rbx], rax
0x180008891  mov     rcx, [rsp+268h+var_28]
0x180008899  xor     rcx, rsp; StackCookie
0x18000889c  call    __security_check_cookie
0x1800088a1  mov     rbx, [rsp+268h+arg_0]
0x1800088a9  add     rsp, 250h
0x1800088b0  pop     rdi
0x1800088b1  pop     rsi
0x1800088b2  pop     rbp
0x1800088b3  retn
0x1800088b4  mov     r8, [r8]
0x1800088b7  jmp     loc_18000880C
0x1800088bc  mov     r9d, eax; char *
0x1800088bf  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800088c6  mov     edx, 38Ah; void *
0x1800088cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800088d1  mov     r9d, eax; char *
0x1800088d4  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800088db  mov     edx, 38Dh; void *
0x1800088e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800088e6  mov     r9d, 80070490h; char *
0x1800088ec  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800088f3  mov     edx, 38Fh; void *
0x1800088f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
