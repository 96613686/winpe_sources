# _lambda_fe62db151725febec21c4848a637b25d_::operator()

- ea: `0x14002435c`
- end: `0x1400244d6`
- name: `_lambda_fe62db151725febec21c4848a637b25d_::operator()`
- size: `378`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001afcc`
- `0x1400337ec`

## callees

- `0x1400055ac`
- `0x1400061cc`
- `0x14002435c`
- `0x1400244dc`
- `0x140026c20`
- `0x14006a010`

## string_xrefs

- `0x1400243c2`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.cpp`
- `0x140024409`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.cpp`
- `0x140024450`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.cpp`

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
0x14002435c  mov     [rsp-18h+arg_0], rbx
0x140024361  mov     [rsp-18h+arg_18], rsi
0x140024366  push    rbp
0x140024367  push    rdi
0x140024368  push    r14
0x14002436a  mov     rbp, rsp
0x14002436d  sub     rsp, 60h
0x140024371  mov     rax, cs:__security_cookie
0x140024378  xor     rax, rsp
0x14002437b  mov     [rbp+var_10], rax
0x14002437f  mov     r14, r8
0x140024382  mov     rsi, rdx
0x140024385  mov     [rbp+var_38], rdx
0x140024389  mov     [rbp+var_30], r8
0x14002438d  mov     [rbp+var_18], 0
0x140024395  mov     rdi, [r8]
0x140024398  mov     rax, [rdi]
0x14002439b  mov     rbx, [rax+30h]
0x14002439f  lea     rcx, [rbp+var_18]
0x1400243a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400243a8  lea     rdx, [rbp+var_18]
0x1400243ac  mov     rcx, rdi
0x1400243af  mov     rax, rbx
0x1400243b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400243b7  mov     rcx, [rbp+18h]; this
0x1400243bb  test    eax, eax
0x1400243bd  jns     short loc_1400243D4
0x1400243bf  mov     r9d, eax; char *
0x1400243c2  lea     r8, aOnecoreAmcoreS_4; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400243c9  mov     edx, 86h; void *
0x1400243ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400243d4  mov     [rbp+var_20], 0
0x1400243dc  mov     rdi, [r14]
0x1400243df  mov     rax, [rdi]
0x1400243e2  mov     rbx, [rax+38h]
0x1400243e6  lea     rcx, [rbp+var_20]
0x1400243ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400243ef  lea     rdx, [rbp+var_20]
0x1400243f3  mov     rcx, rdi
0x1400243f6  mov     rax, rbx
0x1400243f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400243fe  mov     rcx, [rbp+18h]; this
0x140024402  test    eax, eax
0x140024404  jns     short loc_14002441B
0x140024406  mov     r9d, eax; char *
0x140024409  lea     r8, aOnecoreAmcoreS_4; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140024410  mov     edx, 89h; void *
0x140024415  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002441b  mov     [rbp+var_28], 0
0x140024423  mov     rdi, [r14]
0x140024426  mov     rax, [rdi]
0x140024429  mov     rbx, [rax+40h]
0x14002442d  lea     rcx, [rbp+var_28]
0x140024431  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140024436  lea     rdx, [rbp+var_28]
0x14002443a  mov     rcx, rdi
0x14002443d  mov     rax, rbx
0x140024440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024445  mov     rcx, [rbp+18h]; this
0x140024449  test    eax, eax
0x14002444b  jns     short loc_140024462
0x14002444d  mov     r9d, eax; char *
0x140024450  lea     r8, aOnecoreAmcoreS_4; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140024457  mov     edx, 8Ch; void *
0x14002445c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140024462  mov     rdx, [rbp+var_18]
0x140024466  mov     rcx, rsi
0x140024469  call    ??$marshal@UIRandomAccessStream@Streams@Storage@Windows@@@com@@YA?AV?$marshaled_ptr@UIRandomAccessStream@Streams@Storage@Windows@@@0@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; com::marshal<Windows::Storage::Streams::IRandomAccessStream>(Windows::Storage::Streams::IRandomAccessStream *)
0x14002446e  nop
0x14002446f  lea     rcx, [rsi+10h]
0x140024473  mov     rdx, [rbp+var_20]
0x140024477  call    ??$marshal@UIRandomAccessStream@Streams@Storage@Windows@@@com@@YA?AV?$marshaled_ptr@UIRandomAccessStream@Streams@Storage@Windows@@@0@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; com::marshal<Windows::Storage::Streams::IRandomAccessStream>(Windows::Storage::Streams::IRandomAccessStream *)
0x14002447c  nop
0x14002447d  lea     rcx, [rsi+20h]
0x140024481  mov     rdx, [rbp+var_28]
0x140024485  call    ??$marshal@UIRandomAccessStream@Streams@Storage@Windows@@@com@@YA?AV?$marshaled_ptr@UIRandomAccessStream@Streams@Storage@Windows@@@0@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; com::marshal<Windows::Storage::Streams::IRandomAccessStream>(Windows::Storage::Streams::IRandomAccessStream *)
0x14002448a  nop
0x14002448b  lea     rcx, [rbp+var_28]
0x14002448f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140024494  nop
0x140024495  lea     rcx, [rbp+var_20]
0x140024499  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14002449e  nop
0x14002449f  lea     rcx, [rbp+var_18]
0x1400244a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400244a8  nop
0x1400244a9  mov     rcx, r14
0x1400244ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400244b1  mov     rax, rsi
0x1400244b4  mov     rcx, [rbp+var_10]
0x1400244b8  xor     rcx, rsp; StackCookie
0x1400244bb  call    __security_check_cookie
0x1400244c0  lea     r11, [rsp+60h+var_s0]
0x1400244c5  mov     rbx, [r11+20h]
0x1400244c9  mov     rsi, [r11+38h]
0x1400244cd  mov     rsp, r11
0x1400244d0  pop     r14
0x1400244d2  pop     rdi
0x1400244d3  pop     rbp
0x1400244d4  retn
```
