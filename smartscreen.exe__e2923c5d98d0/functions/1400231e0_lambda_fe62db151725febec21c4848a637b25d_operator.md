# _lambda_fe62db151725febec21c4848a637b25d_::operator()

- ea: `0x1400231e0`
- end: `0x140023359`
- name: `_lambda_fe62db151725febec21c4848a637b25d_::operator()`
- size: `377`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001a1dc`
- `0x14003237c`

## callees

- `0x140005260`
- `0x140005e4c`
- `0x1400231e0`
- `0x140023360`
- `0x140025aa0`
- `0x140068010`

## string_xrefs

- `0x140023246`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.cpp`
- `0x14002328d`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.cpp`
- `0x1400232d4`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall lambda_fe62db151725febec21c4848a637b25d_::operator()(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  int v15; // [rsp+20h] [rbp-40h]
  __int64 v16; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+40h] [rbp-20h] BYREF
  __int64 v18; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v18 = 0;
  v5 = *a3;
  v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a3 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v7 = v6(v5, &v18);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\apprep\\src\\com_api.cpp",
      (const char *)(unsigned int)v7,
      v15);
  v17 = 0;
  v8 = *a3;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a3 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v10 = v9(v8, &v17);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\apprep\\src\\com_api.cpp",
      (const char *)(unsigned int)v10,
      v15);
  v16 = 0;
  v11 = *a3;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a3 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  v13 = v12(v11, &v16);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\apprep\\src\\com_api.cpp",
      (const char *)(unsigned int)v13,
      v15);
  com::marshal<Windows::Storage::Streams::IRandomAccessStream>(a2, v18);
  com::marshal<Windows::Storage::Streams::IRandomAccessStream>(a2 + 16, v17);
  com::marshal<Windows::Storage::Streams::IRandomAccessStream>(a2 + 32, v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
  return a2;
}

```

## disassembly

```asm
0x1400231e0  mov     [rsp-18h+arg_0], rbx
0x1400231e5  mov     [rsp-18h+arg_18], rsi
0x1400231ea  push    rbp
0x1400231eb  push    rdi
0x1400231ec  push    r14
0x1400231ee  mov     rbp, rsp
0x1400231f1  sub     rsp, 60h
0x1400231f5  mov     rax, cs:__security_cookie
0x1400231fc  xor     rax, rsp
0x1400231ff  mov     [rbp+var_10], rax
0x140023203  mov     r14, r8
0x140023206  mov     rsi, rdx
0x140023209  mov     [rbp+var_38], rdx
0x14002320d  mov     [rbp+var_30], r8
0x140023211  mov     [rbp+var_18], 0
0x140023219  mov     rdi, [r8]
0x14002321c  mov     rax, [rdi]
0x14002321f  mov     rbx, [rax+30h]
0x140023223  lea     rcx, [rbp+var_18]
0x140023227  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14002322c  lea     rdx, [rbp+var_18]
0x140023230  mov     rcx, rdi
0x140023233  mov     rax, rbx
0x140023236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002323b  mov     rcx, [rbp+18h]; this
0x14002323f  test    eax, eax
0x140023241  jns     short loc_140023258
0x140023243  mov     r9d, eax; char *
0x140023246  lea     r8, aOnecoreAmcoreS_4; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14002324d  mov     edx, 86h; void *
0x140023252  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140023258  mov     [rbp+var_20], 0
0x140023260  mov     rdi, [r14]
0x140023263  mov     rax, [rdi]
0x140023266  mov     rbx, [rax+38h]
0x14002326a  lea     rcx, [rbp+var_20]
0x14002326e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140023273  lea     rdx, [rbp+var_20]
0x140023277  mov     rcx, rdi
0x14002327a  mov     rax, rbx
0x14002327d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023282  mov     rcx, [rbp+18h]; this
0x140023286  test    eax, eax
0x140023288  jns     short loc_14002329F
0x14002328a  mov     r9d, eax; char *
0x14002328d  lea     r8, aOnecoreAmcoreS_4; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140023294  mov     edx, 89h; void *
0x140023299  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002329f  mov     [rbp+var_28], 0
0x1400232a7  mov     rdi, [r14]
0x1400232aa  mov     rax, [rdi]
0x1400232ad  mov     rbx, [rax+40h]
0x1400232b1  lea     rcx, [rbp+var_28]
0x1400232b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400232ba  lea     rdx, [rbp+var_28]
0x1400232be  mov     rcx, rdi
0x1400232c1  mov     rax, rbx
0x1400232c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400232c9  mov     rcx, [rbp+18h]; this
0x1400232cd  test    eax, eax
0x1400232cf  jns     short loc_1400232E6
0x1400232d1  mov     r9d, eax; char *
0x1400232d4  lea     r8, aOnecoreAmcoreS_4; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400232db  mov     edx, 8Ch; void *
0x1400232e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400232e6  mov     rdx, [rbp+var_18]
0x1400232ea  mov     rcx, rsi
0x1400232ed  call    ??$marshal@UIRandomAccessStream@Streams@Storage@Windows@@@com@@YA?AV?$marshaled_ptr@UIRandomAccessStream@Streams@Storage@Windows@@@0@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; com::marshal<Windows::Storage::Streams::IRandomAccessStream>(Windows::Storage::Streams::IRandomAccessStream *)
0x1400232f2  nop
0x1400232f3  lea     rcx, [rsi+10h]
0x1400232f7  mov     rdx, [rbp+var_20]
0x1400232fb  call    ??$marshal@UIRandomAccessStream@Streams@Storage@Windows@@@com@@YA?AV?$marshaled_ptr@UIRandomAccessStream@Streams@Storage@Windows@@@0@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; com::marshal<Windows::Storage::Streams::IRandomAccessStream>(Windows::Storage::Streams::IRandomAccessStream *)
0x140023300  nop
0x140023301  lea     rcx, [rsi+20h]
0x140023305  mov     rdx, [rbp+var_28]
0x140023309  call    ??$marshal@UIRandomAccessStream@Streams@Storage@Windows@@@com@@YA?AV?$marshaled_ptr@UIRandomAccessStream@Streams@Storage@Windows@@@0@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; com::marshal<Windows::Storage::Streams::IRandomAccessStream>(Windows::Storage::Streams::IRandomAccessStream *)
0x14002330e  nop
0x14002330f  lea     rcx, [rbp+var_28]
0x140023313  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140023318  nop
0x140023319  lea     rcx, [rbp+var_20]
0x14002331d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140023322  nop
0x140023323  lea     rcx, [rbp+var_18]
0x140023327  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14002332c  nop
0x14002332d  mov     rcx, r14
0x140023330  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140023335  mov     rax, rsi
0x140023338  mov     rcx, [rbp+var_10]
0x14002333c  xor     rcx, rsp; StackCookie
0x14002333f  call    __security_check_cookie
0x140023344  lea     r11, [rsp+60h+var_s0]
0x140023349  mov     rbx, [r11+20h]
0x14002334d  mov     rsi, [r11+38h]
0x140023351  mov     rsp, r11
0x140023354  pop     r14
0x140023356  pop     rdi
0x140023357  pop     rbp
0x140023358  retn
```
