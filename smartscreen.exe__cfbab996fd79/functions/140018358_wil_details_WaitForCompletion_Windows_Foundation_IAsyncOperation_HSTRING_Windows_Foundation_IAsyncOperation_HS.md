# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x140018358`
- end: `0x1400184e9`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001802c`

## callees

- `0x1400061cc`
- `0x140007138`
- `0x140018358`
- `0x1400184f0`
- `0x140026c20`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140018424`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140018424`

## string_xrefs

- `0x1400183a2`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x14001843b`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

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
0x140018358  mov     [rsp-8+arg_8], rbx
0x14001835d  mov     [rsp-8+arg_10], rdi
0x140018362  push    rbp
0x140018363  mov     rbp, rsp
0x140018366  sub     rsp, 60h
0x14001836a  mov     rax, cs:__security_cookie
0x140018371  xor     rax, rsp
0x140018374  mov     [rbp+var_8], rax
0x140018378  mov     rdi, rcx
0x14001837b  mov     [rbp+var_30], 0
0x140018383  lea     rcx, [rbp+var_30]
0x140018387  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001838c  lea     rcx, [rbp+var_30]
0x140018390  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x140018395  mov     ebx, eax
0x140018397  test    eax, eax
0x140018399  jns     short loc_1400183D7
0x14001839b  mov     rcx, [rbp+8]; this
0x14001839f  mov     r9d, eax; char *
0x1400183a2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400183a9  mov     edx, 648h; void *
0x1400183ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400183b3  nop
0x1400183b4  mov     rcx, [rbp+var_30]
0x1400183b8  test    rcx, rcx
0x1400183bb  jz      short loc_1400183D2
0x1400183bd  mov     [rbp+var_30], 0
0x1400183c5  mov     rax, [rcx]
0x1400183c8  mov     rax, [rax+10h]
0x1400183cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400183d1  nop
0x1400183d2  jmp     loc_1400184C8
0x1400183d7  mov     rax, [rdi]
0x1400183da  mov     rdx, [rbp+var_30]
0x1400183de  mov     rcx, rdi
0x1400183e1  mov     rax, [rax+30h]
0x1400183e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400183ea  mov     ebx, eax
0x1400183ec  test    eax, eax
0x1400183ee  jns     short loc_1400183F7
0x1400183f0  mov     edx, 649h
0x1400183f5  jmp     short loc_14001843B
0x1400183f7  mov     rax, [rbp+var_30]
0x1400183fb  mov     rcx, [rax+38h]
0x1400183ff  mov     [rbp+pHandles], rcx
0x140018403  mov     [rbp+dwindex], 0
0x14001840a  lea     rax, [rbp+dwindex]
0x14001840e  mov     qword ptr [rsp+60h+lpdwindex], rax; int
0x140018413  lea     r9, [rbp+pHandles]; pHandles
0x140018417  mov     r8d, 1; cHandles
0x14001841d  or      edx, 0FFFFFFFFh; dwTimeout
0x140018420  lea     ecx, [r8+7]; dwFlags
0x140018424  call    cs:__imp_CoWaitForMultipleHandles
0x14001842b  nop     dword ptr [rax+rax+00h]
0x140018430  mov     ebx, eax
0x140018432  test    eax, eax
0x140018434  jns     short loc_140018450
0x140018436  mov     edx, 655h; void *
0x14001843b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140018442  mov     r9d, eax; char *
0x140018445  mov     rcx, [rbp+8]; this
0x140018449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001844e  jmp     short loc_1400184BF
0x140018450  mov     rax, [rbp+var_30]
0x140018454  mov     edx, [rax+30h]
0x140018457  cmp     edx, 1
0x14001845a  jz      short loc_1400184BD
0x14001845c  mov     [rbp+var_20], 0
0x140018464  mov     rax, [rdi]
0x140018467  mov     rbx, [rax]
0x14001846a  lea     rcx, [rbp+var_20]
0x14001846e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140018473  lea     r8, [rbp+var_20]
0x140018477  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14001847e  mov     rcx, rdi
0x140018481  mov     rax, rbx
0x140018484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018489  mov     ebx, eax
0x14001848b  test    eax, eax
0x14001848d  js      short loc_1400184B2
0x14001848f  mov     [rbp+var_28], 8000FFFFh
0x140018496  mov     rcx, [rbp+var_20]
0x14001849a  mov     rax, [rcx]
0x14001849d  lea     rdx, [rbp+var_28]
0x1400184a1  mov     rax, [rax+40h]
0x1400184a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400184aa  mov     ebx, eax
0x1400184ac  test    eax, eax
0x1400184ae  cmovns  ebx, [rbp+var_28]
0x1400184b2  lea     rcx, [rbp+var_20]
0x1400184b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400184bb  jmp     short loc_1400184BF
0x1400184bd  xor     ebx, ebx
0x1400184bf  lea     rcx, [rbp+var_30]
0x1400184c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400184c8  mov     eax, ebx
0x1400184ca  mov     rcx, [rbp+var_8]
0x1400184ce  xor     rcx, rsp; StackCookie
0x1400184d1  call    __security_check_cookie
0x1400184d6  lea     r11, [rsp+60h+var_s0]
0x1400184db  mov     rbx, [r11+18h]
0x1400184df  mov     rdi, [r11+20h]
0x1400184e3  mov     rsp, r11
0x1400184e6  pop     rbp
0x1400184e7  retn
```
