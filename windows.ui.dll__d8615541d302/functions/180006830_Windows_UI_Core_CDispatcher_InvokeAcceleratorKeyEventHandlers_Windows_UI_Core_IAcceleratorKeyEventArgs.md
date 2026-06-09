# Windows::UI::Core::CDispatcher::InvokeAcceleratorKeyEventHandlers(Windows::UI::Core::IAcceleratorKeyEventArgs *)

- ea: `0x180006830`
- end: `0x180006c1f`
- name: `?InvokeAcceleratorKeyEventHandlers@CDispatcher@Core@UI@Windows@@QEAAJPEAUIAcceleratorKeyEventArgs@234@@Z`
- size: `1007`
- prototype: `__int64 __fastcall(Windows::UI::Core::CDispatcher *__hidden this, struct Windows::UI::Core::IAcceleratorKeyEventArgs *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006470`
- `0x18006f370`

## callees

- `0x1800038e0`
- `0x180006830`
- `0x180006c30`
- `0x180006c58`
- `0x180014754`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006a60`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006a60`

## string_xrefs

- `0x1800069f2`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`
- `0x180006a29`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`
- `0x180006aa8`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`
- `0x180006ae0`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`
- `0x180006b3a`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`
- `0x180006b72`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::UI::Core::CDispatcher::InvokeAcceleratorKeyEventHandlers(
        Windows::UI::Core::CDispatcher *this,
        struct Windows::UI::Core::IAcceleratorKeyEventArgs *a2)
{
  unsigned int v4; // r14d
  __int64 (__fastcall *v5)(struct Windows::UI::Core::IAcceleratorKeyEventArgs *, GUID *, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax
  char v10; // al
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  unsigned __int64 v23; // rax
  int v24; // [rsp+20h] [rbp-60h] BYREF
  __int64 v25; // [rsp+28h] [rbp-58h] BYREF
  int v26; // [rsp+30h] [rbp-50h] BYREF
  int v27; // [rsp+34h] [rbp-4Ch] BYREF
  __int128 v28; // [rsp+38h] [rbp-48h] BYREF
  __int128 v29; // [rsp+48h] [rbp-38h]
  __int128 v30; // [rsp+58h] [rbp-28h]
  __int64 v31; // [rsp+68h] [rbp-18h] BYREF
  int v32; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( (unsigned int)Windows::UI::Core::CDispatcher::CheckAccess(this) )
  {
    v4 = -2147024809;
    if ( !a2 )
      return v4;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    LOBYTE(v24) = 0;
    v25 = 0;
    v5 = **(__int64 (__fastcall ***)(struct Windows::UI::Core::IAcceleratorKeyEventArgs *, GUID *, __int64 *))a2;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
    v6 = v5(a2, &GUID_272b1ef3_c633_4da5_a26c_c6d0f56b29da, &v25);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v27 = 0;
      v26 = 0;
      v8 = (*(__int64 (__fastcall **)(struct Windows::UI::Core::IAcceleratorKeyEventArgs *, int *))(*(_QWORD *)a2 + 48LL))(
             a2,
             &v27);
      v7 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x575,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
          (const char *)(unsigned int)v8,
          v24);
        v16 = v25;
        if ( v25 )
        {
          v25 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        return v7;
      }
      v9 = (*(__int64 (__fastcall **)(struct Windows::UI::Core::IAcceleratorKeyEventArgs *, int *))(*(_QWORD *)a2 + 56LL))(
             a2,
             &v26);
      v7 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x576,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
          (const char *)(unsigned int)v9,
          v24);
        v15 = v25;
        if ( v25 )
        {
          v25 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        return v7;
      }
      if ( *((_QWORD *)this + 16) )
      {
        v31 = 0;
        v32 = 0;
        v21 = (*(__int64 (__fastcall **)(struct Windows::UI::Core::IAcceleratorKeyEventArgs *, __int64 *))(*(_QWORD *)a2 + 64LL))(
                a2,
                &v31);
        v7 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x57B,
            (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
            (const char *)(unsigned int)v21,
            v24);
          v22 = v25;
          if ( v25 )
          {
            v25 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          return v7;
        }
        DWORD2(v28) = v27 + 256;
        *(_QWORD *)&v29 = v26;
        v23 = (unsigned __int16)v31 | ((unsigned __int64)BYTE4(v31) << 16) | *((_QWORD *)&v29 + 1);
        *((_QWORD *)&v29 + 1) = v23;
        if ( (_BYTE)v32 )
        {
          v23 |= 0x1000000u;
          *((_QWORD *)&v29 + 1) = v23;
        }
        if ( BYTE1(v32) )
        {
          v23 |= 0x20000000u;
          *((_QWORD *)&v29 + 1) = v23;
        }
        if ( BYTE2(v32) )
        {
          v23 |= 0x40000000u;
          *((_QWORD *)&v29 + 1) = v23;
        }
        if ( HIBYTE(v32) )
          *((_QWORD *)&v29 + 1) = v23 | 0x80000000;
        (*(void (__fastcall **)(_QWORD, __int128 *, int *))(**((_QWORD **)this + 16) + 24LL))(
          *((_QWORD *)this + 16),
          &v28,
          &v24);
      }
      v10 = v24;
      if ( !(_BYTE)v24 )
      {
        v4 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Devices::Input::MouseDevice *,Windows::Devices::Input::MouseEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::Devices::Input::CMouseDevice *,CMouseEventArgs *>(
               (char *)this + 136,
               this,
               a2);
        v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 48LL))(v25, &v24);
        v7 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x599,
            (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
            (const char *)(unsigned int)v11,
            v24);
          v20 = v25;
          if ( v25 )
          {
            v25 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          return v7;
        }
        v10 = v24;
      }
      v12 = *((_QWORD *)this + 16);
      if ( v12 )
      {
        if ( !v10 )
        {
          (*(void (__fastcall **)(__int64, __int128 *, int *))(*(_QWORD *)v12 + 32LL))(v12, &v28, &v24);
          LOBYTE(v17) = v24;
          v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 56LL))(v25, v17);
          v7 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x59F,
              (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
              (const char *)(unsigned int)v18,
              v24);
            v19 = v25;
            if ( v25 )
            {
              v25 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            }
            return v7;
          }
        }
      }
      if ( (v27 & 0xFFFFFFFB) != 0 )
      {
        if ( ((v27 - 1) & 0xFFFFFFFB) == 0 )
        {
          *((_BYTE *)this + v26 + 249) = 0;
          if ( (_BYTE)v24 )
            *((_BYTE *)this + v26 + 505) = 0;
        }
      }
      else
      {
        *((_BYTE *)this + v26 + 249) = 1;
        *((_BYTE *)this + v26 + 505) = (_BYTE)v24 == 1;
      }
      v13 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return v4;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x570,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
      (const char *)(unsigned int)v6,
      v24);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
  }
  else
  {
    v7 = -2147417842;
    RoOriginateError(2147549454LL, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x180006830  mov     [rsp-28h+arg_10], rbx
0x180006835  push    rbp
0x180006836  push    rsi
0x180006837  push    rdi
0x180006838  push    r14
0x18000683a  push    r15
0x18000683c  mov     rbp, rsp
0x18000683f  sub     rsp, 80h
0x180006846  mov     rax, cs:__security_cookie
0x18000684d  xor     rax, rsp
0x180006850  mov     [rbp+var_8], rax
0x180006854  mov     rsi, rdx
0x180006857  mov     rdi, rcx
0x18000685a  call    ?CheckAccess@CDispatcher@Core@UI@Windows@@QEAAHXZ; Windows::UI::Core::CDispatcher::CheckAccess(void)
0x18000685f  xor     r15d, r15d
0x180006862  test    eax, eax
0x180006864  jz      loc_180006A57
0x18000686a  mov     r14d, 80070057h
0x180006870  test    rsi, rsi
0x180006873  jz      loc_18000699F
0x180006879  xorps   xmm0, xmm0
0x18000687c  movups  [rbp+var_48], xmm0
0x180006880  movups  [rbp+var_38], xmm0
0x180006884  movups  [rbp+var_28], xmm0
0x180006888  mov     byte ptr [rbp+var_60], r15b
0x18000688c  mov     [rbp+var_58], r15
0x180006890  mov     rax, [rsi]
0x180006893  mov     rbx, [rax]
0x180006896  lea     rcx, [rbp+var_58]
0x18000689a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000689f  lea     r8, [rbp+var_58]
0x1800068a3  lea     rdx, _GUID_272b1ef3_c633_4da5_a26c_c6d0f56b29da
0x1800068aa  mov     rcx, rsi
0x1800068ad  mov     rax, rbx
0x1800068b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b5  mov     ebx, eax
0x1800068b7  test    eax, eax
0x1800068b9  js      loc_180006B6B
0x1800068bf  mov     [rbp+var_4C], r15d
0x1800068c3  mov     [rbp+var_50], r15d
0x1800068c7  mov     rax, [rsi]
0x1800068ca  lea     rdx, [rbp+var_4C]
0x1800068ce  mov     rcx, rsi
0x1800068d1  mov     rax, [rax+30h]
0x1800068d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068da  mov     ebx, eax
0x1800068dc  test    eax, eax
0x1800068de  js      loc_180006A22
0x1800068e4  mov     rax, [rsi]
0x1800068e7  lea     rdx, [rbp+var_50]
0x1800068eb  mov     rcx, rsi
0x1800068ee  mov     rax, [rax+38h]
0x1800068f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f7  mov     ebx, eax
0x1800068f9  test    eax, eax
0x1800068fb  js      loc_1800069EB
0x180006901  cmp     [rdi+80h], r15
0x180006908  jnz     loc_180006B11
0x18000690e  mov     al, byte ptr [rbp+var_60]
0x180006911  test    al, al
0x180006913  jnz     short loc_18000694B
0x180006915  lea     rcx, [rdi+88h]
0x18000691c  mov     r8, rsi
0x18000691f  mov     rdx, rdi
0x180006922  call    ??$InvokeAll@PEAVCMouseDevice@Input@Devices@Windows@@PEAVCMouseEventArgs@@@?$EventSource@U?$ITypedEventHandler@PEAVMouseDevice@Input@Devices@Windows@@PEAVMouseEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVCMouseDevice@Input@Devices@Windows@@PEAVCMouseEventArgs@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Devices::Input::MouseDevice *,Windows::Devices::Input::MouseEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::Devices::Input::CMouseDevice *,CMouseEventArgs *>(Windows::Devices::Input::CMouseDevice *,CMouseEventArgs *)
0x180006927  mov     r14d, eax
0x18000692a  mov     rcx, [rbp+var_58]
0x18000692e  mov     rax, [rcx]
0x180006931  lea     rdx, [rbp+var_60]
0x180006935  mov     rax, [rax+30h]
0x180006939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000693e  mov     ebx, eax
0x180006940  test    eax, eax
0x180006942  js      loc_180006AD9
0x180006948  mov     al, byte ptr [rbp+var_60]
0x18000694b  mov     rcx, [rdi+80h]
0x180006952  test    rcx, rcx
0x180006955  jnz     loc_180006A68
0x18000695b  mov     eax, [rbp+var_4C]
0x18000695e  mov     ecx, 0FFFFFFFBh
0x180006963  test    ecx, eax
0x180006965  jnz     short loc_1800069C5
0x180006967  movsxd  rax, [rbp+var_50]
0x18000696b  mov     byte ptr [rax+rdi+0F9h], 1
0x180006973  cmp     byte ptr [rbp+var_60], 1
0x180006977  setz    cl
0x18000697a  movsxd  rax, [rbp+var_50]
0x18000697e  mov     [rax+rdi+1F9h], cl
0x180006985  mov     rcx, [rbp+var_58]
0x180006989  test    rcx, rcx
0x18000698c  jz      short loc_18000699F
0x18000698e  mov     [rbp+var_58], r15
0x180006992  mov     rdx, [rcx]
0x180006995  mov     rax, [rdx+10h]
0x180006999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699e  nop
0x18000699f  mov     eax, r14d
0x1800069a2  mov     rcx, [rbp+var_8]
0x1800069a6  xor     rcx, rsp; StackCookie
0x1800069a9  call    __security_check_cookie
0x1800069ae  mov     rbx, [rsp+80h+arg_10]
0x1800069b6  add     rsp, 80h
0x1800069bd  pop     r15
0x1800069bf  pop     r14
0x1800069c1  pop     rdi
0x1800069c2  pop     rsi
0x1800069c3  pop     rbp
0x1800069c4  retn
0x1800069c5  dec     eax
0x1800069c7  test    ecx, eax
0x1800069c9  jnz     short loc_180006985
0x1800069cb  movsxd  rax, [rbp+var_50]
0x1800069cf  mov     [rax+rdi+0F9h], r15b
0x1800069d7  cmp     byte ptr [rbp+var_60], r15b
0x1800069db  jz      short loc_180006985
0x1800069dd  movsxd  rax, [rbp+var_50]
0x1800069e1  mov     [rax+rdi+1F9h], r15b
0x1800069e9  jmp     short loc_180006985
0x1800069eb  mov     rcx, [rbp+28h]; this
0x1800069ef  mov     r9d, ebx; char *
0x1800069f2  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800069f9  mov     edx, 576h; void *
0x1800069fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a03  nop
0x180006a04  mov     rcx, [rbp+var_58]
0x180006a08  test    rcx, rcx
0x180006a0b  jz      short loc_180006A1E
0x180006a0d  mov     [rbp+var_58], r15
0x180006a11  mov     rax, [rcx]
0x180006a14  mov     rax, [rax+10h]
0x180006a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1d  nop
0x180006a1e  mov     eax, ebx
0x180006a20  jmp     short loc_1800069A2
0x180006a22  mov     rcx, [rbp+28h]; this
0x180006a26  mov     r9d, ebx; char *
0x180006a29  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180006a30  mov     edx, 575h; void *
0x180006a35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a3a  nop
0x180006a3b  mov     rcx, [rbp+var_58]
0x180006a3f  test    rcx, rcx
0x180006a42  jz      short loc_180006A55
0x180006a44  mov     [rbp+var_58], r15
0x180006a48  mov     rax, [rcx]
0x180006a4b  mov     rax, [rax+10h]
0x180006a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a54  nop
0x180006a55  jmp     short loc_180006A1E
0x180006a57  xor     edx, edx
0x180006a59  mov     ebx, 8001010Eh
0x180006a5e  mov     ecx, ebx
0x180006a60  call    cs:__imp_RoOriginateError
0x180006a66  jmp     short loc_180006A1E
0x180006a68  test    al, al
0x180006a6a  jnz     loc_18000695B
0x180006a70  mov     rax, [rcx]
0x180006a73  lea     r8, [rbp+var_60]
0x180006a77  lea     rdx, [rbp+var_48]
0x180006a7b  mov     rax, [rax+20h]
0x180006a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a84  mov     rcx, [rbp+var_58]
0x180006a88  mov     rax, [rcx]
0x180006a8b  mov     dl, byte ptr [rbp+var_60]
0x180006a8e  mov     rax, [rax+38h]
0x180006a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a97  mov     ebx, eax
0x180006a99  test    eax, eax
0x180006a9b  jns     loc_18000695B
0x180006aa1  mov     rcx, [rbp+28h]; this
0x180006aa5  mov     r9d, eax; char *
0x180006aa8  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180006aaf  mov     edx, 59Fh; void *
0x180006ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ab9  nop
0x180006aba  mov     rcx, [rbp+var_58]
0x180006abe  test    rcx, rcx
0x180006ac1  jz      short loc_180006AD4
0x180006ac3  mov     [rbp+var_58], r15
0x180006ac7  mov     rax, [rcx]
0x180006aca  mov     rax, [rax+10h]
0x180006ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad3  nop
0x180006ad4  jmp     loc_180006A1E
0x180006ad9  mov     rcx, [rbp+28h]; this
0x180006add  mov     r9d, ebx; char *
0x180006ae0  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180006ae7  mov     edx, 599h; void *
0x180006aec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006af1  nop
0x180006af2  mov     rcx, [rbp+var_58]
0x180006af6  test    rcx, rcx
0x180006af9  jz      short loc_180006B0C
0x180006afb  mov     [rbp+var_58], r15
0x180006aff  mov     rax, [rcx]
0x180006b02  mov     rax, [rax+10h]
0x180006b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0b  nop
0x180006b0c  jmp     loc_180006A1E
0x180006b11  xor     eax, eax
0x180006b13  mov     [rbp+var_18], rax
0x180006b17  mov     [rbp+var_10], eax
0x180006b1a  mov     rax, [rsi]
0x180006b1d  lea     rdx, [rbp+var_18]
0x180006b21  mov     rcx, rsi
0x180006b24  mov     rax, [rax+40h]
0x180006b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b2d  mov     ebx, eax
0x180006b2f  test    eax, eax
0x180006b31  jns     short loc_180006B92
0x180006b33  mov     rcx, [rbp+28h]; this
0x180006b37  mov     r9d, eax; char *
0x180006b3a  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180006b41  mov     edx, 57Bh; void *
0x180006b46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b4b  nop
0x180006b4c  mov     rcx, [rbp+var_58]
0x180006b50  test    rcx, rcx
0x180006b53  jz      short loc_180006B66
0x180006b55  mov     [rbp+var_58], r15
0x180006b59  mov     rax, [rcx]
0x180006b5c  mov     rax, [rax+10h]
0x180006b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b65  nop
0x180006b66  jmp     loc_180006A1E
0x180006b6b  mov     rcx, [rbp+28h]; this
0x180006b6f  mov     r9d, ebx; char *
0x180006b72  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180006b79  mov     edx, 570h; void *
0x180006b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b83  nop
0x180006b84  lea     rcx, [rbp+var_58]
0x180006b88  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006b8d  jmp     loc_180006A1E
0x180006b92  mov     eax, [rbp+var_4C]
0x180006b95  add     eax, 100h
0x180006b9a  mov     dword ptr [rbp+var_48+8], eax
0x180006b9d  movsxd  rax, [rbp+var_50]
0x180006ba1  mov     qword ptr [rbp+var_38], rax
0x180006ba5  movzx   ecx, byte ptr [rbp+var_18+4]
0x180006ba9  shl     rcx, 10h
0x180006bad  movzx   eax, word ptr [rbp+var_18]
0x180006bb1  or      rcx, rax
0x180006bb4  mov     rax, qword ptr [rbp+var_38+8]
0x180006bb8  or      rax, rcx
0x180006bbb  mov     qword ptr [rbp+var_38+8], rax
0x180006bbf  cmp     byte ptr [rbp+var_10], r15b
0x180006bc3  jz      short loc_180006BCE
0x180006bc5  bts     rax, 18h
0x180006bca  mov     qword ptr [rbp+var_38+8], rax
0x180006bce  cmp     byte ptr [rbp+var_10+1], r15b
0x180006bd2  jz      short loc_180006BDD
0x180006bd4  bts     rax, 1Dh
0x180006bd9  mov     qword ptr [rbp+var_38+8], rax
0x180006bdd  cmp     byte ptr [rbp+var_10+2], r15b
0x180006be1  jz      short loc_180006BEC
0x180006be3  bts     rax, 1Eh
0x180006be8  mov     qword ptr [rbp+var_38+8], rax
0x180006bec  cmp     byte ptr [rbp+var_10+3], r15b
0x180006bf0  jz      short loc_180006BFE
0x180006bf2  mov     ecx, 80000000h
0x180006bf7  or      rax, rcx
0x180006bfa  mov     qword ptr [rbp+var_38+8], rax
0x180006bfe  mov     rcx, [rdi+80h]
0x180006c05  mov     rax, [rcx]
0x180006c08  lea     r8, [rbp+var_60]
0x180006c0c  lea     rdx, [rbp+var_48]
0x180006c10  mov     rax, [rax+18h]
0x180006c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c19  jmp     loc_18000690E
```
