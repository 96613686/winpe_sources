# CAutoplayDialog::InitNoContentAutoplay(IAutoPlayDeviceDataManager *,_GUID const &,ushort const *,ulong,int,ushort const *,ushort const *,ushort const *)

- ea: `0x1800ada80`
- end: `0x1800add21`
- name: `?InitNoContentAutoplay@CAutoplayDialog@@UEAAJPEAUIAutoPlayDeviceDataManager@@AEBU_GUID@@PEBGKH222@Z`
- size: `673`
- prototype: `__int64 __usercall@<rax>(CAutoplayDialog *__hidden this@<rcx>, struct IAutoPlayDeviceDataManager *@<rdx>, const struct _GUID *@<r8>, const unsigned __int16 *@<r9>, unsigned int, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ad960`

## callees

- `0x180054000`
- `0x180054170`
- `0x1800885ec`
- `0x18008c65c`
- `0x1800ada80`
- `0x180107164`
- `0x18018c430`
- `0x180191c90`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800adb91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800adbbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800adb91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800adbbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800adce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800adcf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800adcfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800add05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800adce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800adcf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800adcfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800add05`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800adb1c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800adb1c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800adbff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800adbff`

## pseudocode

```c
__int64 __fastcall CAutoplayDialog::InitNoContentAutoplay(
        CAutoplayDialog *this,
        struct IAutoPlayDeviceDataManager *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        const unsigned __int16 *a9)
{
  PVOID v13; // rcx
  HRESULT Instance; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  HANDLE EventW; // rax
  HANDLE v19; // rax
  _QWORD *v20; // rsi
  __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned __int16 *v24; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 *v25; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+38h] BYREF

  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_e749d865168d34635d0bc124a43c07cf_Traceguids, a4);
  }
  Instance = _AllocString<CTCoAllocPolicy>(v13, a2, a4, (char *)this + 16);
  if ( Instance >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::UI::Xaml::Interop::IBindableObservableVector>::operator=((char *)this + 376, a2);
    *((_DWORD *)this + 82) = a5;
    *((_DWORD *)this + 106) = a6;
    *((struct _GUID *)this + 7) = *a3;
    if ( StringFromGUID2((const GUID *const)this + 7, (LPOLESTR)this + 16, 39) )
    {
      Instance = 0;
      if ( a7 )
        Instance = _AllocString<CTCoAllocPolicy>(v16, v15, a7, (char *)this + 432);
      if ( a8 )
        Instance = _AllocString<CTCoAllocPolicy>(v16, v15, a8, (char *)this + 24);
      if ( Instance >= 0 )
      {
        if ( !a9
          || (v17 = _AllocString<CTCoAllocPolicy>(v16, v15, a9, (char *)this + 440),
              *((_DWORD *)this + 82) |= 4u,
              Instance = v17,
              v17 >= 0) )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)this + 45) = EventW;
          if ( EventW || (Instance = ResultFromLastError(), Instance >= 0) )
          {
            v19 = CreateEventW(0, 1, 0, 0);
            *((_QWORD *)this + 46) = v19;
            if ( v19 || (Instance = ResultFromLastError(), Instance >= 0) )
            {
              v20 = (_QWORD *)((char *)this + 408);
              Instance = CoCreateInstance(
                           &CLSID_AutoplayDeviceHandler,
                           0,
                           3u,
                           &GUID_a74de05b_c901_4506_a161_7f66e5f908f9,
                           (LPVOID *)this + 51);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(*(_QWORD *)*v20 + 24LL))(
                             *v20,
                             a4);
                if ( Instance >= 0 )
                {
                  v21 = *v20;
                  v26 = 0;
                  Instance = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v21 + 72LL))(
                               v21,
                               &v26);
                  if ( Instance >= 0 )
                  {
                    v22 = *v20;
                    v25 = 0;
                    Instance = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v22 + 64LL))(
                                 v22,
                                 &v25);
                    if ( Instance >= 0 )
                    {
                      v24 = 0;
                      Instance = SHFormatResMessageArgAlloc(&_ImageBase, 9979, &v24);
                      if ( Instance >= 0 )
                      {
                        Instance = CAutoPlayHandlerChooser::Init(this, v26, v24, v25);
                        if ( Instance >= 0 )
                        {
                          pv = 0;
                          Instance = SHFormatResMessageArgAlloc(&_ImageBase, 9991, &pv);
                          if ( Instance >= 0 )
                          {
                            Instance = CAutoPlayHandlerChooser::SetToastText(this, (const unsigned __int16 *)pv);
                            CoTaskMemFree(pv);
                          }
                        }
                        CoTaskMemFree(v24);
                      }
                      CoTaskMemFree(v25);
                    }
                    CoTaskMemFree(v26);
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800ada80  push    rbp
0x1800ada82  push    rbx
0x1800ada83  push    rsi
0x1800ada84  push    rdi
0x1800ada85  push    r14
0x1800ada87  push    r15
0x1800ada89  mov     rbp, rsp
0x1800ada8c  sub     rsp, 58h
0x1800ada90  mov     r14, r9
0x1800ada93  mov     rsi, r8
0x1800ada96  mov     r15, rdx
0x1800ada99  mov     rdi, rcx
0x1800ada9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adaa3  lea     rax, WPP_GLOBAL_Control
0x1800adaaa  cmp     rcx, rax
0x1800adaad  jz      short loc_1800ADAD0
0x1800adaaf  test    byte ptr [rcx+44h], 1
0x1800adab3  jz      short loc_1800ADAD0
0x1800adab5  cmp     byte ptr [rcx+41h], 4
0x1800adab9  jb      short loc_1800ADAD0
0x1800adabb  mov     rcx, [rcx+38h]
0x1800adabf  lea     r8, WPP_e749d865168d34635d0bc124a43c07cf_Traceguids
0x1800adac6  mov     edx, 16h
0x1800adacb  call    WPP_SF_S
0x1800adad0  lea     r9, [rdi+10h]
0x1800adad4  mov     r8, r14
0x1800adad7  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800adadc  mov     ebx, eax
0x1800adade  test    eax, eax
0x1800adae0  js      loc_1800ADD12
0x1800adae6  lea     rcx, [rdi+178h]
0x1800adaed  mov     rdx, r15
0x1800adaf0  call    ??4?$ComPtr@UIBindableObservableVector@Interop@Xaml@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIBindableObservableVector@Interop@Xaml@UI@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::UI::Xaml::Interop::IBindableObservableVector>::operator=(Windows::UI::Xaml::Interop::IBindableObservableVector *)
0x1800adaf5  mov     eax, [rbp+arg_20]
0x1800adaf8  lea     rcx, [rdi+70h]; rguid
0x1800adafc  mov     [rdi+148h], eax
0x1800adb02  lea     rdx, [rdi+20h]; lpsz
0x1800adb06  mov     eax, [rbp+arg_28]
0x1800adb09  mov     r8d, 27h ; '''; cchMax
0x1800adb0f  mov     [rdi+1A8h], eax
0x1800adb15  movups  xmm0, xmmword ptr [rsi]
0x1800adb18  movdqu  xmmword ptr [rcx], xmm0
0x1800adb1c  call    cs:__imp_StringFromGUID2
0x1800adb22  test    eax, eax
0x1800adb24  jz      loc_1800ADD0D
0x1800adb2a  mov     r8, [rbp+arg_30]
0x1800adb2e  xor     ebx, ebx
0x1800adb30  test    r8, r8
0x1800adb33  jz      short loc_1800ADB43
0x1800adb35  lea     r9, [rdi+1B0h]
0x1800adb3c  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800adb41  mov     ebx, eax
0x1800adb43  mov     r8, [rbp+arg_38]
0x1800adb47  test    r8, r8
0x1800adb4a  jz      short loc_1800ADB57
0x1800adb4c  lea     r9, [rdi+18h]
0x1800adb50  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800adb55  mov     ebx, eax
0x1800adb57  test    ebx, ebx
0x1800adb59  js      loc_1800ADD12
0x1800adb5f  mov     r8, [rbp+arg_40]
0x1800adb63  test    r8, r8
0x1800adb66  jz      short loc_1800ADB85
0x1800adb68  lea     r9, [rdi+1B8h]
0x1800adb6f  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800adb74  or      dword ptr [rdi+148h], 4
0x1800adb7b  mov     ebx, eax
0x1800adb7d  test    eax, eax
0x1800adb7f  js      loc_1800ADD12
0x1800adb85  xor     r9d, r9d; lpName
0x1800adb88  xor     r8d, r8d; bInitialState
0x1800adb8b  xor     ecx, ecx; lpEventAttributes
0x1800adb8d  lea     edx, [r9+1]; bManualReset
0x1800adb91  call    cs:__imp_CreateEventW
0x1800adb97  mov     [rdi+168h], rax
0x1800adb9e  test    rax, rax
0x1800adba1  jnz     short loc_1800ADBB2
0x1800adba3  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800adba8  mov     ebx, eax
0x1800adbaa  test    eax, eax
0x1800adbac  js      loc_1800ADD12
0x1800adbb2  xor     r9d, r9d; lpName
0x1800adbb5  xor     r8d, r8d; bInitialState
0x1800adbb8  xor     ecx, ecx; lpEventAttributes
0x1800adbba  lea     edx, [r9+1]; bManualReset
0x1800adbbe  call    cs:__imp_CreateEventW
0x1800adbc4  mov     [rdi+170h], rax
0x1800adbcb  test    rax, rax
0x1800adbce  jnz     short loc_1800ADBDF
0x1800adbd0  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800adbd5  mov     ebx, eax
0x1800adbd7  test    eax, eax
0x1800adbd9  js      loc_1800ADD12
0x1800adbdf  xor     edx, edx; pUnkOuter
0x1800adbe1  lea     rsi, [rdi+198h]
0x1800adbe8  lea     r9, _GUID_a74de05b_c901_4506_a161_7f66e5f908f9; riid
0x1800adbef  mov     [rsp+58h+ppv], rsi; ppv
0x1800adbf4  lea     rcx, CLSID_AutoplayDeviceHandler; rclsid
0x1800adbfb  lea     r8d, [rdx+3]; dwClsContext
0x1800adbff  call    cs:__imp_CoCreateInstance
0x1800adc05  mov     ebx, eax
0x1800adc07  test    eax, eax
0x1800adc09  js      loc_1800ADD12
0x1800adc0f  mov     rcx, [rsi]
0x1800adc12  mov     rdx, r14
0x1800adc15  mov     rax, [rcx]
0x1800adc18  mov     rax, [rax+18h]
0x1800adc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc21  mov     ebx, eax
0x1800adc23  test    eax, eax
0x1800adc25  js      loc_1800ADD12
0x1800adc2b  mov     rcx, [rsi]
0x1800adc2e  lea     rdx, [rbp+var_18]
0x1800adc32  mov     [rbp+var_18], 0
0x1800adc3a  mov     rax, [rcx]
0x1800adc3d  mov     rax, [rax+48h]
0x1800adc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc46  mov     ebx, eax
0x1800adc48  test    eax, eax
0x1800adc4a  js      loc_1800ADD12
0x1800adc50  mov     rcx, [rsi]
0x1800adc53  lea     rdx, [rbp+var_20]
0x1800adc57  mov     [rbp+var_20], 0
0x1800adc5f  mov     rax, [rcx]
0x1800adc62  mov     rax, [rax+40h]
0x1800adc66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc6b  mov     ebx, eax
0x1800adc6d  test    eax, eax
0x1800adc6f  js      loc_1800ADD01
0x1800adc75  lea     r8, [rbp+var_28]
0x1800adc79  mov     [rbp+var_28], 0
0x1800adc81  mov     edx, 26FBh
0x1800adc86  lea     rcx, __ImageBase
0x1800adc8d  call    SHFormatResMessageArgAlloc
0x1800adc92  mov     ebx, eax
0x1800adc94  test    eax, eax
0x1800adc96  js      short loc_1800ADCF7
0x1800adc98  mov     r9, [rbp+var_20]; unsigned __int16 *
0x1800adc9c  mov     rcx, rdi; this
0x1800adc9f  mov     r8, [rbp+var_28]; unsigned __int16 *
0x1800adca3  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x1800adca7  call    ?Init@CAutoPlayHandlerChooser@@UEAAJPEBG00@Z; CAutoPlayHandlerChooser::Init(ushort const *,ushort const *,ushort const *)
0x1800adcac  mov     ebx, eax
0x1800adcae  test    eax, eax
0x1800adcb0  js      short loc_1800ADCED
0x1800adcb2  lea     r8, [rbp+pv]
0x1800adcb6  mov     [rbp+pv], 0
0x1800adcbe  mov     edx, 2707h
0x1800adcc3  lea     rcx, __ImageBase
0x1800adcca  call    SHFormatResMessageArgAlloc
0x1800adccf  mov     ebx, eax
0x1800adcd1  test    eax, eax
0x1800adcd3  js      short loc_1800ADCED
0x1800adcd5  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800adcd9  mov     rcx, rdi; this
0x1800adcdc  call    ?SetToastText@CAutoPlayHandlerChooser@@IEAAJPEBG@Z; CAutoPlayHandlerChooser::SetToastText(ushort const *)
0x1800adce1  mov     rcx, [rbp+pv]; pv
0x1800adce5  mov     ebx, eax
0x1800adce7  call    cs:__imp_CoTaskMemFree
0x1800adced  mov     rcx, [rbp+var_28]; pv
0x1800adcf1  call    cs:__imp_CoTaskMemFree
0x1800adcf7  mov     rcx, [rbp+var_20]; pv
0x1800adcfb  call    cs:__imp_CoTaskMemFree
0x1800add01  mov     rcx, [rbp+var_18]; pv
0x1800add05  call    cs:__imp_CoTaskMemFree
0x1800add0b  jmp     short loc_1800ADD12
0x1800add0d  mov     ebx, 80004005h
0x1800add12  mov     eax, ebx
0x1800add14  add     rsp, 58h
0x1800add18  pop     r15
0x1800add1a  pop     r14
0x1800add1c  pop     rdi
0x1800add1d  pop     rsi
0x1800add1e  pop     rbx
0x1800add1f  pop     rbp
0x1800add20  retn
```
