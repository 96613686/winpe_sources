# wil::details::functor_wrapper_void__lambda_ab5e9adf3cb0abd65d116aaa87d17a75___::Run

- ea: `0x180025ae0`
- end: `0x180025bf3`
- name: `wil::details::functor_wrapper_void__lambda_ab5e9adf3cb0abd65d116aaa87d17a75___::Run`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180024180`

## callees

- `0x1800241b4`
- `0x180024878`
- `0x180025ae0`
- `0x180026538`
- `0x180033010`

## string_xrefs

- `0x180025bcc`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x180025be1`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall wil::details::functor_wrapper_void__lambda_ab5e9adf3cb0abd65d116aaa87d17a75___::Run(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rdi
  _QWORD *v4; // rax
  int v5; // eax
  DWORD v6; // edx
  int v7; // r8d
  __int64 v8; // rbx
  int v9; // eax
  __int64 v10; // rcx
  __int64 *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v18; // [rsp+48h] [rbp+28h] BYREF
  __int64 v19; // [rsp+50h] [rbp+30h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v4 = *(_QWORD **)(v3 + 8);
  v19 = 0;
  v5 =  Windows::Devices::Radios::IRadioStatics::`vcall'{48,{flat}}(*v4, &v19, a3);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x735,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v5,
      savedregs);
  v8 = v19;
  v18 = 0;
  v9 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>(
         v19,
         v6,
         v7);
  if ( v9 >= 0 )
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 64LL))(v8, &v18);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x71B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v9,
      savedregs);
  v10 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = *(__int64 **)v3;
  v12 = v18;
  v18 = 0;
  v13 = *v11;
  *v11 = v12;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return 0;
}

```

## disassembly

```asm
0x180025ae0  push    rbp
0x180025ae2  push    rbx
0x180025ae3  push    rdi; int
0x180025ae4  mov     rbp, rsp
0x180025ae7  sub     rsp, 20h
0x180025aeb  mov     [rbp+arg_0], 0
0x180025af2  mov     rdi, [rcx+8]
0x180025af6  mov     rax, [rdi+8]
0x180025afa  mov     [rbp+arg_10], 0
0x180025b02  lea     rdx, [rbp+arg_10]
0x180025b06  mov     rcx, [rax]
0x180025b09  call    ??_9IRadioStatics@Radios@Devices@Windows@@$BDA@AA; [thunk]: Windows::Devices::Radios::IRadioStatics::`vcall'{48,{flat}}
0x180025b0e  mov     rcx, [rbp+18h]; this
0x180025b12  test    eax, eax
0x180025b14  js      loc_180025BDE
0x180025b1a  mov     rbx, [rbp+arg_10]
0x180025b1e  mov     [rbp+arg_8], 0
0x180025b26  mov     [rbp+arg_0], 4
0x180025b2d  mov     rcx, rbx
0x180025b30  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180025b35  test    eax, eax
0x180025b37  js      short loc_180025B4D
0x180025b39  mov     rax, [rbx]
0x180025b3c  lea     rdx, [rbp+arg_8]
0x180025b40  mov     rcx, rbx
0x180025b43  mov     rax, [rax+40h]
0x180025b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b4c  nop
0x180025b4d  mov     rcx, [rbp+18h]; this
0x180025b51  test    eax, eax
0x180025b53  js      short loc_180025BC9
0x180025b55  mov     [rbp+arg_0], 2
0x180025b5c  mov     rcx, [rbp+arg_10]
0x180025b60  test    rcx, rcx
0x180025b63  jz      short loc_180025B7A
0x180025b65  mov     [rbp+arg_10], 0
0x180025b6d  mov     rax, [rcx]
0x180025b70  mov     rax, [rax+10h]
0x180025b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b79  nop
0x180025b7a  mov     rdx, [rdi]
0x180025b7d  mov     rax, [rbp+arg_8]
0x180025b81  mov     [rbp+arg_8], 0
0x180025b89  mov     rcx, [rdx]
0x180025b8c  mov     [rdx], rax
0x180025b8f  test    rcx, rcx
0x180025b92  jz      short loc_180025BA1
0x180025b94  mov     rax, [rcx]
0x180025b97  mov     rax, [rax+10h]
0x180025b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ba0  nop
0x180025ba1  mov     rcx, [rbp+arg_8]
0x180025ba5  test    rcx, rcx
0x180025ba8  jz      short loc_180025BBF
0x180025baa  mov     [rbp+arg_8], 0
0x180025bb2  mov     rax, [rcx]
0x180025bb5  mov     rax, [rax+10h]
0x180025bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bbe  nop
0x180025bbf  xor     eax, eax
0x180025bc1  add     rsp, 20h
0x180025bc5  pop     rdi
0x180025bc6  pop     rbx
0x180025bc7  pop     rbp
0x180025bc8  retn
0x180025bc9  mov     r9d, eax; char *
0x180025bcc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025bd3  mov     edx, 71Bh; void *
0x180025bd8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025bde  mov     r9d, eax; char *
0x180025be1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025be8  mov     edx, 735h; void *
0x180025bed  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
