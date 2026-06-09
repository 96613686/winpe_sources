# _lambda_d7e9df8ef86ff5b61d56833042a6c94b_::operator()

- ea: `0x180075ed0`
- end: `0x180076114`
- name: `_lambda_d7e9df8ef86ff5b61d56833042a6c94b_::operator()`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007476c`

## callees

- `0x180008b68`
- `0x180048954`
- `0x180075ed0`
- `0x180076aac`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075f4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007609c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800760e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075f4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007609c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800760e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall lambda_d7e9df8ef86ff5b61d56833042a6c94b_::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  struct IInspectable *v7; // rcx
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  struct IInspectable *v11; // rcx
  DataPackageCloner *v12; // rbx
  void **v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  struct IInspectable *v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  struct IInspectable *v19; // rcx
  __int64 v20; // rcx
  struct IInspectable *v21; // rcx
  int v22; // [rsp+20h] [rbp-20h]
  __int64 v23; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  struct IInspectable *v25; // [rsp+78h] [rbp+38h] BYREF
  __int64 v26; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  v26 = a3;
  v25 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, struct IInspectable **))(*(_QWORD *)a2 + 56LL))(a2, &v25);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v5,
      v22);
    v7 = v25;
    if ( v25 )
    {
      v25 = 0;
      ((void (__fastcall *)(struct IInspectable *))v7->lpVtbl->Release)(v7);
    }
    return v6;
  }
  string = 0;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = v9(a2, &string);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v10,
      v22);
    WindowsDeleteString(string);
    string = 0;
    v11 = v25;
    if ( v25 )
    {
      v25 = 0;
      ((void (__fastcall *)(struct IInspectable *))v11->lpVtbl->Release)(v11);
    }
    return v6;
  }
  v23 = 0;
  v12 = *(DataPackageCloner **)a1;
  v13 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v23);
  v14 = DataPackageCloner::CloneInspectable(v12, v25, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, v13);
  v6 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v14,
      v22);
    v15 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    WindowsDeleteString(string);
    string = 0;
    v16 = v25;
    if ( v25 )
    {
      v25 = 0;
      ((void (__fastcall *)(struct IInspectable *))v16->lpVtbl->Release)(v16);
    }
    return v6;
  }
  LOBYTE(v26) = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, __int64, __int64 *))(***(_QWORD ***)(a1 + 8) + 80LL))(
          **(_QWORD **)(a1 + 8),
          string,
          v23,
          &v26);
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v17,
      v22);
    v18 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    WindowsDeleteString(string);
    string = 0;
    v19 = v25;
    if ( v25 )
    {
      v25 = 0;
      ((void (__fastcall *)(struct IInspectable *))v19->lpVtbl->Release)(v19);
    }
    return v6;
  }
  v20 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  WindowsDeleteString(string);
  string = 0;
  v21 = v25;
  if ( v25 )
  {
    v25 = 0;
    ((void (__fastcall *)(struct IInspectable *))v21->lpVtbl->Release)(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x180075ed0  mov     [rsp-28h+arg_10], r8
0x180075ed5  push    rbp
0x180075ed6  push    rbx
0x180075ed7  push    rsi
0x180075ed8  push    rdi
0x180075ed9  push    r14
0x180075edb  mov     rbp, rsp
0x180075ede  sub     rsp, 40h
0x180075ee2  mov     rdi, rdx
0x180075ee5  mov     rsi, rcx
0x180075ee8  xor     r14d, r14d
0x180075eeb  mov     [rbp+arg_8], r14
0x180075eef  mov     rax, [rdx]
0x180075ef2  lea     rdx, [rbp+arg_8]
0x180075ef6  mov     rcx, rdi
0x180075ef9  mov     rax, [rax+38h]
0x180075efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f02  mov     ebx, eax
0x180075f04  test    eax, eax
0x180075f06  jns     short loc_180075F41
0x180075f08  mov     rcx, [rbp+28h]; this
0x180075f0c  mov     r9d, eax; char *
0x180075f0f  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180075f16  lea     edx, [r14+7Bh]; void *
0x180075f1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075f1f  nop
0x180075f20  mov     rcx, [rbp+arg_8]
0x180075f24  test    rcx, rcx
0x180075f27  jz      short loc_180075F3A
0x180075f29  mov     [rbp+arg_8], r14
0x180075f2d  mov     rax, [rcx]
0x180075f30  mov     rax, [rax+10h]
0x180075f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f39  nop
0x180075f3a  mov     eax, ebx
0x180075f3c  jmp     loc_180076109
0x180075f41  mov     [rbp+string], r14
0x180075f45  mov     rax, [rdi]
0x180075f48  mov     rbx, [rax+30h]
0x180075f4c  xor     ecx, ecx; string
0x180075f4e  call    cs:__imp_WindowsDeleteString
0x180075f54  mov     [rbp+string], r14
0x180075f58  lea     rdx, [rbp+string]
0x180075f5c  mov     rcx, rdi
0x180075f5f  mov     rax, rbx
0x180075f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f67  mov     ebx, eax
0x180075f69  test    eax, eax
0x180075f6b  jns     short loc_180075FB0
0x180075f6d  mov     rcx, [rbp+28h]; this
0x180075f71  mov     r9d, eax; char *
0x180075f74  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180075f7b  mov     edx, 7Eh ; '~'; void *
0x180075f80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075f85  nop
0x180075f86  mov     rcx, [rbp+string]; string
0x180075f8a  call    cs:__imp_WindowsDeleteString
0x180075f90  mov     [rbp+string], r14
0x180075f94  mov     rcx, [rbp+arg_8]
0x180075f98  test    rcx, rcx
0x180075f9b  jz      short loc_180075FAE
0x180075f9d  mov     [rbp+arg_8], r14
0x180075fa1  mov     rax, [rcx]
0x180075fa4  mov     rax, [rax+10h]
0x180075fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075fad  nop
0x180075fae  jmp     short loc_180075F3A
0x180075fb0  mov     [rbp+var_10], r14
0x180075fb4  mov     rbx, [rsi]
0x180075fb7  lea     rcx, [rbp+var_10]
0x180075fbb  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180075fc0  mov     r9, rax; void **
0x180075fc3  lea     r8, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x180075fca  mov     rdx, [rbp+arg_8]; struct IInspectable *
0x180075fce  mov     rcx, rbx; this
0x180075fd1  call    ?CloneInspectable@DataPackageCloner@@QEAAJPEAUIInspectable@@AEBU_GUID@@PEAPEAX@Z; DataPackageCloner::CloneInspectable(IInspectable *,_GUID const &,void * *)
0x180075fd6  mov     ebx, eax
0x180075fd8  test    eax, eax
0x180075fda  jns     short loc_18007603C
0x180075fdc  mov     rcx, [rbp+28h]; this
0x180075fe0  mov     r9d, eax; char *
0x180075fe3  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180075fea  mov     edx, 81h; void *
0x180075fef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075ff4  nop
0x180075ff5  mov     rcx, [rbp+var_10]
0x180075ff9  test    rcx, rcx
0x180075ffc  jz      short loc_18007600F
0x180075ffe  mov     [rbp+var_10], r14
0x180076002  mov     rax, [rcx]
0x180076005  mov     rax, [rax+10h]
0x180076009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007600e  nop
0x18007600f  mov     rcx, [rbp+string]; string
0x180076013  call    cs:__imp_WindowsDeleteString
0x180076019  mov     [rbp+string], r14
0x18007601d  mov     rcx, [rbp+arg_8]
0x180076021  test    rcx, rcx
0x180076024  jz      short loc_180076037
0x180076026  mov     [rbp+arg_8], r14
0x18007602a  mov     rax, [rcx]
0x18007602d  mov     rax, [rax+10h]
0x180076031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076036  nop
0x180076037  jmp     loc_180075F3A
0x18007603c  mov     byte ptr [rbp+arg_10], r14b
0x180076040  mov     rax, [rsi+8]
0x180076044  mov     rcx, [rax]
0x180076047  mov     rax, [rcx]
0x18007604a  lea     r9, [rbp+arg_10]
0x18007604e  mov     r8, [rbp+var_10]
0x180076052  mov     rdx, [rbp+string]
0x180076056  mov     rax, [rax+50h]
0x18007605a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007605f  mov     ebx, eax
0x180076061  test    eax, eax
0x180076063  jns     short loc_1800760C5
0x180076065  mov     rcx, [rbp+28h]; this
0x180076069  mov     r9d, eax; char *
0x18007606c  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180076073  mov     edx, 84h; void *
0x180076078  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007607d  nop
0x18007607e  mov     rcx, [rbp+var_10]
0x180076082  test    rcx, rcx
0x180076085  jz      short loc_180076098
0x180076087  mov     [rbp+var_10], r14
0x18007608b  mov     rax, [rcx]
0x18007608e  mov     rax, [rax+10h]
0x180076092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076097  nop
0x180076098  mov     rcx, [rbp+string]; string
0x18007609c  call    cs:__imp_WindowsDeleteString
0x1800760a2  mov     [rbp+string], r14
0x1800760a6  mov     rcx, [rbp+arg_8]
0x1800760aa  test    rcx, rcx
0x1800760ad  jz      short loc_1800760C0
0x1800760af  mov     [rbp+arg_8], r14
0x1800760b3  mov     rax, [rcx]
0x1800760b6  mov     rax, [rax+10h]
0x1800760ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760bf  nop
0x1800760c0  jmp     loc_180075F3A
0x1800760c5  mov     rcx, [rbp+var_10]
0x1800760c9  test    rcx, rcx
0x1800760cc  jz      short loc_1800760DF
0x1800760ce  mov     [rbp+var_10], r14
0x1800760d2  mov     rax, [rcx]
0x1800760d5  mov     rax, [rax+10h]
0x1800760d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760de  nop
0x1800760df  mov     rcx, [rbp+string]; string
0x1800760e3  call    cs:__imp_WindowsDeleteString
0x1800760e9  mov     [rbp+string], r14
0x1800760ed  mov     rcx, [rbp+arg_8]
0x1800760f1  test    rcx, rcx
0x1800760f4  jz      short loc_180076107
0x1800760f6  mov     [rbp+arg_8], r14
0x1800760fa  mov     rax, [rcx]
0x1800760fd  mov     rax, [rax+10h]
0x180076101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076106  nop
0x180076107  xor     eax, eax
0x180076109  add     rsp, 40h
0x18007610d  pop     r14
0x18007610f  pop     rdi
0x180076110  pop     rsi
0x180076111  pop     rbx
0x180076112  pop     rbp
0x180076113  retn
```
