# Windows::ApplicationModel::Activation::ToastActivationPlugin::CreateEventArgs(ushort const *,ushort const * *,ulong,IInspectable * *)

- ea: `0x18002e8b0`
- end: `0x18002e9b4`
- name: `?CreateEventArgs@ToastActivationPlugin@Activation@ApplicationModel@Windows@@UEAAJPEBGPEAPEBGKPEAPEAUIInspectable@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Activation::ToastActivationPlugin *__hidden this, const unsigned __int16 *, const unsigned __int16 **, unsigned int, struct IInspectable **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x180028bc4`
- `0x18002e7c4`
- `0x18002e8b0`
- `0x180032010`

## string_xrefs

- `0x18002e957`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Activation::ToastActivationPlugin::CreateEventArgs(
        Windows::ApplicationModel::Activation::ToastActivationPlugin *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        int a4,
        struct IInspectable **a5)
{
  struct IInspectable **v5; // rsi
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, GUID *, struct IInspectable ***); // rbx
  __int64 v11; // rdx
  __int64 v12; // rdx
  struct IInspectable **v14; // rax
  int v15[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  const unsigned __int16 **v17; // [rsp+60h] [rbp+30h] BYREF
  int v18; // [rsp+68h] [rbp+38h] BYREF

  v18 = a4;
  v17 = a3;
  v5 = a5;
  if ( !a5 || (a4 & 1) == 0 )
    return 2147942487LL;
  *a5 = 0;
  a5 = 0;
  *(_QWORD *)v15 = 0;
  Microsoft::WRL::ComPtr<ToastActivationEventArgs>::InternalRelease(v15, a2);
  v6 = Microsoft::WRL::Details::MakeAndInitialize<ToastActivationEventArgs,ToastActivationEventArgs,unsigned short const * * &,unsigned long &>(
         v15,
         &v17,
         &v18);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 50;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastactivationplugin.cpp",
      (const char *)(unsigned int)v6,
      v15[0]);
    Microsoft::WRL::ComPtr<ToastActivationEventArgs>::InternalRelease(v15, v12);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a5);
    return v7;
  }
  v9 = *(_QWORD *)v15;
  v10 = **(__int64 (__fastcall ***)(__int64, GUID *, struct IInspectable ***))(*(_QWORD *)v15 + 16LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a5);
  v6 = v10(v9 + 16, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &a5);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 51;
    goto LABEL_7;
  }
  v14 = a5;
  a5 = 0;
  *v5 = (struct IInspectable *)v14;
  Microsoft::WRL::ComPtr<ToastActivationEventArgs>::InternalRelease(v15, v11);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a5);
  return 0;
}

```

## disassembly

```asm
0x18002e8b0  mov     [rsp-18h+arg_0], rbx
0x18002e8b5  mov     [rsp-18h+arg_18], r9d
0x18002e8ba  mov     [rsp-18h+arg_10], r8
0x18002e8bf  push    rbp
0x18002e8c0  push    rsi
0x18002e8c1  push    rdi
0x18002e8c2  mov     rbp, rsp
0x18002e8c5  sub     rsp, 30h
0x18002e8c9  mov     rsi, [rbp+arg_20]
0x18002e8cd  test    rsi, rsi
0x18002e8d0  jz      loc_18002E9A2
0x18002e8d6  test    r9b, 1
0x18002e8da  jz      loc_18002E9A2
0x18002e8e0  mov     qword ptr [rsi], 0
0x18002e8e7  mov     [rbp+arg_20], 0
0x18002e8ef  mov     qword ptr [rbp+var_10], 0
0x18002e8f7  lea     rcx, [rbp+var_10]
0x18002e8fb  call    ?InternalRelease@?$ComPtr@VToastActivationEventArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ToastActivationEventArgs>::InternalRelease(void)
0x18002e900  lea     r8, [rbp+arg_18]
0x18002e904  lea     rdx, [rbp+arg_10]
0x18002e908  lea     rcx, [rbp+var_10]
0x18002e90c  call    ??$MakeAndInitialize@VToastActivationEventArgs@@V1@AEAPEAPEBGAEAK@Details@WRL@Microsoft@@YAJPEAPEAVToastActivationEventArgs@@AEAPEAPEBGAEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<ToastActivationEventArgs,ToastActivationEventArgs,ushort const * * &,ulong &>(ToastActivationEventArgs * *,ushort const * * &,ulong &)
0x18002e911  mov     ebx, eax
0x18002e913  test    eax, eax
0x18002e915  jns     short loc_18002E91E
0x18002e917  mov     edx, 32h ; '2'
0x18002e91c  jmp     short loc_18002E954
0x18002e91e  mov     rdi, qword ptr [rbp+var_10]
0x18002e922  mov     rax, [rdi+10h]
0x18002e926  mov     rbx, [rax]
0x18002e929  lea     rcx, [rbp+arg_20]
0x18002e92d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e932  lea     r8, [rbp+arg_20]
0x18002e936  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18002e93d  lea     rcx, [rdi+10h]
0x18002e941  mov     rax, rbx
0x18002e944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e949  mov     ebx, eax
0x18002e94b  test    eax, eax
0x18002e94d  jns     short loc_18002E97D
0x18002e94f  mov     edx, 33h ; '3'; void *
0x18002e954  mov     r9d, eax; char *
0x18002e957  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e95e  mov     rcx, [rbp+18h]; this
0x18002e962  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e967  lea     rcx, [rbp+var_10]
0x18002e96b  call    ?InternalRelease@?$ComPtr@VToastActivationEventArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ToastActivationEventArgs>::InternalRelease(void)
0x18002e970  lea     rcx, [rbp+arg_20]
0x18002e974  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e979  mov     eax, ebx
0x18002e97b  jmp     short loc_18002E9A7
0x18002e97d  mov     rax, [rbp+arg_20]
0x18002e981  mov     [rbp+arg_20], 0
0x18002e989  mov     [rsi], rax
0x18002e98c  lea     rcx, [rbp+var_10]
0x18002e990  call    ?InternalRelease@?$ComPtr@VToastActivationEventArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ToastActivationEventArgs>::InternalRelease(void)
0x18002e995  lea     rcx, [rbp+arg_20]
0x18002e999  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e99e  xor     eax, eax
0x18002e9a0  jmp     short loc_18002E9A7
0x18002e9a2  mov     eax, 80070057h
0x18002e9a7  mov     rbx, [rsp+30h+arg_0]
0x18002e9ac  add     rsp, 30h
0x18002e9b0  pop     rdi
0x18002e9b1  pop     rsi
0x18002e9b2  pop     rbp
0x18002e9b3  retn
```
