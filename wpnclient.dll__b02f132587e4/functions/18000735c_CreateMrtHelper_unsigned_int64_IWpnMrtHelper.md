# CreateMrtHelper(unsigned __int64,IWpnMrtHelper * *)

- ea: `0x18000735c`
- end: `0x1800074bf`
- name: `?CreateMrtHelper@@YAJ_KPEAPEAUIWpnMrtHelper@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(unsigned __int64, struct IWpnMrtHelper **)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007280`
- `0x180008560`
- `0x18000a460`
- `0x18000b440`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x18000710c`
- `0x18000735c`
- `0x180015204`
- `0x180032010`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x1800073a5`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1800073a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateMrtHelper(__int64 a1, struct IWpnMrtHelper **a2)
{
  int InstanceAsUser; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD *); // rbx
  int v9; // eax
  int v10; // eax
  struct IWpnMrtHelper *v11; // rcx
  _QWORD v13[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  struct IWpnMrtHelper *v15; // [rsp+70h] [rbp+30h] BYREF
  __int64 v16; // [rsp+78h] [rbp+38h] BYREF

  v16 = 0;
  IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(&v16);
  InstanceAsUser = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1028, a1);
  v5 = InstanceAsUser;
  if ( InstanceAsUser >= 0 )
  {
    v13[0] = 0;
    v7 = v16;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v16 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v13);
    v9 = v8(v7, v13);
    v5 = v9;
    if ( v9 >= 0 )
    {
      v15 = 0;
      v10 = Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::As<IWpnMrtHelper>(v13, &v15);
      v5 = v10;
      if ( v10 >= 0 )
      {
        v11 = v15;
        if ( v15 )
        {
          (*(void (__fastcall **)(struct IWpnMrtHelper *))(*(_QWORD *)v15 + 8LL))(v15);
          v11 = v15;
        }
        *a2 = v11;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        v5 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x25B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
          (const char *)(unsigned int)v10,
          (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x258,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v9,
        (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)InstanceAsUser,
      (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
    v6 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000735c  mov     [rsp-18h+arg_0], rbx
0x180007361  push    rbp
0x180007362  push    rsi
0x180007363  push    rdi
0x180007364  mov     rbp, rsp
0x180007367  sub     rsp, 40h
0x18000736b  mov     rsi, rdx
0x18000736e  mov     rbx, rcx
0x180007371  mov     [rbp+arg_18], 0
0x180007379  lea     rcx, [rbp+arg_18]
0x18000737d  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnPlatform>>)
0x180007382  mov     [rsp+40h+var_18], rax
0x180007387  lea     rax, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x18000738e  mov     qword ptr [rsp+40h+var_20], rax; int
0x180007393  mov     r9, rbx
0x180007396  xor     edx, edx
0x180007398  mov     r8d, 404h
0x18000739e  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x1800073a5  call    cs:__imp_CoCreateInstanceAsUser
0x1800073ab  mov     ebx, eax
0x1800073ad  test    eax, eax
0x1800073af  jns     short loc_1800073ED
0x1800073b1  mov     rcx, [rbp+18h]; this
0x1800073b5  mov     r9d, eax; char *
0x1800073b8  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800073bf  mov     edx, 255h; void *
0x1800073c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073c9  nop
0x1800073ca  mov     rcx, [rbp+arg_18]
0x1800073ce  test    rcx, rcx
0x1800073d1  jz      short loc_1800073E8
0x1800073d3  mov     [rbp+arg_18], 0
0x1800073db  mov     rax, [rcx]
0x1800073de  mov     rax, [rax+10h]
0x1800073e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073e7  nop
0x1800073e8  jmp     loc_1800074B0
0x1800073ed  mov     [rbp+var_10], 0
0x1800073f5  mov     rdi, [rbp+arg_18]
0x1800073f9  mov     rax, [rdi]
0x1800073fc  mov     rbx, [rax+20h]
0x180007400  lea     rcx, [rbp+var_10]
0x180007404  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007409  lea     rdx, [rbp+var_10]
0x18000740d  mov     rcx, rdi
0x180007410  mov     rax, rbx
0x180007413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007418  mov     ebx, eax
0x18000741a  test    eax, eax
0x18000741c  jns     short loc_180007438
0x18000741e  mov     rcx, [rbp+18h]; this
0x180007422  mov     r9d, eax; char *
0x180007425  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000742c  mov     edx, 258h; void *
0x180007431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007436  jmp     short loc_18000749D
0x180007438  mov     [rbp+arg_10], 0
0x180007440  lea     rdx, [rbp+arg_10]
0x180007444  lea     rcx, [rbp+var_10]
0x180007448  call    ??$As@UIWpnMrtHelper@@@?$ComPtr@UIWpnPresentationEndpoint@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnMrtHelper@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::As<IWpnMrtHelper>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnMrtHelper>>)
0x18000744d  mov     ebx, eax
0x18000744f  test    eax, eax
0x180007451  jns     short loc_180007476
0x180007453  mov     rcx, [rbp+18h]; this
0x180007457  mov     r9d, eax; char *
0x18000745a  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007461  mov     edx, 25Bh; void *
0x180007466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000746b  lea     rcx, [rbp+arg_10]
0x18000746f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007474  jmp     short loc_18000749D
0x180007476  mov     rcx, [rbp+arg_10]
0x18000747a  test    rcx, rcx
0x18000747d  jz      short loc_18000748F
0x18000747f  mov     rax, [rcx]
0x180007482  mov     rax, [rax+8]
0x180007486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000748b  mov     rcx, [rbp+arg_10]
0x18000748f  mov     [rsi], rcx
0x180007492  lea     rcx, [rbp+arg_10]
0x180007496  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000749b  xor     ebx, ebx
0x18000749d  lea     rcx, [rbp+var_10]
0x1800074a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800074a6  nop
0x1800074a7  lea     rcx, [rbp+arg_18]
0x1800074ab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800074b0  mov     eax, ebx
0x1800074b2  mov     rbx, [rsp+40h+arg_0]
0x1800074b7  add     rsp, 40h
0x1800074bb  pop     rdi
0x1800074bc  pop     rsi
0x1800074bd  pop     rbp
0x1800074be  retn
```
