# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x140016b54`
- end: `0x140016cde`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140016830`

## callees

- `0x140005e4c`
- `0x140006d88`
- `0x140016b54`
- `0x140016ce4`
- `0x140025aa0`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140016c20`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140016c20`

## string_xrefs

- `0x140016b9e`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x140016c31`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *))
{
  int v2; // eax
  int v3; // ebx
  __int64 v4; // rcx
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  int lpdwindex; // [rsp+20h] [rbp-40h]
  __int64 v10; // [rsp+30h] [rbp-30h] BYREF
  int v11; // [rsp+38h] [rbp-28h] BYREF
  __int64 v12; // [rsp+40h] [rbp-20h] BYREF
  DWORD dwindex; // [rsp+48h] [rbp-18h] BYREF
  HANDLE pHandles; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v10 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  v2 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v10);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v10);
    v3 = v5;
    if ( v5 >= 0 )
    {
      pHandles = *(HANDLE *)(v10 + 56);
      dwindex = 0;
      v5 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
      v3 = v5;
      if ( v5 >= 0 )
      {
        if ( *(_DWORD *)(v10 + 48) == 1 )
        {
          v3 = 0;
        }
        else
        {
          v12 = 0;
          v7 = **a1;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
          v3 = v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v12);
          if ( v3 >= 0 )
          {
            v11 = -2147418113;
            v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 64LL))(v12, &v11);
            if ( v3 >= 0 )
              v3 = v11;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
        }
        goto LABEL_16;
      }
      v6 = 1621;
    }
    else
    {
      v6 = 1609;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v5,
      lpdwindex);
LABEL_16:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    return (unsigned int)v3;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x648,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
    (const char *)(unsigned int)v2,
    lpdwindex);
  v4 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140016b54  mov     [rsp-8+arg_8], rbx
0x140016b59  mov     [rsp-8+arg_10], rdi
0x140016b5e  push    rbp
0x140016b5f  mov     rbp, rsp
0x140016b62  sub     rsp, 60h
0x140016b66  mov     rax, cs:__security_cookie
0x140016b6d  xor     rax, rsp
0x140016b70  mov     [rbp+var_8], rax
0x140016b74  mov     rdi, rcx
0x140016b77  mov     [rbp+var_30], 0
0x140016b7f  lea     rcx, [rbp+var_30]
0x140016b83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140016b88  lea     rcx, [rbp+var_30]
0x140016b8c  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x140016b91  mov     ebx, eax
0x140016b93  test    eax, eax
0x140016b95  jns     short loc_140016BD3
0x140016b97  mov     rcx, [rbp+8]; this
0x140016b9b  mov     r9d, eax; char *
0x140016b9e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140016ba5  mov     edx, 648h; void *
0x140016baa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016baf  nop
0x140016bb0  mov     rcx, [rbp+var_30]
0x140016bb4  test    rcx, rcx
0x140016bb7  jz      short loc_140016BCE
0x140016bb9  mov     [rbp+var_30], 0
0x140016bc1  mov     rax, [rcx]
0x140016bc4  mov     rax, [rax+10h]
0x140016bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016bcd  nop
0x140016bce  jmp     loc_140016CBE
0x140016bd3  mov     rax, [rdi]
0x140016bd6  mov     rdx, [rbp+var_30]
0x140016bda  mov     rcx, rdi
0x140016bdd  mov     rax, [rax+30h]
0x140016be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016be6  mov     ebx, eax
0x140016be8  test    eax, eax
0x140016bea  jns     short loc_140016BF3
0x140016bec  mov     edx, 649h
0x140016bf1  jmp     short loc_140016C31
0x140016bf3  mov     rax, [rbp+var_30]
0x140016bf7  mov     rcx, [rax+38h]
0x140016bfb  mov     [rbp+pHandles], rcx
0x140016bff  mov     [rbp+dwindex], 0
0x140016c06  lea     rax, [rbp+dwindex]
0x140016c0a  mov     qword ptr [rsp+60h+lpdwindex], rax; int
0x140016c0f  lea     r9, [rbp+pHandles]; pHandles
0x140016c13  mov     r8d, 1; cHandles
0x140016c19  or      edx, 0FFFFFFFFh; dwTimeout
0x140016c1c  lea     ecx, [r8+7]; dwFlags
0x140016c20  call    cs:__imp_CoWaitForMultipleHandles
0x140016c26  mov     ebx, eax
0x140016c28  test    eax, eax
0x140016c2a  jns     short loc_140016C46
0x140016c2c  mov     edx, 655h; void *
0x140016c31  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140016c38  mov     r9d, eax; char *
0x140016c3b  mov     rcx, [rbp+8]; this
0x140016c3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016c44  jmp     short loc_140016CB5
0x140016c46  mov     rax, [rbp+var_30]
0x140016c4a  mov     edx, [rax+30h]
0x140016c4d  cmp     edx, 1
0x140016c50  jz      short loc_140016CB3
0x140016c52  mov     [rbp+var_20], 0
0x140016c5a  mov     rax, [rdi]
0x140016c5d  mov     rbx, [rax]
0x140016c60  lea     rcx, [rbp+var_20]
0x140016c64  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140016c69  lea     r8, [rbp+var_20]
0x140016c6d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140016c74  mov     rcx, rdi
0x140016c77  mov     rax, rbx
0x140016c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016c7f  mov     ebx, eax
0x140016c81  test    eax, eax
0x140016c83  js      short loc_140016CA8
0x140016c85  mov     [rbp+var_28], 8000FFFFh
0x140016c8c  mov     rcx, [rbp+var_20]
0x140016c90  mov     rax, [rcx]
0x140016c93  lea     rdx, [rbp+var_28]
0x140016c97  mov     rax, [rax+40h]
0x140016c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016ca0  mov     ebx, eax
0x140016ca2  test    eax, eax
0x140016ca4  cmovns  ebx, [rbp+var_28]
0x140016ca8  lea     rcx, [rbp+var_20]
0x140016cac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140016cb1  jmp     short loc_140016CB5
0x140016cb3  xor     ebx, ebx
0x140016cb5  lea     rcx, [rbp+var_30]
0x140016cb9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140016cbe  mov     eax, ebx
0x140016cc0  mov     rcx, [rbp+var_8]
0x140016cc4  xor     rcx, rsp; StackCookie
0x140016cc7  call    __security_check_cookie
0x140016ccc  lea     r11, [rsp+60h+var_s0]
0x140016cd1  mov     rbx, [r11+18h]
0x140016cd5  mov     rdi, [r11+20h]
0x140016cd9  mov     rsp, r11
0x140016cdc  pop     rbp
0x140016cdd  retn
```
