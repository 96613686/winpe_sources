# CGraphicsDeviceManager::CheckDXGIAdapter(bool *)

- ea: `0x1800508d0`
- end: `0x180050d89`
- name: `?CheckDXGIAdapter@CGraphicsDeviceManager@@IEAAJPEA_N@Z`
- size: `1209`
- prototype: `__int64 __fastcall(CGraphicsDeviceManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050844`

## callees

- `0x1800029dc`
- `0x1800508a0`
- `0x1800508d0`
- `0x180050d90`
- `0x180052df0`
- `0x180081a68`
- `0x180095130`
- `0x180095b4c`
- `0x1800ea010`

## import_xrefs

- `dxgi!CreateDXGIFactory1` at `0x180050c8b`
- `dxgi!CreateDXGIFactory1` at `0x180050c8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CGraphicsDeviceManager::CheckDXGIAdapter(CGraphicsDeviceManager *this, bool *a2, __int64 a3)
{
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 (__fastcall *v7)(__int64, GUID *, __int64); // r9
  __int64 v8; // r10
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v12; // r8
  __int64 v13; // rax
  int (__fastcall **v14)(__int64, GUID *, __int64); // rdx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rax
  int (__fastcall **v20)(__int64, GUID *, __int64); // r9
  __int64 v21; // r10
  void *v22; // rdx
  __int64 *v23; // rcx
  __int64 v24; // rbx
  char v25; // si
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  void **v32; // rax
  HRESULT DXGIFactory1; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rax
  int (__fastcall *v38)(__int64, __int64, GUID *, __int64); // r10
  __int64 v39; // r11
  int v40; // [rsp+20h] [rbp-E0h]
  __int64 v41; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v42; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v43; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v44; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v45; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v47[96]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v48[296]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+1E8h] [rbp+E8h]
  _BYTE v50[296]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v51; // [rsp+318h] [rbp+218h]
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  if ( a2 )
    *a2 = 0;
  v43 = 0;
  v5 = *(_QWORD *)(**((_QWORD **)this + 5) + 48LL);
  v43 = 0;
  v6 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
         &v43,
         a2,
         a3,
         v5);
  v9 = v7(v8, &GUID_770aae78_f26f_4dba_a829_253c83d1b387, v6);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
      (const char *)(unsigned int)v9,
      v40);
    if ( v43 )
      (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
    return v10;
  }
  if ( (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 312LL))(*((_QWORD *)this + 8)) >= 0 )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v43 + 104LL))(v43) )
      goto LABEL_20;
    memset_0(v48, 0, 0x130u);
    v28 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 5) + 64LL))(*((_QWORD *)this + 5), v48);
    v10 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
        (const char *)(unsigned int)v28,
        v40);
    }
    else
    {
      v44 = 0;
      v32 = (void **)winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                       &v44,
                       v29,
                       v30,
                       v31);
      DXGIFactory1 = CreateDXGIFactory1(&GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a, v32);
      v10 = DXGIFactory1;
      if ( DXGIFactory1 >= 0 )
      {
        v45 = 0;
        v37 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                &v45,
                v34,
                v35,
                v36);
        if ( v38(v39, v49, &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0, v37) >= 0 )
        {
          v25 = 1;
          v42 = 0;
          v26 = *v44;
          v42 = 0;
          if ( (*(int (__fastcall **)(_QWORD *, _QWORD, __int64 *))(v26 + 56))(v44, 0, &v42) < 0
            || (memset_0(v50, 0, 0x130u), (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v42 + 64LL))(v42, v50) < 0)
            || v51 != v49 )
          {
            v41 = 0;
            v46 = 0;
            memset_0(v47, 0, sizeof(v47));
            v27 = *v45;
            v41 = 0;
            if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64 *))(v27 + 56))(v45, 0, &v41) < 0
              || (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v41 + 56LL))(v41, v47) < 0 )
            {
              v25 = 0;
            }
            wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v46);
            wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v41);
          }
          if ( v42 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          if ( v25 )
          {
            v41 = 0;
            v42 = 0;
            v13 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                    &v42,
                    *v44,
                    v12,
                    v44);
            if ( (*v14)(v15, &GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8, v13) >= 0 )
            {
              v18 = v41;
              v41 = 0;
              if ( v18 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
              v19 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                      &v41,
                      v16,
                      v17,
                      *v43);
              if ( (*v20)(v21, &GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8, v19) >= 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 248LL))(v41, *((unsigned int *)this + 28));
                *((_DWORD *)this + 28) = 0;
                wil::details::ResetEvent(*((wil::details **)this + 10), v22);
                (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v42 + 240LL))(
                  v42,
                  *((_QWORD *)this + 10),
                  (char *)this + 112);
                v23 = v45;
                v24 = *((_QWORD *)this + 5);
                *((_QWORD *)this + 5) = v45;
                if ( v23 )
                  (*(void (__fastcall **)(__int64 *))(*v23 + 8))(v23);
                if ( v24 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              }
            }
            if ( v41 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
            if ( v42 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          }
        }
        else
        {
          v25 = 0;
        }
        if ( v45 )
          (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
        if ( v44 )
          (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
        if ( !v25 )
          goto LABEL_5;
LABEL_20:
        if ( a2 )
          *a2 = 1;
        goto LABEL_6;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x123,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
        (const char *)(unsigned int)DXGIFactory1,
        v40);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v44);
    }
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v43);
    return v10;
  }
LABEL_5:
  CGraphicsDeviceManager::HandleGraphicsDeviceLost(this);
LABEL_6:
  if ( v43 )
    (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
  return 0;
}

```

## disassembly

```asm
0x1800508d0  mov     [rsp-8+arg_10], rbx
0x1800508d5  push    rbp
0x1800508d6  push    rsi
0x1800508d7  push    rdi
0x1800508d8  push    r14
0x1800508da  push    r15
0x1800508dc  lea     rbp, [rsp-230h]
0x1800508e4  sub     rsp, 330h
0x1800508eb  mov     rax, cs:__security_cookie
0x1800508f2  xor     rax, rsp
0x1800508f5  mov     [rbp+250h+var_30], rax
0x1800508fc  mov     rdi, rdx
0x1800508ff  mov     r14, rcx
0x180050902  xor     r15d, r15d
0x180050905  test    rdx, rdx
0x180050908  jz      short loc_18005090D
0x18005090a  mov     [rdx], r15b
0x18005090d  mov     [rsp+350h+var_310], r15
0x180050912  mov     r10, [rcx+28h]
0x180050916  mov     rax, [r10]
0x180050919  mov     r9, [rax+30h]
0x18005091d  mov     [rsp+350h+var_310], r15
0x180050922  lea     rcx, [rsp+350h+var_310]
0x180050927  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18005092c  mov     r8, rax
0x18005092f  lea     rdx, _GUID_770aae78_f26f_4dba_a829_253c83d1b387
0x180050936  mov     rcx, r10
0x180050939  mov     rax, r9
0x18005093c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050941  mov     ebx, eax
0x180050943  test    eax, eax
0x180050945  js      short loc_1800509AA
0x180050947  mov     rcx, [r14+40h]
0x18005094b  mov     rax, [rcx]
0x18005094e  mov     rax, [rax+138h]
0x180050955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005095a  test    eax, eax
0x18005095c  jns     loc_180050C2A
0x180050962  mov     rcx, r14; this
0x180050965  call    ?HandleGraphicsDeviceLost@CGraphicsDeviceManager@@IEAAXXZ; CGraphicsDeviceManager::HandleGraphicsDeviceLost(void)
0x18005096a  nop
0x18005096b  mov     rcx, [rsp+350h+var_310]
0x180050970  test    rcx, rcx
0x180050973  jz      short loc_180050982
0x180050975  mov     rax, [rcx]
0x180050978  mov     rax, [rax+10h]
0x18005097c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050981  nop
0x180050982  xor     eax, eax
0x180050984  mov     rcx, [rbp+250h+var_30]
0x18005098b  xor     rcx, rsp; StackCookie
0x18005098e  call    __security_check_cookie
0x180050993  mov     rbx, [rsp+350h+arg_10]
0x18005099b  add     rsp, 330h
0x1800509a2  pop     r15
0x1800509a4  pop     r14
0x1800509a6  pop     rdi
0x1800509a7  pop     rsi
0x1800509a8  pop     rbp
0x1800509a9  retn
0x1800509aa  mov     rcx, [rbp+258h]; this
0x1800509b1  mov     r9d, ebx; char *
0x1800509b4  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x1800509bb  mov     edx, 118h; void *
0x1800509c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800509c5  nop
0x1800509c6  mov     rcx, [rsp+350h+var_310]
0x1800509cb  test    rcx, rcx
0x1800509ce  jz      short loc_1800509DD
0x1800509d0  mov     rax, [rcx]
0x1800509d3  mov     rax, [rax+10h]
0x1800509d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509dc  nop
0x1800509dd  mov     eax, ebx
0x1800509df  jmp     short loc_180050984
0x1800509e1  mov     rcx, [rsp+350h+var_318]
0x1800509e6  test    rcx, rcx
0x1800509e9  jz      short loc_1800509F8
0x1800509eb  mov     rax, [rcx]
0x1800509ee  mov     rax, [rax+10h]
0x1800509f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509f7  nop
0x1800509f8  test    sil, sil
0x1800509fb  jnz     short loc_180050A45
0x1800509fd  mov     rcx, [rsp+350h+var_300]
0x180050a02  test    rcx, rcx
0x180050a05  jz      short loc_180050A14
0x180050a07  mov     rax, [rcx]
0x180050a0a  mov     rax, [rax+10h]
0x180050a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a13  nop
0x180050a14  mov     rcx, [rsp+350h+var_308]
0x180050a19  test    rcx, rcx
0x180050a1c  jz      short loc_180050A2B
0x180050a1e  mov     rax, [rcx]
0x180050a21  mov     rax, [rax+10h]
0x180050a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a2a  nop
0x180050a2b  test    sil, sil
0x180050a2e  jz      loc_180050962
0x180050a34  test    rdi, rdi
0x180050a37  jz      loc_18005096B
0x180050a3d  mov     byte ptr [rdi], 1
0x180050a40  jmp     loc_18005096B
0x180050a45  mov     [rsp+350h+var_320], r15
0x180050a4a  mov     [rsp+350h+var_318], r15
0x180050a4f  mov     r9, [rsp+350h+var_308]
0x180050a54  mov     rdx, [r9]
0x180050a57  lea     rcx, [rsp+350h+var_318]
0x180050a5c  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x180050a61  mov     r8, rax
0x180050a64  mov     rax, [rdx]
0x180050a67  lea     rdx, _GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8
0x180050a6e  mov     rcx, r9
0x180050a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a76  test    eax, eax
0x180050a78  js      loc_180050B28
0x180050a7e  mov     rcx, [rsp+350h+var_320]
0x180050a83  mov     [rsp+350h+var_320], r15
0x180050a88  test    rcx, rcx
0x180050a8b  jnz     loc_180050D66
0x180050a91  mov     r10, [rsp+350h+var_310]
0x180050a96  mov     r9, [r10]
0x180050a99  lea     rcx, [rsp+350h+var_320]
0x180050a9e  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x180050aa3  mov     r8, rax
0x180050aa6  lea     rdx, _GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8
0x180050aad  mov     rcx, r10
0x180050ab0  mov     rax, [r9]
0x180050ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ab8  test    eax, eax
0x180050aba  js      short loc_180050B28
0x180050abc  mov     rcx, [rsp+350h+var_320]
0x180050ac1  lea     rbx, [r14+70h]
0x180050ac5  mov     rax, [rcx]
0x180050ac8  mov     edx, [rbx]
0x180050aca  mov     rax, [rax+0F8h]
0x180050ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ad6  mov     [rbx], r15d
0x180050ad9  mov     rcx, [r14+50h]; this
0x180050add  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x180050ae2  mov     rcx, [rsp+350h+var_318]
0x180050ae7  mov     rax, [rcx]
0x180050aea  mov     r8, rbx
0x180050aed  mov     rdx, [r14+50h]
0x180050af1  mov     rax, [rax+0F0h]
0x180050af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050afd  mov     rcx, [rsp+350h+var_300]
0x180050b02  mov     rbx, [r14+28h]
0x180050b06  mov     [r14+28h], rcx
0x180050b0a  test    rcx, rcx
0x180050b0d  jnz     loc_180050D77
0x180050b13  test    rbx, rbx
0x180050b16  jz      short loc_180050B28
0x180050b18  mov     rax, [rbx]
0x180050b1b  mov     rcx, rbx
0x180050b1e  mov     rax, [rax+10h]
0x180050b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b27  nop
0x180050b28  mov     rcx, [rsp+350h+var_320]
0x180050b2d  test    rcx, rcx
0x180050b30  jz      short loc_180050B3F
0x180050b32  mov     rax, [rcx]
0x180050b35  mov     rax, [rax+10h]
0x180050b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b3e  nop
0x180050b3f  mov     rcx, [rsp+350h+var_318]
0x180050b44  test    rcx, rcx
0x180050b47  jz      short loc_180050B56
0x180050b49  mov     rax, [rcx]
0x180050b4c  mov     rax, [rax+10h]
0x180050b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b55  nop
0x180050b56  jmp     loc_1800509FD
0x180050b5b  mov     sil, 1
0x180050b5e  mov     [rsp+350h+var_318], r15
0x180050b63  mov     rcx, [rsp+350h+var_308]
0x180050b68  mov     rax, [rcx]
0x180050b6b  mov     [rsp+350h+var_318], r15
0x180050b70  lea     r8, [rsp+350h+var_318]
0x180050b75  xor     edx, edx
0x180050b77  mov     rax, [rax+38h]
0x180050b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b80  test    eax, eax
0x180050b82  js      short loc_180050BB8
0x180050b84  xor     edx, edx; Val
0x180050b86  mov     r8d, 130h; Size
0x180050b8c  lea     rcx, [rbp+250h+var_160]; void *
0x180050b93  call    memset_0
0x180050b98  mov     rcx, [rsp+350h+var_318]
0x180050b9d  mov     rax, [rcx]
0x180050ba0  lea     rdx, [rbp+250h+var_160]
0x180050ba7  mov     rax, [rax+40h]
0x180050bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bb0  test    eax, eax
0x180050bb2  jns     loc_180050CEA
0x180050bb8  mov     [rsp+350h+var_320], r15
0x180050bbd  mov     [rsp+350h+var_2F8], r15
0x180050bc2  xor     edx, edx; Val
0x180050bc4  lea     r8d, [rdx+60h]; Size
0x180050bc8  lea     rcx, [rsp+350h+var_2F0]; void *
0x180050bcd  call    memset_0
0x180050bd2  mov     rcx, [rsp+350h+var_300]
0x180050bd7  mov     rax, [rcx]
0x180050bda  mov     [rsp+350h+var_320], r15
0x180050bdf  lea     r8, [rsp+350h+var_320]
0x180050be4  xor     edx, edx
0x180050be6  mov     rax, [rax+38h]
0x180050bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bef  test    eax, eax
0x180050bf1  js      short loc_180050C0D
0x180050bf3  mov     rcx, [rsp+350h+var_320]
0x180050bf8  mov     rax, [rcx]
0x180050bfb  lea     rdx, [rsp+350h+var_2F0]
0x180050c00  mov     rax, [rax+38h]
0x180050c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c09  test    eax, eax
0x180050c0b  jns     short loc_180050C10
0x180050c0d  mov     sil, r15b
0x180050c10  lea     rcx, [rsp+350h+var_2F8]
0x180050c15  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x180050c1a  nop
0x180050c1b  lea     rcx, [rsp+350h+var_320]
0x180050c20  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x180050c25  jmp     loc_1800509E1
0x180050c2a  mov     rcx, [rsp+350h+var_310]
0x180050c2f  mov     rax, [rcx]
0x180050c32  mov     rax, [rax+68h]
0x180050c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c3b  test    eax, eax
0x180050c3d  jnz     loc_180050A34
0x180050c43  xor     edx, edx; Val
0x180050c45  mov     r8d, 130h; Size
0x180050c4b  lea     rcx, [rbp+250h+var_290]; void *
0x180050c4f  call    memset_0
0x180050c54  mov     rcx, [r14+28h]
0x180050c58  mov     rax, [rcx]
0x180050c5b  lea     rdx, [rbp+250h+var_290]
0x180050c5f  mov     rax, [rax+40h]
0x180050c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c68  mov     ebx, eax
0x180050c6a  test    eax, eax
0x180050c6c  js      loc_180050D13
0x180050c72  mov     [rsp+350h+var_308], r15
0x180050c77  lea     rcx, [rsp+350h+var_308]
0x180050c7c  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x180050c81  mov     rdx, rax; ppFactory
0x180050c84  lea     rcx, _GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a; riid
0x180050c8b  call    cs:__imp_CreateDXGIFactory1
0x180050c91  mov     ebx, eax
0x180050c93  test    eax, eax
0x180050c95  js      loc_180050D30
0x180050c9b  mov     [rsp+350h+var_300], r15
0x180050ca0  mov     r11, [rsp+350h+var_308]
0x180050ca5  mov     rax, [r11]
0x180050ca8  mov     r10, [rax+0D0h]
0x180050caf  mov     [rsp+350h+var_300], r15
0x180050cb4  lea     rcx, [rsp+350h+var_300]
0x180050cb9  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x180050cbe  mov     r9, rax
0x180050cc1  lea     r8, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0
0x180050cc8  mov     rdx, [rbp+250h+var_168]
0x180050ccf  mov     rcx, r11
0x180050cd2  mov     rax, r10
0x180050cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050cda  test    eax, eax
0x180050cdc  jns     loc_180050B5B
0x180050ce2  mov     sil, r15b
0x180050ce5  jmp     loc_1800509FD
0x180050cea  mov     eax, dword ptr [rbp+250h+var_168]
0x180050cf0  cmp     dword ptr [rbp+250h+var_38], eax
0x180050cf6  jnz     loc_180050BB8
0x180050cfc  mov     eax, dword ptr [rbp+250h+var_168+4]
0x180050d02  cmp     dword ptr [rbp+250h+var_38+4], eax
0x180050d08  jz      loc_1800509E1
0x180050d0e  jmp     loc_180050BB8
0x180050d13  mov     rcx, [rbp+258h]; this
0x180050d1a  mov     r9d, eax; char *
0x180050d1d  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x180050d24  mov     edx, 120h; void *
0x180050d29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050d2e  jmp     short loc_180050D57
0x180050d30  mov     rcx, [rbp+258h]; this
0x180050d37  mov     r9d, eax; char *
0x180050d3a  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x180050d41  mov     edx, 123h; void *
0x180050d46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050d4b  nop
0x180050d4c  lea     rcx, [rsp+350h+var_308]
0x180050d51  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x180050d56  nop
0x180050d57  lea     rcx, [rsp+350h+var_310]
0x180050d5c  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x180050d61  jmp     loc_1800509DD
0x180050d66  mov     rax, [rcx]
0x180050d69  mov     rax, [rax+10h]
0x180050d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d72  jmp     loc_180050A91
0x180050d77  mov     rax, [rcx]
0x180050d7a  mov     rax, [rax+8]
  ... truncated ...
```
